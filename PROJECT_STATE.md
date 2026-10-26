# Xu AI Roadmap — PROJECT_STATE

**Updated:** 2026-10-25  
**Roadmap:** v1.0  
**Phase:** Week 0 — Environment Setup  
**Status:** Week 0 核心环境验收完成（PyTorch + CUDA + Autograd）；待保存实验代码与建立 GitHub 仓库

## 1. 当前目标

建立能够长期坚持的 AI 学习与工程实践机制，6–12 个月内形成面向上海大型科技公司 AI Systems / LLM Inference 等岗位的基本求职能力。长期积累数学 + 系统 + AI 的技术优势。

## 2. 当前进度

- [x] 明确职业方向及时间预算
- [x] 完成第一轮能力评估
- [x] 制定 Roadmap v1.0
- [x] 创建 ChatGPT Project
- [x] 配置 Project Instructions（用户已确认配置）
- [x] 创建并上传 PROJECT_STATE.md（初始版本）
- [x] 初步检查硬件：Intel i7-14700K、NVIDIA RTX 4070 SUPER
- [ ] 补充 RAM、磁盘容量实测值
- [x] GPU 显存实测：12282 MiB（约 12 GiB）
- [x] 安装并启动 WSL2 + Ubuntu 24.04.5 LTS
- [x] 建立 Linux 项目目录：~/projects/xu-ai-lab
- [x] 修复/更新 APT 软件包索引，可访问官方 Ubuntu 软件源
- [x] 创建并验证 Python 3.12.3 虚拟环境：~/projects/xu-ai-lab/.venv
- [x] 验证 PyTorch 与 NVIDIA CUDA 可用性（`torch.cuda.is_available() == True`）
- [x] 完成第一个 Tensor + Autograd 实验（GPU 上计算 `y=x²+2x+1`，`x=3`，`y=16`，梯度 `8`）
- [ ] 将实验保存为可复现 Python 脚本
- [ ] 确认 NumPy 安装状态（曾收到缺少 NumPy 的警告）
- [ ] 建立 GitHub 仓库

## 3. 当前项目

| Project | Status |
|---|---|
| LLM Fine-tuning Lab | Not Started |
| LLM Inference Scheduler | Not Started |
| RAG / Agent | Not Started |

## 4. Technical Backlog

- C/C++ Atomic、Memory Barrier
- Linux Memory Profiling
- Multi-Head Attention 深层机制
- GPU Memory / CUDA
- FlashAttention

## 5. 投入与运行机制

- 正常周目标：10 小时；忙碌周：3–5 小时；极忙周尽量完成 1 小时。
- 不追补中断任务；非阻塞知识问题放进 Technical Backlog。
- **本周实际投入：** 尚未统计，不估算。
- **当前运行模式：** Week 0 轻量启动。

## 6. 已验证环境信息

- Windows 主机 CPU：Intel Core i7-14700K
- GPU：NVIDIA GeForce RTX 4070 SUPER（`nvidia-smi` 报告 12282 MiB 总显存）
- NVIDIA-SMI：610.43.02；驱动支持的 CUDA UMD 版本：13.3
- PyTorch：`2.14.1+cu130`；PyTorch CUDA Runtime：13.0；Triton：3.8.0
- PyTorch GPU 可用：`torch.cuda.is_available() == True`；Tensor 设备：`cuda:0`
- Linux：WSL2 中 Ubuntu 24.04.5 LTS
- Linux 用户：xzx
- 项目目录：`/home/xzx/projects/xu-ai-lab`
- Python：3.12.3
- 虚拟环境：`/home/xzx/projects/xu-ai-lab/.venv`
- 验收命令 `which python` 输出：`/home/xzx/projects/xu-ai-lab/.venv/bin/python`
- WSL 曾提示 Windows localhost 代理不能直接镜像到 NAT 网络；APT 更新现已成功，暂不处理代理警告。

## 7. 最近一次进展

**2026-10-20：** 成功启动 Ubuntu，解决初始 APT 包索引缺失导致的 `python3.12-venv` 不可用问题，创建并激活 Python venv，验证 Python 3.12.3 正常。

**2026-10-24 晚至 2026-10-25 凌晨：** 恢复 WSL Ubuntu-24.04 与 `.venv`；通过 `nvidia-smi` 验证 GPU；安装 `torch-2.14.1+cu130`，验证 `torch.cuda.is_available()` 返回 `True`；在 `cuda:0` 运行最小 Tensor + Autograd 实验，输出 `y=16.0`、`dy/dx=8.0`。曾出现 NumPy 未安装警告；对话中未确认后续安装是否完成。

## 8. 下一步（唯一主线任务）

**把今天已验证的 GPU Tensor + Autograd 实验保存为项目内的可复现 Python 脚本，并运行验证。**

验收标准：
- 在 `~/projects/xu-ai-lab` 内保存一个 `.py` 文件；
- 在已激活的 `.venv` 中执行，输出设备 `cuda:0`、`y=16.0` 和梯度 `8.0`；
- 不依赖公司代码、日志或敏感数据。

重新打开终端后：

```bash
wsl
cd ~/projects/xu-ai-lab
source .venv/bin/activate
```

之后再建立 GitHub 仓库；NumPy 状态和 RAM/磁盘容量可以顺手检查，但不阻塞主线。

## 9. 下次恢复入口

优先阅读第 8 节，直接执行下一项任务。中断后不补课、不惩罚、不重复初始化。

> 维护说明：本文件为可替换版本。ChatGPT 生成新版本不代表 Project Source 已自动更新；替换后需重新核验。
