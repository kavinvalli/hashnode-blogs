## Start with your first Tailwind CSS Project

Tailwind CSS is a low-level css framework which provides you hundred of classes to make styling easier. I have even written a full website without writing any custom css. Tailwind can do that. Lately, it is being used in many big projects and companies

## Making a directory
```sh
mkdir tailwind_dev && cd tailwind_dev
```
Paste the above in your terminal/command prompt

Now to install tailwind, we need to use **npm** which is a package manager for node and javascript. So, to install tailwind, you need to have node installed on your machine, which brings in npm with it
> You can download Node from https://nodejs.org/en/download/

## Initializing npm
To use npm inside a project, you need to initialize the project to use npm. So, to do that, paste the below in the command line
```sh
npm init -y
```
This will create the following file in the directory
- package.json

## Installing **Tailwind**
```sh
npm install tailwindcss --save
```
This will create a folder called *node_modules*

## Using tailwind
We will be having two directories in our folder
- src
- public

The src folder will have the uncompiled css.
The public folder will have everything ready and all the html, js, etc, files.

So, to do that create these two using the following command
```sh
mkdir public && mkdir src
```

```sh
cd src && touch styles.css && cd ..
```

This will create the two directories and create are style.css file inside the src directory

```sh
cd public && touch index.html && cd ..
```

Now, open the folder in your favourite code editor. My favourite is VS Code, and if you have it installed you can open the directory with the following command
```sh
code .
```
## Start editing CSS
Now, go to the style.css file inside your src folder and add the following:
```css
@tailwind base;

@tailwind components;

@tailwind utilities;
```
These are just some basic tailwind css you need to import to get started.

Now, in you package.json file and edit the following line:
```diff
- "test": "echo \"Error: no test specified\" && exit 1"
+ "build-css": "tailwindcss build src/styles.css -o public/styles.css"
```
Now, run the following in the terminal
```sh
npm run build-css
```

Now, you would be able to see a styles.css file inside the public directory

## Editing HTML to use tailwind

Now in the *index.html* file, add the following inside the head tag

```html
<link rel="stylesheet" href="styles.css">
```

Voilà, you are ready to use tailwind. To verify, just add the following in the body tag

```html
<h1>H1</h1>
<h2>H2</h2>
<h3>H3</h3>
```

If the size of all the three texts, is the same, then you're ready to start off.
I would suggest going through the video below and the following videos of the playlist, of **The Net Ninja**. I learnt Tailwind CSS from his videos and personally love the way, he teaches it

%[https://www.youtube.com/watch?v=3ZMUgga6SsY]

You should also go through the [Tailwind documentation](https://tailwindcss.com/docs/installation) for better understanding 
