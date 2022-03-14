---
layout: default
title: Using Ponicode CLI
nav_order: 2
parent: Ponicode CLI
has_children: false
has_toc: false
toc: true
---

# Using Ponicode CLI

> **Warning**:
> Ponicode CLI is available for Typescript, Javascript and Python. 
> However, some of the options listed below are only available for TypeScript

#### Write a test file for a given source file

To use Ponicode CLI on one specific source file, you can simply use:

```
ponicode test /path/to/your/source_file
```

#### Write a test file for a specific function in a source file (`--func`)

If you want to add tests for a specific function, Ponicode CLI does it for you.
To do so, simply run:

```
ponicode test --func mySuperFunction /path/to/source_file
```

#### Write a test file for multiples files

You really want to go to the step further and add tests for _multiples_ files?

To do so, you have multiple possibilities.

**Given files**

If you want to add test files for specific source files, you can specify which one only by adding them as arguments to the command, such as:

```
ponicode test src/utils.ts src/superFile.ts
```

**Glob pattern (`**/\*`)**

Maybe you're too lazy to write _every_ single files in the command line, and want to use a glob pattern to fetch them all?

With Ponicode CLI, you can do it:

```
ponicode test src/**/*.ts
```

#### Write a JSON report (`--json`)

You may want data about your code and the tests generated?

You can generate it along the generated tests, and have it in a json file.

```
ponicode test src/utils.ts --json
```

By default, the JSON will be written in the current directory you're executing the command.
If you want to have it in a different location, simply specify it next to the `--json` such as:

```
poniode test src/utils.ts --json report/poni-report.json
```

> Note: You have to add the `--json` option to **_the end_** of the command.


#### Dry run (`--dry-run`)

If you want to test the capabilities of Ponicode CLI, but don't want it to generate test files, you can run `ponicode` with the option `--dry-run` to do so:

```
ponicode test --dry-run src/api/**.js
```


#### Use Rewire (`--rewire / -r`) *[JS/TS only]*

By default, Ponicode does not generate unit tests for functions that are ***not exported***. 
If you would like Ponicode to use the dependency [`rewire`](https://www.npmjs.com/package/rewire) to unit test unexported functions, you can use the flag `-r` when launching `ponicode test`:

```
ponicode test src/myFolder/myFile.ts --rewire
```

When using this flag, please keep in mind that:
- using `rewire` might require additional configuration on your side for Jest to be able to run your tests.
- `Jest` excludes rewired tests from its coverage calculations 


#### Dashboard (`--dashboard / -d`) *[TS only]*

If you have subscribed to the [Premium plan](https://app.ponicode.com/account/billing/plan), you can have access to the advanced TurboCov dashboard for your TypeScript project. To do so, add the option `--dashboard` (or `-d`):

```
ponicode test --dashboard ./src
```

As well as generating your test files, this command will **run** them using Jest, and upload coverage information to the TurboCov Dashboard.

You can find more information on the [dashboard page](platform/dashboard.md) of the Docs.


#### (Re)run test *[TS only]*

If your tests failed to run, or your coverage failed to be updated to your TurboCov dashboard, you can re-launch the coverage calculation again by using the following command at your project root.

```
ponicode cov run
```
