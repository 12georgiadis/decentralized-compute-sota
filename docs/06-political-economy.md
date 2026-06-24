## Political Economy of Compute, and an Honest Verdict on Decentralization

### Two left frameworks, read against the AI-capex supercycle

Any political-economy reading of out-of-datacenter compute inherits two competing left-wing frameworks, both of which predate the 2025-2026 capex supercycle and must be read against it.

- **Technofeudalism (pessimistic).** Yanis Varoufakis (*Technofeudalism: What Killed Capitalism*, 2023; essay ["The Age of Cloud Capital"](https://www.persuasion.community/p/the-age-of-cloud-capital), *Persuasion*, 29 April 2024) argues that "cloud capital" is a mutation of capital "so much more powerful than its predecessor that... it has killed off its host," such that "profit and markets have been evicted from the epicenter of our economic and social system." Profit is replaced by **cloud rent** - "a form of rent that must be paid for access to those platforms" - and markets are replaced by "cloud fiefdoms... which look like, but are not, markets."
- **Fully Automated Luxury Communism (optimistic).** Aaron Bastani (*Fully Automated Luxury Communism*, Verso, [2019](https://en.wikipedia.org/wiki/Fully_Automated_Luxury_Communism)) is the counter-pole: ever-cheaper compute and automation could push society past scarcity into abundance.
- **The contest.** The technofeudalism reading is **not settled**. Henry Snow ([*Jacobin*, 27 Oct 2023](https://jacobin.com/2023/10/cloud-capitalism-technofeudalism-serfs-cloud-big-data-yanis-varoufakis)) argues this is intensified capitalism, not feudalism: firms keep power "insofar as they command greater profit," users *do* migrate ("the defining feature of serfs is that they do not freely migrate"), and search results are "literally, sold to advertisers" in functioning markets. We attribute technofeudalism as Varoufakis's *argument*, not as a consensus description.

### The concentration (the empirical core)

The "who controls compute" question is answered, first, by concentration. NVIDIA reported a record [**\$75.2B** in data-center revenue in calendar Q1 2026 (fiscal Q1 FY2027), up ~92% YoY](https://cryptobriefing.com/nvidia-data-center-revenue-75-billion/), with hyperscalers at roughly 50% (~\$38B), and holds an estimated **85-92%** of the AI-accelerator market (projected to ease toward ~75% by 2026 as AMD and custom silicon scale). The four hyperscalers' combined 2026 capex is commonly cited as analyst-consensus in the **~\$600B-\$725B** range (the figure varies by source and by AI-only vs total - treat as a range, not a point).

The cloud-rent thesis is visible in "neocloud" financials. CoreWeave reported [**\$5.13B** FY2025 revenue and a **\$66.8B** contracted backlog](https://finance.yahoo.com/news/coreweave-crwv-reports-2025-revenue-195641826.html) but a [**\$1.17B** GAAP net loss with Microsoft at **~67%** of 2025 revenue](https://investors.coreweave.com/news/news-details/2026/CoreWeave-Reports-Strong-Fourth-Quarter-and-Fiscal-Year-2025-Results/) - extreme single-customer concentration. The "renters" are no longer only startups; they include the AI labs themselves, and most independent capacity is financed by, and contractually locked to, the same NVIDIA/hyperscaler core, so its independence is largely nominal.

### The honest verdict: real but bounded, split cleanly by workload

Decentralized compute is **a real but bounded movement, not a credible challenger to hyperscaler dominance at the frontier.** The evidence splits by workload.

**(1) Frontier training stays centralized.** Per Epoch AI ([Jaime Sevilla et al.](https://epoch.ai/gradient-updates/how-far-can-decentralized-training-over-the-internet-scale)), the largest decentralized pretraining runs (INTELLECT-1, Protocol Model 8B, Consilience 40B) sit at **6e22-6e23 FLOP - ~1000x below** frontier models such as Grok 4. Decentralized training grows **~20x/year** vs **~5x/year** centralized, which mechanically implies ~5.5 years to parity *if both trends held* - but Sevilla's own conclusion is that "**we won't see decentralized training runs catch up to the frontier of training in scale this decade.**" Bandwidth is the binding constraint: over consumer internet, under a 10-minute sync, naive data parallelism caps out at a "rather small **600M parameter model**." Only algorithmic tricks make larger runs viable: DiLoCo's **~500x** bandwidth reduction, Nous Research's DeMo optimizer, and Prime Intellect's asynchronous RL.

**(2) Inference / rendering / batch is the genuine, growing niche.** Akash Network crossed [**~\$5M** compute spend in Q1 2026 (all-time high)](https://akash.network/blog/akash-network-q1-2026-report/), reporting [utilization above 80% and 428% YoY usage growth](https://www.ainvest.com/news/akash-network-surpasses-5-million-compute-spend-ai-infrastructure-bottlenecks-2605/) - real, price-sensitive demand for cheaper GPU-hours than hyperscaler list prices.

**(3) The web3 precedent is a cautionary tale on metric integrity.** io.net's April 2024 Sybil attack saw [**~1.8 million fake GPUs** attempt to connect](https://www.theblock.co/post/291315/solana-based-depin-io-net-ceo-claims-network-was-attacked-in-detailed-postmortem), and as of 2026 only [**~6,720** daily-verified-active GPUs out of ~327,000 registered](https://cryptonews.com/news/io-net-ceo-details-recent-sybil-attack-and-new-security-measures/). The whole DePIN sector generated only [**~\$72M** real on-chain revenue in FY2025 against a ~\$10B circulating market cap](https://messari.io/report/state-of-depin-2025), with [revenue decoupling from token price](https://decrypt.co/356349/depin-tokens-lag-revenues-rise-fundamentals) for the small subset with real usage. Advertised "registered GPUs" ≠ available capacity.

### REAL vs HYPE

| Claim | Verdict | Evidence |
|---|---|---|
| Compute is concentrated in NVIDIA + hyperscalers | **REAL** | \$75.2B NVIDIA data-center Q1-2026; ~85-92% accelerator share ([source](https://cryptobriefing.com/nvidia-data-center-revenue-75-billion/)) |
| Neoclouds embody "cloud rent" + customer lock-in | **REAL** | CoreWeave \$5.13B rev, \$1.17B loss, 67% Microsoft ([source](https://investors.coreweave.com/news/news-details/2026/CoreWeave-Reports-Strong-Fourth-Quarter-and-Fiscal-Year-2025-Results/)) |
| Decentralized **inference/rendering** has real demand | **REAL (small)** | Akash ~\$5M Q1-2026, >80% util, +428% YoY ([source](https://akash.network/blog/akash-network-q1-2026-report/)) |
| Permissionless training is technically real | **REAL (niche)** | 6e22-6e23 FLOP runs via DiLoCo/DeMo/async-RL ([source](https://epoch.ai/gradient-updates/how-far-can-decentralized-training-over-the-internet-scale)) |
| Decentralized training will rival the frontier | **HYPE** | ~1000x below frontier; Sevilla: won't catch up this decade ([source](https://epoch.ai/gradient-updates/how-far-can-decentralized-training-over-the-internet-scale)) |
| DePIN "registered GPU" counts = capacity | **HYPE** | io.net ~6,720 verified vs ~327k registered; ~1.8M fake in Sybil attack ([source](https://cryptonews.com/news/io-net-ceo-details-recent-sybil-attack-and-new-security-measures/)) |
| DePIN sector scale matches its valuation | **HYPE** | ~\$72M real revenue vs ~\$10B market cap ([source](https://messari.io/report/state-of-depin-2025)) |
| Technofeudalism is a settled description | **CONTESTED** | Varoufakis's argument; disputed by Jacobin/Snow ([source](https://jacobin.com/2023/10/cloud-capitalism-technofeudalism-serfs-cloud-big-data-yanis-varoufakis)) |

**Synthesis.** The technical achievement is real, the economic traction is real but small and concentrated in inference/rendering, and the marketing routinely overstates scale. Out-of-datacenter compute is an emerging movement with a defensible niche - *not* a replacement for Google, Amazon, or Microsoft datacenters at the frontier.

---

*Sources for this section are linked inline above. The consolidated source list is in [SOURCES.md](../SOURCES.md).*
