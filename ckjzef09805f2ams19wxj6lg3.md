## The ultimate .gitignore dev tool is here

I just found one of a dev tool called [gitignore.io](https://www.toptal.com/developers/gitignore) which as it's name suggests, helps generate a gitignore file for our project.

## Web
1. Go to www.gitignore.io
2. Fill in the languages, IDE's, OS's you're using
3. Click Create
4. Copy Code and paste it into a `.gitignore` file in your project root

## CLI
1. Go to [this link](https://docs.gitignore.io/install/command-line)
2. Follow instructions based on your os and terminal
3. Go to a project
4. List possibilities for gitignore
```sh
gi list
```

![Screenshot 2021-01-16 at 1.00.36 PM.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1610782245800/v6AYlqtIE.jpeg)
> This will list all the possibilities for your `.gitignore` file that you can choose from

5. Create a `.gitignore` file
Say, I am choosing `node`, `vscode`, and `macos` as my options.
```sh
gi node,vscode,macos >> .gitignore
```
![Screenshot 2021-01-16 at 1.01.38 PM.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1610782301817/sRMqHkdkp.jpeg)

And voilà, your `.gitignore` file has been created!