---
title: "Linux"
linkTitle: "Linux"
type: "docs"
weight: 35
description: >
  Linux install guide
---

Download the latest release for Linux under [Releases](https://github.com/wasmvision/wasmvision/releases) by clicking on the latest release.

Under "Assets" click on the link for either "wasmvision-linux-amd64" or "wasmvision-linux-arm64" depending on your processor.

Extract the executable to your desired directory.

You might need to set the file as "executable", which you can do from the command line by running `chmod +x ./wasmvision` in the same directory to which you extracted the `wasmvision` executable.

Verify wasmVision is installed by running these commands:

```shell
cd /path/to/wasmvision/install
wasmvision version
```

Now you can run a test to capture video using your webcam, blur it using a WebAssembly processor, and then stream the output to port 8080 on your local machine:

```shell
wasmvision run -p blur
```

wasmVision will automatically download the `blur.wasm` processor from our repo to your local `$HOME/processors` directory.

Point your browser to `http://localhost:8080` and you should see the output.

![mjpeg-stream](/images/mjpeg-stream.png)
