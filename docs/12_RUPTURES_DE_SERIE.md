# Registre des ruptures de série

**Statut :** Brouillon
**Responsable :** Cinthia Coelho
**Dernière vérification :** 2026-08-18
**Date d'observation :** 2026-08-18

## Objet

Recenser les discontinuités méthodologiques, institutionnelles et périmétriques qui
**invalident une comparaison temporelle** sur le territoire clermontois, et fixer la règle
d'affichage qui en découle.

Une rupture de série n'est pas une donnée manquante. C'est une donnée présente, exacte,
et **non comparable** avec celle qui la précède. C'est le mode de défaillance le plus
dangereux d'un observatoire, parce qu'il produit des graphiques parfaitement lisibles et
entièrement faux.

## Règle d'affichage

> **Aucune représentation temporelle ne franchit une rupture non résolue sans marque
> visuelle explicite et sans note accessible indiquant la nature de la rupture.**

Trois traitements possibles, par ordre de préférence :

1. **Segmenter** la série de part et d'autre de la rupture, sans ligne de jonction.
2. **Marquer** la rupture par un trait vertical et une infobulle, si la continuité
   visuelle reste défendable.
3. **Renoncer** à la série et n'afficher que la période homogène la plus utile.

Ne jamais interpoler par-dessus une rupture. Ne jamais présenter comme « évolution » un
écart dont une partie est méthodologique.

## Registre

### R1 — 2018-01-01 · Création de Clermont Auvergne Métropole

**Type :** transfert de compétences et de périmètre financier
**Séries affectées :** l'ensemble des séries financières de la Ville ; dépenses
d'équipement ; voirie ; culture ; développement économique ; déchets ; transport.

C'est la rupture la plus dangereuse du territoire. Les dépenses et la dette de la Ville
diminuent par **transfert**, non par gestion. La dette du territoire passe d'environ
30 M€ en 2017 à environ 400 M€ fin 2021 — portée par la Métropole, pas par la Ville.

**Traitement obligatoire :** toute série financière de la Ville franchissant 2018 doit
être accompagnée de la série **consolidée Ville + Métropole** (ensemble intercommunal).
Une courbe « dépenses de la Ville 2014-2025 » présentée seule est un mensonge graphique.

Voir aussi [13_SPHERES_DE_COMPETENCE](13_SPHERES_DE_COMPETENCE.md) : cette rupture et
l'attribution des compétences sont la même réalité institutionnelle, vue par l'horloge
puis par le pouvoir.

### R2 — 2021 · Réforme de la taxe d'habitation

**Type :** changement d'assiette fiscale
**Séries affectées :** taux et produit de la taxe foncière sur les propriétés bâties ;
recettes fiscales communales.

La commune absorbe la part départementale de la TFPB, avec un coefficient correcteur de
neutralisation. Le taux communal de 2021 **n'est pas comparable** à celui de 2020 : il
additionne le taux communal et le taux départemental antérieurs. Le produit de taxe
d'habitation disparaît.

### R3 — 2022 · Élargissement du périmètre de la délinquance enregistrée

**Type :** changement de champ de comptage
**Séries affectées :** indices SSMSI communaux.

Depuis 2022, les bases couvrent l'ensemble des crimes et délits non routiers enregistrés.
Plusieurs indices augmentent par effet de comptage. Rupture parallèle du côté de l'enquête
de victimation : passage de CVS à VRS la même année.

**Rappel de champ, distinct de la rupture :** la base communale ne commence qu'en **2016**.
Une ligne de base 2014 en matière de sécurité communale est impossible.

### R4 — 2023 · FiLoSoFi 2

**Type :** refonte de la source de localisation des ménages
**Séries affectées :** niveau de vie médian, taux de pauvreté, indicateurs d'inégalité,
à l'échelle communale, infracommunale et QPV.

Cause : disparition de la taxe d'habitation, qui servait à localiser les ménages. L'INSEE
déclare explicitement que les indicateurs 2023 **ne sont pas comparables** avec les
millésimes 2012 à 2021. Aggravation : **il n'existe pas de millésime 2022**.

**Conséquence directe :** il est impossible de tracer une courbe continue du taux de
pauvreté de Clermont-Ferrand de 2014 à 2023. Tout écart apparent entre 2021 et 2023 peut
être entièrement méthodologique.

**Effet secondaire à signaler :** les données de revenu en QPV les plus récentes relèvent
de FiLoSoFi 1 (millésime 2021) tandis que les données communales relèvent de FiLoSoFi 2
(millésime 2023). Le rapport QPV / ville n'est donc **pas calculable correctement**
aujourd'hui.

### R5 — 2024 · Trois ruptures simultanées

