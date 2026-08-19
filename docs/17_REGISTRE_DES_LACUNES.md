# Registre des lacunes et des demandes d'accès

**Statut :** Brouillon
**Responsable :** Cinthia Coelho
**Dernière vérification :** 2026-08-19
**Date d'observation :** 2026-08-18

## Objet

Documenter ce qui **devrait exister et n'a pas été trouvé**, la demande d'accès formulée,
et le délai de réponse obtenu.

Ce registre transforme le principal handicap de l'observatoire — les trous de données — en
contenu public, et il le protège : on ne peut pas reprocher de dissimuler à qui publie ce
qu'il ne sait pas.

## Principe

> **L'absence de preuve n'est pas la preuve d'une absence.**
> Une donnée manquante n'est jamais un zéro, jamais un « non fait », jamais une
> présomption. Elle est enregistrée comme lacune, avec la recherche effectuée et sa date.

**Ce principe vaut aussi pour l'administration elle-même.** Ne pas avoir trouvé un
document n'établit pas qu'il n'existe pas, encore moins qu'une obligation n'a pas été
respectée. Un constat de non-conformité ne peut être formulé qu'après une demande restée
sans réponse ou explicitement refusée. **Avant la demande, on écrit ce qu'on a cherché et
ce qu'on n'a pas trouvé — rien de plus.**

Distinguer systématiquement : `connu` · `inconnu` · `absent` · `sans objet` · `restreint`
· `contradictoire` · `non vérifiable`.

Cas particulier à ne jamais confondre avec un zéro : dans les bases de délinquance
enregistrée, les valeurs supprimées par le secret statistique. La règle de diffusion
limite aux communes ayant enregistré plus de cinq faits pendant trois années successives.
Une cellule absente ne signifie pas « aucun fait ». Elle interdit aussi de sommer les
communes pour reconstituer un total métropolitain.

## Lacunes constatées

Toutes datent du relevé du **18 août 2026**. Aucune demande d'accès n'a encore été
déposée ; le statut de chacune est donc `constatee`.

| Lacune | Sphère | Ce qui a été cherché, et non trouvé | Action prévue |
|---|---|---|---|
| **Restauration scolaire et périscolaire** — repas servis, fréquentation de la cantine, tarifs par quotient familial, effectifs ALSH | `ville` | Aucune source ouverte nationale n'a été identifiée sur ce thème. Compétence parmi les plus directes et les plus coûteuses de la commune sur les écoles | Demande directe à la Ville |
| **Subventions de la Ville aux associations, détail par bénéficiaire** | `ville` | Recherche sur les portails open data local et national : aucun jeu de données de subventions de la Ville trouvé au 18 août 2026. La Métropole publie les siennes au-delà de 23 000 €. Le total communal reste accessible par le compte 6574 des balances comptables, sans détail | Demande à la Ville, en citant le décret n° 2017-779 comme fondement du droit à communication. **Aucun constat de conformité ou de non-conformité n'est formulé avant la réponse** |
| **Activité de la lecture publique 2014-2025** — prêts, inscrits, fréquentation, horaires, budget d'acquisition | `metropole` | Le jeu ouvert national n'expose que le millésime courant et les synthèses publiées ont des années manquantes. **Les données existent** : le réseau renseigne l'enquête ministérielle chaque année | Demande des données transmises à l'enquête |
| **Fréquentation du réseau de transport** — voyages par an | `metropole` | Aucune série ouverte trouvée. L'offre est publiée, l'usage ne l'est pas | Rapport annuel du délégataire, document communicable |
| **Vidéoprotection** — nombre de caméras, coût, année de mise en service | `ville` | Aucune base nationale fiable ; le seul jeu ouvert trouvé est un travail individuel arrêté en 2014 | Reconstitution par délibérations et lignes budgétaires, puis demande |
| **Émissions de gaz à effet de serre du territoire** | `metropole` | Le bilan de la Ville s'arrête en 2021. Un inventaire territorial existe dans le cadre du plan climat, son accès ouvert n'a pas été confirmé | Vérifier auprès de l'observatoire régional |
| **Structure de la dette** — taux fixe ou variable, classification, durée résiduelle, prêteurs | `ville` | Présente uniquement en annexe PDF du compte administratif | Extraction manuelle ou demande |
| **Justice à l'échelle communale** | `etat` | **Impossible par construction** : le ressort du tribunal dépasse largement la commune | Aucune. À documenter comme impossibilité, pas comme lacune |

## Structure d'un enregistrement

| Champ | Contenu |
|---|---|
| `objet` | Ce qui devrait exister |
| `pourquoi` | À quelle question de l'observatoire cela répond |
| `sphere` | Sphère compétente ([13](13_SPHERES_DE_COMPETENCE.md)) |
| `base_legale` | Texte fondant le droit à communication, s'il existe |
| `recherche_effectuee` | Ce qui a été cherché, où, et à quelle date |
| `statut` | `constatee` · `demandee` · `repondue` · `refusee` · `silence` · `cada_saisie` · `impossible` |
| `date_demande` / `date_reponse` | Pour mesurer le délai réel |
| `resultat` | Document obtenu, refus motivé, ou silence |

## Indicateur de réactivité administrative

Le registre produit un sous-produit inattendu : le **délai de réponse de l'administration
aux demandes d'accès**, avec un dénominateur propre — ce qui est rare parmi les indicateurs
de cet observatoire.

Trois garde-fous à poser dès la conception :

1. l'indicateur porte sur une **administration**, jamais sur une personne ;
2. il n'est pas agrégé dans un score composite ni dans un classement d'acteur politique ;
3. sa définition est versionnée comme n'importe quel autre indicateur, avec sa méthode et
   ses limites, et le nombre de demandes est publié en même temps que le délai — un délai
   moyen calculé sur trois demandes ne veut rien dire.

## Procédure de demande

1. Demande écrite et datée, adressée à l'autorité compétente, avec accusé de réception.
2. **Un mois** de délai de réponse ; le silence vaut refus.
3. Saisine de la CADA dans les **deux mois** suivant le refus — **jamais avant**
   l'expiration du délai d'un mois, sous peine d'irrecevabilité.
4. Avis de la CADA, puis suite donnée par l'administration.
5. En dernier recours, tribunal administratif — la saisine de la CADA étant un préalable
   obligatoire.

Chaque étape est enregistrée. Le processus lui-même est une donnée publique.

**Ton des demandes.** Une demande d'accès est un droit, pas un reproche. Elle est rédigée
comme telle. Un observatoire qui ouvre le dialogue par une accusation obtient moins de
documents, et les obtient plus tard.

## Ce qui reste à établir

- Rédiger les trois premières demandes : restauration scolaire, subventions de la Ville,
  données de la lecture publique.
- Décider du niveau de publicité du registre : public dès la demande, ou après réponse.
- Formaliser l'enregistrement en format structuré.

## État actuel

Brouillon. Aucune demande déposée. Toutes les lacunes sont au statut `constatee` et
proviennent du relevé du 18 août 2026.

## Documents liés

- [10_INVENTAIRE_DES_SOURCES](10_INVENTAIRE_DES_SOURCES.md)
- [13_SPHERES_DE_COMPETENCE](13_SPHERES_DE_COMPETENCE.md)
- [15_SOURCES_DES_DECISIONS_MUNICIPALES](15_SOURCES_DES_DECISIONS_MUNICIPALES.md)
