## Crypto / DePIN incentive networks

**Scope.** Token-incentivized networks that coordinate GPU/compute supply off the hyperscaler datacenter - independent datacenters, repurposed crypto-mining rigs, and consumer-GPU hobbyists - and sell that capacity for AI inference, 3D/VFX rendering, and ML training.

### The defining 2025-2026 tension: market caps vs. verifiable cash

By 2025-2026 the sector split into a small revenue-generating core and a long tail of token-subsidized "empty capacity." Messari's *State of DePIN 2025* pegs the whole sector at **~\$10B circulating market cap** against only **~\$72M of real FY25 on-chain revenue**, with leaders trading at ~10-25x revenue (down from >1,000x in 2021) ([Messari](https://messari.io/report/state-of-depin-2025); [Decrypt](https://decrypt.co/356349/depin-tokens-lag-revenues-rise-fundamentals)). An independent reality check counts **650+ projects, a peak ~\$19B market cap, ~\$110k average annual revenue per project, and fewer than 20 projects with meaningful non-token revenue** ([BlockEden, Mar 2026](https://blockeden.xyz/blog/2026/03/21/depin-march-2026-reality-check-650-projects-19b-market-cap-revenue/)).

The structural critique is consistent: most networks bootstrapped supply by paying hardware providers in inflationary token emissions, producing headline GPU counts that vastly exceed *paid* utilization. The canonical illustration is io.net's **April 2024 Sybil / GPU-metadata attack**, where ~**1.8M fake GPUs** attempted to connect and active connections collapsed from **~600,000 to ~100,000** after patching ([Cointelegraph](https://cointelegraph.com/news/io-net-responds-to-gpu-metadata-attack); [The Block](https://www.theblock.co/post/291315/solana-based-depin-io-net-ceo-claims-network-was-attacked-in-detailed-postmortem)). "GPU count" has been a discredited vanity metric ever since.

