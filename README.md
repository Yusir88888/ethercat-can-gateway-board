<div align="center">

# EtherCAT‑CAN 网关转换板





> 机器人电控EtherCAT从站转CAN总线网关板，实现EtherCAT与CAN报文互相转发

</div>

## 📖 项目简介
本硬件为机器人电控网关板，实现 **EtherCAT从站协议与CAN2.0B总线相互转换**。
上位X86主机通过EtherCAT网口下发指令，板卡完成协议解析，转发为CAN总线报文；同时CAN侧设备反馈数据回传给EtherCAT主机。
可以和48V LM5148多路输出机器人电源板配套使用，用于移动机器人、协作机器人、关节模组的运动控制系统。
仓库开源完整Altium Designer原理图、PCB工程、BOM物料清单，可直接打板与二次开发。

## ✨ 核心功能
- 🌐 EtherCAT：EtherCAT从站，RJ45接口，对接X86运动控制主机
- 📡 CAN总线：2路CAN2.0B通道，连接伺服驱动器、关节模组等外设
- 💾 板载I2C‑EEPROM：保存EtherCAT从站配置信息
- 🔌 外设扩展：预留LED状态指示灯、复位按键、USB调试接口
- 🤖 典型用途：机器人电控，EtherCAT主站转CAN设备协议桥接

## 🛠️ 技术方案 & 设计要点
- EDA软件：Altium Designer
- 协议：EtherCAT Slave、CAN 2.0B
- 外设资源：双CAN通道、I2C EEPROM、状态LED、外部复位、USB调试
- 应用搭配：可配合48V LM5148机器人多路电源板组成整套机器人电控

> 💡 设计难点：
高速EtherCAT差分信号布线阻抗控制；CAN总线增加隔离防护；数字通信地处理，降低EtherCAT高速信号对CAN总线的电磁干扰，保证报文收发稳定可靠。

## 🖼️ 工程预览
<img width="992" height="608" alt="image" src="https://github.com/user-attachments/assets/0638ca2e-9032-4fba-9f43-9440d63ea5a6" />
<img width="1280" height="2190" alt="微信图片_20261023133416_482_2" src="https://github.com/user-attachments/assets/7a2fa431-f257-40fe-9626-3208776c1814" />

> 图：EtherCAT‑CAN网关原理图
[EtherCAT-CAN_Project.pdf](https://github.com/user-attachments/files/33857079/EtherCAT-CAN_Project.pdf)

## 📋 打板说明
1. Altium Designer 20及以上版本打开工程
2. EtherCAT差分网线严格做100Ω差分阻抗控制
3. CAN总线建议外接终端电阻，根据实际应用选择接入
4. 调试顺序：先检查电源，再调试EtherCAT通信，最后测试CAN收发

## ⚠️ 调试注意事项
- EtherCAT通信需要EtherCAT主站软件进行配置
- CAN总线注意共地，长距离通信必须匹配终端电阻
- 本项目只开源硬件原理图PCB，EtherCAT从站固件需要自行开发适配

## 📜 开源协议
本项目基于 **MIT License** 开源。
允许查看、修改、复刻、商用，仅需保留原始版权声明。

## 📮 交流反馈
发现bug或优化建议请提交 Issue；
欢迎Fork本项目，提交PR共同完善。
