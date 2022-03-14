---
layout: default
title: Set up
nav_order: 1
parent: Ponicode IntelliJ Plugin
has_children: false
has_toc: false
---

#### Installation

You can install the Ponicode IntelliJ extension directly from the [**JetBrains marketplace**][extension].

<p align="center">
    <img src="/docs/intellij_plugin/images/ponicode-mktplace.png" alt="Ponicode on the JetBrains Marketplace" width="700"/>
</p>

#### Login

> **<span style="color:green">NOTE<span>**
>
> Note that the intellij plugin uses the same authentification than [Ponicode CLI](/docs/cli/index/), so if you are already logged in on Ponicode CLI, you can skip this step

Once you have installed the extension you won't be able to use the ponicode features as long as you haven't logged in to our service. But don't worry it's pretty easy. Normally in the few seconds that follows the installation you should see a balloon notification telling you you are not logged, you just have to click the **Log In** button inside the popup to be redirected to our authentification platform.

<p align="center">
    <img src="/docs/intellij_plugin/images/login-popup.png" alt="Ponicode on the JetBrains Marketplace" width="400"/>
</p>

Upon clicking the button you will be redirected to your web browser where you can log in using either github or gitlab or bitbucket.

<p align="center">
    <img src="/docs/intellij_plugin/images/login-options.png" alt="Log in to Ponicode" width="700"/>
</p>

After that you can go back to your IDE and [start using ponicode](/docs/intellij_plugin/use).

Note that as long as you have not logged, you will see the ponies but you get a balloon popup everytime you try to generate your tests.

[extension]: https://plugins.jetbrains.com/plugin/17980-ponicode

<div align="right">
    <a href="/docs/intellij_plugin/use" >
        > How to use Intellij Plugin
    </a>
</div>
