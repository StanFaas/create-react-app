# CRA Multiple endpoints

A modified react-scripts fork which allows you to setup custom endpoints for your Create React App projects.

## Motivation

React looks for your index.html and index.js files to build/start your project. I've changed this so that you can have multiple endpoints in one CRA project.

A simple use case would be to have a normal `/` endpoint and a `/admin` one, with different builds too.

## Installation

First you should delete the current react-scripts module  
`yarn remove react-scripts`

Then you install mine:  
`yarn add @stanfaas/react-scripts`

**Concerned?**  
I can imagine you being concerned about react-scripts not being updated now. But don't you worry. This repo is using [Pull](https://github.com/wei/pull) to keep it synced with the real one.

## Usage

I'll show you how to create multiple endpoints according to the following example:
Imagine having an app that needs different endpoints for the users and one for the admin.

**Step 1: Prepare the js files**  
Instead of only having a `index.js` file in your `src/` folder, you also create an `admin.js` file.  
Make sure the `index` will load all the things you need for the user part of your app, and do the same for `admin`.

**Step 2: Prepare the html files**  
In your public folder, you find a `index.html`, duplicate that and change the name to `admin.html`. Again, edit that file to your needs.

**Step 3: Change your package.json scripts**  
Now you have everything setup, you can change your package.json scripts to make sure you can build your endpoints.

```json
"build": "react-scripts build"
"build-admin": "ENTRY=admin react-scripts build"
```

That's it! I hope this is as useful to you as it is to me.

---

---

## react-scripts

This package includes scripts and configuration used by [Create React App](https://github.com/facebook/create-react-app).<br>
Please refer to its documentation:

- [Getting Started](https://facebook.github.io/create-react-app/docs/getting-started) – How to create a new app.
- [User Guide](https://facebook.github.io/create-react-app/) – How to develop apps bootstrapped with Create React App.
