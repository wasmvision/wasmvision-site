---
title: "MCP Server Resources"
linkTitle: "MCP"
type: "docs"
weight: 35
description: >
  MCP Server Resources.
---

wasmVision provides the following [MCP resources](https://modelcontextprotocol.io/docs/concepts/resources) for image data.

## `images://input`

Reading from the `images://input` resource returns the current input image before the running processing pipeline. The returned image data is of MIME type `image/jpeg` and has been base64 encoded.

```json
{
    "jsonrpc": "2.0",
    "id": 1,
    "result": {
        "data": "base64-encoded-image-data-here"
    }
}
```

## `images://output`

Reading from the `images://output` resource returns the current output image after the running processors in the pipeline have processed it. The returned image data is of MIME type `image/jpeg` and has been base64 encoded.

```json
{
    "jsonrpc": "2.0",
    "id": 1,
    "result": {
        "data": "base64-encoded-image-data-here"
    }
}
```
