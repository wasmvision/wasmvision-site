
---
title: "Creating your own processors"
linkTitle: "Processors"
type: "docs"
weight: 10
description: >
  About writing your own wasmVision processors.
---

You can write new processors for wasmVision using Go, Rust, or the C programming languages.

See the [Processors list](/docs/reference/processors) if you are looking for pre-compiled processors you can try out right away.

## Go

Many of the processors in this repo have been written using TinyGo as an example of some of the things you can do:

https://github.com/wasmvision/wasmvision/tree/main/processors

Developing a new processor using the Go programming language requires using TinyGo to compile the module to WebAssembly using either the `wasm-unknown` or `wasip1` target.

The package with the Go bindings for wasmCV is located here:

https://github.com/wasmvision/go-wasmcv

The package with the Go bindings for the wasmVision platform SDK is located here:

https://github.com/wasmvision/wasmvision-sdk-go

## Rust

The `blurrs.wasm` and `facedetectynrs.wasm` processors in this repo have been written using Rust as an example of some of the things you can do:

https://github.com/wasmvision/wasmvision/tree/main/processors/blurrs

https://github.com/wasmvision/wasmvision/tree/main/processors/facedetectynrs


Developing a new processor using the Rust programming language requires compiling the module to WebAssembly using the `wasm32-unknown-unknown` target.

The crate with the Rust bindings for wasmCV is located here:

https://crates.io/crates/wasmcv

The crate with the Rust bindings for the wasmVision platform SDK is located here:

https://crates.io/crates/wasmvision

## C

The `blurc.wasm` processor in this repo has been written using C as an example of some of the things you can do:

https://github.com/wasmvision/wasmvision/tree/main/processors/blurc

Developing a new processor using the C programming language requires using `clang` to compile the module to WebAssembly using the `wasm32-unknown-unknown` target.

The files for the C bindings for wasmCV are located here:

https://github.com/wasmvision/wasmcv/tree/main/components/c/wasmcv

The files for the C bindings for the wasmVision platform SDK are located here:

https://github.com/wasmvision/wasmvision-sdk/tree/main/components/c/wasmvision
