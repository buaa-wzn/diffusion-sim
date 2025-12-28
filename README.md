# Safety-Critical Interactive Scenario Generation (Diffusion)

Diffusion-based **safety-critical interactive 2-D scenario generation** for autonomous vehicle testing.  
The system generates multi-agent trajectories from **minimal initial conditions** (position/velocity/acceleration) and refines them with a **conditional diffusion residual model**, aiming to produce realistic and challenging interactive scenarios for simulation, HiL, and downstream RL augmentation.

---

## Highlights

- **Minimal-condition generation**: no long history required
- **Interaction-aware encoding**: agent–agent encoder + global interaction module
- **Diffusion refinement**: denoise residual motion to improve realism and stability
- **High-throughput generation**: scalable scenario sampling for large evaluation
- **HiL validation + RL augmentation**: validate realism and improve policy safety

---

## Method Overview

Our pipeline follows a staged generation strategy:

1. **Scenario initialization** from fitted parameter distributions (e.g., cut-in statistics)
2. **Interaction encoding** for all agents at the snapshot time
3. **Coarse multi-agent trajectory decoding**
4. **Diffusion-based refinement** to correct residual errors and improve fidelity

---

## Architecture

### Overall framework
> Replace the image path after you export your figure.

![Overall framework](assets/overall_framework.png)

### Interaction encoder (AAEncoder + Global interaction)
![AA encoder](assets/aa_encoder.png)

### HiL test bench and data logging
![HiL setup](assets/hil_setup.png)


---

## Datasets

### HighD (primary)
We extract safety-critical cut-in segments and build train/val/test splits, where the test set contains unseen recordings for generalization evaluation.

---

## Results (placeholders)

### Quantitative comparison
![Main quantitative results](assets/results_table.png)

### Qualitative visualization
![Qualitative cases](assets/qualitative_cases.png)

### HiL error distribution
![HiL error distribution](assets/hil_error_distribution.png)

---

## Getting Started

This repo is under active development. The following items will be released progressively:

- [ ] TODO: environment setup instructions (PyTorch/CUDA versions, requirements)
- [ ] TODO: data preprocessing for HighD cut-in extraction + split generation
- [ ] TODO: staged training pipeline (coarse model → diffusion refinement)
- [ ] TODO: inference pipeline for batch scenario generation + export format
- [ ] TODO: evaluation scripts (trajectory-level + scenario-level metrics)
- [ ] TODO: HiL replay/logging utilities and demo
- [ ] TODO: RL augmentation scripts + evaluation in Highway / 51Sim
- [ ] TODO: pretrained checkpoints + configs for paper results

(We keep the TODO list minimal here; details will live in `docs/`.)

---