**a) M57 obligatoire pour toutes les collectivités.** Renumérotation des comptes par
nature et changement de nomenclature fonctionnelle. Les séries construites compte par
compte à partir des balances cassent. Clermont publiait déjà son budget en M57 dès 2023 :
la rupture peut donc être antérieure d'un an pour la Ville — **à vérifier** sur la
délibération d'adoption anticipée.

**b) Nouvelle géographie des quartiers prioritaires.** Clermont-Ferrand compte 5 QPV.
Le suffixe du code porte l'information de continuité : `N` nouveau, `M` périmètre modifié,
`I` périmètre identique.

| Code | Quartier | Continuité |
|---|---|---|
| QN06307N | Centre | **Nouveau** — aucun historique avant 2024 |
| QN06301M | Saint-Jacques | **Modifié** — évolution = effet réel + effet de périmètre |
| QN06302I | Quartiers Nord | Identique — série chaînable |
| QN06303I | La Gauthière | Identique — série chaînable |
| QN06304I | Fontaine du Bac | Identique — série chaînable |

**c) Nouveau régime des données essentielles de la commande publique.** Publication
centralisée, 27 champs obligatoires, applicable aux contrats notifiés à partir du
1er janvier 2024. La hausse de volume observée en 2024 est une hausse de **déclaration**,
pas d'achat public.

### R6 — 2026 · Compte financier unique

**Type :** changement de document source
**Séries affectées :** comptes exécutés.

Le compte financier unique remplace le compte administratif et le compte de gestion, à
partir de l'exercice 2026, avec un premier vote au plus tard le 30 juin 2027. La rupture
tombe exactement sur le premier exercice exécuté du mandat. Tout analyseur devra gérer
les deux formats.

### R7 — permanent · Périmètre comptable

Les comptes individuels de la DGFiP portent sur le **seul budget principal**, à
l'exclusion des budgets annexes. L'OFGL propose les deux versions. Comparer une valeur
consolidée à une valeur « budget principal » produit des écarts de plusieurs dizaines de
millions d'euros. **Choisir une convention, l'écrire sur chaque graphique.**

### R8 — permanent · Dénominateur de population

Population municipale ≠ population totale ≠ population DGF. Les millésimes INSEE changent
chaque année avec trois ans de décalage. Recalculer une série en euros par habitant avec
un millésime plus récent déplace toute la série. Fixer une source de population unique et
la déclarer.

### R9 — 2008 · Taux de chômage localisé

Abandon de l'interprétation française du concept BIT au profit de l'interprétation
européenne, et passage d'une mesure de fin de trimestre à une moyenne trimestrielle.
Séries antérieures et postérieures non comparables. Ne concerne que les séries remontant
avant 2008.

### R10 — divers · Ruptures propres à une source

Recensées dans [l'inventaire](10_INVENTAIRE_DES_SOURCES.md), colonne « ruptures » :
questionnaire de multi-résidence du recensement (2018, effet sensible dans une ville
universitaire) ; enquête de recensement annulée en 2021 ; passage à 100 % DSN dans les
effectifs URSSAF (juin 2021) puis inclusion des apprentis (juin 2023) ; comptabilisation
des UEEA dans les effectifs du premier degré (2024) ; gel de la série DNB et démarrage des
indicateurs de valeur ajoutée des collèges en 2022 ; absence de millésime 2022 de la base
permanente des équipements puis harmonisation européenne en 2023 ; blessés hospitalisés
non comparables depuis 2018 dans les accidents de la route ; révision méthodologique de
l'accessibilité aux médecins en 2015 ; mise en place du dispositif GMBI (2023) puis
changement déclaratif (2025) dans les logements vacants.

## Ce qui reste à établir

- Faire de ce registre un **enregistrement structuré** plutôt qu'un document en prose,
  pour qu'une rupture soit interrogeable et applicable à plusieurs séries à la fois.
- Vérifier la date exacte d'adoption de la M57 par la Ville de Clermont-Ferrand.
- Distinguer, dans le modèle de données, « valeur manquante » et « série
  méthodologiquement incomparable à partir de cette date ». Cette distinction n'existe
  aujourd'hui nulle part.

## État actuel

Brouillon. Les ruptures R1 à R6 sont documentées et sourcées ; R7 à R10 sont établies mais
mériteraient chacune une référence primaire explicite.

## Documents liés

- [10_INVENTAIRE_DES_SOURCES](10_INVENTAIRE_DES_SOURCES.md)
- [11_LATENCE_ET_DEUX_HORLOGES](11_LATENCE_ET_DEUX_HORLOGES.md)
- [13_SPHERES_DE_COMPETENCE](13_SPHERES_DE_COMPETENCE.md)
- [16_TERRITOIRES_DE_COMPARAISON](16_TERRITOIRES_DE_COMPARAISON.md)
