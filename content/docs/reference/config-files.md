---
title: "wasmVision Config Files"
linkTitle: "Config Files"
type: "docs"
weight: 35
description: >
  About wasmVision Config Files
---

You can use an external TOML or YAML file to configure wasmVision. Here is an TOML example:

```toml
[main]
logging = "info"
destination = ":8080"
cuda-enable = true

[processing]
pipeline = [
    "ollama.wasm",
    "style-transfer.wasm",
    "captions.wasm"
]

[configuration]
ollama-model = "qnguyen3/nanollava"
caption-line-height = "30"
caption-size = "0.9"

[models]
download = true

[server]
mcp-enable = false
mcp-port = ":5001"
```

Here is the same configuration in YAML format:

```yaml
main:
  logging: "info"
  destination: ":8080"
  cuda-enable: true

processing:
  pipeline:
    - "ollama.wasm"
    - "style-transfer.wasm"
    - "captions.wasm"

configuration:
  ollama-model: "qnguyen3/nanollava"
  caption-line-height: "15"
  caption-size: "0.9"

models:
  download: true

server:
  mcp-enable: false
  mcp-port: ":5001"
```
