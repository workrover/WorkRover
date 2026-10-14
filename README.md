<p align="center">
  <img src="https://workrover.github.io/workrover-logo.png" alt="WorkRover" width="360">
</p>

<h1 align="center">WorkRover: Scaling Long-Horizon Cowork Agent Training Via Recursive Environment Evolution</h1>

<p align="center">
  <a href="https://arxiv.org/abs/2610.18067"><img src="https://img.shields.io/badge/arXiv-2610.18067-b31b1b.svg" alt="arXiv paper"></a>
  <a href="https://workrover.github.io/"><img src="https://img.shields.io/badge/Project-Page-2563eb.svg" alt="Project page"></a>
  <a href="https://huggingface.co/papers/2610.18067"><img src="https://img.shields.io/badge/Hugging_Face-Paper-ffd21e.svg" alt="Hugging Face paper"></a>
</p>

<p align="center">
  🤗 <b>Data: Coming soon</b> &nbsp; | &nbsp;
  🤗 <b>SFT model: Coming soon</b> &nbsp; | &nbsp;
  🤗 <b>RL model: Coming soon</b>
</p>

The official repository for **WorkRover**, a framework for training long-horizon cowork agents through **recursive environment evolution**.

WorkRover jointly builds and validates work contexts, executable tasks, and evidence-grounded verifiers, then improves these environments using agent rollout feedback. Post-training Qwen3.5-35B-A3B with WorkRover yields **WorkRover-35B-A3B**.

> **Release status:** Data, SFT model weights, and RL model weights are **Coming soon**. Implementation and usage instructions are also being prepared. This repository currently contains the project overview and release information.

## 📰 News

- **2026-10-14:** The WorkRover repository is online. Stay tuned for data, model, and code releases.
- **2026-10-13:** The [WorkRover paper](https://arxiv.org/abs/2610.18067) is available on arXiv.

## ✨ Highlights

- **Construct aligned environments.** Harness-driven synthesis jointly builds and validates work contexts, executable tasks, and evidence-grounded verifiers using workspace state and execution feedback.
- **Evolve environments with FCR.** Factorial Compatibility Replay evaluates combinations of component revisions through dependency-closed replay and selects the smallest validated repair among tested candidates, while preserving task requirements and evaluation constraints.
- **Learn from verified progress with VTCA.** Verifier-to-Turn Credit Assignment augments trajectory-level GRPO advantages with deterministic workspace-progress signals and assigns a bounded share of positive-progress credit to prerequisite turns through recorded dependencies.

## 🧩 Framework

<p align="center">
  <img src="https://workrover.github.io/method-overview.webp" alt="WorkRover framework: work context construction, long-horizon task synthesis, verifier synthesis and validation, and recursive environment evolution." width="100%">
</p>

WorkRover connects **environment construction → validation → recursive repair → agent training**. See the [paper](https://arxiv.org/abs/2610.18067) and [project page](https://workrover.github.io/#method) for the full method.

<details>
<summary><b>Verifier-to-Turn Credit Assignment (VTCA)</b></summary>

<p align="center">
  <img src="https://workrover.github.io/turn-credit.webp" alt="VTCA pipeline: rollout sampling, terminal evaluation, workspace progress checks, prerequisite attribution, and policy updates." width="100%">
</p>

</details>

## 📊 Performance

Reported results for the backbone and WorkRover-35B-A3B:

| Model | JobBench (%) ↑ | GDPval v2 (Elo) ↑ | AutomationBench (%) ↑ | WorkBuddy Bench (Office, %) ↑ | OfficeQA Pro (%) ↑ |
| :--- | ---: | ---: | ---: | ---: | ---: |
| Qwen3.5-35B-A3B | 10.62 | 804.75 | 6.00 | 60.50 | 19.55 |
| **WorkRover-35B-A3B** | **36.89** | **1218.00** | **28.67** | **74.13** | **48.87** |
| **Improvement** | **+26.27 pp** | **+413.25 Elo** | **+22.67 pp** | **+13.63 pp** | **+29.32 pp** |

**pp** denotes percentage points. Scores follow Table 1 of the paper; see the [project results](https://workrover.github.io/#results) for the complete comparison and evaluation details.

## 🤗 Data and Models

| Resource | Description | Availability |
| :--- | :--- | :--- |
| SFT data | Supervised fine-tuning trajectories | **Coming soon** |
| RL data | Reinforcement-learning tasks and environments | **Coming soon** |
| SFT model | Checkpoint after supervised fine-tuning | **Coming soon** |
| RL model | WorkRover-35B-A3B after reinforcement learning | **Coming soon** |

Download links and data/model documentation will be added here when the resources are released.

## 🛠️ Code and Usage

**Coming soon.** Environment construction and evolution code, SFT/RL training instructions, and evaluation guidance will be added as the implementation is released.

## 📖 Citation

If you find WorkRover useful, please cite our paper:

```bibtex
@misc{he2026workrover,
  title = {WorkRover: Scaling Long-Horizon Cowork Agent Training Via Recursive Environment Evolution},
  author = {Hang He and Linting Wang and Guanming Liu and Bo Mao
            and Jinxiu Liu and Yiran Suo and Maosen Zhou and Zhiheng Xi
            and Guanting Dong and Zhou Shao and Rui Zheng and Jie Zhou
            and Chengcheng Wan and Tao Gui and Qi Zhang and Xipeng Qiu
            and Xuanjing Huang},
  year = {2026},
  eprint = {2610.18067},
  archivePrefix = {arXiv},
  primaryClass = {cs.AI},
  url = {https://arxiv.org/abs/2610.18067}
}
```
