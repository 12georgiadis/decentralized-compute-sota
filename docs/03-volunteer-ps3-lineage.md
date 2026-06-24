## Volunteer / Open-Source Distributed Computing (the PS3 lineage)

Volunteer distributed computing is the original "compute outside the hyperscaler datacenter" model: idle consumer CPUs/GPUs - and one famous game console - federated into a virtual supercomputer, paid in nothing but altruism and leaderboard credit. The lineage runs from **distributed.net** (1997, key-cracking) and **SETI@home** (1999) through **BOINC** (the generalized middleware SETI@home spawned), to the protein-science projects **Folding@home** (2000) and **Rosetta@home** (2004-05), and the number-theory project **GIMPS** (1996). A modern open-AI branch - **AI Horde**, **Hivemind/Petals** - extends the same idea to diffusion and LLMs.

The honest through-line: volunteer compute is **real and scientifically productive**, but it runs on altruism rather than money, **peaks on crisis** and for **short, fault-tolerant, embarrassingly-parallel jobs**, and **fails** for low-latency serving of frontier models over home internet.

### What is REAL (verified traction)

- **Crisis-scale science.** Folding@home became the world's first exaFLOP-class system during COVID-19: **470 native PF / 958 x86 PF on 20 Mar 2020**, then **768 native PF / ~1.5 x86 exaFLOPS by 25 Mar 2020**, as active devices grew from ~30,000 (Jan 2020) to roughly **1 million** in three months. It has produced **226 scientific papers** ([Wikipedia: Folding@home](https://en.wikipedia.org/wiki/Folding@home)).
- **The PS3 era.** The Folding@home PS3 client ran **23 Mar 2007 → 6 Nov 2012**; **15M+ PS3 users donated 100M+ compute hours**, and it drove the network past 1 PF (16 Sep 2007) and to a Guinness World Record ([Folding@home PS3 FAQ](https://foldingathome.org/faqs/high-performance/folding-sony-playstation-3-ps3/); [Sony Interactive press release](https://sonyinteractive.com/en/press-releases/playstation3-enables-foldinghome-to-be--recognized-by-guinness-world-records-as-worlds--most-powerful-distributed-computing-network/)). Ended "following discussions with Sony," no detailed public reason.
- **Nobel-grade output.** Rosetta@home fed the software behind **David Baker's 2024 Nobel Prize in Chemistry** (shared with Hassabis and Jumper) ([HHMI](https://www.hhmi.org/hhmi-david-baker-wins-2024-nobel-chemistry)).
- **A live, money-free AI network.** AI Horde (non-profit Haidra; NLnet/NGI0-funded) is live: a June 2026 API snapshot showed ~13 image + 30 text workers and **lifetime totals of 181,015,719 images** and **272,684,437 text requests / 59.9B tokens** ([img totals](https://aihorde.net/api/v2/stats/img/totals); [text totals](https://aihorde.net/api/v2/stats/text/totals)). Its **kudos are "inherently valueless,"** cannot be sold for money/crypto (offenders zeroed out), and it is explicitly **anti-blockchain** ([AI Horde FAQ](https://github.com/Haidra-Org/AI-Horde/blob/main/FAQ.md)).
- **Maintained training plumbing.** **Hivemind** (Kademlia DHT + DMoE + fault-tolerant all-reduce) still ships - release **1.1.12, 3 Jan 2026** ([releases](https://github.com/learning-at-home/hivemind/releases)).

### What is HYPE (unvalidated as durable public infrastructure)

- **"Decentralized frontier-LLM serving over home internet."** **Petals** (Borzunov & Ryabinin et al., 2023; Yandex Research / HSE / UW / Hugging Face / ENS Paris-Saclay) proved the concept but is **abandoned as a public swarm**: last release **v2.2.0 (6 Sep 2023)**, last commit **25 Aug 2024**, flagship models flagged as under-served ([repo](https://github.com/bigscience-workshop/petals); [health monitor](https://health.petals.dev/)). The failure is structural: serving one 100B-400B model needs **every layer-shard online at once** over high-latency, churning WAN links - the opposite of AI Horde's "many tiny jobs."
- **"The people's supercomputer."** GIMPS' 2024 record prime **2^136,279,841 − 1 (41,024,320 digits, 12 Oct 2024)** - the first Mersenne prime found on GPUs - was **not** found by federated home PCs but by one person (**Luke Durant**) renting thousands of datacenter GPUs across **17 countries**, reportedly spending **~\$2M for a \$3,000 award** ([mersenne.org](https://www.mersenne.org/primes/?press=M136279841); [Popular Science](https://www.popsci.com/science/largest-prime-number/)).
- **"Sustainable forever."** distributed.net still grinds RC5-72 ~3 decades on, and Folding@home has fallen from ~1.5 EF to **12.9 native PF (24.8 x86) by 31 Oct 2025** ([Wikipedia](https://en.wikipedia.org/wiki/Folding@home)) - pure-altruism networks decay without a crisis or an incentive layer.

### Comparison table

| Project (year) | Workload shape | Status 2026 | Peak / scale | Incentive | Verdict |
|---|---|---|---|---|---|
| Folding@home (2000) | Protein MD, parallel | Alive, shrunk | 768 native PF / ~1.5 x86 EF (Mar 2020); 12.9 native PF (Oct 2025) | Altruism + leaderboard | REAL; crisis-peaked |
| Folding@home PS3 (2007-12) | Cell-processor folding | Retired 6 Nov 2012 | 15M users, 100M+ hrs, Guinness record | Altruism | REAL; ended via Sony |
| Rosetta@home (2004) | Protein structure/design | Alive | ~200k volunteers (2008) | Altruism | REAL; fed 2024 Nobel work |
| SETI@home (1999) | Radio-signal search | Hibernating (31 Mar 2020) | Most lifetime participants ever | Altruism | REAL; 0 ET signals; spawned BOINC |
| GIMPS (1996) | Mersenne primality | Alive | Record prime 2024 (on rented GPUs) | \$3,000 award | REAL math; "volunteer" framing HYPE |
| distributed.net (1997) | RC5-72 key search | Still running | Unfinished after ~3 decades | Altruism | Sustainability cautionary tale |
| AI Horde (2022) | Image diffusion + single-turn text | Alive | 181M images, 60B tokens lifetime | Non-monetary kudos | REAL; the money-free model that works |
| Hivemind (lib) | Decentralized training | Maintained (1.1.12, Jan 2026) | Research experiments | n/a | REAL plumbing |
| Petals (2023) | Distributed LLM **inference** | Abandoned swarm (commit Aug 2024) | Flagships under-served | None | HYPE for persistent public serving |

### Feasibility verdict

Volunteer compute over home internet is viable for (a) embarrassingly-parallel inference of small/medium models (AI Horde) and (b) experimental fault-tolerant collaborative training of single models (Hivemind/sahajBERT/CALM). It is **not** viable as a persistent public service for low-latency frontier (100B-400B) model serving (Petals' failure mode): high WAN latency, node churn, and the all-shards-online requirement break it, against the sub-microsecond, 800Gbps-1.6Tbps interconnects frontier work assumes. AI Horde is the key counter-evidence to crypto-token compute pitches: a network sustained ~4 years on reputation-only kudos it explicitly forbids monetizing.

---

*Sources for this section are linked inline above. The consolidated source list is in [SOURCES.md](../SOURCES.md).*
