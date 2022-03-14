---
layout: default
title: Your First Unit Test
parent: Ponicode Unit Test (GUI)
nav_order: 2
grand_parent: The Ponicode VSCode extension
has_children: false
has_toc: false
---
# Creating your first unit test in the Ponicode Interface

Ponicode interface is composed of 2 sections:

- **Unit tests**: Shows test cases of your test file
- **Suggestions**: Suggestions provided by Ponicode AI for useful test cases

You can create unit tests from these two sections.

#### Using AI-generated suggestions

Creating unit test with the help of our AI is super simple:

When opening Ponicode on the function you want to test, suggestions will appear.

Simply add the ones you want by clicking on the plus right next to it:

<p align="center">
    <img src="/docs/vscode_extension/gui_test/images/webview_suggestions_plus.png" alt="ponicode_decorator" width="550"/>
</p>

And voilà! You can see the suggestion added to your list of units tests, and you can see the test written by clicking on the file in the top right corner.

<p align="center">
    <img src="/docs/vscode_extension/gui_test/images/suggestion_added.png" alt="ponicode_decorator" width="550"/>
</p>

#### Adding a test manually

However, if you want to test your function with specific parameters, you can write your own tests too only with the value you want (we'll do the rest promise)

To do so, add a test case by clicking on the blue cross shown as below:

<p align="center">
    <img src="/docs/vscode_extension/gui_test/images/add_test_case.png" alt="ponicode_decorator" width="550"/>
</p>

After that, you can write the wanted value(s) in the input cell, as shown in the screenshot below:

<p align="center">
    <img src="/docs/vscode_extension/gui_test/images/write_cell.png" alt="ponicode_decorator" width="550"/>
</p>

When you're done, you'll see the value in the cell.

And voilà! Check out your freshly generated test by clicking on the file in the top right corner!

<p align="center">
    <img src="/docs/vscode_extension/gui_test/images/test_case_added.png" alt="ponicode_decorator" width="550"/>
</p>

<div align="right">
    <a href="/docs/vscode_extension/gui_test/unitTests" >
        > The Unit Tests section
    </a>
</div>