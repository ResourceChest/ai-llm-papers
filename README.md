# AI & LLM Papers

[![License: MIT](https://img.shields.io/github/license/ResourceChest/ai-llm-papers)](LICENSE)
[![Last Commit](https://img.shields.io/github/last-commit/ResourceChest/ai-llm-papers)](https://github.com/ResourceChest/ai-llm-papers/commits/main)
[![GitHub Stars](https://img.shields.io/github/stars/ResourceChest/ai-llm-papers)](https://github.com/ResourceChest/ai-llm-papers/stargazers)
[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)](https://github.com/ResourceChest/.github/blob/main/CONTRIBUTING.md)
[![Link Check](https://github.com/ResourceChest/ai-llm-papers/actions/workflows/link-check.yml/badge.svg)](https://github.com/ResourceChest/ai-llm-papers/actions/workflows/link-check.yml)

A curated reading list of foundational and frontier research papers in AI and large language models. Covers the key papers behind the architectures, training methods, and techniques that power modern LLMs -- from the original Transformer to today's reasoning and retrieval systems.

## Contents

- [Architecture & Foundations](#architecture--foundations)
- [Memory & Efficiency](#memory--efficiency)
- [Training, Alignment & RL](#training-alignment--rl)
- [Reasoning & Prompting](#reasoning--prompting)
- [Retrieval & Tools](#retrieval--tools)
- [More from ResourceChest](#more-from-resourcechest)
- [Contributing](#contributing)
- [Disclaimer](#disclaimer)

---

## Architecture & Foundations

- [**Attention Is All You Need**](https://arxiv.org/abs/1706.03762) (Vaswani et al., 2017) -- The original Transformer. Introduced self-attention as a replacement for recurrence, fundamentally reshaping NLP and beyond.

- [**BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding**](https://arxiv.org/abs/1810.04805) (Devlin et al., 2018) -- Bidirectional pretraining with masked language modeling. Set new benchmarks across a wide range of NLP tasks.

- [**Language Models are Few-Shot Learners**](https://arxiv.org/abs/2005.14165) (Brown et al., 2020) -- GPT-3. Demonstrated that scaling to 175B parameters enables strong in-context learning without fine-tuning.

- [**Scaling Laws for Neural Language Models**](https://arxiv.org/abs/2001.08361) (Kaplan et al., 2020) -- Empirical scaling laws showing predictable relationships between model size, data, compute, and performance.

- [**Training Compute-Optimal Large Language Models**](https://arxiv.org/abs/2203.15556) (Hoffmann et al., 2022) -- Chinchilla. Showed that most LLMs were undertrained for their size, establishing optimal compute-to-data ratios.

- [**LLaMA: Open and Efficient Foundation Language Models**](https://arxiv.org/abs/2302.13971) (Touvron et al., 2023) -- Demonstrated that smaller, well-trained open models can match much larger proprietary ones, catalyzing the open-source LLM ecosystem.

- [**Switch Transformers: Scaling to Trillion Parameter Models with Simple and Efficient Sparsity**](https://arxiv.org/abs/2101.03961) (Fedus et al., 2022) -- Mixture-of-Experts with simplified routing. Showed MoE can scale Transformers to trillion parameters efficiently.

- [**GShard: Scaling Giant Models with Conditional Computation and Automatic Sharding**](https://arxiv.org/abs/2006.16668) (Lepikhin et al., 2020) -- Early large-scale MoE system with automatic parallelism for training 600B+ parameter models.

- [**DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model**](https://arxiv.org/abs/2405.04434) (DeepSeek-AI, 2024) -- Introduced Multi-head Latent Attention (MLA) and DeepSeekMoE architecture for efficient high-performance language modeling.

- [**DeepSeek-V3 Technical Report**](https://arxiv.org/abs/2412.19437) (DeepSeek-AI, 2024) -- Scaled MLA and DeepSeekMoE further with auxiliary-loss-free load balancing and multi-token prediction training.

## Memory & Efficiency

- [**Engram: Conditional Memory via Scalable Lookup**](https://arxiv.org/abs/2505.08254) (DeepSeek, 2025) -- Adds an N-gram-based O(1) lookup module as a new sparsity axis alongside MoE. Introduces multi-head hashing (MHH), tokenizer compression, and contextualized gating.

- [**FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness**](https://arxiv.org/abs/2205.14135) (Dao et al., 2022) -- IO-aware exact attention algorithm that reduces memory usage from quadratic to linear while being 2-4x faster than standard attention.

- [**FlashAttention-2: Faster Attention with Better Parallelism and Work Partitioning**](https://arxiv.org/abs/2307.08691) (Dao, 2023) -- Improved FlashAttention with better GPU occupancy, achieving up to 2x additional speedup over the original.

- [**GQA: Training Generalized Multi-Query Transformer Models from Multi-Head Checkpoints**](https://arxiv.org/abs/2305.13245) (Ainslie et al., 2023) -- Grouped-Query Attention. Interpolates between multi-head and multi-query attention for better quality-speed tradeoff during inference.

- [**Multi-Head Attention as Mixture-of-Head Attention**](https://arxiv.org/abs/2404.07454) (Jin et al., 2024) -- MoH. Treats attention heads as experts, dynamically activating only the most relevant heads per token to reduce compute.

- [**Native Sparse Attention: Hardware-Aligned and Natively Trainable Sparse Attention**](https://arxiv.org/abs/2502.11089) (DeepSeek, 2025) -- NSA. Hardware-aligned sparse attention that is natively trainable end-to-end, achieving substantial speedups over full attention on 64k+ sequences while matching or exceeding full attention quality on general benchmarks and long-context tasks.

- [**TurboQuant: Online Vector Quantization with Near-optimal Distortion Rate**](https://arxiv.org/abs/2504.19874) (Zandieh et al., 2025) -- Google's lightweight, accelerator-friendly quantization method for KV cache compression. Achieves quality-neutral 3.5-bit and near-lossless 2.5-bit quantization per channel using a two-stage MSE + QJL approach.

## Training, Alignment & RL

- [**Training language models to follow instructions with human feedback**](https://arxiv.org/abs/2203.02155) (Ouyang et al., 2022) -- InstructGPT / RLHF. Established the SFT + reward model + PPO pipeline for aligning language models to human intent.

- [**Direct Preference Optimization: Your Language Model is Secretly a Reward Model**](https://arxiv.org/abs/2305.18290) (Rafailov et al., 2023) -- DPO. Eliminated the need for a separate reward model by directly optimizing the policy from preference data.

- [**DeepSeekMath: Pushing the Limits of Mathematical Reasoning in Open Language Models**](https://arxiv.org/abs/2402.03300) (Shao et al., 2024) -- Introduced Group Relative Policy Optimization (GRPO), the RL algorithm that powers DeepSeek-R1's reasoning capabilities.

- [**DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning**](https://arxiv.org/abs/2501.12948) (DeepSeek-AI, 2025) -- RL-trained reasoning model that develops chain-of-thought and self-verification behaviors through pure reinforcement learning.

## Reasoning & Prompting

- [**Chain-of-Thought Prompting Elicits Reasoning in Large Language Models**](https://arxiv.org/abs/2201.11903) (Wei et al., 2022) -- Showed that prompting LLMs to think step-by-step dramatically improves performance on reasoning tasks.

- [**Self-Consistency Improves Chain of Thought Reasoning in Language Models**](https://arxiv.org/abs/2203.11171) (Wang et al., 2022) -- Sample multiple reasoning paths and take the majority answer. A simple technique that significantly boosts CoT accuracy.

- [**Tree of Thoughts: Deliberate Problem Solving with Large Language Models**](https://arxiv.org/abs/2305.10601) (Yao et al., 2023) -- Generalizes CoT by exploring multiple reasoning branches with search, enabling LLMs to backtrack and plan.

## Retrieval & Tools

- [**Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks**](https://arxiv.org/abs/2005.11401) (Lewis et al., 2020) -- RAG. Combined a pretrained retriever with a generator, establishing the foundation for grounding LLMs in external knowledge.

- [**Toolformer: Language Models Can Teach Themselves to Use Tools**](https://arxiv.org/abs/2302.04761) (Schick et al., 2023) -- Trained LLMs to autonomously decide when and how to call external tools (calculators, search, APIs) mid-generation.

---

## More from ResourceChest

| Repository | Description |
|:-----------|:------------|
| [AI Agents](https://github.com/ResourceChest/ai-agents) | Practical AI agents, frameworks, and tools for developers |
| [Chrome Privacy Extensions](https://github.com/ResourceChest/chrome-privacy-extensions) | Curated Chrome extensions for privacy and security |
| [Custom GPTs](https://github.com/ResourceChest/custom-gpts) | Community-curated catalog of useful Custom GPTs with ratings |
| [FinOps Tools](https://github.com/ResourceChest/finops-tools) | Vendor-neutral tools for cloud cost optimization |
| [Local-First Tools](https://github.com/ResourceChest/local-first-tools) | Local-first, offline-capable, privacy-respecting tools |
| [Dev Tools (No Signup)](https://github.com/ResourceChest/dev-tools-no-signup) | Free developer tools that work instantly without an account |

> **[Follow ResourceChest](https://github.com/ResourceChest)** for more curated resource collections.

---

## Contributing

Want to suggest a paper? Pull requests are welcome. See our [CONTRIBUTING.md](https://github.com/ResourceChest/.github/blob/main/CONTRIBUTING.md) for guidelines.

**When adding a paper:**
- Link directly to the arXiv abstract page (not the PDF)
- Include authors and year
- Write a one-to-two sentence summary explaining why the paper matters
- Place it in the most relevant category

## Disclaimer

This list is curated based on personal research and community input. Inclusion does not imply endorsement. Paper summaries are intentionally brief -- always read the original work for full context.
