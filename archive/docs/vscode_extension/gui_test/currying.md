# Curried functions

We call curried functions those function that take (at least) one argument, and return another function that in turns takes another argument.

Here is an example of a curried function:

```javascript
function sum(a) {
  return function (b) {
    return a + b;
  };
}
```

#### Testing curried functions with Ponicode

Curried input parameters do not appear by default when opening the Ponicode interface. 
For instance, when opening the Ponicode GUI on the function `sum`, a single input parameter column will be present, corresponding to the first parameter `a`.

<p align="center">
    <img src="vscode_extension/gui_test/images/curry_1.png" alt="input-column-selector" width="700"/>
</p>

In order to add a column for one (or multiple) curried parameters, open the **input column selector** by clicking on the cog icon [⚙] to the right of the *inputs* title.

<p align="center">
    <img src="vscode_extension/gui_test/images/curry_column_selector.png" alt="input-column-selector" width="500"/>
</p>

The column for the new curried parameter will appear in green (different from blue, used for standard parameters). 

<p align="center">
    <img src="vscode_extension/gui_test/images/curry_2.png" alt="input-column-selector" width="700"/>
</p>

The generated unit test will look something like this: 

```javascript
let result = sum(2)(10)
expect(result).toBe(12)
```

You can add more than one curried parameters, but all of them will be considered as arguments to the returned function. For example, two curried parameter might result in this type of function call: 

```javascript
sum(2)(8, 13)
```

#### AI Suggestions

For the moment, Ponicode only suggest meaningful input values for the arguments of the "parent" function. Value suggestions for the curried arguments are always `undefined`, but you can manually modify them to fit your needs.

<p align="center">
    <img src="vscode_extension/gui_test/images/curry_suggestions.png" alt="input-column-selector" width="650"/>
</p>

#### Limitations

Today, Ponicode only supports one level of arument currying.

This means that Ponicode allows testing a function that is called in the following way:
```javascript
sum(100)(15)
```
But it does *not* allow testing a function that is called in the following way:
```javascript
sum(100)(15)(28)
```

<div align="right">
    <a href="#/vscode_extension/gui_test/modifyingTestFile.md" >
        > Modifying the test file
    </a>
</div>
