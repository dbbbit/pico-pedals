# pico-pedals

### 简介

`pico-pedals` 项目将提供完整的赛车模拟 `踏板控制器` 方案，包括但不限于上位机软件、硬件资料及相关固件。

本项目支持免费商业授权，请联系作者提供品牌ID并保留本项目链接即可。

### 目录说明

- Doc：使用文档、接线图等
- Software：上位机配置软件
- Firmware：芯片固件

### 快速开始

这里先给最简单的使用案例，后续将提供更多称重传感器\放大模块\ADC模块使用文档。

#### 接线图
- 以树莓派 Pico 为例，没错这就是项目名称的由来
- Pico 自带 ADC 支持最大电压 3.3v 输入，如果使用VSYS（5v）作为 VCC， 输入ADC前要用电阻分压到 3.3v 以下。
- 踏板信号可以使用来自电位器、霍尔传感器或者是 INA12x/AD62x 之类的放大器输出。

<img src="https://github.com/dbbbit/pico-pedals/blob/master/Doc/pico-pin.png" />

```code
油门信号 -- GPIO_26
刹车信号 -- GPIO_27
离合信号 -- GPIO_28
VCC  -- ADC_VREF(3v3)
GND  -- AGND
```

#### 固件烧录

```code
按住开发板上的BOOT按钮，插入USB数据线，保持片刻后释放按钮即可在文件管理器中看到一个可读写的存储器。
拖动 Firmware/rp2040 目录下的固件到存储器中即可完成烧录，之后就可以打开软件进行校准配置。
```

#### 软件配置
<img src="https://github.com/dbbbit/pico-pedals/blob/master/Doc/GUI.png" width="800"/>

```code
校准：将每个踏板踩到底并保存最大值完成校准。
```

### 开发

- GUI 软件源码见 pico-pedals-gui（Star过百即发布）
    - 理论上支持所有带 usb-hid 功能的芯片
    - 固件需要实现约定的 `配置协议`

- 已支持芯片
    - 树莓派 `RP2040`

- 待支持芯片
    - stm32c8t6 
    - arduino ATMEGA32U4 

### 授权品牌
- SIMSONN