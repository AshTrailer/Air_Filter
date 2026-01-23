## Air_Filter

Air_Filter is a compact, modular soldering fume extraction and air filtration device designed as a personal hardware project.

The enclosure measures approximately 9.8 × 11 × 11 cm and is constructed as a two-part, chamfered square housing, assembled using M3 fasteners. Inside, it integrates a Sanyo centrifugal blower capable of generating nearly 700 Pa of static pressure at 12 V, providing strong suction performance for soldering smoke removal.

Power is supplied via a standard DC jack, and airflow is adjustable through a rotary PWM control knob. The fan speed is controlled by a potentiometer-driven PWM generator, allowing smooth and flexible airflow regulation.

The mechanical design supports multiple fan orientations. In an upright configuration (front-facing intake), the device allows three different placement orientations. When laid horizontally, the outlet direction can be freely adjusted to suit different workspace layouts.

The filtration module is designed to be detachable and replaceable, enabling easy maintenance and future filter upgrades.

This repository documents the mechanical design, electronics, and overall system concept of the Air_Filter project, intended for learning, experimentation, and open-source sharing.


## Air_Filter
Air_Filter 是一个紧凑型、模块化的焊接烟气过滤与空气抽吸装置，是一个个人硬件设计与实现项目。

整机外壳尺寸约为 9.8 × 11 × 11 cm，采用带倒角的方形结构设计，由上下两部分组成，通过 M3 螺丝与螺母进行装配固定。内部集成了一款山洋（Sanyo）离心风机，在 12 V 供电条件下可提供接近 700 Pa 的静压，具备较强的烟气抽吸能力，适用于焊接烟雾的捕集与过滤。

设备通过标准 DC Jack 接口供电，侧面设有 PWM 调速旋钮。风机转速由电位器控制的 PWM 发生器进行调节，可实现平滑、可控的风量调节。

在结构设计上，该风机支持多种安装与摆放方式。在竖直放置（正面进气）的情况下，可实现三种不同的摆放方向；在水平放置时，出风口方向可根据使用环境自由调整，以适应不同的工作台布局。

过滤模块采用可拆卸、可更换的结构设计，便于维护与后续升级不同类型的过滤介质。

本仓库用于记录 Air_Filter 项目的整体设计思路，包括机械结构、电气控制以及系统集成方案，主要用于学习、实验与开源分享。

## Media / 项目展示

> 项目实物照片与演示视频

- 实物整体外观
- 内部结构拆解
- 不同摆放方式演示
- PWM 调速与运行状态展示

（此处插入图片 / 视频链接）

---

## Design Background & Motivation  
## 设计背景与动机

**时间：2026 年 1 月 12 日**

在日常焊接过程中，无论是 DIY 用户还是电子工程相关学习者，都会不可避免地接触到大量焊接烟气。这些烟气中往往包含松香、助焊剂残留以及细小颗粒物，长期吸入对健康存在潜在危害。

在调研过程中发现，市面上常见的焊接烟气过滤装置普遍存在以下问题：

- 体积较大，占用工作台空间  
- 价格偏高，不适合个人或 DIY 用户  
- 结构封闭，难以维护或自行改造  

因此，基于**小型化、可维护、可复用、适合个人工作台**的目标，萌生了自行设计并实现一款紧凑型焊接烟气过滤装置的想法。

在实际设计与制作过程中遇到了大量问题，包括结构强度、风道设计、噪声控制、过滤效率与体积之间的权衡等。这些问题均在实践中逐一分析并尝试解决。目前该项目仍处于持续迭代阶段，并非最终完成版本，后续仍会不断更新和优化。

---
Design Evolution & Versions
设计迭代与版本演进

This project is developed iteratively. Each version focuses on validating different aspects of mechanical design, airflow performance, noise control, and manufacturability.
The following sections document the design rationale, trade-offs, and lessons learned from each version.
<img width="1370" height="929" alt="Testing" src="https://github.com/user-attachments/assets/5604fe4a-fb58-4cbc-a8c9-f1eae82bf3f7" />

---
Version 1 – Initial Prototype
第一版原型设计（V1）

