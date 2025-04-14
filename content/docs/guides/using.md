
---
title: "Using wasmVision"
linkTitle: "Usage"
type: "docs"
weight: 35
description: >
  About common ways to use wasmVision.
---

These are some of the things you can do with wasmVision.

## Automatically download the `blur` processor, capture from your webcam (default), process the video, and stream the output using MJPEG to port 8080 (default)

```shell
wasmvision run -p blur
```

## Automatically download the `mosaic` processor and the `mosaic-9.onnx` model, capture from your webcam (default), process the video, and stream the output using MJPEG to port 8080 (default)

```shell
wasmvision run -p mosaic
```

## Capture from your webcam (default), process the video using the `mosaic.wasm` processor located in the default processor directory, and stream the output using MJPEG to port 8080 (default)

```shell
wasmvision run -p mosaic.wasm
```

## Capture from your webcam (default), process the video using the `yourcustom.wasm` processor located in a non-default directory, and stream the output using MJPEG to port 8080 (default)

```shell
wasmvision run -p /path/to/processors/yourcustom.wasm
```

## Capture from a secondary webcam, process the video, and stream the output using MJPEG to port 8080 (default)

```shell
wasmvision run -s /dev/video2 -p /path/to/processors/mosaic.wasm
```

## Capture from your webcam (default), process the video using 2 processors chained together, and stream the output using MJPEG to port 8080 (default)

```shell
wasmvision run -p /path/to/processors/hello.wasm -p /path/to/processors/mosaic.wasm
```

## Capture from a file, process the video, and stream the output using MJPEG to port 6000

```shell
wasmvision run -s /path/to/video/filename.mp4 -p /path/to/processors/blur.wasm -o mjpeg -d :6000
```

## Capture from your webcam, process the video, and save the output to a file

```shell
wasmvision run -p /path/to/processors/mosaic.wasm -o file -d /path/to/video/filename.avi
```

## `wasmvision download`

```shell
NAME:
   wasmvision download - Download computer vision models and processors

USAGE:
   wasmvision download [command [command options]] 

COMMANDS:
   model      download a known computer vision model
   processor  download a known processor

OPTIONS:
   --help, -h  show help
```

## Download the `candy.wasm` processor used for fast neural style transfer from the wasmVision repository to the default processors directory on the local machine.

```shell
wasmvision download processor candy
```

## Download the `candy-9.onnx` model used for fast neural style transfer from the official ONNX repository to the default models directory on the local machine.

```shell
wasmvision download model candy-9
```

## `wasmvision info`

```shell
NAME:
   wasmvision info - Show installation info

USAGE:
   wasmvision info

OPTIONS:
   --help, -h  show help
```

Run this to obtain information about the installed capabilities of wasmVision.

```shell
wasmVision version 0.3.1 linux/amd64
Camera backends:  GSTREAMER V4L2 FIREWIRE UEYE OBSENSOR
Stream backends:  FFMPEG GSTREAMER INTEL_MFX V4L2 CV_IMAGES CV_MJPEG
Writer backends:  FFMPEG GSTREAMER INTEL_MFX CV_IMAGES CV_MJPEG
```

## `wasmvision listall`

```shell
NAME:
   wasmvision listall - Lists all known models and processors

USAGE:
   wasmvision listall [command [command options]] 

COMMANDS:
   models      lists all known computer vision models
   processors  lists all known wasm processors

OPTIONS:
   --help, -h  show help
```

## Show a list of all models that can be downloaded, either manually or automatically.

```shell
wasmvision listall models
```

## Show a list of all processors that can be downloaded, either manually or automatically.

```shell
wasmvision listall processors
```

