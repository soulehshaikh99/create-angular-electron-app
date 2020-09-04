<div align="center">
<img alt="Electron Angular Crossover Banner" src="https://raw.githubusercontent.com/soulehshaikh99/assets/master/create-electron-framework-app/readme/svg/Electron_Angular.svg" width="580" />
</div>
<br />
The boilerplate code to get started creating Cross-platform Desktop Apps with Electron and Angular as front-end technology.
<br />
<br />
<div align="center">

[![forthebadge](http://forthebadge.com/images/badges/built-by-developers.svg)](http://forthebadge.com)&nbsp;&nbsp;&nbsp;&nbsp;[![forthebadge](http://forthebadge.com/images/badges/makes-people-smile.svg)](http://forthebadge.com)<br />

[![forthebadge](http://forthebadge.com/images/badges/uses-html.svg)](http://forthebadge.com)&nbsp;&nbsp;&nbsp;[![forthebadge](http://forthebadge.com/images/badges/uses-css.svg)](http://forthebadge.com)&nbsp;&nbsp;&nbsp;[![forthebadge](http://forthebadge.com/images/badges/uses-js.svg)](http://forthebadge.com)

[![js-standard-style](https://cdn.rawgit.com/feross/standard/master/badge.svg)](https://github.com/feross/standard)

</div>

## ✒️ Overview

The aim of this project is to provide Web Developers using `angular` the power to create cross-platform desktop apps using `electron`.

#### 🧐 What packages does the project use?

**`electron`** enables you to create desktop applications with pure JavaScript by providing a runtime with rich native (operating system) APIs. You could see it as a variant of the Node.js runtime that is focused on desktop applications instead of web servers.

**`electron-builder`** is used as a complete solution to package and build a ready for distribution (supports Numerous target formats) Electron app with "auto update" support out of the box.

**`electron-serve`** is used for Static file serving for Electron apps.

**`angular`** is an application design framework and development platform for creating efficient and sophisticated single-page apps. Angular is written in TypeScript. It implements core and optional functionality as a set of TypeScript libraries that you import into your apps.

**`concurrently`** is used to run multiple commands concurrently.

**`wait-on`** is used as it can wait for sockets, and http(s) resources to become available.
<br />

## 🚀 Getting Started

**Note:** If you wish to use npm over yarn then modify `package.json` by replacing `yarn` with `npm` in `electron-dev` and `preelectron-pack` scripts.
But I strongly recommend using <em>yarn</em> as it is a better choice when compared to <em>npm</em>.

### 🤓 Use this boilerplate

```bash
# Clone the Project

# Use degit scaffolding tool
$ npx degit soulehshaikh99/create-angular-electron-app create-angular-electron-app
# or GitHub CLI Users
$ gh repo clone https://github.com/soulehshaikh99/create-angular-electron-app.git
# or Normal Git Users
$ git clone https://github.com/soulehshaikh99/create-angular-electron-app.git

# Switch location to the cloned directory
$ cd create-angular-electron-app

# Install dependencies
$ yarn # or npm install

# Run your app
$ yarn electron-dev # or npm run electron-dev

# Package Your App
$ yarn electron-pack # or npm run electron-pack
```

### 💫 Create this boilerplate from scratch (Manual Setup)

#### 1) Start by installing @angular/cli globally

```bash
$ yarn global add @angular/cli
# npm i -g @angular/cli
```

#### 2) Create a angular project using @angular/cli

```bash
$ ng new create-angular-electron-app
```

#### 3) Switch to project directory

```bash
$ cd create-angular-electron-app
```

#### 4) Move all dependencies to devDependencies using IDE / Text Editor

```bash
"dependencies": {},
"devDependencies": {
  "@angular-devkit/build-angular": "~0.1000.8",
  "@angular/animations": "~10.0.14",
  "@angular/cli": "~10.0.8",
  "@angular/common": "~10.0.14",
  "@angular/compiler-cli": "~10.0.14",
  "@angular/compiler": "~10.0.14",
  "@angular/core": "~10.0.14",
  "@angular/forms": "~10.0.14",
  "@angular/platform-browser-dynamic": "~10.0.14",
  "@angular/platform-browser": "~10.0.14",
  "@angular/router": "~10.0.14",
  "@types/jasmine": "~3.5.0",
  "@types/jasminewd2": "~2.0.3",
  "@types/node": "^12.11.1",
  "codelyzer": "^6.0.0",
  "jasmine-core": "~3.5.0",
  "jasmine-spec-reporter": "~5.0.0",
  "karma-chrome-launcher": "~3.1.0",
  "karma-coverage-istanbul-reporter": "~3.0.2",
  "karma-jasmine-html-reporter": "^1.5.0",
  "karma-jasmine": "~3.3.0",
  "karma": "~5.0.0",
  "protractor": "~7.0.0",
  "rxjs": "~6.5.5",
  "ts-node": "~8.3.0",
  "tslib": "^2.0.0",
  "tslint": "~6.1.0",
  "typescript": "~3.9.5",
  "zone.js": "~0.10.3"
}
```

#### 5) Install Development Dependencies

```bash
$ yarn add --dev electron electron-builder wait-on concurrently
# npm i -D electron electron-builder wait-on concurrently
```

#### 6) Install Production Dependency

```bash
$ yarn add electron-serve # or npm i electron-serve
```

#### 7) Your dependencies should look something like this

```json
"dependencies": {
  "electron-serve": "^1.0.0"
},
"devDependencies": {
  "@angular-devkit/build-angular": "~0.1000.8",
  "@angular/animations": "~10.0.14",
  "@angular/cli": "~10.0.8",
  "@angular/common": "~10.0.14",
  "@angular/compiler-cli": "~10.0.14",
  "@angular/compiler": "~10.0.14",
  "@angular/core": "~10.0.14",
  "@angular/forms": "~10.0.14",
  "@angular/platform-browser-dynamic": "~10.0.14",
  "@angular/platform-browser": "~10.0.14",
  "@angular/router": "~10.0.14",
  "@types/jasmine": "~3.5.0",
  "@types/jasminewd2": "~2.0.3",
  "@types/node": "^12.11.1",
  "codelyzer": "^6.0.0",
  "concurrently": "^5.3.0",
  "electron-builder": "^22.8.0",
  "electron": "^10.1.1",
  "jasmine-core": "~3.5.0",
  "jasmine-spec-reporter": "~5.0.0",
  "karma-chrome-launcher": "~3.1.0",
  "karma-coverage-istanbul-reporter": "~3.0.2",
  "karma-jasmine-html-reporter": "^1.5.0",
  "karma-jasmine": "~3.3.0",
  "karma": "~5.0.0",
  "protractor": "~7.0.0",
  "rxjs": "~6.5.5",
  "ts-node": "~8.3.0",
  "tslib": "^2.0.0",
  "tslint": "~6.1.0",
  "typescript": "~3.9.5",
  "wait-on": "^5.2.0",
  "zone.js": "~0.10.3"
}
```

#### 8) Download the app icon

[favicon.png](https://raw.githubusercontent.com/soulehshaikh99/assets/master/framework-icons/angular/favicon.png) and place it in the src/assets directory.

#### 9) Add `outputPath` configuration in `angular.json`

```bash
{
  "projects": {
    "create-angular-electron-app": {
      "architect": {
        "build": {
          "options": {
            "outputPath": "build"
          }
        }
      }
    }
  }
}
```

#### 10) Create main.js file (serves as entry point for Electron App's Main Process)

```bash
# Windows Users
$ fsutil file createnew main.js 0
# notepad main.js

# Linux and macOS Users
$ touch main.js
```

#### 11) Paste the below code in main.js file

```js
// Modules to control application life and create native browser window
const { app, BrowserWindow } = require("electron");
const path = require("path");
const serve = require("electron-serve");
const loadURL = serve({ directory: "build" });

// Keep a global reference of the window object, if you don't, the window will
// be closed automatically when the JavaScript object is garbage collected.
let mainWindow;

function isDev() {
  return !app.isPackaged;
}

function createWindow() {
  // Create the browser window.
  mainWindow = new BrowserWindow({
    width: 800,
    height: 600,
    webPreferences: {
      nodeIntegration: true,
    },
    // Use this in development mode.
    icon: isDev()
      ? path.join(process.cwd(), "src/assets/favicon.png")
      : path.join(__dirname, "build/assets/favicon.png"),
    // Use this in production mode.
    // icon: path.join(__dirname, 'build/assets/favicon.png'),
    show: false,
  });

  // This block of code is intended for development purpose only.
  // Delete this entire block of code when you are ready to package the application.
  if (isDev()) {
    mainWindow.loadURL("http://localhost:4200/");
  } else {
    loadURL(mainWindow);
  }

  // Uncomment the following line of code when app is ready to be packaged.
  // loadURL(mainWindow);

  // Open the DevTools and also disable Electron Security Warning.
  // process.env['ELECTRON_DISABLE_SECURITY_WARNINGS'] = true;
  // mainWindow.webContents.openDevTools();

  // Emitted when the window is closed.
  mainWindow.on("closed", function () {
    // Dereference the window object, usually you would store windows
    // in an array if your app supports multi windows, this is the time
    // when you should delete the corresponding element.
    mainWindow = null;
  });

  // Emitted when the window is ready to be shown
  // This helps in showing the window gracefully.
  mainWindow.once("ready-to-show", () => {
    mainWindow.show();
  });
}

// This method will be called when Electron has finished
// initialization and is ready to create browser windows.
// Some APIs can only be used after this event occurs.
app.on("ready", createWindow);

// Quit when all windows are closed.
app.on("window-all-closed", function () {
  // On macOS it is common for applications and their menu bar
  // to stay active until the user quits explicitly with Cmd + Q
  if (process.platform !== "darwin") app.quit();
});

app.on("activate", function () {
  // On macOS it's common to re-create a window in the app when the
  // dock icon is clicked and there are no other windows open.
  if (mainWindow === null) createWindow();
});
// In this file you can include the rest of your app's specific main process
// code. You can also put them in separate files and require them here.
```

#### 12) Update the script section of `package.json`

```bash
# Add this scripts
"electron": "wait-on http://localhost:4200 && electron .",
"electron-dev": "concurrently \"yarn run start\" \"yarn run electron\"",
"preelectron-pack": "yarn build",
"electron-pack": "electron-builder"

# You should end up with something similar
"scripts": {
  "ng": "ng",
  "start": "ng serve",
  "build": "ng build",
  "test": "ng test",
  "lint": "ng lint",
  "e2e": "ng e2e",
  "electron": "wait-on http://localhost:4200 && electron .",
  "electron-dev": "concurrently \"yarn run start\" \"yarn run electron\"",
  "preelectron-pack": "yarn build",
  "electron-pack": "electron-builder"
}
```

#### 13) Add the following configuration in `package.json`

**Note:** build configuration is used by electron-builder, modify it if you wish to add more packaging and native distribution options for different OS Platforms.

```bash
"main": "main.js",  # Application Entry Point, please verify entry point is set to main.js
"build": {
  "icon": "src/assets/favicon.png",
  "productName": "Angular and Electron App",
  "files": [
    "build/**/*",
    "main.js"
  ],
  "win": {},  # Windows Specific Configuration
  "linux": {},  # Linux Specific Configuration
  "mac": {}  # MacOs Specific Configuration
}
```

#### 14) Test drive your app

```bash
# Run your app
$ yarn electron-dev # or npm run electron-dev

# Package Your App
$ yarn electron-pack # or npm run electron-pack
```

### 💯 Result

<div align="center">
<img alt="Electron Angular Window Screeenshot" src="https://raw.githubusercontent.com/soulehshaikh99/assets/master/create-electron-framework-app/readme/png/create-angular-electron-app.png" />
</div>

<h3>😍 Made with ❤️ from Souleh</h3>

[![forthebadge](http://forthebadge.com/images/badges/built-with-love.svg)](http://forthebadge.com)
<br/>

<h3>📋 License: </h3>
Licensed under the <a href="https://github.com/soulehshaikh99/create-angular-electron-app/blob/master/LICENSE">MIT License</a>.