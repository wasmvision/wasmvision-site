---
title: "How to Output"
linkTitle: "How to Output"
type: "docs"
weight: 20
description: >
  How to output video using wasmVision.
---

There are several different ways you can output the results of the video that you process.

This can be either via streaming, or by saving to a file.

## MPJEG Stream

By default, wasmVision can stream the output in MJPEG format.

When using wasmVision, this is configured by using the `--output=mjpeg` flag.

To control the stream destination port, you can use the `--destination` (`-d` for short) flag like this:

```shell
wasmvision run -p hello.wasm -o mjpeg -d :8081
```

## Save to File

wasmVision can write data to image and video files in several different formats.

When using wasmVision, this is configured by using the `--output=file` flag.

To control the file type and destination, you can use the `--destination` (`-d` for short) flag like this:

```shell
wasmvision run -p hello.wasm -o file -d /path/to/video/filename.avi
```

Output to a single file:

```shell
--output=file --destination=image.png
```

Output to a sequence of files:

```shell
--output=file --destination=images{id}.png
```

## Other streaming formats

You can also output streams in a number of different formats using GStreamer. More info about this will go here soon.
