# Périmètre

**Statut :** Brouillon
**Responsable :** Cinthia Coelho
**Dernière vérification :** 2026-08-18
**Date d'observation :** 2026-08-18

## Objet

Définir ce que ce dépôt couvre, ce qu'il exclut, et où passe la frontière avec le dépôt
`project-iagora`. Sans cette frontière écrite, les deux dépôts divergent en quelques mois.

## Périmètre territorial

| Entité | Code | Rôle dans l'observatoire |
|---|---|---|
| Clermont-Ferrand | INSEE 63113 | Territoire principal |
| Clermont Auvergne Métropole | EPCI, 21 communes | **Indispensable** — exerce une large part des compétences |
| Zone d'emploi de Clermont-Ferrand | — | Seul niveau où existe un taux de chômage au sens BIT |
| Aire d'attraction / unité urbaine | AAV2020-022 / UU2020-63701 | Contexte |
| QPV | 5 quartiers, 15,1 % de la population | Analyse infra-communale |
| Panel de villes-centres | 10 à 12 communes | Comparaison — voir [16](16_TERRITOIRES_DE_COMPARAISON.md) |

**Décision de périmètre.** L'objet observé est le **territoire**, pas l'institution. Un
observatoire limité à la seule Ville produirait mécaniquement une imputation fausse : il
montrerait des dépenses en baisse là où il n'y a eu qu'un transfert de compétence en 2018,
et demanderait au maire des comptes sur ce qu'il ne décide pas. Voir
[13_SPHERES_DE_COMPETENCE](13_SPHERES_DE_COMPETENCE.md).

## Périmètre temporel

- **Ligne de base : 2014 → 2026.** Deux mandats d'Olivier Bianchi. C'est la période qui
  permet de dire « comment la ville est arrivée là ». Elle est encore incontestée
  aujourd'hui ; elle ne le restera pas.
- **Mandat observé : mars 2026 → 2032.** Julien Bony, élu en mars 2026.
- **Premier exercice civil complet : 2027.** Premières données statistiques
  correspondantes : **mi-2028**. Voir [11](11_LATENCE_ET_DEUX_HORLOGES.md).

Toutes les sources ne remontent pas à 2014. Les limites réelles, source par source, sont
dans [l'inventaire](10_INVENTAIRE_DES_SOURCES.md). Les cas les plus contraignants :
délinquance enregistrée (2016), couverture petite enfance (2017), logements vacants
LOVAC (2020), valeur ajoutée des collèges (2022).

## Ce que ce dépôt contient

- l'inventaire des sources publiques mobilisables pour le territoire ;
- les propriétés méthodologiques de ces sources : latence, granularité, profondeur,
  ruptures, volatilité, droits ;
- l'attribution des compétences institutionnelles par domaine ;
- la méthodologie de comparaison territoriale ;
- le registre des lacunes et des demandes d'accès.

## Ce que ce dépôt ne contient pas

- **aucun code** d'acquisition, de transformation ou de publication ;
- **aucune donnée acquise** auprès d'un producteur public ;
- **aucune évaluation** du mandat, ni classement, ni score d'acteur politique ;
- **aucune autorisation d'acquisition** : documenter une source n'est pas décider de la
  collecter.

## Frontière avec `project-iagora`

[`project-iagora`](https://github.com/ccoelhofize/project-iagora) est une **plateforme de
connaissance vérifiable**, conçue pour être réutilisable par d'autres collectivités, dont
la documentation est en anglais et dont le premier pilote porte sur Clermont-Ferrand.

La règle de partage est celle de la **généricité** :

| Nature | Dépôt | Exemple |
|---|---|---|
| Concept réutilisable par n'importe quelle collectivité | `project-iagora` | La notion de « rupture de série » comme enregistrement canonique |
| Fait territorial propre à Clermont-Ferrand | **ce dépôt** | Le fait que la rupture de 2018 est la création de Clermont Auvergne Métropole |
| Vocabulaire normatif du modèle de données | `project-iagora` | L'énumération des sphères de compétence |
| Attribution concrète d'un domaine à une sphère | **ce dépôt** | La culture relève de la Métropole à Clermont-Ferrand |
| Contrats exécutables, schémas, pipeline, interface | `project-iagora` | `contracts/v1/` |
| Inventaire analytique des sources d'un territoire | **ce dépôt** | Les 61 indicateurs |

### Risque assumé et son traitement

Cette séparation crée un **risque de dérive conceptuelle** : plusieurs constats de ce
dépôt ne sont pas territoriaux mais structurels — latence de publication, rupture de
série, sphère de compétence, volatilité des sources, registre de lacunes. Ils décrivent
des propriétés que toute collectivité française présente. S'ils restent ici, le modèle de
données de `project-iagora` reste aveugle à ces propriétés.

Traitement : le répertoire [`upstream/`](../upstream/README.md) tient la liste des
concepts candidats à une remontée vers `project-iagora`, avec le type d'artefact visé
(ADR, RFC, mise à jour de spécification) et l'état de la proposition. Ce dépôt est écrit
en français ; toute remontée devra être rédigée en anglais, conformément aux conventions
de `project-iagora`.

### Points de friction identifiés avec les décisions déjà acceptées

Deux constats de ce dépôt entrent en tension avec des décisions **déjà acceptées** dans
`project-iagora`. Ils sont signalés ici pour ne pas être découverts trop tard :

1. **Comparaison inter-territoriale.** ADR-0001 et le périmètre produit excluent
   explicitement la « comparaison avec d'autres villes ». La méthodologie du panel gelé
   est donc documentée ici comme travail futur, sans être proposée en amont tant qu'une
   révision de périmètre n'a pas été décidée. Voir [16](16_TERRITOIRES_DE_COMPARAISON.md).
2. **Capture périodique de sources volatiles.** RFC-0001 interdit, pour l'incrément
   courant, toute « collecte de source continue ou planifiée », et exige une décision
   ultérieure. Le constat de perte irréversible documenté en
   [14](14_VOLATILITE_DES_SOURCES.md) répond précisément à l'une des questions laissées
   ouvertes par ce RFC ; il ne le contredit pas, mais il ne peut pas être mis en œuvre
   sans cette décision.

## État actuel

Document de cadrage, en brouillon. Le périmètre territorial et temporel est stable ; la
frontière entre les deux dépôts est une proposition qui n'a pas encore été validée côté
`project-iagora`.

## Documents liés

- [10_INVENTAIRE_DES_SOURCES](10_INVENTAIRE_DES_SOURCES.md)
- [13_SPHERES_DE_COMPETENCE](13_SPHERES_DE_COMPETENCE.md)
- [16_TERRITOIRES_DE_COMPARAISON](16_TERRITOIRES_DE_COMPARAISON.md)
- [upstream/README](../upstream/README.md)
