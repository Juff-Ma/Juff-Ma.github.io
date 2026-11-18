---
title: "AvaloniaAcrylic"
date: "2026-09-26"
tags: ["Avalonia", "GUI"]
topics: ["Projects"]
type: "blank"
draft: false
---
Acrylic/Frosted glass controls for Avalonia

# [AvaloniaAcrylic](https://github.com/Juff-Ma/AvaloniaAcrylic)

Avalonia by default does not include frosted glass controls that work in the actual rendering environment. What it does include is a OS-Powered acrylic renderer.

In the past there have been multiple gists and code snippets for implementing something like this. I built AvaloniaAcrylic as a drop in package for rendering such a control.

With code as simple as

```xaml
<acrylic:AcrylicBackdropControl Width="50" Height="50"/>
```

one can display beautiful acrylic UI elements on all platforms supported by Avalonia.Skia.

### Sample

![Screenshot](https://raw.githubusercontent.com/Juff-Ma/AvaloniaAcrylic/refs/heads/main/assets/SampleApp.png)

The screenshot above shows what's actually possible beside just basic squares.
