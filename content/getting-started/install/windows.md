---
title: "Windows"
linkTitle: "Windows"
type: "docs"
weight: 65
description: >
  Windows install guide
---

Download the latest release for Windows under [Releases](https://github.com/wasmvision/wasmvision/releases) by clicking on the latest release.

Under the "Assets" click on the link for "wasmvision-windows-amd64".

NOTE: you will likely need to configure your Windows Defender to download the ZIP file with the `wasmvision.exe` executable.

Extract the executable to your desired directory.

Verify it is installed like this:

```shell
chdir C:\path\to\wasmvision\install
wasmvision.exe version
```

Now you can run a test to capture video using your webcam, blur it using a WebAssembly processor, and then stream the output to port 8080 on your local machine:

```shell
wasmvision.exe run -p blur
```

wasmVision will automatically download the `blur.wasm` processor from our repo to your local `$HOME/processors` directory.

You will probably need to configure Windows Firewall to allow the `wasmvision.exe` executable to access the network port on your local machine.

Point your browser to `http://localhost:8080` and you should see the output.

![mjpeg-stream](/images/mjpeg-stream.png)

## Next steps

Now that you have installed wasmVision take a look at [Next Steps](/getting-started/next-steps) for what to do next.
