# Sources des décisions municipales

**Statut :** Brouillon
**Responsable :** Cinthia Coelho
**Dernière vérification :** 2026-08-18
**Date d'observation :** 2026-08-18

## Objet

Cartographier l'accès aux décisions du conseil municipal et du conseil métropolitain :
classes de documents, latences réelles, cadre juridique, et limites structurelles.

C'est la matière première de l'horloge rapide décrite en
[11](11_LATENCE_ET_DEUX_HORLOGES.md), et la source des documents probants d'un suivi
d'engagements.

## Classes de documents et latences

| Classe | Latence | Nature | Rôle |
|---|---|---|---|
| **Vidéo de séance** | le jour même | Diffusion publique en direct, chaîne officielle | Source la plus rapide ; transcription automatique possible sous 24 h |
| **Liste des délibérations** | 1 semaine | Obligation légale | Ancrage juridique rapide ; **inclut les délibérations refusées** |
| **Recueil des actes / PDF de séance** | 2 à 6 semaines | Document unique agrégeant la séance | Lest probatoire ; exige très probablement une reconnaissance optique de caractères |
| **Procès-verbal** | 6 à 9 semaines | Débats, déclarations, interventions | Le plus riche et structurellement le plus lent |
| **Jeu de données ouvert des délibérations** | annuelle | Format normalisé, API | Modèle de données et réconciliation rétroactive |

### Le contre-intuitif

Le jeu de données ouvert paraît être la solution évidente. Il ne l'est pas : sa fréquence
déclarée est **annuelle** et sa couverture déclarée s'arrête en **septembre 2024**. Un
observatoire construit dessus naîtrait avec deux ans de retard.

L'ordre d'utilité réel est donc inversé : **vidéo → liste → recueil → procès-verbal**, le
jeu de données servant de modèle de données et de réconciliation, pas de source primaire.

> **Vérification bloquante.** Télécharger le fichier du jeu de données et lire la date
> maximale réelle, ainsi que les champs de vote et d'URL effectivement renseignés. Cette
> seule vérification décide de toute l'architecture du pipeline. Tant qu'elle n'est pas
> faite, le reste de ce document reste une hypothèse de travail.

## Cadre juridique

### Publication des actes

Depuis le 1er juillet 2022 (ordonnance n° 2021-1310 et décret n° 2021-1311), les actes
réglementaires et les actes ni réglementaires ni individuels des communes et de leurs
groupements doivent être **publiés sous forme électronique** sur le site institutionnel.

**Conséquence structurelle :** les **décisions individuelles** — nominations, subventions
nominatives, autorisations individuelles — sont seulement notifiées aux intéressés et
n'ont **pas d'obligation de publication**. Un suivi d'engagements qui dépendrait d'actes
individuels aura donc des trous **légitimes et irréparables** par la seule collecte
automatique.

### Liste des délibérations

Le compte rendu de séance a été supprimé au 1er juillet 2022 et remplacé par la **liste
des délibérations** (art. L2121-25 CGCT) : date de la séance et objet de l'ensemble des
délibérations **approuvées ou refusées**, publiée **dans un délai d'une semaine**.

Le fait que les délibérations **refusées** y figurent est décisif : c'est la seule voie
permettant d'observer ce que le conseil a rejeté. Un engagement rejeté en conseil est une
information au moins aussi forte qu'un engagement adopté. Attention : le jeu de données
ouvert s'intitule « délibérations **votées** » — il pourrait donc omettre les refusées.

### Procès-verbal

Art. L2121-15 CGCT : le procès-verbal est publié sous forme électronique, de manière
permanente et gratuite, **dans la semaine qui suit la séance au cours de laquelle il a été
arrêté**. Or cette séance est la **suivante**, pas celle des faits. D'où la latence réelle
de 6 à 9 semaines.

### Droit d'accès

