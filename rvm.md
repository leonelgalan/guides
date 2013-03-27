## Installation

A GCC compiler is needed to compile Ruby. The easiest way to  get it on Mac is to install XCode (App Store). Please read the [documentation](https://rvm.io/os/osx/).

Follow the instructions at [rvm.io/rvm/install](https://rvm.io/rvm/install/).

## Get latest ruby
Update RVM (`rvm get stable`) and find the latest stable ruby 1.9.3 (`rvm list known`, type `:q` to exit), by looking at the patch number just before head:

```
...
[ruby-]1.9.3[-p392]
[ruby-]1.9.3-head
...
```
Or visit [http://www.ruby-lang.org/en/downloads/](http://www.ruby-lang.org/en/downloads/) and find the version that says "Stable (recommended)"

Or get it in a "single command" by typing this in your console:
`curl 'http://ftp.ruby-lang.org/pub/ruby/1.9/' 2> /dev/null | ruby -e 'puts STDIN.lines.map { |x| /1\.9\.3-p\d+\b/.match(x) }.compact.last[0]'`

1.9.3-p392 is the latest at the time of this writing.

```
rvm install 1.9.3-p392
```

## .ruby-version and .ruby-gemset instead of .rvmrc
Recently the use of `.ruby-version` and `.ruby-gemset` is preferred. Using a `.rvmrc` will display a warning. 

Read more about this in [wayneeseguin/rvm#1517](https://github.com/wayneeseguin/rvm/issues/1517).

```
# Replace existing .rvmrc
ruby-1.9.3-p392@rails-app

# With .ruby-version
ruby-1.9.3-p392

# and .ruby-gemset
rails-app
```

## Manually mark a .rvmrc file as trusted
`cd` inside the directory and run `rvm rvmrc trust`. This is useful when a .rvmrc was marked as untrusted previously and RVM remember this decision, so no prompt is shown afterwards.