# Test Runner Settings

## Javascript
The test runner is configured via 2 means: throught VSCode and with config files.
#### VSCode settings

Open your VSCode settings `File > Preferences > Settings` or <kbd>CTRL</kbd> + <kbd>,</kbd> (Windows and Linux) or <kbd>CMD</kbd> + <kbd>,</kbd> (Macos). Then search for "Ponicode".

<p align="center">
    <img src="vscode_extension/gui_test/configuration/images/ponicode_settings.png"  width="700"/>
</p>

⚠️ Please make sure to select __workspace__ tab and not __user__ one.

Inside you can configure how the test runner handles typescript files throught the vscode settings.

<p align="center">
    <img src="vscode_extension/gui_test/configuration/images/runner_1.png"  width="700"/>
</p>

There is 3 available values:
* __Use .js file if exists and up to date__: The test runner will try to run the compiled js file. If it is missing or outdated, the test runner will use the source .ts file.
* __Only use .ts file__: The test runner will only run your .ts file.
* __Only use .js file__: The test runner will only run your .js file.

#### Config files 

The test runners reads configuration from several config files.

**1 - The Jest config file**

The test runners will search for your jest config starting from the configured test location, walking the file system tree upward.
It will use the first jest.config.js, jest.config.ts or package.json found.

The test runner will use the [moduleNameMapper](https://jestjs.io/docs/configuration#modulenamemapper-objectstring-string--arraystring) specified in this config to run your tests.

**2 - The Babel config file**

The test runner will also search for babel.config.json in a similar fashion. If the babel config is found, the test runner will use babel with the provided configuration to run load your files.

You can find more information about babel [here](https://babeljs.io/docs/en/config-files)

## Python

The Ponicode Python test runner uses the *Python interpreter* configured in the settings of the [Official Python Extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python). Ensure that you have configured your Python runner. The minimum required version is 3.6.

<div align="right">
    <a href="#/vscode_extension/gui_test/configuration/testLocation.md" >
        > Test Location 
    </a>
</div>