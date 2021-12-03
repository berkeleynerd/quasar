---
title: "Powershell"
linkTitle: "Powershell"
weight: 4
description: >
   microsoft's cross-platform command-line shell and cmdlet scripting language 
---

Finally, we need to decide on a shell to use within our terminal environment. Since this guide assumes you are using Windows we will stick with Microsoft's default PowerShell environment for now. Other options available include Microsoft's Windows Subsystem for Linux (WSL) and the version of the classic Linux BASH shell installed along with Git. These other options all involve additional setup, however, and come with various limitations and caveats in addition to the advantages they provide in some scenarios.

## Update PowerShell

An older version of PowerShell called, confusingly, Windows PowerShell is included by default when Windows is installed and can not be upgraded or uninstalled. It is also locked-down by default as it is intended for system administration. You can use this version if you prefer but to do so and follow along with this guide you will need to loosen these restrictions for the current user by executing the command `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser`

To use the latest release version of PowerShell you can install it using winget :

```
winget install Microsoft.PowerShell
```

## Update the default PowerShell profile

While there are some amazingly functional and visually appealing ways to [customize your PowerShell prompt](https://www.hanselman.com/blog/my-ultimate-powershell-prompt-with-oh-my-posh-and-the-windows-terminal) we are going to simply update ours using a small script that will display the Git branch associated with the current directory if it is under source control. This will help us determine at a glance if we are working in the correct branch.

```
Invoke-WebRequest -Uri "https://git.io/JXGyz" -OutFile $PROFILE
```

## Shell and terminal defaults

To load the latest version of PowerShell by default and / or configure Windows Terminal as your default terminal application navigate to the _Settings _tab in Windows Terminal using the shortcut `Ctrl-,` and set the following values:  
![Windows Terminal](WindowsTerminal-Defaults.png)