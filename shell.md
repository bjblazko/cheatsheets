# Setup

On macOS, change to ZSH (if not already set):

```bash
chsh -s /bin/zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
git clone https://github.com/powerline/fonts.git --depth=1
cd fonts
./install.sh
cd ..
rm -rf fonts
```

In `~/.zshrc`, change theme to:

```
ZSH_THEME="agnoster"
```

Then, in terminal app (e.g. iTerm2), select font *Meslo LG S DZ Regular for Powerline* (you may have to experiment).

See:

* https://github.com/robbyrussell/oh-my-zsh
* https://github.com/powerline/fonts
