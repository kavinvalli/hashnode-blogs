## Local NodeJS Environment Variables

The [DotEnv](https://www.npmjs.com/package/dotenv) is an NPM package which allows you to load local NodeJS Environment Variables in your project. It is based on [The Twelve-Factor App Methodology](https://12factor.net/config) - Storing configuration in environment separate from code.

## Installation
The installation is as easy as any other NPM Package
```sh
npm install dotenv
# YARN
yarn add dotenv
```

## Setup
Create a `.env` file in your root directory. Add any env vars you want in that file.
For eg.
```
DB_HOST=localhost
DB_PORT=3306
DB_USER=root
DB_PASSWORD=password
```

## Load the variables
Now in your starting JS file (which you run using `node <filename>.js`) add the following line of code
```js
require('dotenv').config()
```
What this does is, it imports the `dotenv` module using the CommonJS syntax and then calls the `config` function on it. This loads up the dotenv variables in the `.env` file created earlier. You can also pass an object as an argument into it which you can find [here](https://www.npmjs.com/package/dotenv#options)

## Use the variables
You can use the variables inside that file now like any other env variable using the Global Object `process` and the object `env` inside it in the following way:
```js
console.log(process.env.DB_HOST)
```

Note that you can use the env variables inside the .env file only after calling the config function in the dotenv module. So the above line of code needs to come after the `require('dotenv').config()` function.