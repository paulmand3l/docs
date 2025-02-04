---
title: "Configure a Fake Camera"
linkTitle: "Fake"
weight: 35
type: "docs"
description: Configure a camera to use for testing."
tags: ["camera", "components"]
# SMEs: Bijan, vision team
---

A `fake` camera is a camera model for testing.
The camera always returns the same image, which is an image of a gradient.
This camera also returns a point cloud.

You can optionally specify either a height or width, and the image will be scaled to preserve a 16:9 aspect ratio.
You cannot specify both a height and width.

{{< tabs name="Configure a Fake Camera" >}}
{{% tab name="Config Builder" %}}

On the **COMPONENTS** subtab, navigate to the **Create Component** menu.
Enter a name for your camera, select the type `camera`, and select the `fake` model.

<img src="../img/create-fake.png" alt="Creation of a join color depth view in the Viam app config builder." style="max-width:600px" />

Fill in the attributes for your join color depth view:

<img src="../img/configure-fake.png" alt="Configuration of a join color depth view in the Viam app config builder." />

{{% /tab %}}
{{% tab name="JSON Template" %}}

```json {class="line-numbers linkable-line-numbers"}
{
    "name": "<camera_name>",
    "type": "camera",
    "model" : "fake",
    "attributes": {
        "width": <integer>,
        "height": <integer>
    }
}
```

{{% /tab %}}
{{< /tabs >}}

The following attributes are available for fake cameras:

| Name | Inclusion | Description |
| ---- | --------- | ----------- |
| `width` | *Optional* | The width of the image in pixels. The default resolution is 1280 x 720. If you specify either width or height, the image gets scaled to preserve 16:9 aspect ratio. You cannot specify both `width` and `height`. |
| `height` | *Optional* | The width of the image in pixels. The default resolution is 1280 x 720. If you specify either width or height, the image gets scaled to preserve 16:9 aspect ratio. You cannot specify both `width` and `height` |

## View the camera stream

Once your camera is configured, go to the **CONTROL** tab, and click on the camera's dropdown menu.
Then toggle the camera or the Point Cloud Data view to ON.
You will see the live video feed from your camera.
You can change the refresh frequency as needed to change bandwidth.

![Fake Camera View](../img/fake-view.png)

## Next Steps

{{< readfile "/static/include/components/camera-model-next-steps.md" >}}
