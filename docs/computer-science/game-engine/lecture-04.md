# Lecture 04：游戏引擎中的渲染实践

- Objects with one type of effect
- Focus on representation and math correctness
- No strict performance requirements
  - Realtime(30 FPS) / interactive(10 FPS) / offline
  - Out-of-core rendering

## GPU 架构

GPU v.s. CPU -> SIMT v.s. SIMD

GPU Architecture:

- GPC(Graphics Processing Cluster)
- SM(Streaming Multiprocessor)
- Texture Units
- CUDA Core
- Warp

Data Flow from CPU to GPU

CPU and Main Memory

- Data Load / Unload
- Data Preparation

CPU to GPU

- High Latency
- Limited Bandwidth

GPU and Video Memory

- High Performance Parallel Rendering

!!! info "Tips"

    Always minimize data transfer between CPU and GPU when possible.

    尽可能数据单向传输，同时尽可能不要从显卡中读数据

GPU Bounds and Performance

- Memory Bounds
- ALU Bounds
- TMU(Texture Memory Unit) Bounds
- BW(Bandwidth) Bounds

## 可渲染物体

- Material
- Texture
- Shader
- Mesh/Submesh
- Resource Pool

## 可见性裁剪（Visibility Culling）

只渲染可见的物体，在摄像机锥形视野内的物体

## 贴图压缩

Block Compression

## Cluster-based Mesh Pipeline
