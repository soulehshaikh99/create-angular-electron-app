# Angular and Electron JS App
:rocket: :telescope: Discover the easiest way to get started with the most popular blend of Angular and Electron JS App

<h3>Use this boilerplate:</h3>

```cmd
git clone https://github.com/soulehshaikh99/create-angular-electron-app.git
cd create-angular-electron-app

yarn install
yarn global add @angular/cli electron electron-builder
    or
npm install
npm i -g @angular/cli electron electron-builder
```

**Note:** If you wish to use npm over yarn then modify package.json by replacing 'yarn' with 'npm' in preelectron-pack script.
But I strongly recommend using <em>yarn</em> as it is a better choice when compared to <em>npm</em>.

<h3>Scripts Instructions:</h3>

**1) For running app in development mode**

```cmd
// Execute both the commands in seperate windows

yarn start //Wait for the server to start and compile everything
yarn run electron //Run this command when compiling is done
    or
npm start //Wait for the server to start and compile everything
npm run electron //Run this command when compiling is done
```

**2) For packaging app using electron-builder**

```cmd
yarn run electron-pack
        or
npm run electron-pack
```

<h3>Manual Setup using <a href="https://angular.io/cli">Angular CLI</a>(@angular/cli)</h3>

**1) Install Necessary Packages Globally**

```cmd
yarn global add @angular/cli electron electron-builder
    or
npm i -g @angular/cli electron electron-builder
```

**2) Create New Angular App**

```cmd
ng new create-angular-electron-app
```

**3) Change directory to that project folder**

```cmd 
cd create-angular-electron-app
```

**4) Install electron as development dependency**

```cmd 
yarn add --dev electron
            or
npm i -D electron
```

**5) Create main.js file in root of project folder**

```cmd
// Windows Users
notepad.exe main.js

// Linux and macOS Users
touch main.js
```

**6) Paste this code in main.js file**

```javascript
// Modules to control application life and create native browser window
const {app, BrowserWindow} = require('electron');
const path = require('path');

// Keep a global reference of the window object, if you don't, the window will
// be closed automatically when the JavaScript object is garbage collected.
let mainWindow;

function isDev() {
    return !app.isPackaged;
}

function createWindow () {
    // Create the browser window.
    mainWindow = new BrowserWindow({
        width: 800,
        height: 650,
        webPreferences: {
            nodeIntegration: true
        },
        // Change this code while packaging app to load icon from `build` directory
        icon: isDev() ? `${path.join(__dirname, 'src/favicon.ico')}` : `${path.join(__dirname, 'build/favicon.ico')}`,
        show: false
    });


    // This block of code is intended for development purpose only.
    // Only use loadFile() method when packaging app
    isDev() ? mainWindow.loadURL('http://localhost:4200/') : mainWindow.loadFile(`${path.join(__dirname, 'build/index.html')}`);

    // Open the DevTools and also disable Electron Security Warning.
    // process.env['ELECTRON_DISABLE_SECURITY_WARNINGS'] = true;
    // mainWindow.webContents.openDevTools();

    // Emitted when the window is closed.
    mainWindow.on('closed', function () {
        // Dereference the window object, usually you would store windows
        // in an array if your app supports multi windows, this is the time
        // when you should delete the corresponding element.
        mainWindow = null
    });

    // Emitted when the window is ready to be shown
    // This helps in showing the window gracefully.
    mainWindow.once('ready-to-show', () => {
        mainWindow.show()
    });
}

// This method will be called when Electron has finished
// initialization and is ready to create browser windows.
// Some APIs can only be used after this event occurs.
app.on('ready', createWindow);

// Quit when all windows are closed.
app.on('window-all-closed', function () {
// On macOS it is common for applications and their menu bar
// to stay active until the user quits explicitly with Cmd + Q
    if (process.platform !== 'darwin') app.quit()
});

app.on('activate', function () {
// On macOS it's common to re-create a window in the app when the
// dock icon is clicked and there are no other windows open.
    if (mainWindow === null) createWindow()
});

// In this file you can include the rest of your app's specific main process
// code. You can also put them in separate files and require them here.
```

**7) Add a period in base tag (href attribute) before slash in src/index.html**

`<base href="./">`

**8) Now change the outputPath in angular.json to build directory**

`"outputPath": "build"`

**9) Move all dependencies to devDependencies as they are not needed in production build.
Your devDependencies section should look something like this**

```json
"devDependencies": {
  "@angular-devkit/build-angular": "~0.13.0",
  "@angular/animations": "~7.2.0",
  "@angular/cli": "~7.3.9",
  "@angular/common": "~7.2.0",
  "@angular/compiler": "~7.2.0",
  "@angular/compiler-cli": "~7.2.0",
  "@angular/core": "~7.2.0",
  "@angular/forms": "~7.2.0",
  "@angular/language-service": "~7.2.0",
  "@angular/platform-browser": "~7.2.0",
  "@angular/platform-browser-dynamic": "~7.2.0",
  "@angular/router": "~7.2.0",
  "@types/jasmine": "~2.8.8",
  "@types/jasminewd2": "~2.0.3",
  "@types/node": "~8.9.4",
  "codelyzer": "~4.5.0",
  "core-js": "^2.5.4",
  "electron": "^5.0.1",
  "jasmine-core": "~2.99.1",
  "jasmine-spec-reporter": "~4.2.1",
  "karma": "~4.0.0",
  "karma-chrome-launcher": "~2.2.0",
  "karma-coverage-istanbul-reporter": "~2.0.1",
  "karma-jasmine": "~1.1.2",
  "karma-jasmine-html-reporter": "^0.2.2",
  "protractor": "~5.4.0",
  "rxjs": "~6.3.3",
  "ts-node": "~7.0.0",
  "tslib": "^1.9.0",
  "tslint": "~5.11.0",
  "typescript": "~3.2.2",
  "zone.js": "~0.8.26"
}
```

**10) Add electron, preelectron-pack and electron-pack scripts. Make sure your scripts section in package.json looks like this**

```json
"scripts": {
  "ng": "ng",
  "start": "ng serve",
  "build": "ng build --prod",
  "test": "ng test",
  "lint": "ng lint",
  "e2e": "ng e2e",
  "electron": "electron .",
  "preelectron-pack": "yarn build",
  "electron-pack": "build"
}
```

**11) Add the following configuration in package.json**

**Note:** build configuration is used by electron-builder, modify it if you wish to add more packaging and native distribution options for different OS Platforms.
```json
"main": "main.js",
"build": {
  "productName": "Angular and Electron App",
  "files": [
    "build/**/*",
    "main.js"
  ]
}
```

**Result**

![Result](https://user-images.githubusercontent.com/39525716/57412119-489e8380-720d-11e9-9a2a-17b3073052c9.PNG)

<h3>Made with :heart: from Souleh</h3>

<h3>:clipboard: License: </h3>
Licensed under the <a href="https://github.com/soulehshaikh99/create-angular-electron-app/blob/master/LICENSE">MIT License</a>.
