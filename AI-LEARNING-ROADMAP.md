# 🧠 AI 学习地图：从实战到精通

> 定制版本 · 基于你现有的 Hermes Agent 实战经验
> 最后更新：2026-05-04

---

## 📍 你的起点

你已经会的东西（不需要从头学）：

- ✅ AI Agent 实战（Hermes、AAS 编排）
- ✅ 工具调用（Function Calling、MCP）
- ✅ Prompt Engineering（日常在用）
- ✅ RAG 概念（知识库方向）
- ✅ 各种 AI API 的使用

你需要补的东西（从"会用"到"真懂"）：

- 🔲 Transformer / Attention 底层原理
- 🔲 LLM 训练流程（预训练 → SFT → RLHF）
- 🔲 Diffusion 模型（图像生成）
- 🔲 Embedding & 向量空间（理解语义的基础）
- 🔲 Agent 架构模式（ReAct、Plan-and-Execute 等）
- 🔲 多模态（Vision、Audio）
- 🔲 前沿方向（Reasoning、World Model）

---

## 🗺️ 六个阶段

### 阶段 1：数学基础刷新（1-2 周）

> 不是让你重新学数学，是把"AI 用到的数学"捡起来

**学什么：**

| 主题 | 重点 | 为什么需要 |
|------|------|-----------|
| 线性代数 | 矩阵乘法、向量空间、特征值 | Attention 的本质就是矩阵运算 |
| 概率统计 | 贝叶斯、分布、最大似然 | 理解 LLM 输出概率、采样 |
| 微积分 | 偏导数、链式法则、梯度下降 | 训练过程的直觉 |
| 信息论 | 熵、交叉熵、KL散度 | 损失函数的本质 |

**用什么资料：**

- 📺 3Blue1Brown《线性代数的本质》（YouTube，有中文字幕）
- 📺 3Blue1Brown《微积分的本质》
- 📖 《深度学习的数学》（神嶌敏正）——小白友好，图多

**怎么做笔记：**

- **MarginNote**：每个视频拉 3 个核心概念卡片
- **GoodNotes**：手写推导一遍矩阵乘法、梯度下降的直觉图
- **Obsidian**：建 `MATH-FUNDAMENTALS` 页面，链接到后面每个阶段

**⚠️ 常见坑：** 不要试图把数学学完美再往下走。够用就行，遇到不懂的再回来补。

---

### 阶段 2：深度学习核心（2-3 周）

> 理解"神经网络"到底是什么

**学什么：**

1. **神经网络基础**
   - 神经元、层、激活函数（ReLU、GELU）
   - 前向传播 vs 反向传播
   - 损失函数 & 优化器（Adam）

2. **核心架构演进**
   - CNN（为什么图像用卷积）
   - RNN / LSTM（为什么序列需要记忆）
   - Transformer（为什么它取代了 RNN）

3. **训练基础**
   - Batch、Epoch、Learning Rate
   - 过拟合 / 欠拟合
   - 正则化（Dropout、Layer Norm）

**用什么资料：**

- 📺 Andrej Karpathy《Neural Networks: Zero to Hero》（YouTube）
  - 第 1-4 集：micrograd → backprop → makemore
  - **强烈推荐**，从代码层面理解，不是黑盒
- 📖 《动手学深度学习》（d2l.ai）——有中文版，代码可运行
- 📺 李沐《动手学深度学习》（B站，逐行讲代码）

**怎么做笔记：**

- **MarginNote**：每个架构做一个对比卡片（CNN vs RNN vs Transformer）
- **GoodNotes**：手画 Transformer 的完整结构图（这一步极其重要）
- **Obsidian**：
  - 建 `DL-ARCHITECTURES` 页面
  - 链接：CNN → 图像理解 → Diffusion
  - 链接：RNN → 序列 → Transformer → LLM

**⚠️ 常见坑：** Karpathy 的代码一定要自己跟着敲一遍，光看不练等于没学。

---

### 阶段 3：Transformer & Attention（2-3 周）⭐ 最核心

> 这是整个现代 AI 的基石，值得花最多时间

