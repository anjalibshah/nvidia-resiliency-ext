# NVIDIA Resiliency Extension

The NVIDIA Resiliency Extension (NVRx) integrates multiple resiliency-focused solutions for PyTorch-based workloads. Users can modularly integrate NVRx capabilities into their own infrastructure to maximize AI training productivity at scale. NVRx maximizes goodput by enabling system-wide health checks, quickly detecting faults at runtime and resuming training automatically. NVRx minimizes loss of work by enabling fast and frequent checkpointing. 

For detailed documentation and usage information about each component, please refer to https://nvidia.github.io/nvidia-resiliency-ext/.

> ⚠️ NOTE: This project is still experimental and under active development. The code, features, and documentation are evolving rapidly. Please expect frequent updates and breaking changes. Contributions are welcome and we encourage you to watch for updates.

<img src="https://github.com/anjalibshah/nvidia-resiliency-ext/blob/main/docs/source/media/nvrx_core_features.png" alt="Figure highlighting core NVRx features including automatic restart, hierarchical checkpointing, fault detection and health checks" width="950" height="350">


## Core Components and Capabilities

- **[Fault Tolerance](https://github.com/NVIDIA/nvidia-resiliency-ext/blob/main/docs/source/fault_tolerance/index.rst)**
  - Detection of hung ranks.  
  - Restarting training in-job, without the need to reallocate SLURM nodes.

- **[In-Process Restarting](https://github.com/NVIDIA/nvidia-resiliency-ext/blob/main/docs/source/inprocess/index.rst)**
  - Detecting failures and enabling quick recovery.

- **[Async Checkpointing](https://github.com/NVIDIA/nvidia-resiliency-ext/blob/main/docs/source/checkpointing/async/index.rst)**
  - Providing an efficient framework for asynchronous checkpointing.

- **[Local Checkpointing](https://github.com/NVIDIA/nvidia-resiliency-ext/blob/main/docs/source/checkpointing/local/index.rst)**
  - Providing an efficient framework for local checkpointing.

- **[Straggler Detection](https://github.com/NVIDIA/nvidia-resiliency-ext/blob/main/docs/source/straggler_det/index.rst)**
  - Monitoring GPU and CPU performance of ranks.  
  - Identifying slower ranks that may impede overall training efficiency.

- **[PyTorch Lightning Callbacks](https://github.com/NVIDIA/nvidia-resiliency-ext/blob/main/docs/source/fault_tolerance/integration/ptl.rst)**
  - Facilitating seamless NVRx integration with PyTorch Lightning.

## Installation

### From sources
- `git clone https://github.com/NVIDIA/nvidia-resiliency-ext`
- `cd nvidia-resiliency-ext`
- `pip install .`


### From PyPI wheel
- `pip install nvidia-resiliency-ext`

### Platform Support

| Category             | Supported Versions / Requirements                                          |
|----------------------|----------------------------------------------------------------------------|
| Architecture         | x86_64, arm64                                                              |
| Operating System     | Ubuntu 22.04, 24.04                                                        |
| Python Version       | >= 3.10, < 3.13                                                            |
| PyTorch Version      | >= 2.3.1 (injob & chkpt), >= 2.5.1 (inprocess)                             |
| CUDA & CUDA Toolkit  | >= 12.5 (12.8 required for GPU health check)                               |
| NVML Driver          | >= 535 (570 required for GPU health check)                                 |
| NCCL Version         | >= 2.21.5 (injob & chkpt), >= 2.26.2 (inprocess)                           |

