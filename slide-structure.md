# Slide Deck Structure — Autoencoder-based Deep Clustering (10–15 min)

> 12–14 slides, ~1 min per slide. Build in PowerPoint/Google Slides, export PDF, upload to SlideShare. All diagrams original — redraw, don't screenshot the paper.

| # | Slide | Content | ~Time |
|---|---|---|---|
| 1 | Title | Article title, your name, course, the survey citation (arXiv:2504.02087) | 0:30 |
| 2 | The problem | Clustering high-dimensional data; curse of dimensionality in one visual (distances stop discriminating) | 1:00 |
| 3 | The fix: learn the space first | Autoencoder crash course — your own encoder→bottleneck→decoder diagram | 1:00 |
| 4 | The sandbox idea | Why AEs are the field's playground: non-linear, domain-agnostic, stable, hosts all strategies | 1:00 |
| 5 | Recipe 1: Sequential | Train AE → cluster embedding. AE+k-Means, DEN, N2D, DDC. Strength + fatal weakness (no recovery) | 1:00 |
| 6 | Recipe 2: Alternating | Take turns: embedding ⇄ clusters. AEC, DCN, ACe/DeC, DipEncoder. Reconstruction = anti-collapse regularizer | 1:15 |
| 7 | Recipe 3: Simultaneous | End-to-end. DEC's sharpening trick (KL target), IDEC's fix, DCEC's architecture swap | 1:15 |
| 8 | Taxonomy map | Your own decision-tree figure: pick a strategy × pick a network | 0:45 |
| 9 | Spotlight: the λ₁ ablation | **Your recreated experiment.** Four embedding scatter plots (λ₁ = 0/0.5/1) with REC, SIL, ACC. The money slide: unsupervised metrics crown a different winner than accuracy | 2:00 |
| 10 | Dirty secrets | Hyperparameter brittleness (knob-count bar chart) + the evaluation paradox (learned embeddings make anything "look perfect") | 1:15 |
| 11 | 2025: old dogs, new tricks | BRB (reclustering barrier, ICLR 2025), CLUDI (diffusion meets clustering), CueCo (contrastive + clustering jointly) | 1:15 |
| 12 | My take | Your one or two "two cents" opinions | 1:00 |
| 13 | Takeaways | Three crisp bullets + references + QR/link to the Medium article | 0:45 |

## Speaker notes tips
- Slide 9 is the centerpiece — rehearse it most. Walk through λ₁ = 0 (SIL 99.35%, REC explodes, ACC drops) → λ₁ = 1 (REC healthy, ACC 88.38%) slowly.
- Keep slides 5–7 visual: one architecture diagram per recipe, minimal text.
- Record with Zoom; do a dry run to land inside 15 minutes.
- Export the final deck as PDF into `slides/` and keep the editable source too.
