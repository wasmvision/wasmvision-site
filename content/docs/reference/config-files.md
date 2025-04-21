---
title: "wasmVision Config Files"
linkTitle: "Config Files"
type: "docs"
weight: 10
description: >
  About wasmVision Config Files
---

You can use an external TOML or YAML file to configure wasmVision.

For details on each of the different settings, please see [Settings](/docs/reference/flags)

{{< tabpane text=true >}}
  {{% tab header="**Config**:" disabled=true /%}}
  {{% tab header="TOML" lang="en" %}}
```toml
[main]
logging = "info"
capture = "auto"
source = "testpattern"
width = 640
height = 480
output = "mjpeg"
destination = ":8080"
cuda-enable = false

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
  {{% /tab %}}
  {{% tab header="YAML" lang="en" %}}
```yaml
main:
  logging: "info"
  capture: "auto"
  source: "testpattern"
  width: 640
  height: 480
  output: "mjpeg"
  destination: ":8080"
  cuda-enable: false

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
  {{< /tab >}}
{{< /tabpane >}}

