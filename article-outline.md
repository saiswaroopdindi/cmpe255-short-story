# Medium Article Outline — "How Autoencoders Learned to Cluster"

> Target: ~1,500–2,500 words (6–10 min read). Gist over math: architecture, ablations, metrics — no equation weeds. Every section written from scratch in your own words; use the research notes as raw material, never as sentences to copy.

## 1. The hook — "Your clustering metric is lying to you" (150–200 words)
Open with the λ₁ ablation punchline: crank one knob on IDEC, Silhouette hits 99.35% — looks perfect — while the actual clustering accuracy gets *worse*. Pose the question: if the metric says perfect and the truth says worse, what are we even optimizing? One original scatter-plot figure here (your recreation of the ablation).

## 2. Why clustering breaks in high dimensions (150–200 words)
The curse of dimensionality in plain language: distances stop meaning anything, k-Means and friends fall apart. The fix the whole field converged on: don't cluster the raw data — cluster a learned low-dimensional embedding. No math; one small diagram of raw space → embedding space.

## 3. Enter the sandbox: the autoencoder (200–250 words)
Crash course: encoder squeezes data through a bottleneck, decoder rebuilds it, the reconstruction loss keeps it honest. Why the authors call it a sandbox — non-linear (unlike PCA), needs no domain knowledge, stable to train, and it hosts *every* training strategy so methods are comparable. Original AE diagram here.

## 4. Three ways to teach a sandbox to cluster (500–700 words — the meat)
Structure as "three recipes," each with a mini architecture diagram you draw yourself:
- **Recipe 1 — Sequential:** train the AE, then cluster the embedding (AE+k-Means, DEN, N2D, DDC). Simplest; but if the embedding is bad, game over.
- **Recipe 2 — Alternating:** take turns improving the embedding and the clusters (AEC, DCN, ACe/DeC, DipEncoder). The clustering loss visibly compacts the blobs — and the reconstruction term is the only thing stopping total collapse.
- **Recipe 3 — Simultaneous:** one end-to-end optimization (DEC, IDEC, DCEC, DKM). The famous DEC trick: sharpen confident assignments with a KL target; IDEC's fix of keeping reconstruction alive.
Close with the taxonomy mind-map figure (your own decision tree: pick a strategy, pick a network).

## 5. The ablation that broke the metric (250–300 words)
Deep-dive your recreated Figure-4 experiment: λ₁ = 0 vs. 0.5 vs. 1 on MNIST. Report REC / SIL / ACC for each. The lesson: the reconstruction term is an anti-distortion regularizer, and unsupervised metrics (Silhouette, reconstruction loss) can crown a different winner than supervised accuracy. This is the section the rubric's "ablation studies" bullet wants.

## 6. The dirty secrets: hyperparameters and evaluation (200–250 words)
- Hyperparameter hell: λ₂ swinging 0.1 → 10 across datasets; DEN's five knobs vs. ACe/DeC's knob elimination. Your original "knob-count" bar chart goes here.
- The evaluation paradox: in a learned embedding, the network is powerful enough to make *anything* look perfect — tuning without labels is the field's central practical headache.

## 7. 2025: old dogs, new tricks (200–250 words)
The companion papers — this is the "more surveys content together" requirement:
- **BRB (ICLR 2025):** the reclustering barrier — why classic methods plateau — and vintage DEC/IDEC/DCN + contrastive loss ≈ SOTA.
- **CLUDI:** diffusion models meet clustering for the first time; stochastic sampling as data augmentation.
- **CueCo (ICIP 2025):** contrastive + clustering losses trained jointly — a modern building block snapping into the old sandbox.

## 8. My two cents (150–200 words)
Pick one or two angles from the research notes (e.g., "we traded the curse of dimensionality for the curse of hyperparameters," or "maybe the clustering loss was never the point"). This is the section that makes the article *yours*.

## 9. Takeaways + references (100–150 words)
Three crisp takeaways, links to the survey and companion papers, note that all figures were created for this article.

---

### Writing rules (rubric compliance)
- Write every sentence yourself; paraphrase, don't lift. Turnitin will be run.
- Link the arXiv papers; never screenshot their figures — recreate or redraw.
- Cite methods with author+year inline, e.g., "Xie's DEC (2016)."
- Keep equations out; describe losses in words ("a penalty that pulls points toward their cluster center").
- Aim for 5–8 original figures total; every figure needs a caption that teaches something.
