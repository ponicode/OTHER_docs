---
layout: default
title: Test Location settings
nav_order: 15
parent: Ponicode Unit Test (GUI)
grand_parent: The Ponicode VSCode extension
has_children: true
has_toc: false
---

# Test Location

Ponicode allows configuring where your unit tests are written.

To change the settings, open your preferences (<kbd>cmd</kbd> on MacOS or <kbd>ctrl</kbd>+ <kbd> , </kbd>), then type in the search bar _"Ponicode test location"_.

Alternatively, you can open the settings directly from your Ponicode interface, by clicking on the <i class="fas fa-cog" style="color:blue"></i>`Test settings (gear icon)` on the top right corner.

<p align="center">
    <img src="/docs/vscode_extension/gui_test/configuration/images/test_location_1.png" alt="test_settings_icon" width="750"/>
</p>

Two fields can be modified: `Test Location: Location Type` and `Test Location: Path`. Each of them can be configured by `User` or `Workspace`.

#### User or workspace?

You have a choice to configure your settings by `User` or `Workspace`, please only use workspace when changing Ponicode related settings.

<p align="center">
    <img src="/docs/vscode_extension/gui_test/configuration/images/test_location_2.png" alt="test_settings_icon" width="750"/>
</p>

##### Test Location: Location Type

This field can take one of the following three values:

- Same path as source file
- In folder _"\_\_tests\_\_"_ at worspace root
- Custom

<p align="center">
    <img src="/docs/vscode_extension/gui_test/configuration/images/test_location_3.png" alt="Test Location: Location Type section" width="650"/>
</p>

`Same path as source file` and `In folder __tests__ at workspace root` are the two options recommended by Ponicode, and there are associated with strict Test location paths. If you want to customise your path, just select `Custom` and adjust the path as you like.

##### Test Location: Path

The following keywords can be used to defined the path:

- _"{rootDir}"_: refers to the workspace folder that each file is contained in, or - when a file is not in a workspace - the path of the file itself.
- _"{filePath}"_: refers to the relative path from the {rootDir} to the file a test should be created for, excluding the filename itself. This can be - used to recreate the same file tree in a separate tests folder, for example.
- _"{fileName}"_: refers to the basename of the file a test should be created for, excluding its extension.
- _"{ext}"_: refers to the extension of the file a test should be created for. It must be preceded by the character _"."_

<p align="center">
    <img src="/docs/vscode_extension/gui_test/configuration/images/test_location_4.png" alt="Test Location: Location Type section" width="650"/>
</p>

The following constraints apply to the combination that can be created using the above keywords.

- Characters allowed in directory and file names are restricted to: _[a-z]_, _[A-Z]_, _[0-9]_, _"\_"_ (underscore), _"#"_ (dash), _"."_ (dot) and _" "_ (space). (Note: **only** underscore is a valid character in Python test file location). All other characters are considered invalid.
- _"."_ and _".."_ are accepted as valid directories.
- Each keyword can be used only once in the path. All of them are optional, except for _"{ext}"_ which is mandatory.
- The path cannot be absolute. If it does not begin with _"{rootDir}"_ or _"."_, it is assumed as implicit.
- For now, no directory can be excluded from the _"{filePath}_".For example, if the path for a file is _"{rootDir}/src/foo/bar/myFile.js"_, it is not possible to exclude src from the _"{filePath}"_. This means that Ponicode generated tests cannot be written in a path such as _"{rootDir}/tests/foo/bar/myFile.js"_. Instead, it is possible to write into: _"{rootDir}/tests/src/foo/bar/myFile.{ext}"_
- The following path (and its synonyms) is considered invalid because the test file would have the same path as the source file: _"{rootDir}/{filePath}/{fileName}.{ext}"_

**Note:** for the time being, the same convention applies to all files in the same workspace - irrespectively of language. In the future, we will allow to define different test file location conventions for unit tests of each different language supported by Ponicode.
