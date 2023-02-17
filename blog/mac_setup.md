# Mac 配置

### 00. ClashX Pro - Proxy

[Download ClashX Pro](https://install.appcenter.ms/users/clashx/apps/clashx-pro/distribution_groups/public)



### 01. Warp - Terminal

[Download Warp](https://www.warp.dev/)



### 02. Fig - Shell autocomplete

[Download Fig](https://fig.io/)



### 03. Tmux

- [Install tmux](https://github.com/tmux/tmux/wiki/Installing)

- config file: `~/.tmux.conf` 

- [Install TPM (Tmux Plugin Manager)](https://github.com/tmux-plugins/tpm)：

  - ```shell
    git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
    ```
  - Reload Tmux environment
    ```shel
    tmux source ~/.tmux.conf
    ```

[tmux-tutorial](https://github.com/bryant-video/tmux-tutorial)

[Tmux入门指南](https://cloud.tencent.com/developer/article/1095535)



### 04. Oh My Posh - Prompt

- [Install Oh My Posh](https://ohmyposh.dev/docs/installation/macos)

  ``` sh
  brew install jandedobbeleer/oh-my-posh/oh-my-posh
  ```

- Install Hack Nerd Font

  ```sh
  brew tap homebrew/cask-fonts && brew install --cask font-hack-nerd-font
  ```

- Config Oh My Posh: modify `~/.zshrc`

  ```sh
  # oh my posh promt
  OMP_THEME="gruvbox"
  eval "$(oh-my-posh init zsh --config /opt/homebrew/opt/oh-my-posh/themes/$OMP_THEME.omp.json)"
  ```
  
- Reboot `zsh`

  ```sh
  exec zsh
  ```



### Mac 设置

- 修改用户名、个人目录

  用户与群组 -> 右键 -> 高级选项

- [Mac 原生词典扩展词库](https://blog.csdn.net/qq_36239671/article/details/125226531)
  - `pip3 install lxml beautifulsoup4 html5lib`
  
  - [Install Additional Tools for Xcode](https://developer.apple.com/download/all/)，在此界面搜索 Additional Tools for Xcode，将 .dmg 中 Utilities 中的 Dictionary Development Kit 拖拽提取到 /Applications/Utilities/
  
  - [Download pyglossary code](https://github.com/ilius/pyglossary)
  
  - ```shell
    cd ~/Documents/牛津第九版/
    python3 ~/codes/pyglossary/main.py --write-format=AppleDict --write-options=css=~/Documents/牛津第九版/oalecd9.css ~/Documents/牛津第九版/牛津高阶双解\(第9版\)_V3.1.2版.mdx ~/Documents/oxford
    cd ~/Documents/oxford
    make
    make install
    ```

