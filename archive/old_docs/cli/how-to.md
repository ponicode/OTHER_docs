# How to use Ponicode CLI

> Warning :
> Ponicode CLI is compatible with Typescript and Javascript.

## Write a test file for a given source file

To use Ponicode CLI on one specific source file, you can simply use :
```
ponicode test /path/to/your/source_file
```

## Write a test file for a specific function in a source file (`--func`)

If you want to add tests for a specific function, Ponicode CLI does it for you.
To do so, simply use : 
```
ponicode test --func mySuperFunction /path/to/source_file
```

## Write a test file for multiples files

You really want to go to the step further and add tests for _multiples_ files ?

To do so, you have multiple possibilities.

### Given files

If you want to add test files for specific source files, you can specify which one only by adding them as arguments to the command, such as :
```
ponicode test src/utils.ts src/superFile.ts
```

### Glob pattern (`**/*`)

Maybe you're too lazy to write _every_ single files in the command line, and want to use a glob pattern to fetch them all ? 

With Ponicode CLI, you can do it :
```
ponicode test src/**/*.ts
```

## Write a JSON report (`--json`)

You may want data about your code and the tests generated ?

You can generate it along the generated tests, and have it in a json file.
```
ponicode test src/utils.ts --json
```

By default, the JSON will be written in the current directory you're executing the command.
If you want to have it in a different location, simply specify it next to the `--json` such as :
```
poniode test src/utils.ts --json report/poni-report.json
```

> Note : You have to add the `--json` option to **_the end_** of the command.

## Dry run (`--dry-run`)

Maybe you want to test the capabilities of Ponicode CLI and doesn't want it to write test files for you ? Fine !
You can execute our tool with `--dry-run` to do so : 
```
ponicode test --dry-run src/api/**.js 
```

