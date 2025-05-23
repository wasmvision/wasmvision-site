---
title: "How to Capture"
linkTitle: "How to Capture"
type: "docs"
weight: 10
description: >
  How to capture video using wasmVision.
---

wasmVision can capture video data from a webcam, from data files, or from a stream. 

## Webcam

Your webcam will probably "just work" on Linux, macOS, or Windows. However, you might need to determine the correct identifier to use. Very typically the ID of "0" is the default camera.

When using wasmVision, this is configured by using the `--capture webcam` flag. Note that this is the default value for `capture`.

If you need to use a different webcam other than the default, you can use the `--source` (`-s` for short) flag like this:

```shell
wasmvision run --capture webcam -s 2 -p hello.wasm
```

## FFMpeg

FFMpeg is very useful to read data from files and streams of different formats.

When using wasmVision, this is configured by using the `--capture ffmpeg` flag.

To capture from a file using FFMpeg, you can use the `--source` (`-s` for short) flag like this:

```shell
wasmvision run --capture ffmpeg -s /path/to/video.avi -p hello.wasm
```

To capture from a UDP stream using FFMpeg, you can use the `--source` (`-s` for short) flag like this:

```shell
wasmvision run --capture ffmpeg -s udp://127.0.0.1:6789 -p hello.wasm
```

## GStreamer

GStreamer is a multipurpose video processing tool that has its own pipeline to pre or post processing video streams.

To capture from a test pattern created using GStreamer, you can use the `--source` (`-s` for short) flag like this:

```shell
wasmvision run --capture gstreamer -s "videotestsrc ! videoconvert ! appsink" -p hello.wasm
```

The following GStreamer plugins are included with wasmVision on Linux systems:

- core (https://gstreamer.freedesktop.org/documentation/coreelements/index.html)

- app (https://gstreamer.freedesktop.org/documentation/app/index.html?gi-language=c)

- audioparsers (https://gstreamer.freedesktop.org/documentation/audioparsers/index.html?gi-language=c)

- codectimestamper (https://gstreamer.freedesktop.org/documentation/codectimestamper/index.html?gi-language=c)

- isomp4 (https://gstreamer.freedesktop.org/documentation/isomp4/index.html?gi-language=c)

- openh264 (https://gstreamer.freedesktop.org/documentation/openh264/index.html?gi-language=c)

- playback (https://gstreamer.freedesktop.org/documentation/playback/index.html?gi-language=c)

- rawparse (https://gstreamer.freedesktop.org/documentation/rawparse/index.html?gi-language=c)

- rtp (https://gstreamer.freedesktop.org/documentation/rtp/index.html?gi-language=c)

- rtpmanager (https://gstreamer.freedesktop.org/documentation/rtpmanager/index.html?gi-language=c)

- rtsp (https://gstreamer.freedesktop.org/documentation/rtsp/index.html?gi-language=c)

- tcp (https://gstreamer.freedesktop.org/documentation/tcp/index.html?gi-language=c)

- udp (https://gstreamer.freedesktop.org/documentation/udp/index.html?gi-language=c)

- videoconvertscale https://gstreamer.freedesktop.org/documentation/videoconvertscale/index.html?gi-language=c()

- videoparsers (https://gstreamer.freedesktop.org/documentation/videoparsersbad/index.html?gi-language=c)

- videotestsrc (https://gstreamer.freedesktop.org/documentation/videotestsrc/index.html?gi-language=c)
