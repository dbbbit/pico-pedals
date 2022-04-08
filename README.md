# pico-pedals

### 简介

`pico-pedals` 项目旨在提供模拟 `踏板控制` 方案，包括上位机软件、固件等。


### 快速开始

使用内置 ADC 是比较经济实用的方案，按说明接线并刷入固件即可。

- 支持电位器、霍尔传感器或者是称重传感器经过放大器的输出信号。
- 自带 ADC 支持最大电压 3.3v 输入，如果使用VSYS（5v）作为 VCC， 信号输入ADC前要用电阻分压到 3.3v 以下。

#### 接线图


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
按住开发板上的 BOOT 按钮，插入电脑，保持片刻后释放按钮即可在文件管理器中看到一个可读写的存储器。
拖动 .uf2 后缀的固件到存储器中完成烧录。
```

#### 软件配置
<img src="https://github.com/dbbbit/pico-pedals/blob/master/Doc/GUI.png" width="800"/>

```code
校准：将每个踏板踩到底并保存最大值完成校准。
```

### 授权
- SIMSONN
- SIMJACK