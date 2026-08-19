# Inventaire des sources

**Statut :** Brouillon
**Responsable :** Cinthia Coelho
**Dernière vérification :** 2026-08-18
**Date d'observation :** 2026-08-18
**Version structurée :** [`data/sources.csv`](../data/sources.csv)

## Objet

Recenser les sources de données publiques mobilisables pour observer le territoire
clermontois, avec pour chacune : producteur, granularité, profondeur historique, cadence,
latence de publication, format, licence, sphère de compétence et ruptures connues.

Cet inventaire est un inventaire **d'aptitude analytique** : il répond à la question
« cette source permet-elle de mesurer quelque chose, et à quelles conditions ? ». Il ne
remplace pas un inventaire d'aptitude **probante**, qui répond à « ce document fait-il
foi ? ».

## Méthode

Relevé effectué le 18 août 2026 par consultation directe des pages de chaque producteur.
Les éléments marqués « à vérifier » n'ont pas été confirmés et ne doivent pas être
utilisés en production.

**Limites du relevé, déclarées.** Trois obstacles techniques ont limité la couverture, et
aucun n'a été contourné :

- les API des portails Opendatasoft de Clermont-Ferrand et de la Métropole sont
  interdites au robot par leur `robots.txt` ;
- les pages de catalogue de ces portails sont rendues en JavaScript et illisibles sans
  navigateur ;
- le domaine de la Ville n'a pas pu être lu (échec de validation TLS lors de la lecture
  du `robots.txt`).

Conséquence : environ **70 des 125 jeux de données** de l'organisation métropolitaine ont
été énumérés. Le catalogue maître, publié par la Métropole elle-même, comble cette lacune
en un téléchargement. Aucune de ces limites n'affecte un pipeline de production normal.

## Vue d'ensemble

| Domaine | Indicateurs | Ligne de base la plus profonde | Lacunes dures |
|---|---|---|---|
| Finances | 14 | 2010 (balances comptables) | Détail des subventions de la Ville, structure de la dette |
| Socio-économique | 10 | 1968 (recensement) | Chômage communal (inexistant par construction) |
| Éducation | 7 | ~2014 | **Restauration scolaire (totale)** |
| Culture | 5 | 2001 (musées) | **Série de lecture publique** |
| Sport | 2 | ~2014 | Historique des équipements |
| Sécurité | 7 | 2005 (accidents), 2016 (délinquance) | **Vidéoprotection** |
| Santé | 2 | ~2015 | — |
| Environnement | 5 | 2002 (déchets) | GES territoriaux récents |
| Mobilité | 5 | ~2020 | **Fréquentation du réseau de transport** |
| Démocratie | 5 | 2014 (élections) | Vote nominal (impossible en droit) |
| **Total** | **61** | | **6 lacunes dures** |

## Finances

La famille la mieux servie : séries longues, comparables entre communes, licence ouverte.

| Indicateur | Source | Début | Latence | Sphère | Note |
|---|---|---|---|---|---|
| Épargne brute et taux d'épargne | OFGL / balances DGFiP | 2012 | 8-12 mois | `ville` | Résultat direct de la gestion courante |
| Capacité de désendettement | OFGL | 2012 | 8-12 mois | `ville` | Marquer le seuil d'alerte usuel de 12 ans |
| Encours de dette €/hab | OFGL commune + EPCI | 2012 | 8-12 mois | `ville` `metropole` | **Honnête seulement si les deux dettes apparaissent** |
| Encours et ratios (source locale) | Ville de CF | 2020 | ~7 mois | `ville` | Extrait des comptes administratifs |
| Dépenses d'équipement €/hab | OFGL | 2012 | 8-12 mois | `ville` | Superposer le cycle électoral |
| Taux de TFPB et produit fiscal | REI, DGFiP | 1982 | ~12 mois | `ville` / `etat` | Le taux est voté ; les bases sont nationales |
| DGF €/hab | OFGL | 2018 | ~3 mois | `etat` | Trou 2014-2017 ; reconstituer par le compte 7411 |
| Rigidité des dépenses | Balances DGFiP | 2010 | ~7 mois | `ville` `etat` | Le point d'indice est national |
| Subventions aux associations (total) | Balances, compte 6574 | 2010 | ~7 mois | `ville` | Le levier politique le plus discrétionnaire |
| Subventions > 23 000 € (détail) | Métropole | 2020 | ~12 mois | `metropole` | La Ville ne publie pas |
| Budget primitif par chapitre | Ville de CF, SCDL/M57 | 2022 | ~7 mois | `ville` | Budget voté ; l'exécuté n'est pas ouvert |
| Commande publique | DECP consolidées | 2018 (fiable 2024) | ~2 mois | `ville` | **Ne jamais sommer les montants** : accords-cadres |
| Marchés publics de la Ville | Ville de CF | 2019 | ~7 mois | `ville` | Avec géolocalisation |
| Ratio d'intégration métropolitaine | OFGL consolidé | 2018 | 8-12 mois | `metropole` | « Quelle part de l'argent public le maire décide-t-il encore ? » |

