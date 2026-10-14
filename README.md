initial code to connect Github with vs code
check
git remote -v  
git config --global user.name
git config --global user.email 

add
git config --global user.name "username"
git config --global user.email "email" 
git remote add origin https://github.com/Shakana25/Test-React   

remove
git config --global --unset user.name
git config --global --unset user.email
git remote remove origin

echo "# Test-React" >> README.md
git init
git add README.md // git add .
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/Shakana25/Test-React.git
git push -u origin main

Generate token Manual Navigation
If you want to find it from your GitHub profile page:
Click your profile icon in the top-right corner of GitHub.
Click Settings.Scroll all the way down on the left sidebar to Developer Settings (at the very bottom).Click Personal access tokens $\rightarrow$ Tokens (classic).
Click Generate new token $\rightarrow$ Generate new token (classic).
Check the repo box, generate it, copy the code, and paste it into that window!

if a code is put into production need to bundle/ optimised/ minimised/compressed our code remove comment, consolelog.

create react app it will create immidiately.
not only react there are some other package help us to make react code fast.
npm- node package manager. 
npm.com - it manages the packages
standered repository for the all packages.

now i want to get npm 
npm init /npm init -y

package name: (react-day2) 
version: (1.0.0) 
description: this is start of react project creation
entry point: (app.js) 
test command: jest
git repository: (https://github.com/Shakana25/Test-React.git) 
keywords: test, react, first
author: shakana
license: (ISC) 
type: (commonjs) 

package.json created: configuration for npm
npm take care the version of all packages. 
now i want to get packages from npm: start installing our dependency

most important package is bundler: webpack/ vite/parcel 
These are bundle/ optimised/ minimised/compressed/clean our code, give to production

npm install -D parcel :- like this way we can install any dependency from npm. 
 -D mean dev dependency, use for develepment phase.
  "devDependencies": {
    "parcel": "^2.16.4"
  }

  ^ caret- parcel automatically update 2.16.5 - minor upgrade //safe
  ~ tilde- atomatically update major version- 3.1.1 // not safe- lot of things is break"
  "parcel": "2.16.4"- no upgrade

  it created package-lock.json - keep the exact version of package.

  "node_modules/@parcel/bundler-default": {
      "version": "2.16.4",
      "resolved": "https://registry.npmjs.org/@parcel/bundler-default/-/bundler-default-2.16.4.tgz",
      "integrity": "sha512-Nb8peNvhfm1+660CLwssWh4weY+Mv6vEGS6GPKqzJmTMw50udi0eS1YuWFzvmhSiu1KsYcUD37mqQ1LuIDtWoA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@parcel/diagnostic": "2.16.4",
        "@parcel/graph": "3.6.4",
        "@parcel/plugin": "2.16.4",
        "@parcel/rust": "2.16.4",
        "@parcel/utils": "2.16.4",
        "nullthrows": "^1.1.1"
      },}
      integrity: developer said it work on local , but break in production. this integrity. keep exact version from development , production.

      and node modules also created when install package.json contain only the version, node module like a database contain all the package- very heavy

      our project need parcel, like wise parcel need some other dependency(packages)- this is call as transitive dependency. 

      how it know, what are the dependency use in parcel, parcel's package-lock.json contain all the dependecy versions.
      our project have 1 package.json, package-lock.json. like wise each and every transitive package have unique  package.json, package-lock.json.

      go to folder , check the size of node module, it is huge.
      we can't put this huge node module to git hub/ production. 

      check sourse control how many file we changed?
      so we will create git ignore file and add /node_modules.

      we have to put package, package-lock.json in git, production. then only they understand all the trasitive packages actual versions. 

      if i have my package, package-lock , i can regenerate node_modules. 
      : npm install  //it will recreate node_modules. 
      thats why we don't need to add node module in to git/ production.

      what ever  things we can re generate, we don't need to put it in git.
      npx parcel index.html 
      // run our project in local host// our file hosted on local server
      parcel create and give server. parcel host our app in the server.

      npm- packege manage
      npx- execute package

      another way get react into our app using npm.