# Volatilité des sources et perte irréversible

**Statut :** Brouillon
**Responsable :** Cinthia Coelho
**Dernière vérification :** 2026-08-19
**Date d'observation :** 2026-08-18

## Objet

Classer les sources selon ce qu'elles font de leur propre passé, et établir lesquelles
détruisent de l'information si personne ne les capture.

C'est le seul chapitre de ce dépôt dont le coût de report est **irréversible**. Une
décision d'architecture peut être reprise dans six mois ; six mois de série non capturée
n'existeront jamais.

## Classes de volatilité

| Classe | Définition | Conséquence |
|---|---|---|
| `serie_publiee` | Le producteur publie et conserve l'historique | Rien à faire, on collecte quand on veut |
| `millesime_ecrasant` | Un millésime remplace le précédent au même emplacement | Chaque millésime non capturé est perdu |
| `fenetre_glissante` | Seules les N dernières périodes sont exposées | Perte progressive et silencieuse |
| `instantane_courant` | Photographie de l'état présent, sans version | Le changement est le signal, et il est invisible |
| `temps_reel_sans_retention` | Rafraîchi en continu, écrasé à chaque fois | Valeur historique nulle sans capture |
| `registre_vivant` | Registre corrigé rétroactivement | Une correction est indistinguable d'un fait nouveau |

## Constat sur le territoire clermontois

Environ **70 % du catalogue open data local** relèvent de `instantane_courant` ou de
`temps_reel_sans_retention`. Sur les 125 jeux de données recensés, à peine une quinzaine
constituent de véritables séries temporelles. **La collectivité elle-même ne conserve pas
l'historique de ses propres données ouvertes.**

Ce n'est pas une critique : ce n'est pas la fonction d'un portail open data. Mais cela
signifie qu'aujourd'hui, à Clermont-Ferrand, **personne ne garde**. Ni la collectivité, ni
la presse locale, ni l'opposition.

C'est aussi, pour l'observatoire, la position la plus solide qui soit : celui qui devient
le seul endroit où le territoire se souvient de lui-même n'a pas besoin d'avoir raison
contre quelqu'un.

## Sources prioritaires à préserver

Par ordre d'urgence décroissante.

### Perte quotidienne en cours

| Source | Classe | Cadence | Pourquoi |
|---|---|---|---|
| Indice ATMO communal | `fenetre_glissante` | quotidienne | N'expose que 9 jours ; aucune source communale n'a d'historique de qualité de l'air |
| Agenda culturel de la Ville | `instantane_courant` | quotidienne | N'expose que les événements **à venir** ; le passé est effacé par construction |
| Occupation des parkings métropolitains | `temps_reel_sans_retention` | 15 minutes | Rafraîchi à la minute, sans rétention ; une série de pression automobile que personne n'a |
| Stations de vélos en libre-service | `temps_reel_sans_retention` | 15 minutes | Idem, usage cyclable |
| GTFS temps réel du réseau de transport | `temps_reel_sans_retention` | continue | L'archive publique ne remonte qu'à 2025 |

### Perte annuelle ou par millésime

| Source | Classe | Cadence | Pourquoi |
|---|---|---|---|
| Demandeurs d'emploi, données communales | `fenetre_glissante` | trimestrielle | Fenêtre glissante de 10 ans : 2014-2016 disparaîtra du jeu publié |
| Activité des bibliothèques | `millesime_ecrasant` | annuelle | Le millésime courant remplace le précédent ; les synthèses PDF ont des trous |
| Recensement des équipements sportifs | `registre_vivant` | annuelle | Aucun millésime publié ; une correction rétroactive est indistinguable d'un équipement neuf |
| Annuaire de l'éducation | `registre_vivant` | mensuelle | Registre vivant sans historique |
| Base Muséofile | `registre_vivant` | annuelle | Idem |

### Instantanés dont le changement est le signal

Parcs et jardins, secteurs scolaires, structures petite enfance, salles associatives,
équipements sportifs municipaux, îlots de fraîcheur, périmètre de la ZFE, tronçons à 30 et
50 km/h. Cadence mensuelle ou trimestrielle suffisante. Ce qui compte n'est pas la valeur,
c'est la **différence** entre deux captures.

**Total sous surveillance : 15 à 20 jeux de données. Pas 125.** Archiver l'ensemble du
catalogue serait du gaspillage : la liste des cimetières ne change pas.

## Exigences d'une préservation correcte

1. **Ajout seul.** Une capture n'écrase jamais la précédente.
2. **Empreinte de contenu.** Enregistrer un hachage du contenu à chaque capture, pour
   distinguer « la donnée a changé » de « le portail a republié le même fichier ». Les
   portails réécrivent leurs horodatages lors des réindexations ; sans empreinte, le
   journal est saturé de faux changements.
3. **Horodatage de capture** distinct de la date de publication déclarée par la source.
4. **Séparer préserver et publier.** Capturer pour ne pas perdre n'est ni publier, ni
   valider, ni tenir pour vrai. Une copie datée est une pièce d'archive ; elle ne devient
   une donnée de l'observatoire qu'après vérification humaine.

## Garde-fous

Une capture automatique répétée pendant six ans peut déraper de deux façons : en devenant
une charge pour les serveurs publics, ou en accumulant une masse que personne ne relit.
Les règles suivantes s'appliquent à toute collecte.

1. **Cadence proportionnée à la source.** On ne capture pas plus souvent que la source ne
   change. Collecter chaque jour un jeu publié une fois par an n'apporte rien et coûte à
   tout le monde.
2. **Respect des conditions d'utilisation** du portail, et des règles d'accès
   automatisé qu'il publie. En cas de doute, on demande, on ne suppose pas.
3. **Identification.** Le collecteur s'annonce, avec un moyen de contact. Un observatoire
   citoyen n'a aucune raison de collecter anonymement.
4. **Limitation de débit et reprise douce.** Une erreur du serveur entraîne une attente
   croissante, jamais une nouvelle tentative immédiate.
5. **Aucune donnée personnelle.** Si une source en contient, elle n'entre pas dans
   l'archive en l'état ; la question est traitée avant la première capture, pas après.
6. **Le volume est surveillé.** Une estimation de la taille de l'archive à six ans est
   faite avant de choisir un support de stockage.
7. **Rien n'est publié automatiquement depuis l'archive.** La chaîne s'arrête à la copie
   datée ; le passage à la publication est une décision humaine.

## Ce qui reste à établir

- Fixer les cadences définitives par source.
- Estimer le volume de l'archive à six ans, puis choisir le support. Un dépôt versionné
  convient bien aux fichiers texte de petite taille ; il convient mal aux fichiers
  volumineux ou binaires.
- Lire les conditions d'utilisation des deux portails locaux et, si elles sont ambiguës,
  écrire au contact open data avant la première capture.
- Décider du sort des captures jamais relues : conservation indéfinie, ou purge après
  vérification groupée.

## État actuel

Brouillon. Le constat des ~70 % repose sur l'énumération d'environ 70 des 125 jeux de
données de l'organisation métropolitaine ; le catalogue maître doit être téléchargé pour
confirmation. **Aucune capture n'est aujourd'hui en place.**

## Documents liés

- [10_INVENTAIRE_DES_SOURCES](10_INVENTAIRE_DES_SOURCES.md)
- [11_LATENCE_ET_DEUX_HORLOGES](11_LATENCE_ET_DEUX_HORLOGES.md)
- [18_CHANTIERS](18_CHANTIERS.md)
