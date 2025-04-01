

# DevOps Learning Roadmap

## Introduction
I am Arjun, a MERN stack developer currently expanding my skill set by learning DevOps. My goal is to gain expertise in automation, CI/CD pipelines, cloud infrastructure, and containerization to enhance my development workflow and become a well-rounded engineer.

## Current Focus
Currently, I am focusing on mastering basic Bash commands as part of my DevOps learning journey. This includes understanding file handling, process management, and scripting. Moving forward, I will dive into version control (Git), containerization (Docker), and CI/CD pipelines.

## Tools & Technologies
- **Operating Systems**: Linux (Ubuntu), Windows
- **Scripting & Automation**: Bash
- **Version Control**: Git, GitHub
- **Containerization**: Docker (upcoming)
- **CI/CD**: Jenkins, GitHub Actions (upcoming)
- **Cloud Platforms**: AWS (future learning)

## Projects
- **Bash Scripting**: Automating daily tasks and system operations.
- **Version Control Setup**: Managing projects efficiently with Git and GitHub.
- **CI/CD Pipeline (Upcoming)**: Setting up a basic pipeline using GitHub Actions.
- **Dockerized Application (Upcoming)**: Deploying a simple web application using Docker.

## Progress Metrics
- ✅ Completed **Basic Bash Commands** (Week 1)
- ⏳ Learning **Advanced Bash Scripting** (Week 2)
- 🔜 Exploring **Git & GitHub Workflows** (Week 3)
- 🔜 Understanding **Docker & Containerization** (Week 4)
- 🔜 Implementing **CI/CD Pipelines** (Week 5+)

## Connect With Me
- **GitHub**: [github.com/arjunkumar811](https://github.com/arjunkumar811)
- **LinkedIn**: [https://www.linkedin.com/in/arjunitagi](https://www.linkedin.com/in/arjunitagi)
- **Email**: [kumararjun26401@gmail.com](mailto:kumararjun26401@gmail.com)



# DevOps Topics Breakdown

## Linux / Bash scripting

| Easy | Medium | Hard |
| --- | --- | --- |
| Basic bash commands |  |  |
| Aliases, .bashrc/.zshrc |  |  |
| Interactive vs non-interactive shells | Process Management |  |
|  | Cron jobs |  |
|  | File transfer - FTP, SCP |  |
|  | File permissions |  |
| Creating your own bash script - variables, loops, conditionals, functions |  |  |
|  | Args in bash scripts |  |
|  | Stderr, stdout, file descriptors, piping |  |
|  | Grep |  |
|  | Creating a CLI in Node.js |  |

### Projects
1. Create a script that `ssh`s into a VM, pulls the latest code, and restarts it.
2. Do the same using ssh2.

---

## VMs / EC2 / GCP VMs

| Easy | Medium | Hard |
| --- | --- | --- |
| What are VMs? |  |  |
| Creating a VM in various cloud providers, specs, pricing |  |  |
| GUI vs CLI for creating VMs | Keypairs and SSH into VMs |  |
|  | Deploying a non-containerized app to a VM |  |
| Process management |  |  |
| Reverse proxies |  |  |
|  | Certificate management |  |
|  | Load balancers |  |

---

## ASGs / MIG

| Easy | Medium | Hard |
| --- | --- | --- |
| What is autoscaling, why do you need it? |  |  |
|  | Images, target groups, ASGs, LBs, autoscaling policies |  |
|  | MIG internals |  |

---

## Containerization

| Easy | Medium | Hard |
| --- | --- | --- |
| What is a container? | What is Docker? | Docker vs other container runtimes |
|  | How to dockerize your app (WORKDIR, CMD, RUN, ENV, COPY, ARG) |  |
|  |  | Volumes and networks |
| Publishing to DockerHub, other registries |  |  |
|  | Running a Docker container in a VM, exposing it over the internet |  |
|  |  | Multi-stage builds |
|  | Docker Compose |  |

---

## ECS (Warming up for Kubernetes)

| Easy | Medium | Hard |
| --- | --- | --- |
| What is ECS, common use cases |  |  |
|  | ECR vs DockerHub |  |
|  | Setting up task definitions |  |
|  | Serverless vs EC2 instances for deploying, pros and cons |  |
|  | Autoscaling policies |  |

---

## Kubernetes

| Easy | Medium | Hard |
| --- | --- | --- |
| Introduction to Kubernetes, clusters, nodes, pods, worker node vs control plane |  | Kubernetes architecture |
|  | Local deployment using kind/minikube |  |
|  | ReplicaSets, Deployments |  |
|  | Networking Concepts - Services, Types of services |  |
|  |  | Ingress, Ingress controllers |
|  | Certificate management |  |
|  | Storage - PVs, PVCs, StorageClasses |  |
|  |  | StatefulSets, DaemonSets, Jobs, and CronJobs |
|  | ConfigMaps and Secrets |  |
|  | Kubernetes policies, RBAC, CRDs |  |
|  |  | HPAs, VPA, Cluster autoscaler |
|  | EKS, eksctl, best practices |  |
|  | Extra - k9s, kubectx |  |

---

## Infrastructure as Code (IaC) / Terraform

| Easy | Medium | Hard |
| --- | --- | --- |
| What is IaC? |  |  |
|  | IaC using Bash scripts, AWS CLI/EKSCTL |  |
|  | Various IaC tools (Ansible vs Terraform) |  |
|  | Installing Terraform, HCL syntax, Providers |  |
|  | Running Terraform Commands (init, plan, apply, destroy) |  |
|  |  | Managing state, variables, counts |
|  |  | Terraform with AWS |
|  |  | Remote state on S3 |

---

## Monitoring & Logging

| Easy | Medium | Hard |
| --- | --- | --- |
| Introduction to monitoring, why do you need it? |  |  |
|  | Datadog vs NewRelic vs Sentry |  |
|  | Self-hosted monitoring using Prometheus |  |
|  | Pulling vs pushing metrics, Push gateway |  |
|  | Grafana for charting, observability |  |
|  | Prometheus and Grafana service discovery in Kubernetes |  |

---

## CI/CD & GitOps

| Easy | Medium | Hard |
| --- | --- | --- |
| What is CI/CD? |  |  |
| GitHub CI/CD YAML format, GitHub Actions |  |  |
| Using CI/CD to deploy to a VM |  |  |
|  | Using CI/CD to provision infrastructure using IaC |  |
|  | Using CI/CD to deploy to a Kubernetes cluster |  |

---

## GitOps

| Easy | Medium | Hard |
| --- | --- | --- |
| What is GitOps? |  |  |
|  | Creating AWS resources using GitOps |  |
|  | Creating/Updating Kubernetes clusters |  |
|  | GitOps using ArgoCD |  |
|  |  | GitOps in a multi-cluster environment using ArgoCD |

---

## CDNs & Object Stores

| Easy | Medium | Hard |
| --- | --- | --- |
| What are object stores? |  |  |
| Introduction to CDNs |  |  |
|  | S3, R2 for assets |  |
|  | CloudFront as a CDN |  |
|  | Attaching a custom domain to your CDN, certificate management |  |

### Projects
1. Build a serverless provider (AWS Lambda / Repl.it)
2. Build a distributed video transcoder / image resizer
3. Build an alerts manager and status page provider

