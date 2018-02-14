---
title: Step 1. Get set up
subtitle: "Build an app with App Toolbox"
---

<!-- toc -->

The [Polymer App Toolbox][toolbox] is a collection of components, tools and
templates for building Progressive Web Apps with Polymer.

Follow the instructions below to install, build, and deploy a project using an
App Toolbox template in less than 15 minutes.

## Install Polymer CLI

Polymer CLI is an all-in-one command line tool for Polymer projects. In this tutorial you use
Polymer CLI to initialize, serve, and build your project. You can also use it for linting and
testing, but this tutorial won't cover those topics.

Polymer CLI requires Node.js, npm, Git and Bower. For full installation instructions, see [the
Polymer CLI documentation](/{{{polymer_version_dir}}}/docs/tools/polymer-cli).

To install Polymer CLI:

    npm install -g polymer-cli

## Initialize your project from a template

1. Create a new project folder to start from.

        mkdir my-app
        cd my-app

1. Initialize your project with an app template.

        polymer init

    Press the down arrow until `polymer-3-starter-kit` is highlighted and press the enter / return
    key to select.


## Serve your project

The App Toolbox templates do not require any build steps to get started
developing.  You can serve the application using the Polymer CLI, and
file changes you make will be immediately visible by refreshing
your browser.

To serve your project:

    polymer serve --open --npm

Note: The `--npm` flag tells the Polymer development server to find the Polymer library and any components you add to your project in `node_modules`.

## Project structure

The diagram below is a brief summary of the files and directories within
the project.

```text

```

## Next steps

Your app is now up and running locally. Next, learn how to add
a page to your app.

<a class="blue-button"
    href="create-a-page">Next step: Create a page</a>

[toolbox]: /3.0/toolbox/
[md]: http://www.google.com/design/spec/material-design/introduction.html
