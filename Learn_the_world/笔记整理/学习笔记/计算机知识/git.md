情景：通过git实现obsidain笔记多端互通
思路：将存储obsidian文件的文件夹设为git仓库

问题1:  想用脚本实现add commit pull push一条龙，但是要用不同的commit名称标记不同电脑的修改
解决1: 使用.gitignore将特定文件不上传

问题2: .gitignore文件需要在commit之前使用，否则本地有缓存.gitignore文件无法生效
解决2：一开始听信博客说删掉.git文件夹（引出第三个问题）
实则应该使用git rm --cached先在版本控制中移除需要忽视的文件
https://www.cnblogs.com/lovebing/p/17934843.html

问题3:删除.git之后如何重建远程仓库
解决3: 进入仓库
```
git init
git remote 仓库名称 URL
```
感觉git remote这一步其实是修改了.git文件夹中的config文件，因此怀疑可以直接修改config文件实现

问题4:两台设备会出现同时修改一个文件的情况（比如.obsidian配置文件，这个文件大概率必须同步，而且浏览记录会修改这个文件，意即只浏览也可能带来冲突情况）

设想解决方案1: 每次跨平台使用前后必须进行pull和push（麻烦琐碎，不好自动化
设想解决方案2:push时完全覆盖云端