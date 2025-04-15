
---
title: "wasmVision Processors"
linkTitle: "Processor List"
type: "docs"
weight: 10
description: >
  wasmVision Built-in Processors
---

These are the processors that are built-in to wasmVision and can be automatically downloaded and run.

## asciify.wasm

![asciify](/images/asciify-processor.png)

Processor written in Go that converts image frames to ascii art.

https://github.com/wasmvision/wasmvision/tree/main/processors/asciify

## blur.wasm

![blur](/images/blur-processor.png)

Processor written in Go that performs a blur on image frames.

https://github.com/wasmvision/wasmvision/tree/main/processors/blur

## blurc.wasm

![blurc](/images/blur-processor.png)

Processor written in C that performs a blur on the image frame.

https://github.com/wasmvision/wasmvision/tree/main/processors/blurc

## blurrs.wasm

![blurrs](/images/blur-processor.png)

Processor written in Rust that performs a blur on the image frame.

https://github.com/wasmvision/wasmvision/tree/main/processors/blurrs

## captions.wasm

Processor written in Go that adds text captions to the final output image.

https://github.com/wasmvision/wasmvision/tree/main/processors/captions

## edge-detect.wasm

![edge-detect](/images/edge-detect-processor.png)

wasmVision processor that detects edges using a model called Dense Extreme Inception Network for Edge Detection (DexiNed), a Convolutional Neural Network (CNN) architecture for edge detection.

https://github.com/wasmvision/wasmvision/tree/main/processors/edge-detect

## face-expression.wasm

![face-expression](/images/face-expression-processor.png)

wasmVision processor using Facial Expression Recognition (FER) featuring semi-supervised learning model with 88.27% accuracy.

https://github.com/wasmvision/wasmvision/tree/main/processors/face-expression

## faceblur.wasm

![faceblur](/images/faceblur-processor.png)

wasmVision processor that blurs previously detected faces before outputting the final image. 

https://github.com/wasmvision/wasmvision/tree/main/processors/faceblur

## facedetectyn.wasm

![facedetectyn](/images/facedetectyn-processor.png)

Processor written using TinyGo that recognizes faces using YuNet, a light-weight, fast and accurate face detection model.

https://github.com/wasmvision/wasmvision/tree/main/processors/facedetectyn

## facedetectynrs.wasm

![facedetectyn](/images/facedetectyn-processor.png)

Processor written using Rust that recognizes faces using YuNet, a light-weight, fast and accurate face detection model.

https://github.com/wasmvision/wasmvision/tree/main/processors/facedetectynrs

## gaussianblur.wasm

![gaussianblur](/images/gaussianblur-processor.png)

Processor written in Go that performs a gaussian blur on the image frame.

https://github.com/wasmvision/wasmvision/tree/main/processors/gaussianblur

## hello.wasm

Processor written in Go that displays some information about the image frame.

https://github.com/wasmvision/wasmvision/tree/main/processors/hello

## object-detector.wasm

![object-detector](/images/object-detector-processor.png)

wasmVision processor that performs object detection using the YOLOv8 real-time object detection model.

https://github.com/wasmvision/wasmvision/tree/main/processors/object-detector

## ollama.wasm

![ollama](/images/ollama-processor.png)

Processor that obtains text descriptions of image frames, by sending frames to an [Ollama](https://ollama.com/) server running a model for generating image descriptions such as `llava`.

https://github.com/wasmvision/wasmvision/tree/main/processors/ollama

## style-transfer.wasm

![udnie](/images/udnie-processor.png)

Processor written in Go that performs fast neural style transfer using one of several different DNN models.

https://github.com/wasmvision/wasmvision/tree/main/processors/style-transfer
