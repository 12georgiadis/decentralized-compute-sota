# Sources

This repository is a sourced survey. This file is its consolidated **bibliography**.

## How sources are cited here

- **In the text.** Every non-trivial claim links inline to its primary source (organization, document, date).
- **Vendor figures are flagged.** Any number that could only be traced to a company's own page is labeled self-reported.
- **Dated snapshots.** All dollar figures are snapshots from mid-June 2026 and drift over time.
- **Claims that did not hold up are kept, not hidden** — listed under "Refuted / do-not-repeat" rather than silently dropped.
- **The signed essay** ([essai/decentralisation-du-compute.fr.md](essai/decentralisation-du-compute.fr.md)) carries its own formal bibliography.

A confidence level (high / medium / low) is marked on each finding below.

---

## Commercial GPU rental marketplaces

**Headline.** GPU rental marketplaces are real and 5-9x cheaper than hyperscalers, but consumer-host earnings are thin and DePIN "supply" numbers are inflated by an order of magnitude.

### Verified findings

- _(high)_ TensorDock operates an explicit 75/25 revenue split: hosts keep 75%, TensorDock retains a 25% platform fee, paid via Stripe. Confirmed by TensorDock's own host page and its binding Supplier Hosting Agreement, but NOT by any independent third party (all corroboration traces back to TensorDock).  
  Sources: https://www.tensordock.com/host.html · https://docs.tensordock.com/legal-information/supplier-hosting-agreement
- _(high)_ Vast.ai does not disclose its commission in official docs; its own host-earnings article states 'Live GPU prices are typically about 25% above what hosts earn,' implying a ~25% effective spread.  
  Sources: https://vast.ai/article/how-much-money-can-you-earn-renting-out-your-gpu-on-vast-ai
- _(medium)_ Vast.ai host earnings (vendor figures, treat as best-case): consumer GPUs like the RTX 5090 earn \$0.30-\$0.60/GPU-hr; a 4x RTX 5090 rig at 80% utilization generates \$700-\$1,400/month; H100/H200 earn \$2.15-\$4.00+/GPU-hr.  
  Sources: https://vast.ai/article/how-much-money-can-you-earn-renting-out-your-gpu-on-vast-ai
- _(high)_ H100 on-demand rental spans roughly \$1.49-\$6.98/hr across 15+ providers in 2026, clustering at \$2-\$4/hr; specialized GPU clouds run 50-75% cheaper than hyperscalers for the same hardware.  
  Sources: https://intuitionlabs.ai/articles/h100-rental-prices-cloud-comparison · https://getdeploying.com/gpus/nvidia-h100
- _(high)_ RunPod's documented 1-7% revenue share is for Hub repository/template deployers (paid to RunPod credit, tiered by monthly usage; 1% lifetime on template referrals), NOT for raw GPU hosts. The Community Cloud host split is invite-only/vetted and undisclosed.  
  Sources: https://docs.runpod.io/hub/revenue-sharing · https://www.runpod.io/product/runpod-hub
- _(high)_ Salad targets gamers with idle rigs and caps advertised earnings at 'up to \$180 every month' for a guaranteed-workload GPU (3090/3090Ti/4090); real-world earnings run ~\$30-\$200/month, paid in 'Salad Balance' (gift cards, games, crypto, PayPal), not cash salary. One user's 4x RTX 5090 made \$460 in 30 days.  
  Sources: https://salad.com/download-high-end · https://www.youtube.com/watch?v=o9Yw4pfPbLk
- _(high)_ io.net suffered a 2024 Sybil attack: ~1.8M fake GPUs attempted to connect and ~400,000 workers were spoofed seeking token rewards; the CEO postmortem confirmed it and Proof-of-Work GPU verification was introduced in April 2024 in response.  
  Sources: https://www.theblock.co/post/291315/solana-based-depin-io-net-ceo-claims-network-was-attacked-in-detailed-postmortem · https://x.com/ionet/status/1780877493672595941
- _(high)_ io.net markets 327,000 'registered' GPUs but in Q1 2025 the daily average of verified, active GPUs was only 6,720 (~2% of the registered base), with ~5,350 cluster-ready on a given day; verified count fell 11.1% QoQ even as revenue grew. This is the headline credibility gap of DePIN supply numbers.  
  Sources: https://messari.io/report/state-of-io-net-q1-2025
- _(high)_ Akash Network's GPU traction shrank through 2025: Q4 2025 averaged 63.3 active providers, GPU usage fell 46.1% QoQ (367 to 198 GPUs), and capacity dropped 16.4% QoQ (702 to 587) as providers exited. Foundry (DCG-backed) is the largest single supplier.  
  Sources: https://messari.io/report/state-of-akash-q4-2025 · https://akash.network/blog/q4-2025-report/
- _(medium)_ Vast.ai verification is automated/randomized and prioritizes datacenter-grade gear; 'Mining rigs may never be verified,' and verified H100s list around \$1.50-\$1.87/hr while unverified ones list near \$0.90/hr and 'mostly sit idle.' Consumer-host net profit after electricity is thin (~\$8/mo RTX 3080, ~\$52/mo RTX 4090 per independent guides).  
  Sources: https://vast.ai/article/how-much-money-can-you-earn-renting-out-your-gpu-on-vast-ai · https://earnifyhub.com/learning-guides/make-money-renting-out-gpu-2026

### Refuted / do-not-repeat

- TensorDock on-demand H100 SXM5 = \$2.25/hr, A100 SXM4 80GB = \$1.80/hr, RTX 4090 = \$0.35/hr, H100 spot = \$1.30/hr - REFUTED as current. Only H100 on-demand (~\$2.25 on the live page) is in range; independent aggregator computeprices.com (June 2026) shows H100 \$1.99/hr, A100 80GB \$0.95/hr, RTX 4090 \$0.32/hr, and the \$1.30 spot figure is stale (live spot ~\$1.91). Treat the \$1.80/\$0.35/\$1.30 trio as fabricated/stale composite, do not repeat.
- RunPod's 1-7% figure as a GPU-HOST commission - KILLED. It is the Hub repository-deployer revenue share paid to RunPod credit, not the Community Cloud host payout (which is undisclosed). Never cite it as RunPod's marketplace take rate on hosts.
- Any specific Vast.ai commission percentage stated as official - KILLED. Vast does not publish a commission; only a self-reported ~25% renter-vs-host spread exists. Third-party '10-15%' and '25-30%' estimates are unsourced competitor-blog guesses, demote to 'estimated, unverified.'
- TensorDock's 75/25 split as independently verified - DEMOTE the independence claim. The split is confirmed only by TensorDock's own pages and legal agreement; the serp.co review reproduces the marketing text verbatim and is not independent corroboration.

## Crypto / DePIN incentive networks

**Headline.** DePIN compute is a ~\$10B market cap sitting on ~\$72M of verifiable 2025 revenue: real paid AI-inference demand exists but is small, concentrated, and dwarfed by token-subsidized headline capacity; the largest revenue claims are the least auditable.

### Verified findings

- _(high)_ Messari's State of DePIN 2025 puts the whole DePIN sector at roughly \$10B circulating market cap but only ~\$72M in real FY25 on-chain revenue, with leading networks trading at ~10-25x revenue (vs >1,000x in the 2021 cycle). This is the load-bearing sector-level number.  
  Sources: https://messari.io/report/state-of-depin-2025 · https://decrypt.co/356349/depin-tokens-lag-revenues-rise-fundamentals · https://incrypted.com/en/depin-projects-generated-72m-in-onchain-revenue-in-2025-report/
- _(high)_ An independent reality check (BlockEden, March 2026) counts 650+ DePIN projects with a combined market cap that briefly topped ~\$19B, yet ~\$110k average annual revenue per project and fewer than 20 projects generating meaningful non-token revenue. Confirms a small revenue core and a long subsidized tail.  
  Sources: https://blockeden.xyz/blog/2026/03/21/depin-march-2026-reality-check-650-projects-19b-market-cap-revenue/
- _(high)_ Akash Network's demand is the most independently auditable (on-chain in Cosmos explorers / Messari): ~60% utilization on accelerated compute, ~367 active GPUs of ~702 total capacity in Q3 2025, daily fees hitting all-time highs >\$13k. Network spend more than doubled YoY. The verifiable absolute numbers are small (low single-digit millions).  
  Sources: https://messari.io/report/state-of-akash-q3-2025 · https://akash.network/blog/akash-2025-year-in-review/
- _(high)_ io.net suffered an April 2024 Sybil/GPU-metadata attack: ~1.8M fake GPUs attempted to connect and active GPU connections collapsed from ~600,000 to ~100,000 after security patches. This is the canonical example of headline GPU counts diverging from real verified capacity.  
  Sources: https://cointelegraph.com/news/io-net-responds-to-gpu-metadata-attack · https://www.theblock.co/post/291315/solana-based-depin-io-net-ceo-claims-network-was-attacked-in-detailed-postmortem · https://cryptonews.com/news/io-net-ceo-details-recent-sybil-attack-and-new-security-measures/
- _(high)_ io.net (June 2026) introduced an Incentive Dynamic Engine that permanently burns at least 50% of post-payout network revenue in IO, with a stated minimum of ~12M IO burned over the coming year and a first burn executed on its June 11 2026 third anniversary; the network reported >4 billion AI inference tokens processed per day. Corroborated across multiple outlets and io.net's own litepaper.  
  Sources: https://www.coindesk.com/press-release/2026/06/11/io-net-to-burn-up-to-12m-tokens-as-network-closes-usd8m-deal-and-hits-4-billion-daily-ai-tokens · https://crypto.news/io-net-incentive-dynamic-engine-burn/
- _(high)_ io.net (IO) circulating supply is ~349.5M of a max 800M (~43.7%), market cap ~\$62M against FDV ~\$143M as of June 2026 - i.e. less than half the supply circulates, implying material future dilution. Cross-checked against both CoinGecko and CoinMarketCap.  
  Sources: https://www.coingecko.com/en/coins/io-net · https://coinmarketcap.com/currencies/io-net/
- _(high)_ Bittensor (TAO) executed its first Bitcoin-style halving on December 14 2025, cutting issuance from ~7,200 to ~3,600 TAO/day (1 to 0.5 TAO per block); dTAO (Feb 2025) routes emissions via subnet alpha-token markets. TAO carried a multi-billion market cap with no comparable verifiable compute revenue.  
  Sources: https://crypto.com/us/market-updates/bittensor-halving-all-you-need-to-know · https://www.dlnews.com/articles/defi/bittensor-halving-seen-to-boost-tao-price-and-starve-zombie-subnets/ · https://research.grayscale.com/reports/bittensor-on-the-eve-of-the-first-halving
- _(high)_ Render Network operates a Burn-Mint Equilibrium (BME) model (USD value of RENDER burned per job minus a ~5% fee, fiat payments converted and burned). It discloses burns/emissions but NOT USD job revenue. 2025 saw >22M frames rendered and the 1-millionth lifetime RENDER burned; market cap roughly \$940M-\$1.15B in late 2025/2026.  
  Sources: https://know.rendernetwork.com/basics/burn-mint-equilibrium · https://rendernetwork.medium.com/render-network-foundation-monthly-report-december-2025-43d956808e3f
- _(high)_ Gensyn never reached mainnet compute revenue: it ran a testnet (RL Swarm, now PAUSED, with focus shifting to the Delphi prediction-market app) and launched a December 2025 token sale of 300M \$AI (3% of supply) via an English auction on Sonar with a \$1M FDV floor and \$1B FDV cap.  
  Sources: https://chainwire.org/2025/12/15/gensyn-launches-ai-token-sale-on-sonar/ · https://docs.gensyn.ai/testnet
- _(medium)_ Kuzco (rebranding toward Inference.net) is pre-token, rewarding contributors with KZO points. By 2025 it reported 6,000+ GPUs supplying ~98TB of VRAM and claimed >90% per-GPU utilization. Exact connected-node counts vary by source (roughly 5K-8.5K), and the >90% utilization figure is self-reported.  
  Sources: https://solanacompass.com/projects/kuzco · https://www.kzoptimize.com/
