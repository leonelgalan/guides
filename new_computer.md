## Bash
```bash
;: Install Xcode
;: Install Command Line Tools
xcode-select —-install
;: Open and close Xcode
;: Install OH-MY-ZSH
curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh
```

## Zsh
```bash
;: Install Homebrew
ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"
;: Add ~/bin and /usr/local/bin before /usr/bin on path in ~/.zshrc
;: export PATH=~/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin

;: Install rbenv
brew install rbenv
;: Add rbenv initialization to .zshrc
echo 'if which rbenv > /dev/null; then eval "$(rbenv init - zsh)"; fi' >> ~/.zshrc
source ~/.zshrc
;: Install ruby-build
brew install ruby-build
;: Install Ruby 2.0.0 and Update gems
rbenv install 2.0.0-p247
rbenv global 2.0.0-p247
rbenv shell 2.0.0-p247
gem update --system

;: Update Git
brew install git
;: Setup Git
echo ".DS_Store" >> ~/.gitignore
git config --global core.excludesfile ~/.gitignore
git config --global user.email "leonelgalan@gmail.com"
git config --global user.name "Leonel Galan"
;: Setup Github
;: Generate Key
mkdir ~/.ssh
cd ~/.ssh
ssh-keygen -t rsa -C "leonelgalan@gmail.com"
ssh-add id_rsa
;: Copy/Paste Key on Github Settings
pbcopy < ~/.ssh/id_rsa.pub
;: Test Settings
ssh -T git@github.com

;: Setup Gems
echo "gem: --no-ri --no-rdoc" >> ~/.gemrc
;: Install Gems
gem install hub
gem install bundler


;: Install Casks
brew tap phinze/homebrew-cask
brew install brew-cask
brew cask install iterm2
brew cask install alfred
;: Read https://github.com/phinze/homebrew-cask/blob/master/USAGE.md#alfred-integration
brew cask install mou  
brew cask install spotify
brew cask install sublime-text-3
;: Set `subl` command line
mkdir ~/bin
ln -s ~/Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl ~/bin/subl
;: Install Package Control https://sublime.wbond.net/installation#st3
brew cask install dropbox
brew cask install github
brew cask install google-chrome
brew cask install harvest
brew cask install bartender
brew cask install grand-perspective
brew cask install silverlight
;: Paid license works through the App Store
;: brew cask install sparrow
brew cask install spectacle
brew cask search drive
brew cask install google-drive
brew cask install hangout
brew cask install google-hangout
brew cask install brightness
brew cask install skype
brew cask install hall

;: Install Tools
brew install heroku-toolbelt
brew install imagemagick
brew install postgres
initdb /usr/local/var/postgres -E utf8
```

[![Analytics](https://ga-beacon.appspot.com/UA-49118238-1/leonelgalan/guides/new_computer.md?pixel)](https://github.com/igrigorik/ga-beacon)
