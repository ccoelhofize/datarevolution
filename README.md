# Observatoire de Clermont-Ferrand — base de connaissance territoriale

**Statut :** Brouillon
**Responsable :** Cinthia Coelho
**Dernière vérification :** 2026-08-18
**Langue de travail :** français

Ce dépôt documente **les sources de données publiques du territoire clermontois** et la
méthodologie permettant de les lire sans les faire mentir. Il ne contient ni site web, ni
pipeline, ni données acquises : il contient la connaissance nécessaire pour que ces
choses-là soient construites correctement.

Il accompagne le mandat municipal **2026-2032** et couvre le territoire de
**Clermont-Ferrand** (INSEE 63113) **et de Clermont Auvergne Métropole**.

## Pourquoi ce dépôt existe

Un observatoire citoyen échoue rarement par manque de données. Il échoue parce qu'il
compare des séries incomparables, parce qu'il impute à un maire des compétences qu'il
n'exerce pas, parce qu'il présente comme actuel un chiffre vieux de trois ans, ou parce
qu'il n'a pas conservé ce que les portails publics effacent.

Ce dépôt existe pour empêcher ces quatre erreurs. Il répond à quatre questions, source par
source :

1. **Quand ?** — quel délai sépare le fait de sa publication, et donc à partir de quelle
   date une évaluation est seulement possible ([11](docs/11_LATENCE_ET_DEUX_HORLOGES.md)).
2. **Qui décide ?** — quelle sphère institutionnelle exerce réellement la compétence
   mesurée ([13](docs/13_SPHERES_DE_COMPETENCE.md)).
3. **Est-ce comparable ?** — quelles ruptures méthodologiques interdisent de tracer une
   courbe continue ([12](docs/12_RUPTURES_DE_SERIE.md)).
4. **Que perd-on chaque jour ?** — quelles sources écrasent leur propre historique
   ([14](docs/14_VOLATILITE_DES_SOURCES.md)).

## Principes

1. **Une donnée sans date de référence et sans date de publication n'est pas une donnée.**
2. **Un chiffre sans sphère de compétence est une imputation, pas une information.**
3. **Aucune courbe ne traverse une rupture de série sans la signaler.**
4. **L'absence de preuve n'est pas la preuve d'une absence** — les lacunes sont
   enregistrées, pas comblées par inférence ([17](docs/17_REGISTRE_DES_LACUNES.md)).
5. **Ce qui n'est pas archivé est perdu.** Les instantanés volatils sont capturés avant
   d'être exploités.
6. **Ce dépôt documente l'action publique. Il ne fait pas campagne, ne classe pas les
   élus et ne prescrit pas de choix politique.**

## Ce que ce dépôt n'est pas

- Ce n'est pas une plateforme logicielle. L'implémentation vit dans
  [`project-iagora`](https://github.com/ccoelhofize/project-iagora) — voir
  [00_PERIMETRE.md](docs/00_PERIMETRE.md) pour la frontière exacte entre les deux dépôts.
- Ce n'est pas un entrepôt de données. Aucune valeur acquise auprès d'un producteur
  public n'est stockée ici.
- Ce n'est pas une évaluation du mandat. Aucune donnée statistique du mandat 2026-2032
  ne sera disponible avant **mi-2028** ; ce dépôt explique pourquoi et prépare le terrain.

## Carte des documents

| Document | Objet |
|---|---|
| [00_PERIMETRE](docs/00_PERIMETRE.md) | Périmètre territorial, temporel, et frontière avec `project-iagora` |
| [10_INVENTAIRE_DES_SOURCES](docs/10_INVENTAIRE_DES_SOURCES.md) | 61 indicateurs vérifiés : producteur, granularité, profondeur, délai, format, licence |
| [11_LATENCE_ET_DEUX_HORLOGES](docs/11_LATENCE_ET_DEUX_HORLOGES.md) | Délais de publication et fenêtre minimale d'évaluabilité |
| [12_RUPTURES_DE_SERIE](docs/12_RUPTURES_DE_SERIE.md) | Registre des discontinuités méthodologiques datées |
| [13_SPHERES_DE_COMPETENCE](docs/13_SPHERES_DE_COMPETENCE.md) | Vocabulaire des sphères et attribution par domaine |
| [14_VOLATILITE_DES_SOURCES](docs/14_VOLATILITE_DES_SOURCES.md) | Classes de volatilité et perte irréversible |
| [15_SOURCES_DES_DECISIONS_MUNICIPALES](docs/15_SOURCES_DES_DECISIONS_MUNICIPALES.md) | Accès aux délibérations : classes, latences, cadre juridique |
| [16_TERRITOIRES_DE_COMPARAISON](docs/16_TERRITOIRES_DE_COMPARAISON.md) | Strate DGFiP et panel gelé de villes-centres |
| [17_REGISTRE_DES_LACUNES](docs/17_REGISTRE_DES_LACUNES.md) | Ce qui manque, ce qui a été demandé, et en combien de temps on a répondu |
| [99_INDEX](docs/99_INDEX.md) | Index de navigation et état de chaque document |
| [upstream/](upstream/README.md) | Concepts candidats à une remontée vers `project-iagora` |
| [data/sources.csv](data/sources.csv) | L'inventaire en format structuré |

## Licence

Documentation originale : **CC BY 4.0** — voir [LICENSE.md](LICENSE.md).
Les données publiques citées conservent les droits de leurs producteurs (le plus souvent
Licence Ouverte 2.0 ou ODbL) ; ces droits sont indiqués source par source dans
l'inventaire.

## État actuel

Tous les documents sont en **brouillon**. Le relevé a été effectué le 18 août 2026 par
vérification directe des pages de chaque producteur. Les éléments marqués
« non vérifié » le sont réellement et ne doivent pas entrer en production sans contrôle.

Trois vérifications bloquantes restent à faire avant toute décision d'architecture :

1. la date maximale réelle du jeu de données des délibérations votées ;
2. la présence d'une classification fonctionnelle dans les balances comptables ;
3. l'énumération exhaustive du catalogue open data local (≈ 70 des 125 jeux recensés).