- _(medium)_ Nosana surpassed 50,000 independent GPU hosts since its January 2025 mainnet, pays hosts per completed inference job in NOS (streamed by the second), and advertises GPU pricing from ~\$0.048/hr with a demonstrated ~68% inference cost reduction in one case (vendor claims up to 85%). Cost-savings figures are vendor/marketing-sourced.  
  Sources: https://nosana.com/hosts/ · https://solanacompass.com/projects/nosana
- _(high)_ Spheron's Fizz nodes target consumer-grade hardware; operators keep ~90% of user lease payments and must maintain at least 50% uptime within a 24-hour ERA to accrue rewards. (Note: the 90% figure is the operator's revenue share, NOT an uptime requirement - the uptime floor is 50%.)  
  Sources: https://docs.spheron.network/fizz/reward-details · https://thedefiant.io/news/press-releases/spheron-introduces-fizz-node-for-flexible-ai-compute-resources
- _(low)_ Aethir self-reported \$127.8M+ revenue for Jan-Dec 2025, 1.5B+ compute hours, 440,000+ GPU containers across 94 countries, and \$166M ARR by Q3 2025 - published on Aethir's own blog/X, closed-source, not on DeFiLlama/Token Terminal, and not on-chain auditable. Treat as VENDOR-SOURCED and unverified.  
  Sources: https://aethir.com/blog-posts/aethirs-2025-wrap-up-decentralized-gpu-cloud-milestones
- _(medium)_ Despite claiming \$127.8M of 2025 revenue, Aethir (ATH) traded around \$83M market cap (~\$0.0041) in June 2026 - below its claimed annual revenue and ~96.6% off its \$0.12 all-time high - an inverse anomaly suggesting the market heavily discounts the self-reported figures.  
  Sources: https://metamask.io/price/aethir
- _(high)_ Aethir received a \$343.5M (closed; ~\$344M announced) private placement into ATH tokens via a Digital Asset Treasury run by Nasdaq-listed Predictive Oncology (POAI), closing October 8 2025. This is treasury/token-purchase capital, NOT compute revenue, and must not be conflated with ARR.  
  Sources: https://www.globenewswire.com/news-release/2025/09/29/3157798/0/en/Predictive-Oncology-Inc-Announces-Private-Placements-of-344-Million-to-Initiate-a-Digital-Asset-Treasury-Strategy-Focused-on-Aethir-ATH-Tokens.html · https://cointelegraph.com/news/predictive-oncology-depin-treasury-aethir-ath-token
- _(high)_ Crypto VCs are openly split on the sector: Meltem Demirors (Crucible Capital) wrote 'DePIN is dying and i don't see it coming back,' while Dan Elitzer (Nascent) called many DePIN projects 'almost entirely thinly veiled shitcoin ICOs.' Operators counter that the sector is maturing 'from hype to substance.'  
  Sources: https://thedefiant.io/news/infrastructure/crypto-vcs-debate-depin

### Refuted / do-not-repeat

- io.net's '\$8M largest-ever enterprise contract generating ~\$650k/month on-chain' (announced June 11 2026): DROPPED. Every outlet traces to a single io.net GlobeNewswire press release (the CoinDesk link is a paid /press-release/ placement); the customer is unnamed, no on-chain data is cited, and the \$650k/month is a forward projection ('expected to contribute'), not verified realized earnings. Numbers are quoted accurately but fail the independence test - do not present as fact.
- '1,000+ GPUs' for Akash: SOFTENED. The auditable Q3 2025 figure is ~367 active GPUs of ~702 total capacity (Messari); the ~1,000 figure is not the verified active base.
- '~\$3.15M total Akash network spend in 2025' and '~\$4.3M ARR': NOT independently confirmed at the exact dollar value in this pass. Akash spend 'more than doubled YoY' and daily fees exceeded \$13k are confirmed; cite the directional/auditable figures rather than the precise headline dollar total until checked against a Cosmos explorer.
- 'Render ~\$2.7M 2025 revenue (third-party estimate)': UNVERIFIED third-party estimate. Render does not disclose USD job revenue; present only burns/frames as confirmed, and flag any USD revenue figure as an external estimate.
- Aethir's 'Rev/MC beat Filecoin by 135%, Render by 455%, Bittensor by 14x': DEMOTED to vendor self-promotion (Aethir wrap-up). Built on the same unverified revenue base - do not repeat as an independent finding.
- Spheron Fizz '90% uptime to earn': WRONG conflation. 90% is the operator's lease-revenue share; the uptime floor is 50% within a 24h ERA. Use the corrected figures.
- Inference.net/Kuzco '6,000-8,500 GPU nodes, >90% per-GPU utilization': PARTIALLY VERIFIED. 6,000+ GPUs / ~98TB VRAM confirmed; node-count range and the >90% utilization claim are self-reported and vary by source - flag as vendor-sourced.

## Volunteer / open-source distributed computing (the PS3 lineage)

**Headline.** Volunteer compute is real and old, but it runs on altruism, not money: it scales spectacularly during crises (Folding@home's COVID exaFLOP) and for tiny fault-tolerant jobs (AI Horde), and collapses for low-latency frontier-model serving (Petals).

### Verified findings

- _(high)_ Folding@home's PlayStation 3 client ran 23 March 2007 to 6 November 2012; over 15 million PS3 users donated more than 100 million computational hours. The program ended 'following discussions with Sony' with no detailed public reason given.  
  Sources: https://foldingathome.org/faqs/high-performance/folding-sony-playstation-3-ps3/ · https://en.wikipedia.org/wiki/Folding@home · https://en.wikipedia.org/wiki/Life_with_PlayStation
- _(medium)_ Folding@home crossed 1 petaFLOPS on 16 September 2007 and was recognized by Guinness World Records as the most powerful distributed computing network, a milestone the PS3 client drove (reported PS3 share ~0.93 of 1.194 petaFLOPS, i.e. ~78%; the exact split is from secondary aggregation and should be treated as approximate).  
  Sources: https://sonyinteractive.com/en/press-releases/playstation3-enables-foldinghome-to-be--recognized-by-guinness-world-records-as-worlds--most-powerful-distributed-computing-network/ · https://en.wikipedia.org/wiki/Folding@home
- _(high)_ During the COVID-19 surge, Folding@home reached 470 native petaFLOPS (958 x86 PF) on 20 March 2020 and 768 native PF / ~1.5 x86 exaFLOPS by 25 March 2020 - described as the first exaFLOP-scale computing system - after active devices grew from ~30,000 (Jan 2020) to roughly 1 million in three months. It produced 226 scientific papers and has since fallen to 12.9 native PF (24.8 x86) by 31 Oct 2025.  
  Sources: https://en.wikipedia.org/wiki/Folding@home
- _(high)_ Rosetta@home fed David Baker's Rosetta software; Baker shared the 2024 Nobel Prize in Chemistry (with Hassabis and Jumper) for computational protein design. The project, run by UW's Institute for Protein Design, used distributed volunteer compute and had ~200,000 volunteers by early 2008.  
  Sources: https://www.hhmi.org/hhmi-david-baker-wins-2024-nobel-chemistry · https://en.wikipedia.org/wiki/David_Baker_(biochemist) · https://vcomp.org/en/projects/rosetta-at-home
- _(high)_ SETI@home hibernated on 31 March 2020 after 21 years; it had the most lifetime participants of any volunteer project (~5.2M), found zero confirmed extraterrestrial signals, and is the named ancestor of the BOINC middleware.  
  Sources: https://en.wikipedia.org/wiki/SETI@home
- _(high)_ GIMPS found the largest known prime, 2^136,279,841 − 1 (41,024,320 digits), on 12 Oct 2024 - the first Mersenne prime found on GPUs. Ex-Nvidia engineer Luke Durant used a self-funded 'cloud supercomputer' of thousands of rented datacenter GPUs across 24 regions/17 countries, reportedly spending around \$2 million; the standard GIMPS award is only \$3,000.  
  Sources: https://www.mersenne.org/primes/?press=M136279841 · https://www.popsci.com/science/largest-prime-number/ · https://www.tomshardware.com/tech-industry/former-nvidia-engineer-discovers-41-million-digit-prime-largest-prime-number-known-to-man-was-uncovered-and-verified-with-the-help-of-gpus
- _(high)_ AI Horde (run by the non-profit Haidra, funded by donations and NLnet/NGI0) is a live volunteer network. A June 2026 live API snapshot showed ~13 image workers + 30 text workers, ~565 image and ~29 text requests queued, ~671 megapixelsteps/min and ~33,480 tokens/min throughput. All-time cumulative: 181,015,719 images and 272,684,437 text requests / 59,940,291,980 tokens.  
  Sources: https://aihorde.net/api/v2/status/performance · https://aihorde.net/api/v2/stats/img/totals · https://aihorde.net/api/v2/stats/text/totals
- _(high)_ AI Horde's 'kudos' incentive is explicitly non-monetary: kudos are 'inherently valueless,' cannot be exchanged for money or crypto (offenders' accounts are zeroed out), and the project is explicitly hostile to blockchain and 'will never integrate with any of them.' Kudos buys only queue priority and reputation.  
  Sources: https://github.com/Haidra-Org/AI-Horde/blob/main/FAQ.md · https://stablehorde.net/faq/
- _(high)_ Petals (BitTorrent-style distributed LLM inference, built on Hivemind by Yandex Research / HSE / UW / Hugging Face / ENS Paris-Saclay; authors Borzunov and Ryabinin) is effectively abandoned as a public swarm: last release v2.2.0 on 6 Sep 2023, last commit 25 Aug 2024, and its health monitor lists flagship models as needing more servers.  
  Sources: https://github.com/bigscience-workshop/petals · https://api.github.com/repos/bigscience-workshop/petals/commits?per_page=1 · https://health.petals.dev/
- _(high)_ Hivemind, the underlying PyTorch decentralized-training library (Kademlia DHT, DMoE, fault-tolerant all-reduce), is still maintained: release 1.1.12 published 3 January 2026.  
  Sources: https://github.com/learning-at-home/hivemind/releases
- _(medium)_ distributed.net (1997) is still grinding RC5-72 in 2026 with an effectively astronomical time-to-exhaustion - a standing illustration of the sustainability ceiling of pure-altruism volunteer compute.  
  Sources: https://en.wikipedia.org/wiki/Distributed.net

### Refuted / do-not-repeat

- Do NOT claim distributed.net will exhaust the RC5-72 keyspace in '~36 years' as a firm figure - projected completion times vary wildly with throughput and the precise number is not robustly sourced; state only that it remains unfinished after ~3 decades.
- Do NOT state the PS3 launch date as definitively '23 March 2007' without hedging - sources split between 22 and 23 March 2007 for the firmware/client; the substance (March 2007) holds but the exact day is weakly corroborated.
- Do NOT present the PS3's '~78% of Folding@home power' as a clean primary fact - the 0.93/1.194 PF split comes from secondary aggregation; report it as approximate.
- Do NOT imply GIMPS' record prime was found by federated home volunteers - it was found on rented datacenter GPUs by a single self-funded individual (Luke Durant).
- Do NOT describe OpenAssistant as crowd-COMPUTE - it was a crowd-DATA effort (13,500+ volunteers, ~600k data points) wound down in 2023-2024, and does not belong in a compute-federation comparison.
- Do NOT cite a combined Folding@home '~2.4 ExaFLOPS by 12 Apr 2020' figure as established - it traces to a single secondary outlet (TechSpot) and was not independently confirmed here; the verified peak is 768 native PF / ~1.5 x86 EF on 25 Mar 2020.
- Do NOT claim Petals is 'actively maintained' on the strength of its README marketing language - the commit/release timeline (last commit Aug 2024) contradicts it.

## Decentralized / distributed training

