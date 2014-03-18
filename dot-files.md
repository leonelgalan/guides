# Dot Files

## .gitignore
Setting a global `.gitignore` file is a good idea and excluding the .DS_Store files from all our projects even better!

```
git config --global core.excludesfile ~/.gitignore
echo ".DS_Store" >> ~/.gitignore
```

## .gemrc
Install gems faster!

```
gem: --no-ri --no-rdoc
```

[![Analytics](https://ga-beacon.appspot.com/UA-49118238-1/leonelgalan/guides/dot-files.md?pixel)](https://github.com/igrigorik/ga-beacon)
