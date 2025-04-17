---
title: "Face Counting"
linkTitle: "Face Counting"
type: "docs"
weight: 10
description: >
  How to build a face counting application that saves the counts to a database.
---

This tutorial will get you started with wasmVision by showing how to build a face counting application that saves the counts to a BoltDB database.

## Detect faces

First, let us run the built-in face detector using the `wasmvision run` command:

```bash
wasmvision run -p facedetectyn.wasm
```

wasmVision should automatically download both the `facedetectyn.wasm` processor and also the `yunet_2023mar` computer vision model needed for detecting faces.

Point your browser to `http://localhost:8080` and you should see the output.

## Create config file

Next, let's do the same thing as in the first step, but use a configuration file so we can more easily change the various parameters needed for our face counting application.

wasmVision supports both `TOML` and `YAML` formats for configuration files.

Create a new file named `facecount.toml` (or `facecount.yaml`) and make sure it contains the following data:

{{< tabpane text=true >}}
  {{% tab header="**Config**:" disabled=true /%}}
  {{% tab header="TOML" lang="en" %}}
  ```toml
[main]
logging = "warn"

[processing]
pipeline = [
    "facedetectyn.wasm"
]
```
  {{% /tab %}}
  {{% tab header="YAML" lang="en" %}}
```yaml
main:
  logging: "warn"

processing:
  pipeline:
    - "facedetectyn.wasm"
```
  {{< /tab >}}
{{< /tabpane >}}


## Run using config file

Now we can run wasmVision again, but this time using the config file we just created:

{{< tabpane text=true >}}
  {{% tab header="**Config**:" disabled=true /%}}
  {{% tab header="TOML" lang="en" %}}
```bash
wasmvision run -f facecount.toml
```
  {{% /tab %}}
  {{% tab header="YAML" lang="en" %}}
```bash
wasmvision run -f facecount.yaml
```
  {{< /tab >}}
{{< /tabpane >}}

Point your browser to `http://localhost:8080` and you should see the same output.

## Count detected faces

Now we will add another processor. This processor is the built-in `face-counter.wasm` processor that can use the face information from the `facedetectyn.wasm` processor to create the count of faces detected.

Change the logging to `info` so we can see the output on the terminal:

{{< tabpane text=true >}}
  {{% tab header="**Config**:" disabled=true /%}}
  {{% tab header="TOML" lang="en" %}}
  ```toml
[main]
logging = "info"

[processing]
pipeline = [
    "facedetectyn.wasm",
    "face-counter.wasm"
]
```
  {{% /tab %}}
  {{% tab header="YAML" lang="en" %}}
```yaml
main:
  logging: "info"

processing:
  pipeline:
    - "facedetectyn.wasm"
    - "face-counter.wasm"
```
  {{< /tab >}}
{{< /tabpane >}}


Run wasmVision again:

{{< tabpane text=true >}}
  {{% tab header="**Config**:" disabled=true /%}}
  {{% tab header="TOML" lang="en" %}}
```bash
wasmvision run -f facecount.toml
```
  {{% /tab %}}
  {{% tab header="YAML" lang="en" %}}
```bash
wasmvision run -f facecount.yaml
```
  {{< /tab >}}
{{< /tabpane >}}

You should see output similar to the following including the JSON data of the face counts:

```
2025/04/16 11:17:50 INFO {"timestamp":"2025-04-16T09:17:50.882075Z","average-faces-seen":1}
```

## Save data to BoltDB

Next switch to using the BoltDB database to store the face counts on disk.

Add a new `datastorage` key with the value `"boltdb"` into the `main]` section.

Also change the logging back to `warn` to reduce the amount of output on the terminal:

{{< tabpane text=true >}}
  {{% tab header="**Config**:" disabled=true /%}}
  {{% tab header="TOML" lang="en" %}}
  ```toml
[main]
logging = "warn"
datastorage = "boltdb"

[processing]
pipeline = [
    "facedetectyn.wasm",
    "face-counter.wasm"
]
```
  {{% /tab %}}
  {{% tab header="YAML" lang="en" %}}
```yaml
main:
  logging: "warn"
  datastoreage: "boltdb"

processing:
  pipeline:
    - "facedetectyn.wasm"
    - "face-counter.wasm"
```
  {{< /tab >}}
{{< /tabpane >}}


We need to tell wasmVision where the database file is located using the `WASMVISION_STORAGE_BOLTDB_FILENAME` environmental variable:

