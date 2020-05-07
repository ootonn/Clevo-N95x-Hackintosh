# 炫龙KP2 神舟ZX7-CP5S2 K690E 黑苹果EFI CPU I5-8400 蓝天 CLEVO N95TP6模具

## 相关申明

- 博客地址: https://www.wutong.tk/
- 长期更新: https://www.wutong.tk/index.php/hackintosh/2.html
- 本EFI为OC引导支持 `炫龙KP2` `神舟ZX7-CP5S2` `神舟K690E`  等采用  `蓝天 CLEVO N95TP6` 模具的机型
- 希望本EFI能够给大家带来便利，问题讨论点击加入[**<u>QQ交流群：1046199095</u>**](https://jq.qq.com/?_wv=1027&k=5hGmbfx)

## 博主配置

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
- 触摸板仿原生驱动，支持全部手势

## 未实现功能

- 未替换无线网卡前，无线网卡无法驱动，睡眠可能秒醒（添加6D补丁后修复睡眠）
- HDMI接口为独显输出，10.13.* 以后版本无法驱动N卡独显，所以无解

## 使用方法

- 屏幕为1080P分辨率，使用默认`config.plist`
- 屏幕为4K分辨率，请将`config_4k.plist`重命名为`config.plist`
- `config.plist` 中 `Platformlnfo` - `Generic` 自行更换五码

[<u>**更多信息**</u>](https://www.wutong.tk/index.php/hackintosh/2.html)