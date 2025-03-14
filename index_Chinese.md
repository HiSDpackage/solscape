---
layout: single
permalink: /index_Chinese
title: "soluscape-1.0: 使用高阶鞍点动力学（HiSD）构建解景观"
excerpt: "快速入门指南"
sidebar:
    nav: docs_Chinese
toc: true
toc_sticky: true
mathjax: true

---
# 概要

`soluscape` 是一个基于高阶鞍点动力学（HiSD）构建解景观的Python工具包。该工具包支持动力系统中鞍点的数值计算及其层级结构分析，简化了鞍点搜索流程，提供灵活的参数设置和丰富的可视化功能。

## 功能特性

- **多算法实现**：
  - `HiSD`: 梯度系统的高阶鞍点动力学算法
  - `GHiSD`: 非梯度系统的普适高阶鞍点动力学算法
- **多加速算法实现**：
  - `HiSD`: 基础鞍点搜索算法
  - `NHiSD`: 带Nesterov加速的HiSD算法
  - `HHiSD`: 带Heavy Ball加速的HiSD算法
- **灵活特性**：
  - 支持多种输入形式（梯度函数或能量函数，表达式字符串或函数句柄）
  - 自动校验参数有效性
  - 模块化类设计方便扩展
  - 便捷的搜索轨迹、热力图和鞍点连接图绘制
  - 重要计算结果自动保存
  - 支持处理函数系统
  - 可自动合并相同鞍点

## 安装指南

1. 克隆仓库：
   ```bash
   git clone https://github.com/HiSDpackage/soluscape
   cd soluscape-1.0

2. 安装依赖:
   ```bash
   pip install -r requirements.txt
   ```

## 快速入门

以下是使用 soluscape-1.0 的基本工作流程：

1. **添加路径**:
   使用以下Python代码将目录添加到系统路径：

   ```python
   import sys
   sys.path.append('/path/to/soluscape-1.0')
   ```

   将  `'/path/to/soluscape-1.0'` 替换为实际的 `soluscape-1.0` 目录路径。

2. **导入模块**:
   ```python
   from soluscape import Landscape
   ```

3. **初始化对象**:
   ```python
   landscape = Landscape(**kwargs)
   ```

4. **运行计算**:
   ```python
   landscape.Run()
   ```

5. **绘制图形**:
   ```python
   landscape.DrawTrajectory(**kwargs)
   landscape.DrawConnection(**kwargs)
   ```

6. **保存结果**:
   ```python
   mylandscape.Save(filepath, fileformat)
   ```

7. **重启计算**:
   ```python
   landscape.RestartFromPoint(RestartPoint, MaxIndex)
   landscape.RestartFromSaddle(BeginID, Perturbation, MaxIndex)
   ```

更多详细用法请参考[documentation](https://github.com/HiSDpackage/soluscape/blob/main/doc/Documentation.pdf)文件。（您也可以在左侧的["教程"](https://hisdpackage.github.io/soluscape/Tutorial/Tutorial_overview)部分查看）

## 依赖项

HiSD 依赖以下Python库：

内置包：
- `copy`
- `sys`
- `warnings`
- `inspect`
- `json`
- `itertools`
- `math`
- `pickle`

第三方包：
- `numpy-2.2.3`
- `scipy-1.15.2`
- `sympy-1.13.3`
- `matplotlib-3.10.0`
- `networkx-3.4.2`

## 示例

[GitHub仓库](https://github.com/HiSDpackage/soluscape)的`gallery`目录中提供以下示例Jupyter Notebook文件：（您也可以在左侧的["示例"](https://hisdpackage.github.io/soluscape/Examples/Examples_overview)部分查看）

- `Ex_1_Butterfly.ipynb`
- `Ex_2_MullerBrownPotential.ipynb`
- `Ex_3_Cubic.ipynb`
- `Ex_4_PhaseField.ipynb`



---

感谢使用`soluscape`！我们欢迎任何反馈或建议。

