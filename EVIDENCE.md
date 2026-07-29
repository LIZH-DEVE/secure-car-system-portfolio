# Evidence Summary

## 完整双向开发基线

- Python回归：907 passed，1 skipped；
- FPGA pytest：73 passed；
- RTL UART入口到UART出口no-force：10/10；
- 综合后UART入口到UART出口no-force：10/10；
- Vivado 2024.1实现器件：xc7a50tfgg484-1；
- WNS 0.536 ns，WHS 0.006 ns；
- 无black box、NSTD、UCIO、critical warning或DRC error。

## 较早资格产物的真实硬件门禁

- AES 600次、SM4 600次正式STOP压力通过；
- STM32直连命令静默停车10/10；
- 完整PC—ESP32—FPGA—STM32链路失联停车10/10；
- 七类负向注入通过，最终STOP/PWM0。

## 解释限制

- 离线测试、综合实现和真实硬件资格证据属于不同证据层，不能相互替代；
- 后期比赛现场另有AES精简配置，不能把它与完整AES/SM4基线描述成同一bitstream；
- 实体超声波未安装，真实距离测量不在验收声明内。

