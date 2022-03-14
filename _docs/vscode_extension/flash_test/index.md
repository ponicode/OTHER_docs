---
layout: default
title: Ponicode Flash Test
nav_order: 3
parent: The Ponicode VSCode extension
has_children: false
has_toc: false
---

# Flash Test

Ponicode Flash Test allows you to generate non-regression snapshot tests in one click.

Simply click on *"Ponicode Flash Test"* above the function you want to test (after having made sure it has a pony next to it). 

<p align="center">
    <img src="/docs/vscode_extension/flash_test/images/flash_test_decorator.png" alt="Flash test decorator" width="300"/>
</p>

A window will open next to it, showing you the progress Ponicode is making in writing the test file.

<p align="center">
    <img src="/docs/vscode_extension/flash_test/images/flash_test.png" alt="Flash test interface" width="400"/>
</p>

Once Flash Test succeeds, the test file is opened for you automatically.

For each tested function, Ponicode writes one test suite which contains from 4 to 7 test cases. The selection of scenarios is chosen by the Ponicode AI based on what it considers more pertinent to test in order to increase your coverage. You will always find a few *happy paths* and a few *edge cases*.

<p align="center">
    <img src="/docs/vscode_extension/flash_test/images/flash_test_result.png" alt="Flash test result" width="400"/>
</p>

You can configure the location where your tests are written in your [Test Location Settings](/docs/vscode_extension/gui_test/configuration/testLocation).