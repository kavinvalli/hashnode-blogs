## How to add auto-reload to your Node JS app?

This is one of the first things I searched for, when I started learning Node JS with Express, since it was becoming too hard of a job to keep stopping and re-running the server, again and again. This is why, I use an npm package called [**nodemon**](https://www.npmjs.com/package/nodemon)

## Setting up a node server
I hope you have NodeJS installed in your machine.
- Let's setup the directory
```sh
mkdir nodemon_tutorial && cd nodemon_tutorial
```

```sh
npm init -y
```
>This would create a package.json
- Now, let's install express to start a server
```sh
npm install express
```

- Now, let's create a file named index.js
```sh
touch index.js
```

- Open the folder in your favourite Code Editor. I use VS Code, so I will run:
```sh
code .
```

- Now inside index.js add the following

```js
const express = require('express');
const app = express();
const port = process.env.PORT || 3000

app.get('/', (req, res) => {
   res.send("Hello World!");
})

app.listen(port, () => {
   console.log(`App is running at port: ${port}`);
})
```

### Explanation of code
- *Line 1:* In line 1, we are just importing the express package for running the server
- *Line 2:* We are making an app, by instantiating the express module
- *Line 3:* We are creating a variable for the port. It will search for an environment variable with name `PORT`. If it does not find any, by default, it assigns it to `3000`.
- *Line 5-7:* Here, we are just creating a route. So, if a person, sends a `get` request to `/`, then he will get `Hello World` as response
- *Line 9-11:* We are just making the app run and listen on port variable
Now, you could run this app, by simply saying
```sh
node index.js
```

This will give the output
```sh
App is running at port: 3000
```
- Now just go to your browser and type: `localhost:3000/`

## Disadvantage of this
- Now go to index.js and change `"Hello World!"` to `"Hello, this is my first nodemon app!"`
- Now, even if you go to the browser and refresh, it will remain the same

## Settings up nodemon to run the server
- To install **nodemon** run:
```sh
npm install nodemon --save-dev
```
- We are adding `--save-dev` because we want this only in development and not while publishing it.

- Now, go to `package.json` file and remove the following line:

```js
"test": "echo \"Error: no test specified\" && exit 1"
```
**And add the following line**

```js
"start":"nodemon index.js"
```

- So, what we are doing is that we are making nodemon run the server instead of node.
- Now, terminate the server which was running and run:
```sh
npm start
```

- Now, go to localhost:3000
- Try changing the response while getting / in the index.js and after you save it, the server should auto-reload. Now go to the browser and refresh again. You should see the new response
