---
title: "ESIT-D2I 2026 · Charting the Path to Bifröst"
excerpt: "Third-place solution for robust CSI localisation and machine unlearning under realistic data corruption."
domain: "Wireless AI · Competition"
stack: "PyTorch · Transformer · BYOL/SIGReg · DICHASUS"
order: 1
header:
  overlay_color: "#0b2d45"
---

## Challenge

The IEEE Information Theory Society competition addressed CSI-based localisation under noisy and partially corrupted measurements. The second task focused on removing the influence of unreliable users from a pretrained model without retraining it from scratch.

## Contribution

- Built an array-token Transformer for wireless localisation.
- Used BYOL and SIGReg self-supervision before supervised fine-tuning.
- Added masked refinement and robust fine-tuning for phase offsets, antenna dropout, trajectory corruption and other realistic artifacts.
- Investigated retain-only fine-tuning and Fisher-based dampening for machine unlearning.

## Outcome

The solution achieved **third place** across the robustness and machine-unlearning challenges.

[View the public repository](https://github.com/TheoriginalMMM/esit-d2i-2026-bifrost){: .btn .btn--primary }

