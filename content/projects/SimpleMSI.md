---
title: "SimpleMSI"
date: "2025-11-01"
tags: ["MSI"]
topics: ["Projects"]
type: "blank"
draft: false
---
Simple config-based tool to build MSI packages.

# [SimpleMSI](https://github.com/Juff-Ma/SimpleMSI)

Building MSI files is hard. Most tools are either proprietary and cost thousands of dollars or have a very steep learning curve.

SimpleMSI fixes this by doing what it says on the tin: letting devs build an MSI installer the easy way.

That way

- Paid and proprietary software
- Complicated tools and/or unreadable configuration formats
- Knowing a language like C# or JS to script the installer

turns into easy and friendly

- Free and open source
- Simple command line interface with sensible defaults
- No scripting required, just a plain TOML file

Such a TOML file can, in fact, look as basic as this:

```toml
[general]
guid = "6b62cc5c-4d7b-4377-a322-eb825c074c9e"
name = "YourApp"
platform = "x64"
version = "1.0.0"
install_scope = "machine"

[install]
source_files = []
source_dirs = ["build-dir\\*.*"]

[[install.env_vars]]
name = "PATH"
value = "@"
part = "suffix"

[[install.shortcuts]]
target = "your-main.exe"
```

In fact, I didn't even write that myself. It was generated with a single command, namely: `simplemsi init YourApp -e your-main.exe -d build-dir\*.*`.

Of course you will not have every option available to you that you get with more complex MSI tools. But SimpleMSI condenses them down into a subset that most apps actually need.