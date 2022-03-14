---
layout: default
title: Running your tests
parent: Ponicode Unit Test (GUI)
nav_order: 8
grand_parent: The Ponicode VSCode extension
has_children: false
has_toc: false
---

# Running your test

You can always use your test runner of choice (Jest, Pytest, etc) to run your tests, but POnicode also allws you to run your tests directly in the Ponicode interface. 

There are two modes for running your tests: manual mode or watch mode.

**Manual mode**

You can run each test individually by clicking on the <i class="fas fa-play" style="color:green"></i>`Play` button. 

If the test passed, you will see a green check right of your test row.

<p align="center">
    <img src="/docs/vscode_extension/gui_test/images/test_case_running_1.png"  width="500"/>
</p>

If the test fails, you will see a red cross (<i class="fas fa-times" style="color:red"></i>) icon. You can then make the test pass by clicking on the bolt icon (<i class="fas fa-bolt" style="color:orange"></i>) to correct it.

<p align="center">
    <img src="/docs/vscode_extension/gui_test/images/test_case_running_2.png"  width="500"/>
</p>


**Watch mode**

Watch mode can automaticaly run your tests when needed. You can enable it using the toggle in to top right corner.

<p align="center">
    <img src="/docs/vscode_extension/gui_test/images/test_case_running_3.png"  width="500"/>
</p>

#### Troubleshooting

**"Failed to import some files"**

<p align="center">
    <img src="/docs/vscode_extension/gui_test/images/test_case_running_4.png"  width="300"/>
</p>


This probably means that you have a typo in your imports or that the module you are importing is not installed.

**"Failed to evaluate beforeEach"

<p align="center">
    <img src="/docs/vscode_extension/gui_test/images/before_each_error.png" alt="before_each_error" width="500"/>
</p>

This usually means that there is a syntax error in the before each.
Make sure that all your identifier are imported in the test file and that your classes are instatiated correctly.

#### Running your test in the terminal (JS)

Ponicode write your test in jest format. You can run the tests in your terminal with jest.
Jest is installed with this command:
`npm install --save-dev jest`
or
`yarn add --dev jest`

Then add this configuration to your package.json:
```
{
	"scripts": {
		"test": "test"
	}
}
```

You can run all your tests with `npm run test` or `yarn run test`

You can run tests files individually with `jest FILE_NAME.test.js`

For advanced use of Jest, refer to the [official docs](https://jestjs.io/docs/getting-started).


<div align="right">
    <a href="/docs/vscode_extension/gui_test/currying" >
        > Currying
    </a>
</div>