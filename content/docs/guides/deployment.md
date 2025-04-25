
---
title: "Deployment"
linkTitle: "Deployment"
type: "docs"
weight: 50
description: >
  How to deploy wasmVision.
---

## Edge devices

### Raspberry Pi

You can run wasmVision natively on Raspberry Pi 3+ devices that use a 64-bit Linux-based operating system such as [Raspberry Pi OS](https://www.raspberrypi.com/software/operating-systems/).

The wasmVision ARM64 builds already support hardware acceleration using NEON.

To install wasmVision, download the latest "wasmvision-linux-arm64.tar.gz" file with the release build, expand the compressed file, and put on the desired device. There are no external dependencies, so it should "just work".

https://github.com/wasmvision/wasmvision/releases

### NVIDIA Jetson

Native support for CUDA on the NVIDIA Jetson is coming soon.

### AMD64

You can run wasmVision natively on AMD64 devices that use a 64-bit Linux-based operating system.

The wasmVision AMD64 builds already support hardware acceleration using SIMD.

To install wasmVision, download the latest "wasmvision-linux-amd64.tar.gz" file with the release build, expand the compressed file, and put on the desired device. There are no external dependencies, so it should "just work".

https://github.com/wasmvision/wasmvision/releases

### AMD64 with NVIDIA GPU

You can run the wasmVision container with CUDA support on AMD64 devices that use a 64-bit Linux-based operating system.

For more information, please see [CUDA](/docs/guides/cuda#docker)

## Cloud

### Google Cloud Run jobs

You can use [Google Cloud Run jobs](https://cloud.google.com/run/docs/overview/what-is-cloud-run#cloud-run-jobs) to run wasmVision on demand to process images or videos.

A typical setup would first create a container image based on the wasmVision Docker container image in the [Google Cloud Artifact Registry](https://cloud.google.com/artifact-registry/docs/repositories/remote-repo). 

Once the image was available in the Artifact Registry, create a new [Google Cloud Job](https://cloud.google.com/run/docs/create-jobs#job).

[Execute the job with the specific parameters](https://cloud.google.com/run/docs/execute/jobs#override-job-configuration) to process each image or video file.

You can also use [Google Cloud storage volume mounts](https://cloud.google.com/run/docs/configuring/jobs/cloud-storage-volume-mounts) to make available a location to read or write the image/video data.

### Microsoft Azure Container Apps jobs

You can use [Microsoft Azure Container Apps jobs](https://learn.microsoft.com/en-us/azure/container-apps/jobs) to run wasmVision on demand to process images or videos.

One way is to [trigger a manual job](https://learn.microsoft.com/en-us/azure/container-apps/jobs?tabs=azure-cli#manual-jobs) that processes each image or video file.

### Other cloud environments

More information on other cloud deployment scenarios is coming soon. Stay tuned!
