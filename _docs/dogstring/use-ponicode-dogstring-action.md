---
layout: default
title: Github Action
nav_order: 2
parent: Ponicode Dogstring
has_children: false
has_toc: false
---

# Ponicode DogString Action

#### Why a Github Action?

Ponicode's Dogstring Github Action allows to integrate AI-powered automatic docstring generation into your CI.

Effectively, this means that you will never again produce undocumented code: the Ponicode Github action allows you to generate Dogstring either for your whole project in bulk, or only on the lates portion of code that you have modified (the *diff* of your commit). 

The Github Action runs on your code and generates a PR to add a docstring to all functions which do not already have one. You are then free to review the PR, make the comments you need and merge it into your branch.
#### Add your Ponicode Token to your Github secrets

1. Go to [https://app.ponicode.com/actions](https://app.ponicode.com/actions)

2. Sign in with your **GitHub** or **GitLab** account
<p align="center">
    <img src="/docs/dogstring/images/use_dogstring_1.png" alt="sign_in" width="600"/>
</p>

3. Click on `authorize Ponicode`
<p align="center">
    <img src="/docs/dogstring/images/use_dogstring_2.png" alt="authorize" width="600"/>
</p>

4. Copy you tokens
<p align="center">
    <img src="/docs/dogstring/images/use_dogstring_3.png" alt="token" width="650"/>
</p>

5. Go to your repository where you want to use the action.

6. Go to settings.
<p align="center">
    <img src="/docs/dogstring/images/use_dogstring_7.png" alt="settings" width="650"/>
</p>


7. Click on `Secrets`
<p align="center">
    <img src="/docs/dogstring/images/use_dogstring_4.png" alt="settings" width="650"/>
</p>

8. Click on `New repository secret`
<p align="center">
    <img src="/docs/dogstring/images/use_dogstring_5.png" alt="secrets" width="650"/>
</p>

9. Name it *`"PONICODE_TOKEN"`* and paste your token in the **Value**.
<p align="center">
    <img src="/docs/dogstring/images/use_dogstring_6.png" alt="secrets" width="650"/>
</p>


10. Click on `Add Secret`
Your Ponicode Token is now added to your repository's secrets!

#### Add the YAML file to your repository
You will need to create a yaml file, which will trigger the action, at the following location: `.github/worflows/ponicode_action.yml`
One way of doing it is directly on **GitHub**.

1. Click on `Add File` and create new file
<p align="center">
    <img src="/docs/dogstring/images/use_dogstring_8.png" alt="add_file" width="650"/>
</p>

2. Name it `.github/worflows/ponicode_action.yml`
<p align="center">
    <img src="/docs/dogstring/images/use_dogstring_9.png" alt="github_editor" width="650"/>
</p>

3. Paste one of our example in the Edit new file section
4. Click on commit new file
5. You can now use our Github action to generate docstrings for all your Python files!

**YAML file example**
<p align="center">
    <img src="/docs/dogstring/images/use_dogstring_10.png" alt="yaml_file" width="650"/>
</p>

In the first box you control what will trigger the action.

In the second box you choose the parameters of the action.

- **repo_path:** The relative path in your repository to the files you want Ponicode to test. By default, Ponicode tests your whole repository.
- **auth_token:** String. No default value. You need to add your authentication ponicode token at [https://app.ponicode.com/actions](https://app.ponicode.com/actions)
- **all_repo:** Boolean. By default, the value is False. Choose if you want to write docstrings only on the files you just committed (False) or on all your repository (True)
- **enable_template:** Boolean. By default, the value is true. Choose if you want the docstrings to include the parameters and their types.


Once the docstrings are written, we use the create pull request action to see the results in the branch of your choice. If you want more details go to [https://github.com/peter-evans/create-pull-request](https://github.com/peter-evans/create-pull-request)

You can see the Ponicode Dogstring action and different use cases here: [https://github.com/ponicode/dogstring-action](https://github.com/ponicode/dogstring-action)
