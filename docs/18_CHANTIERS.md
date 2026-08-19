# Les six chantiers

**Statut :** Brouillon
**Responsable :** Cinthia Coelho
**Dernière vérification :** 2026-08-19

## Objet

Le plan de travail de fond, par ordre de priorité. Chaque chantier dit **pourquoi il
existe**, **ce qu'il produit**, et **ce qui se passe si on l'ajourne**.

Ces six chantiers avaient d'abord été conçus comme des propositions à porter vers une
plateforme externe. Cette plateforme étant archivée, ils deviennent le travail de ce
dépôt — ce qui les simplifie : plus de procédure d'acceptation à respecter, plus de
périmètre hérité à contourner.

---

## Chantier 1 — La copie datée

**Priorité : la plus haute. C'est le seul dont le coût d'ajournement est irréversible.**

**Pourquoi.** Environ 70 % des jeux de données ouverts locaux écrasent leur propre
historique. Chaque jour sans copie est un jour définitivement perdu. Voir
[14_VOLATILITE_DES_SOURCES](14_VOLATILITE_DES_SOURCES.md).

**Produit.** Un collecteur qui, à cadence fixe, télécharge 15 à 20 jeux de données et
en conserve chaque version, avec empreinte de contenu et horodatage de capture.

**Si on l'ajourne.** On ne rattrape rien. Une décision d'architecture se reprend six mois
plus tard ; six mois de série non capturée n'existeront jamais.

**Préalable :** le chantier dépend de l'énumération complète du catalogue local.

---

## Chantier 2 — Le socle de données

**Pourquoi.** Aujourd'hui, la latence de publication, les ruptures de série et les sphères
de compétence n'existent que sous forme de prose. Un graphique ne peut pas interroger de
la prose. Tant que ces notions ne sont pas structurées, rien n'empêche une courbe de
traverser 2018 ou 2023 en silence.

**Produit.** Un modèle de données et des contrôles automatiques portant au minimum sur :

| Objet | Ce qu'il porte |
|---|---|
| `source` | producteur, URL, licence, granularité, **latence de publication**, **cadence du producteur**, **classe de volatilité** |
| `capture` | date de capture, empreinte du contenu, source d'origine |
| `indicateur` | définition, unité, formule, **sphère de compétence**, limites connues |
| `observation` | valeur, territoire, **année de référence**, **année de publication**, source, capture |
| `rupture` | indicateur ou famille concernée, date, nature, effet sur la comparaison |
| `territoire` | Clermont-Ferrand, Métropole, villes du panel, QPV |
| `lacune` | ce qui manque, la recherche effectuée, la demande, la réponse |

**Règles à rendre automatiques.** Une observation sans source et sans capture est refusée.
Une série qui traverse une rupture non déclarée est refusée. Une valeur absente ne peut
pas être convertie en zéro. Un total ne peut pas agréger des territoires dont certaines
valeurs sont supprimées par le secret statistique.

**Si on l'ajourne.** Les règles restent des intentions. Elles seront violées de bonne foi,
et personne ne s'en apercevra avant qu'un lecteur extérieur ne le fasse.

---

## Chantier 3 — Le panel de comparaison

**Pourquoi.** Un indicateur sans comparaison ne permet aucun jugement honnête. Voir
[16_TERRITOIRES_DE_COMPARAISON](16_TERRITOIRES_DE_COMPARAISON.md).

**Produit.** Une liste de 10 à 12 villes-centres, ses critères de sélection publiés, une
date de gel, et le contrôle de comparabilité institutionnelle pour chacune.

**Si on l'ajourne.** Le panel finira par être choisi au moment où un chiffre pose
problème — c'est-à-dire au pire moment possible pour la crédibilité.

---

## Chantier 4 — Les demandes d'accès

**Pourquoi.** Six lacunes dures ne se combleront pas toutes seules, et trois d'entre elles
portent sur des données qui **existent déjà** côté administration. Voir
[17_REGISTRE_DES_LACUNES](17_REGISTRE_DES_LACUNES.md).

**Produit.** Trois demandes écrites — restauration scolaire, subventions de la Ville,
données de la lecture publique — et le registre qui suit leur sort.

**Si on l'ajourne.** Les délais légaux courent à partir de la demande. Chaque mois de
retard est un mois de retard sur la réponse, et les délais réels dépassent souvent le
délai légal.

---

## Chantier 5 — Le suivi des décisions

**Pourquoi.** C'est la seule horloge qui tourne vite, et le mandat vient de commencer :
le corpus à reprendre est encore minuscule. Voir
[15_SOURCES_DES_DECISIONS_MUNICIPALES](15_SOURCES_DES_DECISIONS_MUNICIPALES.md).

**Produit.** Un suivi des séances du conseil municipal et du conseil métropolitain :
calendrier, liste des délibérations — **y compris celles qui ont été refusées** —,
documents justificatifs.

**Attention à la dérive.** Ce chantier est celui qui peut faire dérailler le projet vers un
catalogue d'actes administratifs. La délibération est une **preuve**, pas un contenu. Si
une délibération ne se rattache à aucune question que se pose un habitant, elle est
archivée sans être mise en avant.

**Préalable :** établir la date réelle du jeu de données des délibérations.

---

## Chantier 6 — La traduction

**Pourquoi.** Un observatoire que seuls des spécialistes comprennent a échoué, quelle que
soit la qualité de ses données. Ce risque n'est pas théorique : **les documents de ce
dépôt sont eux-mêmes écrits dans une langue technique.** Ils sont faits pour ça, mais rien
n'empêche aujourd'hui ce vocabulaire de passer tel quel dans l'interface.

**Produit.** Un glossaire à deux colonnes : la notion telle qu'elle est utilisée ici, et
la façon de la dire à quelqu'un qui n'a jamais ouvert un budget communal. Par exemple :

| Ici | Sur le site |
|---|---|
| Latence de publication | « Ce chiffre décrit 2023, il a été publié en 2026 » |
| Rupture de série | « Avant et après cette date, on ne compte pas la même chose » |
| Sphère de compétence | « Qui décide : la Ville, la Métropole, ou l'État » |
| Épargne brute | « Ce qui reste à la ville une fois payées ses dépenses courantes » |
| Capacité de désendettement | « Combien d'années il faudrait pour rembourser la dette » |

**Règle.** Aucune notion technique n'apparaît dans l'interface sans sa traduction. Le mot
technique peut rester, en second, pour qui veut vérifier — jamais en premier.

**Si on l'ajourne.** C'est précisément ce qui a fait échouer la tentative précédente. Une
fois le vocabulaire installé dans l'interface, on ne le retire plus : il faut tout
réécrire.

---

## Ordre recommandé

1. **Chantier 1** — irréversible.
2. **Chantier 2** — conditionne la justesse de tout ce qui sera publié.
3. **Chantier 4** — les délais courent à partir de la demande.
4. **Chantier 3** — avant la première publication chiffrée.
5. **Chantier 6** — avant la première maquette d'interface.
6. **Chantier 5** — dès que le préalable est levé.

## État actuel

Aucun chantier n'est commencé. Les trois vérifications préalables sont ouvertes en issues.

## Documents liés

- [14_VOLATILITE_DES_SOURCES](14_VOLATILITE_DES_SOURCES.md)
- [16_TERRITOIRES_DE_COMPARAISON](16_TERRITOIRES_DE_COMPARAISON.md)
- [17_REGISTRE_DES_LACUNES](17_REGISTRE_DES_LACUNES.md)
- [99_INDEX](99_INDEX.md)
