## Renting compute to train models bigger than your own hardware

**Bottom line for a solo artist-researcher.** If your local ceiling is ~2x RTX 5090 (32GB) + RTX 4090 (24GB), renting in 2026 unlocks full-finetune and large-model work that local hardware cannot reach - and it is cheap enough that the gate is no longer money. The practical envelope is: **rent ONE 8-GPU node, do anything from LoRA to a full finetune of a 7B-70B model, pay tens to low-hundreds of dollars per run.** The variables that actually bite are non-price: the interconnect, who physically owns the box (privacy), spot interruption, and which grid the electrons came from.

### 1. What it costs (mid-2026, per GPU-hour)

H100 SXM5 on-demand has commoditized to roughly \$2-\$3 on specialist clouds, with marketplace floors near \$1.49-\$2.00 and hyperscaler *list* prices at ~\$4-\$12. The honest gap, once you account for AWS's ~44% 2025 price cut, is about **2-3x**, not the 6-10x in vendor headlines.

| Tier | Provider | H100 SXM5 on-demand | Notes |
|---|---|---|---|
| Marketplace / community | Vast.ai | ~\$1.49-\$2.00 ([source](https://getdeploying.com/gpus/nvidia-h100), [source](https://intuitionlabs.ai/articles/h100-rental-prices-cloud-comparison)) | host-specific reliability; \$1.49 was a July-2025 promo |
| Marketplace / community | RunPod Community | ~\$1.99 (PCIe), ~\$2.69 (SXM) ([source](https://www.synpixcloud.com/blog/cloud-gpu-pricing-comparison-2026)) | spot ~\$1.25 |
| Managed specialist | Lambda | ~\$2.99 ([source](https://www.buildmvpfast.com/blog/gpu-cloud-cost-comparison-runpod-lambda-labs-coreweave-2026)) | ~\$1.89 reserved |
| Managed specialist | Nebius | ~\$2.00-\$2.95 ([source](https://intuitionlabs.ai/articles/h100-rental-prices-cloud-comparison)) | InfiniBand available |
| Premium / IB node | CoreWeave | ~\$6.16 (\$49.24/hr for the 8x HGX node) ([source](https://www.buildmvpfast.com/blog/gpu-cloud-cost-comparison-runpod-lambda-labs-coreweave-2026)) | per-GPU pricing of an InfiniBand node |
| Bare-metal node | Oracle | ~\$10 (\$80/hr, all-or-nothing 8-GPU SKU) ([source](https://intuitionlabs.ai/articles/h100-rental-prices-cloud-comparison)) | you rent the whole node |
| Hyperscaler (list) | AWS p5 / Azure ND v5 | ~\$3.90 blended to ~\$12.29 list ([source](https://www.cloudzero.com/blog/h100-gpu-cost/)) | AWS p5 fell ~44% in 2025 |

The cross-provider consensus is that the on-demand market "settled around \$2-4/GPU-hr" by late 2025 (IntuitionLabs, 2026; [source](https://intuitionlabs.ai/articles/h100-rental-prices-cloud-comparison)). **Vendor "up to X% cheaper" figures are marketing.** In particular the Spheron H100-spot-\$1.03 and Akash-\$0.41 lows are self-reported; independent floors sit nearer \$1.25/hr.

### 2. What you can actually train (rented, 2026)

| Job | Hardware | Time | Cost (approx.) |
|---|---|---|---|
| LoRA/QLoRA 7B-34B | single 4090 / A100 / H100 | a few hours | ~\$1-\$15 |
| QLoRA 70B | single 80GB H100/A100 | 8-12 h | ~\$10-\$16 |
| **FULL finetune 70B** | **8x H100 node** | **24-48 h** | **~\$250-\$510** |
| Pretrain mid-size from scratch | multi-node, InfiniBand | days-weeks | not solo-realistic |

Sources: [Spheron fine-tuning guide 2026](https://www.spheron.network/blog/how-to-fine-tune-llm-2026/), [io.net fine-tuning budget guide](https://io.net/blog/llm-fine-tuning-budget-guide-gpu-costs-timelines-and-what-to-spend), [Index.dev LoRA vs QLoRA 2026](https://www.index.dev/blog/top-ai-fine-tuning-tools-lora-vs-qlora-vs-full). PEFT cuts memory ~10-20x while retaining ~90-95% of full-finetune quality, which is why a real artist finetune is **tens of dollars, not thousands**. Genuine **pretraining from scratch** is where this breaks: GPT-3-class was ~1,287 MWh / ~552 t CO2 ([Patterson et al., 2021](https://arxiv.org/abs/2104.10350)) - multi-million-dollar, multi-node, InfiniBand-mandatory territory out of reach for an individual, and precisely what the collective protocols (below) exist for.

### 3. The most overlooked variable: the interconnect

Inside one 8x box, GPUs talk over **NVLink 4 (~900 GB/s)**. The moment you cross machines, your effective throughput is set by the fabric between nodes ([APXML, interconnect technologies](https://apxml.com/courses/how-to-build-a-large-language-model/chapter-18-hardware-considerations-llm-training/interconnect-technologies-nvlink-infiniband)):

| Fabric | Latency | Bandwidth efficiency | Wall-clock penalty (70B / 4 nodes) |
|---|---|---|---|
| InfiniBand NDR | ~0.6 us | ~95% of theoretical | baseline |
| RoCEv2 (tuned) | ~1-5 us | ~92% | small |
| Ethernet (congested) | 10-50 us | degraded | +10-15% ([Spheron](https://www.spheron.network/blog/multi-node-gpu-training-without-infiniband/)) |

**The actionable rule:** a solo user almost never needs multi-node InfiniBand. Anything that fits on **one** 8x H100/H200 node (640 GB / 1128 GB VRAM) uses NVLink internally and sidesteps the inter-node fabric question entirely ([RunPod, do I need InfiniBand?](https://www.runpod.io/articles/guides/infiniband-for-distributed-ai-training)). One node covers an enormous range - everything in the table above.

### 4. Decentralized compute: two different things, do not conflate them

- **(1) Rent a box from a marketplace** (Akash ~\$1.33/H100-hr per [Coinstancy, 2026](https://coinstancy.com/academy/guides/akash-network/); io.net renting clusters "50-70% below AWS" per [DEXTools, 2026](https://www.dextools.io/tutorials/what-is-io-net-decentralized-gpu-ai-depin-solana-guide-2026); plus Vast, RunPod, Prime Intellect's exchange). You get a normal Docker/SSH box and train your **own** model. This is the realistic path for an individual.
- **(2) Join a training protocol** (Nous Psyche; Prime Intellect's INTELLECT runs). You contribute your GPU to one big shared model everyone co-trains; you do **not** get a private box, and the result is collectively owned. INTELLECT-2 (May 2025) is the first 32B model trained via globally distributed permissionless RL across 100+ nodes on three continents, using PRIME-RL, the **TOPLOC** verifier and SHARDCAST ([Prime Intellect](https://www.primeintellect.ai/blog/intellect-2); [arXiv:2505.07291](https://arxiv.org/html/2505.07291v1)). This is for contributing to communal frontier-scale runs, not for training your own work.

### 5. The real gotchas (all non-price)

- **Privacy.** On a permissionless/community box the **host physically owns the machine**: with root/hypervisor access they can in principle read your data, training set and weights from RAM/VRAM/disk. Akash "does not inspect tenant data" - but equally does not protect it from the host. The only robust defense is **GPU TEE / confidential computing** (NVIDIA H100/H200 CC-mode), which encrypts weights+inputs+outputs even from a rogue admin, at **under ~5% overhead for typical LLM workloads and near-zero for large models** ([arXiv:2409.03992](https://arxiv.org/pdf/2409.03992); [Phala benchmark](https://phala.com/posts/confidential-computing-on-nvidia-h100-gpu-a-performance-benchmark-study)). But pay-as-you-go TEE GPUs on decentralized markets are still mostly **roadmap** in 2026, not a click-to-rent default. **Practical rule: treat any community GPU as untrusted** - no sensitive footage, unreleased weights or personal data unless it is a TEE-attested or vetted "secure cloud" host.
- **Verifiability ≠ privacy.** TOPLOC proves a remote node *ran the model it claimed* (contributor anti-cheat, validated ~100x faster than generation in Prime Intellect's tests). It does **not** make your data private to the host. The two are routinely conflated.
- **Spot interruption.** Spot/interruptible cuts price 50-80% but jobs can be preempted with little notice - only worth it for fault-tolerant runs with **frequent checkpointing**.
- **Egress.** A genuine marketplace advantage: SF Compute and several decentralized providers advertise **no egress fees** vs hyperscalers' high egress, so moving checkpoints/datasets off is cheap (you still pay storage + upload time).

### 6. Ecology: where and when, not just how much

Data centres used ~415 TWh in 2024 (~1.5% of global electricity) and the IEA Base Case projects ~945 TWh (~3%) by 2030, AI the main driver - accelerated/AI servers growing ~30%/yr ([IEA, Energy and AI](https://www.iea.org/reports/energy-and-ai/energy-demand-from-ai); [DCD](https://www.datacenterdynamics.com/en/news/iea-data-center-energy-consumption-set-to-double-by-2030-to-945twh/)). The carbon of a single run is dominated by **where** and **when** it runs: region choice can swing emissions by **>60x** (a model trained in Estonia can emit >61x the CO2eq of the same model in Sweden, 2016 intensities - [Carbontracker, arXiv:2007.03051](https://arxiv.org/pdf/2007.03051)), and time-shifting non-urgent training to low-carbon-intensity hours cuts emissions substantially with zero model changes ([Chasing Low-Carbon Electricity, arXiv:2303.02508](https://arxiv.org/pdf/2303.02508)). A climate-conscious renter should pick low-carbon regions and schedule via grid-intensity data ([Electricity Maps](https://www.electricitymaps.com/), [WattTime AER](https://watttime.org/news-and-insights/solution_matches/automated-emissions-reduction-aer/)). **Caveat against greenwashing:** networks that "soak up idle consumer GPUs" have an ambiguous footprint - reusing idle silicon is efficient, but a consumer GPU on a dirty grid can be worse per FLOP than an optimized datacentre on a clean one.

### Killed / demoted claims
- io.net "8xH100 ~\$3.35/hr vs AWS \$98.32/hr" - **dropped**: \$3.35 for eight H100s implies ~\$0.42/GPU-hr, below every verified floor; it pits a marketing low against a list-price high.
- Spheron H100 spot \$1.03 and "6.7x cheaper than AWS" - **demoted** to vendor/unverified (independent floors ~\$1.25).
- Akash \$0.41 / "up to 85% cheaper" - **demoted** to marketing (independent check ~\$1.33/H100-hr).
- Hyperscaler \$12.29/GPU-hr presented as live cost - **qualified** as list price (AWS p5 ~\$3.90 blended post-2025-cut).
- GPT-4-class ~50 GWh - **retained at medium confidence** (widely-repeated estimate, not vendor-disclosed).

---

*Sources for this section are linked inline above. The consolidated source list is in [SOURCES.md](../SOURCES.md).*
