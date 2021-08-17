TFlow is a motion vector generator that helps increase the utility and quality of your flipbooks. With provided shader examples it adapts to many rendering pipelines.

![](https://i.imgur.com/G0HDxbH.gif)

To get TFlow: 
- [Unity aset store product page](missing_link)
- Unreal Engine coming soon

# What's inside

- An editor baking tool for Unity
- TODO: Shaders

# Support

TFlow baking tool works on any platform/pipeline.

| Application         | Baking tool support |
|-------              |-------|
| Unity 2019.4 LTS    |  ✅  |
| Unity 2020.3 LTS    |  ✅  |
| Unity 2021.1        |  ✅  |
| Unity 2021.2b       |  ✅  |
| Unreal Engine       |  🔜 Work in progress  |

However, shaders support is not as simple as there is many pipeline versions.

> 👉 If you need support for TFlow for a specific pipeline version, please contact us through the asset store page.

| Pipeline            | Shaders support |
|-------              |-------|
| Unity URP 11+       |  ✅  |
| Unity HDRP 11+      |  ✅  |
| Unity Amplify       |  ✅  |
| Unity VFX Graph     |  ✅  (supported by default) |
| Unity Shader Graph  |  ✅  |
| Unity Custom Shaders  |  ✅  |
| Unreal Engine       |  🔜 Work in progress  |

# Getting started

<details>
  <summary><strong>Installation</strong></summary>

- Download TFlow package for [Unity](missing_link)
- Import the package in a Unity project
- The tool can be opened from `Window > Tuatara > TFlow`
</details>
<details>
<summary><strong>Baking</strong></summary>

- Open the tool `Window > Tuatara > TFlow`
- Drop your flipbook in and fill in the size
- Check *Loop* if your sequence is supposed to loop

> 💡 The column and row count will be filled automatically if the size is included in the file name like "*COLUMSxROWS*".

![baking_01](img/unity_baking_01.jpg)

- Press *Bake* and *Save As*.

For more informations, check the *Advanced* chapter.
</details>
<details>
  <summary><strong>Runtime / Unity VFX Graph</strong></summary>
  Explain here 
</details>

# Advanced

<details>
  <summary><strong>Use TFlow Motion Vectors in custom shaders</strong></summary>
  WIP
</details>

# Technical support

[Submit an issue here](https://github.com/Tuatara-VFX/TFlow/issues) to ask any question related to TFlow or to get technical support. 

Don't hesitate to send us feature request as well.

# Resources

- [Tuatara website](https://tuataragames.com/)