**Headline.** Low-communication algorithms made decentralized training of mid-sized models genuinely real by 2026, but the frontier itself remains centralized, and the flagship project's own best model retreated to an InfiniBand datacenter.

### Verified findings

- _(high)_ The core algorithmic enabler is DiLoCo (Douillard et al., Google DeepMind, Nov 2023): each replica runs hundreds of local 'inner' steps (typically H=500) and synchronizes only 'outer' pseudo-gradients, cutting inter-node communication by roughly 500x. The binding constraint is bandwidth, not latency, because infrequent syncing tolerates high latency.  
  Sources: https://arxiv.org/abs/2311.08105
- _(high)_ OpenDiLoCo (Prime Intellect, 11 July 2024) reproduced DiLoCo across 2 continents / 3 countries at billion-parameter scale (up to 1.1B params) while maintaining 90-95% compute utilization, scaling the method to 3x the original work's size.  
  Sources: https://www.primeintellect.ai/blog/opendiloco · https://arxiv.org/html/2407.07852v1
- _(high)_ 'Scaling Laws for DiLoCo' (DeepMind, arXiv:2503.09799, Mar 2025) found that when well-tuned, DiLoCo scales BETTER than data-parallel as model size grows: M=2 replicas achieve lower loss than data-parallel above several billion parameters, validated on 4B and 10B runs, with larger optimal batch sizes as a bonus.  
  Sources: https://arxiv.org/abs/2503.09799 · https://arxiv.org/html/2503.09799
- _(high)_ INTELLECT-1 (Prime Intellect, Dec 2024) was the first 10B-parameter model collaboratively trained across the globe: 1T tokens, up to 14 concurrent nodes / 112 H100 GPUs, 30 independent compute providers, 5 countries / 3 continents, 42-day run (10 Oct to 22 Nov 2024). Achieved 83% compute utilization across continents and 96% US-only, with a claimed ~400x bandwidth reduction. Independently confirmed by the technical report arXiv:2412.01152.  
  Sources: https://www.primeintellect.ai/blog/intellect-1 · https://arxiv.org/abs/2412.01152
- _(high)_ INTELLECT-2 (Prime Intellect, May 2025) was the first globally distributed RL run of a 32B model, with permissionless contribution. Benchmark gains over its QwQ-32B base were marginal (AIME24 +2.2, AIME25 +0.1, IFEval actually DROPPED 83.4 to 81.5), and the team explicitly admitted 'it was difficult to obtain huge amounts of generalized improvement on benchmarks.'  
  Sources: https://arxiv.org/html/2505.07291v1 · https://www.primeintellect.ai/blog/intellect-2
- _(high)_ DECISIVE ADVERSARIAL DATAPOINT: Prime Intellect's flagship INTELLECT-3 (106B MoE / 12B active, post-trained from GLM-4.5-Air, released ~27 Nov 2025) was NOT trained decentralized. It ran on a centralized 512x H200 cluster with 400Gbps NDR InfiniBand over ~2 months. Reason: asynchronous RL discards rollouts that drift more than 8 steps behind the current policy, which 'demands InfiniBand, not commodity broadband from someone's garage.'  
  Sources: https://www.primeintellect.ai/blog/intellect-3 · https://x.com/PrimeIntellect/status/1993895069951422817 · https://www.implicator.ai/prime-intellects-intellect-3-open-source-ambition-meets-centralized-reality/
- _(high)_ Epoch AI (Jaime Sevilla, director; 'How far can decentralized training over the internet scale?', Dec 2025) independently estimates the largest decentralized runs (INTELLECT-1, Pluralis Protocol Model 8B, Nous Consilience 40B) at 6e22-6e23 FLOP, i.e. ~1000x less compute than the largest frontier models (e.g. Grok 4). Decentralized compute is growing ~20x/year (600,000x since 2020) but, in Epoch's words, 'we won't see decentralized training runs catch up to the frontier of training in scale this decade.'  
  Sources: https://epoch.ai/gradient-updates/how-far-can-decentralized-training-over-the-internet-scale
- _(high)_ Epoch AI quantifies the aggregation penalty: scaling from 1 to 8 nodes already causes a ~1.5x compute decrease, implying that scaling to 10,000 nodes would require ~6x the FLOP of centralized training for the same performance. The bottleneck is therefore economic/compute-aggregation, not pure physics.  
  Sources: https://epoch.ai/gradient-updates/how-far-can-decentralized-training-over-the-internet-scale
- _(high)_ Templar (Bittensor Subnet 3) completed Covenant-72B on 10 Mar 2026, claimed as the largest decentralized LLM pretraining ever: 72B params, ~1.1T tokens, 70+ permissionless commodity-GPU contributors over home internet. Its SparseLoCo algorithm claims a 146x communication reduction via sparsification + 2-bit quantization + error feedback. Performance is only 'comparable to Llama-2-70B' (a 2023-era model), and ~1.1T tokens is far below the 15T+ of modern frontier pretraining.  
  Sources: https://arxiv.org/pdf/2603.08163 · https://www.emergentmind.com/papers/2603.08163 · https://taodaily.io/templars-covenant-72b-becomes-the-largest-decentralized-llm-training-run-ever-completed/
- _(high)_ Nous Research's Psyche network is pretraining Consilience-40B over ~20T tokens (the largest internet-pretraining run by token count), coordinated on the Solana blockchain and built on the DisTrO/DeMo optimizer family, which claims communication reductions of several orders of magnitude. The 40B target is deliberately sized to train on a single DGX and run inference on a single RTX 3090.  
  Sources: https://nousresearch.com/nous-psyche · https://huggingface.co/PsycheFoundation/consilience-40b-CqX3FUm4 · https://importai.substack.com/p/import-ai-413-40b-distributed-training
- _(high)_ Pluralis Research's 'Protocol Models' (arXiv:2506.01260, June 2025) use Subspace Networks to compress activations/gradients between pipeline stages by up to 100x (99% compression) with no convergence degradation, training an 8B LLaMA over consumer internet as slow as 80 Mbps and matching a 100Gbps-datacenter convergence baseline.  
  Sources: https://arxiv.org/abs/2506.01260 · https://pluralis.ai/blog/pluralis-multi-party-training-stack/
- _(high)_ Many of these projects are entangled with crypto-token economics, so headline figures are often token-price-correlated marketing rather than peer review. Templar runs on Bittensor (TAO/alpha tokens); Nous Psyche coordinates on Solana; Gensyn (a16z-backed, ~\$50M raised) launched an RL Swarm testnet (Mar 2025) with an \$AI token for payments/staking/governance.  
  Sources: https://nousresearch.com/nous-psyche · https://docs.gensyn.ai/testnet/rl-swarm · https://www.panewslab.com/en/articles/eaulwlvx

### Refuted / do-not-repeat

- 'Gensyn's \$AI token at \$1B FDV' - NOT confirmed. Only a ~\$50M a16z-led raise and an \$AI utility token (payments/staking/governance) on a testnet are documented; no \$1B fully-diluted-valuation figure was found in primary sources. Do not repeat the \$1B FDV number.
- 'INTELLECT-2 requires a minimum of 4x RTX 3090 to contribute' - the 32B size, permissionless design, and consumer-GPU sufficiency are independently corroborated, but the SPECIFIC '4x RTX 3090 minimum' figure is single-sourced to Prime Intellect's own blog and was NOT independently verified. State it as vendor-claimed, not as established fact.
- 'INTELLECT-3 ... reality is that frontier RL requires centralized clusters' as a verbatim quote - the implicator.ai article's verbatim text is the eight-step-staleness / 'demands InfiniBand, not commodity broadband' passage. The crisp 'frontier RL requires centralized clusters' wording is a paraphrase of the article's thesis, not a word-for-word quote; attribute it as a characterization, not a direct quotation.
- 'Covenant-72B is frontier-scale' - reject. It matches Llama-2-70B (2023) and is ~1000x below frontier compute per Epoch AI; 'largest DECENTRALIZED run' is defensible, 'frontier-scale' is not.
- Nous DisTrO '1000x-10000x' communication reduction - vendor-stated range from Nous; the published DeMo paper and Epoch AI's FLOP estimate support that Consilience is real and large by token count, but treat the specific 1000x-10000x multiplier as a claim, not a verified benchmark.

## Yann LeCun and the open / commons AI debate

