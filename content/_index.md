---
title: "wasmVision Home"
---

{{< blocks/cover title="" image_anchor="top" height="min" color="primary" >}}

![wasmVision Logo](images/wasmvision-logo-icon-transparent.png)

<p class="display-1 mt-0 mt-md-5 pb-4">wasmVision</p>
<p class="h2 mt-md-5 pb-4">Get going with computer vision</p>

<div class="mx-auto">
	<a class="btn btn-lg btn-primary mr-3 mb-4" href="{{< relref "/getting-started" >}}">
		Get Started <i class="fas fa-arrow-alt-circle-right ml-2"></i>
	</a>
	<a class="btn btn-lg btn-secondary mr-3 mb-4" href="https://github.com/wasmvision/wasmvision">
		See the code <i class="fab fa-github ml-2 "></i>
	</a>
</div>

{{< /blocks/cover >}}

{{% blocks/lead color="secondary" %}}

wasmVision is a high-performance computer vision processing engine with advanced algorithms and vision models, that is designed to be customized and extended using WebAssembly.

{{% /blocks/lead %}}

{{< blocks/section color="primary-light" type="row">}}
{{% blocks/feature icon="fa fa-video-camera" title="Capture" url="docs/concepts/capture" %}}
    Capture video from cameras,
    video files, or streams
{{% /blocks/feature %}}

{{% blocks/feature icon="fa fa-cogs" title="Process" url="docs/concepts/processors" %}}
    Process video using computer vision
    algorithms and machine learning models
{{% /blocks/feature %}}

{{% blocks/feature icon="fa fa-film" title="Output" url="docs/concepts/output" %}}
    Output results to a stream,
	video file, or data store
{{% /blocks/feature %}}
{{< /blocks/section >}}

{{% blocks/lead color="secondary" %}}

Use the built-in processors for face detection, edge detection, and other common tasks.

You can also create your own processors using Go, Rust, and C programming languages.

Ready to get started? [Click here](getting-started).

{{% /blocks/lead %}}
