# JanusVLN Tutorial — Docker Version

This document explains how to run inference with JanusVLN_Base on the R2R `val_unseen` split via Docker on a Linux machine equipped with NVIDIA GPUs.

The Docker image includes the JanusVLN source code and the complete runtime environment, but it does not include the model weights, Matterport3D scene data, R2R episodes, or inference outputs. Users must download these resources separately and mount them into the container.

## 1. Verified Environment

The current image has been verified in the following environment:

- Linux x86_64
- 8 × NVIDIA RTX A6000 GPUs, each with 48 GB of VRAM
- NVIDIA Driver 550.54.14
- Python 3.9.23
- PyTorch 2.5.0 + CUDA 12.4
- Habitat-Sim / Habitat-Lab 0.2.4
- Transformers 4.50.0
- Flash Attention 2.7.1.post4
- JanusVLN source commit: `64ac8373c1e3c4a810a999cad536f633f2277d68`

The number of processes can be adjusted to match the number of available GPUs. Inference can be started on a single GPU, but completing the full `val_unseen` split will be very slow. The image has currently been verified only on GPUs with 48 GB of VRAM. GPUs with 24 GB of VRAM have not yet been tested and may run out of memory.

It is recommended to reserve at least 80 GB of free disk space for the image, model, dataset, downloaded archives, and output files.

## 2. Install Docker and NVIDIA Container Support

First, follow the official documentation to install:

