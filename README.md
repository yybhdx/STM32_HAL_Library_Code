# STM32 HAL库 学习项目 (STM32 HAL Library Learning Project)

![Language](https://img.shields.io/badge/Language-C-blue.svg)
![Framework](https://img.shields.io/badge/Framework-STM32Cube%20HAL-orange.svg)
![IDE](https://img.shields.io/badge/IDE-Keil%20%7C%20VSCode-brightgreen.svg)
![MCU](https://img.shields.io/badge/MCU-STM32F103C8T6-blue.svg)

本项目是基于 STM32 HAL 库的学习实践记录，参考了江协科技等相关教程。项目包含了从基础外设到高级应用的多个实验模块。

## 🎯 项目简介
本项目旨在通过实践掌握 STM32F103 系列微控制器的 HAL 库开发。每个文件夹代表一个独立的实验，包含了 STM32CubeMX 配置、底层驱动、核心代码以及多平台工程文件。

---

## 🗺️ 学习路线图 (Learning Roadmap)

### 第一阶段：基础外设 (Basics)
*掌握 GPIO 输入输出与基础显示*
- `01 led_blink`: LED 闪烁基础
- `02 LED_color`: 幻彩 LED 控制 (WS2812等)
- `03 LED_KEY`: 按键输入处理
- `04 buzzer and Photoresistor_sensor`: 蜂鸣器与模拟传感器应用
- `05 OLED`: 0.96寸 OLED 屏幕基础显示

### 第二阶段：中断与定时器 (Timers & PWM)
*理解实时响应与波形控制*
- `06 External_interrupt`: 外部中断 (EXTI) 核心原理
- `07 Rotary_encoder`: 旋转编码器硬件计次
- `08 pwm_led`: 定时器 PWM 产生呼吸灯
- `09 PWM_drive servo`: PWM 舵机精准角度控制
- `10 PWM_control_of_DC_motor`: PWM 电机调速
- `11 Measuring_Frequency`: 输入捕获 (IC) 测量频率
- `12 PWMI_Input_Capture`: PWMI 模式测量占空比
- `13 Encoder_Interface`: 硬件编码器接口模式测速

### 第三阶段：数据采集与高速传输 (ADC & DMA)
*掌握模拟信号数字化与内存管理*
- `14 ADC_Single_Channl`: 基础模拟量采集
- `15 ADC_Multi_Channl`: 多路信号轮询采集
- `16~18 DMA Transfer`: DMA 存储器间传输 (单次/多次/循环)
- `19 ADC+DMA (Normal)`: ADC 配合 DMA 的单次扫描传输
- `20 ADC+DMA (Circular)`: 高效连续实时信号监控

### 第四阶段：通讯协议深入 (Communications)
*实现设备间的高效对话*
- `21~22 USART Basic`: 串口发送与查询接收
- `24 USART Interrupt`: 串口中断收发
- `25 USART DMA + IDLE`: **推荐！** 串口 DMA 配合空闲中断处理不定长数据
- `26 I2C OLED`: 硬件 I2C 驱动显示屏
- `28~29 MPU6050`: 硬件/软件 I2C 驱动六轴传感器
- `30~31 W25Q64`: 软件/硬件 SPI 驱动 Flash 存储
- `42~43 Bluetooth`: 蓝牙无线串口通讯与数据透传

### 第五阶段：系统管理与底层应用 (System & Advanced)
*深入 MCU 核心功能与存储管理*
- `32 BKP`: 备份寄存器数据掉电保存
- `33 RTC`: 实时时钟万年历
- `34~36 PWR`: 深入低功耗模式 (Sleep/Stop/Standby)
- `37~38 Watchdog`: IWDG 与 WWDG 提高系统稳定性
- `39~40 Internal Flash`: 读写内部 Flash 实现参数永久保存
- `41 Infrared`: 红外遥控 NEC 协议解码

---

## 📚 学习资料与笔记
本项目不仅包含代码，还整理了重要的学习文档：
- 📄 [HAL库常用API说明](./HAL库API.docx)
- 📄 [关于晶振选择的深度疑问与解答](./晶振选择的疑问.docx)
- 📄 [串口DMA不定长数据流程解析](./25%20USART串口DMA收发不定长数据/流程解析.docx)

---

## 🛠️ 开发环境配置 (IDE Setup)

### 选项 A: Keil MDK-ARM (推荐)
1. 确保安装了 `Keil uVision5` 及 `STM32F1xx` 器件包。
2. 进入各模块的 `MDK-ARM` 文件夹。
3. 双击打开 `.uvprojx` 工程。
4. 编译 (F7) 并下载 (F8)。

### 选项 B: VS Code (现代开发环境)
本项目支持基于 `EIDE` 或 `Cmake` 的开发模式（见 `Test_Cmake_Vscode`）：
1. 安装 VS Code 插件：`Embedded IDE (EIDE)` 或 `Cortex-Debug`。
2. 确保已配置 `arm-none-eabi-gcc` 工具链。
3. 可通过 `.mxproject` 导入工程配置。

---

## 🔧 硬件连接提示
- **调试器**: 使用 ST-Link V2 (SWD 模式)。
- **电源**: 确保 3.3V 供电稳定。
- **OLED**: I2C 默认连接至 `PB6 (SCL)` 和 `PB7 (SDA)`。

---
*Created with ❤️ by [Your Name/Github Username]*
