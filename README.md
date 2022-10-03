# NPM (Node Package Manager)

Node js has several packages. Each package is used to perform deifferent tasks. So you can install packages as you required.  
You can know about the packages from [npm](https://www.npmjs.com/) site.  

**How to get started with npm:**  
Use the command `npm init` to initialize the npm. Provide the necessary informations. After providing all information a json file will be created named `package.json`. Like,  
```json
//package.json
{
  "name": "npm",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "J Iqbal",
  "license": "ISC"
}
```

If you don't want to provide any information in creating the package.json file then use `npm init -y` command. `-y` means yes to all. All fields will remain as default.  
You can use the command `code .` to open the project in `V S code`.  

**Installing Packages:**  
You can install packages using command `npm install <package name>`. That will install all necessary dependent files. If you write the command in terminal then following will be happened.
```sh
PS D:\NPM\practice> npm install moment

added 1 package, and audited 2 packages in 2s

found 0 vulnerabilities
```
So the package `moment` is installed and that will be added in `package.json` file under `dependencies` like as, 
```json
//package.json
"dependencies": {
    "moment": "^2.29.4"
  }
```
The latest version is installed. If you want to install any specific version then use command `npm install <package name>@<version>`. Such as `npm install moment@2.2.1`.  
If you want to install the package as development dependencies then use command `npm install -D <package name>`. Such as, `npm install -D moment` and that will result as below.
```json
//package.json
 "devDependencies": {
    "moment": "^2.29.4"
  }
```
**Semantic Versioning:**  
The installed package version looks like 5.12.3. Here segregation is like major.minor.patch.  
**Patch update** appears with bug fixing, When any bug is fixed the patch version is updated.  
**Mainor update** means the addition of new features which is compatible with previous one.  
**Major update** means changing th eentire project of something which is not compatible with previous vresion.  

**Version Controlling:**  
Let say a project contains some npm packages and after few days new version is available. So how that version can be updated and which updates will be compatible with the current project.  
**Exact Version:** No updated version will be compatible if you use the exact version. Such as,
```json
  "devDependencies": {
    "moment": "2.29.4"
  }
```
You can use the command `npm install <package name> --save-exact` to install the exact version.

**Greater Version:** Only greater versions of the specified version will be compatible with the current project. Here the sign `>` is used.. Such as,
```json
  "devDependencies": {
    "moment": ">2.29.4"
  }
```
**Compatible Changes:** Only minor and patch updates will be compatible. Here `^` sign is used. Range is in between 2.29.4 and <3.0.0
```json
  "devDependencies": {
    "moment": "^2.29.4"
  }
```
**Minor Level Changes:** Only patch update will be compatible. Here `~` sign is used. Range is in between 2.29.4 and <2.30.0
```json
  "devDependencies": {
    "moment": "~2.29.4"
  }
```
**`npm view`:**  
You can see the details of a package using command `npm view <package name>` in terminal.
```sh
PS D:\NPM\practice> npm view moment

moment@2.29.4 | MIT | deps: none | versions: 74
Parse, validate, manipulate, and display dates
https://momentjs.com

keywords: moment, date, time, parse, format, validate, i18n, l10n, ender

dist
.tarball: https://registry.npmjs.org/moment/-/moment-2.29.4.tgz
.shasum: 3dbe052889fe7c1b2ed966fcb3a77328964ef108
.integrity: sha512-5LC9SOxjSc2HF6vO2CyuTDNivEdoz2IvyJJGj6X8DJ0eFyfszE0QiEd+iXmBvUP3WHxSjFH/vIsA0EN00cgr8w==
.unpackedSize: 4.2 MB

maintainers:
- ichernev <iskren.chernev@gmail.com>
- timrwood <washwithcare@gmail.com>
- mj1856 <mj1856@hotmail.com>
- maggiepint <maggiepint@gmail.com>
- marwahaha <marwahaha@berkeley.edu>

dist-tags:
latest: 2.29.4

published 2 months ago by ichernev <iskren.chernev@gmail.com>
```
You can see the all published versions using command `npm view <package name> versions`
```sh
PS D:\NPM\practice> npm view moment versions
[
  '1.0.0',  '1.0.1',  '1.1.0',  '1.1.1',  '1.2.0',
  '1.3.0',  '1.4.0',  '1.5.0',  '1.5.1',  '1.6.0',
  '1.6.1',  '1.6.2',  '1.7.0',  '1.7.1',  '1.7.2',
  '2.0.0',  '2.1.0',  '2.2.1',  '2.3.0',  '2.3.1',
  '2.4.0',  '2.5.0',  '2.5.1',  '2.6.0',  '2.7.0',
  '2.8.1',  '2.8.2',  '2.8.3',  '2.8.4',  '2.9.0',
  '2.10.2', '2.10.3', '2.10.5', '2.10.6', '2.11.0',
  '2.11.1', '2.11.2', '2.12.0', '2.13.0', '2.14.0',
  '2.14.1', '2.15.0', '2.15.1', '2.15.2', '2.16.0',
  '2.17.0', '2.17.1', '2.18.0', '2.18.1', '2.19.0',
  '2.19.1', '2.19.2', '2.19.3', '2.19.4', '2.20.0',
  '2.20.1', '2.21.0', '2.22.0', '2.22.1', '2.22.2',
  '2.23.0', '2.24.0', '2.25.0', '2.25.1', '2.25.2',
  '2.25.3', '2.26.0', '2.27.0', '2.28.0', '2.29.0',
  '2.29.1', '2.29.2', '2.29.3', '2.29.4'
]
```

**`package.json`**  
* Containing all the dependent package information.
* Generated and updated this file autometically.
* This file is needed to commit in source control

**`npm update`:**  
You can update the version of the packages depending on the version control.  
Updating the versions for all packages using command `npm update`.  
Updating the  version foe a specific package using command `npm update <package name>`.

**npm scripts:**  
An object called scripts is available in `package.json`. There are two types of scripts.  
* Default scripts
* Custom scripts

**Default scripts:**  
Some built in scripts are availble. Such as,
```json
  "scripts": {
    "prestart": "node ./preServer.js",
    "start": "node ./myServer.js",
    "poststart": "echo \"Post-Start\""
    }
```
If you execute the code from terminal using command `npm start` then first `prestart` then `start` and then `poststart` will be executed.

**Custom scripts:**  
You can add scripts as you required.
```json
  "scripts": {
    "custom": "node ./customScripts.js",
    "custom2": "echo \"custom 2\"",
  },
```
If you execute the scripts using command `npm run custom` then first script will be executed.  
You can execute all the scripts using a package `npm-run-all`. Install the package and add another script in package.json file.
```json
  "scripts": {
    "prestart": "node ./preServer.js",
    "start": "node ./myServer.js",
    "poststart": "echo \"Post-Start\"",
    "custom": "node ./customScripts.js",
    "custom2": "echo \"custom 2\"",
    "all": "npm-run-all --parallel start custom custom2"
  },
```
Here scripts `all` is defined as run all scripts. When you will use `npm-run-all --parallel` then all the scripts will be executed in parallel. But if you will use `npm-run-all --serial` then the scripts will be executed one after another. You can run this scripts using command `npm run all`.
