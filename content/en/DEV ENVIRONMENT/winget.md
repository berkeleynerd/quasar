---
title: "Winget"
linkTitle: "Winget"
weight: 3
description: >
   discover, install, and manage applications from the command-line
---

{{% pageinfo %}}
Winget is installed by default with Windows 11
{{% /pageinfo %}}

We are also going to need a package manager. What is a package manager you ask? Well, it's an application you use from the command line to install, upgrade, and remove applications. If you have heard of chocolatey it's like that but made by Microsoft. If you come from the Mac world you can think of it as a Windows version of homebrew.

To install `winget` browse to its release page on GitHub, download the latest **.msixbundle** file, then double-click it. Make sure the version you download is marked **latest release** and isn't an old or preview release.

[Download WinGet](https://github.com/microsoft/winget-cli/releases)

## Upgrading packages
You can update any app installed with winget to the latest version with the command `winget upgrade <package>`

The command `winget list <package>` will report the version currently installed and whether an upgrade is available. You can also run `winget list` without specifying a package to check if upgrades are available for any installed package.