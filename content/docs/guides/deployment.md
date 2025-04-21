
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

Most information on various cloud deployment scenarios is coming soon. Stay tuned!
