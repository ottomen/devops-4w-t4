# DevOps course | Task 4

You have been invited to the startup "AsciiArtify", which plans to develop a new software product for converting images into ascii-art using Machine Learning.
AsciiArtify was created by two young programmers with experience in software development and the desire to launch their own product, but no experience in DevOps.
The startup team prepares the concept of the project and chooses tools for the local development system, considering options based on Kubernetes — minikube, kind and k3d.

## Introduction

### minikube

minikube implements a **local** Kubernetes cluster on macOS, Linux, and Windows.

### kind

kind or kubernetes in Docker is a suite of tooling for local Kubernetes “clusters” where each “node” is a Docker container. kind is targeted at **testing** Kubernetes.

### k3d

k3d is a lightweight wrapper to run k3s (minimal Kubernetes distribution) in Docker.

## Characteristics comparison

| area                            | minikube              | kind (Kubernetes IN Docker) | k3d                   |
| ------------------------------- | --------------------- | --------------------------- | --------------------- |
| Popularity on Github            | 26.5k stars           | 11.6k stars                 | 4.4k stars            |
| Cross-platform                  | Linux, macOS, Windows | Linux, macOS, Windows       | Linux, macOS, Windows |
| Load balancing                  | Yes, but simple       | Yes                         | Yes                   |
| Supports production deployments | No                    | Not found                   | Not found             |

## Pros and Cons

### minikube

**Pros:** Easy to use CLI, wide range of container or virtual machine managers. Lightweight solution. Handy UI sdashboard.
**Cons:** It's not a production-grade solution.

### kind

**Pros:** good tool for testing k8s
**Cons:** currently, kind supports one default way to build a node-image

### k3d

**Pros:** simple to use toolset
**Cons:** k3d only supported a local container runtime for running the k8s cluster

## Demos

### minikube

[![minikube demo](https://asciinema.org/a/DJtlXA9WBecJCTs9YECmVzs5l.svg)](https://asciinema.org/a/DJtlXA9WBecJCTs9YECmVzs5l)

### kind

[![kind demo](https://asciinema.org/a/CyKo3t8lmZ5NmRujNPknBcAwh.svg)](https://asciinema.org/a/CyKo3t8lmZ5NmRujNPknBcAwh)

### k3d

[![k3d demo](https://asciinema.org/a/d7wtezGNmZ40AWXNhVSl8yQsb.svg)](https://asciinema.org/a/d7wtezGNmZ40AWXNhVSl8yQsb)

## Recap

**Minikube**'s goal to quickly set up local Kubernetes clusters, but it's authors strongly discourage using it in production or for listening to remote traffic. I would recommend this tool for local testing only.

**kind** was primarily designed for testing Kubernetes itself, but may be used for local development or CI. I would recommend this tool for local testing, because it was made for that.

**k3d** is built to create and manage single- and multi-node clusters in Docker, e.g. for local development on Kubernetes.

They are very similar in some way. For the PoC I would recommend minikube for local development, and kind for testing purposes.

As for Podman alternative to Docker, minikube can use it via experimental diver. k3d uses the Docker API and is compatible with Podman v4 and higher.
Starting with kind 0.11.0, Rootless Docker and Rootless Podman can be used as the node provider of kind.
