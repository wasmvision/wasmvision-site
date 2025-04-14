
---
title: "Processors"
linkTitle: "Processors"
type: "docs"
weight: 35
description: >
  About wasmVision processors.
---

wasmVision processing modules are WebAssembly guest modules that support the [wasmCV interface](https://wasmcv.org).

Processors can filter images, analyze them, and modify them using traditional computer vision algorithms.

Processors can also use deep neural networks and other machine learning algorithms, and can even download the models they need automatically.

See the [processors directory](../processors/) for pre-compiled processors you can try out right away.

Processors can be written in [Go](#go), [Rust](#rust), or the [C programming language](#c).

## How processors work

```mermaid
flowchart TD
    subgraph engine
        Runtime[WASM Runtime]
        Runtime<-->OpenCV
        subgraph platform
            Logging
            Config
        end
        Runtime<-->platform
    end
    subgraph processors
        Runtime-- input frame -->processor.wasm
        processor.wasm<--wasmCV function calls-->Runtime
        processor.wasm-- output frame -->Runtime
        processor.wasm<--wasmVision platform function calls (logging, config, ...)-->platform
    end
```

### wasmCV

wasmVision processors call OpenCV functions implemented by the wasmVision engine to obtain information or perform operations on image frames. To do this, processors use the wasmCV bindings for the programming language being use to create the processor.

Full documentation of the computer vision functions supported by the wasmCV interface definitions is here:

https://wasmcv.org/docs/0.7.0/

The repository with the wasmCV interface and bindings can be found here:

https://github.com/wasmvision/wasmcv

### wasmVision Platform

In addition, the wasmVision engine has functions that are part of the platform itself. For example, processors need logging, the ability to load configuration data at runtime, and other capabilities. The repository with the wasmVision platform interfaces is here:

https://github.com/wasmvision/wasmvision-sdk