**Avertissements de famille.** Les comptes individuels de la DGFiP portent sur le seul
budget principal, hors budgets annexes. Le compte administratif de la Ville n'est pas
publié en données ouvertes : pour la dépense réellement exécutée, la DGFiP est la seule
voie, avec 7 à 9 mois de latence. Piège d'hygiène constaté : sur le portail local, un jeu
intitulé « Budget 2023 » porte l'identifiant `bp2022` — ne jamais déduire l'année du nom
technique.

## Socio-économique

| Indicateur | Source | Début | Latence | Sphère | Note |
|---|---|---|---|---|---|
| Population municipale | INSEE | 1968 | ~3 ans | `etat` | Contexte, pas résultat |
| Demandeurs d'emploi cat. A | Dares / France Travail | fenêtre 10 ans | **21 jours** | `etat` | Le plus rapide ; arrondi au multiple de 5 ; **à archiver** |
| Taux de chômage BIT | INSEE, zone d'emploi | 2003 | 1 trimestre | `etat` | **Non communal** — l'indiquer dans le titre |
| Emploi salarié privé | URSSAF | 2006 | ~150 jours | `metropole` | Exclut la fonction publique — énorme ici |
| Taux de pauvreté | INSEE FiLoSoFi | 2012 | ~3 ans | `etat` | **Rupture 2023** ; ne pas titrer sans désagréger par âge |
| Niveau de vie médian | INSEE FiLoSoFi | 2012 | ~3 ans | `etat` | Idem |
| Logements vacants structurels | LOVAC | 2020 | ~1 an | `ville` | Un des rares indicateurs où l'action municipale est lisible |
| Parc social et taux SRU | RPLS, inventaire SRU | 2011 | 1-1,5 an | `metropole` | L'enjeu est chez les communes voisines |
| Créations d'établissements | INSEE | 2012 | ~7 mois | `metropole` | Désagréger par forme juridique |
| Population en QPV | INSEE / ANCT | 2015 | 3-5 ans | `etat` | 5 QPV, 15,1 % de la population ; **rupture 2024** |

**Le cas du chômage.** Il n'existe pas de taux de chômage communal en France, et cela ne
relève pas d'un oubli : le taux localisé est une estimation de synthèse combinant des
sources administratives et une enquête dont l'échantillon n'a aucune puissance
statistique sous la zone d'emploi. Trois substituts, à ne jamais confondre :

- *demandeurs d'emploi catégorie A* — communal, administratif, très rapide ;
- *taux de chômage de la zone d'emploi* — au sens BIT, non communal ;
- *chômage au sens du recensement* — communal, déclaratif, non BIT, trois ans de retard.

**Prudence éditoriale.** Le taux de pauvreté relevé en 2023 est élevé, en grande partie
par effet de la population étudiante qui déclare de faibles revenus. Ne jamais titrer sur
ce chiffre sans désagrégation par âge : c'est l'erreur la plus fréquente des observatoires
de villes universitaires.

## Éducation, petite enfance

