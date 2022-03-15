# Modifying the test file

Ponicode allows you to generate a test file automatically according to the test cases you are adding.  

In many cases you might want to modify the generated test file.

**Changes compliant with the Ponicode interface**

The following changes to the test file allow you to continue using the Ponicode interface to add, modify and run your tests:

-   Add custom imports to add globals, custom variables, custom classes etc... and use them in your test cases, or directly in the extension in the cells: see [here](add link to what can be entered in the cell)
-   Modify the `beforeEach` section
-   Add simple test cases that is Ponicode syntax friendly
-   Modify custom validation function s
-   Modify test description
-   Delete a test case

**Changing to Manual**

If you desire to make changes beyond the areas listed above, you can still do so. However, you will notice that your test suite will disappear from the Ponicode Interface.

When you are in Manual Mode, you can still use the Ponicode Interface to generate *new* test suites with as many test cases as you like, but you will lose the advantages or being able to edit and run your previous tests through a GUI.

**Errors**

A red bar at the top of the Ponicode interface indicates that Ponicode is encountering a problem while parsing your test file. 
This could be due to network errors or to a real parsing issue. If you encounter such a situation do not hesitate to contact the Ponicode team at ping@ponicode.com.

<div align="right">
    <a href="#/vscode_extension/gui_test/importSyntax.md" >
        > Supported import syntax
    </a>
</div>
