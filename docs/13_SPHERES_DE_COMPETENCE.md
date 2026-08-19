# Sphères de compétence

**Statut :** Brouillon
**Responsable :** Cinthia Coelho
**Dernière vérification :** 2026-08-18
**Date d'observation :** 2026-08-18

## Objet

Définir un vocabulaire contrôlé des sphères institutionnelles, et attribuer chaque domaine
observé à la sphère qui **décide réellement**.

Sans cette attribution, un observatoire produit mécaniquement une imputation fausse : il
place un chiffre sous la photographie d'un maire et laisse le lecteur conclure que ce
maire en est responsable. C'est vrai pour une minorité des indicateurs seulement.

## Vocabulaire

| Valeur | Signification |
|---|---|
| `ville` | Commune de Clermont-Ferrand |
| `metropole` | Clermont Auvergne Métropole (ou SMTC pour les transports) |
| `departement` | Conseil départemental du Puy-de-Dôme |
| `region` | Région Auvergne-Rhône-Alpes |
| `etat` | État, ses services déconcentrés et ses opérateurs (préfecture, rectorat, ARS, police nationale, France Travail) |
| `partagee` | Deux sphères ou plus décident conjointement — les sphères doivent alors être énumérées |
| `indeterminee` | L'attribution n'a pas encore été établie ; valeur par défaut, jamais un choix éditorial |

**Règles.**

1. Tout indicateur publié porte une sphère. `indeterminee` est admissible et honnête ;
   l'absence de champ ne l'est pas.
2. La sphère est affichée **à côté du chiffre**, au même niveau de lisibilité.
3. `partagee` n'est pas une échappatoire : il faut nommer les sphères et dire ce que
   chacune décide.
4. La sphère n'est pas une opinion. Elle se justifie par un texte : code général des
   collectivités territoriales, statuts de la Métropole, ou base BANATIC des compétences
   exercées par l'EPCI.

## Attribution par domaine

### Ce que la Ville décide réellement

| Domaine | Portée |
|---|---|
| Écoles maternelles et élémentaires | Bâtiments, entretien, fluides, ATSEM, matériel, sectorisation — **pas** les enseignants, les programmes ni les ouvertures de classes |
| Restauration scolaire, périscolaire, ALSH | Compétence facultative mais exercée, entièrement municipale |
| Petite enfance | Autorité organisatrice de l'accueil du jeune enfant depuis le 1er janvier 2025 ; financement CAF ; PMI départementale |
| Police municipale | Recrutement, doctrine d'emploi, horaires, armement, vidéoprotection |
| Pouvoir de police de la circulation | Zones 30, stationnement, arrêtés |
| Subventions aux associations | Levier politique le plus discrétionnaire du budget municipal |
| Taux des impôts locaux | Le taux est voté par le conseil ; **les bases relèvent de l'État** |
| Logement vacant | Taxe sur les logements vacants, permis de louer, OPAH, action coercitive |
| Équipements sportifs de proximité | Propriété et entretien |
| Écoles de musique, salles de spectacle de quartier, équipements de proximité | Restent communaux |

### Ce que la Métropole décide

| Domaine | Remarque |
|---|---|
| **Culture** | **44 sites culturels**, dont les 15 bibliothèques et médiathèques, les 3 musées de France (Roger-Quilliot, Bargoin, Henri-Lecoq), le conservatoire à rayonnement régional et l'école supérieure d'art |
| Déchets | Collecte, déchèteries, tarification |
| Transport et mobilité | Via le SMTC ; voirie ; aménagements cyclables ; ZFE |
| Développement économique | Zones d'activité, attractivité |
| Habitat | PLH, délégation des aides à la pierre |
| Urbanisme | PLUi |
| Bruit | Cartes stratégiques, PPBE |

> **Constat majeur du relevé.** À Clermont-Ferrand, **la culture n'est pas une compétence
> de la Ville**. Étiqueter un indicateur culturel `ville` serait factuellement faux. Le
> risque n'est pas théorique : un bloc « Culture » sur une page consacrée à la Ville
> attribue implicitement au maire une politique qu'il ne décide pas.

### Ce que d'autres sphères décident

| Domaine | Sphère |
|---|---|
| Collèges | `departement` |
| Lycées | `region` |
| Enseignement supérieur | `etat` (avec cofinancement immobilier `region` et `metropole`) |
| Enseignants, programmes, ouvertures de classes | `etat` |
| Police nationale, enquête, élucidation | `etat` |
| Justice | `etat` — et non imputable à l'échelle communale (voir plus bas) |
| Santé, autorisations d'établissements, démographie médicale | `etat` / ARS |
| Emploi, chômage, règles d'inscription | `etat` |
| Prestations sociales, niveau de vie, pauvreté | `etat` |
| Dotations de l'État, bases fiscales, point d'indice de la fonction publique | `etat` |
| Géographie des quartiers prioritaires | `etat` (décret) ; contrat de ville `partagee` |

## Conséquences éditoriales

**1. La sphère est une information, pas une réserve.** Le fait que la majorité des chiffres
par lesquels on juge un maire français échappent à son pouvoir est en soi le constat
politique le plus utile de l'observatoire. Un citoyen qui le comprend réclame la bonne
chose à la bonne personne.

**2. Les indicateurs pleinement municipaux sont rares — et donc précieux.** Effectifs de
police municipale, subventions aux associations, restauration scolaire, logement vacant,
taux d'imposition votés. Ce sont eux qui portent la responsabilité réelle du mandat.

**3. Certains indicateurs ne sont imputables à personne à l'échelle communale.** Le
ressort du tribunal judiciaire de Clermont-Ferrand couvre une large part du département :
aucun indicateur de réponse pénale n'est attribuable à la commune. Ce n'est pas une
lacune de données, c'est une impossibilité structurelle — et elle protège autant l'exécutif
qu'elle limite l'observatoire.

**4. Une série qui change de sphère change de nature.** C'est exactement ce qui se produit
en 2018 : voir [12_RUPTURES_DE_SERIE](12_RUPTURES_DE_SERIE.md), R1. Compétence et
comparabilité sont ici la même question.

## Ce qui reste à établir

- Vérifier chaque attribution contre la base BANATIC des compétences effectivement
  exercées par Clermont Auvergne Métropole, et contre les statuts de la Métropole.
- Trancher le traitement des équipements communautaires de proximité, cofinancés par la
  Métropole mais gérés localement : `partagee` semble la valeur juste, à confirmer.
- Documenter le rôle propre du CCAS, qui n'apparaît pas encore dans ce document.

## État actuel

Brouillon. Le vocabulaire est une proposition. Les attributions relèvent d'un relevé
documentaire et doivent être confirmées source juridique par source juridique avant toute
publication.

## Documents liés

- [10_INVENTAIRE_DES_SOURCES](10_INVENTAIRE_DES_SOURCES.md)
- [12_RUPTURES_DE_SERIE](12_RUPTURES_DE_SERIE.md)
- [00_PERIMETRE](00_PERIMETRE.md)