**Headline.** Yann LeCun has become the most prominent industry advocate for AI-as-commons, and his 2026 moves (the AMI Labs startup, the AI Alliance's Project Tapestry) push that vision toward explicitly distributed, sovereign compute - but the actual non-datacenter training movement remains small, frequently retreats to conventional NVIDIA clusters for its flagship runs, and is partly token-subsidized.

### Verified findings

- _(high)_ LeCun's core public thesis since Dec 2023: open foundation models will displace closed ones the way Wikipedia beat commercial encyclopedias, on grounds of cultural/linguistic diversity. Verbatim quote confirmed on his own X/LinkedIn posts and corroborated in substance by independent journalism (TIME).  
  Sources: https://x.com/ylecun/status/1738641767405138223
- _(high)_ LeCun frames concentration of power via proprietary AI as a greater danger than open models - the foundational 'AI as commons' argument. Quote verified verbatim in the Lex Fridman #416 transcript (recorded/published 2024-03-07) and echoed by NYU CDS and CBS News.  
  Sources: https://lexfridman.com/yann-lecun-3-transcript/
- _(high)_ LeCun left Meta (departure reported Nov 2025; effective around Jan 2026) and co-founded Advanced Machine Intelligence Labs (AMI), HQ Paris with hubs in NY, Montreal, Singapore, focused on world models / JEPA rather than LLMs.  
  Sources: https://techcrunch.com/2026/03/09/yann-lecuns-ami-labs-raises-1-03-billion-to-build-world-models/
- _(high)_ AMI Labs raised a \$1.03B (890M EUR) seed at a \$3.5B pre-money valuation, reported as Europe's largest-ever seed round (announced ~9 March 2026). Co-led by Cathay Innovation, Greycroft, Hiro Capital, HV Capital, and Bezos Expeditions; strategic backers reported include Nvidia, Samsung, Temasek, Toyota Ventures, Bpifrance. Meta did not invest.  
  Sources: https://techcrunch.com/2026/03/09/yann-lecuns-ami-labs-raises-1-03-billion-to-build-world-models/ · https://news.crunchbase.com/venture/world-model-ai-lab-ami-raises-europes-largest-seed-round/ · https://x.com/ylecun/status/2031268686984527936
- _(high)_ On 7 April 2026 LeCun was named Chief Science Advisor to the AI Alliance (200+ member orgs), which launched Project Tapestry - an open-source platform for distributed, globally federated training of frontier open models where institutions/nations contribute while retaining control of data and producing sovereign derivative models. This is the most direct link from LeCun's commons rhetoric to non-hyperscaler distributed compute.  
  Sources: https://www.prnewswire.com/news-releases/ai-alliance-launches-project-tapestry-to-build-a-collaborative-foundation-for-open-and-sovereign-ai-302735918.html · https://thealliance.ai/projects/tapestry
- _(high)_ At the AI Pulse conference (4 Dec 2025) LeCun gave the canonical 2025 read of the open debate, verbatim: 'OpenAI, of course, stopped being open quite a long time ago. Anthropic never was'; Meta 'is kind of rethinking its strategy about open source... maybe not as systematic as it used to be'; and 'the best open source models at the moment in the LLM world are all Chinese.'  
  Sources: https://officechai.com/ai/meta-is-rethinking-its-strategy-on-open-source-former-chief-scientist-yann-lecun/
- _(high)_ EleutherAI (non-profit, Stella Biderman et al.) released the Common Pile v0.1 on 5-6 June 2025: an 8TB dataset of openly-licensed/public-domain text from 30 sources, built with U Toronto/Vector, Hugging Face, AI2, MIT, CMU, LLNL and others. It trained Comma v0.1-1T and v0.1-2T (two 7B models on 1T and 2T tokens) that match Llama 1/2 7B - a falsifiable rebuttal to the claim that unlicensed text is necessary for performance. This is a data/legal-commons argument; the models were trained on conventional clusters.  
  Sources: https://blog.eleuther.ai/common-pile/ · https://arxiv.org/abs/2506.05209 · https://techcrunch.com/2025/06/06/eleutherai-releases-massive-ai-training-dataset-of-licensed-and-open-domain-text/
- _(high)_ Prime Intellect (SF, founded 2023) trained INTELLECT-2 (32B), the first 32B model trained via globally distributed reinforcement learning across a heterogeneous swarm of permissionless compute contributors (May 2025, open-sourced with PRIME-RL, TOPLOC, SHARDCAST).  
  Sources: https://www.primeintellect.ai/blog/intellect-2-release · https://arxiv.org/abs/2505.07291
- _(high)_ Prime Intellect's flagship INTELLECT-3 (106B MoE, 12B active, built on GLM-4.5-Air; late Nov 2025) was trained NOT on a decentralized swarm but on a conventional centralized cluster of 512 NVIDIA H200 GPUs across 64 nodes over ~2 months. The flagship retreated to centralized hardware - a key adversarial flag.  
  Sources: https://www.primeintellect.ai/blog/intellect-3 · https://www.implicator.ai/prime-intellects-intellect-3-open-source-ambition-meets-centralized-reality/
- _(high)_ Nous Research raised a \$50M Series A led by Paradigm (April 2025) at a ~\$1B token valuation, and runs Psyche on the Solana blockchain to pool idle consumer- and industrial-grade GPU compute (Nous DisTrO reduces inter-node bandwidth); it ran a 15B test run in Dec 2024. Crypto/token incentives are explicit - contribution framed as a transaction, not a donation.  
  Sources: https://siliconangle.com/2025/04/25/nous-research-raises-50m-decentralized-ai-training-led-paradigm/ · https://www.theblock.co/post/352000/paradigm-leads-50-million-usd-round-decentralized-ai-project-nous-research
- _(high)_ The EU AI Gigafactories program (Council Reg. (EU) 2026/150; ~20B EUR InvestAI; 3-5 sites of ~100,000 chips each; EU covers up to 17% of capex) drew an informal call (closed 20 June 2025) of 76 expressions of interest covering 60 sites across 16 member states, with >230B EUR proposed and >=3M GPUs foreseen - but the formal call was deferred into early/Q2 2026.  
  Sources: https://digital-strategy.ec.europa.eu/en/news/overwhelming-response-76-respondents-express-interest-european-ai-gigafactories-initiative · https://www.lightreading.com/ai-machine-learning/eu-defers-formal-call-for-ai-gigafactories-to-early-2026
- _(high)_ New York's Empire AI consortium (10 member universities/institutions) is backed by \$500M+ in public+private funding, including up to \$340M in state capital; its Beta supercomputer at the University at Buffalo uses NVIDIA's Blackwell platform and is ~11x prior capacity. State-funded but conventional datacenter hardware.  
  Sources: https://www.governor.ny.gov/news/governor-hochul-announces-90-million-plan-expand-historic-empire-ai-consortium-and-enhance · https://www.hpcwire.com/off-the-wire/state-of-new-york-invests-40m-to-launch-empire-ai-beta-with-nvidia-blackwell-supercomputing/
- _(medium)_ The US NAIRR Pilot (NSF + 14 federal agencies + 28 private/nonprofit partners; Microsoft \$20M Azure credits, NVIDIA \$30M incl. \$24M DGX access) connected 400+ researchers and is transitioning to a permanent NAIRR Operations Center under solicitation NSF 25-546 (Sept 2025).  
  Sources: https://www.nsf.gov/focus-areas/ai/nairr · https://www.fiercesensors.com/electronics/nairr-pilot-gets-30m-nvidia-20m-azure
- _(medium)_ The Public AI Network (publicai.co) launched a Public AI Inference Utility in Q4 2025 - a free/low-cost utility serving open models (e.g. Switzerland's Apertus, Singapore's SEA-LION v4) with national system prompts; an inference 'public option' on open models, distinct from training compute.  
  Sources: https://publicai.substack.com/p/we-launched-the-inference-utility · https://huggingface.co/blog/inference-providers-publicai

### Refuted / do-not-repeat

- DROPPED PRECISION: NAIRR Pilot served '600+ projects / 6,000 students' - the primary NSF/partner sources confirm '400+ researchers/educators' and '28 partners / 14 agencies'; the 600/6,000 figures could not be corroborated, so we report 400+ and avoid the higher numbers.
- DO NOT conflate the public-interest Public AI Network (publicai.co / publicai.network, Madisen Taylor) with the unrelated '\$PUBLIC' / 'PublicAI' web3 token project at publicai.io - they are different entities despite near-identical names. Treating them as one would be an error.
- DO NOT describe Prime Intellect's INTELLECT-3 (106B) as 'decentralized/distributed training' - it was trained on a centralized 512x H200 / 64-node cluster. Only INTELLECT-1 (10B, 14 nodes/3 continents) and INTELLECT-2 (32B, permissionless RL swarm) are the genuinely distributed runs.
- DO NOT state Meta invested in AMI Labs - reporting is explicit that Meta did NOT invest; co-leads were Cathay Innovation, Greycroft, Hiro Capital, HV Capital, Bezos Expeditions.
- DO NOT call Llama or most 'open' frontier models fully 'open source' without qualification - they are open-WEIGHT with usage restrictions and do not meet the OSI open-source definition; this critique applies to LeCun's own past phrasing.
- DO NOT cite Bloomberg/TIME/CNBC figures as if primary-verified - those originals were paywalled (403); all numbers used here are corroborated through accessible secondary sources (TechCrunch, Crunchbase, PR Newswire, official .gov/.eu pages, arXiv, company blogs).
- DO NOT attribute the Wikipedia analogy to the Lex Fridman podcast - it comes from LeCun's Dec 2023 X/LinkedIn post; the podcast yielded the concentration-of-power quote only.

## Political economy and verdict

**Headline.** Compute concentration is the empirical core; decentralized compute is a real but bounded niche (inference/rendering), not a frontier challenger

### Verified findings

- _(high)_ Yanis Varoufakis (Technofeudalism: What Killed Capitalism, 2023; essay 'The Age of Cloud Capital', Persuasion, 29 April 2024) argues cloud capital is a mutation of capital that 'killed off its host', evicting profit and markets from the centre of the economy and replacing profit with 'cloud rent' - the toll paid for access to platforms (cloud 'fiefdoms' that resemble but are not markets). Verified verbatim against the primary source.  
  Sources: https://www.persuasion.community/p/the-age-of-cloud-capital
- _(high)_ The technofeudalism thesis is contested. Henry Snow (Jacobin, 27 Oct 2023) argues this is still capitalism, not feudalism: firms retain power only insofar as they command profit, users do freely migrate (e.g. to TikTok), and search results are literally sold in functioning ad markets - 'the defining feature of serfs is that they do not freely migrate.' Verified verbatim.  
  Sources: https://jacobin.com/2023/10/cloud-capitalism-technofeudalism-serfs-cloud-big-data-yanis-varoufakis
- _(high)_ Aaron Bastani (Fully Automated Luxury Communism, Verso, 2019) is the optimistic counter-pole: ever-cheaper compute and automation could push society past scarcity into abundance. Cited as the framework against which cheap-decentralized-compute claims should be read.  
  Sources: https://en.wikipedia.org/wiki/Fully_Automated_Luxury_Communism
- _(medium)_ NVIDIA reported record data-center revenue of \$75.2B in calendar Q1 2026 (fiscal Q1 FY2027), up ~92% YoY, with hyperscalers at roughly 50% (~\$38B). NVIDIA holds ~85-92% of the AI-accelerator market, projected to ease toward ~75% by 2026 as AMD and custom silicon (Google TPU, AWS Trainium, Broadcom ASICs) scale. This is the empirical core of compute concentration.  
  Sources: https://cryptobriefing.com/nvidia-data-center-revenue-75-billion/
- _(high)_ CoreWeave (a 'neocloud') reported \$5.13B FY2025 revenue with a \$66.8B contracted backlog but a \$1.17B GAAP net loss, with Microsoft at ~67% of 2025 revenue (up from 62% in 2024) - concrete evidence of the cloud-rent model AND of extreme customer concentration. Confirmed via CoreWeave's own FY2025 release and secondary reporting.  
  Sources: https://finance.yahoo.com/news/coreweave-crwv-reports-2025-revenue-195641826.html · https://investors.coreweave.com/news/news-details/2026/CoreWeave-Reports-Strong-Fourth-Quarter-and-Fiscal-Year-2025-Results/
- _(high)_ The frontier stays centralized. Per Epoch AI (Jaime Sevilla et al., 'How far can decentralized training over the internet scale?'), the largest decentralized pretraining runs (INTELLECT-1, Protocol Model 8B, Consilience 40B) sit at 6e22-6e23 FLOP, ~1000x below frontier models like Grok 4. Decentralized training grows ~20x/year vs ~5x/year for centralized, but Sevilla concludes 'we won't see decentralized training runs catch up to the frontier of training in scale this decade.' Bandwidth is the binding constraint: over consumer internet under a 10-minute sync you cap out at a ~600M-parameter model; only algorithmic tricks (DiLoCo's ~500x bandwidth reduction, Nous DeMo, Prime Intellect asynchronous RL) make larger runs viable. Verified against the primary source.  
  Sources: https://epoch.ai/gradient-updates/how-far-can-decentralized-training-over-the-internet-scale
- _(high)_ Inference/rendering/batch is the genuine, growing niche. Akash Network crossed ~\$5M compute spend in Q1 2026 (all-time high), reporting utilization above 80% and 428% YoY usage growth, per its own Q1 2026 report and secondary coverage. This is real demand, not purely token-subsidized.  
  Sources: https://akash.network/blog/akash-network-q1-2026-report/ · https://www.ainvest.com/news/akash-network-surpasses-5-million-compute-spend-ai-infrastructure-bottlenecks-2605/
- _(high)_ The web3 precedent is a strong cautionary tale on metric integrity. io.net's April 2024 Sybil attack saw ~1.8 million fake GPUs attempt to connect (io.net's own postmortem), and as of 2026 only ~6,720 daily-verified-active GPUs out of ~327,000 registered. Self-reported and token-inflated metrics are endemic.  
  Sources: https://cryptonews.com/news/io-net-ceo-details-recent-sybil-attack-and-new-security-measures/ · https://www.theblock.co/post/291315/solana-based-depin-io-net-ceo-claims-network-was-attacked-in-detailed-postmortem
- _(medium)_ The whole DePIN sector generated only ~\$72M real on-chain revenue in FY2025 against a circulating market cap of roughly \$10B (Messari, State of DePIN 2025), with only a small subset of 650+ projects producing meaningful non-token revenue. The gap between market cap and real revenue is the core hype signal.  
  Sources: https://messari.io/report/state-of-depin-2025 · https://decrypt.co/356349/depin-tokens-lag-revenues-rise-fundamentals

### Refuted / do-not-repeat

- Do NOT claim decentralized training 'will catch up to' or 'rival' the frontier - even on the optimistic ~20x/year vs ~5x/year trend Epoch AI computes ~5.5 years to parity AND Sevilla concludes it will NOT catch the frontier in scale this decade. Frame only as a growing gap-narrowing trend, never as convergence.
- Do NOT state DePIN revenue figures as audited/on-chain-verified for networks that self-report (io.net) or structurally do not disclose; flag provenance.
- Do NOT present io.net's ~327,000 'registered GPUs' (or similar advertised counts) as available capacity - use the ~6,720 daily-verified figure and note the ~1.8M fake-GPU Sybil history.
- Do NOT treat the technofeudalism thesis as settled fact - it is academically contested (Jacobin/Henry Snow). Attribute it as Varoufakis's argument, not a consensus description of the economy.
- Do NOT cite a single hard hyperscaler-capex total as fact - 2026 estimates range widely (~\$600B-\$725B) depending on source and AI-only vs total; present as analyst-consensus range, not a precise number. (Not independently re-verified in this pass.)
- Do NOT assert NVIDIA's exact accelerator share as a single point - sources give a band (~85-92%, easing toward ~75% by 2026); the \$75.2B/-92% figures trace to CFO commentary via secondary reporting, not re-verified here against NVIDIA's primary filing.

