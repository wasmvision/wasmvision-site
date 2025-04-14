---
title: "macOS"
linkTitle: "macOS"
type: "docs"
weight: 45
description: >
  macOS install guide
---

**NOTE: wasmVision currently runs on M-series processors only when using the Homebrew installer. You must install from source to use Intel processors.**

Install wasmVision on macOS using Homebrew:

```shell
brew tap wasmvision/tools
brew install wasmvision
```

Verify it is installed like this:

```shell
wasmvision version
```

Now you can run a test to capture video using your webcam, blur it using a WebAssembly processor, and then stream the output to port 8080 on your local machine:

```shell
wasmvision run -p blur
```

wasmVision will automatically download the `blur.wasm` processor from our repo to your local `$HOME/processors` directory.

Point your browser to `http://localhost:8080` and you should see the output.

![mjpeg-stream](/images/mjpeg-stream.png)
