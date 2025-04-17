
---
title: "Output"
linkTitle: "Output"
type: "docs"
weight: 20
description: >
  About outputting video or images from wasmVision.
---

wasmVision can output the results or processing to a stream or video file.

See our [guide on output](/docs/guides/output) for details.

You can also [save data to BoltDB, Redis and other datastores](/docs/concepts/datastore).

## MJPEG

By default, wasmVision outputs an MJPEG stream so you can easily view the final output from processing.

## File

You can also configure wasmVision to output to a video file.

## Stream

wasmVision allows you to output to a video stream, thanks to including FFMpeg.
