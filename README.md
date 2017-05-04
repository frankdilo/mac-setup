# Mac Setup

Scripts to setup new macs.



## Install [Homebrew](https://brew.sh/) and [Cask](https://caskroom.github.io/)

```sh
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" && brew tap caskroom/cask
```

This will also download the Command Line Tools (`git`, etc.)



## Clone this repo

```sh
mkdir projects
cd projects
git clone https://github.com/frankdilo/mac-setup.git && cd mac-setup
```



## Install casks

```sh
while read app; do
  brew cask install "$app"
done < homebrew-cask/basic.txt
```



```sh
# Remove downloaded files and cleanup space
brew cask cleanup
```



## Install Mac App Store apps

```sh
brew install mas # cli for the mac app store
```

```sh
while read app_id; do
  mas install $app_id
done < echo $(grep -o '^[^#]*' mas/basic.txt | grep -v '^$')
```

