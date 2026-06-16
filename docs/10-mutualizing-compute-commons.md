## Mutualizing compute: commons, co-ops, and reciprocity

> **Scope.** This section is about *sharing* compute non-commercially - lending an idle GPU and drawing on the pool when you need more - rather than buying it. The honest finding: a robust, single-balance *"earn idle, draw busy, net-settle"* **product** does not exist outside token economies, and inside them it tends to re-create rent. But the *commons* version is real, mature, and copyable by a small artist-researcher collective. The recurring failure mode is never the technology; it is governance - unmonitored free-riding, no graduated sanctions, and Sybil identities. (Framework after Elinor Ostrom, *Governing the Commons*, 1990, and Mozilla's 2024 digital-commons translation of Ostrom's eight design principles.)

### The reciprocity spectrum (four bands)

| Band | Examples | Money? | Same balance to earn *and* spend? | Reward for hosting | Honest verdict |
|---|---|---|---|---|---|
| 1. Pure give-to-get / mutual aid | AI Horde, BOINC, Folding@home, Petals | None | Points = priority only (Horde); none (Petals) | Queue priority (Horde) or a public "thanks" (Petals) | Cleanest commons; best-effort, no SLA |
| 2. Marketplace, shared identity, **no** net-settle | Vast.ai, RunPod | Yes | **No** - roles kept separate by design | Cash payout (separate account) | Most practical today; DIY reciprocity |
| 3. Non-crypto points/balance | Salad, ShareAI | Yes | Mostly separate ledgers | Cash/gift-card balance | Closer to a circle, marketing-heavy |
| 4. Token DePIN | io.net, Akash, Render, Aethir | Token | **Yes** - one token both sides | Token emissions | Only true one-balance circle; carries rent + price risk |

### Band 1 - non-monetary reciprocity (the template to copy)

The cleanest working model of "lend my GPU, get priority back" is **AI Horde** (Haidra / db0). Its rules, taken verbatim from the project's own `kudos.md`, are the design spec a small group can adopt almost unchanged:

