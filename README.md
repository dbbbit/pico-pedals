# pico-pedals

### 简介

`pico-pedals` 项目将提供完整的赛车模拟 `踏板控制器` 方案，包括上位机软件\固件\硬件资料等。


支持商业使用，请联系作者授权（为避免滥用，请提供必要信息如品牌ID及链接，二次开发需保留原作信息）。

### 目录说明

- Doc：使用文档、接线图等
- Software：上位机软件
- Firmware：芯片固件

### 快速开始

使用开发板内置 ADC 是最经济实用的方案，已测试可用， 按以下说明接线并刷入固件即可。

项目重点在于软件和固件开发，各种传感器、放大器、外置ADC的使用支持可参考网上教程或等后续更新。


#### 接线图

- 以树莓派 Pico 开发板为例（没错这就是项目名称的由来
- Pico 自带 ADC 支持最大电压 3.3v 输入，如果使用VSYS（5v）作为 VCC， 信号输入ADC前要用电阻分压到 3.3v 以下。
- 踏板信号可以使用来自电位器、霍尔传感器或者是称重传感器经过 INA12x/AD62x 等放大器输出。

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

- GUI 上位机软件
    - 可支持所有带 usb-hid 功能的芯片
    - 芯片固件需要适配，实现相关 `配置协议`

- 已支持芯片
    - 树莓派 `RP2040`


### 已授权品牌
- SIMSONN
- SIMJACK