- [Docker Engine](https://docs.docker.com/engine/install/)
- [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html)

After installation, run:

```bash
nvidia-smi
docker run --rm --runtime=nvidia --gpus all \
  nvidia/cuda:12.4.1-base-ubuntu22.04 nvidia-smi
```

Both commands should display the GPU information correctly. Users do not need to install Conda, PyTorch, Habitat, or the CUDA Toolkit on the host because they are already included in the image.

## 3. Create the Working Directory

```bash
mkdir -p janusvln-reproduce/{models,data/datasets,data/scene_datasets,outputs,downloads}
cd janusvln-reproduce
export JANUSVLN_HOME="$PWD"
```

Run all subsequent commands from the `janusvln-reproduce` directory.

## 4. Download the JanusVLN_Base Model

Model page: [ModelScope — misstl/JanusVLN_Base](https://www.modelscope.cn/models/misstl/JanusVLN_Base)

The model is approximately 18 GB. Git LFS is recommended for downloading it:

```bash
git lfs install
git clone https://www.modelscope.cn/misstl/JanusVLN_Base.git \
  models/JanusVLN_Base
```

After downloading, check the weight files:

```bash
ls -lh models/JanusVLN_Base/model-0000*-of-00004.safetensors
du -sh models/JanusVLN_Base
```

You should see four `safetensors` shards, with a total directory size of approximately 18 GB.

## 5. Prepare the Matterport3D Scenes

R2R inference uses MP3D scenes. Because MP3D is subject to dataset licensing terms, it cannot be redistributed with the Docker image. Users must request access through the [official Matterport3D page](https://niessner.github.io/Matterport/) and obtain the official `download_mp.py` script.

The download command provided in the official Habitat documentation is:

```bash
python2 downloads/download_mp.py \
  --task habitat \
  -o "$JANUSVLN_HOME/data/scene_datasets/mp3d"
```

Only the Habitat version is required; the complete original Matterport3D dataset is not needed. Once the download is complete, the final directory structure must be as follows:

```text
data/scene_datasets/mp3d/
├── 17DRP5sb8fy/
│   ├── 17DRP5sb8fy.glb
│   ├── 17DRP5sb8fy.house
│   └── 17DRP5sb8fy.navmesh
├── 1LXtFkjw3qL/
│   └── ...
└── ...
```

You can verify the data with the following commands:

```bash
find data/scene_datasets/mp3d -mindepth 1 -maxdepth 1 -type d | wc -l
find data/scene_datasets/mp3d -maxdepth 2 -name '*.glb' | head
du -sh data/scene_datasets/mp3d
```

The complete MP3D Habitat dataset should contain 90 scenes. The copy verified for this tutorial is approximately 21 GB. If the download tool creates an additional `v1/scans/` hierarchy, move the 90 scene directories within it directly under the `mp3d/` directory shown above.

Official Habitat dataset documentation: [Habitat-Sim DATASETS.md](https://github.com/facebookresearch/habitat-sim/blob/main/DATASETS.md#matterport3d-mp3d-dataset)

## 6. Download the R2R VLN-CE Episodes

The JanusVLN project provides the following download link for the R2R data:

<https://drive.google.com/file/d/1fo8F4NKgZDH-bPSdVU3cONAkt5EW-tyr/view>

Download and extract the archive:

```bash
python3 -m pip install --user gdown
gdown --fuzzy \
  'https://drive.google.com/file/d/1fo8F4NKgZDH-bPSdVU3cONAkt5EW-tyr/view' \
  -O downloads/R2R_VLNCE_v1-3_preprocessed.zip

mkdir -p downloads/r2r-unpacked
unzip downloads/R2R_VLNCE_v1-3_preprocessed.zip \
  -d downloads/r2r-unpacked
mv downloads/r2r-unpacked/R2R_VLNCE_v1-3_preprocessed \
  data/datasets/r2r
```

After extraction, verify the files:

```bash
ls -lh data/datasets/r2r/val_unseen/val_unseen.json.gz
ls -lh data/datasets/r2r/val_seen/val_seen.json.gz
du -sh data/datasets/r2r
```

In the verified dataset, `val_unseen` contains 1,839 episodes across 11 scenes, while `val_seen` contains 778 episodes across 53 scenes. The R2R episodes occupy approximately 251 MB in total.

## 7. Verify the Final Directory Structure

```text
janusvln-reproduce/
├── models/
│   └── JanusVLN_Base/
│       ├── config.json
│       ├── model-00001-of-00004.safetensors
│       └── ...
├── data/
│   ├── datasets/
│   │   └── r2r/
│   │       ├── val_seen/
│   │       └── val_unseen/
│   └── scene_datasets/
│       └── mp3d/
│           ├── 17DRP5sb8fy/
│           └── ...
├── outputs/
└── downloads/
```

## 8. Pull and Verify the Docker Image

The official image repository is hosted on Docker Hub at [`amapcvlab/janusvln`](https://hub.docker.com/r/amapcvlab/janusvln). The complete image reference is `docker.io/amapcvlab/janusvln:latest`. Once the repository is public, the image can be pulled without signing in. The current image is available only for Linux x86_64 (amd64).

> The image is currently being pushed to Docker Hub. Run the pull command below after the upload is complete and the repository page becomes accessible.

```bash
export JANUSVLN_IMAGE='docker.io/amapcvlab/janusvln:latest'
docker pull "$JANUSVLN_IMAGE"
```

After pulling the image, verify its architecture and local digest:

```bash
docker image inspect "$JANUSVLN_IMAGE" \
  --format 'architecture={{.Architecture}} image_id={{.Id}}'
docker image ls --digests amapcvlab/janusvln
```

First, verify the environment and GPU access:

```bash
docker run --rm \
  --runtime=nvidia \
  --gpus all \
  "$JANUSVLN_IMAGE" \
  python /usr/local/bin/verify_env.py
```

The expected output should include:

```text
JanusVLN: 0.1.0
habitat-lab: 0.2.4
habitat-sim: 0.2.4
torch: 2.5.0+cu124
transformers: 4.50.0
CUDA available: True
JanusVLN environment verification passed.
```

## 9. Run R2R `val_unseen` Inference

### 9.1 Single GPU

```bash
mkdir -p outputs/r2r_val_unseen_1gpu

docker run --rm \
  --runtime=nvidia \
  --gpus device=0 \
  --shm-size=16g \
  -v "$JANUSVLN_HOME/models/JanusVLN_Base:/models/JanusVLN_Base:ro" \
  -v "$JANUSVLN_HOME/data:/workspace/JanusVLN/data:ro" \
  -v "$JANUSVLN_HOME/outputs/r2r_val_unseen_1gpu:/outputs" \
  -e CHECKPOINT=/models/JanusVLN_Base \
  -e OUTPUT_PATH=/outputs \
  -e CONFIG=config/vln_r2r.yaml \
  -e NPROC_PER_NODE=1 \
  -e SAVE_VIDEO=0 \
  "$JANUSVLN_IMAGE" \
  bash scripts/evaluation_docker.sh
```

### 9.2 All Visible GPUs

```bash
GPU_COUNT="$(nvidia-smi --query-gpu=index --format=csv,noheader | wc -l)"
mkdir -p outputs/r2r_val_unseen_multigpu

docker run --rm \
  --runtime=nvidia \
  --gpus all \
  --shm-size=16g \
  -v "$JANUSVLN_HOME/models/JanusVLN_Base:/models/JanusVLN_Base:ro" \
  -v "$JANUSVLN_HOME/data:/workspace/JanusVLN/data:ro" \
  -v "$JANUSVLN_HOME/outputs/r2r_val_unseen_multigpu:/outputs" \
  -e CHECKPOINT=/models/JanusVLN_Base \
  -e OUTPUT_PATH=/outputs \
  -e CONFIG=config/vln_r2r.yaml \
  -e NPROC_PER_NODE="$GPU_COUNT" \
  -e SAVE_VIDEO=0 \
  "$JANUSVLN_IMAGE" \
  bash scripts/evaluation_docker.sh
```

The `--gpus` option exposes GPUs to the container, while `--runtime=nvidia` is also required for Habitat's headless EGL rendering. On the verified machine, omitting either option may prevent the container from starting successfully.

By default, the script evaluates the R2R `val_unseen` split. Each inference process uses one GPU, so `NPROC_PER_NODE` must not exceed the number of GPUs visible inside the container.

To save visualization videos, change `SAVE_VIDEO=0` to `SAVE_VIDEO=1`. By default, the program saves videos for approximately 5% of the episodes.

## 10. Check the Outputs

During inference, results are continuously written to:

```text
outputs/r2r_val_unseen_multigpu/result.json
```

Each line near the beginning of this file contains the result for one episode, including:

- `success`: whether the agent successfully reached the goal;
- `spl`: the SPL metric, which accounts for both success and path length;
- `os`: Oracle Success;
- `ne`: the navigation distance from the final position to the goal;
- `steps`: the number of executed steps.

After all episodes are complete, the aggregated results are appended to the end of the file:

```bash
tail -n 1 outputs/r2r_val_unseen_multigpu/result.json
```

After completing all 1,839 episodes on 8 RTX A6000 GPUs, this image produced:

```json
{
  "sucs_all": 0.5394236445426941,
  "spls_all": 0.5005337360665313,
  "oss_all": 0.5856444239616394,
  "ones_all": 5.106735706329346,
  "length": 1839
}
```

These values correspond to an NE of 5.1067, an OSR of 58.5644%, an SR of 53.9424%, and an SPL of 50.0534%. For a complete `val_unseen` evaluation, `length` should be 1839. If video saving is enabled, videos will appear in the `vis_0/` subdirectory of the output directory.

## 11. Evaluate the Test Results

It is recommended to verify all of the following:

1. `verify_env.py` reports that the environment verification passed and CUDA is available;
2. The final `length` value in `result.json` is 1839;
3. The logs contain no CUDA out-of-memory errors, EGL initialization failures, or missing scene files;
4. The aggregated Success, SPL, Oracle Success, and Navigation Error metrics are close to the published reference results.

For the same split, the paper reports an NE of 5.17, an OS of 58.0%, an SR of 52.8%, and an SPL of 49.2% for JanusVLN_Base without additional training data. The complete evaluation results from this image are consistent with the paper and slightly better on all four metrics. These small differences may result from rounding in the paper, GPU kernel behavior, or software-version differences; they do not indicate that the model received further training or improvement.

Navigation inference involves GPU kernels, Flash Attention, and Habitat simulation. Different GPU models, drivers, and parallelization settings may cause a small number of episode trajectories to differ. Therefore, reproducibility should be assessed by whether the aggregate metrics are close, rather than requiring every trajectory to match exactly at the bit level.

## 12. Troubleshooting

### `CUDA available: False`

Check the NVIDIA driver and NVIDIA Container Toolkit, and confirm that the `docker run` command includes `--runtime=nvidia --gpus ...`.

### EGL or Habitat-Sim Initialization Failure

Make sure that both `--runtime=nvidia` and `--gpus` are provided. Do not assume that Habitat is working correctly merely because PyTorch can detect CUDA.

### MP3D Scene Not Found

Verify that the host-side path has the following structure:

```text
data/scene_datasets/mp3d/17DRP5sb8fy/17DRP5sb8fy.glb
```

There must not be an additional `v1/scans/` level between `mp3d/` and the scene ID.

### Checkpoint Not Found

Check the following files:

```bash
test -f models/JanusVLN_Base/config.json
test -f models/JanusVLN_Base/model-00001-of-00004.safetensors
```

### CUDA Out of Memory

The current inference setup loads one complete model on each GPU. Reducing `NPROC_PER_NODE` does not reduce the VRAM used by an individual process. It is recommended to begin testing with a GPU that has at least 48 GB of VRAM.

### Resume After Interruption

The program continuously writes completed episodes to `result.json`. If a run is interrupted, it can be restarted with the same output directory, provided that the dataset and configuration have not changed. Do not mix outputs from different splits, models, or parameter settings in the same directory.

## Related Links

- [Official JanusVLN Repository](https://github.com/MIV-XJTU/JanusVLN)
- [JanusVLN_Base Model](https://www.modelscope.cn/models/misstl/JanusVLN_Base)
- [Matterport3D Dataset](https://niessner.github.io/Matterport/)
- [Habitat-Sim Dataset Preparation Guide](https://github.com/facebookresearch/habitat-sim/blob/main/DATASETS.md)
