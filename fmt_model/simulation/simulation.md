# 模型仿真
> “一切可以被控制的对象，都需要被数学量化”

模型仿真功能在飞控系统开发的各个阶段都占有非常重要的地位。在项目前期，模型在环仿真可以帮助快速发现并解决软件中存在的问题， 使系统功能快速落地。在项目中后期，软件在环/硬件在环可以快速测试并验证系统在真实平台上的表现，并得到大量的测试数据，加速系统功能迭代。

![v_model](figures/v_model.png)

FMT Model 提供了功能丰富和全面的仿真功能，如模型在环仿真 (MIL)，硬件在环仿真 (HIL) 以及开环仿真 (Open-Loop Simulation) 的功能，基本涵盖了V型开发流程所需的大部分仿真功能。对于其它的仿真模式，如软件在环仿真 (SIL) 环和芯片在环仿真 (PIL) 后续也将支持。

- [模型在环仿真 (MIL Simulation)](mil_sim.md)
- 软件在环仿真 (SIL Simulation) [TBA]
- 硬件在环仿真 (HIL Simulation) [TBA]
- [开环仿真 (Open-loop Simulation)](openloop_sim.md)
- 使用第三方仿真器 [TBA]
