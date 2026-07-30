# Hardware Platform

## Overview

本项目采用多节点软硬件协同架构，由网络通信模块、FPGA处理模块、嵌入式控制模块和物理执行平台组成。

## FPGA Processing Platform

- Device: Xilinx Artix-7 XC7A50T
- Role:
  - 通信协议处理；
  - 安全事务控制；
  - 状态校验；
  - 车控逻辑集成。

## ESP32 Communication Module

ESP32作为无线通信入口：

- 负责Wi-Fi连接；
- 完成UDP数据收发；
- 实现网络与UART之间的数据桥接。

## STM32 Control Module

STM32负责设备侧执行：

- 控制指令解析；
- PWM/GPIO电机控制；
- 状态生成与回传；
- 通信异常情况下的安全停车。

## Hardware Photos

后续补充：

- FPGA开发板照片；
- ESP32通信模块照片；
- STM32控制板照片；
- 整机安装照片。

## Notes

硬件图片仅用于项目展示，不包含敏感配置、密钥或调试环境信息。
