# SSJS Scripts Intro
Welcome to the wonderful world of Server Side Javascript! Arguably your most powerful tool in SFMC. Don't believe me? Here are some of the amazing things you can do with SSJS; 

## SSJS Pros
* Create reusable code through the use of functions (something you're not able to do in AMPscript)

* Create more robust and simpler code with Objects, Arrays and their associated Properties/Methods (Again, something AMPscript doesn't have. Just remember that SFMC only supports [ECMAscript 3.0](https://www.ecma-international.org/wp-content/uploads/ECMA-262_3rd_edition_december_1999.pdf))

* Access Objects and data via SFMCs API using WSProxy, which basically gives you unlimited possibilities of what you can do 

* Use SSJS as part of Automations via Script Activities (Again, imagine the possibilities, especially when you combine this with WSProxy)

In short, if you're using SFMC, you should really learn SSJS. It will make your life a lot easier. However, SSJS isn't perfect, and certainly has its Cons

## SSJS Cons
* SSJS is slow to render so shouldn't be used in emails since it has the possibility of timing out (especially if your ssjs includes an API call)

* Again, since SSJS is slow to render, it shouldnt be used for building Apps (i.e. Building a SFMC Super Admin Web App on CloudPages)

* SSJS only supports [ECMAscript 3.0](https://www.ecma-international.org/wp-content/uploads/ECMA-262_3rd_edition_december_1999.pdf). This is frustrating because modern day js has a lot of features and capabilities that make coding simpler. Read here for a slight workaround to this.

* SSJS can't interact with your CRM environment directly (it can however be used with AMPscript which of course can access records in connected CRMs)

* SSJS can be used with AMPscript, however it's a bit awkward to use both together and isn't recommended

* SSJS doesn't support [external libraries](https://developer.salesforce.com/docs/atlas.en-us.mc-programmatic-content.meta/mc-programmatic-content/index.htm)


# SSJS Notes

## How to Convert Javascript ES6 -> ES3
Unfortunately, SSJS doesn't support ECMAscript 3.0 (AKA ES3), this means SSJS can only us js capabilties from 1999. However, if you are someone who knows how to write in modern day javascript, or you just want to use a method not available in ES3, you can leverage Google's Closure Compiler tool.

### What is Google's Closure Compiler tool? 
[Googles Closure Compiler](https://developers.google.com/closure/compiler) tool is a nifty tool for making Javascript download and run faster. It basically optimizes it and cuts out and 'dead' code. What's more, is that you can use it to convert your ES6 javascript code to ES3. 

### Steps to Use Google's Closure Compiler tool 
1. Open Visual Studio code and create a working directory
2. Initialize npm 
```
npm init
```
3. Install  google-closure-compiler
```
npm install --save google-closure-compiler
```
4. Create an app.js file and write your code (it can be named anything)
5. Run google-closure compiler 
```
google-closure-compiler --js app.js --language_in ECMASCRIPT_2020 --js_output_file newApp.js --language_out ECMASCRIPT3
```


