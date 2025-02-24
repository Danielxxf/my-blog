---
title: Comfyui 为产品生成场景图
slug: comfyui-product-image
date: 2025-01-30T23:01:00.000Z
description: 想使用 Comfyui 搭建一个绘制产品图的工作流，记录一些过程中遇到的问题。
image: /img/comfyui-product-image.webp
categories:
  - AIGC
---
### 选用模型
iclight_sd15_fc_uset_Idm
### 工作流


### 遇到的问题
#### Error. No naistyles.csv found when connect comfyui web
Modify "ComfyUI-NAI-styler" in "naistyler_nodes.py" to "ComfyUI-Universal-Styler"
#### No module named 'git'
cd pathtocomfyui\python_embedded

.\python.exe -m pip install -U gitpython
