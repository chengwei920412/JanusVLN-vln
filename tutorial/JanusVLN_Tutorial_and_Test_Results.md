# JanusVLN Usage Guide and Test Results

# Usage Guide

We provide tutorials for using JanusVLN in three ways: Conda, Skill (with Conda), and Docker.

Conda usage guide: [View here](<tutorial/conda/JanusVLN_Tutorial_Conda_Version.md>)

Conda usage guide with Skill assistance: [View here](<tutorial/skill/JanusVLN_Tutorial_Skill_Version.md>)

Docker usage guide: [View here](<tutorial/docker/JanusVLN_Tutorial_Docker_Version.md>)

# Test Results

We conducted three tests using the JanusVLN\_Base model on the R2R Val-Unseen dataset with two environment configurations, Conda and Docker, on servers equipped with A6000 and A100 GPUs.

The average differences from the results reported in the paper were as follows: NE (Navigation Error) was 0.03 meters lower; OS (Oracle Success) was 0.27 percentage points lower; SR (Success Rate) was 0.32 percentage points higher; and SPL (Success weighted by Path Length) was 0.09 percentage points higher.

| Configuration | Type | NE: Navigation Error (m) ↓ | OS: Oracle Success ↑ | SR: Success Rate ↑ | SPL: Success weighted by Path Length ↑ |
| --- | --- | --- | --- | --- | --- |
| Conda A6000 | Results reported in the paper | 5.17 | 58.0 | 52.8 | 49.2 |
| Conda A6000 | Test results | 5.20 | 57.37 | 52.47 | 48.81 |
|  | Difference from the paper | \-0.03 | \-0.63 | \-0.33 | \-0.39 |
| Docker A6000 | Test results | 5.11 | 58.56 | 53.94 | 50.05 |
|  | Difference from the paper | +0.06 | +0.56 | +1.14 | +0.85 |
| Docker A100 | Test results | 5.29 | 57.26 | 52.96 | 49.01 |
|  | Difference from the paper | \-0.12 | \-0.74 | +0.16 | \-0.19 |
| Average difference from the paper |  | \-0.03 | \-0.27 | +0.32 | +0.09 |

# Detailed Test Results

Conda A6000 test results: [View here](<test_results/conda/result.json>)

Docker A6000 test results: [View here](<test_results/docker/result_docker.json>)

Docker A100 test results: [View here](<test_results/docker/result_a100.json>)
