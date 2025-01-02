目标：利用mac强单核实现服务端挂载，再用服务器/zeroteir实现内网穿透or异地局域网
流程->客户端制作+分发->基于客户端使用serverpackcreator制作服务端+修改properties


## 1. mod服务端制作
软件：serverpackcreator（跨平台

## 2.win上整合包相关资源下载失败，使用管理员权限运行启动器解决

## 3.invalid session
关闭正版验证：server.properties 文件中修改online mode为false

## 4.地图替换
https://aibofan.com/minecraft-server-side-directory-structure-configuration-file-description-and-common-instructions/
官方文档
https://manuals.plus/games/skyfactory-4-multiplayer-instructions

## 5.出生点保护取消
spawn-protection=0


## 6.
zerotire
tailsacle

# 1.20.1原版增强
选用模组较多的1.20.1
模组列表：
	JEI
	ModernFix
	Journeymap
	Sound physics
	better animationså
光影
	性能（负载）：
	compelement=photon>makeup>lite


## 使用说明：
1.解压该压缩包，HMCL-3.6.11.jar是启动器(win推荐使用自己的启动器)。
```
解压文件夹目录：
Better_Classic_1.20.1.zip
server_address.txt（服务器地址）
HMCL-3.6.11.jar
```
2.双击打开启动器，点击左下角 版本列表->安装整合包- >导入本地整合包文件->选择当前目录下的Better_Classic_1.20.1.zip->点击 安装
3.设置“离线模式”账户，启动游戏

光影
	效果（负载）：
	compelement=photon>makeup>lite





遇到问题：hmcl打包的整合包无法导入
其实用HMCL的.minecraft 文件夹中的内容即可
https://www.bilibili.com/video/BV1Ei421R7D5?spm_id_from=333.788.recommend_more_video.0&vd_source=8021a8ee85ea0173334af43af38ab97b
需要设置variable.txt中的java路径


EULA


 ```dataviewjs // PS. remove backslash \ at the very beginning!

dv.span("** 😊 Title  😥**") /* optional ⏹️💤⚡⚠🧩↑↓⏳📔💾📁📝🔄📝🔀⌨️🕸️📅🔍✨ */
const calendarData = {
	year: 2022,  // (optional) defaults to current year
	colors: {    // (optional) defaults to green
		blue:        ["#8cb9ff", "#69a3ff", "#428bff", "#1872ff", "#0058e2"], // first entry is considered default if supplied
		green:       ["#c6e48b", "#7bc96f", "#49af5d", "#2e8840", "#196127"],
		red:         ["#ff9e82", "#ff7b55", "#ff4d1a", "#e73400", "#bd2a00"],
		orange:      ["#ffa244", "#fd7f00", "#dd6f00", "#bf6000", "#9b4e00"],
		pink:        ["#ff96cb", "#ff70b8", "#ff3a9d", "#ee0077", "#c30062"],
		orangeToRed: ["#ffdf04", "#ffbe04", "#ff9a03", "#ff6d02", "#ff2c01"]
	},
	showCurrentDayBorder: true, // (optional) defaults to true
	defaultEntryIntensity: 4,   // (optional) defaults to 4
	intensityScaleStart: 10,    // (optional) defaults to lowest value passed to entries.intensity
	intensityScaleEnd: 100,     // (optional) defaults to highest value passed to entries.intensity
	entries: [],                // (required) populated in the DataviewJS loop below
}

//DataviewJS loop
for (let page of dv.pages('"daily notes"').where(p => p.exercise)) {
	//dv.span("<br>" + page.file.name) // uncomment for troubleshooting
	calendarData.entries.push({
		date: page.file.name,     // (required) Format YYYY-MM-DD
		intensity: page.exercise, // (required) the data you want to track, will map color intensities automatically
		content: "🏋️",           // (optional) Add text to the date cell
		color: "orange",          // (optional) Reference from *calendarData.colors*. If no color is supplied; colors[0] is used
	})
}

renderHeatmapCalendar(this.container, calendarData)

```