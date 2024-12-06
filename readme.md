[演示与特性](#演示与特性) | [下载安装及用法](#下载安装及用法) | [服务及支持](#服务及支持)

1kdd: 省事一键云虚拟机云容器云桌面云开发pve后端(带镜像有演示)
=====

1kdd是一套学习编程语言的最小实践环境选型方案,并相关管理工具和相关脚本，最终组合实现的一套"一键开发桌面理念"系统存在。   

 * 作为一套"虚拟机管理器"的系统最小核心，基于精简+headless的pve，devdeskos实现了一套in a nutshell的统一透明ve后端。    
 * 作为一套"社交化学习编程"的前端，pveman上整合了社交，及ide（作为pve的developermode存在），及一套学习编程语言的最小实践环境选型方案。    

> 1kdd也指代:1keystokedd,1keydowndd,1keynotedevdesk,1keydevabledocker,1keydiskdump,1keydeepindsm,1keydebiandist,1keydebiandesk,1keydevdeploy,1keydebugdemo,1key desk dock,1key datacenter and desk,1key dir disk,1key deconterized desk,1kilometer distance to dev,1key for dev over dev(second dev),1k dev and deploy in os cases,etc ..

项目地址：[https://github.com/minlearn/1kdd](https://github.com/minlearn/1kdd)

演示与特性✨
-----

onekeydevdesk支持一键dd和构建devdeskos，devdeskos是onekeydevdesk的shell os，作为构建+集成范例存在。支持左栏清爽模式/即时切换暗黑主题/一屏式容器创建向导，集成pbs服务和存储（ 安装演示：[https://www.bilibili.com/video/BV1pr4y1j75w/](https://www.bilibili.com/video/BV1pr4y1j75w/) ）,原生lxc vnc桌面（ 安装演示：[https://www.bilibili.com/video/BV1PV4y1o7f2/](https://www.bilibili.com/video/BV1PV4y1o7f2/) ），512m小内存可安装，支持headless部署和分离式前端pveman ( 安装演示: [https://www.bilibili.com/video/BV1eRt7eTE5A/](https://www.bilibili.com/video/BV1eRt7eTE5A/) )，todo: 可社交分享联合的虚拟机实例，支持docker，集成serverless,支持容器级debugger接入和edtior ide,集成appstore  

![](https://github.com/minlearn/minlearnprogramming/raw/master/_build/assets/devdeskos.png)


下载安装及用法📄
-----

> 注：以下尽量在debian系linux云主机或本地虚拟机下完成,rh系centos/rocky/alma不推荐  

 * 快速恢复模式,指定安装目标os镜像：脚本运行后会重启进入dd过程，进入后，如有网络直接访问ip:80，会看到vnc进度，如果要进一步查看问题访问ip:8000。目标os安装后，会自动扩展磁盘空间和调整网络。（安装演示：[https://www.bilibili.com/video/BV17B4y1b79Y/](https://www.bilibili.com/video/BV17B4y1b79Y/) 和 [https://www.bilibili.com/video/BV1HSndezEaq/](https://www.bilibili.com/video/BV1HSndezEaq/) ） 
```
wget -qO- inst.sh|bash -s - -选项名 选项值          -t 目标值

                          ————————————————————————————————————————————————
   * 指定debian镜像源:     | -m github/gitee/xxxx | -t debian,             | * debian是原生方式
   * 指定第一张网卡名:      | -i enp0s1...         |    debianmu,           |   安装的纯净debian;
   * 指定静态网络配置:      | -n ip/cidr,gateway   |    debiandemu,         | * debianmu是live方式安装的
   * 指定第一个硬盘名:      | -p sda...            |    debianctmu,         |   headless devdeskos+gui devdeskos双启动;
   * 指定用户密码安装:      | -w mypass...         |    dummy,              | * debiandemu是d到本地文件的
   * 指定安装完成动作:      | -o 1/2/3/4           |    或自定gz/xz/qcow2镜像 |   独立桌面版devdeskos
       不扩展磁盘:         |    1:noexpanddisk    |                        | * debianctmu是转换openvz/lxc根文件系统的容器版devdeskos
       不注入网络:         |    2:noinjectnetcfg  |                        | * 自定义镜像是dd方式安装的raw系统硬盘格式经过
       保持不重启:         |    3:noreboot        |                        |   gzip/xz打包后托管的http/https地址;
       不预先清除:         |    4:nopreclean      |                        |   或者qcow2格式的cloudimage托管的http/https地址
   * 指定使用IP6:          |  -6 1                |                        | * dummy是空目标仅供调试模式用
                          ————————————————————————————————————————————————                                             
                          * 以上选项可有可无可组合    * -t必须指定，且唯一
``` 
  
> 恢复完成后的系统，```linux用户名为root密码为inst.sh```，windows保留原包密码。(注意不指定为inst.sh,注意，指定时密码小于6位或8位可能不符合某些os要求会导致失败)   
> 更多第三方dd镜像仓库[《https://inst.sh》](https://minlearn.org/inst/)

 * 开启DEBUG模式，此模式dd时打开一个network-console,且如无网络5分钟后会重启,并进入DD前的正常系统。免破坏系统。可配合dummy目标Dryrun进入救援，也可附在其它target后dd出问题时进入ssh调试  
`wget -qO- inst.sh | bash -s - -d(-t xxx -d)`  

> DEBUG模式下以```用户名为sshd密码为空```登录ssh 

服务及支持👀
-----

项目及项目关联（见文尾），可为分免费部分和服务性收费部分，大部分免费公益性服务，仅对要求作者动手的服务收费，项目和社区维护需要长期付出大量精力，请捐助或付费支持作者：  

如何支持：

 * 本人长期接有偿付费dd含解决疑难机型DD问题和定制镜像服务，价格各60元起，不成功不收费，附加10元可加群：  
`怎么联系: 点击如下作者个人tg地址，简单说明需求或说明来意即可，不要说你好，在吗。直接说事`  
[minlearn_1keydd](https://t.me/minlearn_1keydd)

 * 本人维护有一个tg群和一个内部论坛，直接捐赠打赏60元/10U起加群,可终身免费咨询inst+1kdd技术支持+给discuss提issue+更多不定期福利，你可任意捐助打赏我任意数值虚拟币：  
`怎么捐助/付款: 用支持tron链的钱包或交易所APP扫描下列钱包地址(走链将u转成trx手续费最低，交易所内转0手续)，将支付截图或交易HASH发送到上面tg地址后，等待作者将你tg邀入群和内部社区`  
BINA: [TTdYbcFMBLHSsw9yrrdRn8jMAFFC7U4Byp](https://tronscan.io/#/address/TTdYbcFMBLHSsw9yrrdRn8jMAFFC7U4Byp)，内部id：878248518  
OKEX: [TPvrETkN21H8fagFjyYAECihyRhrRAMCTR](https://tronscan.io/#/address/TPvrETkN21H8fagFjyYAECihyRhrRAMCTR)，内部id：292251340602744832  
![](https://github.com/minlearn/minlearnprogramming/raw/master/_build/assets/donate.png)

* 项目买断
`10000u = inst+1kdd+discuss全套ci构建源码, 全部协助转让`

-----

此项目关联 https://github.com/minlearn/ 下所有项目，主体为 https://github.com/minlearn/minlearnprogramming/ 和 https://github.com/minlearn/1kdd ，这是一套为配合我在《minlearnprogramming》最小编程/统一开发的想法的综合项目。  
本项目长期保存