**学什么：**

1. **Self-Attention 机制**
   - Q、K、V 到底是什么（用你自己的话解释）
   - 为什么要做点积？
   - 为什么要除以 √d_k？
   - Softmax 在这里的作用

2. **完整 Transformer 架构**
   - Multi-Head Attention
   - Positional Encoding（为什么位置信息很重要）
   - Feed Forward Network
   - Residual Connection & Layer Norm
   - Encoder-Decoder 结构

3. **为什么 Transformer 这么强**
   - 并行计算 vs RNN 的串行
   - 全局感受野
   - 可扩展性（Scaling Law）

**用什么资料：**

- 📄 原论文：《Attention Is All You Need》（Vaswani et al., 2017）
- 📺 Jay Alammar《The Illustrated Transformer》（jalammar.github.io）
- 📺 Andrej Karpathy《Let's build GPT: from scratch》（YouTube）
  - **从零实现一个 mini GPT**，这是理解 LLM 最好的方式
- 📄 Lilian Weng 的博客：lilianweng.github.io（Transformers 系列文章）

**怎么做笔记：**

- **GoodNotes**（最关键的一步）：
  - 手写 Attention 公式的每一步推导
  - 画 Q·K^T 的矩阵运算过程
  - 写"为什么这样设计"而不是"公式是什么"
  - ❓ 丢给 AI 的问题示例：
    - "如果不用 softmax，直接用点积值会怎样？"
    - "Multi-Head 为什么要多头而不是一个大的？"
    - "Positional Encoding 为什么用 sin/cos 而不是直接嵌入数字？"

- **MarginNote**：
  - 原论文高亮 10 个关键设计决策
  - 每个决策做一个"为什么"卡片

- **Obsidian**：
  - 建 `TRANSFORMER` 核心页面
  - 知识图谱结构：
    ```
    Transformer
    ├── Self-Attention → Q/K/V → 点积 → Softmax
    ├── Multi-Head Attention → 多个视角
    ├── Positional Encoding → 序列位置
    ├── Feed Forward → 非线性变换
    ├── Residual Connection → 梯度流通
    └── Layer Norm → 训练稳定
    ```
  - 链接到下游：
    - Attention → LLM（Decoder-only）
    - Attention → Diffusion（Cross-Attention）
    - Attention → Vision（ViT）

**⚠️ 常见坑：** 不要背公式。要理解"为什么要这样设计"。每个公式背后都有一个工程直觉。

---

### 阶段 4：大语言模型 LLM（3-4 周）

> 理解 ChatGPT 背后的完整故事

**学什么：**

1. **LLM 的进化路线**
   - GPT 系列（1 → 2 → 3 → 3.5 → 4 → 4o）
   - LLaMA / Mistral / DeepSeek 等开源模型
   - Decoder-only 为什么赢了 Encoder-Decoder

2. **训练流程（三个阶段）**
   - **预训练（Pre-training）**：预测下一个 token
     - 数据从哪来？
     - 训练要多少钱？
     - Scaling Law（更多数据/参数 → 更强）
   - **监督微调（SFT）**：学会对话
     - 为什么需要 SFT？
     - 指令数据的质量 > 数量
   - **人类反馈对齐（RLHF / DPO）**
     - 为什么模型会"有害"？
     - Reward Model 是怎么训练的？
     - DPO 为什么更简单？

3. **推理 & 应用**
   - Tokenization（BPE）
   - Temperature / Top-p 采样
   - Context Window & 滑动窗口注意力
   - 推理优化（KV Cache、量化）

**用什么资料：**

- 📺 Andrej Karpathy《Intro to Large Language Models》（1 小时精华）
- 📺 Andrej Karpathy《State of GPT》（OpenAI 演讲）
- 📄 Meta《LLaMA》论文 + Meta《Llama 3》技术报告
- 📄 DeepSeek《DeepSeek-V2》论文（MoE 架构）
- 📄 DPO 原论文《Direct Preference Optimization》
- 📖 《Build a LLM from Scratch》（Sebastian Raschka）——2024 新书，强烈推荐

