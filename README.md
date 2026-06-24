# Compute Outside the Datacenter

### A verified state of the art of decentralized AI compute (mid 2026)

> Renting your machine for AI, crypto GPU networks, the Folding@home / PlayStation 3 lineage, decentralized model training, the open commons. What is real, what is hype, and whether anything can actually emerge outside Google, Amazon and Microsoft.

*Français : voir [README.fr.md](README.fr.md) et l'essai signé [essai/decentralisation-du-compute.fr.md](essai/decentralisation-du-compute.fr.md).*

---

## TL;DR (the verdict)

Decentralized compute is **neither a dead end nor a revolution**. It is a real and durable **second tier** that coexists with hyperscaler datacenters without replacing them at the frontier. It lowers rents (an anti-rent force: H100 at 2 to 4 USD/hour versus hyperscaler list prices), routes around GPU scarcity, and keeps an open-training escape hatch alive that matters politically more than it matters by FLOP share.

- **Believe** the inference revenue and the low-communication training results.
- **Discount** the token market caps and the advertised "GPU counts" by roughly an order of magnitude.

The single master pattern: across every family, **advertised capacity vastly exceeds verified working capacity**. io.net markets 327,000 "registered" GPUs but averaged about 6,720 verified-active per day in Q1 2025 (about 2 percent), after a 2024 Sybil attack involving roughly 1.8 million fake GPUs. The whole DePIN sector is around 10 billion USD of market cap on roughly 72 million USD of real on-chain 2025 revenue (Messari, *State of DePIN 2025*). Auditability is the line between signal and noise.

---

## The five families

Conflating these is the root of most hype. Each differs by who supplies the hardware, who pays, and which workload is viable.

| # | Family | Supply | Payment | Viable workload | Evidence grade |
|---|---|---|---|---|---|
| 1 | **Commercial marketplaces** (Vast.ai, RunPod, TensorDock, Salad) | Pros and prosumers, aggregated | Fiat, market-priced | Inference, fine-tuning, training on rented datacenter GPUs | **Strong** (auditable prices, RunPod 120M USD ARR) |
| 2 | **Crypto / DePIN** (io.net, Render, Akash, Bittensor, Aethir, Nosana) | Token-incentivized hosts | Token, sometimes fiat | Increasingly real paid inference, rendering, RL | **Mixed** (small real revenue, large speculative caps) |
| 3 | **Volunteer / open-source** (Folding@home, BOINC, the PS3 era, AI Horde) | Donated idle cycles, unpaid | None (altruism, kudos) | Embarrassingly parallel science, **not** LLM training | **Proven but workload-limited** |
| 4 | **Decentralized training** (Prime Intellect, Nous, DiLoCo) | Dispersed GPUs, low-communication algorithms | Varies (research, token, co-op) | Low-communication pretraining and RL across continents | **Early but real** (the only genuinely new capability) |
| 5 | **Open commons** (LeCun, open weights, Project Tapestry) | Governance / IP layer | n/a | Political precondition, not a source of FLOPs | Real as a movement |

---

## Read the survey

Each section is fully sourced. Vendor and self-reported figures are flagged; dollar figures are dated snapshots that drift week to week.

1. [Commercial GPU rental marketplaces and who the hosts are](docs/01-commercial-marketplaces.md)
2. [Crypto / DePIN incentive networks](docs/02-depin-crypto.md)
3. [Volunteer / open-source distributed computing (the PS3 lineage)](docs/03-volunteer-ps3-lineage.md)
4. [Decentralized / distributed training of frontier models](docs/04-decentralized-training.md)
5. [Yann LeCun and the open / commons AI debate](docs/05-lecun-open-commons.md)
6. [Political economy of compute](docs/06-political-economy.md)
7. [Synthesis, verdict, cross-platform feasibility, and collective action](docs/07-synthesis-and-verdict.md)
8. [Renting compute to train bigger than your hardware](docs/08-renting-compute-to-train.md)
9. [Ecology of compute: energy, footprint, and traceability](docs/09-ecology-and-traceability.md)
10. [Mutualizing compute: the commons, and how a collective organizes](docs/10-mutualizing-compute-commons.md)

**Sources and method:** the consolidated, verified source list (vendor figures flagged, refuted claims kept) is in [SOURCES.md](SOURCES.md).

---

## What a small group can actually do today

Drawn from the synthesis (full list in section 7):

- **A buying co-op on the proven marketplaces.** Pool demand on Vast.ai / RunPod / TensorDock to rent H100s at 2 to 4 USD/hour instead of paying hyperscaler rates. Lowest-risk action; treat it as a compute credit union, not an investment.
- **A private distributed-inference swarm** across your own NVIDIA GPUs plus Apple Silicon for orchestration, over a private network, to run a large open model none of the machines could run alone.
- **Reproduce OpenDiLoCo or contribute to a Prime Intellect-style run.** The frontier-relevant and politically meaningful skill: attacking the moat at the level of model *creation*, not inference.
- **Contribute idle cycles to Folding@home / BOINC** as the cross-platform baseline and an honest demonstration of the volunteer-compute ceiling.
- **Build an honest public benchmark of real USD-per-token and USD-per-GPU-hour** (verified versus advertised) across providers. The sector's core pathology is unverifiable claims; a rigorous counter-hype artifact is genuinely useful.
- **Co-locate hardware physically** when possible. For tightly coupled training the bandwidth wall is decisive, so a small co-located cluster on a fast LAN beats the same GPUs scattered across home internet.

---

## Notes

Dollar figures are dated snapshots from mid-2026 and drift over time; vendor-reported numbers are labelled as self-reported. Corrections and additional sources are welcome via issues and pull requests.

---

## License and citation

Dual-licensed: text under **CC BY-NC-ND 4.0**, code under **PolyForm Noncommercial 1.0.0**. See [LICENSE.md](LICENSE.md). Please cite with [CITATION.cff](CITATION.cff).

Author: **Ismaël Joffroy Chandoutis**, 2026.
