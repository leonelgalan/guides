# Git

I strongly recommend you read a couple of chapters (1-3) of [Pro Git](http://git-scm.com/book). This book was published by Apress and available for free online at git's official site.

## The Basics

### Cloning

Getting an existing repo on your computer:

```sh
git clone git@github.com:rails/rails.git
```

Or `git clone rails/rails` if you have [hub](https://github.com/github/hub) installed and aliased.

This will clone the `rails/rails` repo from Github and copy it's content to a `rails` project. A hidden result of this operation is a [remote](http://git-scm.com/book/en/Git-Basics-Working-with-Remotes) called `origin` pointing to the original repo.

Avoid using **https** addresses when cloning. If you do this, you will be promoted for your credentials constantly.

### Pulling/Pushing from a Second Remote

You can have multiple remotes per repository (e.g., github/heroku, github/bitbucket, etc.)

```sh
git remote add heroku git@heroku.com:enigmatic-river.git
```
You can see all your remotes by typing

```sh
git remote -v
```
#### Pull and Push
Always (at the beginning) pull before you push. This makes sure you have the latest code locally, before you push the changes to the server, conflicts make occur when pulling.

```sh
git pull origin master
git push origin master
```

### Commit

- Avoid using `-a or --all` when commiting, similarly avoid using `git add .` before commiting.
- Commit often and small, write meaningful commit messages.

### Merge Conflicts

> TODO

### Branching

> TODO