- *"if the request is allowed and is successfully completed by a worker, that worker is awarded the same number of kudos"* - the requester's charge is exactly the worker's reward.
- *"workers receive a nominal amount of kudos merely for being online and available, in 10-minute increments"* - **availability itself is rewarded**, not just completed work.
- *"It is against the Terms of Service to sell or buy kudos"*; *"Kudos can be freely exchanged between users for any reason other than for currency"*; *"Kudos never expire."*
- *"The total number of kudos in your account determines your starting place in line when queuing a job"* - kudos buy **priority, not exclusion**. *"Anonymous users start with 0 kudos, while registered users have at least 25"* (a small anti-Sybil nudge). Free-riding is deliberately tolerated: a no-kudos request is simply served last, never blocked. (Source: [haidra-assets/docs/kudos.md](https://github.com/Haidra-Org/haidra-assets/blob/main/docs/kudos.md).)

**BOINC** and **Folding@home** add the missing anti-cheat layer. BOINC assumes every node is unreliable or malicious except the central server, so it **replicates each job across independent hosts and grants credit only to a validated quorum/consensus**; *adaptive replication* then stops re-running jobs sent to proven-reliable hosts, pulling the ~2× verification overhead back toward ~1× (target only 5–10% of CPU time). This is exactly the Sybil/free-rider defense expressed as code. (Sources: [BOINC CreditNew wiki](https://github.com/BOINC/boinc/wiki/CreditNew); [AdaptiveReplication](https://boinc.berkeley.edu/trac/wiki/AdaptiveReplication); Anderson, *BOINC: A Platform for Volunteer Computing*, 2019, [arXiv:1903.01699](https://arxiv.org/pdf/1903.01699).) Folding@home's **Quick Return Bonus** rewards fast, reliable turnaround - `final_points = base_points × max(1, sqrt(k × deadline_length / elapsed_time))`, gated by a passkey and an 80%+ successful-return record (Sources: [Folding@home bonus-points FAQ](https://foldingathome.org/faqs/points/bonus-points/); [QRB qualifications](https://foldingathome.org/faqs/points/bonus-points/what-are-the-qualifications-for-the-qrb/)).

**Petals** (collaborative LLM inference, BigScience, 2022) is the honest limit case: genuine mutual aid, but **no token and no enforceable priority** - the only documented thanks for hosting 10+ blocks is being named on the public swarm monitor (`--public_name`). A points-for-priority scheme appears in its README only as a *possible future* incentive, not live behavior. So mutual aid exists, but it gives you no claim on compute when *you* need it. (Source: [Petals README](https://github.com/bigscience-workshop/petals/blob/main/README.md).)

> **Scale note (volatile).** Volunteer pools are large but their headline FLOPS move. As of November 2025, BOINC runs ~**18.6 petaFLOPS** (24h average) across ~89,400 computers - not the ~41 PFLOPS / ~791,000-machine figure still quoted in some summaries, which appears stale. ([Grokipedia: BOINC](https://grokipedia.com/page/Berkeley_Open_Infrastructure_for_Network_Computing)). Treat any single FLOPS number as a snapshot.

### Band 2 - marketplaces: reciprocity is DIY, not a feature

Vast.ai and RunPod let one person be *both* host and renter - but **not cleanly on one balance**. Vast.ai's own documentation: *"If you've ever rented instances or hosted machines on an account, you cannot cash out until your referral earnings exceed your lifetime instance spend,"* and hosting uses a **separate account from the client account**. The platform actively *separates* the two roles for payout integrity; you can self-fund (earn on the host account, top up the client account from the same bank) but there is **no automatic credit netting**. ([Vast.ai referral docs](https://docs.vast.ai/guides/reference/referral-program).) This is the most practical option today, but the "virtuous circle" is something you assemble by hand.

### Band 4 - token DePIN: the only true one-balance circle, and where rent creeps back

Token networks are the only band explicitly designed so you **supply and consume the same token**. Akash opened **Homenode beta** (Feb 2026) for consumer RTX 4090/5090 owners to contribute and earn ([PRNewswire, 25 Feb 2026](https://www.prnewswire.com/news-releases/akash-launches-early-access-for-homenode-bringing-decentralized-compute-to-everyday-devices-302696087.html)), and shipped **Burn-Mint Equilibrium** on 23 March 2026, which market-buys and burns AKT on every compute payment to mint a stable settlement credit (ACT), re-anchoring the token to real usage ([Akash AEP-76](https://akash.network/roadmap/aep-76/)).

But the best-documented finding in this whole cluster is that **token reciprocity financializes the commons into rent**:

| Symptom | Figure | Source |
|---|---|---|
| DePIN projects with meaningful non-token revenue | **fewer than 20 of 650+** (late 2024, >\$16B combined market cap) | [BlockEden, Apr 2026](https://blockeden.xyz/blog/2026/04/12/depin-revenue-pivot-token-subsidies-ai-compute-akash-render-ionet/) |
| io.net registered vs. verified-active GPUs (Q1 2025) | **327,000 registered → ~6,720 active daily (~2%)** | [Nansen Research](https://research.nansen.ai/articles/ionet-does-it-have-what-it-takes) |

The mechanism is plain: *block rewards are paid to every operator passing uptime checks* regardless of real jobs, so emissions can subsidize empty infrastructure; when token prices fall, mercenary supply switches off and utilization collapses. Because emissions are inflationary by design - they dilute holders to fund growth - early "yield" is partly other people's dilution, i.e. **a rent extracted from the token, not earned from compute**. Akash's BME and io.net's incentive redesign are direct attempts to strip that rent out, which is itself an admission the original design leaked it.

### The public / philanthropic layer (and the EU caveat)

A real, growing commons exists at the funding layer - but in 2025–2026 it is mostly **US-academic-gated**: New York's **Empire AI "Alpha"** (donated by the Simons Foundation / Flatiron Institute, a nine-university consortium) runs ~200 NVIDIA H100-class GPUs ([Empire AI, June 2025](https://www.empireai.edu/2025/06/27/empire-ai-launches-beta-one-of-the-most-powerful-academic-ai-supercomputers-in-the-nation/)); the **Massachusetts AI Hub** (\$31M) reserves *"at least 40% of compute time… for startups, entrepreneurs and partner institutions including non-member colleges and nonprofits"* ([MassTech, May 2025](https://masstech.org/news/governor-healey-advances-states-ai-leadership-major-investments-massachusetts-ai-hub)); alongside NSF ACCESS and the NAIRR Pilot. **For a Paris-based collective the realistic equivalents are EGI / EOSC and French/EU research-infrastructure routes**, where pooled idle capacity is already vast - OSG delivered >1.2 billion CPU-hours in 2024 (>100M opportunistic) ([OSG](https://osg-htc.org/)) and the EGI Federation served ~116,000 users across ~1.24M cores in 2024 ([EGI 2024 report](https://www.egi.eu/article/egi-federation-annual-report-2024-now-available/); [EGI 1M-cores milestone](https://www.egi.eu/article/the-egi-federation-reaches-1000000-cores/)).

### Bottom line for a 3–6 person artist-researcher collective

The most reliable virtuous circle is **self-built**, not bought:

1. **Reciprocity layer (no money).** Pool real hardware and share it internally by a non-monetary fair-use ledger - copy AI Horde's kudos logic (reward both completed jobs *and* uptime; points buy priority, never exclusion; free-riding tolerated but deprioritized). Keeping money out of this layer also sidesteps the fiscal and legal questions that paid pooling would raise.
2. **Anti-cheat.** If trust ever frays, borrow BOINC's pattern: replicate to a quorum, grant credit only on consensus, relax replication for proven-reliable peers.
3. **Co-location, later.** If you ever buy hardware together, run a "condominium" cluster: owners get top priority on their own nodes (e.g. Slurm fairshare weighted by contribution) while idle cycles are preemptable by everyone - mutualizing slack without losing ownership.
4. **Overflow.** Use Vast.ai / RunPod / Salad as a supply-side outlet (rent your idle rig) and a demand-side overflow (burst when the pool is full) - but expect DIY reciprocity, not one-balance netting.
5. **Free public credits.** Apply in parallel to EGI/EOSC and French/EU research-infrastructure programs rather than the US-gated NAIRR/Empire AI/CalCompute tier.

> **Practical, not legal advice.** Any move from a non-monetary fair-use ledger to *paid* compute-sharing, token rewards, or cash payouts can carry tax, VAT, and contractual consequences (and, for token bands, securities/price exposure). Treat the points above as options to confirm with a qualified professional under French/EU law, never as settled law. Before pooling or buying anything, write a one-page Ostrom-style charter: clear membership boundaries, rules fit to your group, collective decision-making, monitoring by accountable members, **graduated** sanctions, and cheap conflict resolution. (Ostrom, 1990; Mozilla digital-commons framework, 2024.)

---

## Mutualizing compute: how a small collective actually lends GPUs to each other

For a small, *trusted* artist-researcher collective - say one MacBook, one Mac Mini, and two RTX 5090 Windows boxes - "sharing GPUs" is not one problem but three, stacked from easy to underestimated: **networking**, **orchestration**, and **isolation/governance**. A fourth, **French legal/fiscal qualification**, sits underneath all of it. Every fiscal point below is an *option to put to an expert-comptable or avocat fiscaliste*, never settled law.

### Layer 1 - Networking (the solved layer)

This is the part that genuinely works out of the box. [Tailscale](https://tailscale.com/kb/1084/sharing) is a WireGuard mesh VPN where you can share **a single node** with one named friend without exposing the rest of your network:

- *"A shared machine is visible only to the individual recipient user - it is not visible to the recipient user's entire tailnet."* ([tailscale.com/kb/1084/sharing](https://tailscale.com/kb/1084/sharing))
- Shared machines are **quarantined by default**: they can answer incoming connections from the tailnet they're shared to but cannot initiate their own, and recipient access still obeys the owner tailnet's ACLs ([same source](https://tailscale.com/kb/1084/sharing)).
- A reusable invite link works **up to 1,000 times** and unused links **expire after 30 days**; only an Owner/Admin/IT admin can share ([same source](https://tailscale.com/kb/1084/sharing)).

This is exactly the trust-scoping a collective wants: you lend access to *one GPU box*, not to your network. Tailscale even pitches the use case directly - *"Imagine splitting the cost of a good GPU with your friends and everyone getting private AI access from anywhere"* ([tailscale.com/blog/self-host-a-local-ai-stack](https://tailscale.com/blog/self-host-a-local-ai-stack)).

> **Hype check.** A tempting but wrong synthesis claims "Tailscale Peer Relays (GA 2025) keep distributed-compute traffic flowing across CGNAT, marketed alongside GPU cost-splitting." Two corrections: Peer Relays reached **general availability on 18 February 2026** (introduced October 2025), per [tailscale.com/blog/peer-relays-ga](https://tailscale.com/blog/peer-relays-ga); and the GPU-cost-splitting blog post above **never mentions** Peer Relays, CGNAT, firewalls, or distributed compute. Peer Relays do solve hard-NAT traversal - just keep the two facts separate.

### Layer 2 - Orchestration (pick by ambition)

| Tool | Best for | How sharing works | Key constraint |
|---|---|---|---|
| **[Exo](https://github.com/exo-explore/exo)** | A Mac-heavy fleet running LLM **inference** | Self-discovering **p2p** cluster (no master-worker), tensor-parallel sharding (~1.8x on 2 devices, ~3.2x on 4), MLX backend on Apple Silicon, exposes an OpenAI-compatible API at `http://localhost:52415` | Per the current repo, **Linux is CPU-only**, GPU support still under development - so the RTX 5090 Windows boxes are **not yet first-class GPU peers** ([github.com/exo-explore/exo](https://github.com/exo-explore/exo)) |
| **[dstack](https://dstack.ai/docs/concepts/fleets/)** | Real job orchestration on existing boxes | "SSH fleets": list hosts + SSH key in YAML; **GPU blocks** partition a host into concurrent slots (`blocks: 4` splits GPU/CPU/mem evenly; `blocks: auto` = one per GPU); `placement: cluster` wires hosts for distributed jobs | Hosts must be **Linux + Docker**, the SSH user needs **passwordless sudo**, the SSH server needs **`AllowTcpForwarding yes`**, NVIDIA hosts need CUDA 12.1 + NVIDIA Container Toolkit. A Windows RTX 5090 box must run **WSL2 or dual-boot Linux** ([dstack.ai](https://dstack.ai/docs/concepts/fleets/)) |
| **[SkyPilot](https://docs.skypilot.co/en/latest/overview.html)** | Portability across your boxes **and** rented cloud | `sky ssh up` turns IPs + SSH creds into an **SSH Node Pool**; `sky launch --infra ssh/my-node-pool` targets it; one CLI also spans Kubernetes, Slurm, and clouds | Useful only if you sometimes burst beyond your own hardware ([docs.skypilot.co](https://docs.skypilot.co/en/stable/reservations/existing-machines.html)) |
| **SLURM fairshare** | Classic HPC accounting | `PriorityDecayHalfLife` defaults to **7 days** (raw usage decayed ~every 5 min); `TRESBillingWeights` bills CPU/mem/each GPU model separately | Overkill for a tiny collective ([slurm.schedmd.com](https://slurm.schedmd.com/priority_multifactor.html), [hpc-docs.uni.lu](https://hpc-docs.uni.lu/slurm/fairsharing/)) |

For governance at collective scale, the heavy SLURM machinery is unnecessary: **wall-time limits + automatic checkpointing**, or **dstack GPU blocks as hard quotas**, give you "Shared Mode" (lend idle GPUs, reclaim when the owner needs them) without a scheduler.

### Layer 3 - Isolation (the part people underestimate)

**Letting someone run code on your GPU machine is letting them run code on your machine.** Two hard facts:

1. **Containers are not a security barrier.** [NVIDIAScape (CVE-2025-23266, CVSS 9.0, disclosed July 2025 by Wiz)](https://www.wiz.io/blog/nvidia-ai-vulnerability-cve-2025-23266-nvidiascape) showed a **three-line Dockerfile** - `FROM busybox` / `ENV LD_PRELOAD=/proc/self/cwd/poc.so` / `ADD poc.so /` - escaping the NVIDIA Container Toolkit's `createContainer` hook to **host root**, because the hook inherits the image's environment variables. All NCT **≤ v1.17.7** were affected (fixed in v1.17.8). Wiz's verbatim lesson: *"containers are not a strong security barrier and should not be relied upon as the sole means of isolation."*
2. **GPUs leak between tenants.** Outside specialized features like MIG, GPUs **generally lack tenant-level memory isolation**; leftover VRAM can be read by the next job unless zeroed, and shared hardware enables contention side-channels (plus newer GPU Rowhammer-class attacks) ([introl.com](https://introl.com/blog/multi-tenant-gpu-security-isolation-strategies-shared-infrastructure-2025), [tomshardware.com](https://www.tomshardware.com/pc-components/gpus/new-geforge-and-gddrhammer-attacks-can-fully-infiltrate-your-system-through-nvidias-gpu-memory-rowhammer-attacks-in-gpus-force-bit-flips-in-protected-vram-regions-to-gain-read-write-access)).

**The isolation ladder, weakest → strongest:**

| Rung | Mechanism | Note |
|---|---|---|
| (a) | Trust + plain SSH user accounts | Only for genuinely trusted peers - the realistic case for a small collective |
| (b) | Containers | **Convenience, not security** (see NVIDIAScape) |
| (c) | VM with GPU passthrough (IOMMU/VT-d/AMD-Vi + `vfio-pci`) | Near-native perf, full isolation, snapshot/restore on compromise |
| (d) | [Kata Containers](https://github.com/kata-containers/kata-containers/blob/main/docs/use-cases/GPU-passthrough-and-Kata.md) | Pods inside lightweight micro-VMs with a **separate kernel**; supports full GPU passthrough (one GPU/pod), built for untrusted/multi-tenant inference |
| (e) | MIG (true hardware memory-path isolation) | **Not on the consumer RTX 5090.** MIG is product-segmented, not Blackwell-gated: the RTX PRO 6000 (same GB202 die) supports 4 instances, datacenter Blackwell up to 7 ([docs.nvidia.com](https://docs.nvidia.com/datacenter/tesla/mig-user-guide/supported-gpus.html), [fluence.network](https://www.fluence.network/blog/nvidia-rtx-5090/)) |
| (f) | Confidential Computing (H100/Blackwell datacenter) | For the paranoid |

**Practical rule for a small collective:** lend only to trusted humans, prefer a dedicated/dual-boot Linux box you'd be willing to wipe, isolate with a passthrough VM you can snapshot, **zero VRAM between users, patch the NVIDIA Container Toolkit, and never expose the box to the open internet** (Tailscale-only + ACLs + quarantine).

### Layer 4 - French legal/fiscal qualification (confirm with a professional)

> **Disclaimer.** None of this is firm French tax law as applied to your situation. Every point must be confirmed by an **expert-comptable or avocat fiscaliste** before money - or even a reciprocal favour - changes hands.

The *act* of letting someone use your machine falls into different legal boxes, and the box drives the tax treatment:

- **Prêt à usage / commodat** (Code civil **art. 1875-1876**) is *"essentiellement gratuit"* by nature and is the **cleanest box for pure reciprocal lending** ([Légifrance](https://www.legifrance.gouv.fr/codes/section_lc/LEGITEXT000006070721/LEGISCTA000006136396/)). The catch: *any* consideration paid to the lender, or any **équivalent economic advantage**, can strip the commodat qualification and requalify the arrangement as an **onerous contract (location/bail)** ([fiscaloo.fr](https://www.fiscaloo.fr/14633-commodat-ou-pret-a-usage/)). A strict tit-for-tat "you lend me GPU, I lend you GPU" could itself read as an *avantage économique équivalent* - **this exact point must be checked.**
- **Prestation de service / BIC** - if money or a measurable counterpart flows, you're likely rendering a commercial service.
- **Échange (barter)** - reciprocal exchange is, for tax purposes, generally treated as two valued transactions, not a wash.

**The structures that keep it clean:**

| Vehicle | Fiscal posture |
|---|---|
| **Pure reciprocal commodat** (no money, no measurable counterpart) | Cleanest, *subject to the avantage-équivalent caveat above* |
| **Association loi 1901** with gestion désintéressée | Escapes IS/TVA/CET on **accessory** lucrative receipts only if non-lucrative activity stays predominant **and** lucrative receipts stay under the **2024 franchise des impôts commerciaux of €78,596** (up from €76,679 in 2023) ([legifiscal.fr](https://www.legifiscal.fr/actualites-fiscales/3733-franchise-impot-associations-seuil-porte-78596.html)) |
| **SCIC** | **Fiscalisée de plein droit** - commercial taxes apply by reason of corporate form, no sectoral carve-out ([Assemblée nationale, Q. n°10160](https://questions.assemblee-nationale.fr/q15/15-10160QE.htm)) |

**The battle-tested French precedent** for mutualizing infrastructure among small ethical structures is **CHATONS** (*Collectif des Hébergeurs Alternatifs, Transparents, Ouverts, Neutres et Solidaires*), launched by **Framasoft on 9 February 2016** ([framablog.org](https://framablog.org/2016/10/12/naissance-du-collectif-chatons/)). CHATONS is a **charter-bound collective whose members are each their own legal entity** (mostly assos loi 1901), and members demonstrably **load-shed compute between each other**: during the April 2020 lockdown, Framasoft offloaded its most-used services onto less-burdened member structures ([fr.wikipedia.org](https://fr.wikipedia.org/wiki/Collectif_des_h%C3%A9bergeurs_alternatifs,_transparents,_ouverts,_neutres_et_solidaires)). The actionable lesson: a **charte d'usage + convention de mise à disposition** between named members can carry most of the weight, without immediately reaching for a heavy legal vehicle.

---

*Sources accessed June 2026. Technical claims verified against vendor documentation and the Wiz disclosure; fiscal points stated as options requiring professional confirmation under French law.*

---

## How to organize a positive compute commons

### Can you really be in a virtuous circle?

YES, you can genuinely be in a give-and-take compute commons, but the clean "one balance, net-settle" version only exists if you accept a token economy and its rent dynamics. For a small artist/research collective the realistic answer is a points-and-priority commons among trusted peers, NOT a financialized pool. Here is the honest options ladder, cheapest-trust-cost first:

RUNG 0 (today, zero infra): Use AI Horde as the existence proof and a real outlet. Run a worker on your 5090s when idle, earn kudos for completed jobs AND for mere online availability (nominal kudos in 10-minute increments), then spend kudos to jump the queue when you need more than your own box gives. Kudos can't be bought/sold, never expire, can be gifted. This is a true earn-idle / draw-busy loop, but the "draw" is shared community inference capacity, not a private cluster for training a big custom model.

RUNG 1 (your gear, trusted peers, lending): Tailscale node-sharing to lend ONE quarantined GPU box to ONE named collaborator when you're not using it, ACL-scoped, revocable. Tailscale itself markets "split the cost of a good GPU with your friends." This is the cleanest reciprocity primitive: you lend your 4090 box this month, a peer lends theirs next month. No token, no netting product, just human tit-for-tat.

RUNG 2 (your gear, real orchestrated pool): Stand up a federated pool across the collective's machines. For Mac-heavy LLM inference, Exo (p2p, MLX, OpenAI-compatible API on :52415) - but note Linux/Windows is still CPU-only in Exo today, so your Windows RTX 5090 boxes are NOT yet first-class GPU peers there. For real GPU job orchestration including your 5090s, dstack SSH fleets with "GPU blocks" as hard quotas (requires each box run Linux/WSL2 + Docker + NVIDIA Container Toolkit). Add SLURM fairshare or simple wall-time + checkpointing for "you contributed more, you get more" accounting. This is where "earn-idle / draw-busy" actually becomes real on YOUR hardware, settled by social accounting (a shared ledger, fairshare decay) rather than a salable token.

RUNG 3 (burst when training big): When a job exceeds the collective's pooled GPUs, SkyPilot unifies your SSH machines + rented cloud into one CLI ("sky launch --infra ssh"), so you self-fund a burst. On commercial marketplaces (Vast.ai) you CAN both host and rent, but Vast.ai deliberately keeps host and renter on separate accounts and blocks cashout until referral earnings exceed lifetime spend, so the "one balance net-settle" is something YOU assemble manually, not a feature.

RUNG 4 (only if you accept rent risk): Token DePIN (Akash Homenode beta for 4090/5090 owners; io.net). This is the ONLY band designed so you supply and consume the same token. Akash's Burn-Mint Equilibrium (live 23 Mar 2026) is an explicit attempt to re-anchor the token to real usage, which is itself an admission the original design leaked rent. Treat any "yield" as partly other holders' dilution, not earned compute.

What a real virtuous circle requires (the load-bearing constraints): credit BOTH completed work and idle availability (or idle gets unrewarded and the commons starves); make credit non-salable and priority-only (the moment it's sellable or grants exclusion, it becomes rent); defend against free-riders/Sybil by deprioritizing rather than excluding (AI Horde) and by quorum-replication if results must be trusted (BOINC); keep the pool small and trust-based so isolation risk stays manageable. The richest public-commons programs (NAIRR, Empire AI, CalCompute, Mass AI Hub) are mostly US-academic-gated and NOT a realistic tap for a Paris collective; your equivalents are EGI/EOSC and French/EU research-infrastructure routes.

### Modalities: technical, governance, legal

TECHNICAL (federated pool tooling + isolation/security):
- Networking (solved): Tailscale node-sharing exposes ONLY the single shared machine to one named recipient ("not visible to the recipient's entire tailnet"); shared machines are quarantined by default (answer incoming, cannot initiate outbound); recipient still bound by your tailnet ACLs; reusable invite links work up to 1,000 times, expire unused in 30 days; only Owner/Admin can share. Accurate trust-scoping for lending one GPU box. (Note: Tailscale Peer Relays reached GA 18 Feb 2026, but Tailscale's own GPU-cost-splitting blog never mentions Peer Relays/CGNAT/distributed compute, that linkage would be your inference, not their claim.)
- Orchestration tiers: Exo (p2p, no master-worker, tensor parallelism ~1.8x on 2 devices / ~3.2x on 4, MLX backend, OpenAI-compatible API at localhost:52415, Thunderbolt 5 RDMA ~99% latency cut) BUT current repo lists Linux as CPU-only, GPU support under development, so Windows/Linux RTX 5090 boxes are NOT yet first-class GPU peers, best fit is a Mac-heavy fleet. dstack SSH fleets (list of hosts + SSH key in YAML; "GPU blocks" partition a host into concurrent slots as hard quotas; "placement: cluster" for distributed jobs) require Linux + Docker + passwordless sudo + AllowTcpForwarding yes + CUDA 12.1 + NVIDIA Container Toolkit, so a Windows 5090 box must run WSL2 or dual-boot. SkyPilot ("sky ssh up", "sky launch --infra ssh") unifies SSH machines + cloud + k8s + Slurm into one pool, good for cloud burst. SLURM fairshare (PriorityDecayHalfLife default 7 days, usage decayed every ~5 min, TRESBillingWeights bills each GPU model at separate rates) is capable but overkill for a tiny collective, simpler equivalents are wall-time limits + checkpointing or dstack GPU blocks.
- Isolation (the real risk, NOT solved by containers): NVIDIAScape (CVE-2025-23266, CVSS 9.0, disclosed July 2025 by Wiz) escapes the NVIDIA Container Toolkit to host root via a 3-line Dockerfile (LD_PRELOAD trick); all NCT up to v1.17.7 affected, fixed in v1.17.8. Wiz's verbatim lesson: "containers are not a strong security barrier and should not be relied upon as the sole means of isolation." GPUs leak between tenants: outside MIG they lack tenant-level memory isolation, so unclear VRAM lets a later job read leftover data, plus contention side-channels and GPU Rowhammer-class attacks. MIG (true hardware memory-path isolation) is NOT on consumer RTX 5090, it is product-segmented (same GB202 die ships MIG on RTX PRO 6000 but not on the 5090). Practical rung above plain containers: Kata Containers (each pod in a lightweight VM with its own kernel via hypervisor, full GPU passthrough one-GPU-per-pod, positioned for untrusted/multi-tenant). HONEST RULE: lend only to trusted humans, on a box you'd wipe, Tailscale-only access, VRAM zeroed between users, NCT patched.

GOVERNANCE (commons / Ostrom, fairness, free-riding/Sybil):
- Reward model: AI Horde awards a fulfilling worker exactly the kudos the requester was charged, AND gives online-but-idle workers nominal kudos in 10-minute increments, so availability itself is rewarded (this is the design that keeps a commons from starving). Kudos can't be bought/sold (ToS violation), can be freely gifted, never expire, only set queue priority (priority, NOT exclusive access); registered users start with >=25 kudos, anonymous with 0.
- Free-riding posture: tolerated and simply deprioritized, never excluded (Ostrom-compatible: graduated, non-punitive). Folding@home's Quick Return Bonus (final_points = base * max(1, sqrt(k * deadline / elapsed)), gated by passkey + 80%+ return record) shows how to reward reliability without coercion.
- Sybil / cheating defense as code: BOINC replicates each job across independent hosts and grants credit only to a validated quorum/consensus; adaptive replication then skips re-running jobs sent to proven-reliable hosts, cutting ~2x overhead toward ~1x (target 5-10% of CPU time). Use this only if results must be trusted by strangers; among trusted peers it's overkill.
- Scale reality check: pooled idle academic capacity is enormous and near-free (OSG >1.2B CPU-hours in 12 months, >100M opportunistic; EGI ~116,000 users across ~1.24M cores) but those are NOT a direct tap for you. BOINC's real current throughput is ~18.6 PFLOPS / ~89,400 computers (Nov 2025), an order smaller than the stale "41.58 PFLOPS / 791,443 machines" figure still circulating.

LEGAL / ECONOMIC / FISCAL (France, FLAG: confirm with an expert-comptable or avocat fiscaliste, this is NOT settled advice):
- Pure reciprocal lending: a true commodat / prêt à usage (Code civil art. 1875-1876) is by nature "essentiellement gratuit" and is the cleanest legal box for non-monetary lending. BUT any consideration to the lender, or any equivalent economic advantage, can strip the commodat and requalify the act as onerous (rental/bail). CRITICAL NUANCE TO CHECK: strict tit-for-tat GPU-for-GPU lending could itself read as an "avantage économique équivalent" and lose the commodat qualification, this exact point must go to a professional.
- Association loi 1901 (gestion désintéressée): escapes IS/TVA/CET on accessory lucrative receipts only if non-lucrative activity stays significantly predominant AND lucrative receipts stay under the 2024 franchise des impôts commerciaux of 78,596 EUR (up from 76,679 in 2023). A SCIC by contrast is fiscalisée de plein droit (commercial taxes apply by reason of corporate form, no sectorisation carve-out), per BOFiP and a parliamentary answer.
- CHATONS (Collectif des Hébergeurs Alternatifs) is the French/francophone reference culture for exactly this kind of decentralized, non-lucrative, ethical self-hosting commons, a natural community/legal frame to study before building.
- TOKEN/DePIN warning has a fiscal dimension too: token rewards are not neutral lending, they create taxable events and price exposure, another reason to keep the trusted-peer commons non-monetary and to consult a professional before any token path.
- BLANKET FLAG: every fiscal framing above is an option to confirm, never settled law, and the right move is a single short consult with an expert-comptable/avocat fiscaliste before formalizing any structure.

### Open questions

- FRENCH FISCAL/LEGAL: whether strict reciprocal GPU-for-GPU lending counts as an 'avantage économique équivalent' that strips the commodat (prêt à usage) qualification and makes it an onerous/taxable contract. This is the single most consequential open question and only an expert-comptable or avocat fiscaliste can settle it.
- Whether a tiny trusted collective should adopt any formal structure (association loi 1901 vs informal commodat vs SCIC) at all, or stay fully informal until receipts/scale force the question. The 78,596 EUR franchise and gestion-désintéressée tests are real but their application to compute-sharing specifically is unverified here.
- Exo's GPU support roadmap for Linux/Windows: today the RTX 5090 boxes are not first-class GPU peers in Exo, so the cleanest Mac-heavy inference fleet may not actually harness your most powerful cards. The timeline for Exo GPU support is unknown.
- Real-world security posture: the findings establish the threat (NVIDIAScape, VRAM leakage, no MIG on 5090) but not a validated, low-effort isolation recipe a non-expert can run. Kata Containers is the named rung above plain containers, but its operational cost/complexity for a solo artist is untested.
- Token DePIN economics are moving fast (Akash BME 23 Mar 2026, io.net incentive redesign): whether these redesigns actually eliminate the rent dynamic or just relabel it is not yet demonstrable, and any participation carries unmodeled price/slashing risk.
- EGI/EOSC and French/EU research-infrastructure access routes are named as the realistic public-commons equivalent for a Paris collective, but the actual eligibility, application path, and whether an independent artist-researcher (not a university) qualifies are not established in these findings.

---

*Sources for this section are linked inline above. The consolidated, verified source list and the verification method are in [SOURCES.md](../SOURCES.md).*
