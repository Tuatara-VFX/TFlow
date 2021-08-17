TFlow is a motion vector generator that helps increase the utility and quality of your flipbooks. With provided shader examples it adapts to many rendering pipelines.

![](https://i.imgur.com/G0HDxbH.gif)

# How does it work?

1. Use our baking tool to generate motion vectors for your flipbook
2. Use the motion vectors and the flipbook at runtime to get good quality frame blending

# Get TFlow

- [Unity Asset Store](https://u3d.as/2F5t)
- UE Marketplace - 🔜 Coming Soon

# What's inside

- An editor baking tool for Unity.

  ![](img/v1.jpg)

- Shaders, nodes and material examples to integrate optical flow in your projects.

# Support

TFlow baking tool works on any Windows platform/pipeline.

| Application         | Baking tool support |
|-------              |-------|
| Unity 2019.4 LTS    |  ✅  |
| Unity 2020.3 LTS    |  ✅  |
| Unity 2021.1        |  ✅  |
| Unity 2021.2b       |  ✅  |
| Unreal Engine       |  🔜 Coming Soon  |

A set of shader functions is available to use on any Unity or pipeline version. Using those functions you'll be able to support optical flow in your own shaders.
We also provide integration examples for Universal RP, High Definition RP, Shader Graph and Amplify Shader Editor.

| Pipeline            | Shaders support |
|-------              |-------|
| Unity Universal RP 10+       |  ✅  |
| Unity High Definition RP 10+      |  ✅  |
| Unity Amplify Shader Editor       |  ✅  |
| Unity VFX Graph     |  ✅  (Supported by default) |
| Unity Shader Graph  |  ✅  |
| Unity Custom Shaders  |  ✅  |
| Unreal Engine       |  🔜 Coming Soon  |

> 👉 If you need support for a specific Unity or pipeline version, feel free to contact us.

# Getting started

<details>
  <summary><strong>Unity Installation</strong></summary>

- Download TFlow package for Unity. See [Get TFlow](#get-tflow).
- Import the package in your Unity project

</details>
<details>
<summary><strong>Baking</strong></summary>

- Open the tool `Window > Tuatara > TFlow` or right click on your flipbook ``Tuatara > Open TFlow`.
- Drop your flipbook in and fill in the size
- Check *Loop* if your sequence is supposed to loop

> 💡 The column and row count will be filled automatically if the size is included in the file name like "*COLUMSxROWS*".

![baking_01](img/unity_baking_01.jpg)

- Press *Bake* and *Save As*.

For more details, check the *Advanced* chapter.
</details>

<details>
  <summary><strong>Universal RP Shaders setup</strong></summary>
  Explain here 
</details>

<details>
  <summary><strong>High Definition RP Shaders setup</strong></summary>
  Explain here 
</details>

<details>
  <summary><strong>Amplify Shaders setup</strong></summary>
  Explain here 
</details>

<details>
  <summary><strong>VFX Graph setup</strong></summary>
  Explain here 
</details>

<details>
  <summary><strong>Shader graph setup</strong></summary>
  Explain here 
</details>

# Advanced

<details>
  <summary><strong>Looping flipbooks</strong></summary>

![](img/looping.jpg)

If your animation is supposed to loop, enable the *Loop* checkbox so that the last frame blends with the first frame.
Otherwise, the last frame fades out.

</details>

<details>
  <summary><strong>Downsampling</strong></summary>

![](img/downsample.jpg)

- Input Downsample (red)

  Increase this value to reduce the input size before generating motion vectors. This will increase the processing speed and reduce the overall quality. 
  We recommend to increase this value only if the input size is higher than 2048x2048.

- Output Downsample (green)

  Increase this value as much as possible to get the smallest motion vectors texture and thus save runtime performance.
  Don't increase it if the blending looks worst.
  Changing this doesn't affect the processing speed.

</details>

<details>
  <summary><strong>Baking options</strong></summary>

![](img/optical_flow_options.jpg)

- **Softness** 

  Use a small value do detect fine detail/slow motion and a larger value for fast motion. 
  Using a larger value slow down the baking process.
  This setting is a simplification of *Search size* in *Advanced* settings. 

- **Offset**

  Play with this value if the blending doesn't look correct.
  Most of the time, there is no need to change it and you can leave it to 0.
  This setting will offset *Motion intensity* in *Advanced* settings. 
  It doesn't affect the motion vectors but only the blending.

- **Input downsample**

  See the **Downsampling** advanced topic.

- **Custom settings**

  When enabled, you get full control over *Motion Intensity* and *Search Size*. These settings are not designed to be used manually.

- **Motion intensity**

  Controls the motion vectors intensity in the blending process.
  With a value of 0, you can preview what the blending looks like without motion vectors, just a regular blending.
  This setting doesn't affect the motion vectors but only the blending.

- **Search size**

  TFlow use the *Farneback Optical Flow* algorithm to generate motion vectors and the *Search Size* is the most important setting.
  Use a small value do detect fine detail/slow motion and a larger value for fast motion. 
  Using a larger value slow down the baking process.
  It's in pixel space.

</details>

<details>
  <summary><strong>Export options</strong></summary>
![](img/export.jpg)

- **Downsample**

  See the **Downsampling** advanced topic.

- **Encode Motion Intensity**

  Save the motion intensity value (from *Optical flow options > Advanced*) into the blue and alpha channels.
  This value is required at runtime for blending. See the **Motion intensity** advanced topic.

- **Quality**

  Save the texture as 32bit per channel float [0, 1] or 8bit per channel [0, 255].
  Always choose Extreme quality unless you have strong size/performance constraints (such as Android platform).

- **Generate Mip Maps**

  Enable this to generate mip maps. 
  You can always change this afterwards in the texture import settings.

- **High quality compression**

  Always enable this if your platform support it, it's non destructive compression. 
  You can always change this afterwards in the texture import settings.


</details>

<details>
  <summary><strong>Motion intensity</strong></summary>
  WIP
</details>

<details>
  <summary><strong>Write your own shader</strong></summary>
  WIP
</details>

# Technical support

For any question related to TFlow or to get technical support.
- [Github](https://github.com/Tuatara-VFX/TFlow/issues)
- <support@example.com>

Don't hesitate to send us feature request as well.

# Resources

- [Tuatara](https://tuataragames.com/)
- [Free VFX Image Sequences & Flipbooks](https://blog.unity.com/technology/free-vfx-image-sequences-flipbooks)
