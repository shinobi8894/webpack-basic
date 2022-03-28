# How to use Webpack Basic
This is for beginners. How to use Webpack?
## Basic Setup
First let's create a directory, initialize npm, install webpack locally, and install the webpack-cli (the tool used to run webpack on the command line):
```
mkdir webpack-demo
cd webpack-demo
npm init -y
npm install webpack webpack-cli --save-dev
```
### Project
```
 webpack-basic
  |- package.json
  |- package-lock.json
 |- index.html
 |- /src
   |- index.js
```
### src/index.js
```
function component() {
  const element = document.createElement('div');

  // Lodash, currently included via a script, is required for this line to work
  element.innerHTML = _.join(['Hello', 'webpack'], ' ');

  return element;
}

document.body.appendChild(component());
```
### index.html
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Getting Started</title>
    <script src="https://unpkg.com/lodash@4.17.20"></script>
  </head>
  <body>
    <script src="./src/index.js"></script>
  </body>
</html>
```
We also need to adjust our package.json file in order to make sure we mark our package as private, as well as removing the main entry. This is to prevent an accidental publish of your code.

### Package.json
```
 {
   "name": "webpack-demo",
   "version": "1.0.0",
   "description": "",
  "private": true,
   "scripts": {
     "test": "echo \"Error: no test specified\" && exit 1"
   },
   "keywords": [],
   "author": "",
   "license": "MIT",
   "devDependencies": {
     "webpack": "^5.38.1",
     "webpack-cli": "^4.7.2",
   }
 }
 ```
 
 ### Creating Bundle
```
  webpack-demo
  |- package.json
  |- package-lock.json
 |- /dist
   |- index.html
  |- /src
    |- index.js
  ```
  
  ```
  npm install --save lodash
  ```
  
  ### src/index.js
  
  ```
  import _ from 'lodash';

 function component() {
   const element = document.createElement('div');

   element.innerHTML = _.join(['Hello', 'webpack'], ' ');

   return element;
 }

 document.body.appendChild(component());
 ```
 
 ### dist/index.html
 ```
  <!DOCTYPE html>
 <html>
   <head>
     <meta charset="utf-8" />
     <title>Getting Started</title>
   </head>
   <body>
    <script src="main.js"></script>
   </body>
 </html>
 ```
 
 ## Final
 ```
 npx webpack
 ```
 Open the index.html
