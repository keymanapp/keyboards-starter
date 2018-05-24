# Open Source Keyman keyboards starter template

## Introduction

This repository is designed to be used along with the instructions 
at <https://help.keyman.com/developer/keyboards/>. It is essentially an empty template
repository that provides just the tools and structure to allow you to submit a new keyboard 
layout to the primary keyboards repository hosted at <https://github.com/keymanapp/keyboards>. 
Note that if you plan to submit many keyboards, you should instead follow the instructions at 
the first link above on how to clone the full keyboards repository.

## File Layout

Keyboards are grouped into three folders:

  * `release` - keyboards with full source that pass our stringent quality checks, Unicode only
  * `legacy` - binary distributions of keyboards, migrated from Tavultesoft servers, Unicode and 
    non-Unicode
  * `experimental` - keyboards that have not yet passed the quality check, available from the 
    'experimental' category in Keyman apps with Keyman 10 and later. Unicode only.

Within each of the folders, keyboards are further grouped by first letter or by prefix, where 
multiple keyboards share the same prefix indicating provenance, for example `sil` or `gff`.

In most circumstances, you should create a subfolder tree for your keyboard layout under
`release/e/example`, where _e_ and _example_ are the first initial and the full name of your
keyboard, respectively.

## Contributing

First, read the guide! <https://help.keyman.com/developer/keyboards/>

Keyman Developer 10.0 is recommended to edit these files. <https://keyman.com/developer>

## Building Keyboards

### Prerequisites

Windows:
  * Git for Windows (or MinGW)
  * You will need to use **Git Bash** or equivalent to build (not tested with Cygwin), not 
    Windows Command Prompt or PowerShell.
  * You can also **WSL** (Bash on Ubuntu on Windows) if you place the repo in a 
    Windows-accessible path (such as `/mnt/c/...`), so the Keyman Developer Compiler 
    can run (requires Windows 10 Anniversary Update or later). Beware of line-ending changes
    if mixing Windows and WSL usage!

Linux, macOS:
  * **WINE** is required in order to run the Keyman Developer 
    compiler which is currently a Windows-only executable.

### Build instructions

`build.sh` can be used to build all the keyboards from the command line.
  
* The Keyman Developer compiler is included in the `tools/` folder and so Keyman Developer 
  is not required for builds.
  
* Common `build.sh` parameters:
  * `--help     List build.cmd parameters`
  * `-s         Quieter build`
  * `-c         Clean instead of build`
  * `-d         Include debug information`
  * `-w         Treat warnings as errors`
  * `[target]   Specific folder to build`

* Each keyboard also includes a project file which can be used to build the project - either from the command line 
  kmcomp compiler, or from the Keyman Developer IDE.

## Deprecated keyboards

If a keyboard has been replaced by another keyboard, include a DEPRECATED.md file in the folder referencing the 
new keyboard name.

## Common links

   * <https://help.keyman.com/developer/keyboards/>: Guide to working with this repository 
   * <https://keyman.com/developer/keymanweb/keyboards.php>: Published documentation for each keyboard
   * <https://r.keymanweb.com/api/4.0/keyboards/>: JSON API for compiled keyboards available from Keyman Cloud
   * <https://help.keyman.com/developer/cloud/keyboard_info/>: Documentation on the .keyboard_info file format used in this repository
   * <https://github.com/keymanapp/keyboards>: Primary keyboards repository.