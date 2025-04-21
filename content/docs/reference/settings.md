---
title: "wasmVision Settings"
linkTitle: "Settings"
type: "docs"
weight: 10
description: >
  About wasmVision settings
---

## `--file string, -f string`
TOML or YAML file with configuration

## `--source string, -s string`
video capture source to use. webcam id, file name, stream, testpattern (0 is the default webcam on most systems) (default: "0")

## `--capture string`
video capture type to use (auto, ffmpeg, gstreamer, webcam) (default: "auto")

## `--width int, -w int`
width to use for capture of the video stream (default: 0)

## `--height int, -h int`
height to use for capture of the video stream (default: 0)

## `--output string, -o string`
output type (mjpeg, file, none) (default: "mjpeg")

## `--destination string, -d string`
output destination (port, file path)

## `--logging string`
logging level to use (error, warn, info, debug) (default: "warn")

## `--cuda-enable`
enable CUDA support (if available) (default: false)

## `--benchmark`
enable output of benchmark data (default: false)

## `--processor string, -p string [ --processor string, -p string ]`
wasm module to use for processing frames. Format: -processor /path/processor1.wasm -processor /path2/processor2.wasm

## `--processors-dir string `
directory for processor loading (default to $home/processors) [$WASMVISION_PROCESSORS_DIR]

## `--processor-download`
automatically download known processors (default: true)

## `--config string=string, -c string=string [ --config string=string, -c string=string ]`
configuration for processors. Format: -config key1=val1 -config key2=val2

## `--models-dir string`
directory for model loading (default to $home/models) [$WASMVISION_MODELS_DIR]

## `--models-download, --download`
automatically download known models (default: true)

## `--mcp-server`
enable MCP server (default: false)

## `--mcp-port string`
port for MCP server (default: ":5001")

## `--datastorage string`
datastorage backend to use for processor data (memory, boltdb, redis, nats) (default: "memory")

```
