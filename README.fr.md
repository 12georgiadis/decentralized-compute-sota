# Le compute hors des data centers

### Un état de l'art vérifié de l'informatique IA décentralisée (mi-2026)

> Louer sa machine pour l'IA, les réseaux GPU crypto, la lignée Folding@home / PlayStation 3, l'entraînement décentralisé de modèles, les communs ouverts. Ce qui est réel, ce qui est du vent, et si quelque chose peut vraiment émerger en dehors de Google, Amazon et Microsoft.

*English: see [README.md](README.md). Le survey technique détaillé est en anglais dans [docs/](docs/). La lecture critique signée est en français : [essai/decentralisation-du-compute.fr.md](essai/decentralisation-du-compute.fr.md).*

---

## En une phrase

La décentralisation du compute n'est **ni une voie morte, ni une révolution**. C'est un **deuxième tier** durable qui coexiste avec les data centers sans les remplacer au frontier. Il comprime la rente (une force anti-rente : H100 à 2 à 4 USD/heure contre les prix de liste des hyperscalers), contourne la pénurie de GPU, et maintient ouverte une porte de sortie sur l'entraînement libre qui compte politiquement plus qu'elle ne pèse en FLOP.

- **Croire** les revenus d'inférence et les résultats d'entraînement à faible communication.
- **Diviser par dix** les capitalisations de token et les nombres de GPU annoncés.

Le motif maître : partout, la **capacité annoncée dépasse de très loin la capacité réellement active**. io.net affiche 327 000 GPU « enregistrés » mais comptait environ 6 720 GPU actifs vérifiés par jour au Q1 2025 (environ 2 pour cent), après une attaque Sybil en 2024 portant sur près de 1,8 million de faux GPU. Le secteur DePIN entier pèse environ 10 milliards USD de capitalisation pour environ 72 millions USD de revenu réel on-chain en 2025 (Messari, *State of DePIN 2025*). L'auditabilité est la ligne de partage entre le signal et le bruit.

---

## Les cinq familles

| # | Famille | Qui fournit | Paiement | Charge viable | Grade de preuve |
|---|---|---|---|---|---|
| 1 | **Marketplaces commerciales** (Vast.ai, RunPod, TensorDock, Salad) | Pros et prosumers, agrégés | Fiat, prix de marché | Inférence, fine-tuning, training sur GPU loués | **Solide** (prix auditables, RunPod 120M USD ARR) |
| 2 | **Crypto / DePIN** (io.net, Render, Akash, Bittensor, Aethir, Nosana) | Hôtes incités par token | Token, parfois fiat | Inférence payée croissante, rendering, RL | **Mitigé** (revenu réel faible, caps spéculatives) |
| 3 | **Bénévole / open-source** (Folding@home, BOINC, l'ère PS3, AI Horde) | Cycles donnés, non payés | Aucun (altruisme, kudos) | Calcul scientifique massivement parallèle, **pas** le training LLM | **Prouvé mais limité par la charge** |
| 4 | **Entraînement décentralisé** (Prime Intellect, Nous, DiLoCo) | GPU dispersés, algos low-comm | Variable | Pré-entraînement low-comm et RL inter-continents | **Précoce mais réel** (la seule vraie nouveauté) |
| 5 | **Communs ouverts** (LeCun, open-weights, Project Tapestry) | Couche gouvernance / propriété | n/a | Précondition politique, pas une source de FLOP | Mouvement réel |

---

## Lire

Le survey technique complet et sourcé est en anglais dans [docs/](docs/) (sections 1 à 10). L'annexe des sources : [SOURCES.md](SOURCES.md).

La lecture critique, en français et signée, est ici : **[essai/decentralisation-du-compute.fr.md](essai/decentralisation-du-compute.fr.md)**.

---

## Licence et citation

Double licence : texte sous **CC BY-NC-ND 4.0**, code sous **PolyForm Noncommercial 1.0.0**. Voir [LICENSE.md](LICENSE.md). Citer avec [CITATION.cff](CITATION.cff).

Auteur : **Ismaël Joffroy Chandoutis**, 2026.
