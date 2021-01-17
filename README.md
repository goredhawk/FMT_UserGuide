# Firmament Autopilot

## 概述
Firmament Autopilot (简称FMT) 是首个基于模型设计 (Model-Based Design， 简称MBD) 的开源自驾仪。FMT项目从 [Starry Pilot](https://github.com/JcZou/StarryPilot) 项目发展而来，目的是打造一个模块化，安全和轻量级的飞控系统。FMT 包括一个主要用C语言实现的嵌入式飞控系统 [FMT Firmware](https://github.com/Firmament-Autopilot/FMT_Firmware) 以及基于 Matlab/Simulink 开发的算法模型库和仿真框架 [FMT Model](https://github.com/Firmament-Autopilot/FMT_Model)。

**项目源码地址**：https://github.com/FirmamentPilot

## 为什么使用 FMT
FMT 采用基于模型设计 (MBD) 的开发模式，可以更快速的开发和验证的您的算法，无需手动编写嵌入式代码，只需要在 Simulink 中通过图形化的方式设计算法模型然后一键生成C/C++代码合入飞控嵌入式代码中，大大提高算法的开发和验证效率。

FMT 的核心算法基于 Matlab/Simulink 平台搭建，继承了 MBD 开发模式的诸多优点，包括：

1. 极大提升算法开发效率，节省时间和人力成本。
2. 减少手动编写代码过程中产生的错误，提升系统稳定性。
3. 极大提升算法的优化和 Debug 效率，简化系统测试和验证流程。
4. 提高算法的可维护性和可移植性。
5. V型开发模式，提升系统的稳定性和安全性。

FMT Firmware 是一个轻量级的飞控嵌入式软件，完美支持 MBD 的开发模式，并且具有优秀的稳定性和实时性。总结起来，FMT Firmware 的特点包括：

- C语言编写的轻量级飞控系统，更高的运行效率以及更易于阅读，使用。
- 跨平台的开发工具链，支持Windows/Linux/Mac OS。
- 支持 MBD 设计模式，大大提升开发和测试效率。
- 支持当前最流行的开源飞控硬件 Pixhawk。
- 基于实时 RTOS RT-Thread。具有优秀的实时性 (时间误差 < 1us) 和算法运行效率 (更低的CPU使用率)。
- 支持 Mavlink V1.0/V2.0和主流地面站 QGC，Mission Planner等。
- 支持硬件在环仿真 (HIl/SIH)。
- 高度模块化，松耦合的软件架构，易于裁剪和移植。

FMT Model 是基于 Matlab/Simulink 开发的仿真模型，包括了完整的仿真模型框架，支持模型在环仿真 (Model-in-the-loop Simulation, MIL)，软件在环仿真 (Software-in-the-loop Simulation, SIL) 和 开环仿真 (Open-loop Simulation)。 以及一套完整的多旋翼基础算法模型：

- 导航模型 (INS)：基于互补滤波算法 (Complementary Filter) 的通用导航模型，支持的传感器包括： IMU，磁力计，气压计，GPS，超声测距仪和光流传感器（可扩展其它传感器的融合）。导航输出的状态信息包括：姿态，速度，世界坐标位置 （经纬高），相对位置，对地高度，陀螺零偏，加速度零偏，传感器健康状态，导航系统状态等信息。适用于大部分的被控对象（无人机，无人车/船，机器人等）和应用场景。
- 飞行管理系统模型 (FMS)：包括飞行模式控制（轨迹飞行，定点，定高，手动，特技模式等），解锁/上锁逻辑，自动起飞降落，安全检查等逻辑控制。
- 控制模型 (Controller)：基于串级 PID 的控制器模型和控制分配。包括速度环、角度环和角速度环控制器。
- 被控对象模型 (Plant)：可以是任意被控对象，如无人机。无人车/船，机器人等。包括动力学模型，作动器模型，环境模型和传感器模型等。

各个模型可以独立配置运行频率并一键生成 C/C++ 代码，然后无缝合入 FMT Firmware 嵌入式飞控中。FMT_Model 除了提供一套基础的算法模型以外，还提供算法模型模板，基于模板可以更快速开发自己的算法模型或者移植已有的算法。

# 手册目录

## FMT Firmware
- [快速上手](fmt_firmware/quick_start/quick_start.md)
- [FMT Firmware架构](fmt_firmware/architecture/architecture.md)
- [组件 (Module)](fmt_firmware/module/module.md)
- [驱动和硬件虚拟设备 (Driver/HAL)](fmt_firmware/device/device.md)
- 任务 (Task)
- 硬件在环仿真 (HIL/SIH)
- 贡献

## FMT Model
- [快速上手](fmt_model/quick_start/quick_start.md)
- [FMT Model架构](fmt_model/architecture/architecture.md)
- [模型仿真](fmt_model/simulation/simulation.md)
- [模型接口标准 (FMT Model Interface)](fmt_model/fmt_model_interface/fmt_model_interface.md)
- [算法模型库](fmt_model/algorithm_model/models.md)
- [模型代码生成与合入](fmt_model/code_generation/code_generation.md)
- [模型二次开发](fmt_model/develop/develop.md)
- 贡献