**怎么做笔记：**

- **GoodNotes**：
  - 画完整的 LLM 训练流程图（预训练 → SFT → RLHF）
  - 手写 BPE 分词的过程（一个具体例子）
  - 写"如果我是 OpenAI，我会怎么设计训练流程"

- **MarginNote**：
  - 每篇论文拉 3 个核心创新点
  - GPT-1/2/3/4 做一个演进时间线卡片

- **Obsidian**：
  - 建 `LLM` 核心页面
  - 知识图谱：
    ```
    LLM
    ├── 预训练 → Next Token Prediction → Scaling Law
    ├── SFT → 指令跟随 → 对话能力
    ├── RLHF/DPO → 对齐 → 安全性
    ├── 推理优化 → KV Cache → 量化
    ├── 架构 → MoE (DeepSeek) → 稀疏激活
    └── 应用 → 你在用的 Hermes 就是这一层
    ```

**⚠️ 常见坑：** 不要陷入论文细节。先理解大图，再按需深入。

---

### 阶段 5：多模态 & 生成模型（3-4 周）

> 理解图像生成、语音、视频的底层逻辑

**学什么：**

1. **Diffusion 模型（图像生成）**
   - 扩散过程（加噪 → 去噪）
   - U-Net 架构
   - Classifier-Free Guidance
   - Stable Diffusion / DALL-E / Flux 的区别
   - 你老婆在用的可灵/即梦，底层是什么

2. **Vision & 多模态**
   - ViT（Vision Transformer）
   - CLIP（图文对齐）
   - GPT-4V / GPT-4o 的多模态方案
   - Sora（视频生成）

3. **语音模型**
   - Whisper（语音识别）——你已经在用 mlx_whisper
   - TTS（语音合成）
   - MusicGen（音乐生成）

4. **Embedding & 向量空间**
   - 什么是 Embedding？（用你自己的话）
   - 余弦相似度
   - 向量数据库（RAG 的基础）

**用什么资料：**

- 📺 Lilian Weng 博客：Diffusion Models 系列
- 📄 DDPM 原论文《Denoising Diffusion Probabilistic Models》
- 📺 Yannic Kilcher 论文解读频道（YouTube）
- 📄 CLIP 原论文
- 📺 3Blue1Brown《注意力机制可视化》系列

**怎么做笔记：**

- **GoodNotes**：
  - 手画扩散过程（一张干净的图 → 逐步加噪 → 逐步去噪）
  - 画 U-Net 的结构（编码器-解码器 + Skip Connection）
  - 写"Diffusion 和 GAN 的本质区别是什么"

- **Obsidian**：
  - 建 `GENERATIVE-MODELS` 页面
  - 知识图谱：
    ```
    生成模型
    ├── Diffusion → DDPM → Stable Diffusion → DALL-E 3 → Flux
    │                  ├── U-Net → 去噪网络
    │                  ├── Cross-Attention → 文本控制图像
    │                  └── CFG → 引导生成质量
    ├── GAN → (被 Diffusion 取代的方案)
    ├── VAE → (Latent Space 的基础)
    ├── CLIP → 图文对齐 → 多模态
    └── 视频 → Sora → 可灵 → 时空注意力
    ```

**⚠️ 常见坑：** Diffusion 数学比较重，先理解直觉（"逐步去噪"），再看数学公式。

---

### 阶段 6：Agent & 前沿（持续学习）

> 你已经在这里了，现在补理论让实战更扎实

**学什么：**

1. **Agent 架构模式**
   - ReAct（Reasoning + Acting）
   - Plan-and-Execute
   - Reflection & Self-Correction
   - Multi-Agent 协作
   - 你在用的 Hermes 属于哪种模式？

2. **RAG（检索增强生成）**
   - Embedding → 向量数据库 → 检索 → 注入 Context
   - Chunk 策略、Reranking
   - GraphRAG、Agentic RAG
   - 为什么简单的 RAG 不够用？

3. **推理能力（2024-2025 前沿）**
   - Chain-of-Thought
   - o1/o3 的推理模式（System 2 Thinking）
   - Test-Time Compute
   - DeepSeek-R1（强化学习做推理）

