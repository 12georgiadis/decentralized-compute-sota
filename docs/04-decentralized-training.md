## Decentralized / Distributed Training of Frontier Models

**Bottom line (Nov 2024 - Mar 2026):** Low-communication algorithms have made decentralized training of *mid-sized* models (10B-72B) genuinely real and reproducible. Training *frontier-scale* models over the internet is demonstrated nowhere, and is judged unlikely to catch up this decade. The most telling datapoint of the period is that the leading project's own best model retreated to a centralized datacenter.

### The algorithmic breakthrough: DiLoCo and its descendants

The enabling idea is **DiLoCo** (Douillard et al., Google DeepMind, Nov 2023, [arXiv:2311.08105](https://arxiv.org/abs/2311.08105)): instead of synchronizing gradients every step over a high-bandwidth fabric, each replica runs hundreds of local "inner" steps (typically H=500) and synchronizes only "outer" pseudo-gradients, cutting inter-node communication by ~500x. The constraint that this relaxes is **bandwidth, not latency** - infrequent syncing tolerates the high latency of home internet. Consumer upload (~60 Mbps) sits five-to-six orders of magnitude below InfiniBand (200-400 GB/s), and DiLoCo's whole point is to live within that gap.

Two follow-ups matter:
- **OpenDiLoCo** (Prime Intellect, Jul 2024, [blog](https://www.primeintellect.ai/blog/opendiloco) / [arXiv:2407.07852](https://arxiv.org/html/2407.07852v1)) reproduced DiLoCo across 2 continents / 3 countries at billion-parameter scale with **90-95% compute utilization**.
- **"Scaling Laws for DiLoCo"** (DeepMind, Mar 2025, [arXiv:2503.09799](https://arxiv.org/abs/2503.09799)) found the striking result that, well-tuned, **DiLoCo scales *better* than data-parallel** as models grow: M=2 replicas beat data-parallel above several billion parameters, validated on 4B and 10B runs.

A second wave of compression methods pushes the same idea further: Nous's **DisTrO/DeMo**, Templar's **SparseLoCo** (sparsification + 2-bit quant + error feedback), Pluralis's **Protocol Models** (subspace-constrained activations, [arXiv:2506.01260](https://arxiv.org/abs/2506.01260)), and Macrocosmos's **IOTA** pipeline-parallel SWARM.

### What was actually deployed

| Model / Run | Org | Size | Tokens | Hardware / network | Status | Notes |
|---|---|---|---|---|---|---|
| **INTELLECT-1** | Prime Intellect | 10B | 1T | up to 112 H100 / 14 nodes, 5 countries, home internet | Decentralized, real ([report](https://arxiv.org/abs/2412.01152)) | 30 providers, 42 days, 83% util cross-continent / 96% US-only ([blog](https://www.primeintellect.ai/blog/intellect-1)) |
| **INTELLECT-2** | Prime Intellect | 32B (RL) | - | permissionless consumer GPUs | Decentralized, marginal gains ([paper](https://arxiv.org/html/2505.07291v1)) | +2.2 AIME24, +0.1 AIME25, IFEval *dropped*; team admits limited generalized gain |
| **Consilience-40B** | Nous (Psyche) | 40B | ~20T | DeMo optimizer, Solana-coordinated | Largest internet pretrain by tokens ([HF](https://huggingface.co/PsycheFoundation/consilience-40b-CqX3FUm4)) | Sized to train on 1 DGX, infer on 1×3090 |
| **Protocol Model 8B** | Pluralis | 8B | - | 80 Mbps consumer links | Decentralized, real ([arXiv](https://arxiv.org/abs/2506.01260)) | up to 100x / 99% compression, matches 100Gbps baseline |
| **Covenant-72B** | Templar (Bittensor SN3) | 72B | ~1.1T | 70+ commodity GPUs, home internet | "Largest decentralized run" (10 Mar 2026, [arXiv:2603.08163](https://arxiv.org/pdf/2603.08163)) | SparseLoCo 146x; only matches Llama-2-70B (2023) |
| **INTELLECT-3** | Prime Intellect | 106B MoE (12B active) | - | **512× H200, 400Gbps InfiniBand, ~2 months** | **CENTRALIZED** ([blog](https://www.primeintellect.ai/blog/intellect-3)) | Flagship; *not* decentralized |

### The three adversarial caveats

1. **The scale gap is ~1000x.** Epoch AI (Jaime Sevilla, ["How far can decentralized training over the internet scale?"](https://epoch.ai/gradient-updates/how-far-can-decentralized-training-over-the-internet-scale), Dec 2025) independently places the largest decentralized runs (INTELLECT-1, Pluralis 8B, Consilience 40B) at **6e22-6e23 FLOP** - about 1000x below frontier models such as Grok 4. Decentralized compute is growing ~20x/year (600,000x since 2020), but Epoch's conclusion is blunt: *"we won't see decentralized training runs catch up to the frontier of training in scale this decade."* The penalty is structural - going from 1→8 nodes already costs ~1.5x compute, and naive scaling to 10,000 nodes would cost ~6x the FLOP of a centralized run. This is an economic/aggregation limit, not a physics wall.

2. **RL post-training gains are marginal.** INTELLECT-2 (32B) improved on its QwQ-32B base by only +2.2 (AIME24) and +0.1 (AIME25), and regressed on IFEval; the authors concede *"it was difficult to obtain huge amounts of generalized improvement on benchmarks"* ([arXiv:2505.07291](https://arxiv.org/html/2505.07291v1)).

3. **The flagship retreat.** Prime Intellect's best model, INTELLECT-3 (106B MoE), was trained on a **centralized 512× H200 InfiniBand cluster**, not decentralized ([Prime Intellect](https://x.com/PrimeIntellect/status/1993895069951422817)). The reason is technical: async RL discards rollouts that drift more than 8 steps behind the current policy, which - per [implicator.ai](https://www.implicator.ai/prime-intellects-intellect-3-open-source-ambition-meets-centralized-reality/) - *"demands InfiniBand, not commodity broadband from someone's garage."*

### Reading the hype filter

Most of these projects are entangled with **crypto-token economics** - Templar on Bittensor (TAO/alpha), Nous Psyche on Solana, Gensyn's a16z-backed [RL Swarm testnet](https://docs.gensyn.ai/testnet/rl-swarm) and \$AI token. Headline compression multipliers and "largest ever" claims frequently surface through token-correlated marketing channels rather than peer review, so they should be treated as vendor-stated until independently reproduced.

**Verdict:** Decentralized training is *technically viable and demonstrated* for sub-frontier (≤~72B, ~1T-token) models, and the algorithms are sound and peer-reviewed. It remains *fundamentally constrained* - by compute aggregation and economics, not pure physics - at true frontier scale through at least ~2030. The honest one-liner: the math works, the mid-scale models are real, and the frontier is still in the datacenter.

---

*Sources for this section are linked inline above. The consolidated source list is in [SOURCES.md](../SOURCES.md).*
