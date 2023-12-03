## Steps to bootstrap a new Mac

1. Install Apple's Command Line Tools, which are prerequisites for Git and Homebrew.

```zsh
xcode-select --install
```

2. Clone repo into new hidden directory.

```zsh
# Use HTTPS and switch remotes later.
git clone https://github.com/Jak2423/dotfiles.git
```

3. Create symlinks in the Home directory to the real files in the repo.

```zsh
# There are better and less manual ways to do this;
# investigate install scripts and bootstrapping tools.

ln -s ~/.dotfiles/configs/.zshrc ~/.zshrc
ln -s ~/.dotfiles/configs/.gitconfig ~/.gitconfig
ln -s ~/.dotfiles/configs/iterm2/.p10k.zsh ~/.p10k.zsh
ln -s ~/.dotfiles/Wallpapers ~/Wallpapers
ln -s ~/.dotfiles/configs/neofetch ~/.config

ln -s /Users/jak/.dotfiles/configs/vscode/settings.json /Users/jak/Library/Application\ Support/Code/User/settings.json
ln -s /Users/jak/.dotfiles/configs/vscode/keybindings.json /Users/jak/Library/Application\ Support/Code/User/keybindings.json
ln -s /Users/jak/.dotfiles/configs/vscode/snippets/ /Users/jak/Library/Application\ Support/Code/User
```

````


4. Install Homebrew, followed by the software listed in the Brewfile.

```zsh
# These could also be in an install script.

# Install Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Then pass in the Brewfile location...
brew bundle --file ~/.dotfiles/Brewfile

# ...or move to the directory first.
cd ~/.dotfiles && brew bundle
````
