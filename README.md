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
