# SmartRV

房车内的智能控制系统，包括以下模块

中控系统为树莓派Zero W，待机功耗1～2瓦

1. 车载蓄电池监控，车载锂电池监控
监控采用了佰微电子的350A库仑计，并自己改装加装了串口透传BLE模块，这样树莓派可以无线读取电池运行的电压、电流及电量等信息
2. 太阳能监控
太阳能采用的renogy整体方案，renogy的30A的mppt控制器支持ble模块读取数据，树莓派也可以无线读取太阳能运行的电压、电流及功率等信息
3. 车内空气监控
拆了几个监测还算准确的空气监测器，一个是镭豆，发现使用的是AMS IAQ-CORE监控的VOC，攀藤的PMS3003监控的PM2.5，另外拆了一个Honeywell的，也是用的IAQ-CORE监控的VOC，二氧化碳用的是MH-Z19B，甲醛用的是ZE08-CH2O，这些传感器淘宝都有卖，因此使用以下传感器连接树莓派读取车内空气信息
PM2.5: PMS3003
VOC: IAQ-CORE
二氧化碳：MH-Z19B
甲醛：ZE08-CH2O
因为有可能在车内使用燃烧氧气的炉子，所以还需要监测一氧化碳，一氧化碳检测器暂时没有发现更好的解决方案，暂时使用了ZE16-CO模块监测
所有传感器接上树莓派以后，功耗只增加了最多1瓦
4. 车内多媒体解决方案
5. 自动控制及远程控制
树莓派内部署ssh反向代理隧道，即可远程控制
6. 车内摄像头监控
一开始采用了小蚁1080p云台摄像头方案，发现功耗太大，大概2～4瓦的待机功耗，太烧电池，目前暂时使用reolink带pir传感器的摄像头降低功耗，后期可以考虑树莓派的摄像头实现延迟摄影实现
7. 车内语音控制
目前感觉使用较好的有百度语音及小爱同学
8. 其它待加
