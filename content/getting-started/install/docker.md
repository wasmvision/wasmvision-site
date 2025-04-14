---
title: "Docker"
linkTitle: "Docker"
type: "docs"
weight: 55
---

**NOTE for macOS users: camera input does not work with Docker on macOS. File sources only.**

You can run wasmVision using Docker.

Pull the current development version:

```shell
docker pull ghcr.io/wasmvision/wasmvision:main
```

Verify it is installed like this:

```shell
docker run ghcr.io/wasmvision/wasmvision:main version
```

Now you can run a test to capture video using your webcam, blur it using a WebAssembly processor, and then stream the output to port 8080 on your local machine:

```shell
docker run --privileged --network=host ghcr.io/wasmvision/wasmvision:main run -p /processors/blur.wasm
```

Point your browser to `http://localhost:8080` and you should see the output.

![mjpeg-stream](/images/mjpeg-stream.png)
