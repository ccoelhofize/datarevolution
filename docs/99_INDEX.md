# Index

**Statut :** Brouillon
**Responsable :** Cinthia Coelho
**Dernière vérification :** 2026-08-19

## Documents

| Doc | Titre | Statut | Rôle |
|---|---|---|---|
| [00](00_PERIMETRE.md) | Périmètre | Brouillon | Cadrage territorial, temporel et éditorial |
| [10](10_INVENTAIRE_DES_SOURCES.md) | Inventaire des sources | Brouillon | 61 indicateurs vérifiés |
| [11](11_LATENCE_ET_DEUX_HORLOGES.md) | Latence et deux horloges | Brouillon | Délais de publication ; fenêtre minimale d'évaluabilité |
| [12](12_RUPTURES_DE_SERIE.md) | Ruptures de série | Brouillon | Registre des discontinuités datées |
| [13](13_SPHERES_DE_COMPETENCE.md) | Sphères de compétence | Brouillon | Qui décide quoi |
| [14](14_VOLATILITE_DES_SOURCES.md) | Volatilité des sources | Brouillon | Ce qui se perd sans copie datée |
| [15](15_SOURCES_DES_DECISIONS_MUNICIPALES.md) | Sources des décisions municipales | Brouillon | Délibérations : classes, latences, droit |
| [16](16_TERRITOIRES_DE_COMPARAISON.md) | Territoires de comparaison | Brouillon | Strate DGFiP et panel gelé |
| [17](17_REGISTRE_DES_LACUNES.md) | Registre des lacunes | Brouillon | Ce qui manque et ce qui a été demandé |
| [18](18_CHANTIERS.md) | Les six chantiers | Brouillon | Le plan de travail de fond |
| [99](99_INDEX.md) | Index | — | Ce document |

Voir aussi [`AGENTS.md`](../AGENTS.md) et [`data/sources.csv`](../data/sources.csv).

## Décisions structurantes déjà prises

| # | Décision | Document |
|---|---|---|
| D1 | L'objet observé est le **territoire** (Ville + Métropole), pas l'institution | [00](00_PERIMETRE.md) |
| D2 | Tout chiffre porte sa date de référence, sa date de publication et sa sphère de compétence | [11](11_LATENCE_ET_DEUX_HORLOGES.md), [13](13_SPHERES_DE_COMPETENCE.md) |
| D3 | Aucune série ne franchit une rupture sans marque explicite | [12](12_RUPTURES_DE_SERIE.md) |
| D4 | Deux horloges séparées : décisions et impacts | [11](11_LATENCE_ET_DEUX_HORLOGES.md) |
| D5 | Les lacunes sont enregistrées et publiées, jamais comblées par inférence ; aucun constat de non-conformité avant une demande restée sans réponse | [17](17_REGISTRE_DES_LACUNES.md) |
| D6 | Le panel de comparaison sera public et gelé | [16](16_TERRITOIRES_DE_COMPARAISON.md) |
| D7 | Le produit est une vitrine de l'état de santé de la ville ; le suivi des engagements en est une couche | [00](00_PERIMETRE.md) |
| D8 | Le document administratif est une preuve, jamais le contenu proposé au lecteur | [00](00_PERIMETRE.md), [18](18_CHANTIERS.md) |
| D9 | Aucune notion technique ne paraît dans l'interface sans sa traduction | [18](18_CHANTIERS.md) |

## Questions ouvertes

| # | Question | Bloque | Où |
|---|---|---|---|
| Q1 | Quelle est la date maximale réelle du jeu de données des délibérations ? | Chantier 5 | issue #1 |
| Q2 | Les balances comptables portent-elles une ventilation par domaine ? | Lecture financière par domaine | issue #2 |
| Q3 | Quels sont les ~55 jeux de données locaux non énumérés ? | Chantier 1 | issue #3 |
| Q4 | Quelle cadence de capture, et où stocker les copies datées ? | Chantier 1 | [14](14_VOLATILITE_DES_SOURCES.md) |
| Q5 | Quelles douze villes composent le panel, et à quelle date le geler ? | Chantier 3 | [16](16_TERRITOIRES_DE_COMPARAISON.md) |
| Q6 | Quelle est la date d'adoption de la M57 par la Ville ? | Reconstruction des séries comptables | [12](12_RUPTURES_DE_SERIE.md) |

### Questions fermées

| Question | Réponse | Date |
|---|---|---|
| La comparaison entre villes est-elle autorisée ? | **Oui.** L'exclusion venait d'un périmètre hérité, devenu sans objet | 2026-08-19 |
| Une capture programmée est-elle permise ? | **Oui**, sous les garde-fous énoncés en [14](14_VOLATILITE_DES_SOURCES.md) | 2026-08-19 |

## Prochaines actions

1. Résoudre Q1, Q2 et Q3 — trois vérifications, aucune ne demande plus d'une heure.
2. Lancer le chantier 1 : la copie datée.
3. Arrêter et geler le panel de comparaison.
4. Déposer les trois premières demandes d'accès.
5. Vérifier les attributions de compétence contre BANATIC et les statuts de la Métropole.
