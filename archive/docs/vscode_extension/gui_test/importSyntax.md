# What syntax of import do we support ?

Imports can be written in various different ways.
* In your **source files**, all import syntaxes work well with Ponicode.
* In the **test files**, Ponicode is able to understand a wide range of common import syntaxes, but not all of them.

Here is an overview of Ponicode's supported import syntaxes in the test file.
## Python
#### Supported

Ponicode supports the two most common syntaxes:

```python
import math
from flask import Flask
```
The imported module can be:
* a standard library
* a third party module
* a local application module

#### Not supported yet

Ponicode **doesn't** yet support the following syntax:
* globs
```python
from module import *
```
* relative import
```pyton
from ..some_package import some_function
```
* import function
```python
__import__(module)
```

## Javascript / Typescript

#### Supported

Ponicode handles the following import systems:
* basic
```javascript
import cp from "child_process"
```
* relative
```javascript
import cp from "./my_child_process"
```
* glob
```javascript
import * as cp from "my_child_process"
```
* require
```javascript
const cp = require("child_process")
```

You can use `jest.config` file to specifies how to import files. More information, on [Jest documentation](https://jestjs.io/docs/configuration)


#### Not supported yet

Ponicode **doesn't** yet supported the following syntax:
* es6 syntax
```javascript
import { cp } from  "child_process"
``` 

<div align="right">
    <a href="#/vscode_extension/gui_test/feedback.md" >
        > Sending us feedback
    </a>
</div>
