# DevOps Learning Roadmap

## Introduction

*(Fill this section with a brief introduction about yourself and why you're learning DevOps.)*

## Current Focus

*(Mention what specific DevOps topics, tools, or projects you're currently focusing on.)*

## Tools & Technologies

*(List the DevOps tools, platforms, and technologies you're working with.)*

## Projects

*(Describe the DevOps-related projects you're working on or plan to work on.)*

## Progress Metrics

*(Track your progress, such as completed topics, certifications, or milestones achieved.)*

## Connect With Me

*(Add your contact details, LinkedIn, GitHub, or other social media links.)*

---

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