---

# Extension pass: renting to train, ecology, the commons

## Renting compute to train bigger than your hardware

**Headline.** A solo artist can full-finetune a 70B model on one rented 8-GPU node for low hundreds of dollars; the real gates are interconnect, privacy, and where the grid carbon comes from, not price.

### Verified findings

- _(high)_ H100 SXM5 on-demand has commoditized to roughly \$2-\$3/GPU-hr on specialist clouds (Lambda ~\$2.99, RunPod ~\$1.99-\$2.69, Vast ~\$1.87-\$2.00, Nebius ~\$2.00-\$2.95), with marketplace floors near \$1.49-\$2.00 and hyperscalers at ~\$4-\$12/GPU-hr list. Confirmed by 3+ independent surveys.  
  Sources: https://intuitionlabs.ai/articles/h100-rental-prices-cloud-comparison · https://www.synpixcloud.com/blog/cloud-gpu-pricing-comparison-2026 · https://getdeploying.com/gpus/nvidia-h100 · https://www.cloudzero.com/blog/h100-gpu-cost/
- _(high)_ The on-demand H100 market 'settled around \$2-4/GPU-hr' by late 2025; an 8x InfiniBand HGX node is priced per-GPU (e.g. CoreWeave \$6.16/GPU-hr = \$49.24/hr node; Oracle bare-metal 8xH100 = \$80/hr all-or-nothing).  
  Sources: https://intuitionlabs.ai/articles/h100-rental-prices-cloud-comparison · https://www.buildmvpfast.com/blog/gpu-cloud-cost-comparison-runpod-lambda-labs-coreweave-2026
- _(high)_ QLoRA on a 70B model fits a single 80GB H100, runs ~8-12 hours and costs roughly \$10-\$16 at ~\$1.33/hr; a FULL finetune of 70B needs an 8x H100 node for 24-48 hours at roughly \$250-\$510. PEFT is ~20-50x cheaper than full finetune. So a real artist finetune is tens of dollars, not thousands.  
  Sources: https://www.spheron.network/blog/how-to-fine-tune-llm-2026/ · https://io.net/blog/llm-fine-tuning-budget-guide-gpu-costs-timelines-and-what-to-spend · https://www.index.dev/blog/top-ai-fine-tuning-tools-lora-vs-qlora-vs-full
- _(high)_ Interconnect, not price, sets effective throughput across machines. Inside one 8x box GPUs use NVLink 4 (~900 GB/s); across nodes you depend on InfiniBand (~0.6 us latency, ~95% of theoretical bandwidth) vs Ethernet/RoCEv2 (~1-5 us tuned, degrading to 10-50 us under congestion). For a 70B/4-node job Ethernet typically adds 10-15% wall-clock vs InfiniBand NDR.  
  Sources: https://apxml.com/courses/how-to-build-a-large-language-model/chapter-18-hardware-considerations-llm-training/interconnect-technologies-nvlink-infiniband · https://www.spheron.network/blog/multi-node-gpu-training-without-infiniband/ · https://www.runpod.io/articles/guides/infiniband-for-distributed-ai-training
- _(high)_ The actionable rule for a solo user: anything that fits on ONE 8x H100/H200 node (640 GB / 1128 GB VRAM) uses NVLink internally and sidesteps the inter-node fabric question entirely. Multi-node InfiniBand is almost never needed by an individual; one node covers LoRA through full-finetune of 7B-70B.  
  Sources: https://www.spheron.network/blog/multi-node-gpu-training-without-infiniband/ · https://www.runpod.io/articles/guides/infiniband-for-distributed-ai-training
- _(high)_ Two distinct things must not be conflated: (1) RENTING a normal Docker/SSH GPU box from a marketplace (Akash, io.net, Vast, RunPod, Prime Intellect exchange) to train your OWN model; (2) JOINING a decentralized training protocol (Nous Psyche, Prime Intellect INTELLECT runs) where you contribute your GPU to one collectively-owned model. Only path (1) gives an individual a private box for their own work.  
  Sources: https://www.primeintellect.ai/blog/intellect-2 · https://www.chakra.dev/research/the-third-epoch-of-ai-decentralizing-the-training-stack
- _(high)_ INTELLECT-2 (Prime Intellect, May 2025) is the first 32B-parameter model trained via globally distributed, permissionless reinforcement learning across 100+ heterogeneous nodes on three continents, using PRIME-RL, TOPLOC (verification via locality-sensitive hashing) and SHARDCAST. Nous Psyche's planned 40B pretrain was billed as the largest pretraining run over the internet to date.  
  Sources: https://www.primeintellect.ai/blog/intellect-2 · https://arxiv.org/html/2505.07291v1 · https://www.marktechpost.com/2025/05/12/primeintellect-releases-intellect-2-a-32b-reasoning-model-trained-via-distributed-asynchronous-reinforcement-learning/
- _(high)_ On permissionless/community marketplaces the HOST physically owns the box and (with root/hypervisor access) can in principle read your data, training set and weights from RAM/VRAM/disk. The only robust defense is GPU TEE / confidential computing (NVIDIA H100/H200 CC-mode), which encrypts weights+inputs+outputs even from a rogue admin. Measured overhead is under ~5% for typical LLM workloads and near-zero for large models / long sequences. But pay-as-you-go TEE GPUs on decentralized markets remain mostly roadmap in 2026.  
  Sources: https://arxiv.org/pdf/2409.03992 · https://www.spheron.network/blog/confidential-gpu-computing-nvidia-tee-encrypted-vram/ · https://phala.com/posts/confidential-computing-on-nvidia-h100-gpu-a-performance-benchmark-study
- _(high)_ Data centres used ~415 TWh in 2024 (~1.5% of global electricity, IEA) and the IEA Base Case projects ~945 TWh (~3%) by 2030, with AI as the main driver: accelerated/AI servers grow ~30%/yr vs ~9%/yr for conventional servers, and data-centre demand grows ~15%/yr overall.  
  Sources: https://www.iea.org/reports/energy-and-ai/energy-demand-from-ai · https://www.datacenterdynamics.com/en/news/iea-data-center-energy-consumption-set-to-double-by-2030-to-945twh/ · https://www.spglobal.com/energy/en/news-research/latest-news/electric-power/041025-global-data-center-power-demand-to-double-by-2030-on-ai-surge-iea
- _(high)_ The carbon of a training run is dominated by WHERE and WHEN it runs. Strubell et al.-style region analysis: a model trained in Estonia can emit >61x the CO2eq of the same model trained in Sweden (2016 grid intensities). Time/location-shifting non-urgent training to low-carbon hours/regions, via Electricity Maps or WattTime APIs, cuts emissions with zero model changes.  
  Sources: https://arxiv.org/pdf/2007.03051 · https://arxiv.org/pdf/2303.02508 · https://watttime.org/news-and-insights/solution_matches/automated-emissions-reduction-aer/
- _(medium)_ Genuine pretraining from scratch is where renting breaks for an individual: GPT-3-class was ~1,287 MWh / ~552 t CO2; GPT-4-class is estimated at tens of GWh. This is multi-million-dollar, multi-node, InfiniBand-mandatory territory out of reach for a solo artist; it is precisely what the collective protocols exist for.  
  Sources: https://arxiv.org/abs/2104.10350 · https://www.iea.org/reports/energy-and-ai/energy-demand-from-ai
- _(medium)_ Decentralized marketplaces (Akash ~\$1.33/H100-hr, io.net renting clusters '50-70% below AWS') are genuinely cheaper than hyperscalers, but all 'up to X% cheaper' figures are vendor marketing and reliability/trust is host-specific. Akash 'does not inspect tenant data' but also does not protect it from the host.  
  Sources: https://coinstancy.com/academy/guides/akash-network/ · https://www.dextools.io/tutorials/what-is-io-net-decentralized-gpu-ai-depin-solana-guide-2026 · https://www.cloudzero.com/blog/h100-gpu-cost/

### Refuted / do-not-repeat

- io.net '8xH100 ~\$3.35/hr vs AWS \$98.32/hr' - DROPPED. \$3.35 for eight H100s implies ~\$0.42/GPU-hr, below every verified marketplace floor including Akash's; it conflates a marketing low with a list-price hyperscaler high. The directional claim 'io.net rents 50-70% below AWS' is retained as vendor-reported.
- Spheron H100 spot \$1.03/hr and the derived '6.7x cheaper than AWS' - DEMOTED to vendor/unverified. Self-referential; independent floors sit nearer \$1.25/hr.
- Akash H100 \$0.41 (SXM5) and 'up to 85% cheaper than centralized' - DEMOTED to vendor marketing. Independent check lands Akash nearer ~\$1.33/H100-hr.
- Hyperscaler ceiling stated as up to \$12.29/GPU-hr (\$98/node) presented as the live cost - QUALIFIED as list price. AWS p5 fell ~44% in 2025 to ~\$3.90/GPU-hr blended, so the real marketplace gap is ~2-3x, not 6-10x.
- 'AWS Savings \$1.90-\$2.10' - FLAGGED as a derived estimate, not a published list price (depends on a 3-year commitment).
- GPT-4-class training ~50 GWh - RETAINED at MEDIUM confidence only; it is a widely repeated estimate, not a vendor-disclosed figure.

## Ecology of compute: energy mix and footprint

**Headline.** Where the GPUs sit on the grid decides the footprint, not the vendor's per-query press release; in 2025-2026 the "clean neocloud" narrative collapsed (Crusoe pivoted to a 933 MW gas plant) while genuinely low-carbon options stayed concentrated in French nuclear and Nordic hydro clouds.

### Verified findings

- _(high)_ Grid carbon intensity, not the provider's marketing, is the dominant lever: a model trained in Estonia could emit ~61x the CO2 of the same model trained in Sweden (17.7 vs 1,087.9 gCO2eq for a U-Net), per the Carbontracker paper (Anthony, Kanding, Selvan, 2020, based on 2016 grid intensities). France/EDF reported 26.5 gCO2/kWh in 2025 (79.6% nuclear, 95% decarbonized) and Norway averaged 2.2 gCO2/kWh in 2024, vs fossil grids above 700 gCO2/kWh.  
  Sources: https://arxiv.org/pdf/2007.03051 · https://www.edf.fr/en/2025-annual-results · https://www.globenewswire.com/news-release/2026/02/20/3241693/0/en/EDF-2025-annual-results-Strong-operational-performance-Positive-cash-flow-reducing-net-financial-debt.html
- _(high)_ The 'clean neocloud' narrative collapsed in 2025-2026. Crusoe, founded on flared-gas 'clean compute,' sold its Bitcoin mining unit (55% of 2024 revenue) to NYDIG in March 2025 and pivoted to AI; it then filed a TCEQ permit (Jan 2026) for a 933 MW simple-cycle GAS plant at its Goodnight/Texas campus (built for a Google partnership) that could emit up to ~4.5 million tons CO2/year. Google separately confirmed it is sourcing natural gas without carbon capture for Texas data centers.  
  Sources: https://www.cnbc.com/2025/03/25/crusoe-energy-sells-bitcoin-mining-unit-to-nydig-to-focus-on-ai.html · https://www.latitudemedia.com/news/how-a-crusoe-google-campus-became-texas-co-location-test-case/ · https://cleanview.co/reports/google-power-strategy · https://e360.yale.edu/digest/google-natural-gas-data-center
