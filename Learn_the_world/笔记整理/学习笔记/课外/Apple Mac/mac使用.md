# 一、终端美化
https://www.bilibili.com/video/BV1miWMe9Esq/?spm_id_from=333.1007.top_right_bar_window_history.content.click&vd_source=8021a8ee85ea0173334af43af38ab97b
前置：HomeBrew
方法一：使用官网提供.pkg安装
问题1：缺少前置CLT

问题2:安装CLT之后再次尝试安装，brew -v发现没装上，但是系统路径/opt/homebrew已经存在文件
参考链接：[https://blog.csdn.net/qq_38984332/article/details/137746375]
解决2：跟随操作完成后重启终端

附：echo $PATH查看zsh环境变量

方法二：使用官网提供命令安装
报错：没法链接GitHub仓库（已经挂了梯子）
但是好在装上了CLT


**Westerm+Starship**
1.安装Western：一个新终端
`brew install --cask wezterm`
新建配置文件
`mkdir -p .config/wezterm`
创建 westerm.lua
`touch .config/wezterm/wezterm.lua`
进入  .config/wezterm，编辑wezterm.lua

# 二、github设置
默认已安装git

参考博客：
https://blog.csdn.net/qyqyqyi/article/details/128652728