## How to update a forked repository to match with the origin repository on Github

When you want to contribute to open source, one of the most important things is understand, forking and branching.

Once you have updated some code and made a pull request, you might not do anything with your forks for a lot of time. So the next time you do something, you will have to update it. But how?

## Add an upstream remote
We'll add a remote to our repository called upstream with the follow command:

```shell
git remote add upstream https://github.com/OriginalRepo/OriginalProject.git
```
Make sure to use the link of the origin repository

Now you canverify by running

```shell
git remote -v
```

## Fetch branches and commits from upstream
Run the following command in order to fetch all the updated banches and commits from upstream

```shell
git fetch upstream
```

## Checkout your fork’s local master

```shell
git checkout master
```

## Merge changes from upstream/master into it

```shell
git merge upstream/master
```

## Push changes to update your fork master'

```shell
git push origin master
```

> Note that you might have a different base branch that master.

That's it.. Have fun!