| Indicateur | Source | Début | Latence | Sphère | Note |
|---|---|---|---|---|---|
| Effectifs et classes, écoles | DEPP | ~2014 | ~12 mois | `ville` / `etat` | Bâti communal, classes nationales |
| Effectifs des collèges | DEPP | ~2014 | ~12 mois | `departement` | Contexte |
| Réussite et valeur ajoutée, lycées | DEPP (IVAL) | ~2014 | ~12 mois | `region` | Contexte |
| Valeur ajoutée DNB, collèges | DEPP (IVAC) | **2022** | ~12 mois | `departement` | Série DNB antérieure gelée : deux séries incompatibles |
| Poids étudiant | MESR | 2015-16 | ~18 mois | `etat` | Indicateur identitaire de la ville |
| Couverture petite enfance | CNAF | **2017** | 24-36 mois | `ville` | Offre théorique, pas accès réel |
| **Restauration scolaire** | — | — | — | `ville` | **Lacune totale** |

## Culture, sport, vie associative

| Indicateur | Source | Début | Latence | Sphère | Note |
|---|---|---|---|---|---|
| Lecture publique | Min. Culture / SLL | millésime courant | ~30 mois | `metropole` | **Série impossible** en données ouvertes |
| Musées de France | Min. Culture | 2001 | ~4 ans | `metropole` | Série s'arrête en 2022 |
| Équipements (BPE) | INSEE | 2015 | ~12 mois | `ville` `metropole` | **Utiliser uniquement la base d'évolution** |
| Dépense culture et sport | Balances DGFiP | à vérifier | ~7 mois | `ville` `metropole` | Dépend de la classification fonctionnelle |
| Créations d'associations | RNA / Ithéa | 2011 | 12-24 mois | `etat` / `ville` | Utiliser le flux, jamais le stock |
| Licences sportives | INJEP | ~2014 | ~30 mois | associatif / `ville` | 3 fédérations exclues |
| Équipements sportifs | Data ES | sans historique | 0 | `ville` | **Registre vivant — à archiver** |

**Pourquoi la culture est le point faible.** La cause n'est pas accidentelle, elle est
institutionnelle : le service statistique du ministère de la Culture publie à l'échelle
régionale et en PDF, là où ceux de l'Éducation et des Sports publient à l'échelle
communale et en CSV. C'est une différence de doctrine entre ministères, et elle ne se
corrigera pas d'elle-même. La seule voie réaliste est locale.

**Rappel de compétence :** à Clermont-Ferrand la culture relève de la Métropole. Voir
[13](13_SPHERES_DE_COMPETENCE.md).

## Sécurité, santé

| Indicateur | Source | Début | Latence | Sphère | Note |
|---|---|---|---|---|---|
| Police municipale | Min. Intérieur | 2012 | ~24 mois | `ville` | **Le seul indicateur de sécurité pleinement imputable** |
| Vols de véhicules | SSMSI | 2016 | ~6 mois | `etat` | Taux de plainte ~90 % : proche du phénomène réel |
| Dégradations volontaires | SSMSI | 2016 | ~6 mois | `ville` `etat` | Qualité de l'espace public plus que criminalité |
| Violences intrafamiliales | SSMSI | 2016 | ~6 mois | `etat` / `ville` | **Lecture inversée** — voir ci-dessous |
| Accidents corporels | ONISR (BAAC) | 2005 | ~12 mois | `metropole` `ville` | Utiliser tués et accidents ; **écarter les blessés graves** |
| Verbalisations | Ville de CF | 2019 | ~7 mois | `ville` | Géolocalisées |
| Accès aux généralistes (APL) | DREES | ~2015 | ~2 ans | `etat` | **Exclut l'hôpital** : sans cette note, faux désert médical |
| Établissements de santé | FINESS | — | continue | `etat` | Chaîne de production en transition |
| **Vidéoprotection** | — | — | — | `ville` | **Lacune** |

**La règle de lecture de la délinquance enregistrée.** Ces chiffres mesurent conjointement
un phénomène, la propension des victimes à porter plainte, et l'activité des services.
Trois conséquences :

