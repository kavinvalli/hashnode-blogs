## Control your Github from the command line with the Github CLI

Want to create a repository, but don't want to go to  [Github](https://github.com)  and follow that manual and perhaps long process, every single time.

Use the [Official Github CLI](https://cli.github.com/). It can do a lot of stuff ranging from creating a repo to closing a PR. I have written down some important commands in this blog post. (Have also linked the docs for the commands)

## [Login](https://cli.github.com/manual/gh_auth_login)
First, to use some of the commands listed below, you will have to authenticate the CLI by running
```sh
gh auth login
```

## [Creating a repository](https://cli.github.com/manual/gh_repo_create)
This is probably the command I use the most
```sh
gh repo create repo_name
```

## [List repositories of a user](https://cli.github.com/manual/gh_repo_list)
```sh
gh repo list username
```

## [View Repository in web](https://cli.github.com/manual/gh_repo_view)
### View any repository in web
```sh
gh repo view owner/repo_name --web
```
### View the repository you're currently in (cloned repository)
```sh
gh repo view --web
```

## [Aliases](https://cli.github.com/manual/gh_alias)
### List Aliases
```sh
gh alias list
```
### Set Alias
```sh
gh alias set <alias> <expansion>
```
### Delete Alias
```sh
gh alias delete <alias>
```

These are my most used commands but there are a lot more which can be found on the Github CLI Docs. And most of these commands listed above can also be used with some flags which are listed in the documentations.