4. **世界模型 & 未来方向**
   - World Model（Sora、Genie）
   - 具身智能（Embodied AI）
   - AI 安全 & 对齐

**用什么资料：**

- 📄 ReAct 原论文
- 📄《A Survey on Large Language Model based Autonomous Agents》
- 📄 DeepSeek-R1 技术报告
- 📄 GraphRAG 论文（Microsoft）
- 📄 o1 系统卡片（OpenAI）
- 📺 Andrew Ng《AI Agentic Workflows》演讲

**怎么做笔记：**

- **Obsidian**（主要在这里）：
  - 建 `AGENT-ARCHITECTURES` 页面
  - 知识图谱：
    ```
    Agent
    ├── 单 Agent → ReAct → Plan-Execute → Reflection
    ├── 多 Agent → 编排 → Hermes/AAS
    ├── 工具 → Function Calling → MCP
    ├── 记忆 → 短期(Context) → 长期(Vector DB)
    └── 推理 → CoT → o1(Test-Time Compute) → DeepSeek-R1
    ```

---

## 📅 时间规划

```
月份        阶段                        周时投入
─────────────────────────────────────────────
第 1-2 周   ① 数学基础刷新               5-8h
第 3-5 周   ② 深度学习核心               8-10h
第 6-8 周   ③ Transformer & Attention   10-12h ⭐重点
第 9-12 周  ④ 大语言模型 LLM             8-10h
第 13-16 周 ⑤ 多模态 & 生成模型          8-10h
第 17 周+   ⑥ Agent & 前沿（持续）       按需
```

**总计约 4-5 个月打通基础**，之后进入"按需深入"模式。

---

## 📚 资料优先级（如果你只能选 5 个）

| 优先级 | 资料 | 理由 |
|--------|------|------|
| 🥇 | Karpathy《Let's build GPT》 | 从零理解 LLM，实战代码 |
| 🥈 | Karpathy《Neural Networks: Zero to Hero》 | DL 基础从代码层面理解 |
| 🥉 | Jay Alammar《Illustrated Transformer》 | 最直观的 Transformer 图解 |
| 4 | Sebastian Raschka《Build a LLM from Scratch》 | LLM 训练全流程 |
| 5 | Lilian Weng 博客 | 每个主题都有高质量总结 |

---

## 🔄 笔记工作流（最终版）

```
PDF / 视频 / 论文
      ↓
  MarginNote（拆）
  ├─ 高亮关键概念
  ├─ 做卡片（概念 / 定义 / 例子）
  ├─ 每篇产出：3个核心概念 + 1个结构图 + 1个不懂的点
      ↓
  GoodNotes（懂）
  ├─ 手写推导 / 画图
  ├─ 写"用自己的话解释"
  ├─ 不懂的问题 → 丢给 AI
      ↓
  Obsidian（沉淀）
  ├─ 结构化笔记
  ├─ 知识图谱链接
  ├─ 每个知识点：小白解释 + 实际例子 + 解决了什么问题
      ↓
  AI 深化（Hermes / GPT）
  ├─ 提问不懂的点
  ├─ 让 AI 出测试题
  ├─ 讨论"为什么这样设计"
```

---

## 🎯 检验标准

每个阶段结束后，你应该能做到：

**阶段 1-2：** 能用一句话解释"神经网络在做什么"，能画出一个简单的反向传播过程

**阶段 3：** 能给别人讲清楚 Attention 是什么，能从零手写一个 mini Attention（不需要跑通）

**阶段 4：** 能解释"为什么 ChatGPT 有时候会胡说八道"，能说清楚 RLHF 解决了什么问题

**阶段 5：** 能解释"Diffusion 为什么能生成图像"，能说清楚你老婆用的 AI 绘图工具的底层原理

**阶段 6：** 能解释 Hermes Agent 的架构选择为什么合理，能评判不同 Agent 方案的优劣

---

*这份地图会随着你的学习进度持续更新。每学完一个阶段，回来标记完成 ✅。*
