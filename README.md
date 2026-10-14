# Short Story: Autoencoder-based Deep Clustering

**Course:** CMPE 255 — Data Mining (Short Story Assignment, individual)

One-line summary: a from-scratch explainer of how autoencoders learned to cluster — the building blocks, the three ways to train them, the ablation that shows your clustering metric can lie to you, and where the field is headed in 2025.

## The paper

- **Title:** An Introductory Survey to Autoencoder-based Deep Clustering — Sandboxes for Combining Clustering with Deep Learning
- **Authors:** Collin Leiber, Lukas Miklautz, Claudia Plant, Christian Böhm
- **arXiv:** [2504.02087](https://arxiv.org/abs/2504.02087) — submitted 2 Apr 2025, revised 26 May 2025
- **Status:** arXiv preprint survey (tutorial-style); no venue acceptance verified as of Oct 2026

## Companion reading (adds the "more survey content" the rubric asks for)

| Paper | arXiv | Why it's here |
|---|---|---|
| Breaking the Reclustering Barrier in Centroid-based Deep Clustering (ICLR 2025) | [2411.02275](https://arxiv.org/abs/2411.02275) | Same author team; diagnoses why classic AE methods plateau, shows DEC/IDEC/DCN + contrastive loss rival SOTA. (arXiv ID is Nov 2024; the ICLR version is 2025.) |
| Clustering via Self-Supervised Diffusion (CLUDI) | [2507.04283](https://arxiv.org/abs/2507.04283) | First diffusion model applied to clustering; teacher-student setup where diffusion sampling doubles as augmentation. |
| Cluster Contrast for Unsupervised Visual Representation Learning (CueCo, ICIP 2025) | [2507.12359](https://arxiv.org/abs/2507.12359) | A concrete 2025 "modern building block": contrastive + clustering losses trained jointly. |

## Deliverables

| Deliverable | Link |
|---|---|
| Medium article (written from scratch) | _TODO: paste Medium link_ |
| Slide deck (SlideShare) | _TODO: paste SlideShare link_ |
| Presentation video (10–15 min) | _TODO: paste video link_ |

## Repo layout

```
.
├── README.md               # this file
├── research-notes.md       # research brief: methods, benchmarks, metrics, "two cents" angles
├── article-outline.md      # section-by-section plan for the Medium article
├── slide-structure.md      # slide-by-slide plan for the deck + video
├── article/                # final article text + embedded figure files
├── figures/                # original figures (recreated experiments, diagrams)
├── slides/                 # slide deck source (pptx/pdf)
└── video/                  # recorded presentation (mp4)
```

## Reproducing the figures

All figures in the article were created independently for this project — none are copied from the survey:

- `figures/lambda1_ablation/` — recreation of the λ₁ ablation experiment on MNIST (IDE C with λ₁ = 0 / 0.5 / 1): embedding scatter plots annotated with reconstruction loss, Silhouette score, and clustering accuracy. Shows unsupervised metrics (SIL, REC) picking a different winner than the supervised metric (ACC).
- `figures/taxonomy/` — original decision-tree/mind-map of the deep-clustering landscape (optimization strategy × network type), drawn from scratch.
- `figures/ae_schematic/` — original autoencoder diagram (encoder → bottleneck → decoder), built with [tool used].
- `figures/knob_count/` — bar chart of hyperparameter counts per method (from the survey's appendix tables), illustrating the "curse of hyperparameters".

## References

1. Leiber et al., "An Introductory Survey to Autoencoder-based Deep Clustering," arXiv:2504.02087, 2025.
2. Miklautz et al., "Breaking the Reclustering Barrier in Centroid-based Deep Clustering," ICLR 2025, arXiv:2411.02275.
3. Uziel et al., "Clustering via Self-Supervised Diffusion," arXiv:2507.04283, 2025.
4. Giakoumoglou & Stathaki, "Cluster Contrast for Unsupervised Visual Representation Learning," ICIP 2025, arXiv:2507.12359.
