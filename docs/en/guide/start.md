# Get Started

`code-inspector-plugin` supports use in projects with `webpack` or `vite` as bundler, and supports frameworks such as `vue2/vue3/react`. Please refer to the following access tutorial.

## installation

- Use npm：

```perl
npm install code-inspector-plugin -D
```

- Use yarn：

```perl
yarn add code-inspector-plugin -D
```

- Use pnpm：

```perl
pnpm add code-inspector-plugin -D
```

## Configuration

### 1. Config webpack/vite

Use in webpack：

```js
// webpack.config.js
const { CodeInspectorPlugin } = require('code-inspector-plugin');

module.exports = () => ({
  plugins: [
    CodeInspectorPlugin({
      bundler: 'webpack',
    }),
  ],
});
```

Use in vite：

```js
// vite.config.js
import { defineConfig } from 'vite';
import { CodeInspectorPlugin } from 'code-inspector-plugin';

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [
    CodeInspectorPlugin({
      bundler: 'vite',
    }),
  ],
});
```

### 2. Config vscode command line

::: tip Windows or other IDE can skip this step
This step only needs to be configured if your computer is a Mac and you use vscode as the IDE. If your computer is Windows or you use another IDE, you can skip this step.
:::

- Execution `command + shift + p`(mac) or `ctrl + shift + p`(windows) in vscode , search and click `Shell Command: Install 'code' command in PATH`:

  <img src="https://s3.bmp.ovh/imgs/2021/08/a99ec7b8e93f55fd.png" width="60%" />

- If the following window appears, it indicates successful configuration:

  <img src="https://s3.bmp.ovh/imgs/2021/08/c3d00a8efbb20feb.png" width="40%" />

## Usage

There are currently two ways to use the DOM source code localization function:

1. 【Recommend】Method1: When holding down the combination key on the page and move the mouse over the page, a blue semi transparent mask layer will appear on the DOM, displaying relevant information. Clicking the mask will automatically open the IDE and position the cursor to the corresponding code position of the DOM. (The default combination key for Mac system is `Option + Shift` and for Windows is `Alt + Shift`, and the browser console will output relevant combination key prompts.) DCCCCCCCXFF
   ![image](https://github.com/zh-lx/code-inspector/assets/73059627/a6c72278-d312-45b2-ab76-076a9837439e)
2. Method2：When `showSwitch: true` is configured in the plugin parameters, a Code Inspector switch button will be displayed on the page, click to switch the inspector mode on/off. After the inspector mode is turned on, the function is the same as holding down the combination key in Method1. When the color of the switch is color, it indicates that the code inspector mode is on <img src="https://github.com/zh-lx/code-inspector/assets/73059627/842c3e88-dca7-4743-854c-d61093d3d34f" width="20" style="display: inline-block;" />; and when the switch color is monochrome, it means that code inspector mode is off <img src="https://user-images.githubusercontent.com/73059627/230129864-e2813188-8d49-4a8e-a6bc-dda19c79b491.png" width="20" style="display: inline-block;" />。

![code-inspector](https://user-images.githubusercontent.com/73059627/227070438-6e40e112-6f1d-4f67-9f26-53986bff77c3.gif)