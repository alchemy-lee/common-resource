# Mac 配置

### ClashX Pro - Proxy

[Download ClashX Pro](https://install.appcenter.ms/users/clashx/apps/clashx-pro/distribution_groups/public)

``` shell
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```



### Warp - Terminal

[Download Warp](https://www.warp.dev/)



### Homebrew - Package Manager 

[Install Homebrew](https://mirrors.tuna.tsinghua.edu.cn/help/homebrew/)



### Fig - Shell Autocomplete

[Download Fig](https://fig.io/)



### Tmux

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

[Tmux 配置解析](https://www.bilibili.com/video/BV1kT411S7GL)



### Oh My Posh - Prompt

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



### Raycast - Launcher

[Download Raycast](https://www.raycast.com/)



### Rime - Input Method

[Download Rime](https://github.com/ssnhd/rime)

[Rime Squirrel 鼠须管输入法配置详解](https://ssnhd.com/2022/01/06/rime/)

- `default.custom.yaml`

  ``` yaml
  patch:
    ascii_composer:
        good_old_caps_lock: false # 若为 true， Caps 只切换大小写
        switch_key:
          Caps_Lock: commit_code # Caps 键
          Shift_L: noop # 左 Shift，屏蔽该切换键
          Shift_R: noop # 右 Shift，屏蔽该切换键
          Control_L: noop # 左 Control，屏蔽该切换键
          Control_R: noop # 右 Control，屏蔽该切换键
  ```
  
- `luna_pinyin_simp.custom.yaml`

  ``` yaml
  patch:
    switches:
      - name: ascii_mode # 0 中文，1 英文
        reset: 0
        states: ["中文", "英文"]
  ```
  
- `squirrel.custom.yaml`
  
  ``` yaml
  patch:
  	app_options:    
      com.apple.Spotlight:             # 聚焦搜索
          ascii_mode: true             # true默认英文,false默认中文
      com.runningwithcrayons.Alfred:   # alfred
          ascii_mode: true
      com.tencent.Lemon:               # 腾讯柠檬
          ascii_mode: true
      com.apple.dt.Xcode:              # Xcode
          ascii_mode: true
      com.apple.Terminal:              # 终端
          ascii_mode: true
          vim_mode: true
      com.googlecode.iterm2:
          ascii_mode: true
          vim_mode: true
      com.microsoft.VSCode:            # Visual Studio Code
          ascii_mode: true
          vim_mode: true
      md.obsidian:
          ascii_mode: true
          vim_mode: true
      dev.warp.Warp-Stable:
          ascii_mode: true
          vim_mode: true
      com.raycast.macos:
          ascii_mode: true
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

