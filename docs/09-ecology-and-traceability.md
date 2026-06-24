## Ecology of compute: energy mix, source, and footprint

> **Bottom line.** In 2025-2026 the carbon footprint of "renting compute to train" is decided by **where the GPUs sit on the grid** and **who is telling the truth about it** - not by the per-query figure in a vendor press release. Two things matter for a solo artist-researcher renting H100s: the **grid carbon intensity** of the host region (the dominant lever, varying 20-300x) and the **honesty of the provider's clean-energy accounting** (most "100% renewable" claims rest on annual unbundled certificates). Everything else - PUE, per-query water, even embodied hardware carbon - is a secondary multiplier on top of *where* and *when* you compute.

### 1. The geography of carbon: one number dominates

The carbon of a training run is roughly `hardware power × time × grid carbon intensity`. The first two are fixed by the model; the third varies by **more than two orders of magnitude** across regions, which is why location is the decisive lever.

The canonical illustration comes from the **Carbontracker** paper (Anthony, Kanding & Selvan, 2020, [arXiv 2007.03051](https://arxiv.org/pdf/2007.03051)): the *same* U-Net model emits **17.7 gCO2eq trained in Sweden** versus **1,087.9 gCO2eq trained in Estonia - a ~61x difference** (on 2016 grid intensities). The structural picture has not changed.

| Grid / region | Carbon intensity (gCO2/kWh) | Source |
|---|---|---|
| Norway (2024 average, hydro) | **2.2** | [Sustainability Atlas](https://sustainableatlas.org/post/data-story-data-center-energy-consumption-water-carbon-trends-1624) |
| France / EDF (2025, 79.6% nuclear, 95% decarbonized) | **26.5** | [EDF 2025 results](https://www.globenewswire.com/news-release/2026/02/20/3241693/0/en/EDF-2025-annual-results-Strong-operational-performance-Positive-cash-flow-reducing-net-financial-debt.html) |
| Sweden (training-run figure, 2016) | ~17.7 (per U-Net run) | [Carbontracker](https://arxiv.org/pdf/2007.03051) |
| US national grid average (2024-25) | ~370 | [Guidi et al.](https://www.cell.com/patterns/fulltext/S2666-3899(25)00278-8) |
| **US data-center fleet** (electricity-weighted) | **~548** (~48% above national) | [Guidi et al.](https://www.cell.com/patterns/fulltext/S2666-3899(25)00278-8) |
| Poland / fossil grids | **>700** | [Sustainability Atlas](https://sustainableatlas.org/post/data-story-data-center-energy-consumption-water-carbon-trends-1624) |
| Estonia (training-run figure, 2016, oil shale) | ~1,087.9 (per U-Net run) | [Carbontracker](https://arxiv.org/pdf/2007.03051) |

A striking, well-corroborated finding: the **US data-center fleet runs dirtier than the grid it sits on** - ~548 gCO2e/kWh, about **48% above** the contemporaneous US national average of ~370, because facilities cluster on fossil-heavy interconnects like PJM (Guidi et al., *Patterns* / [Cell](https://www.cell.com/patterns/fulltext/S2666-3899(25)00278-8), also [arXiv 2411.09786](https://www.eesi.org/articles/view/data-center-energy-needs-are-upending-power-grids-and-threatening-the-climate)). *(The study covered ~2,132 facilities; a "1,795" count circulating in secondary write-ups is unsupported - see Killed claims.)*

### 2. PUE: a flat multiplier that hasn't improved in six years

Power Usage Effectiveness (total facility energy ÷ IT energy) is the second multiplier. The headline is **stagnation**: Uptime Institute's 2025 survey reports a global weighted-average **PUE of 1.54**, "virtually unchanged" for the sixth consecutive year ([Uptime Institute 2025](https://intelligence.uptimeinstitute.com/resource/uptime-institute-global-data-center-survey-2025); [mgrid summary](https://mgrid.org/2025/10/01/uptime-institute-data-center-pue-stagnation-2025-liquid-cooling/)). Best-in-class Nordic and hyperscale sites hit 1.1-1.2, but the *average* operator gets no greener over time.

| Region | Avg PUE (2025) |
|---|---|
| China | 1.40 |
| North America | 1.49 |
| Europe | 1.50 |
| Latin America | 1.65 |
| **Global weighted avg** | **1.54** |

Source: [Uptime Institute Global Data Center Survey 2025](https://intelligence.uptimeinstitute.com/resource/uptime-institute-global-data-center-survey-2025).

### 3. The aggregate keeps exploding (independent anchor: IEA)

Per-unit efficiency improves while totals climb, because volume and idle-capacity provisioning dominate. The cleanest independent anchor is the **IEA *Energy and AI* report (2025)**:

- Data centres used **~415 TWh in 2024** (~1.5% of global electricity), the US being ~45% of that.
- Demand is set to **more than double to ~945 TWh by 2030** - roughly Japan's total electricity use today.
- Associated electricity **emissions rise from ~180 Mt CO2 today to ~300 Mt (Base Case) and up to ~500 Mt (Lift-Off Case) by 2035**.

Sources: [IEA executive summary](https://www.iea.org/reports/energy-and-ai/executive-summary), [S&P Global](https://www.spglobal.com/energy/en/news-research/latest-news/electric-power/041025-global-data-center-power-demand-to-double-by-2030-on-ai-surge-iea), [Carbon Brief](https://www.carbonbrief.org/ai-five-charts-that-put-data-centre-energy-use-and-emissions-into-context/).

### 4. Per-query: both "5 drops" and ">150 mL" are true - flag the boundary

Vendor self-reports now converge **low**, but they are **inference-only** and exclude training and embodied hardware. Independent benchmarking shows the spread across models is enormous; **reasoning models are the outliers**.

| Model / source | Energy/query | Water/query | CO2/query | Boundary |
|---|---|---|---|---|
| Google Gemini median text prompt ([Google Cloud, Aug 2025](https://cloud.google.com/blog/products/infrastructure/measuring-the-environmental-impact-of-ai-inference/); [arXiv 2508.15734](https://arxiv.org/abs/2508.15734)) | 0.24 Wh | 0.26 mL (~5 drops) | 0.03 gCO2e | "comprehensive", inference only |
| GPT-4.1 nano, long prompt ([arXiv 2505.09598](https://arxiv.org/html/2505.09598v2)) | ~0.454 Wh | - | - | independent benchmark |
| DeepSeek-R1, long prompt ([arXiv 2505.09598](https://arxiv.org/html/2505.09598v2)) | **~33.6 Wh** | **>150 mL** | **>14 gCO2** | independent benchmark |
| Mistral Large 2, per 400-token inference ([Carbone 4](https://www.carbone4.com/en/ia-generative-mission-mistral-ai)) | - | 45 mL | 1.14 gCO2e | audited LCA, marginal |

A single long DeepSeek-R1 query uses **~70x** the energy of a GPT-4.1-nano query and roughly the electricity of running a 65-inch TV for 20-30 minutes ([arXiv 2505.09598](https://arxiv.org/html/2505.09598v2)). Google also claims a **33x energy / 44x carbon** improvement for Gemini in 12 months - real but self-reported ([Google Cloud](https://cloud.google.com/blog/products/infrastructure/measuring-the-environmental-impact-of-ai-inference/)). **Rule: always state whose boundary a figure uses** (inference vs training vs embodied; on-site vs off-site water; annual-average vs hourly grid carbon).

### 5. Embodied carbon: the under-counted axis

Operational energy is only part of the story. **NVIDIA's own Product Carbon Footprint** puts an **8-GPU H100 baseboard at ~1,312 kg CO2e (~164 kg/card)**, with **memory/HBM the single largest contributor (~42%)** ([InteractDC analysis](https://interactdc.com/posts/understanding-gpus-energy-and-environmental-impact-part-i/); [Introl](https://introl.com/blog/carbon-accounting-ai-workloads-gpu-emissions-tracking-2025)). This is the first vendor GPU LCA disclosure and establishes a baseline: embodied/manufacturing carbon is non-trivial and HBM-driven, and it is growing as memory stacks scale.

At the **model** level, the first credible audited disclosure is **Mistral Large 2** (Jan 2025, with Carbone 4, ADEME, Resilio, Hubblo): **20,400 t CO2e and 281,000 m3 water** across training + 18 months of use ([Carbone 4](https://www.carbone4.com/en/ia-generative-mission-mistral-ai); [Simon Willison's summary](https://simonwillison.net/2025/Jul/22/mistral-environmental-standard/)).

### 6. The "clean neocloud" narrative collapsed (HYPE)

The headline 2025-2026 story is the **collapse of flared-gas "clean compute"**:

- **Crusoe** built its brand on flared-gas-powered "clean compute." In **March 2025** it sold its Bitcoin mining unit (55% of 2024 revenue) to NYDIG to go pure-play AI ([CNBC](https://www.cnbc.com/2025/03/25/crusoe-energy-sells-bitcoin-mining-unit-to-nydig-to-focus-on-ai.html)). It then filed a **TCEQ permit (Jan 2026) for a 933 MW simple-cycle GAS plant** at its **Goodnight/Texas** campus (a Google partnership), projected to emit **up to ~4.5 million tons CO2/year** ([Latitude Media](https://www.latitudemedia.com/news/how-a-crusoe-google-campus-became-texas-co-location-test-case/); [Cleanview](https://cleanview.co/reports/google-power-strategy)).
- **Google** itself confirmed it is sourcing **natural gas without carbon capture** for Texas data centers ([Yale E360](https://e360.yale.edu/digest/google-natural-gas-data-center)).

Meanwhile the **genuinely low-carbon** options remain concentrated in **(a) French nuclear clouds** (Scaleway; Mistral/Eclairion; the EDF-backed gigafactory bid) and **(b) Nordic/Icelandic hydro+geothermal DCs** (atNorth, Verne, PUE ~1.2, clean grids).

**The greenwashing caveat.** Most "100% renewable" claims rest on **annual unbundled RECs**, which critics describe as an accounting gimmick decoupled from real-time grid emissions ([Canary Media](https://www.canarymedia.com/articles/energy-markets/a-deeper-dive-into-24-7-carbon-free-energy)). The honest benchmark is **24/7 hourly carbon-free-energy (CFE) matching** - and even Google, the leader, reached only the **mid-60s percent globally**, not 100% ([Hourly Matching](https://www.hourlymatching.org/blog/google-advances-toward-24-7-carbon-free-energy-globally-at-66-but-japan)).

### 7. Water: on-site vs off-site, and closed-loop

Water is the live debate. The honest framing distinguishes **on-site cooling water** from **off-site power-generation water**. Microsoft reports an **on-site WUE of 0.30 L/kWh** (39% better than its 2021 figure of 0.49) and is shifting to **closed-loop, zero-water-evaporation** designs ([Microsoft Datacenters](https://datacenters.microsoft.com/sustainability/efficiency/)). Industry on-site averages are closer to ~1.9 L/kWh, and **off-site (power generation) water multiplies the total** - so a per-query "water" figure can swing by an order of magnitude depending on whether off-site is counted and whether the site evaporates or recirculates.

### 8. Grid strain: the most concrete societal cost

AI demand is reviving fossil generation and driving up retail bills. In the **PJM** interconnection (Virginia/data-center heartland), the latest capacity auction hit the **\$329.17/MW-day price cap, +22% YoY**, a **\$16.1 billion total** (up from \$14.7B), translating to **~1.5-5% retail bill increases**, with most of the ~30 GW summer demand growth by 2030 attributed to data centers ([Utility Dive](https://www.utilitydive.com/news/pjm-interconnection-capacity-auction-data-center/808264/); [Inside Climate News](https://insideclimatenews.org/news/20072025/pjm-capacity-auction-electricity-price-hike/); [Citizens Utility Board](https://www.citizensutilityboard.org/blog/2025/07/22/pjm-capacity-auction-leads-to-price-spike-for-second-straight-year-threatens-even-higher-com-ed-bills-in-2026-27/)).

### 9. The actionable lever for a solo renter: provider + region

For a solo artist-researcher, the single biggest lever on your real footprint is **which provider and region you rent in** - picking a French (Scaleway) or Nordic clean-grid neocloud cuts real emissions far more than buying any offset. Use [Electricity Maps](https://app.electricitymaps.com) to read real-time grid carbon and choose **when and where** to run. Price-wise, neoclouds are 50-75% cheaper than hyperscalers for the same H100:

| Provider (H100, 2026) | ~\$/GPU-hr | Notes |
|---|---|---|
| Vast.ai (marketplace) | ~\$1.87 | host/region-dependent, often fossil-gridded, no InfiniBand |
| RunPod (community) | ~\$1.99 | host/region-dependent |
| Lambda (on-demand) | ~\$2.49 | |
| Spot (Vast.ai) | ~\$0.34 | interruption risk |
| **AWS P5** | ~\$3.90 | hyperscaler |
| **Azure** | ~\$12.29 | hyperscaler |

Sources: [IntuitionLabs](https://intuitionlabs.ai/articles/h100-rental-prices-cloud-comparison), [Spheron](https://www.spheron.network/blog/gpu-cloud-pricing-comparison-2026/), [CloudZero](https://www.cloudzero.com/blog/h100-gpu-cost/). The cheapest marketplaces are host/region-dependent, frequently fossil-gridded, and typically lack InfiniBand for multi-node training - so "cheapest" and "cleanest" are not the same axis. **The clean-grid choice is yours to make, and it dominates the offset.**

---

#### Killed / corrected claims (anti-greenwashing log)

- **KILLED as written:** "A 2025 study of *1,795* data centers found 548 gCO2e/kWh, *~50%* higher than 369." The carbon-intensity numbers are real (Guidi et al., [arXiv 2411.09786](https://www.eesi.org/articles/view/data-center-energy-needs-are-upending-power-grids-and-threatening-the-climate)), but the study covered **~2,132 facilities** (not 1,795), the gap is **~48%** (not ~50%), and the quote was misattributed to sustainableatlas.org. **Retained in corrected form.**
- **KILLED:** "Virginia (PJM) data centers draw 61% fossil / 7.7% renewable, rest nuclear." Misattributed and misframed - this is a data-center carbon study's figure repackaged as if it were the PJM/Virginia *grid mix*; independent EIA data show Virginia renewables exceed 7.7%. **Dropped.**
- **RECAST:** the "61x Sweden vs Estonia" figure is **correct** but originates in **Carbontracker** (Anthony et al., 2020; 17.7 vs 1,087.9 gCO2eq on 2016 intensities), **not** a Sweden/California/Midcontinent Electricity Maps comparison. The California (~261) / Midcontinent (~501) specifics are unverified and **dropped**.
- **DEMOTED to low confidence:** the off-site water multipliers "Azure 3.14 L/kWh" and "DeepSeek 6.0." Microsoft's on-site WUE of **0.30 L/kWh** is confirmed; the off-site multipliers could not be corroborated and are presented only illustratively.
- **DEMOTED:** the PJM cost specifics "\$9.3B / +\$18/household/month / \$31B in rate increases / >50% bill rises by 2030." Could not be cleanly corroborated; replaced with verified PJM figures (\$329.17/MW-day cap, +22%, \$16.1B total, 1.5-5% bill increases).

---

*Sources for this section are linked inline above. The consolidated source list is in [SOURCES.md](../SOURCES.md).*

---

## Traceability, carbon-aware computing, and the decentralized ecology question

**Bottom line for a solo GPU renter.** You *can* measure your own job and you *can* pick a physically-clean grid. You *cannot* independently verify a vendor's "100% renewable" badge when it rests on certificates (RECs) or power-purchase agreements (PPAs). That verification gap is precisely where greenwashing lives. The highest-leverage green move is not building a home rig - it is **carbon-aware scheduling**: rent in a location-clean region and time batch jobs to clean hours.

### 1. The field split: which number do you even trace?

Two camps emerged over 2024-2026, and they disagree on the fundamental metric.

| Camp | Signal | Lead actor | Stance | Verifiable? |
|---|---|---|---|---|
| **Location / average** | Average grid carbon intensity, location-based | Electricity Maps; Green Software Foundation | "Marginal emissions are not directly measurable [...] without ground truth" → discontinued marginal data in **2024** | Yes - auditable |
| **Marginal / causal** | Marginal Operating Emissions Rate (MOER), 5-min | WattTime | Kept + expanded marginal; TIME 2025 "Best Invention"; 1B+ devices | No ground truth exists |

Electricity Maps stopped selling marginal data in **2024** after "almost a decade," citing "the fundamental impossibility of validating the accuracy of our models" ([Electricity Maps](https://www.electricitymaps.com/content/from-power-markets-to-reality-does-the-marginal-power-plant-really-exist)). Its strongest evidence: on **Jan 1 2024 in PJM**, the operator's own signal said shifting load 3am→5pm avoids 460 kg CO2/MWh, while Singularity's data implied the *opposite*, adding 185 kg/MWh; a 1 MW wind farm at 3am "avoided" 860 kg (PJM) vs 430 kg (Singularity) - same hour, contradictory advice ([Electricity Maps](https://www.electricitymaps.com/content/challenges-of-validating-marginal-signals)). For real-time decisions it now recommends the average signal "in case long-term impact is prioritized and scrutiny, verification, and user-intuitiveness are valued" ([Electricity Maps](https://www.electricitymaps.com/content/marginal-vs-average-real-time-decision-making)).

WattTime took the opposite bet and won mainstream recognition: MOER at 5-minute granularity covers ~99% of world electricity / 210 territories, and TIME named its Automated Emissions Reduction a Best Invention of 2025, with 1B+ devices using it ([TIME](https://time.com/collections/best-inventions-2025/7318530/watttime-automatic-emissions-reduction-aer/); [WattTime](https://watttime.org/news-and-insights/more-than-one-billion-smart-devices-now-using-marginal-emissions-data-to-slash-power-grid-pollution-with-watttimes-aer/)). Both can be true: marginal is the better *causal* lever for automated load-shifting; average is the only *auditable* number for reporting.

### 2. The anti-greenwashing standard: SCI / ISO 21031:2024

The Green Software Foundation's Software Carbon Intensity spec - now **ISO/IEC 21031:2024** - hard-codes the location camp:

> SCI = (E × I + M) per R

where **I is location-based grid carbon intensity**, and crucially: *"Only actions that eliminate emissions reduce an SCI score. As such, an SCI score cannot be reduced through carbon offsets, such as market-based measures"* ([SCI spec](https://sci.greensoftware.foundation/)). In other words, the standard itself refuses to let a "carbon-neutral" certificate lower your number.

### 3. Practical measurement for a solo renter

| Tool | What it does | Caveats |
|---|---|---|
| **CodeCarbon** (Python) | Samples GPU via nvidia-smi/NVML + CPU via RAPL, × regional carbon intensity, × PUE; writes CSV | NVIDIA/Intel-AMD-centric; known accuracy limits; default PUE \~1.58, global fallback \~475 gCO2/kWh ([guide](https://arxiv.org/pdf/2306.08323)) |
| **ML CO2 Impact calculator** | hardware × hours × provider × region | **Ignores PUE** - you must multiply yourself ([ML CO2](https://mlco2.github.io/impact/)) |
| **Cloud dashboards** (AWS CCFT, Azure, GCP) | Vendor-reported footprint | Mostly **market-based**, aggregated, lagged - useful for billing, weak for proof |

Note: contrary to a common summary, CodeCarbon *does* apply PUE; it is the ML calculator that omits it.

### 4. Macro stakes (IEA)

- Datacenter electricity grew \~17% in 2025 to **\~485 TWh**, heading to **\~950 TWh by 2030** (\~3% of global demand); AI-specific datacenter load surged \~50% in 2025 ([IEA](https://www.iea.org/news/data-centre-electricity-use-surged-in-2025-even-with-tightening-bottlenecks-driving-a-scramble-for-solutions)).
- CO2 from datacenter electricity peaks **\~320 Mt by 2030** ([IEA](https://www.iea.org/reports/energy-and-ai/executive-summary)).
- Renewables supply only **\~27%** of datacenter electricity today (projected 50% by 2030).
- US datacenters run at **\~548 gCO2e/kWh, \~48% above** the US grid average of \~369 g - because they cluster in dirty grid regions ([arXiv 2411.09786](https://arxiv.org/abs/2411.09786)).

### 5. The ecology question: efficiency vs electrons

The decentralization debate has **no single answer** - it splits by layer.

**Efficiency favors hyperscale:**

| Metric | Hyperscale | Typical / average |
|---|---|---|
| PUE | \~1.07-1.09 (Meta Luleå, Google) | \~1.56 (Uptime 2024) |
| Overhead wasted | \~7-9% | \~56% |

Sources: [Google](https://datacenters.google/efficiency/), [Introl](https://introl.com/blog/pue-109-google-data-center-efficiency-strategies). And idle silicon is pure waste: **AI servers idle at \~20% of rated power** (validated \~21.4% across studies), so always-on but unused home GPUs burn power for nothing ([LBNL 2024](https://eta-publications.lbl.gov/sites/default/files/2024-12/lbnl-2024-united-states-data-center-energy-usage-report_1.pdf)). Embodied carbon (\~141-150 kg CO2eq per A100) is a use-phase-dominated story for *climate* (\~96%) but a *manufacturing*-dominated story for human toxicity (\~99%) and mineral depletion (\~85%) - so scattering short-lived consumer cards to homes can worsen e-waste and embodied burden ([ScienceDirect / "More than Carbon"](https://www.sciencedirect.com/science/article/pii/S019592552600199X)).

**Where-the-electrons-come-from favors smart decentralization:**

- **"Free electricity is never free" on the centralized side.** New AI load drove PJM capacity costs from \~\$2.2B to \~\$14.7-16.4B (datacenters \~40% of the latest auction), and \~60% of PJM fossil retirements were postponed - **13 of \~23**, including **11 peaker plants** ([Utility Dive](https://www.utilitydive.com/news/pjm-interconnection-capacity-auction-data-center/808264/); [AP via Claims Journal](https://www.claimsjournal.com/news/national/2025/12/23/334736.htm)). The pollution lands unevenly: redlined communities are \~53% more likely to live near peakers (UCLA).
- **Stranded clean energy is real.** Europe curtailed \~**€7.2B** of renewables across seven countries in 2024; technical curtailment topped 10 TWh and is projected to rise (EC: up to \~10x by **2040**; \~22 TWh in GB/Spain/Italy by 2030) ([Saur](https://www.saurenergy.com/solar-energy-news/europe-curtails-over-10-twh-of-power-in-2024-1000-gw-renewables-stuck-in-grid-queues-10984193)). CAISO curtailed \~3.4M MWh in 2024 (+29%, congestion-dominant) ([EIA](https://www.eia.gov/todayinenergy/detail.php?id=65364)).
- **Curtailment-window training works.** Wiesner et al. (Feb 2026) trained a 561M model across three clusters in curtailment windows, cutting operational emissions to **\~5-12% of single-site baseline** with no quality loss ([arXiv 2602.22760](https://arxiv.org/abs/2602.22760)).

**The binding constraint on distributed training is bandwidth.** Naive data-parallel frontier training over consumer uplinks is hopeless; Streaming-DiLoCo (Google DeepMind) reaches data-parallel-baseline quality using **>400x less bandwidth**, making multi-region, low-bandwidth training viable at all ([arXiv 2501.18512](https://arxiv.org/abs/2501.18512)) - though decentralized throughput still trails the frontier by \~2 orders of magnitude.

### 6. The provable clean-rent play

Renting wins on **both** ecology and cost for any real training job.

| Option | Cost (H100) | Verifiability |
|---|---|---|
| Marketplace / specialized cloud | \~\$1.49-4/hr ([IntuitionLabs](https://intuitionlabs.ai/articles/h100-rental-prices-cloud-comparison)) | High if location-clean region |
| Hyperscaler on-demand | \$8+/hr ([CloudZero](https://www.cloudzero.com/blog/h100-gpu-cost/)) | Mostly market-based claims |
| Home rig | High capex + idle waste | Self-measurable but embodied-heavy |

The move that survives audit is to **rent in a physically-clean grid** so the *location-based* number is low regardless of any certificate: Norway is \~98% renewable (\~6 gCO2/kWh in 2024); LUMI runs on Vattenfall hydro; Stargate Norway (Nscale/Aker/OpenAI, 230 MW, 100k GPUs) and Genesis Cloud's Norway site are hydro-powered ([lowcarbonpower](https://lowcarbonpower.org/region/Norway); [Nscale](https://www.nscale.com/press-releases/stargate-norway-nscale-aker-openai); [LUMI](https://lumi-supercomputer.eu/lumi-data-center-will-be-powered-with-hydroelectricity-supplied-by-vattenfall/)).

> **Renter's recipe:** trace your own job (CodeCarbon × Electricity Maps *average* signal), pick a physically-clean region, schedule batch jobs for clean hours (carbon-aware scheduling cuts ~15% temporal to ~50%+ spatial), and treat any "100% renewable" badge backed by RECs/PPAs as marketing, not proof.

### Corrections / unverified claims

- **Misattribution:** the "RTX 4090 matches a datacenter node on system-level energy-per-sample" claim was cited as *Tomei et al. 2025, arXiv:2511.16182* - but that paper is "Green Distributed AI Training: Orchestrating Compute Across Renewable-Powered Micro Datacenters" and contains **no such benchmark**. Claim is unsourced as stated.
- **Date:** Electricity Maps discontinued marginal data in **2024**, not 2025 (the 2025 date is the explanatory article).
- **Unverified figures:** "California 21,000 MWh/day tripled, >70% congestion"; "Next 10: \$700M-1.13B transmission saved / ~40% opex cut"; "Europe curtailment 6x by 2030" (sources say ~10x by 2040 or ~22 TWh by 2030). Treat as unconfirmed.
- **Minor:** "global average PUE 1.58" → Uptime 2024 figure is ~1.56 (1.58 is a CodeCarbon default).

---

*Sources for this section are linked inline above. The consolidated source list is in [SOURCES.md](../SOURCES.md).*
