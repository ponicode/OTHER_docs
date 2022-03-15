# The Unit Tests Section

The Unit Tests section in the Ponicode interface is your way to directly interact with your test file. When you open the interface, Ponicode looks for your test file (more information about test file location [here](vscode_extension/gui_test/configuration/testLocation.md)). In the file exists, this section will be populated with the test cases found in said file. If not, Ponicode creates the file for you as soon as you add your first test case.

When you add or remove a test case in this section, your test file is updated in real time and vice versa.

## Adding test cases

You can add a new test case manually by clicking on the blue icon at the bottom of the unit tests section.

<p align="center">
    <img src="vscode_extension/gui_test/images/running_test_case.png" alt="Test suggestions" width="600"/>
</p>

You can also add test cases chosen from the selection of suggestions proposed to you by the Ponicode AI. Simply click on the <i class="fas fa-plus" style="color:green"></i>`Plus` button on the right hand side of each test case row.

<p align="center">
    <img src="vscode_extension/gui_test/images/suggestions_2.png" alt="Adding test suggestions" width="600"/>
</p>

## Updating Test Cases
All input and outputs values are editable cells. You can complete or overwrite them whenever you want. See the dedicated docs page for more information on [what can be entered in a cell](vscode_extension/gui_test/cell.md).

## Removing Test Cases

To remove a test case, simply click on the <i class="fas fa-trash-alt" style="color:gray"></i>`Bin` icon at the right side of the test case row.

<p align="center">
    <img src="vscode_extension/gui_test/images/suggestions_3.png" alt="Removing test suggestions" width="600"/>
</p>

## Running test cases

You might want to run your test cases to see wether they pass or not. Read the dedicated docs page [running tests](vscode_extension/gui_test/runningTests.md) for more information.

<div align="right">
    <a href="#/vscode_extension/gui_test/suggestions.md" >
        > Suggestions
    </a>
</div>