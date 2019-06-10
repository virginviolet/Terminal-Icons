# Terminal-Icons

A PowerShell module to show file and folder icons in the terminal.

| Azure Pipelines | GitHub Actions | PSGallery | License |
|-----------------|----------------|-----------|---------|
[![Azure Pipelines Build Status][azure-pipeline-badge]][azure-pipeline-build] | [![GitHub Actions Status][github-actions-badge]][github-actions] | [![PowerShell Gallery][psgallery-badge]][psgallery] | [![License][license-badge]][license]

<p align="center">
    <img src="./media/icon_256.png" alt="Icon">
</p>

## Overview

*Terminal-Icons* is a PowerShell module that adds file and folder icons when displaying items in the terminal.
This relies on the custom fonts provided by [Nerd Fonts](https://github.com/ryanoasis/nerd-fonts).


> You must be using one of the fonts provided by Nerd Fonts for this module to work as these fonts include tons of custom glyphs/icons that are referenced by their unicode number.

## How Does this Work?
It uses a custom [format.ps1xml](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_format.ps1xml?view=powershell-6) file that inspects the items being displayed and looks up their appropriate icon based on name or extension.
Icons for well-known files/folders are attempted to be used first before displaying an icon based on the file extension.
Any files/folders that are not matched are shown using a generic file or folder icon.

## Installation

To install the module from the [PowerShell Gallery](https://www.powershellgallery.com/):

```powershell
PS> Install-Module -Name Terminal-Icons -Repository PSGallery
```

## Usage

```powershell
Get-Item ./README.md

Get-ChildItem

Get-ChildItem | Format-List

Get-ChildItem | Format-Wide
```

## Commands

| Command | Description |
|---------|-------------|
Add-TerminalIconsColorTheme | Add a Terminal-Icons color theme for the current user.
Add-TerminalIconsIconTheme  | Add a Terminal-Icons icon theme for the current user.
Format-TerminalIcons        | Prepend a custom icon (with color) to the provided file or folder object when displayed.
Get-TerminalIconsColorTheme | List the available color themes.
Get-TerminalIconsIconTheme  | List the available icon themes.
Get-TerminalIconsTheme      | Get the currently applied color and icon theme.
Set-TerminalIconsColorTheme | Set the Terminal-Icons color theme.
Set-TerminalIconsIconTheme  | Set the Terminal-Icons icon theme.
Show-TerminalIconsTheme     | List example directories and files to show the currently applied color and icon themes.

## Screenshots

```powershell
Get-ChildItem -Path . -Force
```

![Screenshot 1](./media/screenshot1.PNG)

## Contributions

Any ideas on how to improve this module are welcome.
If you have ideas for an appropriate [glyph](http://nerdfonts.com/#cheat-sheet) to display for a well-known folder or file, or a particular file extension, please raise an [issue](https://github.com/devblackops/Terminal-Icons/issues/new).
If you'd like to submit an entirely new color or icon theme, take a look at the existing ones [here](https://github.com/devblackops/Terminal-Icons/tree/master/Terminal-Icons/Data/colorThemes) and [here](https://github.com/devblackops/Terminal-Icons/tree/master/Terminal-Icons/Data/iconThemes), create your new file(s) named what ever you like, and submit a pull request.

[azure-pipeline-badge]: https://dev.azure.com/devblackops/Terminal-Icons/_apis/build/status/devblackops.Terminal-Icons?branchName=master
[azure-pipeline-build]: https://dev.azure.com/devblackops/Terminal-Icons/_build/latest?definitionId=6&branchName=master
[github-actions-badge]: https://wdp9fww0r9.execute-api.us-west-2.amazonaws.com/production/badge/devblackops/Terminal-Icons
[github-actions]:       https://wdp9fww0r9.execute-api.us-west-2.amazonaws.com/production/results/devblackops/Terminal-Icons
[psgallery-badge]:      https://img.shields.io/powershellgallery/dt/terminal-icons.svg
[psgallery]:            https://www.powershellgallery.com/packages/terminal-icons
[license-badge]:        https://img.shields.io/github/license/poshbotio/poshbot.svg
[license]:              https://www.powershellgallery.com/packages/poshbot
