# zA1

**斐讯悟空A1空气净化器个人固件.** 优化开发中

排插A1因为服务器关闭,无法远程控制.

为此,开发供自己使用的FW及对应app,确保自己能够正常使用此排插.取名为zA1.



注意:本项目还在开发完善中,部分文档还为完成,所以以下链接可能无效或错误,请等待更新.



> ### 作者声明
>
> 由于zTC1不良商用问题太严重,所以依然增加了激活码激活功能.
> 由于开发的设备由群友众筹给我,所以激活码以众筹价格收费(16元),如果有需要请联系我.
>
> **同时依然严禁他人将本项目用户用于任何商业活动.个人在非盈利情况下可以自己使用,严禁收费代刷等任何盈利服务.**
>
> 有需要请联系作者:zip_zhang@foxmail.com


QQ群:**783322122**  [点这里直接加群](//shang.qq.com/wpa/qunwpa?idkey=ea22ed67249c1c313922317efbde45629ab4a3908298a355ad832eba9045596b)  (群内只留购买了A1激活码的,入群费用16元为激活码购买.谢谢)(如果提示禁止入群,可能为付费群的一些问题,可以晚点再试)


## 特性

本固件使用斐讯A1空气净化器硬件为基础,实现以下功能:
- [x] 热点web配网

- [x] 按键控制开关

- [x] 五组定时任务设置风量/开关

- [x] ota在线升级

- [x] 无服务器时使用UDP通信(udp通信不稳定,有条件的还是建议上mqtt通信)

- [x] MQTT服务器连接控制

- [x] 通过mqtt连入homeassistant(需要更新homeassistant配置文件)

- [x] 配合M1实现联动功能(M1更新至v0.1.0及以上版本,当前功能测试中,有nr/hass的建议使用服务器实现自动化联动)   zM1固件见[zM1空气传感器](https://github.com/a2633063/zM1)

  

已知问题:

- ~~rgb灯无法控制:受主控限制,无法直接亮彩色,后期改为亮白色~~

- **rgb问题已经解决**,0.0.6的版本开始支持led显示.

注意:从之前版本ota到0.0.6版本后会初始化所有配置,ota完成后请重新配对wifi+激活.

  



## 目录

[前言(必看)](#前言必看)

[开始](#开始)

[激活码说明](#激活码说明)

[拆机接线及烧录固件相关](#拆机接线及烧录固件相关)

[开始使用/使用方法](#开始使用/使用方法)

[接入home assistant](#接入home-assistant)

[其他内容](#其他内容)

​	[代码编译](#代码编译)

​	[通信协议](#通信协议)





## 前言(必看)

- 刷机后将无法还原为原厂固件!
- 除非写明了`如果你不是开发人员,请忽略此项`之类的字眼,否则,请**一个字一个字看清楚看完**整后再考虑动手及提问!很可能一句话就是你成功与否的关键!
- 烧录固件,可以用支持swd的jlink烧录器,也可以用串口ttl工具烧录.(本人不做任何烧录器的售卖,所有提供的链接或推荐都为第三方卖家,和本人无关).
- 使用此固件,需要app端配合,见[SmartControl_Android_MQTT](https://github.com/a2633063/SmartControl_Android_MQTT).
- app只有android,因ios限制,本人不考虑免费做ios开发.(不要再问是否有ios端).

>
> ~~虽然没有ios端,但固件支持homeassistant,可以使用安卓APP配置完成后,连入homeassistant后,使用ios控制. APP主要仅为第一次使用配对网络及配置mqtt服务器时使用,之后可以用homeassistant控制不再使用app.~~

> ~~如果你不知道什么是mqtt或homeassistant,所有有关的内容可以跳过.~~

> ~~如果你有任何问题,可以直接在此项目中提交issue,或给我发送邮件:zip_zhang@foxmail.com,邮件标题中请注明[zA1].~~





## 开始

整体流程如下:拆开A1,将固件/烧录器/pc互相连接,在pc运行烧录软件进行烧录,烧录固件.

烧录完成后,首次使用前配对网络并配置mqtt服务器,之后就可以使用了.



## 激活码说明

为防止被不良商用,直接了必须使用激活码激活的功能.zA1激活码为收费,16元一个.

激活方式见[开始使用中的激活](https://github.com/a2633063/zA1/wiki/开始使用#激活)

## 拆机接线及烧录固件相关

见[固件烧录](https://github.com/a2633063/zA1/wiki/固件烧录)

烧录固件完成后,即可开始使用



## 开始使用/使用方法

见[开始使用](https://github.com/a2633063/zA1/wiki/开始使用)



## 接入home assistant

见[homeassistant接入](https://github.com/a2633063/zA1/wiki/homeassistant接入)



## 其他内容

### 通信协议

> 此项为专业开发人员准备,如果你不是开发人员,请跳过此项

所有通信协议开源,你可以自己开发控制app或ios端

见[通信协议](https://github.com/a2633063/zA1/wiki/通信协议)



