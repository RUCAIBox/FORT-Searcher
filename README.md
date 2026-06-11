<p align="center">
    <img src="figs/logo.png" width="125" style="margin-bottom: 0.2;"/>
<p>
<h1 align="center"> FORT-Searcher: Synthesizing Shortcut-Resistant Search Tasks for Training Deep Search Agents </h1>

The official repo for "FORT-Searcher: Synthesizing Shortcut-Resistant Search Tasks for Training Deep Search Agents".

<!-- [![arXiv](https://img.shields.io/badge/arXiv-26xx.xxxxx-b31b1b.svg)](http://arxiv.org/abs/26xx.xxxxx) -->

<p align="center">
📃 <a href="">Paper (coming soon)</a> &nbsp&nbsp | &nbsp&nbsp 🏠 <a href="">Project Page (coming soon)</a>
</p>

<p align="center">
       🤗 <a href="">SFT Dataset (coming soon)</a>&nbsp&nbsp | &nbsp&nbsp🤗 <a href="">FORT-Searcher-30B-A3B (coming soon)</a>
</p>

We will release the training data, evaluation code, and model weights. Stay tuned for updates!

## Overview

Training deep search agents requires verifiable questions whose answers remain unavailable until sufficient evidence has been acquired through search. Existing synthesis methods often increase apparent difficulty by enriching graph structures, but structural complexity alone does not guarantee realized search difficulty — the intended search process can collapse through a cheaper identifying route.

**FORT** (**F**ramework **o**f Shortcut-**R**esistant **T**raining-Data Synthesis) addresses this by formalizing four actionable shortcut risks and controlling them across the full data construction pipeline:

- **Evidence Co-coverage**: Multiple clues co-occur on a single page, allowing shortcuts
- **Single-clue Selectivity**: A single clue alone suffices to identify the answer
- **Exposed Constants**: Exact strings on the question surface make downstream queries directly executable
- **Prior-knowledge Binding**: The solver names the answer from parametric knowledge before retrieval

FORT controls these risks through entity selection, evidence graph construction, question formulation, and adversarial refinement, producing training data that induces genuinely long-horizon search behavior.

## Pipeline

<p align="center">
    <img src="figs/pipeline.png" width="90%"/>
</p>

## Performance

<p align="center">
    <img src="figs/performance.png" width="75%"/>
</p>

Using SFT only on Qwen3-30B-A3B-Thinking-2507, **FORT-Searcher achieves the best overall performance among comparable-size open-source search agents**:

| Model | BrowseComp | BC-ZH | xbench-05 | xbench-10 | Seal-0 | Overall |
|:------|:---:|:---:|:---:|:---:|:---:|:---:|
| | | | | | | |
| *Proprietary Agents* | | | | | | |
| GPT-5.2-Thinking-xhigh | 65.8 | 76.1 | -- | -- | -- | -- |
| GPT-5.5 | 84.4 | -- | -- | -- | -- | -- |
| Claude Opus 4.7 | 79.3 | -- | -- | -- | -- | -- |
| | | | | | | |
| *Large-scale Open-source Agents* | | | | | | |
| GLM-5 | 75.9 | 72.7 | -- | -- | -- | -- |
| DeepSeek-V3.2 | 67.6 | 65.0 | -- | -- | -- | -- |
| Step 3.5 Flash | 69.0 | 73.7 | 83.7 | 56.3 | -- | -- |
| Kimi-K2.5-Thinking | 74.9 | -- | -- | -- | 57.4 | -- |
| Qwen3.5-397B-A17B | 78.6 | 70.3 | -- | -- | 46.9 | -- |
| Qwen3.5-122B-A10B | 63.8 | 69.9 | -- | -- | 44.1 | -- |
| | | | | | | |
| *Comparable-size Open-source Agents* | | | | | | |
| Tongyi DeepResearch | 43.4 | 46.7 | 75.0 | 47.5 | 45.8 | 51.7 |
| OpenSeekerV2 | 46.0 | 58.1 | 78.0 | 43.4 | 41.4 | 53.4 |
| REDSearcher | 57.4 | 58.2 | -- | -- | -- | -- |
| Qwen3.5-35B-A3B | 61.0 | 69.5 | 77.4 | 50.3 | 41.4 | 59.9 |
| MiroThinker-1.7-mini | 67.9 | 72.3 | 77.2 | **57.2** | **48.2** | 64.6 |
| **FORT-Searcher** | **72.2** | **75.0** | **80.8** | **57.2** | 46.0 | **66.2** |

## Release Plan

- [ ] Training Data (SFT Trajectories)
- [ ] Model Weights (FORT-Searcher-30B-A3B)
- [ ] Evaluation Code

## Citation

```bibtex
@misc{deng2026fortsearchersynthesizingshortcutresistantsearch,
      title={FORT-Searcher: Synthesizing Shortcut-Resistant Search Tasks for Training Deep Search Agents}, 
      author={Jia Deng and Yimeng Chen and Xiaoqing Xiang and Ziyang Zeng and Shuo Tang and Wayne Xin Zhao and Feng Chang and Chuan Hao and Yuan Wei and Ran Tao and Bryan Dai and Ji-Rong Wen},
      year={2026},
      eprint={2606.12087},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2606.12087}, 
}
```

## Contact

- Jia Deng: dengjia0510@outlook.com
- Yimeng Chen: yimeng.chen@kaust.edu.sa
- Wayne Xin Zhao: batmanfly@gmail.com
- Feng Chang: fchang@iquestlab.com
