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

## Overall Architecture  
## 整体结构设计思路

在当前版本中，整机结构被划分为两个主要模块：

- **Base（风机基座部分）**
- **Transmission Roll（过滤与风道模块）**

这种模块化拆分的目的是便于结构设计、装配、维护以及后期针对不同使用场景进行改进。

---

## Base Module  
## Base（风机基座）设计

Base 部分主要用于风机的固定与承载，其设计基于以下几个原则：

- 严格参考风机外壳结构及 datasheet 中的安装尺寸  
- 结合 3D 打印材料的力学特性，保证整体强度与稳定性  
- 为多种风机摆放方式预留安装可能性  

在结构设计中，充分考虑了螺丝受力、壁厚分布以及风机运行时产生的振动问题，以确保长期使用的可靠性。

---

## Transmission Roll Module  
## Transmission Roll（过滤与风道模块）

Transmission Roll 部分主要负责烟气的引导、过滤以及气流输出。

在设计时，重点考虑了以下目标：

- 小型化与便携性  
- 模块可拆卸、可更换  
- 尽量减少内部死角与无效风道  

为了实现整体体积的控制，该版本舍弃了传统的**长直风道设计**，而采用了**快速变化的短风道结构**。  
这种设计的代价是气流湍流增加，导致运行噪声明显偏大。

针对这一问题，目前采用的解决方式是：

- 通过 PWM 调速方式降低风机转速  
- 在可接受吸力范围内，以牺牲部分最大性能来换取噪声控制  

---

## Fan Selection & Filtration Strategy  
## 风机选型与过滤策略

在风机选型阶段，重点考虑了过滤系统所带来的阻力损失。

通过查询焊接烟气的成分资料，可以得知其中主要包含：

- 松香挥发物  
- 助焊剂残留  
- 较多的细小颗粒物  

因此，过滤结构采用多级过滤方案：

1. 初滤棉（拦截大颗粒）  
2. HEPA 滤材（拦截细小颗粒）  
3. 活性炭（吸附气味与部分有害气体）  

---

## Air Velocity & Filter Size  
## 风速与过滤尺寸设计

在设计过程中，重点关注了**过滤介质处的风速问题**。

如果风速过高：

- 气流可能直接穿透过滤材料  
- 过滤效率显著下降  
- 滤材寿命大幅缩短  

最初版本中，过滤装置直径设计为 **50 mm**。  
通过计算后发现，该尺寸下过滤面风速过高，不符合长期使用需求。

经过调整与权衡，理想的过滤面风速应控制在：

> **约 1.5 – 2.5 m/s**

因此，最终将过滤装置直径调整为 **97 mm**，以降低风速并提升过滤效率，同时兼顾整体体积控制。

---

## Filter Shape & Transition Design  
## 过滤形状与过渡设计

在过滤模块的形状选择上，对比了方形、圆形等方案。

最终选择圆形结构，主要基于以下考虑：

- 便于过滤模块的快速更换  
- 结构对称，受力与气流分布更均匀  
- 更利于进风口向过滤区域的平滑过渡  

在风道设计中参考了**等效半角**的计算方法：

- 理想状态下，过渡半角应小于 **7°**，以减少流动分离与湍流  
- 但在便携性与小型化的限制下，当前版本的等效半角已超过 **50°**  

尽管如此，圆形结构仍有助于最大化利用整个过渡区域，减少局部涡流，并尽量避免明显的流动分离。

---

## Filter Thickness & Safety  
## 过滤厚度与安全设计

在整体厚度控制的前提下，当前版本计划使用：

- **厚度不超过 30 mm 的过滤模块**

以平衡过滤效果与设备整体尺寸。

在出风口位置，增加了一层片状防护网结构，用于防止误触风机叶轮，从而降低潜在的使用风险。

---

## Current Status & Future Work  
## 当前状态与后续计划

目前版本仍存在以下问题与改进空间：

- 噪声水平仍有优化余地  
- 风道形状与过渡区域可进一步改进  
- 过滤模块规格仍可继续优化  

该项目将持续迭代，并根据实际使用体验不断调整设计方案。
