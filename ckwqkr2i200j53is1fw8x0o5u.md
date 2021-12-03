## I wrote a Github CLI extension to fuzzy find repos and run actions on them

I went ahead and created a Github CLI extension which fuzzy finds repos and you can choose an action you want to run on it.

### Requirements
1. `gh cli` - minimum version (2.0.0)
2. `fzf`

## Installation
### Via the Github CLI
```sh
gh extension install kavinvalli/gh-repo-fzf
```

### Manually
You can also install it manually by following these steps:
1. Clone repo
```bash
# git
git clone https://github.com/kavinvalli/gh-repo-fzf
# github cli
gh repo clone kavinvalli/gh-fzf
```

2. cd into it
```bash
cd gh-repo-fzf
```

3. Install it locally
```bash
gh extension install .
```

## Usage

- To list all directories you have access to, run:

```sh
gh repo-fzf
```

- To list directories of a particular user / organisation:

```sh
gh repo-fzf <username/organisation-name>
```

After choosing a directory, you will be prompted to choose one of the following:
- `Clone` - clones a repository to your local machine
- `View` - opens the Github URL of the repository
- `Fork` - forks the repository
- `Archive` - archives the repository

Feel free to put up any issue you face on the [Github Repository](https://github.com/kavinvalli/gh-repo-fzf).
Contributions are also welcome.

Don't forget to star the repo 😉

%[https://github.com/kavinvalli/gh-repo-fzf]