Les délibérations, procès-verbaux, budgets et comptes sont des documents administratifs
communicables. En cas de non-publication : demande écrite et datée, **un mois** de délai
de réponse, silence valant refus, puis saisine de la CADA dans les deux mois.

> **Piège procédural :** une saisine de la CADA formée **avant** l'expiration du délai
> d'un mois est irrecevable. La saisine de la CADA est par ailleurs un préalable
> obligatoire à tout recours contentieux en matière d'accès.

Voir [17_REGISTRE_DES_LACUNES](17_REGISTRE_DES_LACUNES.md).

## Limite structurelle : pas de vote nominal

**Il n'existe pas de vote nominal individuel au conseil municipal français.** Le scrutin
ordinaire se fait à main levée et seul le **résultat agrégé** figure au procès-verbal. Le
scrutin public, avec inscription nominative, n'a lieu qu'à la demande d'un quart des
membres présents et reste exceptionnel. Le scrutin secret, obligatoire pour les
nominations, est par nature non nominal.

**Ce que l'observatoire peut donc construire :**

- le résultat agrégé par délibération, lorsqu'il est publié ;
- la position d'un **groupe politique**, souvent déclarée oralement en séance et donc
  saisissable par la vidéo ou le procès-verbal, jamais par une donnée structurée ;
- les déclarations et interventions, qui pour un suivi d'engagements sont fréquemment plus
  utiles que le vote lui-même — c'est en délibération que la promesse devient budget et
  contrat.

**Ce qu'il ne peut pas construire :** qui a voté quoi, individuellement. Ce n'est pas une
limite de Clermont-Ferrand, c'est une limite du droit français. Aucune vue du produit ne
doit suggérer une responsabilité individuelle dans un vote de conseil.

## Cadence des séances

Environ **6 à 8 séances par an** pour chaque assemblée, à intervalle de 6 à 8 semaines,
avec une interruption estivale. Séances budgétaires concentrées en décembre (budget
primitif) et au premier semestre (compte administratif, puis compte financier unique).

Le mandat Bony a débuté par le conseil d'installation de mars 2026 ; la première séance
substantielle est celle du **23 avril 2026**. Le corpus du mandat est donc encore très
court — ce qui est une chance : l'observatoire peut démarrer au commencement exact du
mandat, sans dette de reprise historique. Cette fenêtre ne se représentera pas.

## Charge de travail estimée

| Situation | Heures / mois |
|---|---|
| Mois sans séance (environ 5 par an) | 1 à 2 |
| Mois avec une séance | 6 à 10 |
| Mois avec Ville et Métropole | 10 à 14 |
| Mois budgétaire | 15 à 20 |

**Moyenne annuelle réaliste : 6 à 9 heures par mois**, plus 2 à 4 heures de maintenance
corrective pendant les six premiers mois. Le goulot du projet n'est pas le code.

## Ce qui reste à établir

- La vérification bloquante ci-dessus.
- Inspecter manuellement les pages de publication : le site de la Ville n'a pas pu être
  lu automatiquement lors du relevé (échec de validation TLS lors de la lecture du
  `robots.txt`), et la recherche de délibérations de la Métropole est une application
  JavaScript. Les motifs d'URL des documents doivent être relevés à la main avant
  d'écrire quoi que ce soit.
- Confirmer si la Ville publie le résultat de vote agrégé, et sous quelle forme.
- Évaluer la qualité des PDF : natifs ou numérisés, et donc besoin réel de reconnaissance
  optique.

## État actuel

Brouillon. Le cadre juridique est vérifié et sourcé. Les latences des documents publiés
par la Ville sont estimées par analogie et **non vérifiées** sur Clermont-Ferrand.

## Documents liés

- [11_LATENCE_ET_DEUX_HORLOGES](11_LATENCE_ET_DEUX_HORLOGES.md)
- [17_REGISTRE_DES_LACUNES](17_REGISTRE_DES_LACUNES.md)
- [10_INVENTAIRE_DES_SOURCES](10_INVENTAIRE_DES_SOURCES.md)
