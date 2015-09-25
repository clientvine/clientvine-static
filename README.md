# Clinevine-Static
A static site starter template for Clienvine projects using [Middleman](https://middlemanapp.com/) with [Bower](http://bower.io/) for dependency managment.

## Dependencies
### Homebrew

If Homebrew isn't already installed...
```shell
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Otherwise update homebrew
```shell
brew update
```

### rbenv
```shell
brew install rbenv ruby-build
```
If you're using bash...
```shell
echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
```
If you're using zsh...
```shell
echo 'eval "$(rbenv init -)"' >> ~/.zshrc
```

### Nodejs
```shell
brew install node
```

### Bower
```shell
npm install -g bower
```

## Setting up each new site
Clone the repository
```shell
git clone git@github.com:clientvine/clientvine-static.git
```
Install the version of ruby specified in the ruby-version file
```shell
rbenv install `echo .ruby-version`
```

Get the required libraries...
```shell
gem install bundler
bundle
bower install
```

## Developing
Start a development server:
```shell
middleman server
```
Open [http://localhost:4567](http://localhost:4567)

## Deploying
Build the site
```shell
middleman build
```
Now the production files will be located in the build folder.

(optional)
install gsutil
```shell
pip install gsutil
gsutil config
```
configuration and instructions stored in ~/.boto
[reference google cloud docs](https://cloud.google.com/storage/docs/gsutil/commands/rsync)

```shell
gsutil -m rsync -d -r ./build gs://www.bucketname.com
```

