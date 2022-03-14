---
layout: default
title: Interface Cells
parent: Ponicode Unit Test (GUI)
nav_order: 5
grand_parent: The Ponicode VSCode extension
has_children: false
has_toc: false
---

# What can be entered in a cell

Each row in the Ponicode interface corresponds to a test case. Each cell corresponds to a value - be it an input value, a mock value, an assertion value, or a value that indicates the tested instance.
## Inputs

Input cells can be populated with simple values or expressions.
Expressions are currently only supported in JavaScript and TypeScript, not in Python.
#### Simple values

-   strings: `Hello World !`
-   numbers: 42
-   booleans:
    -   JS/TS: `true` / `false`
    -   Python: `True` / `False`
-   null/undefined:
    -   JS/TS: `undefined` or `null`
    -   Python: `None`
-   arrays: `['one', 2, 'three', true]` (and tuple for Python)
-   objects: `{ name: 'Homer', surname: 'Simpsons', profession: 'Engineer' }`
-   [JS only] fat arrow functions that take no input parameter and have a direct return

**_Note_**: circlualr objects are **not** supported.

#### Expressions [JS/TS only]

In addition to these simple values, you can enter expressions.
Expressions can include:

-   Instantation of objects: `new MyClass()` 
-   Built-in objects and their attributes and methods (for exampple)
-   Global values and their attributes and methods
-   All global scope identifiers declared in the test file or source file, and their attributes and methods
-   Nested expressions that include all the above

For example, you can write this kind of value in a cell:

```javascript
{
    "name": "Bill Smith",
    "hobbies": ["football", "basketball", "music", "food"],
    "bankAccount": Math.PI,
    "dateOfBirth": new Date("31/02/1990"),
    "employed": true,
    "married": undefined,
    "doSomething: () => 42
}
```

If you want to use identifiers that are imported from other files, add the import to the test file. You will be able to use the identifier through the name it is imported with.

## Assertions

Assertion columns can be of different types:

* **Standard assertion columns**: same format and limitations as the values listed in the `Inputs` section.  
* **Spy assertions**: an array that can contain any values listed above
* **Custom validation columns**: boolean [JS/TS only] 
* **"to throw" columns**: boolean [JS/TS only]
* **"to throw with message" columns**: strings [JS/TS only]
* **"is truthy" columns**: boolean [JS/TS only]


## The column *"instance"*

When testing methods, the first column in the Ponicode interface is the `instance` column. It refers to the instance we want to apply our method to for the current test case. This is a dropdown field, where the available choices are the different class instances declared in the `Before Each` section.
Please note that objects instanciated with a *static* constructor will not appear in the drop down; please always construct your instance using the keyword `new`.


<div align="right">
    <a href="/docs/vscode_extension/gui_test/classMethods" >
        > Testing class methods
    </a>
</div>