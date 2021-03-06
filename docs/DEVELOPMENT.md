# Local



### Development

You'll need [Node.js](https://nodejs.org) installed on your computer in order to build this app.

```bash
git clone git clone https://github.com/kevando/screenshit.git
cd screnshiht
yarn install
yarn start
# or
yarn dev
```

### Distribution

_TBD_



## ![Logo](app/icon/32x32.png)



```

{
  "name": "screenshit",
  "productName": "Screen Shit",
  "version": "1.1.1",
  "description": "Coffee for screen shots",
  "main": "src/main.js",
  "license": "MIT",
  "author": "kevando",
  "devDependencies": {
    "@octokit/rest": "^16.3.2",
    "chai": "^3.4.1",
    "chai-as-promised": "^6.0.0",
    "check-for-leaks": "^1.2.0",
    "devtron": "^1.3.0",
    "electron-installer-dmg": "^2.0.0",
    "electron-packager": "^12.2.0",
    "electron-prebuilt-compile": "3.0.2",
    "mocha": "^5.2.0",
    "request": "^2.70.0",
    "rimraf": "^2.5.2",
    "signcode": "^0.5.0",
    "spectron": "^5.0.0",
    "standard": "^8.2.0"
  },
  "dependencies": {
    "electron": "^4.0.1",
    "electron-log": "^2.2.14",
    "electron-settings": "^3.0.7",
    "electron-shortcut-normalizer": "^1.0.0",
    "glob": "^7.1.0",
    "highlight.js": "^9.3.0",
    "update-electron-app": "^1.1.1"
  },
  "scripts": {
    "start": "electron .",
    "dev": "electron . --debug",
    "test": "mocha && standard",
    "package": "npm-run-all package:*",
    "package:mac": "electron-packager . --overwrite --platform=darwin --arch=x64 --out=out --icon=assets/app-icon/mac/app.icns --osx-sign.identity='Developer ID Application: GitHub' --extend-info=assets/mac/info.plist",
    "package:win": "electron-packager . --overwrite --platform=win32 --arch=ia32 --out=out --icon=assets/app-icon/win/app.ico",
    "package:linux": "electron-packager . --overwrite --platform=linux --arch=x64 --out=out",
    "package:sign-exe": "signcode './out/Electron API Demos-win32-ia32/Electron API Demos.exe' --cert ~/electron-api-demos.p12 --prompt --name 'Electron API Demos' --url 'http://electron.atom.io'",
    "package:installer": "node ./script/installer.js",
    "package:sign-installer": "signcode './out/windows-installer/ElectronAPIDemosSetup.exe' --cert ~/electron-api-demos.p12 --prompt --name 'Electron API Demos' --url 'http://electron.atom.io'",
    "xpackage:mas": "./script/mas.sh",
    "windows-store": "node ./script/windows-store.js",
    "release": "node ./script/release.js",
    "prepack": "check-for-leaks",
    "prepush": "check-for-leaks",
    "make": "electron-packager . --overwrite --platform=darwin --arch=x64 --icon=app/icon/icon.icns --prune=true --out=out"
  },
  "repository": "https://github.com/kevando/screenshit",
  "keywords": [
    "screenshot",
    "screen shot",
    "coffee"
  ],
  
  

  "standard": {
    "env": {
      "mocha": true
    }
  },
  "config": {
    "forge": {
      "make_targets": {
        "win32": [
          "squirrel"
        ],
        "darwin": [
          "zip"
        ],
        "linux": [
          "deb",
          "rpm"
        ]
      },
      "electronPackagerConfig": {
        "packageManager": "yarn",
        "icon": "app/icon/icon.icns",
        "osxSign": {
          "identity": "Developer ID Application: Kevaid Inc. (E34JX9GA2A)"
        }
      },
      "electronWinstallerConfig": {
        "name": "screen_shit"
      },
      "electronInstallerDebian": {},
      "electronInstallerRedhat": {},
      "github_repository": {
        "owner": "kevando",
        "name": "screenshit"
      },
      "windowsStoreConfig": {
        "packageName": "",
        "name": "screenshit"
      }
    }
  }
}

```