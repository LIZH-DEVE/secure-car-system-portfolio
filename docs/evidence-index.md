# 公开证据索引

本文件为公开仓库中的证据入口。它为已经公开描述的测试结果分配稳定编号，并说明每项证据能够支持的结论。精确测试日期、Git commit、固件哈希、bitstream 哈希、原始日志和实物视频保存在非公开工程档案中，本仓库不公开这些敏感或体量较大的材料。

## 索引表

| Evidence ID | 证据层 | 测试或检查 | 公开结果 | 能够支持的结论 | 公开位置 |
| --- | --- | --- | --- | --- | --- |
| EV-SW-001 | 软件 | Python 回归 | 907 passed，1 skipped | 协议处理、密码调用封装、状态过滤和异常路径在既定测试输入下符合预期 | [`EVIDENCE.md`](../EVIDENCE.md) |
| EV-FPGA-001 | FPGA 自动化测试 | FPGA pytest | 73 passed | FPGA 侧接口与事务逻辑通过对应自动化测试 | [`EVIDENCE.md`](../EVIDENCE.md) |
| EV-RTL-001 | RTL 仿真 | UART 入口到 UART 出口 no-force | 10/10 | 请求从 UART 入口进入并从 UART 出口返回，未通过强制内部状态绕过数据通路 | [`docs/verification.md`](verification.md) |
| EV-POST-001 | 综合后验证 | UART 入口到 UART 出口 no-force | 10/10 | 综合后的通信和事务通路在对应测试中保持有效 | [`docs/verification.md`](verification.md) |
| EV-IMPL-001 | 实现 | 目标器件 | `xc7a50tfgg484-1` | 当前实现对应 Robei 板载 Artix-7 XC7A50T | [`EVIDENCE.md`](../EVIDENCE.md) |
| EV-IMPL-002 | 时序 | WNS / WHS | 0.536 ns / 0.006 ns | 当前实现报告中的建立和保持裕量均为正 | [`EVIDENCE.md`](../EVIDENCE.md) |
| EV-IMPL-003 | 实现检查 | black box、NSTD、UCIO、critical warning、DRC error | 均未出现 | 当前实现报告未记录这些阻断项 | [`EVIDENCE.md`](../EVIDENCE.md) |
| EV-HW-001 | 真实硬件 | AES STOP 压力 | 600 次通过 | 对应资格产物在指定 AES 压力测试中保持 STOP 安全行为 | [`EVIDENCE.md`](../EVIDENCE.md) |
| EV-HW-002 | 真实硬件 | SM4 STOP 压力 | 600 次通过 | 对应资格产物在指定 SM4 压力测试中保持 STOP 安全行为 | [`EVIDENCE.md`](../EVIDENCE.md) |
| EV-HW-003 | 真实硬件 | STM32 直连命令静默停车 | 10/10 | 执行端在对应直连测试条件下能够进入停车状态 | [`EVIDENCE.md`](../EVIDENCE.md) |
| EV-HW-004 | 真实硬件 | PC–ESP32–FPGA–STM32 完整链路失联停车 | 10/10 | 对应完整链路在失联测试中最终进入安全停车 | [`EVIDENCE.md`](../EVIDENCE.md) |
| EV-HW-005 | 真实硬件 | 七类负向注入 | 通过，最终 STOP/PWM0 | 对应异常输入未导致持续运动，执行端最终 PWM 归零 | [`EVIDENCE.md`](../EVIDENCE.md) |

## 使用边界

- 上述编号是公开仓库中的索引编号，不替代原始日志编号；
- 不同证据层回答的问题不同，不能用软件或仿真结果替代真实硬件结论；
- 完整开发基线、较早资格产物和比赛现场精简配置并非同一个 bitstream；
- 完整链路失联停车 10/10 只证明对应安全路径，不等于所有控制、回传和密码组合均在同一产物上全面通过；
- 精确日期、版本哈希和原始材料只在需要核验的合适场景下线下展示。