- _(high)_ PUE has been flat for six years: Uptime Institute's 2025 survey reports a global weighted-average PUE of 1.54, virtually unchanged since 2019, with regional spread (China 1.4, North America 1.49, Europe 1.50, Latin America 1.65). Efficiency gains have stalled despite AI buildout.  
  Sources: https://intelligence.uptimeinstitute.com/resource/uptime-institute-global-data-center-survey-2025 · https://mgrid.org/2025/10/01/uptime-institute-data-center-pue-stagnation-2025-liquid-cooling/
- _(high)_ IEA (Energy and AI, 2025) is the cleanest independent aggregate anchor: data centres used ~415 TWh in 2024 (~1.5% of global electricity), set to more than double to ~945 TWh by 2030 (~Japan's total use). Associated electricity emissions grow from ~180 Mt CO2 today to ~300 Mt (Base Case) and up to ~500 Mt (Lift-Off Case) by 2035. The US was 45% of 2024 data-centre electricity use.  
  Sources: https://www.iea.org/reports/energy-and-ai/executive-summary · https://www.spglobal.com/energy/en/news-research/latest-news/electric-power/041025-global-data-center-power-demand-to-double-by-2030-on-ai-surge-iea · https://www.carbonbrief.org/ai-five-charts-that-put-data-centre-energy-use-and-emissions-into-context/
- _(high)_ Per-query figures are real but boundary-narrow and span an order of magnitude depending on model and accounting boundary. Google (Aug 2025) puts a median Gemini text prompt at 0.24 Wh / 0.03 gCO2e / 0.26 mL water under its 'comprehensive' boundary, claiming 33x energy / 44x carbon improvement in 12 months. Independent benchmarking ('How Hungry is AI?', arXiv 2505.09598) shows GPT-4.1 nano at ~0.454 Wh vs DeepSeek-R1 at ~33.6 Wh on long prompts, with R1 emitting >14 gCO2 and consuming >150 mL water per query. Both 'five drops' and '>150 mL' are true depending on model/boundary.  
  Sources: https://cloud.google.com/blog/products/infrastructure/measuring-the-environmental-impact-of-ai-inference/ · https://arxiv.org/abs/2508.15734 · https://arxiv.org/html/2505.09598v2
- _(high)_ Embodied (manufacturing) carbon is the under-counted axis. NVIDIA's own Product Carbon Footprint puts an 8-GPU H100 baseboard at ~1,312 kg CO2e (~164 kg/card), with memory/HBM the single largest contributor (~42%). This is the first vendor GPU LCA disclosure.  
  Sources: https://interactdc.com/posts/understanding-gpus-energy-and-environmental-impact-part-i/ · https://introl.com/blog/carbon-accounting-ai-workloads-gpu-emissions-tracking-2025
- _(high)_ The first credible vendor lifecycle disclosure for a model is Mistral Large 2 (Jan 2025, with Carbone 4, ADEME, Resilio, Hubblo): 20,400 t CO2e and 281,000 m3 water over training + 18 months of use, with a marginal per-400-token inference of 1.14 gCO2e and 45 mL water.  
  Sources: https://www.carbone4.com/en/ia-generative-mission-mistral-ai · https://simonwillison.net/2025/Jul/22/mistral-environmental-standard/
- _(high)_ The actionable lever for a solo renter is provider+region selection. H100s rent for ~\$1.49-2.99/GPU-hr on neoclouds/marketplaces (Vast.ai ~\$1.87, RunPod ~\$1.99, Lambda ~\$2.49) vs ~\$3.90/GPU-hr (AWS P5) to ~\$12.29/hr (Azure) on hyperscalers; spot dips to ~\$0.34/hr with interruption risk. Picking a French (Scaleway) or Nordic clean-grid host cuts real emissions far more than any offset.  
  Sources: https://intuitionlabs.ai/articles/h100-rental-prices-cloud-comparison · https://www.spheron.network/blog/gpu-cloud-pricing-comparison-2026/ · https://www.cloudzero.com/blog/h100-gpu-cost/
- _(high)_ Microsoft reports an on-site WUE of 0.30 L/kWh (39% better than its 2021 figure of 0.49) and is moving to closed-loop zero-water-evaporation designs. Most 'renewable' grid claims still rest on annual unbundled RECs that critics call accounting gimmicks; even Google's 24/7 hourly carbon-free-energy matching reached only the mid-60s percent globally, not 100%.  
  Sources: https://datacenters.microsoft.com/sustainability/efficiency/ · https://www.canarymedia.com/articles/energy-markets/a-deeper-dive-into-24-7-carbon-free-energy · https://www.hourlymatching.org/blog/google-advances-toward-24-7-carbon-free-energy-globally-at-66-but-japan
- _(high)_ Grid strain is the most concrete near-term societal cost. PJM's latest capacity auction hit the \$329.17/MW-day price cap (+22% YoY), a ~\$16.1B total (up from \$14.7B), translating to ~1.5-5% retail bill increases, with most new demand attributed to data centers (~30 GW summer growth by 2030).  
  Sources: https://www.utilitydive.com/news/pjm-interconnection-capacity-auction-data-center/808264/ · https://insideclimatenews.org/news/20072025/pjm-capacity-auction-electricity-price-hike/ · https://www.citizensutilityboard.org/blog/2025/07/22/pjm-capacity-auction-leads-to-price-spike-for-second-straight-year-threatens-even-higher-com-ed-bills-in-2026-27/
- _(medium)_ A 2024-25 study of US data centers (Guidi et al., arXiv 2411.09786) found an electricity-weighted average carbon intensity of ~548 gCO2e/kWh, about 48% above the contemporaneous US national average of ~370 gCO2e/kWh, confirming that the data-center fleet runs dirtier than the grid it sits on. (Note: the study covered ~2,132 facilities, not the 1,795 figure circulating in secondary sources.)  
  Sources: https://www.cell.com/patterns/fulltext/S2666-3899(25)00278-8 · https://www.eesi.org/articles/view/data-center-energy-needs-are-upending-power-grids-and-threatening-the-climate · https://arxiv.org/abs/2606.05420

### Refuted / do-not-repeat

- KILLED as written: 'A 2025 study of 1,795 data centers found 548 gCO2e/kWh, ~50% higher than 369 gCO2e/kWh national.' The carbon-intensity numbers are real and well-sourced to Guidi et al. (arXiv 2411.09786), but the study covered ~2,132 facilities (not 1,795), the gap is ~48% (not ~50%), and the quote was misattributed to sustainableatlas.org. Retained in corrected form (548 vs ~370 gCO2e/kWh, ~48%, ~2,132 DCs) at medium confidence.
- KILLED: 'Virginia (PJM grid) data centers draw 61% from fossil fuels and only 7.7% from renewables, the rest nuclear.' Misattributed (not in sustainableatlas.org) and misframed: this is EESI's rephrasing of a data-center carbon study applied as if it were the PJM/Virginia grid electricity mix. Independent EIA data contradict the 7.7% renewables figure (Virginia renewables are higher). Dropped.
- DEMOTED/RECAST: 'Training in Sweden vs Estonia can be 61x less CO2 (Sweden ~17 vs California ~261 vs Midcontinent ~501 gCO2/kWh); Electricity Maps regions.' The 61x figure is correct but comes from the Carbontracker paper (Anthony et al., 2020) based on 2016 Sweden-vs-Estonia intensities (17.7 vs 1,087.9 gCO2eq), NOT a Sweden/California/Midcontinent Electricity Maps comparison. Recast with the correct source and numbers; the California/Midcontinent specifics are unverified and dropped.
- DEMOTED to low confidence / not independently confirmed: the specific off-site water multipliers 'Azure 3.14 L/kWh off-site' and 'DeepSeek 6.0.' Microsoft's on-site WUE of 0.30 L/kWh is confirmed; the off-site multipliers could not be corroborated in primary sources and are presented only as illustrative of the on-site-vs-off-site gap.
- DEMOTED: the specific PJM cost framing '\$9.3B rise / +\$18/household/month / \$31B in 2025 rate increases / >50% bill rises by 2030.' Could not be cleanly corroborated. Replaced with verified PJM figures: \$329.17/MW-day cap, +22% YoY, \$16.1B total (up from \$14.7B), 1.5-5% retail bill increases.

## Traceability and the decentralized-ecology question

**Headline.** A solo GPU renter can measure and choose a clean grid, but cannot independently verify a vendor's "100% renewable" badge - and renting in a physically-clean region beats building a home rig on both ecology and cost.

### Verified findings

- _(high)_ Electricity Maps discontinued its marginal-emissions data offering in 2024 (not 2025) because marginal signals are not directly measurable and cannot be validated against a ground truth; the company publicly explained this in a Jan 21 2025 article. It had worked with marginal emissions for 'almost a decade'.  
  Sources: https://www.electricitymaps.com/content/from-power-markets-to-reality-does-the-marginal-power-plant-really-exist · https://www.electricitymaps.com/content/challenges-of-validating-marginal-signals
- _(high)_ Different marginal-emissions providers give contradictory load-shifting recommendations for the same grid/time. For PJM on Jan 1 2024, PJM's own signal said shifting 3am->5pm avoids 460 kg CO2/MWh, while Singularity's data implied the opposite, adding 185 kg/MWh; a 1 MW wind farm at 3am 'avoided' 860 kg (PJM) vs 430 kg (Singularity's PJM-sourced data).  
  Sources: https://www.electricitymaps.com/content/challenges-of-validating-marginal-signals
- _(high)_ Electricity Maps now recommends the AVERAGE, location-based signal for real-time decisions when long-term impact, scrutiny, verification and auditability are valued; it notes regulations/standards require average emission factors and prohibit marginal factors.  
  Sources: https://www.electricitymaps.com/content/marginal-vs-average-real-time-decision-making · https://www.electricitymaps.com/content/challenges-of-validating-marginal-signals
- _(high)_ The Green Software Foundation Software Carbon Intensity (SCI) spec uses SCI = (E × I + M) per R, where I is LOCATION-BASED grid carbon intensity, and explicitly states 'an SCI score cannot be reduced through carbon offsets, such as market-based measures' - only real emission elimination lowers the score. SCI was ratified as ISO/IEC 21031:2024.  
  Sources: https://sci.greensoftware.foundation/
- _(high)_ WattTime kept and expanded marginal data (MOER, 5-minute granularity, ~99% of world electricity consumption, 210 countries/territories). TIME named its Automated Emissions Reduction (AER) a Best Invention of 2025; over one billion smart devices now use AER.  
  Sources: https://time.com/collections/best-inventions-2025/7318530/watttime-automatic-emissions-reduction-aer/ · https://watttime.org/news-and-insights/more-than-one-billion-smart-devices-now-using-marginal-emissions-data-to-slash-power-grid-pollution-with-watttimes-aer/
- _(high)_ IEA: data-centre electricity grew ~17% in 2025 to ~485 TWh, projected to roughly double to ~945-950 TWh by 2030 (~3% of global demand); AI-focused datacenter consumption surged ~50% in 2025. CO2 from datacenter electricity peaks ~320 Mt by 2030. Renewables currently supply ~27% of datacenter electricity (projected 50% by 2030).  
  Sources: https://www.iea.org/news/data-centre-electricity-use-surged-in-2025-even-with-tightening-bottlenecks-driving-a-scramble-for-solutions · https://www.iea.org/reports/energy-and-ai/executive-summary · https://www.datacenterdynamics.com/en/news/iea-data-center-energy-consumption-set-to-double-by-2030-to-945twh/
- _(high)_ CodeCarbon (open-source Python) samples GPU via nvidia-smi/NVML and CPU via RAPL, multiplies kWh by regional carbon intensity, and applies a PUE multiplier (industry-average ~1.58 default), falling back to a global ~475 gCO2eq/kWh when regional data is unavailable. It is NVIDIA/Intel-AMD-centric and has known accuracy limitations. (Note: it is the ML CO2 Impact calculator, not CodeCarbon, that omits PUE.)  
  Sources: https://arxiv.org/pdf/2306.08323 · https://mlco2.github.io/impact/
- _(high)_ US data centers run at ~548 gCO2e/kWh on average, ~48% above the US grid average of ~369 g, per Harvard-affiliated research, because they cluster in carbon-intensive grid regions.  
  Sources: https://arxiv.org/abs/2411.09786 · https://histsci.fas.harvard.edu/sites/g/files/omnuum9516/files/2026-02/Environmental_Footprint_of_U_S__Data_Centers.pdf
- _(high)_ Modern hyperscale facilities achieve PUE ~1.07-1.09 (Meta Luleå ~1.07, Google ~1.08-1.09) vs an industry-average PUE of ~1.56 (Uptime Institute 2024 survey) - i.e., a leading datacenter wastes ~7-9% on overhead vs ~56% for the typical facility. (Research summary's '1.58 global average' is slightly high; 1.56 is the Uptime figure.)  
  Sources: https://datacenters.google/efficiency/ · https://introl.com/blog/pue-109-google-data-center-efficiency-strategies
- _(high)_ AI servers idle at ~20% of rated power (validated to an average ~21.4% across published studies) per the LBNL 2024 US Data Center Energy Usage Report - so always-on but unused home GPUs are pure waste.  
  Sources: https://eta-publications.lbl.gov/sites/default/files/2024-12/lbnl-2024-united-states-data-center-energy-usage-report_1.pdf
- _(medium)_ Cradle-to-grave LCA of GenAI training on the NVIDIA A100 GPU finds the use phase dominates climate-change impact (~96%) while manufacturing dominates other categories: human toxicity/cancer (~99%) and mineral & metal depletion (~85%). Embodied carbon per A100 is on the order of ~141-150 kg CO2eq (secondary estimates ~150 kg).  
  Sources: https://www.sciencedirect.com/science/article/pii/S019592552600199X · https://www.researchgate.net/publication/395211656_More_than_Carbon_Cradle-to-Grave_environmental_impacts_of_GenAI_training_on_the_Nvidia_A100_GPU
- _(high)_ New AI load drove PJM's capacity auction costs from ~\$2.2B to ~\$14.7-16.4B; data centers were ~40% of the latest auction's costs. ~60% of PJM fossil plants slated for retirement postponed/cancelled, including 13 of ~23 retirements and 11 peaker plants. UCLA research: residents of historically redlined communities are ~53% more likely to live near peaker plants.  
  Sources: https://www.utilitydive.com/news/pjm-interconnection-capacity-auction-data-center/808264/ · https://www.utilitydive.com/news/data-centers-pjm-capacity-auction/808951/ · https://www.claimsjournal.com/news/national/2025/12/23/334736.htm
- _(medium)_ Europe curtailed ~€7.2 billion of renewable electricity across seven countries in 2024 (Beyond Fossil Fuels/E3G/Ember/IEEFA, May 2025); technical curtailment exceeded 10 TWh in 2024 and is projected to rise (EC: up to ~10x by 2040; ~22 TWh across GB/Spain/Italy by 2030). The '6x by 2030' framing is not directly sourced.  
  Sources: https://www.saurenergy.com/solar-energy-news/europe-curtails-over-10-twh-of-power-in-2024-1000-gw-renewables-stuck-in-grid-queues-10984193 · https://www.delfos.energy/blog-posts/curtailment-has-many-names
- _(medium)_ California curtailment is rising and is majority transmission-congestion-driven: CAISO curtailed ~3.4 million MWh of solar+wind in 2024 (+29% vs 2023, solar ~93%), with congestion now the dominant cause. (The precise '21,000 MWh/day tripled in 2025, >70% congestion' figures and the Next 10 \$700M-1.13B transmission / ~40% opex numbers were not independently confirmed.)  
  Sources: https://www.eia.gov/todayinenergy/detail.php?id=65364 · https://www.publicpower.org/periodical/article/wind-and-solar-curtailments-are-rising-california-because-congestion-eia
- _(high)_ Carbon-aware/curtailment-aligned training can cut emissions sharply. Wiesner et al. (arXiv:2602.22760, Feb 2026) trained a 561M transformer across three clusters in curtailment windows, cutting operational emissions to ~5-12% of a single-site baseline while preserving quality.  
  Sources: https://arxiv.org/abs/2602.22760
- _(high)_ The decisive constraint on geographically-distributed training is interconnect bandwidth. Streaming-DiLoCo (Google DeepMind, arXiv:2501.18512) reaches data-parallel-baseline quality while using >400x less bandwidth (two orders of magnitude), making low-bandwidth, multi-region training viable.  
  Sources: https://arxiv.org/abs/2501.18512
- _(high)_ Renting beats home-owning on cost: H100 marketplace pricing in 2026 spans ~\$1.49-\$6.98/hr (bulk \$2-4/hr), 50-75% cheaper than hyperscalers, where AWS/GCP on-demand can exceed \$8/hr.  
  Sources: https://intuitionlabs.ai/articles/h100-rental-prices-cloud-comparison · https://www.cloudzero.com/blog/h100-gpu-cost/
- _(high)_ The provable clean-rent play: rent where the grid is physically clean by location. Norway is ~98% renewable (~6 gCO2/kWh in 2024); LUMI runs on Vattenfall hydro; Stargate Norway (Nscale/Aker/OpenAI, 230 MW, 100k GPUs) and Genesis Cloud's Norway site are hydro-powered - so the location-based number is low regardless of any certificate.  
  Sources: https://lowcarbonpower.org/region/Norway · https://www.nscale.com/press-releases/stargate-norway-nscale-aker-openai · https://lumi-supercomputer.eu/lumi-data-center-will-be-powered-with-hydroelectricity-supplied-by-vattenfall/

### Refuted / do-not-repeat

- MISATTRIBUTED: 'a single consumer RTX 4090 rig can match or beat a multi-kW datacenter node on system-level energy-per-sample (Tomei et al. 2025, arXiv:2511.16182)' - arXiv:2511.16182 is Tomei, Mayer, Alcini & Salsano, 'Green Distributed AI Training: Orchestrating Compute Across Renewable-Powered Micro Datacenters' (Nov 2025), which contains NO RTX 4090 vs datacenter-node system-energy comparison and NO idle-overhead benchmark. The underlying consumer-vs-datacenter energy-parity claim is therefore unsourced as stated.
- DATE ERROR (substance correct): Electricity Maps discontinued marginal data in 2024, NOT 2025 - the company explicitly states 'we stopped offering data about marginal emissions to our customers in 2024'. The '2025' conflates the discontinuation with the Jan 21 2025 explanatory article.
- UNCONFIRMED: 'California spring curtailment tripled to 21,000 MWh/day in 2025, >70% from local transmission congestion' - the official CAISO 2024 figure is ~3.4 million MWh total (congestion-dominant), but the specific daily 21,000 MWh figure and tripling were not found in primary sources.
- UNCONFIRMED: 'siting compute at the stranded source avoids \$700M-1.13B in transmission and cuts datacenter operating cost ~40% (Next 10, 2026)' - the Next 10 report figures could not be independently verified.
- IMPRECISE: 'Europe curtailment projected 6x by 2030' - sources give ~10x by 2040 (European Commission) or ~22 TWh across GB/Spain/Italy by 2030, not a 6x-by-2030 multiplier; €7.2B (2024) is across seven countries, not all of Europe.
- IMPRECISE: 'global/legacy average PUE ~1.58' - the Uptime Institute 2024 figure is ~1.56; CodeCarbon uses 1.58 as a documented default, which is likely the source of the number.
- CLARIFICATION: 'the ML calculator AND CodeCarbon ignore PUE' - only the ML CO2 Impact calculator ignores PUE; CodeCarbon explicitly multiplies energy by a PUE factor (default ~1.58).

## Mutualizing compute: models, commons, reciprocity

**Headline.** Sharing compute without a hyperscaler is a solved problem in the commons - but the clean "earn idle, draw when busy, net-settle on one balance" product only exists inside token economies, where it reintroduces rent

### Verified findings

- _(high)_ AI Horde (Haidra) awards a worker exactly the kudos value of the job it completes, and also generates kudos every 10 minutes a worker stays online - so availability itself is rewarded, not just completed work.  
  Sources: https://github.com/Haidra-Org/AI-Horde/blob/main/FAQ.md · https://horde-sdk.readthedocs.io/en/latest/haidra-assets/docs/kudos/
- _(high)_ AI Horde kudos are 'inherently valueless', cannot be bought or sold for money or crypto (a ToS violation), can be freely gifted via the api/v2/transfer endpoint, never expire, and are explicitly 'merely a prioritization mechanism, not a currency' - they buy queue priority, never exclusive access. Registered users start with at least 25 kudos, anonymous users with 0.  
  Sources: https://github.com/Haidra-Org/AI-Horde/blob/main/FAQ.md · https://horde-sdk.readthedocs.io/en/latest/haidra-assets/docs/kudos/ · https://dbzer0.com/blog/the-kudos-based-economy-for-the-koboldai-horde/
- _(high)_ AI Horde deliberately tolerates free-riding: you can use the service with no kudos by simply going negative, which 'represents your debt to the community'; the shared Anonymous account 'simply keeps going more and more in negative Kudos', which only pushes requests to the back of the priority-sorted queue rather than blocking them.  
  Sources: https://dbzer0.com/blog/the-kudos-based-economy-for-the-koboldai-horde/
- _(high)_ Petals (collaborative LLM inference, BitTorrent-style) offers NO token and NO priority: the only acknowledgement for hosting 10+ blocks is having your name/link shown on the swarm monitor 'as a way to say thanks' (set via --public_name). Genuine mutual aid, but it gives no enforceable claim on compute when you need it.  
  Sources: https://github.com/bigscience-workshop/petals/blob/main/README.md
- _(high)_ Vast.ai structurally separates the host and renter roles for payout integrity: 'Hosting requires a separate account from your client account', and 'If you've ever rented instances or hosted machines on an account, you cannot cash out until your referral earnings exceed your lifetime instance spend.' There is no automatic earn-to-spend credit netting - a one-balance virtuous circle is not a product feature.  
  Sources: https://docs.vast.ai/referral-program · https://cdn.vast.ai/faq/
- _(high)_ Salad pays providers in a 'Salad Balance' redeemable for gift cards, PayPal cash and more, earned from 'real workloads' (AI inference, video rendering, transcription) that have 'nothing to do with blockchain or mining'; crypto mining is only the fallback workload. It is closer to a circle than Vast/RunPod but earn and spend remain largely separate ledgers.  
  Sources: https://community.salad.com/sell-gpu-power/ · https://support.salad.com/article/356-how-does-my-machine-earn-salad-balance
- _(high)_ Token-incentivized DePIN (io.net, Akash, Render, Aethir) is the only band explicitly designed so you both supply and consume the same token. Akash launched 'Homenode' early access (announced 25 Feb 2026) for consumer RTX 4090/5090 owners to contribute and earn.  
  Sources: https://www.prnewswire.com/news-releases/akash-launches-early-access-for-homenode-bringing-decentralized-compute-to-everyday-devices-302696087.html · https://homenode.akash.network/
- _(high)_ The rent-inside-the-commons risk is documented: of 650+ DePIN projects (combined market cap >\$16B) by late 2024, fewer than 20 generated meaningful non-token revenue. io.net's Q1 2025 Messari report showed 327,000 registered GPUs but only ~6,720 verified active daily (~2% utilization), because block rewards pay every operator passing uptime checks regardless of real jobs; when token prices fall, mercenary supply switches off.  
  Sources: https://blockeden.xyz/blog/2026/03/21/depin-march-2026-reality-check-650-projects-19b-market-cap-revenue/ · https://messari.io/report/state-of-io-net-q1-2025
- _(high)_ Akash's Burn-Mint Equilibrium went live 23 March 2026: every on-chain compute payment triggers a market buy-and-burn of AKT and mints a stable settlement credit (ACT) at USD pricing - a direct attempt to re-anchor the token to real compute usage and strip speculation. io.net's parallel fix is the Incentive Dynamic Engine.  
  Sources: https://akash.network/roadmap/aep-76/ · https://akash.network/blog/akash-network-q1-2026-report/
- _(medium)_ BOINC's durable anti-cheat lesson is replication-by-consensus: each work unit is sent to 2+ independent hosts and credit is granted only to results that reach a quorum; the architecture assumes every node is unreliable or malicious except the central server, with adaptive replication skipping re-runs for proven-reliable hosts. Folding@home adds a Quick Return Bonus and team competition.  
  Sources: https://boinc.berkeley.edu/trac/wiki/ValidationSimple · https://boinc.berkeley.edu/trac/wiki/AdaptiveReplication
- _(high)_ Academic federations prove pooled idle capacity is enormous and near-free: the OSG delivered more than 1.2 billion CPU-hours over 12 months (2024), of which over 100 million were purely opportunistic (idle cycles that would otherwise be wasted). The EGI Federation served ~116,000 users in 2024 and surpassed the 1,000,000-core milestone.  
  Sources: https://osg-htc.org/ · https://www.egi.eu/article/egi-federation-annual-report-2024-now-available/ · https://www.egi.eu/article/the-egi-federation-reaches-1000000-cores/
- _(high)_ A live public/philanthropic commons exists that a small collective can tap: NSF ACCESS 'Explore' needs only an abstract (grad students can be PI); the NAIRR Pilot aggregates Microsoft's \$20M Azure credits and NVIDIA's \$30M support; CZI offered a 1,024-H100 DGX SuperPOD (2025 cycle, applications 9 Jan–18 Jun 2025); New York's Empire AI 'Alpha' runs ~200 NVIDIA GPUs (Simons/Flatiron gift, nine universities); Massachusetts' \$31M AI Hub reserves at least 40% of compute for startups and nonprofits. Most are US-academic-gated.  
  Sources: https://allocations.access-ci.org/prepare-requests · https://www.fiercesensors.com/electronics/nairr-pilot-gets-30m-nvidia-20m-azure · https://chanzuckerberg.com/rfa/ai-computing-gpu/ · https://www.empireai.edu/2025/06/27/empire-ai-launches-beta-one-of-the-most-powerful-academic-ai-supercomputers-in-the-nation/ · https://www.mghpcc.org/governor-healey-advances-states-ai-leadership-with-major-investments-in-massachusetts-ai-hub/
- _(high)_ Every durable shared-compute system maps onto Elinor Ostrom's 8 design principles for common-pool resources (Governing the Commons, 1990); Mozilla published a practical 2024 framework translating these principles to digital/data commons that a small group can adapt. The recurring failure mode is governance (unmonitored free-riding, no graduated sanctions, Sybil identities), not technology.  
  Sources: https://wiki.p2pfoundation.net/Eight_Design_Principles_for_Common_Pool_Resource_Systems · https://www.mozillafoundation.org/en/blog/a-practical-framework-for-applying-ostroms-principles-to-data-commons-governance/

### Refuted / do-not-repeat

- EGI Federation 'aggregates ~1.24M CPU cores' - DEMOTED. EGI's own publicly verifiable milestone is 1,000,000 cores (https://www.egi.eu/article/the-egi-federation-reaches-1000000-cores/); the precise 1.24M figure was not corroborated in the 2024 annual reporting and is replaced with 'surpassed 1,000,000 cores'. The ~116,000 users figure IS corroborated.
- BOINC '24h average 41.58 petaFLOPS across ~791,443 machines' - DEMOTED to approximate/undated. The live BOINC computing-power and boincstats pages could not be retrieved (boincstats returned HTTP 403; boinc.berkeley.edu/computing.php did not display the aggregate). The order of magnitude (tens of petaFLOPS across hundreds of thousands of hosts) is consistent with historical figures but the exact live number is NOT verified, so it is stated as approximate rather than as a hard current statistic.
- Folding@home '100,000+ participants rivaling top supercomputers' - KEPT only as a general, undated characterization, not a precise current count; the specific live participant/petaFLOPS figure was not re-verified against a primary dashboard in this pass.
- CZI cluster framed loosely as a generic '2025 cycle' - TIGHTENED: the verified detail is a 1,024-H100 NVIDIA DGX SuperPOD with an application window of 9 Jan–18 Jun 2025 and a 96-GPU minimum request (https://chanzuckerberg.com/rfa/ai-computing-gpu/).
- Akash ACT described as a 'non-transferable stablecoin' - SOFTENED: primary sources describe ACT as a 'stable credit'/settlement credit minted on burn at USD pricing (https://akash.network/roadmap/aep-76/); 'stablecoin' is avoided as it implies a regulatory category not asserted by the source.

## Modalities of sharing/lending GPUs (partial: legal/governance; technical setup to deepen)

**Headline.** Sharing GPUs reciprocally is technically easy and legally simple only if it stays one-way and free; the moment it becomes an explicit exchange, French law likely reclassifies it as barter or rental with tax consequences - confirm with an expert-comptable before relying on any vehicle.

### Verified findings

- _(high)_ The prêt à usage / commodat (Code civil art. 1875 ff.) is the cleanest free-lending vehicle: art. 1876 states verbatim 'Ce prêt est essentiellement gratuit.' Any genuine economic counterpart to the lender disqualifies the commodat and can trigger automatic reclassification as a bail/location. Borrower bearing pure operating/use costs (electricity, maintenance) does NOT disqualify it (art. 1886); a counterpart flowing to the lender as remuneration does.  
  Sources: https://www.doctrine.fr/l/texts/codes/LEGITEXT000006070721/articles/LEGIARTI000006444687 · https://www.captain.legal/fr/demarches-quotidiennes/commodat-pret-a-usage/ · https://www.fiscaloo.fr/14633-commodat-ou-pret-a-usage/
- _(medium)_ Explicit reciprocity ('I lend you my GPU IF you lend me yours') reads as troc/échange, which French doctrine treats as taxable even with no cash changing hands: VAT is due when each invoice is recorded, each leg valued in the transaction base, recorded as 'autres liquidités'/'autres créances'. This is the central trap of a 'virtuous circle' of reciprocal lending.  
  Sources: https://www.experts-et-decideurs.fr/vie-entreprise/gestion-entreprise/troc-entre-entreprises-traitement-comptable-fiscal/ · https://www.creer-gerer-entreprendre.fr/6-la-gestion-de-lentreprise/6-6-la-gestion-commerciale/echange-marchandises/
- _(high)_ The franchise des impôts commerciaux threshold for associations loi 1901 was raised to €80,011 for 2025 (up from €78,596 in 2024; €76,679 in 2023), conditional on gestion désintéressée, predominance of non-lucrative activity, and the règle des 4P. NOTE: the €81,051 figure circulating in some secondary sources is WRONG; the official 2025 figure is €80,011.  
  Sources: https://www.legifiscal.fr/actualites-fiscales/4096-franchise-impot-associations-seuil-porte-80011.html · https://bofip.impots.gouv.fr/bofip/2659-PGP.html/identifiant=BOI-IS-CHAMP-10-50-20-20-20250416 · https://bpifrance-creation.fr/entrepreneur/actualites/associations-franchise-dimpots-mise-a-jour-2025
- _(high)_ An association loi 1901 cannot distribute benefits to members (Article 1, loi du 1er juillet 1901); profit-sharing risks requalification into a société créée de fait, which has no legal personality, with members becoming personally and indefinitely liable. The precise civil/commercial outcome is a case-by-case judicial assessment (affectio societatis, apports, gestion).  
  Sources: https://www.assistant-juridique.fr/but_non_lucratif_association.jsp · https://associations.gouv.fr/lexception-lassujettissement-aux-impots-commerciaux
- _(high)_ A GIE (Groupement d'Intérêt Économique) is purpose-built to 'mettre en commun certains moyens': minimum 2 members, no minimum capital, fiscally transparent (not imposable as such; each member taxed on its share). But members are 'responsables solidairement et indéfiniment sur leurs biens personnels des dettes du groupement', and the GIE's activity must be the prolongement (auxiliary extension) of members' activities, never a substitute.  
  Sources: https://bpifrance-creation.fr/encyclopedie/structures-juridiques/se-regrouper-solutions-juridiques/gie-groupement-dinteret
- _(high)_ A SCIC (Société Coopérative d'Intérêt Collectif) runs on 1 person = 1 vote and must lock at least 57.5% of result into réserves impartageables (15% réserve légale + 50% of the remainder); statutes or AG can raise this to 100%. The locked reserves are deductible from corporate tax. Heavier to run (multiple stakeholder categories, SARL/SAS/SA form).  
  Sources: https://www.l-expert-comptable.com/a/6074-societe-cooperative-d-interet-collectif-scic-definition-avantages.html · https://www.les-scic.coop/foire-aux-questions
- _(high)_ There were 1,421 SCICs in France by end of 2025 (+10.4% since 2022), employing 17,547 people with €1.7bn revenue - evidence the multi-stakeholder coop is a working, growing model, not a theoretical one.  
  Sources: https://www.entreprises.coop/les-societes-cooperatives-d-interet-collectif-scic · https://www.les-scic.coop/chiffres-cles
- _(high)_ GDPR liability layer: running someone else's job that touches personal data makes the machine-lender a sous-traitant under art. 28 - may only act on documented instruction, cannot reuse the data for its own purposes, needs a written DPA. Reuse on one's own initiative reclassifies the lender as a responsable de traitement. Lending raw compute that processes personal data is NOT liability-free. Fines: up to €10M / 2% turnover for art. 28 breaches.  
  Sources: https://www.donneespersonnelles.fr/article-28-rgpd · https://www.leto.legal/articles-rgpd/article-28
- _(high)_ GPUnion (HotNets '25, arXiv 2507.18928) demonstrates campus-scale autonomous idle-GPU sharing with provider-first autonomy (join/pause/leave at will), container-based task dispatch, and automatic checkpointing/migration - reporting +30% GPU utilization, +40% interactive sessions, 94% successful workload migration on provider departure. The closest published technical template for reciprocal artist-collective compute sharing.  
  Sources: https://arxiv.org/abs/2507.18928 · https://dl.acm.org/doi/abs/10.1145/3772356.3772403
- _(high)_ GENCI/MesoNET (EquipEx+ PIA3, started Oct 2021, 6-year project) federates 22 partners (GENCI + 21 regional mésocentres) into a mutualized HPC/AI/Quantum infrastructure with a single national resource-allocation portal and a pooled support team. Shows the trusted-network + central-allocation governance pattern at institutional scale.  
  Sources: https://www.mesonet.fr/2_le-projet.html · https://www.genci.fr/en/learn-about-genci/our-ecosystem
- _(medium)_ The practical no-code toolkit French associations and communes already use to formalize sharing without it becoming a tangle: a written convention de mise à disposition de matériel (defining duration, conservation, return, who pays for damage/loss) plus a charte informatique (acceptable use). These allocate liability without creating a taxable consideration if drafted as a pure prêt à usage.  
  Sources: https://www.fiscaloo.fr/14633-commodat-ou-pret-a-usage/ · https://www.captain.legal/fr/demarches-quotidiennes/commodat-pret-a-usage/

### Refuted / do-not-repeat

- The franchise des impôts commerciaux threshold for 2025 is €81,051 - KILLED. The verified official figure is €80,011 for 2025 (€78,596 in 2024). The €81,051 number in the source quote is incorrect.
- 'Reciprocal free lending is fiscally clean like one-way lending' - KILLED as stated. Only PURE one-way free lending is clean; explicit reciprocity is treated as troc/échange and is taxable per French doctrine (must still be confirmed with a fiscaliste for this specific case).
- 'Lending raw compute is liability-free' - KILLED. If the workload touches personal data, the lender becomes a GDPR art. 28 sous-traitant with documented-instruction limits, no-reuse rule, mandatory DPA, and fine exposure.
