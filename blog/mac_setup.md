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



### Clangd 

- 安装 clangdb：

  sudo apt-get install clangd-9
  
  配置 vscode 的 setting.json，让其找得到 clangd：
  
  ``` json
  "clangd.path": "/usr/lib/llvm-8/bin/clangd",
  ```


- 修改 CMakeLists.txt

  ```cmake
  set(CMAKE_EXPORT_COMPILE_COMMANDS ON CACHE INTERNAL "")
  ```
  
  或者手动生成 compile_commands.json
  
  ```shell
  cd build
  cmake -DCMAKE_EXPORT_COMPILE_COMMANDS=True ..
  ```
  
- vscode 配置 clangd 配置文件：

  shift + command + p: clangd open user configuration file
  
  ``` yaml
  Diagnostics:
    Suppress: type_unsupported
  ```
  
- 配置 clangd 插件 Arguments

  ```json
  --completion-style=detailed
  --compile-commands-dir=${workspaceFolder}/build
  --header-insertion=never
  --query-driver=/opt/homebrew/bin/aarch64-apple-darwin22-g++-12
  ```

- 修改 debug 配置：

  vscode setting.json

  ``` json
  "cmake.debugConfig": {
      "stopAtEntry": false,
      "MIMode": "lldb",
      "miDebuggerPath": "/Users/alchemy/.vscode/extensions/ms-vscode.cpptools-1.14.3-darwin-arm64/debugAdapters/lldb-mi/bin/lldb-mi",
  },
  ```

[vscode + clangd 开发 c\c++](https://blog.csdn.net/weixin_43862847/article/details/119274382)

[最终，我看向了clangd](https://zhuanlan.zhihu.com/p/364518020)

[为 vscode 配置 clangd](https://juejin.cn/post/7126880493668139021)

If you move the clangd binary around, you should also put the builtin headers alongside it.
clangd looks tries to find those relative to its path in ../lib/clang/<version>/include. E.g. if you have clangd version 9 at /opt/bin/clangd, it will look for builtin headers at /opt/lib/clang/9.0.0/include.

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



### Zellij



### Edge

扩展

- Octotree

- Vimium C

  ```
  map K previousTab
  map J nextTab
  ```

- iTab

- JSONVue

- 沙拉查词




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

- 关闭切换输入法 popup

  `sudo defaults write /Library/Preferences/FeatureFlags/Domain/UIKit.plist redesigned_text_cursor -dict-add Enabled -bool NO`
