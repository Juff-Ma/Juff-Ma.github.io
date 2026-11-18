---
title: "VSCode2MSI"
date: "2024-08-02"
tags: ["MSI"]
topics: ["Projects"]
type: "blank"
draft: false
---
Tool for repackaging VSCode to an MSI

# [VSCode2MSI](https://github.com/Juff-Ma/VSCode2Msi)

Sadly, Microsoft doesn't publish MSIs for VSCode. This makes it difficult for people who prefer or require one (e.g. GPO deployment).

VSCode2MSI is designed to solve this problem by doing what Microsoft does not: creating VSCode MSIs.

It does this by repackaging a zip release of VSCode using WiX.

Once the MSI has been built you can install it like any other and it will pretty much work like a normal VSCode installation.
