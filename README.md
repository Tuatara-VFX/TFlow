TFlow is a motion vectors generator that helps increase the utility and quality of your flipbooks. With provided shader examples it adapts to many rendering pipelines.

![](https://i.imgur.com/G0HDxbH.gif)

# How does it work?

1. Use our baking tool to generate motion vectors for your flipbook.
2. Use the motion vectors texture and the flipbook at runtime to get optical flow blending.

# Get TFlow

- [Unity Asset Store](https://u3d.as/2F5t)
- UE Marketplace - 🔜 Coming Soon

# What's inside

- An editor baking tool for Unity that generate motion vectors textures.

  ![](img/v1.jpg)

- Shaders, nodes and material examples to use optical flow blending in your projects.

# Support

TFlow baking tool works on any Windows platform/pipeline.

| Application                 | Baking tool support |
|-------                      |-------|
| Windows Unity 2019.4 LTS    |  ✅  |
| Windows Unity 2020.3 LTS    |  ✅  |
| Windows Unity 2021.1        |  ✅  |
| Windows Unity 2021.2b       |  ✅  |
| Unreal Engine       |  🔜 Coming Soon  |

A set of shader functions is available to use on any Unity or pipeline version. Using those functions you'll be able to support optical flow in your own shaders.
We also provide integration examples for Universal RP, High Definition RP, Shader Graph and Amplify Shader Editor.

| Pipeline            | Shaders support |
|-------              |-------|
| Unity Universal RP 10+       |  ✅ |
| Unity High Definition RP 10+      |  ✅  |
| Unity Amplify Shader Editor       |  ✅  |
| Unity VFX Graph     |  ✅ |
| Unity Shader Graph  |  ✅ |
| Unity Custom Shaders  |  ✅ |
| Other or older Unity pipelines | ✅ but without examples, see **Advanced > Write your own shader**  | 
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

- Open the tool `Window > Tuatara > TFlow` or right click on your flipbook `Tuatara > Open TFlow`.
- Drop your flipbook in and fill in the size
- Check *Loop* if your sequence is supposed to loop

> 💡 The column and row count will be filled automatically if the size is included in the file name like "*COLUMSxROWS*".

![baking_01](img/unity_baking_01.jpg)

- Press *Bake* and *Save As*.

For more details, check the [Advanced](#advanced) chapter.
</details>

<details>
  <summary><strong>Universal RP</strong></summary>
  Extract Universal RP package located in `TFlow/Runtime/Examples` folder.
Open Universal RP scene located in `TFlow/Runtime/Examples/Universal RP` folder.

 **1. Particle System Shaders**
 
We have added optical flow behaviors in our own version of Unity Universal RP particle shaders. You can use them in your materials but selecting one of those :

    Universal Render Pipeline/Particles/Optical Flow/Lit
    Universal Render Pipeline/Particles/Optical Flow/Simple Lit
    Universal Render Pipeline/Particles/Optical Flow/Unlit

To enable optical flow behaviors, you must enable **Flip-Book Blending** and **Optical Flow Blending** and fill the properties correctly.

 1. **Motion Vector** - The texture computed using TFlow baker.
 2. **Columns and Rows** - The related frame count of your flipbook.
 3. **Motion Intensity Encoded** - Did you encoded the intensity in the Motion Vector texture ?
 4. **Motion Intensity** - If the value is not encoded in the texture then use the value in contained in the texture file name (Ex: *8x8_Explosion_MotionVectors_Intensity-0371* fill **0.0371**). You can also get the value in the clipboard by right clicking on the texture (see **Motion Intensity** section).

 **2. Example Shader**
We provide a shader example made with **Shader Graph** to illustrate the usage of the custom nodes. This shader can be selected in `Tuatara/OpticalFlow`.
For more explanations about shader creation with optical flow behaviors using **Shader Graph**, see **Shader Graph** section.

 **3. Shader Functions**
We provide a set of functions that you can use in handwriten shaders or in any node base shader authoring tool.
For more informations about those functions, see **Shader Functions** section.

 **4. Shader Functions**
 We provide a VFX Graph example. By using the VFX Graph without any custom shader, optical flow work out of the box with **Uv Mode** set to **Flipbook Motion Blend**.
For more informations about those functions, see VFX Graph section. 
</details>

<details>
  <summary><strong>High Definition RP</strong></summary>
  Explain here 
</details>

<details>
  <summary><strong>Amplify Shader Editor</strong></summary>
  Explain here 
</details>

<details>
  <summary><strong>VFX Graph</strong></summary>
  Explain here 
</details>

<details>
  <summary><strong>Shader Graph</strong></summary>
  Explain here 
</details>

<details>
  <summary><strong>Shader Functions</strong></summary>
  Explain here 
</details>

# Advanced

<details>
  <summary><strong>Looping flipbooks</strong></summary>

![](img/looping.jpg)

If your flipbook animation is supposed to loop, enable the *Loop* checkbox so that the last frame blends with the first frame.
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

  See **Advanced > Downsampling**.

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

  See **Advanced > Downsampling** .

- **Encode Motion Intensity**

  Save the motion intensity value (from *Optical flow options > Advanced*) into the blue and alpha channels.
  This value is required at runtime for blending. See **Advanced > Motion intensity**.

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
  
  The motion intensity defines how the motion vector texture should influence the blending. It's needed at runtime because the Motion Vector texture is normalized and need to be transformed before being used.
  By default, the motion intensity is in the file name and encoded in the blue and alpha channels. We only keep track of the fractional part of the intensity number (with and intensity of **0.0371** the file name would be *8x8_Explosion_MotionVectors_Intensity-0371*).

  Storing the motion intensity in two places allow to have a motion vectors texture that can be used in any pipeline.

  If you choose to name the texture differently, you can always get the motion texture with right click *Tuatara > Copy Motion Intensity into clipboard*.

  ![](img/encoded_motion_intensity.jpg)
  ![](img/encoded_motion_intensity_log.jpg)

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