- les vols de véhicules (≈ 90 % de plaintes) approchent le phénomène réel ;
- les violences intrafamiliales (≈ 10 % de plaintes) mesurent surtout la libération de la
  parole et la qualité de l'accueil : **une hausse peut être un progrès**, et titrer
  « hausse des violences » est éditorialement interdit ;
- les infractions révélées par l'activité policière, comme les stupéfiants, mesurent des
  effectifs et des priorités nationales, pas la consommation.

Ne jamais intituler ces séries « criminalité » ou « insécurité ».

## Environnement, mobilité

| Indicateur | Source | Début | Latence | Sphère | Note |
|---|---|---|---|---|---|
| Indice ATMO | Atmo AuRA | fenêtre 9 jours | 1 jour | `metropole` `etat` | **Archiver quotidiennement** |
| Concentrations de polluants | Geod'air | ~2014 | variable | `metropole` `etat` | La série longue, par station |
| Déchets kg/habitant | Métropole | **2002** | ~9 mois | `metropole` | La meilleure série du catalogue |
| GES de la Ville | Ville de CF | 2014 | ~5 ans | `ville` | S'arrête en 2021 |
| Exposition au bruit | Métropole | 2011 et 2022 | ~1 an | `metropole` | Prochain point ~2027, soit mi-mandat |
| Fréquentation cyclable | Capteurs ZELT | à vérifier | jours | `metropole` | Points fixes |
| Aménagements cyclables | Geovelo / OSM | ~2020 | 1 mois | `metropole` | Une hausse peut être de la cartographie |
| Offre de transport | GTFS T2C | 2025 | jours | `metropole` | Offre ≠ usage |
| Occupation des parkings | Métropole | temps réel | 0 | `metropole` | **Archiver toutes les 15 minutes** |
| **Fréquentation du réseau** | — | — | — | `metropole` | **Lacune** |

## Démocratie

| Indicateur | Source | Début | Latence | Sphère | Note |
|---|---|---|---|---|---|
| Délibérations votées (jeu ouvert) | Ville via Métropole | 2020-02 | couverture jusqu'à 09/2024 | `ville` | **Vérification bloquante** |
| Liste des délibérations | Site de la Ville | 2022-07 | 1 semaine | `ville` | Inclut les **refusées** |
| Vidéo des séances | Chaîne officielle | ~2020 | le jour même | `ville` | La source la plus rapide du projet |
| Procès-verbal | Site de la Ville | — | 6-9 semaines | `ville` | Le plus riche, le plus lent |
| Résultats électoraux | Ville de CF | 2014 | semaines | `etat` | Inclut mars 2026 |

Détail et cadre juridique : [15](15_SOURCES_DES_DECISIONS_MUNICIPALES.md).

## Vérifications bloquantes

Trois contrôles conditionnent des décisions d'architecture. Aucun n'a été effectué.

1. **Date maximale réelle du jeu de données des délibérations.** Décide si ce jeu est
   source primaire ou note de bas de page — et avec lui toute l'architecture du pipeline.
2. **Présence d'une classification fonctionnelle dans les balances comptables.** Décide
   s'il est possible de dire combien la ville dépense en culture, en sport ou en éducation
   séparément — c'est-à-dire si la lecture par domaine est possible.
3. **Catalogue maître du portail métropolitain.** Ferme la lacune d'énumération des ~55
   jeux de données non recensés.

## État actuel

Brouillon. 61 indicateurs recensés, dont 6 lacunes dures et 4 éléments explicitement
marqués « à vérifier ». Aucune donnée n'a été acquise ; documenter une source n'autorise
pas à la collecter.

## Documents liés

- [`data/sources.csv`](../data/sources.csv) — version structurée
- [11_LATENCE_ET_DEUX_HORLOGES](11_LATENCE_ET_DEUX_HORLOGES.md)
- [12_RUPTURES_DE_SERIE](12_RUPTURES_DE_SERIE.md)
- [13_SPHERES_DE_COMPETENCE](13_SPHERES_DE_COMPETENCE.md)
- [14_VOLATILITE_DES_SOURCES](14_VOLATILITE_DES_SOURCES.md)
- [17_REGISTRE_DES_LACUNES](17_REGISTRE_DES_LACUNES.md)
