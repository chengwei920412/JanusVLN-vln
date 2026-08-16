# JanusVLN\_Tutorial\_Conda\_Version

# Related Resources

Project Homepage: [https://miv-xjtu.github.io/JanusVLN.github.io/](https://miv-xjtu.github.io/JanusVLN.github.io/)

Conda Environment Package: [https://modelscope.cn/datasets/QiDekang/JanusVLN\_Environment](https://modelscope.cn/datasets/QiDekang/JanusVLN_Environment)

Evaluation Records: [https://modelscope.cn/datasets/QiDekang/JanusVLN\_Evaluation\_Records](https://modelscope.cn/datasets/QiDekang/JanusVLN_Evaluation_Records)

# Environment Setup

## 2.1 Original Conda Environment

```plaintext
(base) [qidekang.qdk@localhost streamvln]$ conda activate /home/zengshuang.zs/anaconda3/envs/streamvln
(streamvln) [qidekang.qdk@localhost streamvln]$ conda list
# packages in environment at /home/zengshuang.zs/anaconda3/envs/streamvln:
#
# Name                      Version          Build            Channel
_libgcc_mutex               0.1              main
_openmp_mutex               5.1              1_gnu
absl-py                     2.3.1            pypi_0           pypi
accelerate                  0.28.0           pypi_0           pypi
antlr4-python3-runtime      4.9.3            pypi_0           pypi
attrs                       25.3.0           pypi_0           pypi
beautifulsoup4              4.13.4           pypi_0           pypi
braceexpand                 0.1.7            pypi_0           pypi
bzip2                       1.0.8            h5eee18b_6
ca-certificates             2025.2.25        h06a4308_0
cachetools                  5.5.2            pypi_0           pypi
certifi                     2025.7.14        pypi_0           pypi
charset-normalizer          3.4.2            pypi_0           pypi
click                       8.1.8            pypi_0           pypi
cloudpickle                 3.1.1            pypi_0           pypi
decorator                   5.2.1            pypi_0           pypi
depth-camera-filtering      0.1              pypi_0           pypi
einops                      0.8.1            pypi_0           pypi
expat                       2.7.1            h6a678d5_0
fastdtw                     0.3.4            pypi_0           pypi
faster-fifo                 1.5.2            pypi_0           pypi
filelock                    3.18.0           pypi_0           pypi
flash-attn                  2.7.1.post4      pypi_0           pypi
fsspec                      2025.7.0         pypi_0           pypi
gdown                       5.2.0            pypi_0           pypi
google-auth                 2.40.3           pypi_0           pypi
google-auth-oauthlib        0.4.6            pypi_0           pypi
grpcio                      1.73.1           pypi_0           pypi
gym                         0.23.0           pypi_0           pypi
gym-notices                 0.0.8            pypi_0           pypi
habitat-baselines           0.2.4            dev_0            <develop>
habitat-lab                 0.2.4            dev_0            <develop>
habitat-sim                 0.2.4            pypi_0           pypi
hf-xet                      1.1.5            pypi_0           pypi
huggingface-hub             0.33.4           pypi_0           pypi
hydra-core                  1.3.2            pypi_0           pypi
idna                        3.10             pypi_0           pypi
ifcfg                       0.24             pypi_0           pypi
imageio                     2.37.0           pypi_0           pypi
imageio-ffmpeg              0.6.0            pypi_0           pypi
importlib-metadata          8.7.0            pypi_0           pypi
janusvln                    0.1.0            dev_0            <develop>
jinja2                      3.1.6            pypi_0           pypi
ld_impl_linux-64            2.40             h12ee557_0
libffi                      3.4.4            h6a678d5_1
libgcc-ng                   11.2.0           h1234567_1
libgomp                     11.2.0           h1234567_1
libstdcxx-ng                11.2.0           h1234567_1
libxcb                      1.17.0           h9b100fa_0
llvmlite                    0.43.0           pypi_0           pypi
lmdb                        1.7.2            pypi_0           pypi
markdown                    3.8.2            pypi_0           pypi
markdown-it-py              3.0.0            pypi_0           pypi
markupsafe                  3.0.2            pypi_0           pypi
mdurl                       0.1.2            pypi_0           pypi
modelscope                  1.31.0           pypi_0           pypi
moviepy                     2.2.1            pypi_0           pypi
mpmath                      1.3.0            pypi_0           pypi
msgpack                     1.1.1            pypi_0           pypi
ncurses                     6.4              h6a678d5_0
networkx                    3.2.1            pypi_0           pypi
numba                       0.60.0           pypi_0           pypi
numpy                       1.26.4           pypi_0           pypi
numpy-quaternion            2023.0.4         pypi_0           pypi
nvidia-cublas-cu12          12.4.5.8         pypi_0           pypi
nvidia-cuda-cupti-cu12      12.4.127         pypi_0           pypi
nvidia-cuda-nvrtc-cu12      12.4.127         pypi_0           pypi
nvidia-cuda-runtime-cu12    12.4.127         pypi_0           pypi
nvidia-cudnn-cu12           9.1.0.70         pypi_0           pypi
nvidia-cufft-cu12           11.2.1.3         pypi_0           pypi
nvidia-curand-cu12          10.3.5.147       pypi_0           pypi
nvidia-cusolver-cu12        11.6.1.9         pypi_0           pypi
nvidia-cusparse-cu12        12.3.1.170       pypi_0           pypi
nvidia-cusparselt-cu12      0.6.2            pypi_0           pypi
nvidia-nccl-cu12            2.21.5           pypi_0           pypi
nvidia-nvjitlink-cu12       12.4.127         pypi_0           pypi
nvidia-nvtx-cu12            12.4.127         pypi_0           pypi
oauthlib                    3.3.1            pypi_0           pypi
objectio                    0.2.29           pypi_0           pypi
omegaconf                   2.3.0            pypi_0           pypi
opencv-python               4.11.0.86        pypi_0           pypi
openssl                     3.0.16           h5eee18b_0
packaging                   25.0             pypi_0           pypi
pillow                      11.3.0           pypi_0           pypi
pip                         25.1             pyhc872135_2
proglog                     0.1.12           pypi_0           pypi
protobuf                    3.20.1           pypi_0           pypi
psutil                      7.0.0            pypi_0           pypi
pthread-stubs               0.3              h0ce48e5_1
pyasn1                      0.6.1            pypi_0           pypi
pyasn1-modules              0.4.2            pypi_0           pypi
pygments                    2.19.2           pypi_0           pypi
pysocks                     1.7.1            pypi_0           pypi
python                      3.9.23           he99959a_0
python-dotenv               1.1.1            pypi_0           pypi
pyyaml                      6.0.2            pypi_0           pypi
qwen-vl-utils               0.0.11           pyh29332c3_0     <unknown>
readline                    8.2              h5eee18b_0
regex                       2024.11.6        pypi_0           pypi
requests                    2.32.4           pypi_0           pypi
requests-oauthlib           2.0.0            pypi_0           pypi
rich                        14.0.0           pypi_0           pypi
rsa                         4.9.1            pypi_0           pypi
safetensors                 0.5.3            pypi_0           pypi
scipy                       1.13.1           pypi_0           pypi
setuptools                  67.6.1           pypi_0           pypi
shellingham                 1.5.4            pypi_0           pypi
simplejson                  3.20.1           pypi_0           pypi
soupsieve                   2.7              pypi_0           pypi
sqlite                      3.50.2           hb25bd0a_1
sympy                       1.13.1           pypi_0           pypi
tensorboard                 2.8.0            pypi_0           pypi
tensorboard-data-server     0.6.1            pypi_0           pypi
tensorboard-plugin-wit      1.8.1            pypi_0           pypi
threadpoolctl               3.6.0            pypi_0           pypi
tk                          8.6.14           h993c535_1
tokenizers                  0.21.4           pypi_0           pypi
torch                       2.5.0+cu124      pypi_0           pypi
torchaudio                  2.5.0+cu124      pypi_0           pypi
torchvision                 0.20.0+cu124     pypi_0           pypi
tqdm                        4.67.1           pypi_0           pypi
transformers                4.50.0           pypi_0           pypi
triton                      3.1.0            pypi_0           pypi
typer                       0.16.0           pypi_0           pypi
typing-extensions           4.14.1           pypi_0           pypi
tzdata                      2025b            h04d1e81_0
urllib3                     2.5.0            pypi_0           pypi
webdataset                  0.1.40           pypi_0           pypi
werkzeug                    3.1.3            pypi_0           pypi
wheel                       0.45.1           py39h06a4308_0
xorg-libx11                 1.8.12           h9b100fa_1
xorg-libxau                 1.0.12           h9b100fa_0
xorg-libxdmcp               1.1.5            h9b100fa_0
xorg-xorgproto              2024.1           h5eee18b_1
xz                          5.6.4            h5eee18b_1
zipp                        3.23.0           pypi_0           pypi
zlib                        1.2.13           h5eee18b_1
(streamvln) [qidekang.qdk@localhost streamvln]$ pip list
WARNING: Ignoring invalid distribution -ransformers (/home/zengshuang.zs/anaconda3/envs/streamvln/lib/python3.9/site-packages)
Package                  Version      Editable project location
------------------------ ------------ --------------------------------------------------------
absl-py                  2.3.1
accelerate               0.28.0
antlr4-python3-runtime   4.9.3
attrs                    25.3.0
beautifulsoup4           4.13.4
braceexpand              0.1.7
cachetools               5.5.2
certifi                  2025.7.14
charset-normalizer       3.4.2
click                    8.1.8
cloudpickle              3.1.1
decorator                5.2.1
depth_camera_filtering   0.1
einops                   0.8.1
fastdtw                  0.3.4
faster-fifo              1.5.2
filelock                 3.18.0
flash-attn               2.7.1.post4
fsspec                   2025.7.0
gdown                    5.2.0
google-auth              2.40.3
google-auth-oauthlib     0.4.6
grpcio                   1.73.1
gym                      0.23.0
gym-notices              0.0.8
habitat-baselines        0.2.4        /home/zengshuang.zs/v0.2.4/habitat-lab/habitat-baselines
habitat-lab              0.2.4        /home/zengshuang.zs/v0.2.4/habitat-lab/habitat-lab
habitat-sim              0.2.4
hf-xet                   1.1.5
huggingface-hub          0.33.4
hydra-core               1.3.2
idna                     3.10
ifcfg                    0.24
imageio                  2.37.0
imageio-ffmpeg           0.6.0
importlib_metadata       8.7.0
JanusVLN                 0.1.0        /home/zengshuang.zs/JanusVLN/src
Jinja2                   3.1.6
llvmlite                 0.43.0
lmdb                     1.7.2
magnum                   0.0.0
Markdown                 3.8.2
markdown-it-py           3.0.0
MarkupSafe               3.0.2
mdurl                    0.1.2
modelscope               1.31.0
moviepy                  2.2.1
mpmath                   1.3.0
msgpack                  1.1.1
networkx                 3.2.1
numba                    0.60.0
numpy                    1.26.4
numpy-quaternion         2023.0.4
nvidia-cublas-cu12       12.4.5.8
nvidia-cuda-cupti-cu12   12.4.127
nvidia-cuda-nvrtc-cu12   12.4.127
nvidia-cuda-runtime-cu12 12.4.127
nvidia-cudnn-cu12        9.1.0.70
nvidia-cufft-cu12        11.2.1.3
nvidia-curand-cu12       10.3.5.147
nvidia-cusolver-cu12     11.6.1.9
nvidia-cusparse-cu12     12.3.1.170
nvidia-cusparselt-cu12   0.6.2
nvidia-nccl-cu12         2.21.5
nvidia-nvjitlink-cu12    12.4.127
nvidia-nvtx-cu12         12.4.127
oauthlib                 3.3.1
objectio                 0.2.29
omegaconf                2.3.0
opencv-python            4.11.0.86
packaging                25.0
pillow                   11.3.0
pip                      25.1
proglog                  0.1.12
protobuf                 3.20.1
psutil                   7.0.0
pyasn1                   0.6.1
pyasn1_modules           0.4.2
Pygments                 2.19.2
PySocks                  1.7.1
python-dotenv            1.1.1
PyYAML                   6.0.2
qwen-vl-utils            0.0.11
regex                    2024.11.6
requests                 2.32.4
requests-oauthlib        2.0.0
rich                     14.0.0
rsa                      4.9.1
safetensors              0.5.3
scipy                    1.13.1
setuptools               78.1.1
shellingham              1.5.4
simplejson               3.20.1
soupsieve                2.7
sympy                    1.13.1
tensorboard              2.8.0
tensorboard-data-server  0.6.1
tensorboard-plugin-wit   1.8.1
threadpoolctl            3.6.0
tokenizers               0.21.4
torch                    2.5.0+cu124
torchaudio               2.5.0+cu124
torchvision              0.20.0+cu124
tqdm                     4.67.1
transformers             4.50.0
triton                   3.1.0
typer                    0.16.0
typing_extensions        4.14.1
urllib3                  2.5.0
webdataset               0.1.40
Werkzeug                 3.1.3
wheel                    0.45.1
zipp                     3.23.0
```

## 2.2 Build a Clean Conda Environment

The original environment contains several issues, including symbolic links, and needs to be converted into a clean environment.

Define the commonly used paths:

```plaintext
SRC_ENV=/home/zengshuang.zs/anaconda3/envs/streamvln
CLONE_ENV=/home/qidekang.qdk/miniforge3/envs/streamvln_portable

DEPS_ROOT=/home/qidekang.qdk/workspace/JanusVLN/env/dependencies
HABITAT_REPO="${DEPS_ROOT}/habitat-lab"
JANUS_REPO="${DEPS_ROOT}/JanusVLN"

PACKAGE_DIR=/home/qidekang.qdk/workspace/JanusVLN/env/packages
```

### Clone the Environment

```plaintext
conda create \
    --prefix /home/qidekang.qdk/miniforge3/envs/streamvln_portable \
    --clone /home/zengshuang.zs/anaconda3/envs/streamvln \
    -y

conda activate /home/qidekang.qdk/miniforge3/envs/streamvln_portable
```

### Handle Packages That Depend on External Source Code

Copy the dependency source code to your own path: `/home/qidekang.qdk/workspace/JanusVLN/env/dependencies`

Stop using editable installations and reinstall the following three packages:

```plaintext
ENV_PYTHON=/home/qidekang.qdk/miniforge3/envs/streamvln_portable/bin/python

"${ENV_PYTHON}" -m pip uninstall -y \
    JanusVLN \
    habitat-baselines \
    habitat-lab

"${ENV_PYTHON}" -m pip install \
    --no-deps \
    --no-build-isolation \
    --no-cache-dir \
    /home/qidekang.qdk/workspace/JanusVLN/env/dependencies/habitat-lab/habitat-lab

"${ENV_PYTHON}" -m pip install \
    --no-deps \
    --no-build-isolation \
    --no-cache-dir \
    /home/qidekang.qdk/workspace/JanusVLN/env/dependencies/habitat-lab/habitat-baselines

"${ENV_PYTHON}" -m pip install \
    --no-deps \
    --no-build-isolation \
    --no-cache-dir \
    /home/qidekang.qdk/workspace/JanusVLN/env/dependencies/JanusVLN
```

Result:

```plaintext
(streamvln_portable) [qidekang.qdk@localhost envs]$ pip list
WARNING: Ignoring invalid distribution -ransformers (/home/qidekang.qdk/miniforge3/envs/streamvln_portable/lib/python3.9/site-packages)
Package                  Version
------------------------ ------------
absl-py                  2.3.1
accelerate               0.28.0
antlr4-python3-runtime   4.9.3
attrs                    25.3.0
beautifulsoup4           4.13.4
braceexpand              0.1.7
cachetools               5.5.2
certifi                  2025.7.14
charset-normalizer       3.4.2
click                    8.1.8
cloudpickle              3.1.1
decorator                5.2.1
depth_camera_filtering   0.1
einops                   0.8.1
fastdtw                  0.3.4
faster-fifo              1.5.2
filelock                 3.18.0
flash-attn               2.7.1.post4
fsspec                   2025.7.0
gdown                    5.2.0
google-auth              2.40.3
google-auth-oauthlib     0.4.6
grpcio                   1.73.1
gym                      0.23.0
gym-notices              0.0.8
habitat-baselines        0.2.4
habitat-lab              0.2.4
habitat-sim              0.2.4
hf-xet                   1.1.5
huggingface-hub          0.33.4
hydra-core               1.3.2
idna                     3.10
ifcfg                    0.24
imageio                  2.37.0
imageio-ffmpeg           0.6.0
importlib_metadata       8.7.0
JanusVLN                 0.1.0
Jinja2                   3.1.6
llvmlite                 0.43.0
lmdb                     1.7.2
magnum                   0.0.0
Markdown                 3.8.2
markdown-it-py           3.0.0
MarkupSafe               3.0.2
mdurl                    0.1.2
modelscope               1.31.0
moviepy                  2.2.1
mpmath                   1.3.0
msgpack                  1.1.1
networkx                 3.2.1
numba                    0.60.0
numpy                    1.26.4
numpy-quaternion         2023.0.4
nvidia-cublas-cu12       12.4.5.8
nvidia-cuda-cupti-cu12   12.4.127
nvidia-cuda-nvrtc-cu12   12.4.127
nvidia-cuda-runtime-cu12 12.4.127
nvidia-cudnn-cu12        9.1.0.70
nvidia-cufft-cu12        11.2.1.3
nvidia-curand-cu12       10.3.5.147
nvidia-cusolver-cu12     11.6.1.9
nvidia-cusparse-cu12     12.3.1.170
nvidia-cusparselt-cu12   0.6.2
nvidia-nccl-cu12         2.21.5
nvidia-nvjitlink-cu12    12.4.127
nvidia-nvtx-cu12         12.4.127
oauthlib                 3.3.1
objectio                 0.2.29
omegaconf                2.3.0
opencv-python            4.11.0.86
packaging                25.0
pillow                   11.3.0
pip                      25.1
proglog                  0.1.12
protobuf                 3.20.1
psutil                   7.0.0
pyasn1                   0.6.1
pyasn1_modules           0.4.2
Pygments                 2.19.2
PySocks                  1.7.1
python-dotenv            1.1.1
PyYAML                   6.0.2
qwen-vl-utils            0.0.11
regex                    2024.11.6
requests                 2.32.4
requests-oauthlib        2.0.0
rich                     14.0.0
rsa                      4.9.1
safetensors              0.5.3
scipy                    1.13.1
setuptools               78.1.1
shellingham              1.5.4
simplejson               3.20.1
soupsieve                2.7
sympy                    1.13.1
tensorboard              2.8.0
tensorboard-data-server  0.6.1
tensorboard-plugin-wit   1.8.1
threadpoolctl            3.6.0
tokenizers               0.21.4
torch                    2.5.0+cu124
torchaudio               2.5.0+cu124
torchvision              0.20.0+cu124
tqdm                     4.67.1
transformers             4.50.0
triton                   3.1.0
typer                    0.16.0
typing_extensions        4.14.1
urllib3                  2.5.0
webdataset               0.1.40
Werkzeug                 3.1.3
wheel                    0.45.1
zipp                     3.23.0
```

### Resolve Inconsistent `setuptools` Metadata

Current inconsistency:

```plaintext
conda list: setuptools 67.6.1
pip list:   setuptools 78.1.1
```

Pip likely overwrote the `setuptools` files managed by Conda. As a result, `conda-pack` may report that Conda-managed files have been deleted or overwritten.

Change it to:

```plaintext
conda install \
    --prefix /home/qidekang.qdk/miniforge3/envs/streamvln_portable \
    --freeze-installed \
    --force-reinstall \
    "setuptools=67.6.1" \
    -y
```

### Remove Corrupted `-ransformers` Residue

Get the `site-packages` path:

```plaintext
SITE_PACKAGES=$(
    "${CLONE_ENV}/bin/python" -c \
    'import site; print(site.getsitepackages()[0])'
)

echo "${SITE_PACKAGES}"
```

First, inspect the Transformers-related directories:

```plaintext
find "${SITE_PACKAGES}" \
    -maxdepth 1 \
    \( -name '*ransformers*' -o -name '~*' \) \
    -printf '%f\n'
```

The following valid directories should be preserved:

```plaintext
transformers
transformers-4.50.0.dist-info
```

Remove only the invalid remnants whose names begin with `~ransformers` or `-ransformers`:

```plaintext
shopt -s nullglob

INVALID_TRANSFORMERS=(
    "${SITE_PACKAGES}"/~ransformers*
    "${SITE_PACKAGES}"/-ransformers*
)

if [ "${#INVALID_TRANSFORMERS[@]}" -gt 0 ]; then
    printf 'The following invalid remnants will be removed:\n'
    printf '%s\n' "${INVALID_TRANSFORMERS[@]}"
    rm -rf -- "${INVALID_TRANSFORMERS[@]}"
fi

shopt -u nullglob
```

Verify:

```plaintext
"${CLONE_ENV}/bin/python" -m pip list >/dev/null"${CLONE_ENV}/bin/python" -c \    'import transformers; print(transformers.__version__, transformers.__file__)'
```

The following warning should no longer appear:

```plaintext
Ignoring invalid distribution -ransformers
```

### Check Symbolic Links

Focus on links that still point to the original user's directory:

```plaintext
while IFS= read -r -d '' LINK_PATH; do
    LINK_TARGET=$(readlink -f "${LINK_PATH}" 2>/dev/null || true)

    case "${LINK_TARGET}" in
        /home/zengshuang.zs/*)
            printf 'External symbolic link: %s -> %s\n' \
                "${LINK_PATH}" "${LINK_TARGET}"
            ;;
    esac
done < <(find "${CLONE_ENV}" -type l -print0)
```

If there is no output, no symbolic links point to the original user's directory.

Check for broken symbolic links:

```plaintext
find "${CLONE_ENV}" -xtype l -printf '%p -> %l\n'
```

Normally, there should be no output.

### Check for Hard-Coded Paths to the Original User Directory

```plaintext
grep -RIl \
    --binary-files=without-match \
    --exclude='*.pyc' \
    --exclude='direct_url.json' \
    '/home/zengshuang.zs' \
    "${CLONE_ENV}/bin" \
    "${SITE_PACKAGES}" \
    "${CLONE_ENV}/etc" \
    2>/dev/null
```

If there is no output, you can continue.

If there is output:

*   `.pth`, `.egg-link`, or `__editable__*.py`: the editable installation was not fully removed.
    

*   Python/YAML configuration files: update the paths to the project, model, or data locations on the new server.
    

*   `direct_url.json`: if it points to your own `/home/qidekang.qdk/...` path, it is usually only an installation-source record. If it points to `/home/zengshuang.zs`, reinstalling the corresponding package is recommended.
    

### Resolve Missing Declared Dependencies

Check the dependencies:

```plaintext
"${CLONE_ENV}/bin/python" -m pip check
```

Error:

```plaintext
qwen-vl-utils 0.0.11 requires av, which is not installed.
habitat-sim 0.2.4 requires gitpython, which is not installed.
habitat-sim 0.2.4 requires matplotlib, which is not installed.
```

This indicates that the original environment is missing three declared dependencies.

Fix:

Verify the variable:

```plaintext
echo "${CLONE_ENV}"
```

Expected output:

```plaintext
/home/qidekang.qdk/miniforge3/envs/streamvln_portable
```

Then set:

```plaintext
ENV_PYTHON="${CLONE_ENV}/bin/python"
```

Verify that the wrong Python interpreter is not being used:

```plaintext
"${ENV_PYTHON}" --version
"${ENV_PYTHON}" -m pip --version
```

Install the missing dependencies:

```plaintext
# Install PyAV first because it provides a platform-specific binary wheel
"${ENV_PYTHON}" -m pip install \
    --no-cache-dir \
    --prefer-binary \
    --only-binary=av \
    "av==14.2.0"

# Then install the remaining dependencies and their transitive dependencies
"${ENV_PYTHON}" -m pip install \
    --no-cache-dir \
    --prefer-binary \
    "GitPython==3.1.44" \
    "matplotlib==3.9.4"
```

Verify after installation:

```plaintext
"${ENV_PYTHON}" - <<'PY'
import av
import git
import matplotlib

print("av:", av.__version__, av.__file__)
print("GitPython:", git.__version__, git.__file__)
print("matplotlib:", matplotlib.__version__, matplotlib.__file__)

assert av.__version__ == "14.2.0"
assert git.__version__ == "3.1.44"
assert matplotlib.__version__ == "3.9.4"

print("All three dependencies were installed successfully")
PY
```

Then run the dependency check again:

```plaintext
"${ENV_PYTHON}" -m pip check
```

Expected output:

```plaintext
No broken requirements found.
```

Run a complete import test:

```plaintext
"${ENV_PYTHON}" - <<'PY'
import av
import git
import matplotlib
import habitat_sim
from qwen_vl_utils import process_vision_info

print("av:", av.__version__)
print("GitPython:", git.__version__)
print("matplotlib:", matplotlib.__version__)
print("habitat_sim:", habitat_sim.__file__)
print("qwen_vl_utils imported successfully")
PY
```

Output:

```plaintext
av: 14.2.0
GitPython: 3.1.44
matplotlib: 3.9.4
habitat_sim: /home/qidekang.qdk/miniforge3/envs/streamvln_portable/lib/python3.9/site-packages/habitat_sim-0.2.4-py3.9-linux-x86_64.egg/habitat_sim/__init__.py
qwen_vl_utils imported successfully
```

### Verify the Cloned Environment

Check the key modules:

```plaintext
"${CLONE_ENV}/bin/python" - <<'PY'
import importlib.metadata as metadata

packages = [
    "JanusVLN",
    "habitat-lab",
    "habitat-baselines",
    "habitat-sim",
    "torch",
    "transformers",
    "flash-attn",
]

for name in packages:
    print(f"{name}: {metadata.version(name)}")

import torch
import transformers
import habitat
import habitat_baselines
import habitat_sim
import flash_attn

print("torch:", torch.__version__)
print("CUDA available:", torch.cuda.is_available())
print("transformers:", transformers.__version__)
print("habitat:", habitat.__file__)
print("habitat_baselines:", habitat_baselines.__file__)
print("habitat_sim:", habitat_sim.__file__)
print("flash_attn:", flash_attn.__file__)
PY
```

Output:

```plaintext
JanusVLN: 0.1.0
habitat-lab: 0.2.4
habitat-baselines: 0.2.4
habitat-sim: 0.2.4
torch: 2.5.0+cu124
transformers: 4.50.0
flash-attn: 2.7.1.post4
torch: 2.5.0+cu124
CUDA available: True
transformers: 4.50.0
habitat: /home/qidekang.qdk/miniforge3/envs/streamvln_portable/lib/python3.9/site-packages/habitat/__init__.py
habitat_baselines: /home/qidekang.qdk/miniforge3/envs/streamvln_portable/lib/python3.9/site-packages/habitat_baselines/__init__.py
habitat_sim: /home/qidekang.qdk/miniforge3/envs/streamvln_portable/lib/python3.9/site-packages/habitat_sim-0.2.4-py3.9-linux-x86_64.egg/habitat_sim/__init__.py
flash_attn: /home/qidekang.qdk/miniforge3/envs/streamvln_portable/lib/python3.9/site-packages/flash_attn/__init__.py
```

### Save the Environment Manifests

```plaintext
mkdir -p "${PACKAGE_DIR}"

conda list \
    --prefix "${CLONE_ENV}" \
    --explicit \
    > "${PACKAGE_DIR}/streamvln_conda_explicit.txt"

"${CLONE_ENV}/bin/python" -m pip list \
    --format=freeze \
    > "${PACKAGE_DIR}/streamvln_pip_packages.txt"
```

[View the attached `streamvln_conda_explicit.txt` file in the ModelScope.](https://modelscope.cn/datasets/QiDekang/JanusVLN_Environment/file/view/master/packages%2Fstreamvln_conda_explicit.txt?id=211793&status=1)

[View the attached `streamvln_pip_packages.txt` file in the ModelScope.](https://modelscope.cn/datasets/QiDekang/JanusVLN_Environment/file/view/master/packages%2Fstreamvln_pip_packages.txt?id=211793&status=1)

### Package and Upload the Conda Environment

Package the environment:

```plaintext
STAMP=$(date +%Y%m%d_%H%M%S)
ARCHIVE="${PACKAGE_DIR}/streamvln_portable_${STAMP}.tar.gz"

"$(conda info --base)/bin/conda-pack" \
    --prefix "${CLONE_ENV}" \
    --output "${ARCHIVE}" \
    --format tar.gz \
    --compress-level 6 \
    --n-threads -1
```

Do not add the following options:

```plaintext
--ignore-editable-packages
--ignore-missing-files
```

They may conceal unresolved environment issues.

Generate the checksum file:

```plaintext
cd "${PACKAGE_DIR}"

sha256sum "$(basename "${ARCHIVE}")" \
    > "$(basename "${ARCHIVE}").sha256"

ls -lh \
    "${ARCHIVE}" \
    "${ARCHIVE}.sha256"
```

The Conda environment package has been uploaded to ModelScope: [https://modelscope.cn/datasets/QiDekang/JanusVLN\_Environment](https://modelscope.cn/datasets/QiDekang/JanusVLN_Environment)

## 2.3 Build a Conda Environment from the Downloaded Package

### Check the Server Configuration

Hardware configuration of the test server:

```plaintext
(base) [qidekang.qdk@localhost packages]$ uname -m
x86_64
(base) [qidekang.qdk@localhost packages]$ ldd --version | head -n 1
ldd (GNU libc) 2.17
(base) [qidekang.qdk@localhost packages]$ nvidia-smi
Fri Aug 14 16:21:10 2026
+-----------------------------------------------------------------------------------------+
| NVIDIA-SMI 550.54.14              Driver Version: 550.54.14      CUDA Version: 12.4     |
|-----------------------------------------+------------------------+----------------------+
| GPU  Name                 Persistence-M | Bus-Id          Disp.A | Volatile Uncorr. ECC |
| Fan  Temp   Perf          Pwr:Usage/Cap |           Memory-Usage | GPU-Util  Compute M. |
|                                         |                        |               MIG M. |
|=========================================+========================+======================|
|   0  NVIDIA RTX A6000               Off |   00000000:4F:00.0 Off |                  Off |
| 30%   35C    P8             21W /  300W |       0MiB /  49140MiB |      0%      Default |
|                                         |                        |                  N/A |
+-----------------------------------------+------------------------+----------------------+
|   1  NVIDIA RTX A6000               Off |   00000000:52:00.0 Off |                  Off |
| 31%   42C    P8             23W /  300W |       0MiB /  49140MiB |      0%      Default |
|                                         |                        |                  N/A |
+-----------------------------------------+------------------------+----------------------+
|   2  NVIDIA RTX A6000               Off |   00000000:56:00.0 Off |                  Off |
| 30%   35C    P8             20W /  300W |       0MiB /  49140MiB |      0%      Default |
|                                         |                        |                  N/A |
+-----------------------------------------+------------------------+----------------------+
|   3  NVIDIA RTX A6000               Off |   00000000:57:00.0 Off |                  Off |
| 30%   38C    P8             22W /  300W |       0MiB /  49140MiB |      0%      Default |
|                                         |                        |                  N/A |
+-----------------------------------------+------------------------+----------------------+
|   4  NVIDIA RTX A6000               Off |   00000000:CE:00.0 Off |                  Off |
| 30%   35C    P8             32W /  300W |       0MiB /  49140MiB |      0%      Default |
|                                         |                        |                  N/A |
+-----------------------------------------+------------------------+----------------------+
|   5  NVIDIA RTX A6000               Off |   00000000:D1:00.0 Off |                  Off |
| 30%   36C    P8             27W /  300W |       0MiB /  49140MiB |      0%      Default |
|                                         |                        |                  N/A |
+-----------------------------------------+------------------------+----------------------+
|   6  NVIDIA RTX A6000               Off |   00000000:D5:00.0 Off |                  Off |
| 30%   35C    P8             22W /  300W |       0MiB /  49140MiB |      0%      Default |
|                                         |                        |                  N/A |
+-----------------------------------------+------------------------+----------------------+
|   7  NVIDIA RTX A6000               Off |   00000000:D6:00.0 Off |                  Off |
| 30%   38C    P8             27W /  300W |       0MiB /  49140MiB |      0%      Default |
|                                         |                        |                  N/A |
+-----------------------------------------+------------------------+----------------------+

+-----------------------------------------------------------------------------------------+
| Processes:                                                                              |
|  GPU   GI   CI        PID   Type   Process name                              GPU Memory |
|        ID   ID                                                               Usage      |
|=========================================================================================|
|  No running processes found                                                             |
+-----------------------------------------------------------------------------------------+
```

### Download the Conda Environment Archive

Download the Conda environment package from ModelScope: [https://modelscope.cn/datasets/QiDekang/JanusVLN\_Environment](https://modelscope.cn/datasets/QiDekang/JanusVLN_Environment)

### Extract the Package to a Local Directory

Validate the archive:

```plaintext
(base) [qidekang.qdk@localhost packages]$ tar -tzf /home/qidekang.qdk/workspace/JanusVLN/env/packages/streamvln_portable_20260814_161755.tar.gz \
>     >/dev/null && echo "Archive validation passed"
```

Create the target directory:

```plaintext
mkdir -p /home/qidekang.qdk/miniforge3/envs/streamvln
```

Extract the archive:

```plaintext
tar -xzf \
    /home/qidekang.qdk/workspace/JanusVLN/env/packages/streamvln_portable_20260814_161755.tar.gz \
    -C /home/qidekang.qdk/miniforge3/envs/streamvln
```

Confirm that Python was extracted successfully:

```plaintext
ls -lh /home/qidekang.qdk/miniforge3/envs/streamvln/bin/python
```

### Activate the Environment and Fix the Paths

Initialize Conda:

```plaintext
source /home/qidekang.qdk/miniforge3/etc/profile.d/conda.sh
```

Activate the new environment:

```plaintext
conda activate /home/qidekang.qdk/miniforge3/envs/streamvln
```

Repair the environment prefix:

```plaintext
/home/qidekang.qdk/miniforge3/envs/streamvln/bin/conda-unpack
```

After `conda-unpack` runs successfully, do not move the following directory again:

```plaintext
/home/qidekang.qdk/miniforge3/envs/streamvln
```

### Verify the Current Environment

```plaintext
echo "${CONDA_PREFIX}"
```

Expected output:

```plaintext
/home/qidekang.qdk/miniforge3/envs/streamvln
```

Check Python:

```plaintext
which python
```

Expected output:

```plaintext
/home/qidekang.qdk/miniforge3/envs/streamvln/bin/python
```

Verify further:

```plaintext
/home/qidekang.qdk/miniforge3/envs/streamvln/bin/python --version
/home/qidekang.qdk/miniforge3/envs/streamvln/bin/python -m pip --version
```

### Full Functionality Verification

```plaintext
/home/qidekang.qdk/miniforge3/envs/streamvln/bin/python - <<'PY'
import importlib.metadata as metadata

packages = [
    "JanusVLN",
    "habitat-lab",
    "habitat-baselines",
    "habitat-sim",
    "torch",
    "transformers",
    "flash-attn",
    "qwen-vl-utils",
    "av",
    "GitPython",
    "matplotlib",
]

for name in packages:
    print(f"{name}: {metadata.version(name)}")

import av
import git
import torch
import habitat
import flash_attn
import habitat_sim
import transformers
import matplotlib
import habitat_baselines
from qwen_vl_utils import process_vision_info

print()
print("Key modules imported successfully")
print("Python environment:", __import__("sys").executable)
print("Torch:", torch.__version__)
print("Torch CUDA:", torch.version.cuda)
print("CUDA available:", torch.cuda.is_available())

if torch.cuda.is_available():
    print("GPU:", torch.cuda.get_device_name(0))

print("av:", av.__version__)
print("GitPython:", git.__version__)
print("matplotlib:", matplotlib.__version__)
print("transformers:", transformers.__version__)
print("habitat:", habitat.__file__)
print("habitat_sim:", habitat_sim.__file__)
print("habitat_baselines:", habitat_baselines.__file__)
print("flash_attn:", flash_attn.__file__)
PY
```

# Model Preparation

Download the checkpoints locally.

JanusVLN\_Base：

[https://www.modelscope.cn/models/misstl/JanusVLN\_Base/files](https://www.modelscope.cn/models/misstl/JanusVLN_Base/files)

JanusVLN\_Extra：

[https://www.modelscope.cn/models/misstl/JanusVLN\_Extra](https://www.modelscope.cn/models/misstl/JanusVLN_Extra)

# Data Preparation

The evaluation data requires downloading `datasets` (including `r2r` and `rxr`) and `scene_datasets` (including the validation data for `hm3d` and `mp3d`).

Organize the data as shown below. For details, see the README ([https://github.com/MIV-XJTU/JanusVLN](https://github.com/MIV-XJTU/JanusVLN)).

![image.png](https://alidocs.oss-cn-zhangjiakou.aliyuncs.com/res/AJdl659eaK0VyOke/img/8c6e9307-ad10-4b2d-b2ad-845199d29683.png)

# Evaluation Results

*   Running Instructions
    
    *   Activate the configured Conda environment using its **absolute path** to avoid activating an environment with the same name at another path. For example:
        
        ```plaintext
        conda activate /home/qidekang.qdk/miniforge3/envs/streamvln
        ```
        
    *   Enter the project directory. For example:
        
        ```plaintext
        cd /home/qidekang.qdk/workspace/JanusVLN/code/JanusVLN
        ```
        
    *   Install the JanusVLN source code in the current directory into the active Python environment in editable mode:
        
        ```plaintext
        pip install -e .
        ```
        
    *   Set the absolute checkpoint path in `scripts/evaluation.sh`: `CHECKPOINT=""`
        
    *   Run the evaluation:
        
    
    ```plaintext
    bash scripts/evaluation.sh
    ```
    
*   Evaluation Results
    

We evaluated the JanusVLN\_Base model on the R2R Val-Unseen dataset using a server equipped with eight A6000 GPUs. The results are shown below:

| Type | NE: Navigation Error (m) ↓ | OS: Oracle Success ↑ | SR: Success Rate ↑ | SPL: Success Weighted by Path Length ↑ |
| --- | --- | --- | --- | --- |
| Paper-Reported Metrics | 5.17 | 58.0 | 52.8 | 49.2 |
| Evaluation Results | 5.20 | 57.37 | 52.47 | 48.81 |
| Difference from the Paper | \-0.03 | \-0.63 | \-0.33 | \-0.39 |

*   Results Analysis
    
    *   The differences are only 0.33% for success rate, 0.03 m for navigation error, 0.63% for oracle success, and 0.39% for success weighted by path length.
        
    *   These differences are within the range of normal variation.
        
    *   They may be caused by minor differences in hardware and environment. The experiments reported in the paper were primarily conducted on two A6000 servers, but only one of the servers used in the early experiments is currently available.
        

# Detailed Results Files

The detailed result files have been uploaded to ModelScope: [https://modelscope.cn/datasets/QiDekang/JanusVLN\_Evaluation\_Records](https://modelscope.cn/datasets/QiDekang/JanusVLN_Evaluation_Records)

Per-episode results: `/files/result.json`

Visualization videos: `/files/vis_0`
