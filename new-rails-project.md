## Commands only

`Replace `**`project-name`**` with the project name in lowercase and without spaces`

```
mkdir project-name

rvm get stable ;: Update RVM
rvm list known ;: ruby-1.9.3-p374 is the latest at the time of this writing

;: Exit by typing :q (colon and quit)

tee -a project-name/.rvmrc <<EOF
rvm use --create --install 1.9.3-p374@project-name
EOF

cd project-name

;: Press y on your keyboard when prompted

gem install rails
rails new . -T -d postgresql 
bundle
rails s ;: Test run, just to make sure everything is running

;: Press Ctrl+c to close the server

git init
wget https://raw.github.com/github/gitignore/master/Rails.gitignore -O .gitignore
git add .
git commit -m "Initial commit"
```

## Long version

*	Create your project's new directory: `mkdir project-name` (make directory)
*	Find the latest ruby version at [ruby-lang.org](http://www.ruby-lang.org/en/downloads/) or by updating [RVM](rvm.md) and getting the latest known list: `rvm get stable && rvm list known` (Type _`:q`_ to exit). At the time of this writing: ruby 1.9.3-p374
*	Create a .rvmrc file in the newly created directory. This will (1) install "ruby-1.9.3-p374" if necessary, (2) create the gemset "project-name" if necessary and (3) select this gemset when `cd project-name` (change directory). **TIP**: You can always 	know what ruby/gemset is being used by typing `rvm current`.
	
```
tee -a project-name/.rvmrc <<EOF
rvm use --create --install 1.9.3-p374@project-name
EOF
```

*	Open the project's directory: `cd project-name`. The first time you `cd` inside a folder after the ".rvmrc" file has been changed you will have to accept the changes. Type: _`[y]`_ when prompted.
*	Install Ruby on Rails: `gem install rails`
*	Create a new Ruby on Rails project: `rails new . -d postgresql`
*	Type `bundle`
*	Run `rails s` once and visit _http://localhost:3000_ on your browser, if you see the "Welcome aboard" page, you are doing everything right.
*	Kill the server: _`[Control + c]`_
*	Initialize/start a new git repository: `git init`
*	Replace the contents of .gitignore with the contents of [Rails.gitignore](https://raw.github.com/github/gitignore/master/Rails.gitignore): `wget https://raw.github.com/github/gitignore/master/Rails.gitignore -O .gitignore`
*	Add all the files to the commit: `git add .`. This is the _LAST TIME_ we are using this command, forget it now. From know on, you will only add specific files to each commit.
*	Commit the initial commit: `git commit -m "Initial Commit"`

## Cleanup and final setup

**No skipping in this section, everything is important**

Will remove unnecessary comments, lock the Gemfile with the [pessimistic version constraint](http://docs.rubygems.org/read/chapter/16#page74).

### Gemfile
*	Remove all comments/examples
*	Lock the "pg" gem's version:

```
gem 'pg', '~> 0.14.1'
```
* Add "foreman" and "thin":

```
gem 'foreman', '~> 0.61'
gem 'thin', '~> 1.5.0'
```
*	Create a "Procfile": `echo "web: bundle exec rails server thin -p $PORT -e $RACK_ENV" >> Procfile`
*	Make "development" your default $RACK_ENV and 3000 your default port. Type `echo "RACK_ENV=development\nPORT=3000" >>.env`
*	Load ".env" in the current session: `source .env`
*	Execute `bundle`
*	Test your setup, run `foreman start` and visit _http://localhost:3000_ in your browser. As usual, kill the server by typing `[Control + c]`
*	Commit your changes: `git add Gemfile Gemfile.lock config/routes.rb Procfile .env` and `git commit -m "Gemfile and routes.rb cleanup, Foreman and Thin"`

### Routes
*	Remove all comments/examples except:

```
  #   resources :products
```

```
  # root :to => 'welcome#index'
```

*	Replace `root :to => 'welcome#index'` for `root to: 'welcome#index'`, it is the nicer (ruby 1.9.x) syntax will be using.
*	Commit: `git add config/routes.rb` and `git commit -m "Routes cleanup"`
