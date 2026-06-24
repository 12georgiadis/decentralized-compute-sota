## Commercial GPU Rental Marketplaces and Who the Hosts Are

Outside the hyperscalers, a layer of GPU rental marketplaces has matured into a real, demand-bearing market in 2025-2026. The space divides cleanly into two business models, and a third (crypto-DePIN) that markets itself as a marketplace but functions mostly as a token-subsidized supply experiment.

### Two business models

- **Peer-to-peer marketplaces** aggregate third-party hardware and take a cut: **Vast.ai**, **RunPod** (Community Cloud), **TensorDock**, **Salad**.
- **Vertically integrated / cluster providers** mostly own or lease their fleet and price centrally: **Together AI**, **Hyperbolic** (which calls itself a "marketplace" but sets prices itself).

The division of labor on a marketplace is consistent: the platform handles customers, billing, and scheduling; the host owns hardware uptime, network connectivity, physical infrastructure, and setup.

### The price arbitrage is real

On-demand H100 rental spans roughly **\$1.49–\$6.98/hr** across 15+ specialized providers in 2026, clustering at **\$2–\$4/hr** ([IntuitionLabs](https://intuitionlabs.ai/articles/h100-rental-prices-cloud-comparison)), which is **50–75% cheaper than hyperscaler list prices** for the same hardware ([getdeploying](https://getdeploying.com/gpus/nvidia-h100)). Consumer-GPU floors are genuine and low.

| Provider | Model | Business model | Indicative \$/hr (mid-2026) | Source |
|---|---|---|---|---|
| TensorDock | H100 SXM | P2P marketplace | ~\$1.99/hr on-demand | [computeprices.com](https://computeprices.com/providers/tensordock) |
| TensorDock | A100 80GB SXM | P2P marketplace | ~\$0.95/hr | [computeprices.com](https://computeprices.com/providers/tensordock) |
| TensorDock | RTX 4090 | P2P marketplace | ~\$0.32/hr | [computeprices.com](https://computeprices.com/providers/tensordock) |
| Vast.ai | RTX 5090 (consumer) | P2P marketplace | host earns \$0.30–\$0.60/GPU-hr | [Vast.ai](https://vast.ai/article/how-much-money-can-you-earn-renting-out-your-gpu-on-vast-ai) |
| Various | H100 (market-wide) | mixed | \$1.49–\$6.98/hr, mostly \$2–\$4 | [IntuitionLabs](https://intuitionlabs.ai/articles/h100-rental-prices-cloud-comparison) |

> Caution: vendor and aggregator pricing drifts week to week. An earlier draft of this survey carried TensorDock figures of H100 \$2.25 / A100 80GB \$1.80 / RTX 4090 \$0.35 / H100 spot \$1.30; only the H100 on-demand figure survived verification against the live page and [computeprices.com](https://computeprices.com/providers/tensordock) (June 2026). Quote \$/hr with a date and a source, never as a stable constant.

### Marketplace take rates and host economics

| Marketplace | Documented host split / take rate | What hosts actually earn | Independence of source |
|---|---|---|---|
| TensorDock | **75% to host / 25% platform fee**, paid via Stripe | - | Confirmed by TensorDock's [host page](https://www.tensordock.com/host.html) and binding [Supplier Hosting Agreement](https://docs.tensordock.com/legal-information/supplier-hosting-agreement); **no independent third party** verifies it |
| Vast.ai | Not officially disclosed; self-reported **~25% spread** between renter price and host earnings | \$0.30–\$0.60/GPU-hr (consumer); \$2.15–\$4.00+/GPU-hr (H100/H200); a 4x RTX 5090 rig at 80% util = \$700–\$1,400/mo (vendor best-case) | [Vast.ai](https://vast.ai/article/how-much-money-can-you-earn-renting-out-your-gpu-on-vast-ai) |
| RunPod | **1–7% "revenue share" is for Hub template/app deployers**, paid in RunPod credit - **NOT** the host split, which is invite-only and undisclosed | - | [RunPod docs](https://docs.runpod.io/hub/revenue-sharing) |
| Salad | Pays in "Salad Balance" (gift cards, games, crypto, PayPal), no transparent % | "up to \$180/mo" advertised; ~\$30–\$200/mo real; a user's 4x RTX 5090 made \$460 in 30 days | [Salad](https://salad.com/download-high-end), [user test](https://www.youtube.com/watch?v=o9Yw4pfPbLk) |

Independent guides put **net** consumer-host profit after electricity far below marketing: ~\$8/mo for an RTX 3080 and ~\$52/mo for an RTX 4090 ([EarnifyHub](https://earnifyhub.com/learning-guides/make-money-renting-out-gpu-2026)). Vast.ai verification is automated and prioritizes datacenter-grade gear - "mining rigs may never be verified," verified H100s list at ~\$1.50–\$1.87/hr while unverified ones sit near \$0.90/hr and "mostly sit idle" ([Vast.ai](https://vast.ai/article/how-much-money-can-you-earn-renting-out-your-gpu-on-vast-ai)). The market is two-tier: amateur hosts largely starve unless they reach Verified/Datacenter status.

### The DePIN credibility gap (hype)

Crypto-DePIN networks expose the widest gap between marketed and real supply.

- **io.net** markets **327,000 "registered" GPUs** but averaged only **6,720 verified-active GPUs per day in Q1 2025 (~2%)**, with ~5,350 cluster-ready on a given day ([Messari, State of io.net Q1 2025](https://messari.io/report/state-of-io-net-q1-2025)). Its 2024 Sybil attack saw **~1.8M fake GPUs** attempt to connect and **~400,000 spoofed workers** chasing token rewards before Proof-of-Work verification was added ([The Block](https://www.theblock.co/post/291315/solana-based-depin-io-net-ceo-claims-network-was-attacked-in-detailed-postmortem); [io.net postmortem on X](https://x.com/ionet/status/1780877493672595941)).
- **Akash Network** shrank rather than scaled: Q4 2025 averaged **63 active providers**, GPU usage fell **46% QoQ** (367 → 198) and capacity dropped 16% (702 → 587) as providers exited ([Messari, State of Akash Q4 2025](https://messari.io/report/state-of-akash-q4-2025); [Akash Q4 report](https://akash.network/blog/q4-2025-report/)). Foundry (DCG-backed) is the largest single supplier.

DePIN "registered GPU" counts should be treated as marketing, not deployable capacity; the deployable number is routinely an order of magnitude smaller.

### Who actually hosts

Two profiles, with very different trust models. **(1)** Hobbyists and ex-miners repurposing idle consumer GPUs (Salad's gamer install base; Vast/RunPod community tiers) - low barrier, thin and often token-denominated returns. **(2)** Professional and datacenter operators chasing Verified/Datacenter badges (Vast verification wants CUDA ≥12.0, 90%+ reliability, SOC2/ISO 27001 for the datacenter tier; RunPod Community is invite-only vetted) - these get the enterprise jobs. Renters skew toward AI developers, fine-tuners, inference shops, and budget researchers leaving hyperscaler markups.

---

*Sources for this section are linked inline above. The consolidated source list is in [SOURCES.md](../SOURCES.md).*
