# Vue Flow ๐

[![Vue flow](vue-flow.gif)](https://vueflow.dev/)
![top-language](https://img.shields.io/github/languages/top/bcakmakoglu/vue-flow)
![vulnerabilities](https://img.shields.io/snyk/vulnerabilities/github/bcakmakoglu/vue-flow)
![GitHub code size in bytes](https://img.shields.io/github/languages/code-size/bcakmakoglu/vue-flow)
![GitHub last commit](https://img.shields.io/github/last-commit/bcakmakoglu/vue-flow)

__Vue Flow: A highly customizable Vue 3 Flowchart component.__

With Vue Flow, you can build your own, customized node-based applications like static diagrams or even more complex and
interactive editors!

You can find a detailed explanation of how to get started in the [documentation](https://vueflow.dev/guide/) or check
the [examples](https://vueflow.dev/examples/).

## Table of contents

* [โญ๏ธ Features](#-features)

* [๐  Setup](#-setup)

* [๐ฎ Quickstart](#-quickstart)
  
  + [๐ชด Vue 2](#-vue-2)

* [๐งช Development](#-development)
  
  + [๐ณ Dev Container](#-dev-container)

* [![discord logo](https://api.iconify.design/logos:discord-icon.svg) Discord](#-discord)

* [๐ Special Thanks](#-special-thanks)

* [โญ Stargazers](#-stargazers)

## โญ๏ธ Features

- ๐ถ __Easy setup__: Get started hassle-free - Built-in zoom- & pan features, element dragging, selection and much more

- ๐จ __Customizable__: Use your custom nodes, edges and connection lines and expand on Vue Flows' functionality

- ๐ __Fast__: Tracks changes reactively and only re-renders the appropriate elements

- ๐งฒ __Utils & Composition__: Comes with graph helper and state composable functions for advanced uses

- ๐ฆ __Additional Components__:

  - ๐ผ Background: With two built-in patterns and some configuration options like height, width or color.

  - ๐งญ Minimap: Shows current nodes in a small map shape in the bottom right corner

  - ๐น Controls: Control zoom behavior from a panel on the bottom left

  - ๐ค And (many) more to come...

- ๐ฆพ __Reliable__: Fully written in TypeScript

## ๐  Setup

```bash
$ npm i @vue-flow/core

# or
$ yarn add @vue-flow/core
```

## ๐ฎ Quickstart

A flow consists of __nodes__ and __edges__ (or just nodes). 
Together they are called __elements__.

__Each element needs a unique id.__ 

A node also needs an XY position.
An edge needs a source (node id) and a target (node id). 

A basic setup looks like this:

```vue
<!-- Flowchart.vue -->
<script setup>
import { VueFlow } from '@vue-flow/core'

const elements = ref([
  {
    id: '1',
    label: 'node 1',
    position: { x: 100, y: 100 },
  },
  {
    id: '2',
    label: 'node 2',
    position: { x: 100, y: 200 },
  },
  {
    id: 'e1-2',
    target: '2',
    source: '1',
  },
])
</script>

<template>
  <VueFlow v-model="elements"></VueFlow>
</template>
```


โ ๏ธ __Make sure to import the necessary styles:__

```css
/* import the required styles */
@import "@vue-flow/core/dist/style.css";

/* import the default theme (optional) */
@import "@vue-flow/core/dist/theme-default.css";
```

### ๐ชด Vue 2

**_This library doesn't work with Vue 2._**

Vue Flow uses features that are exclusive to Vue 3, therefore
there is no support for Vue 2, nor will there be any support in the future, sorry.

## ๐งช Development

### Prerequisites

- [Node.js v14+](https://nodejs.org/)
- [PnPm](https://pnpm.io/)


```bash
# skip if you already have pnpm installed
$ npm i -g pnpm

# start examples
$ pnpm dev

# build all packages
$ pnpm build
```

### ๐ณ Dev Container

To start using development containers, install the `Docker` extension
for VSCode.
After installing the extension, open the connection menu either
on the bottom left or open it via the commands tab.
Select the `Open Folder in Container` option to mount the project.

The development container will spin up all packages example apps and forward
the ports to your machine.

## ![discord logo](https://api.iconify.design/logos:discord-icon.svg) Discord

[Join the Vue Flow Discord server!](https://discord.gg/z4FMpfTugW)

Here you can ask questions to the community, propose ideas for new features
or share your work that you have built with Vue Flow.

## ๐ Special Thanks

This project is built with

- [React Flow](https://reactflow.dev/)
  - Vue flow is heavily based on [webkids'](https://webkid.io/) [react flow](https://reactflow.dev/). I wholeheartedly thank
  them for their amazing work! Without them Vue Flow would not exist.
  Please consider [donating](https://github.com/sponsors/wbkd) to them.

- [D3.js](https://d3js.org/)
  - D3 makes all the zoom and pan actions in Vue Flow possible.

- [VueUse](https://vueuse.org/)
  - VueUse is a collection of essential vue composition utilities

## โญ Stargazers

Many thanks to the kind individuals who leave a star.
Your support is much appreciated!

[![Stargazers for @vue-flow/core](https://reporoster.com/stars/bcakmakoglu/vue-flow)](https://github.com/bcakmakoglu/vue-flow/stargazers)
