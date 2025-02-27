<div align="center">

# nessus docker 破解版

<br>

<a href="https://twitter.com/Elliot58616851" target="_blank"><img src="https://img.shields.io/twitter/follow/Elliot58616851?style=social"> </a>

<div>
    <img alt="platform" src="https://img.shields.io/badge/platform-Docker%20%7C%20DockerFile-blueviolet">
</div>
<div>
    <img alt="license" src="https://img.shields.io/github/license/elliot-bia/nessus?logo=1">
    <img alt="stars" src="https://img.shields.io/github/stars/elliot-bia/nessus?style=social">
</div>
<br>

[🇨🇳简体中文](./README-cn.md) | [🇺🇸English](./README.md) | [🇩🇪Deutsch](./README-de.md)


此项目仅供非营利性学习研究，请勿用作非法用途，如有侵权请及时联系删除

</div>




# 用法/Usage
`docker run -itd --name=ramisec_nessus -p 8834:8834 ramisec/nessus`  (只有 497MB !!!)  
就是这么简单! 但是需要下面一行代码更新插件🤣，（如果要保留数据，先创建`~/nessus_data`文件夹）


# 更新
`docker exec -it ramisec_nessus /bin/bash  -c "/nessus/update.sh UPDATE_URL_YOU_GOT"`
这个 **UPDATE_URL_YOU_GOT** 更新url需要先从 [官网](https://tenable.com/products/nessus/nessus-essentials) 申请一个激活码 **an activation-code**，然后再从这个 [网站](https://plugins.nessus.org/v2/offline.php)生成URL
举个栗子:

<img width="544" alt="image" src="https://github.com/elliot-bia/nessus/assets/40572216/0a821a76-060c-4b51-a1a4-f95bd56e2556">

任意机器码格式`aaaaaa11b2222cc33d44e5f6666a777b8cc99912` 都可以，但是不要跟别人相同

然后就生成了 **UPDATE_URL_YOU_GOT**

<img width="540" alt="image" src="https://github.com/elliot-bia/nessus/assets/40572216/486988b6-352e-4d8e-9910-1308c50bc053">

__提醒__  
如果你无法更新成功，请检查网络连接  

# 迁移

如果想要进行旧版本数据迁移，请进行以下操作

```bash
# 创建目录
mkdir ~/nessus_data
# 停止容器
docker stop ramisec_nessus
# 拷贝数据
docker cp ramisec_nessus:/opt/nessus/var/nessus/ ~/nessus_data
# 删除旧容器
docker rm ramisec_nessus
# 开新容器
docker run -itd --name=ramisec_nessus -v ~/nessus_data/nessus/:/opt/nessus/var/nessus/ -p 8834:8834 ramisec/nessus
# 更新插件
docker exec -it ramisec_nessus /bin/bash /nessus/update.sh

```

# 账号密码
account：admin  
password： 每个版本密码就是一个彩蛋！ Easter egg！CHECK the Change Version   
让大家探索一下，避免伸手党，如果解出了密码，自己用就好，不要公开哟😉  

# 说明/Readme
这个破解原本是自用的，也没打算公开出来    
但是昨天在使用fahai破解版awvs的时候，看到了这么一句话：  
`Thank's fahai && Open Source Enthusiast `  
 <img src="https://user-images.githubusercontent.com/40572216/174698816-440d4969-f9d6-4c7d-982c-9af9c4a3e875.png" width = "400" height = "200" alt="图片名称" align=center />

于是我就在思考，我用了那么多开源项目，那我又做出了多少贡献？    
索性将此项目公开，也算为网安做一点贡献    
如果没有意外，会持续更新，毕竟我也要用    
~~就不把自动更新插件版本弄出来了，先用着吧！~~  
已更新！（20220722）


# 更新日志

## v5 20231218

- 修改破解失效问题
- 增加openjdk-8-jdk

##  v4 20230523

- 修复时区Timezone不生效问题

- 增加扫描记录迁移

- 修改密码

  **tips：npaobi/lsspva-iph/ulzzbz**

  **骰子已被掷下，命运显示你的幸运数字是7**

## v3 20220722

__重磅更新：自动更新插件docker版的Nessus搞出来了！__

用法： `docker run -itd --name=ramisec_nessus -p 8834:8834 ramisec/nessus`  
下载下来的容器是没有更新插件的  
之后再更新插件，更新插件的命令都相同：   
`docker exec -it ramisec_nessus /bin/bash /nessus/update.sh`  
下次要更新的话，执行相同的命令即可


## v2 20220621
更新20220620最新版插件，同时采用2个版本 nessus/nessuslite  
前者是已经破解好并且编译好插件，开箱即用    
后者开机后需要等待几分钟编译插件    
password:   
`U2FsdGVkX19WZv+QOe8awVyJwXDPSNSIC1X4AMNA4+3rO8mL/3HZ+mS/Or3DhcWXKs0WHfvOH1q/YNtVdXnaHg==`  
__tips__: github/elliot-bia  


> ~~# 旧版用法/Usage~~  
> ~~`docker run -itd -p 8834:8834 ramisec/nessus`   (4.73GB)~~  
> ~~或者/or~~    
> ~~`docker run -itd -p 8834:8834 ramisec/nessuslite` (3.55GB)~~    
> ~~前者不需要编译，适合低性能高带宽机器~~  
> ~~后者需要编译，适合高性能低带宽机器~~  

其实除了以上解密，还有另一种很简单的办法，让大家挖掘😆


# 捐赠
赏点钱喝杯咖啡吧~  
<img src="zfb_wx_qc.jpg" width="60%" height="60%" alt="zfb_wx_qc.png"/>
