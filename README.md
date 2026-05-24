# STM32 HAL库 学习项目 (STM32 HAL Library Learning Project)

本项目是基于 STM32 HAL 库的学习实践记录，参考了江协科技等相关教程。项目包含了从基础外设到高级应用的多个实验模块。

## 项目简介 (Introduction)
本项目旨在通过实践掌握 STM32F103 系列微控制器的 HAL 库开发。每个文件夹代表一个独立的实验，包含了 STM32CubeMX 的配置文件 (`.ioc`)、底层驱动 (`Drivers`)、核心代码 (`Core`) 以及工程文件 (`MDK-ARM` 或 `VSCODE_EIDE`)。

## 硬件环境 (Hardware Environment)
- **MCU**: STM32F103C8T6 (Cortex-M3)
- **基础外设**: LED, 按键, 蜂鸣器, 光敏电阻
- **显示**: 0.96寸 OLED 屏幕 (I2C 接口)
- **传感器**: 旋转编码器, MPU6050 (六轴加速度计陀螺仪)
- **存储**: W25Q64 (SPI Flash)
- **执行器**: 舵机, 直流电机
- **通讯**: 蓝牙模块 (HC-05/08), 红外接收头

## 软件环境 (Software Environment)
- **配置工具**: STM32CubeMX
- **IDE**: Keil MDK-ARM (uVision5) 或 VS Code
- **固件库**: STM32Cube FW_F1 V1.8.x (HAL 库)

## 项目目录说明 (Project Structure)

### 1. 基础入门 (Basic)
- `01 led_blink`: LED 闪烁
- `02 LED_color`: 幻彩/彩色 LED 控制
- `03 LED_KEY`: 按键输入控制
- `04 buzzer and Photoresistor_sensor`: 蜂鸣器驱动与光敏传感器读取
- `05 OLED`: OLED 屏幕显示基础

### 2. 中断与定时器 (Interrupts & Timers)
- `06 External_interrupt`: 外部中断 (EXTI)
- `07 Rotary_encoder`: 旋转编码器计次
- `08 pwm_led`: PWM 呼吸灯
- `09 PWM_drive servo`: PWM 驱动舵机角度控制
- `10 PWM_control_of_DC_motor`: PWM 控制直流电机速度
- `11 Measuring_Frequency_via_PWMI_Input_Capture`: 输入捕获测量频率
- `12 PWMI_Input_Capture_for_Duty_Cycle_Measurement`: PWMI 模式测量频率和占空比
- `13 Encoder_Interface_Speed`: 定时器编码器接口模式测量速度

### 3. 数据采集与传输 (ADC & DMA)
- `14 ADC_Single_Channl`: ADC 单通道采集
- `15 ADC_Multi_Channl`: ADC 多通道采集
- `16~18 DMA数据转运`: DMA 存储器到存储器的数据转运（单次/多次/循环模式）
- `19 ADC单次转换+扫描+中断+DMA`: ADC 多通道配合 DMA 的单次采集
- `20 ADC连续扫描转换+DMA循环模式`: ADC 配合 DMA 的连续循环采集

### 4. 串口通讯 (USART)
- `21 USART串口发送`: 串口基础发送（printf 重定向等）
- `22 USART接收`: 串口查询方式接收
- `23 usart控制幻彩小灯`: 串口指令协议解析与硬件控制
- `24 USART中断模式`: 串口中断方式收发
- `25 USART串口DMA收发不定长数据`: 串口 DMA + 空闲中断实现高效不定长数据处理

### 5. 常见总线与传感器 (Bus & Sensors)
- `26 I2C驱动OLED`: 硬件 I2C 驱动 OLED
- `27 u8g2库`: (进行中) 移植 u8g2 图形库
- `28 MPU6050`: 硬件 I2C 驱动 MPU6050
- `29_MPU6050_ software`: 软件模拟 I2C 驱动 MPU6050
- `30_W25Q64_SPI_Software`: 软件模拟 SPI 驱动 W25Q64
- `31_W25Q64_SPI_Hardware`: 硬件 SPI 驱动 W25Q64

### 6. 系统与存储 (System & Flash)
- `32_BKP_Reading_Writing`: 备份寄存器操作
- `33_RTC_Real_Time_Clock`: 实时时钟配置与使用
- `34~36 PWR`: 电源管理（睡眠/停机/待机模式）
- `37_Independent_Watchdog`: 独立看门狗 (IWDG)
- `38_Window_Watchdog`: 窗口看门狗 (WWDG)
- `39_Read_Internal_Flash`: 读取内部 Flash
- `40_Erase_and_Write_to_Flash`: 擦除与写入内部 Flash

### 7. 无线与扩展 (Wireless & Extensions)
- `41 Infrared_Remote_Control`: 红外遥控解码
- `42_Bluetooth_Serial_Communication`: 蓝牙串口通讯
- `43_Sending_Data_via_Bluetooth`: 通过蓝牙发送传感器数据

## 如何开始
1. 进入对应实验的子目录。
2. 双击 `.ioc` 文件查看引脚配置与外设设置。
3. 进入 `MDK-ARM` 目录，打开 `.uvprojx` 文件即可在 Keil 中进行开发。
4. 编译、下载，观察硬件现象。

## 学习笔记
项目中部分文件夹包含 `.docx` 或 `.txt` 文件，记录了开发过程中的常见问题（如晶振选择、编译错误、API 说明等），建议结合参考。

---
*Created by [Your Name/Github Username]*
