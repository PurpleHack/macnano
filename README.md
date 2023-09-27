
![mac_nano_preview](/Assets/img/preview.png)

# macnano 小巧精致的 mac mini 改装

史上最强(maybe) mac mini 改装， 视频介绍： https://www.bilibili.com/video/BV1n841117bS

视频一共介绍了 4 种 mac mini 改装方案，每一种都采用不同的 3D 模型。本项目将其中 3 种 3D 打印版本（macnano se）的外壳模型文件开源了出来，方便大家打印制作，全金属版(macnano ultra)暂未开源。

mac mini 很久都没有更换过模具，内部空间利用率很低，体积并不迷你。所以我和一群数码改装爱好者一同改造了 mac mini。改造主要有 5 点需要解决：1.外壳设计。2.供电改造。3.散热改造。4.信号天线改造。 5.开关按钮改造。


## 关于外壳

外壳我已经开源出来了，下载下来直接打印就行。一共有 3 种版本 usb typec 供电版，磁吸供电版和 DC 插头供电局版。 需要注意的是建议使用耐热的 3D 打印材料来打印，不然是有可能造成外壳受热变形。
![typec](/Assets/img/macnano_se_typec_preview.png)
![magnet](/Assets/img/macnano_se_magnet_preview.png)
![dc](/Assets/img/macnano_se_dc_preview.png)



## 关于供电

mac mini 主板使用 12V 供电。低于此电压无法开机，高于 12v 会烧主板。
电线请使用 18AWG 铁氟龙高温线，与 mac mini 主板相连接的插座类型是 HC-PHD-2*10Y, 如图。
![phd](/Assets/img/phd.png)
接线示意图
![power](/Assets/img/power.png)


typec 供电版需要制板并焊接 PCB 电路，文件在 PCB 文件夹下，请用嘉立创 EDA 打开。 给 macnano 供电的设备（充电头，充电宝）需要支持 PD，QC 协议，还要有支持 12V 输出，不然无法开机。（不必考虑损坏主板，如果供电设备不支持 PD，QC 协议或无 12 V 输出，电路板会选择一个低压例如 9v或5v输出，所以不会烧坏主板）

DC 版本需要购买5.5*2.1mm 母座，本项目用的是这种如图![phd](/Assets/img/dc.jpeg)，注意 DC 版本使用的电源一定不能超过 12V，不能超过 12V，不能超过 12V，否则会烧坏主板。

磁吸版本使用 2pin 磁吸线作为插头,如图 ![phd](/Assets/img/magnet.jpg)。

## 关于散热

散热用到的器件有两个，一是 12v 4线 PWM 风扇智能温控调速器，二是 2510 PWM风扇（B3插头）。这两个都能买到成品，非常方便。

## 关于信号

原装 mac mini 的天线非常的大，所以需要购买 2.8g 5.8g 双频 ipex 1代天线，这个没什么难度有手就行。

## 关于开关

3D 打印版的（macnano se）是用的原装开关，好处是减少了改装复杂度，坏处是还需要单独拆卸这个开关零件。未来可能会优化使用自己设计的开关（todo）。


## 没有银弹

不可能将 mac mini 缩小的同时又获得和原装同样的散热和性能，如果真的可以，苹果早就这样做了。改造的最终目标是获得一个相对较小的体积和一个性能，散热比较均衡的机器。typec 最高功率 36W，如果不使用雷电接口反向供电给其他设备是完全够用了。DC 版本理论上可以做到100W甚至更高的功率，这取决于使用的电源功率。散热虽然没有原装的好，但轻度使用完全可以。