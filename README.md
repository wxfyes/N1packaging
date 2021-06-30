# 重要更新
```diff
 N1已支持一键在线升级openwrt和内核！升级方式见下方，目前已经实现同X86固件同样的web升级方式！更加简单快捷！
```
2021年6月18日，上游大雕全面更新了最新代码，受影响，60+或60+o版本升级61版本的，建议重新安装，如果不想刷U盘全新安装，也可以用升级脚本升级，只是选择是否保存配置时，选“n”

很多人喜欢升级用ipk，这里不推荐大家使用，原因会出现不同未知BUG！强烈建议大家用更新固件的方式进行升级~ 故此，暂不开放ipk编译项目~这完全是为了大家好~

2021年5月24日，同步更新F大佬的快照功能
![增加快照功能](https://cdn.jsdelivr.net/gh/wxfyes/N1packaging/img/kuazhao.jpg)

使用方法：固件新刷入或采用新版的 update-xxx-openwrt.sh 脚本升级之后就具备了快照功能，工具包名称：由于取名困难，故采用了 flippy 为命令名称（/usr/sbin/flippy)，在ssh或ttyd下输入即可，全程中文菜单，全交互式操作。
# 特别提醒
不要盲目追新，仓库自动打包的固件或插件，均为最新的版本，最新版本意味着有BUG；如果之前固件使用稳定，无需追新。
总结一句话：**追新有风险、更新须谨慎**

# +和+o的版本区别
* +的内核版本较新；
* +o的版本相对+的内核更稳定；
* f大不太建议N1等盒子使用+的版本，因此比较推荐使用+o的版本。


此项目基于flippy的56+o打包N1和s905X3 （hk1等）贝壳云的openwrt，为王晓峰个人正在使用的固件版本。openwrt来自我的另一个项目[N1Openwrt](https://github.com/wxfyes/N1openwrt)

# 默认IP及密码
默认IP 192.168.1.1  密码 password

# N1全新安装
* 下载对应版本固件
![固件链接地址](https://cdn.jsdelivr.net/gh/wxfyes/N1packaging/img/3.png)
* 将固件写入U盘或TF卡 推荐写盘软件 [rufu](https://rufus.ie/zh/)或者[balenaEtcher](https://github.com/wxfyes/cf/releases)任选其一
* 插入U盘启动盒子，输入192.168.1.1进入后台
* 在系统——TTYD终端——输入用户名root；密码password
* 输入安装命令 `./install-to-emmc.sh`
* 如果显示挂载失败，重新执行上述安装命令`./install-to-emmc.sh`

# N1web在线升级方法
* web在线快速升级，以此进入系统-晶晨宝盒-选择手动上传更新-上传最新下载的N1固件，最后点击升级openwrt固件即可
* ![升级方法](https://cdn.jsdelivr.net/gh/wxfyes/N1packaging/img/sj.png)
# N1 ssh后台升级法（较麻烦）
* cd /mnt/mmcblk2p4
* wget 升级脚本下载.sh后缀文件 [点这里跳转](https://github.com/wxfyes/N1packaging/releases)
![固件链接地址](https://cdn.jsdelivr.net/gh/wxfyes/N1packaging/img/2.png)
* wget .gz后缀名的固件链接,鼠标右击后缀.gz文件获取链接地址 [点这里跳转](https://github.com/wxfyes/N1packaging/releases)
* gzip -d 上一步下载的固件全名
* chmod +x *.sh
* ./升级脚本名字 img固件名

# 插件包括
![插件列表](https://cdn.jsdelivr.net/gh/wxfyes/x86openwrt/img/l.png)
![插件列表](https://cdn.jsdelivr.net/gh/wxfyes/x86openwrt/img/2.png)
![插件列表](https://cdn.jsdelivr.net/gh/wxfyes/x86openwrt/img/3.png)
![插件列表](https://cdn.jsdelivr.net/gh/wxfyes/x86openwrt/img/4.png)
![插件列表](https://cdn.jsdelivr.net/gh/wxfyes/x86openwrt/img/5.png)
![插件列表](https://cdn.jsdelivr.net/gh/wxfyes/x86openwrt/img/6.png)
* SSR-Plus
* passwall
* openclash
* hello word
* Bypass
* Argon主題 
* docker-ce
* dockerman
* 晶晨宝盒（web升级）
* AdGuard Home
* smartdns
* 实时监控
* TTYD终端
* 动态DNS
* UPdp
* 网易音乐解锁
* 京东薅羊毛
* Frp内网穿透
* Frps
* 无线wifi
* CPU性能调节
* sfe加速
* Flow加速
* 多线多播
* 可道云
* transmission
* NFS管理
* qBittorrent

# 自动更新说明
固件采用自动编译，Acrions将会在每天监控上游代码是否更新，如passwall ssrp等，一旦检测到上游代码更加将会自动编译打包，于每天上午7时30分发布最新版固件。

# N1新版固件如何刷

非54+o版升级到55+o版，如果一直卡在fdisk失败那里的解决办法：一是再多试几次，如果还不成功，则需要手动清空分区表然后再重试，具体命令:
```
  dd   if=/dev/zero   of=/dev/mmcblk2  bs=512  count=1  &&  sync
```

# [购买奈飞正规合租车](https://wxf2088.ml/Netfix)

# 感谢
 * [flippy](https://github.com/unifreq)提供内核
 * [coolsnowwolf/Lede](https://github.com/coolsnowwolf/lede)提供源码
 * [mingxiaoyu](https://github.com/mingxiaoyu)提供自动编译脚本
 * [hibuddies](https://github.com/hibuddies/openwrt/)提供源码
