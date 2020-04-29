# 炫龙KP2 神舟ZX7-CP5S2 K690E 黑苹果EFI CPU I5-8400 蓝天 CLEVO N95TP6模具

## 相关申明

- 博客地址: https://www.wutong.tk/
- 长期更新: https://www.wutong.tk/index.php/hackintosh/2.html
- 本EFI为OC引导支持 `炫龙KP2` `神舟ZX7-CP5S2` `神舟K690E`  等采用  `蓝天 CLEVO N95TP6` 模具的机型
- 希望本EFI能够给大家带来便利，问题讨论点击加入[**<u>QQ交流群：1046199095</u>**](https://jq.qq.com/?_wv=1027&k=5hGmbfx)

## 配置相关

### 博主配置

| 规格     | 详细信息                                     |
| -------- | -------------------------------------------- |
| 电脑型号 | 炫龙KP2 蓝天CLEVO N95TP6                     |
| 操作系统 | macOS Catalina 10.15.4                       |
| 处理器   | Intel Core i5-8400 @ 2.81GHz 六核            |
| 内存     | 16 GB 2667 MHz DDR4                          |
| 硬盘     | Samsung SM961 512GB M.2 NGFF PCIe Gen 3.0 x4 |
| 显卡     | Intel UHD Graphics 630 2048MB                |
| 网卡     | 已更换为BCM94360CS2                          |
| 声卡     | ALC269                                       |
| SMBIOS   | MacBookPro14,3                               |

### 适用配置

- #### 硬件配置

  - 核心显卡为`UHD630`（Intel 8、9代CPU）
  - 模具为`蓝天N95系列`可尝试使用

- #### 目前适配机型

  - 炫龙KP2

## 实现功能
- CPU 支持睿频变频
- 核显 UHD630 显存 2048MB
- 硬件加速 4K HEVC/H.265解码
- 原生电源管理、原生NVRAM
- USB内建支持USB2.0、USB3.0
- 屏幕亮度调节、快捷键调节、亮度信息保存
- 声卡完美内建
- 睡眠唤醒正常，支持鼠标唤醒
- 有线网卡正常驱动
- 无线网卡免驱（更换为BCM94360CS2）
- 蓝牙正常驱动（更换与否皆可驱动）
- miniDP热插拔支持4K输出
- 支持iMessage、Facetime，更换网卡后支持Handoff、随航
- 电量、充电状态等正常显示
## 未实现功能
- 未替换无线网卡前，无线网卡无法驱动，睡眠可能秒醒（添加6D补丁后修复睡眠）
- HDMI接口为独显输出，10.13.* 以后版本无法驱动N卡独显，所以无解
- 未使用触摸板驱动，禁用触摸板
## 更新日志

- ### 2020/04/15

  - 更新电量显示，电量、充电状态可正常显示

- ### 2020/04/12
  
  - OC引导初次发布，待更新电量显示功能。

## 常用代码

**直接将下列代码复制到 `macOS` - `终端` 内，输入用户密码后运行即可**

- ### 开启HIDPI

```tcl
sh -c "$(curl -fsSL https://raw.githubusercontent.com/xzhih/one-key-hidpi/master/hidpi.sh)"
```

- ### 重建kext缓存

```tcl
sudo rm /System/Library/PrelinkedKernels/prelinkedkernel
sudo rm /System/Library/Caches/com.apple.kext.caches/Startup/kernelcache
sudo chmod -R 755 /System/Library/Extensions
sudo chmod -R 755 /Library/Extensions
sudo chown -R root:wheel /System/Library/Extensions
sudo chown -R root:wheel /Library/Extensions
sudo touch /System/Library/Extensions
sudo touch /Library/Extensions
sudo kextcache -q -update-volume /
sudo kextcache -system-caches
sudo kextcache -i /
```

- ### 系统睡眠优化

```tcl
sudo pmset -a hibernatemode 0
sudo rm /var/vm/sleepimage
sudo mkdir /var/vm/sleepimage
sudo pmset -a standby 0
sudo pmset -a autopoweroff 0
sudo pmset -a proximitywake 0
```

## 使用方法

- 屏幕为1080P分辨率，使用默认`config.plist`
- 屏幕为4K分辨率，请将`config_4k.plist`重命名为`config.plist`
- `config.plist` 中 `Platformlnfo` - `Generic` 自行更换五码

