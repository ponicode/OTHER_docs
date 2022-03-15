# Mocking (stubs and spies)

You can use Ponicode to mock return values of callables by following these steps:

1 - Open the Unit Test interface for the function or method you want to test by right-clicking anywhere in the function's body and selecting `Ponicode: Unit Test`, or by simply using the `"ctrl+T"` shortcut.

<p align="center">
    <img src="vscode_extension/gui_test/images/ponicode_unit_test.png" width="600"/>
</p>

2 - When the Ponicode interface opens up, go back to the body of the function in your editor and click right on the function or method you'd like to mock, and select `Ponicode: Mock`

<p align="center">
    <img src="vscode_extension/gui_test/images/mocking_selection.png" width="600"/>
</p>

3 - After performing step 2, notice that 2 new columns appear in the Ponicode Interface: one in the section `mocks`, and one in the section `assertions`. The former one is the stub, the second one is the spy assertion `calledWith`.

<p align="center">
    <img src="vscode_extension/gui_test/images/mocking_column.png" width="600"/>
</p>

4 - Enter your desired value in the column `mock` to stub your function with this value. 

Similarly, enter in the the column `calledWithh` an array with the values that the mocked function should have been called with. For instance, if the function should have been called with the values `car` and `6`, enter `["car", 6]`. If desired, you can leave this cell empty, or remove it through the assertion column selector (use the little gear icon on the righ of the title `assertions`) 

<p align="center">
    <img src="vscode_extension/gui_test/images/mocking_value.png" width="600"/>
</p>

## Mocking user-defined functions

Ponicode can mock functions that are defined in the same projects.

**Python**

Most user-defiend functions can be mocked.

**JavaScript / TypeScript**

Jest imposes that in order to be mocked, functions must be exported.

* We do not support mocking non-exported functions
* We do not support mocking conditionally exported functions
* We do not support mocking direct exports (for example: `module.exports = function ()`)

#### Examples

**✅ Works**

```
const db = require('./db')
function foo () {
    db.query()
}
module.exports = { foo }
```

**❌ Fails**

```
const { query } = require('./db')
function foo () {
    query()
}
module.exports = { foo }
```

**❌ Fails with Jest**

```
const query = require('./db').query
function foo () {
    query()
}
module.exports = { foo }
```

*foo* and *db* will not live in the same context, because foo is not exported and **Jest** uses another **JavaScript** engine.

**Workaround**: Export _foo_

What will happen?

1. **Jest** is launched
2. _foo_ is imported via __rewire_, and will live in **Node** context
3. _db_ is imported by _foo_, and will live in **Node** context.
4. From the test file, _db_ is imported via **Jest**’s _require_, and will live in **Jest**’s context.
5. **Jest** will mock _db_ in **Jest**’s context.
6. _foo_ will call _db.query_ in **Node**’s context, the mock will not work. This is a Ponicode-specific limitation.

## Mocking libraries

**Javascript**

Ponicode can mock functions that are defined in node modules. Ponicode can also mock functions from **Node** built-in modules (_fs_, _util_, etc.).

***Exclusions***

* The tested function must be exported (this is a Ponicode-specific limitation).
* We do not support mocking direct exports.

#### Examples

**✅ Works**

```
const axios = require('axios')
function foo () {
    axios.get()
}    
module.exports = { foo }
```

**❌ Fails**

```
const axios = require('axios')
function foo () {
    axios.get()
}
```

_foo_ is not exported. Ponicode-specific limitation.

**❌ Fails**

```
const { get } = require('axios')
function foo () {
    get()
}    
module.exports = { foo }
```

The reference to _axios.get_ was copied before the mock was set up.

**❌ Fails**

```
const axios = require('axios')
function foo () {
    axios()
}
module.exports = { foo }
```

We cannot mock _axios_ itself. This is a Ponicode-specific limitation.

**❌ Fails**

```
const pkg = require('package')
function foo () {
    pkg[0]()
}
module.exports = { foo }
```

We cannot mock _pkg[0]_. Only simply exported members are supported. This is a Ponicode-specific limitation.

<!-- ## Mocking native functions

Ponicode can mock native functions that do not need to be imported. Here are some examples.

### Javascript

**Example**: _Math.random_

### Node

**Example**: _Buffer.from_

### Browser

**Example**: _fetch_ -->

## Mocking variables [JS/TS only]

Ponicode can mock global variables that are defined in the same file as the tested function.

- The variable must be defined in global scope.
- If you want to stub the variable, the variable must not be a constant.


> **<span style="color:green">TypeScript And JavaScript Recommendations<span>**
>
> We recommend to always **export** functions in your project that use mocks or will be mocked, in order to avoid special edge cases proper to JavaScript & TypeScript.
>

<div align="right">
    <a href="#/vscode_extension/gui_test/runningTests.md" >
        > Running your tests
    </a>
</div>