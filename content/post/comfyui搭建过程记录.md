---
title: Comfyui 为产品生成场景图
slug: comfyui-product-image
date: 2025-01-30T23:01:00.000Z
description: 想使用 Comfyui 搭建一个绘制产品图的工作流，记录一些过程中遇到的问题。
image: /img/comfyui-product-image.webp
categories:
  - AIGC
---
## 选用模型

iclight_sd15_fc_uset_Idm

## 工作流

## 遇到的问题

### 图片经过 Ksampler 之后尺寸发生变化（长宽从 750 变成 744）

ksampler 输出的图片尺寸必须是 8 的倍数，主要是因为 Stable Diffusion 及其相关模型的架构设计。Stable Diffusion 的 **核心模型是 UNet**，它在多个 `downsampling`（下采样）和 `upsampling`（上采样）层之间传递数据。

* **下采样（Downsampling）**：每一层都会 **缩小 2 倍**，直到到达最小的 `latent space`。
* **上采样（Upsampling）**：解码时，数据 **放大 2 倍**，恢复到目标尺寸。
* 由于是 **2 的幂次缩放（2×2, 4×4, 8×8）**，所以整个系统要求输入尺寸至少是 **8 的倍数**，否则无法对齐计算图。

### Error. No naistyles.csv found when connect comfyui web

Modify "ComfyUI-NAI-styler" in "naistyler_nodes.py" to "ComfyUI-Universal-Styler"

### No module named 'git'

```shell
cd pathtocomfyui\python_embedded
.\python.exe -m pip install -U gitpython
```

![产品原图](/img/comfyui-product-image-1.webp "产品原图")

![AI 生成背景](/img/comfyui-product-image-2.webp "AI 生成背景")

![现有背景](/img/comfyui-product-image-3.webp "现有背景")

![现有背景替换](/img/comfyui-product-image-4.webp "现有背景替换")
