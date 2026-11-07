# NVIDIA AI Infrastructure and Operations

A hands-on study project for the NVIDIA NCP-AII and NCP-AIO certifications. The goal is to build, operate, and troubleshoot AI infrastructure, then document each exercise so it can be reproduced from a clean environment.

## What we’re working toward

- Explain how GPUs, hosts, and networks fit together in systems such as DGX and HGX.
- Bring up and validate a Linux GPU host, then run and diagnose workloads under Slurm and Kubernetes.
- Collect infrastructure and GPU metrics, build dashboards, and use them to investigate failures and performance changes.
- Track both certification blueprints and turn weak areas into repeatable exercises.

## Lab environments

| Environment | What we’ll use it for |
| --- | --- |
| Apple Silicon MacBook Pro with 48 GB of unified memory | Git, VS Code, iTerm2, Homebrew, and local container and Kubernetes exercises. |
| Linux VMs on the Mac | Multi-host networking, server bring-up practice, and a Slurm controller with separate workers. |
| Local kind clusters | Kubernetes and Helm practice, workload troubleshooting, and Prometheus and Grafana. We’ll add a second cluster when a lab calls for it. |
| Linux host with an NVIDIA GPU | NVIDIA driver and CUDA validation, GPU scheduling, NVIDIA DCGM telemetry, and GPU benchmarking. |

We’ll install tools as labs need them. The initial Mac setup covers Apple Command Line Tools (including Git), iTerm2, VS Code, Homebrew, and GitHub access. Later labs may add Docker Desktop and Compose, kubectl, kind, Helm, Terraform, and smaller tools such as iperf3, jq, and yq. When a lab needs Python, its packages will live in a project-local virtual environment.

## Study roadmap

The target is eight weeks at roughly 20 or more hours per week. The pacing can change as labs reveal topics that need more practice.

| Week | Topics | What we’ll build or verify |
| --- | --- | --- |
| 1 | Workstation setup and GPU architecture | Verify the tools, document the setup, and explain how GPU compute and memory are organized. |
| 2 | DGX, HGX, and GPU networking | Sketch system topology and use Linux VMs to measure network throughput. |
| 3 | Server bring-up, drivers, and CUDA | Write a bring-up checklist, verify an NVIDIA driver, and run a CUDA workload on a GPU host. Use Terraform when a provisioning exercise calls for it. |
| 4 | Base Command Manager and Slurm | Study cluster provisioning and run jobs on a Slurm controller and worker lab. |
| 5 | Containers and GPU Kubernetes | Deploy a workload to kind, practice Helm and multi-cluster operations, and test GPU scheduling on a GPU-backed cluster. |
| 6 | Observability | Deploy Prometheus and Grafana with Helm, query Kubernetes metrics, and use DCGM Exporter on a GPU host to visualize GPU telemetry. |
| 7 | Benchmarking and troubleshooting | Establish a baseline, diagnose a bottleneck, and record the investigation in a runbook. |
| 8 | Certification review | Check progress against both blueprints and rerun selected labs from the documented steps. |

## How the repo will grow

For each lab, we’ll define the objective, set up the environment, run the workload, verify the expected result, and capture what we learned. When something fails, we’ll record the symptom, diagnostic steps, and how we confirmed the fix.

| Planned location | What belongs there |
| --- | --- |
| `docs/setup/mac.md` | Workstation installation steps, versions, verification commands, and fixes. |
| `labs/` | Lab instructions and examples, with `setup.sh` and `validate.sh` when scripting makes the exercise easier to reproduce. |
| `infrastructure/` | Reusable Terraform, Kubernetes, and Helm configuration as those labs are added. |
| `runbooks/` | Troubleshooting procedures based on failures reproduced in the labs. |
| `docs/certification/` | Exam objective tracking and review notes. |

Record the commands we actually ran, the versions that worked, and the expected output. Keep credentials, local environments, and machine-specific state out of Git.

## Current status

Workstation setup is underway. Apple Git is working, the repository is cloned locally, and GitHub authentication is set up. Next, document and verify the Mac setup, then begin **GPU architecture**.
