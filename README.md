# DevOps Homelab
This repository contains the configuration files and deployment manifests for various DevOps tools and infrastructure setup used in my personal Kubernetes Homelab. It leverages GitOps with ArgoCD for continuous delivery and management of Kubernetes resources.

# Overview
The following tools and services have been deployed and managed in this Kubernetes homelab:
ArgoCD: GitOps continuous delivery tool for managing Kubernetes applications.
GitLab: GitLab instance for CI/CD pipelines and repository management.
Cert-Manager: A tool for managing SSL/TLS certificates in Kubernetes.
Rook & Ceph: A cloud-native storage solution for Kubernetes using Ceph.
MetalLB: Load Balancer for exposing services to external traffic.

# Infrastructure Setup
This project follows a modular approach to organize configurations into different sections:

Infrastructure (infra/):
Contains all the configuration files required to set up infrastructure components like GitLab, Cert-Manager, Ceph, etc.
| Image/Logo | Infrastructure Name | Description |
|:----------:|:--------------------:|:-----------|
| <img src="https://docs.rke2.io/img/logo-horizontal-rke2.svg" width="100"/> | **RKE2** | Rancher's next-generation Kubernetes distribution, fully compliant and secured out-of-the-box. |
| <img src="http://argo-cd.readthedocs.io/en/stable/assets/logo.png" width="100"/> | **ArgoCD** | A declarative GitOps continuous delivery tool for Kubernetes. |
| <img src="https://rook.io/images/rook-logo.svg" width="100"/> | **Rook & Ceph** | Rook is a storage orchestrator for Kubernetes; it uses Ceph to provide highly available, distributed storage. |
| <img src="https://about.gitlab.com/images/press/logo/png/gitlab-icon-rgb.png" width="100"/> | **GitLab** | A complete DevOps platform, providing Git repository management, CI/CD pipelines, and more. |
| <img src="https://cdn.prod.website-files.com/64196dbe03e13c204de1b1c8/66e3f89f9261694c9915b3cc_64773cb107fa08930fe8d468_76-image1.png" width="100"/> | **MetalLB** | A load-balancer implementation for bare metal Kubernetes clusters. |
| <img src="https://raw.githubusercontent.com/cert-manager/cert-manager/master/logo/logo-small.png" width="100"/> | **cert-manager** | Automates the management and issuance of TLS certificates in Kubernetes clusters. |

# Deployment Flow
GitOps with ArgoCD:
All the configurations and resources are managed through GitOps using ArgoCD.

The repository is connected to ArgoCD for automatic synchronization of resources.

Whenever there is a change in the repository (via pull request or direct commit), ArgoCD syncs and applies the changes to the Kubernetes cluster.

ArgoCD Configuration:

The repository folder structure is configured to match the requirements for ArgoCD's sync behavior.

ArgoCD deploys applications, manages updates, and rolls back changes as needed based on the YAML files in this repository.

Tools Deployed:
The following tools are deployed using Helm, Kubernetes manifests, or other native tools:

GitLab: Deployed as a CI/CD tool.

Cert-Manager: Automated management of SSL/TLS certificates.

Rook-Ceph: Provides persistent storage using Ceph.

