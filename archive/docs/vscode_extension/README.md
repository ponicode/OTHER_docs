# The Ponicode VSCode extension


Ponicode VSCode extension is an IDE extension which allows to generate Unit Tests for your Javascript, Typescript and Python code in a matter of seconds.

Follow the [Get Started guide](vscode_extension/get_started/) to learn how to install and activate the extension.

Whenever Ponicode identifies a function in your code which it is able to test, it displays a little Pony icon to its left. On each of these functions, you can decide to apply **Ponicode Unit Test** or **Ponicode Flash Test**.

[**Ponicode Unit Test**](vscode_extension/gui_test/) opens the **Ponicode interface**, a GUI built specifically to simplify the display, creation and manipulation of unit tests. The Ponicode interface allows a high level of customisation - enabling you to choose and edit your inputs, mocks and assertions.

[**Ponicode Flash Test**](vscode_extension/flash_test/) automatically generates a test suite for your function, without passing through a GUI. These tests are bootstrapped directly in the file, and can be committed as they are or can be edited by you manually at a later time.

Both features are powered by the **Ponicode's AI engine**, which suggests relevant input values for the function under test

Make sure you also explore the [**Ponicode Side Panel**](vscode_extension/side_panel/), a place where to find information on all the files and functions where Ponicode can help you test.

Visit the section [**Supported Technologies**](vscode_extension/supported_technologies/) to find out which IDEs Ponicode is available for, and which languages and test frameworks are coming next.

<p align="center" >
    <img src="images/vscode.png" alt="vscode" width="85"/>
</p>