Development Time: January 12, 2026
Status: Functional prototype, ongoing evaluation
<img width="1224" height="1145" alt="image" src="https://github.com/user-attachments/assets/34d6d764-d1e5-4901-91a2-5f5d3e31f113" />
<img width="1169" height="1137" alt="image" src="https://github.com/user-attachments/assets/fbf2abe1-b3fe-410f-8ab0-b479e34bd267" />
<img width="978" height="953" alt="V2_3d_print" src="https://github.com/user-attachments/assets/88e1adca-2c0c-41a6-a3ad-bb07d476f2f5" />
![V1_total_view](https://github.com/user-attachments/assets/e932381b-8fd9-47e7-9eea-4025fc0a0cff)
![V1_dimension_1](https://github.com/user-attachments/assets/e67ab164-e65f-4b43-a467-409ac6e51d0c)
![V1_dimension_2](https://github.com/user-attachments/assets/f0b85415-b14a-4ea5-87bc-b71d9a45b0ad)

Design Objectives
设计目标

The first version focused on validating the core feasibility of a compact, desktop-sized soldering fume extraction device, with the following priorities:
Compact overall size suitable for personal workbenches
Sufficient suction performance for soldering smoke capture
Modular structure for easy disassembly and maintenance
Rapid prototyping using 3D printing

第一版主要用于验证一款紧凑型桌面焊接烟雾抽取装置的核心可行性，设计优先考虑以下方面：
体积紧凑，适合个人工作台
吸烟能力足够捕集焊接烟雾
模块化结构，便于拆装和维护
通过 3D 打印快速原型制作

---
Overall Architecture
整体结构

The system is divided into two primary modules:
Base Module – fan mounting and structural support
Transmission Roll Module – airflow guidance and filtration
This modular approach simplifies assembly, maintenance, and future design iterations.

系统分为两个主要模块：
Base Module（风机基座） – 用于风机固定和结构支撑
Transmission Roll Module（过滤与风道模块） – 用于气流导向和过滤
这种模块化设计简化了装配、维护以及未来迭代。

---
Base Module Design
Base（风机基座）设计

The Base module is responsible for mounting and supporting the centrifugal blower.
Key design considerations include:
Strict adherence to fan datasheet dimensions and mounting features
Structural strength based on the mechanical properties of 3D printing materials
Support for multiple fan orientations and placement configurations
Special attention was paid to screw load distribution, wall thickness, and vibration caused by fan operation to ensure long-term mechanical reliability.

Base 模块用于固定和支撑离心风机。
主要设计考虑：
严格遵循风机 datasheet 中的安装尺寸和特征
基于 3D 打印材料力学特性确保结构强度
支持多种风机摆放方向和安装方式
特别注意了螺丝受力分布、壁厚设计，以及风机运行时产生的振动，保证长期机械可靠性。

---
Transmission Roll Module
Transmission Roll（过滤与风道模块）

This module handles airflow redirection, filtration, and exhaust.
Design goals:
Compact and portable form factor
Detachable and replaceable filtration module
Reduced internal dead zones and ineffective airflow paths
To minimize overall size, the V1 design abandoned a traditional long, straight duct and instead adopted a short, rapidly changing airflow path.

Trade-off:
This approach increased airflow turbulence, resulting in noticeably higher noise levels during operation.
Mitigation strategy:
Fan speed reduction via PWM control
Accepting reduced peak suction in exchange for improved acoustic comfort

该模块负责气流导向、过滤和排风。
设计目标：
小型便携
可拆卸、更换的过滤模块
减少内部死角和无效风道
为控制整体尺寸，V1 设计舍弃了传统长直风道，采用短而快速变化的风道。

权衡：
这种设计增加了气流湍流，导致运行时噪声明显增加。
解决策略：
通过 PWM 调速降低风机转速
在可接受吸力范围内，以牺牲峰值性能换取更舒适的噪声水平

---
Fan Selection & Filtration Strategy
风机选型与过滤方案

A Sanyo centrifugal blower was selected due to its ability to provide high static pressure (~700 Pa at 12 V), which is critical for overcoming the pressure drop introduced by multi-stage filtration.
The filtration strategy consists of:
Pre-filter (large particle interception)
HEPA filter (fine particle capture)
Activated carbon layer (odor and gas adsorption)
This combination targets typical soldering fumes containing rosin vapors, flux residues, and fine particulates.

选用 Sanyo 离心风机，因为其可以提供高静压（约 700 Pa @ 12 V），能够克服多级过滤带来的压力损失。
过滤方案包括：
初滤（拦截大颗粒）
HEPA 滤材（拦截细小颗粒）
活性炭层（吸附气味及部分有害气体）
组合设计针对典型焊接烟雾中的松香蒸气、助焊剂残留和细微颗粒物。

---
ilter Shape & Transition Geometry
过滤形状与过渡结构

A circular filter geometry was selected after comparing square and circular alternatives, due to:
Easier replacement and sealing
Symmetric structural loading
More uniform airflow distribution
Airflow transition design referenced equivalent half-angle theory:
Ideal half-angle: < 7° to minimize flow separation
V1 equivalent half-angle: > 50° due to size constraints
Although suboptimal from a fluid dynamics perspective, the circular transition maximizes usable area and reduces severe localized vortices under tight space limitations.

在比较方形和圆形方案后，最终选择圆形过滤结构，原因如下：
更易于更换和密封
结构对称，受力均匀
气流分布更均匀
气流过渡设计参考等效半角理论：
理想半角：小于 7°，可减少流动分离
V1 等效半角：大于 50°，受空间限制
虽然从流体动力学角度并非最优，但圆形结构在有限空间内最大化可用面积，并减少局部涡流。

---
Filter Thickness & Safety Considerations
过滤厚度与安全设计

To balance filtration performance and device thickness:
Filter module thickness was limited to ≤ 30 mm
A protective mesh was added at the exhaust outlet to prevent accidental contact with the fan impeller, improving user safety.

为平衡过滤效果和设备厚度：
过滤模块厚度限制为 ≤ 30 mm
在出风口增加防护网，防止误触风机叶轮，提高使用安全性。

---
Version 2 – Optimisation & Iteration
第二版优化设计（V2）
Development Time: January 13, 2026 – January 23, 2026
Status: Completed prototype, validated through testing
![V2_total_view](https://github.com/user-attachments/assets/a61cbb47-7c22-435b-b2b6-13eeca4633ad)
<img width="931" height="1006" alt="V2_section_view" src="https://github.com/user-attachments/assets/d597bc05-a4e2-4268-ad4c-996c78f40148" />
<img width="978" height="953" alt="V2_3d_print" src="https://github.com/user-attachments/assets/f819bc76-2e8c-4ee2-acf8-3e21c3b5abf5" />

---
Identified Issues in Version 1
第一版（V1）问题总结

During assembly and testing of Version 1, several design limitations were identified:
Overly compact internal structure, leaving insufficient space for mounting control PCBs
The rear enclosure was secured with only two screws, resulting in noticeable gaps at the two unsupported corners
These mechanical issues were not fully considered during early-stage design due to limited prior experience
In practical testing, the airflow transition geometry exhibited a very large equivalent half-angle, leading to significant airflow-induced noise
These issues motivated a comprehensive redesign rather than incremental modification.

在 V1 装配和测试过程中，发现几个设计局限：
内部结构过于紧凑，无法合理安装控制电路板
后壳仅使用两颗螺丝固定，导致未支撑的两个角有明显缝隙
这些机械问题在早期设计阶段未充分考虑，主要由于经验不足
实测中，气流过渡几何结构等效半角过大，导致风噪明显
这些问题促使进行整体重新设计，而非简单改进。

---
Design Changes in Version 2
第二版（V2）设计改进
To address the limitations of V1, Version 2 introduces a scaled-up and structurally refined design.
Mechanical & Structural Improvements:
Overall enclosure dimensions increased to 120 × 120 × 120 mm (L × W × H)
Uniform corner fillets applied on all edges for improved structural consistency and aesthetics
Enclosure fabricated using grey PLA via 3D printing
Improved fastening strategy with symmetrical screw placement to eliminate corner gaps
Reserved internal space for PCB installation and cable routing

为解决 V1 问题，V2 对结构进行放大并优化设计。
机械与结构改进：
外壳尺寸增加至 120 × 120 × 120 mm（长 × 宽 × 高）
四周均匀圆角，提高结构一致性和美观
使用灰色 PLA 3D 打印制造
螺丝固定改为对称布置，消除角缝
为 PCB 安装和走线预留内部空间

Airflow & Acoustic Optimisation:
Airflow transition geometry redesigned
Equivalent half-angle reduced by approximately 20°, from over 50° in V1 to ~30° in V2
This change significantly reduced airflow turbulence and resulted in noticeably lower wind noise during operation

气流与噪声优化：
重新设计气流过渡结构
等效半角降低约 20°，从 V1 的 50°以上降至 约 30°
显著降低气流湍流，噪声明显下降

---
Cost Breakdown & Component Selection
成本与器件选型
The total cost of a single unit in Version 2 is controlled to remain below RMB 100, excluding development time.
Component	Description	Cost (RMB)
3D printed enclosure	PLA material	~13
Centrifugal blower	Sanyo 9BAM12P2J06	~50
4-pin PWM fan control	Fan PWM controller	~4.9
Custom filter elements	3 units	~30
Wiring & connectors	XH2.54 connectors
AWG18 / AWG26 wires	

成本与器件选型
V2 单机成本控制在 100 元人民币以内（不含开发时间）。
器件	              描述	              成本 (RMB)
3D 打印外壳	        PLA 材料	          ~13
离心风机	            Sanyo 9BAM12P2J06	  ~50
4-pin PWM 风机控制	  PWM 控制器	          ~4.9  
定制滤芯	3 个	                          ~33
若干线束与连接器	
XH2.54 接头
AWG18 / AWG26 线	

Testing Results & Further Optimisation
测试结果与后续优化空间
Practical testing of Version 2 showed that:
The redesigned airflow path significantly improved acoustic performance
The selected Sanyo centrifugal blower provides more suction capability than strictly required
Based on these observations, future iterations may adopt a lower-power centrifugal fan to further reduce overall cost, power consumption, and noise, while still meeting performance requirements.

V2 实测结果显示：
改进后的气流路径明显降低了噪声
所选 Sanyo 离心风机的吸力超出实际需求
未来迭代可能采用功率更低的离心风机，以进一步降低成本、功耗和噪声，同时仍能满足性能要求。

Summary
版本总结
Version 2 represents a substantial improvement over Version 1 by resolving key mechanical, acoustic, and integration issues.
This iteration demonstrates a clearer balance between performance, noise, manufacturability, cost, and practical usability, and provides a more robust foundation for future refinement.

V2 相比 V1，在机械、气流和集成方面有显著改进。
该版本在性能、噪声、可制造性、成本和实用性之间取得更好的平衡，为后续优化提供了稳固基础。