```bash
export WASMVISION_STORAGE_BOLTDB_FILENAME="facedata.db"
```

Now run the command again:

{{< tabpane text=true >}}
  {{% tab header="**Config**:" disabled=true /%}}
  {{% tab header="TOML" lang="en" %}}
```bash
wasmvision run -f facecount.toml
```
  {{% /tab %}}
  {{% tab header="YAML" lang="en" %}}
```bash
wasmvision run -f facecount.yaml
```
  {{< /tab >}}
{{< /tabpane >}}

The face count data should now be getting stored into the BoltDB database.

## Check BoltDB data

Let's check that the data is being stored into the BoltDB database as expected.

Install BoltDB command line utility, if you do not already have it:

```bash
go install go.etcd.io/bbolt/cmd/bbolt@latest
```

Now we can list the data that has been stored:

```bash
bbolt keys facedata.db face-counter
```

You should see output similar to this:

```
2025-04-16T09:29:47.294629Z
2025-04-16T09:29:57.340648Z
```

Use one of the keys displayed to retrieve the data:

```bash
bbolt get facedata.db face-counter 2025-04-16T09:29:47.294629Z
```

You should see output similar to this:

```
{"timestamp":"2025-04-16T09:29:47.294629Z","average-faces-seen":1}
```

## Turn off face box drawing

Now turn off the drawing of the face boxes in the output, since it is not needed.

To do this add a new `[configuration]` section to the file, and set the `detect-draw-faces` key to `"false"`.

This configuration setting is used by the `facedetectyn.wasm` processor to turn on or off the drawing of the detected faces on the output.

{{< tabpane text=true >}}
  {{% tab header="**Config**:" disabled=true /%}}
  {{% tab header="TOML" lang="en" %}}
  ```toml
[main]
logging = "warn"
datastorage = "boltdb"

[processing]
pipeline = [
    "facedetectyn.wasm",
    "face-counter.wasm"
]

[configuration]
detect-draw-faces="false"
```
  {{% /tab %}}
  {{% tab header="YAML" lang="en" %}}
```yaml
main:
  logging: "warn"
  datastoreage: "boltdb"

processing:
  pipeline:
    - "facedetectyn.wasm"
    - "face-counter.wasm"

configuration:
  detect-draw-faces: "false"
```
  {{< /tab >}}
{{< /tabpane >}}

Run the command again:

{{< tabpane text=true >}}
  {{% tab header="**Config**:" disabled=true /%}}
  {{% tab header="TOML" lang="en" %}}
```bash
wasmvision run -f facecount.toml
```
  {{% /tab %}}
  {{% tab header="YAML" lang="en" %}}
```bash
wasmvision run -f facecount.yaml
```
  {{< /tab >}}
{{< /tabpane >}}

Point your browser to `http://localhost:8080` and you should see that output no longer shows the face boxes for each face detected.

## Blur faces for privacy

The last step is for us to blur the detected faces to protect the privacy of the detected individuals.

Add another built-in processor named `faceblur.wasm`. This processor uses the same information that the `face-count.wasm` processor does, but with the purpose of blurring the detected faces in the resulting output.

{{< tabpane text=true >}}
  {{% tab header="**Config**:" disabled=true /%}}
  {{% tab header="TOML" lang="en" %}}
  ```toml
[main]
logging = "warn"
datastorage = "boltdb"

[processing]
pipeline = [
    "facedetectyn.wasm",
    "face-counter.wasm",
    "faceblur.wasm"
]

[configuration]
detect-draw-faces="false"
```
  {{% /tab %}}
  {{% tab header="YAML" lang="en" %}}
```yaml
main:
  logging: "warn"
  datastoreage: "boltdb"

processing:
  pipeline:
    - "facedetectyn.wasm"
    - "face-counter.wasm"
    - "faceblur.wasm"

configuration:
  detect-draw-faces: "false"
```
  {{< /tab >}}
{{< /tabpane >}}

Run the command again:

{{< tabpane text=true >}}
  {{% tab header="**Config**:" disabled=true /%}}
  {{% tab header="TOML" lang="en" %}}
```bash
wasmvision run -f facecount.toml
```
  {{% /tab %}}
  {{% tab header="YAML" lang="en" %}}
```bash
wasmvision run -f facecount.yaml
```
  {{< /tab >}}
{{< /tabpane >}}

Point your browser to `http://localhost:8080` and you should see that output now blurs each face detected.