VCs are openly split. Meltem Demirors (Crucible Capital) wrote *"DePIN is dying and i don't see it coming back"*; Dan Elitzer (Nascent) called many projects *"almost entirely thinly veiled shitcoin ICOs"* - while operators argue the sector is maturing "from hype to substance" ([The Defiant](https://thedefiant.io/news/infrastructure/crypto-vcs-debate-depin)).

### Verifiability is the dividing line

| Network | Token / status | Payment model | Headline traction | On-chain auditable? | Reading |
|---|---|---|---|---|---|
| **Akash** | AKT (Cosmos) | BME-style burn + on-chain settlement | ~60% util, ~367 active GPUs of ~702, daily fees >\$13k ATH; spend >2x YoY ([Messari Q3'25](https://messari.io/report/state-of-akash-q3-2025)) | **Yes** (Cosmos explorers) | Most credible real demand; small absolute base |
| **Render** | RENDER (Solana) | Burn-Mint Equilibrium (USD-of-RENDER burned per job, ~5% fee) | >22M frames in 2025; 1M-th lifetime RENDER burned ([Render Dec'25](https://rendernetwork.medium.com/render-network-foundation-monthly-report-december-2025-43d956808e3f)) | Partial (burns yes; **USD job revenue not disclosed**) | Real VFX/3D demand; revenue opaque |
| **io.net** | IO (Solana) | Incentive Dynamic Engine: burns ≥50% of post-payout revenue in IO | >4B daily AI-inference tokens; ≥12M IO/yr burn target ([CoinDesk PR](https://www.coindesk.com/press-release/2026/06/11/io-net-to-burn-up-to-12m-tokens-as-network-closes-usd8m-deal-and-hits-4-billion-daily-ai-tokens)) | Mechanism corroborated; **~\$62M mcap of ~\$143M FDV, only 43.7% of supply circulating** ([CoinGecko](https://www.coingecko.com/en/coins/io-net)) | Recovering credibility; future dilution risk |
| **Bittensor** | TAO | Inflationary emissions (miners/validators/owners), dTAO subnet markets | First halving **14 Dec 2025: 7,200→3,600 TAO/day** ([Crypto.com](https://crypto.com/us/market-updates/bittensor-halving-all-you-need-to-know); [DL News](https://www.dlnews.com/articles/defi/bittensor-halving-seen-to-boost-tao-price-and-starve-zombie-subnets/)) | n/a | Multi-billion mcap, no comparable verifiable compute revenue |
| **Nosana** | NOS (Solana) | Pay-per-job, streamed by the second | 50,000+ GPU hosts since Jan 2025 mainnet; from ~\$0.048/GPU-hr ([Nosana](https://nosana.com/hosts/)) | Job settlement on Solana | Cost-savings (~68%/up to 85%) are **vendor claims** |
| **Spheron (Fizz)** | - | Direct lease; operator keeps **~90% of lease payment** | Consumer hardware; **≥50% uptime per 24h ERA** to earn ([Spheron docs](https://docs.spheron.network/fizz/reward-details)) | - | 90% = revenue share, **not** an uptime rule |
| **Inference.net (ex-Kuzco)** | KZO points (**pre-token**) | Incentivized testnet points | 6,000+ GPUs, ~98TB VRAM; >90% per-GPU util **(self-reported)** ([Solana Compass](https://solanacompass.com/projects/kuzco)) | No (no token) | Valuation event ≠ demand |
| **Gensyn** | \$AI | **No mainnet compute revenue** | RL Swarm testnet **paused**; Dec 2025 sale of 300M \$AI (3%), English auction, \$1M floor / \$1B FDV cap ([Chainwire](https://chainwire.org/2025/12/15/gensyn-launches-ai-token-sale-on-sonar/)) | No | Pre-revenue token sale |
| **Aethir** ⚠️ | ATH | Closed reporting | **Self-reported** \$127.8M 2025 rev / \$166M ARR / 440k GPU containers ([Aethir blog](https://aethir.com/blog-posts/aethirs-2025-wrap-up-decentralized-gpu-cloud-milestones)) | **No** (closed-source, not on DeFiLlama/Token Terminal) | See anomaly below |

### The Aethir anomaly (read carefully)

Aethir publishes the sector's largest revenue figures - \$127.8M+ for 2025, \$166M ARR by Q3 - but they are **entirely self-reported**, closed-source, and not on-chain auditable ([Aethir](https://aethir.com/blog-posts/aethirs-2025-wrap-up-decentralized-gpu-cloud-milestones)). The market appears to discount them heavily: ATH traded near **\$83M market cap (~\$0.0041)** in June 2026, *below its claimed annual revenue* and ~96.6% off its \$0.12 all-time high ([MetaMask price aggregator](https://metamask.io/price/aethir)). Separately, the much-cited **\$343.5M (closed; ~\$344M announced)** is a **Digital Asset Treasury** ATH-token purchase by Nasdaq-listed Predictive Oncology (POAI), closing **8 Oct 2025** - *treasury capital, not compute revenue* ([GlobeNewswire](https://www.globenewswire.com/news-release/2025/09/29/3157798/0/en/Predictive-Oncology-Inc-Announces-Private-Placements-of-344-Million-to-Initiate-a-Digital-Asset-Treasury-Strategy-Focused-on-Aethir-ATH-Tokens.html); [Cointelegraph](https://cointelegraph.com/news/predictive-oncology-depin-treasury-aethir-ath-token)). The recurring adversarial caveat across the sector: vendor "revenue" and "ARR" frequently conflate signed contracts, treasury/DAT token sales, and grants with actual paid compute usage.

### What we deliberately do NOT claim

- **io.net's "\$8M enterprise contract / ~\$650k month on-chain"** (June 2026): every outlet traces to a single io.net GlobeNewswire press release (the CoinDesk URL is a paid `/press-release/` placement); the customer is unnamed, no on-chain figure is cited, and the \$650k/month is a forward projection. *Reported, not verified - excluded as a factual demand signal.*
- Any **precise USD revenue total** for Akash or Render at the dollar level, and any **third-party Render revenue estimate (~\$2.7M)**, until reconciled against a primary explorer - Render does not disclose USD job revenue.
- Aethir's *"Rev/MC beat Filecoin/Render/Bittensor"* comparison - vendor self-promotion built on the same unverified revenue base.

---

*Sources for this section are linked inline above. The consolidated source list is in [SOURCES.md](../SOURCES.md).*
