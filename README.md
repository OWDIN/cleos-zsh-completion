# cleos-zsh-completion
> Additional completion definitions for Cleos. Complete your cleos with zsh completion! :tada:

<p align="center">
  <img src="demo.gif" alt="Demo" />
</p>


**cleos-zsh-completion** is additional completion for cleos. It provides the short description about each command and auto-complete with your tab/arrow keys.

Use cleos with your <kbd>tab</kbd> key or <kbd>↑</kbd> <kbd>↓</kbd> arrow keys. :relaxed:

## How to Install

1. Install **zsh** and **[zsh-completions](https://github.com/zsh-users/zsh-completions)**
2. Install cleos-zsh-completion
3. Reload

You can use it with **zsh** and **[zsh-completions](https://github.com/zsh-users/zsh-completions)**.

If you're already use [Oh My Zsh](https://ohmyz.sh/) and [zsh-completions](https://github.com/zsh-users/zsh-completions), try below:

```bash
curl -fLo ~/.oh-my-zsh/custom/plugins/zsh-completions/src/_cleos https://raw.githubusercontent.com/OWDIN/cleos-zsh-completion/master/_cleos
```

If not, Install [Oh My Zsh](https://ohmyz.sh/) and [zsh-completions](https://github.com/zsh-users/zsh-completions).

```bash
# Install oh-my-zsh
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

# Install zsh-completions
git clone https://github.com/zsh-users/zsh-completions ~/.oh-my-zsh/custom/plugins/zsh-completions
```

You should configure [zsh-completions](https://github.com/zsh-users/zsh-completions).

If you're not familiar with zsh, just type below:

```bash
# Configuration for newbie.
# If you already use zsh, check https://github.com/zsh-users/zsh-completions#oh-my-zsh
echo "plugins=(zsh-completions)" >> $HOME/.zshrc
echo "autoload -U compinit && compinit" >> $HOME/.zshrc
echo "fpath=($HOME/.oh-my-zsh/src $fpath)" >> $HOME/.zshrc
```

Download cleos completion and reload it. Done!

```bash
# Download cleos completion
curl -fLo ~/.oh-my-zsh/custom/plugins/zsh-completions/src/_cleos https://raw.githubusercontent.com/OWDIN/cleos-zsh-completion/master/_cleos

# Reload shell
source $HOME/.zshrc
```

If you want to see full version of configuration, check [my dotfiles](https://github.com/channprj/dotfiles-macOS).

## Recommanded Configuration
You should add below options for help messages. If not, you cannot see yellow help messages. If you don't want to see yellow extra help message, remove `zstyle ':completion:*:messages' format $'\e[00;33m%d'` options.

```bash
# Add this in .zshrc
zstyle ':completion:*' verbose yes
zstyle ':completion:*' group-name ''
zstyle ':completion:*:descriptions' format $'\e[00;32m%d'
zstyle ':completion:*:messages' format $'\e[00;33m%d'
zstyle ':completion:*:manuals' separate-sections true
```

If you're not familiar with zsh, just type below:

```bash
# for newbie
echo "zstyle ':completion:*' verbose yes" >> $HOME/.zshrc
echo "zstyle ':completion:*' group-name ''" >> $HOME/.zshrc
echo "zstyle ':completion:*:descriptions' format $'\e[00;32m%d'" >> $HOME/.zshrc
echo "zstyle ':completion:*:messages' format $'\e[00;33m%d'" >> $HOME/.zshrc
echo "zstyle ':completion:*:manuals' separate-sections true" >> $HOME/.zshrc
```


## Use with customized cleos
If you're use customized cleos like **cleos_docker**, edit **_cleos** first line like below:

```diff
- #compdef cleos
+ #compdef cleos cleos_docker=cleos
```

..or You can also use without edit file like below:

```bash
compdef _cleos cleos cleos2 cleos3
```

## Authors
- CHANN - [@channprj](https://github.com/channprj)

## License
This project is licensed under the MIT License. See [LICENSE](LICENSE) for more detail.

## Reference
- [EOS.io - Cleos Overview](https://developers.eos.io/eosio-nodeos/docs/cleos-overview)
- [ZSH - Completion System](http://zsh.sourceforge.net/Doc/Release/Completion-System.html)
- `man zshcompsys`
