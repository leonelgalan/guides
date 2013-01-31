## Installation

Follow the instructions at [rvm.io/rvm/install](https://rvm.io/rvm/install/)

## Get latest ruby
Update RVM (`rvm get stable`) and find the latest stable ruby (`rvm list known`), by looking at the patch number just before head:

```
...
[ruby-]1.9.3[-p374]
[ruby-]1.9.3-head
...
```
Or visit [http://www.ruby-lang.org/en/downloads/](http://www.ruby-lang.org/en/downloads/) and find the version that says "Stable (recommended)"

1.9.3-p374 is the latest at the time of this writing.

## Manually mark a .rvmrc file as trusted
`cd` inside the directory and run `rvm rvmrc trust`. This is useful when a .rvmrc was marked as untrusted previously and RVM remember this decision, so no prompt is shown afterwards.