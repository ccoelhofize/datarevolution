# Index

**Statut :** Brouillon
**Responsable :** Cinthia Coelho
**Dernière vérification :** 2026-08-18

## Documents

| Doc | Titre | Statut | Rôle |
|---|---|---|---|
| [00](00_PERIMETRE.md) | Périmètre | Brouillon | Cadrage territorial et temporel ; frontière avec `project-iagora` |
| [10](10_INVENTAIRE_DES_SOURCES.md) | Inventaire des sources | Brouillon | 61 indicateurs vérifiés |
| [11](11_LATENCE_ET_DEUX_HORLOGES.md) | Latence et deux horloges | Brouillon | Délais de publication ; fenêtre minimale d'évaluabilité |
| [12](12_RUPTURES_DE_SERIE.md) | Ruptures de série | Brouillon | Registre des discontinuités datées |
| [13](13_SPHERES_DE_COMPETENCE.md) | Sphères de compétence | Brouillon | Vocabulaire et attribution par domaine |
| [14](14_VOLATILITE_DES_SOURCES.md) | Volatilité des sources | Brouillon | Classes de volatilité ; perte irréversible |
| [15](15_SOURCES_DES_DECISIONS_MUNICIPALES.md) | Sources des décisions municipales | Brouillon | Délibérations : classes, latences, droit |
| [16](16_TERRITOIRES_DE_COMPARAISON.md) | Territoires de comparaison | Brouillon — **mise en œuvre bloquée** | Strate DGFiP et panel gelé |
| [17](17_REGISTRE_DES_LACUNES.md) | Registre des lacunes | Brouillon | Ce qui manque et ce qui a été demandé |
| [99](99_INDEX.md) | Index | — | Ce document |

Voir aussi [`upstream/`](../upstream/README.md) et [`data/sources.csv`](../data/sources.csv).

## Décisions structurantes déjà prises

| # | Décision | Document |
|---|---|---|
| D1 | L'objet observé est le **territoire** (Ville + Métropole), pas l'institution | [00](00_PERIMETRE.md) |
| D2 | Tout chiffre porte sa date de référence, sa date de publication et sa sphère de compétence | [11](11_LATENCE_ET_DEUX_HORLOGES.md), [13](13_SPHERES_DE_COMPETENCE.md) |
| D3 | Aucune série ne franchit une rupture sans marque explicite | [12](12_RUPTURES_DE_SERIE.md) |
| D4 | Deux horloges séparées : décisions et impacts | [11](11_LATENCE_ET_DEUX_HORLOGES.md) |
| D5 | Les lacunes sont enregistrées et publiées, jamais comblées par inférence | [17](17_REGISTRE_DES_LACUNES.md) |
| D6 | Le panel de comparaison, quand il existera, sera public et gelé | [16](16_TERRITOIRES_DE_COMPARAISON.md) |

## Questions ouvertes

| # | Question | Bloque | Document |
|---|---|---|---|
| Q1 | Quelle est la date maximale réelle du jeu de données des délibérations ? | L'architecture du pipeline | [15](15_SOURCES_DES_DECISIONS_MUNICIPALES.md) |
| Q2 | Les balances comptables portent-elles une classification fonctionnelle ? | La lecture financière par domaine | [10](10_INVENTAIRE_DES_SOURCES.md) |
| Q3 | Quels sont les ~55 jeux de données locaux non énumérés ? | L'exhaustivité de l'inventaire | [10](10_INVENTAIRE_DES_SOURCES.md) |
| Q4 | Comment concilier capture périodique et admission validée par un humain ? | La préservation des sources volatiles | [14](14_VOLATILITE_DES_SOURCES.md) |
| Q5 | La comparaison inter-territoriale sera-t-elle autorisée ? | Tout comparateur | [16](16_TERRITOIRES_DE_COMPARAISON.md) |
| Q6 | Quelle est la date d'adoption de la M57 par la Ville ? | La reconstruction des séries comptables | [12](12_RUPTURES_DE_SERIE.md) |

## Prochaines actions

1. Résoudre Q1, Q2 et Q3 — trois vérifications, aucune ne demande plus d'une heure.
2. Rédiger la proposition de préservation des sources volatiles ([`upstream/`](../upstream/README.md)).
3. Arrêter et geler le panel de comparaison.
4. Déposer les trois premières demandes d'accès ([17](17_REGISTRE_DES_LACUNES.md)).
5. Vérifier les attributions de compétence contre BANATIC et les statuts de la Métropole.
