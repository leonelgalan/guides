## Installation
Let's go the easy way, install [Homebrew](homebrew.md) first!

```sh
brew update
brew doctor

brew install rbenv
brew install ruby-build
```

### Upgrades?
```sh
brew update
brew doctor

brew upgrade rbenv
brew upgrade ruby-build
```

## Get latest ruby
Visit [http://www.ruby-lang.org/en/downloads/](http://www.ruby-lang.org/en/downloads/) and find the version that says "Stable (recommended)"

Or get it in a "single command" by typing this in your console:
```sh
curl 'http://ftp.ruby-lang.org/pub/ruby/2.0/' 2> /dev/null | ruby -e 'puts STDIN.each_line.map { |x| /2\.0\.0-p\d+\b/.match(x) }.compact.last[0]'
```

2.0.0-p247 is the latest at the time of this writing.

```sh
rbenv install 2.0.0-p247
```

## Usage
### rehash, I'm not even sure why!
**After `gem install ...` or `bundle`**

```sh
rbenv rehash
```

### Set a global version
```sh
rbenv global 2.0.0-p247
```

### Set a version, per project
```sh
cd project_name

rbenv local 2.0.0-p247
```

[![Analytics](https://ga-beacon.appspot.com/UA-49118238-1/leonelgalan/guides/rbenv.md?pixel)](https://github.com/igrigorik/ga-beacon)
