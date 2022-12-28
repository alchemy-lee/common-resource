# 在 Warp 中使用 Oh My Posh

### 安装 Oh My Posh

``` sh
brew install jandedobbeleer/oh-my-posh/oh-my-posh
```

[macOS | Oh My Posh](https://ohmyposh.dev/docs/installation/macos)



### 安装字体 Hack Nerd Font

```sh
brew tap homebrew/cask-fonts && brew install --cask font-hack-nerd-font
```



### 配置 Oh My Posh

修改 `.zshrc`

```sh
# oh my posh promt
OMP_THEME="gruvbox"
eval "$(oh-my-posh init zsh --config /opt/homebrew/opt/oh-my-posh/themes/$OMP_THEME.omp.json)"
```

重启 `zsh`

```sh
exec zsh
```



