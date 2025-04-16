
---
title: "Creating your own processors"
linkTitle: "Creating Processors"
type: "docs"
weight: 40
description: >
  About writing your own wasmVision processors.
---

You can write new processors for wasmVision using Go, Rust, or the C programming languages.

See the [Processors list](/docs/reference/processors) if you are looking for pre-compiled processors you can try out right away.

## Go

### Creating a new processor

You can create a new processor using our template as follows.

First, install the `gonew` command:

```bash
go install golang.org/x/tools/cmd/gonew@latest
```

Now you can create a new processor like this:

```bash
gonew github.com/wasmvision/go-processor-template your.domain/your-processor
```

Compile the processor like this:

```bash
cd your-processor
go mod tidy
tinygo build -o your-processor.wasm -target=wasip1 -buildmode=c-shared -scheduler=none --no-debug .
```

### Examples

Most of the built-in processors in have been written using TinyGo. They are examples of some of the things you can do:

https://github.com/wasmvision/wasmvision/tree/main/processors

### Details

Developing a new processor using the Go programming language requires using TinyGo to compile the module to WebAssembly using either the `wasm-unknown` or `wasip1` target.

The package with the Go bindings for wasmCV is located here:

https://github.com/wasmvision/go-wasmcv

The package with the Go bindings for the wasmVision platform SDK is located here:

https://github.com/wasmvision/wasmvision-sdk-go

## Rust

### Examples

The `blurrs.wasm` and `facedetectynrs.wasm` processors in this repo have been written using Rust as an example of some of the things you can do:

https://github.com/wasmvision/wasmvision/tree/main/processors/blurrs

https://github.com/wasmvision/wasmvision/tree/main/processors/facedetectynrs


### Details

Developing a new processor using the Rust programming language requires compiling the module to WebAssembly using the `wasm32-unknown-unknown` target.

The crate with the Rust bindings for wasmCV is located here:

https://crates.io/crates/wasmcv

The crate with the Rust bindings for the wasmVision platform SDK is located here:

https://crates.io/crates/wasmvision

## C


### Examples

The `blurc.wasm` processor in this repo has been written using C as an example of some of the things you can do:

https://github.com/wasmvision/wasmvision/tree/main/processors/blurc

### Details

Developing a new processor using the C programming language requires using `clang` to compile the module to WebAssembly using the `wasm32-unknown-unknown` target.

The files for the C bindings for wasmCV are located here:

https://github.com/wasmvision/wasmcv/tree/main/components/c/wasmcv

The files for the C bindings for the wasmVision platform SDK are located here:

https://github.com/wasmvision/wasmvision-sdk/tree/main/components/c/wasmvision
