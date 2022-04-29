---
layout: default
title: Ponicode Generate Values
nav_order: 3
parent: The Ponicode VSCode extension
has_children: false
has_toc: false
---

# Generate Values *[TS only]*

Ponicode Generate Values allows you to generate example values that match a given type.  

It can be applied to type declarations, class declarations, function input parameters, function return types, and variables.
For now, it is only available for TypeScript.

### Types and classes
You will see a CodeLens decoration above all type and class declarations, reading *"Ponicode: Generate Values"*.

<p align="center">
    <img src="/docs/vscode_extension/generate_values/images/types.png" alt="Generate values decorator" width="300"/>
</p>

When you click on it, a new tab will open, showing you all the values Ponicode was able to suggest for the selected type.
You can select whether you want happy paths or edge cases by selecting the desired tab at the top of the page.

<p align="center">
    <img src="/docs/vscode_extension/generate_values/images/webview_types.png" alt="webview type" width="400"/>
</p>


If you want to generate values only for one particular property of a type or an object, you can **right click** on the property and select *"Ponicode: Generate Values"*. For instance, in the example below, values will be only generated for the property *"surname"* rather than for the whole object *"User"*.

<p align="center">
    <img src="/docs/vscode_extension/generate_values/images/property.png" alt="property" width="400"/>
</p>

Once again, a tab will open showing you all the values Ponicode was able to suggest for the selected property:

<p align="center">
    <img src="/docs/vscode_extension/generate_values/images/webview_property.png" alt="property webview" width="400"/>
</p>


### Functions


You can also generate values for functions, by right clicking on a **function declaration** or a **function call**, and selecting *"Ponicode: Generate Values"*:

<p align="center">
    <img src="/docs/vscode_extension/generate_values/images/function.png" alt="function" width="400"/>
</p>

<p align="center">
    <img src="/docs/vscode_extension/generate_values/images/function_rightclick.png" alt="function right click" width="400"/>
</p>

The "Generate Values" tab will allow you to choose between visualising values that match:
* The **input parameters** of the function
* The **return type** of the function
To switch between input parameters and return type, you can use the buttons at the top of the page:

<p align="center">
    <img src="/docs/vscode_extension/generate_values/images/input_param.png" alt="input param webview" width="400"/>
</p>

<p align="center">
    <img src="/docs/vscode_extension/generate_values/images/return_value.png" alt="return type webview" width="400"/>
</p>

### Variables

You can also generate values that match a variable's type. Once again, right click on the desired variable and select *"Ponicode: Generate Values"*.