## Requirements

* An Intel CPU
* OS X 10.5 or higher
* [Xcode](http://itunes.apple.com/us/app/xcode/id497799835) (~1.5 GB) or [Command Line Tools for Xcode](https://developer.apple.com/downloads) (~100 MB). Using Command Line Tools for Xcode requires:
  * `sudo xcode-select -switch /usr/bin` (http://stackoverflow.com/a/11729126/637094)
  * Replace `/usr/bin/xcrun` with (http://stackoverflow.com/q/13041525/637094):

```bash
#!/bin/bash
$@
```

Read the [longer instructions at Homebrew Github Wiki](https://github.com/mxcl/homebrew/wiki/Installation)

## Installation
```sh
ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"
```

## Troubleshooting
```sh
brew doctor
```

## Usage
**Update brew and make sure you have no issues before installing new software (for example, `git`)**

```sh
brew update
brew doctor

brew install git
```

Periodically run `brew outdated` to see what goodies (new versions) are you missing

```sh
brew outdated
...
ninja (1.1.0 < 1.3.4)
...
```
 >  Ninjas 1.3.4 are better than 1.1.0, no doubt!

Upgrade `ninja` by typing `brew upgrade ninja`

## Don't

 * Run `brew upgrade`, alone without parameters it will upgrade all your kegs!

[![Analytics](https://ga-beacon.appspot.com/UA-49118238-1/leonelgalan/guides/homebrew.md?pixel)](https://github.com/igrigorik/ga-beacon)
