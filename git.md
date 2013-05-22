# Git

I strongly recommend you read a couple of chapters (1-3) of [Pro Git](http://git-scm.com/book). This book was published by Apress and available for free online at git's official site.

## The Basics

### Cloning

Getting an existing repo on your computer:

```
git clone git@github.com:rails/rails.git
```

This will clone the `rails/rails` repo from Github and copy it's content to a `rails` project. A hidden result of this operation is a [remote](http://git-scm.com/book/en/Git-Basics-Working-with-Remotes) called `origin` pointing to the original repo.

Avoid using **https** addresses when cloning. If you do this, you will be promoted for your credentials constantly.

### Pulling/Pushing from a Second Remote

You can have multiple remotes per repository (e.g., github/heroku, github/bitbucket, etc.)

```
git remote add heroku git@heroku.com:enigmatic-river.git
```
You can see all your remotes by typing

```
git remote -v
```
#### Pull and Push

```
git pull origin master
git push origin master
```

### Branching

> TODO


