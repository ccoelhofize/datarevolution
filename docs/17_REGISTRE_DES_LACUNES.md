# Registre des lacunes et des demandes d'accès

**Statut :** Brouillon
**Responsable :** Cinthia Coelho
**Dernière vérification :** 2026-08-18
**Date d'observation :** 2026-08-18

## Objet

Documenter ce qui **devrait exister et n'existe pas**, la demande d'accès formulée, et le
délai de réponse obtenu.

Ce registre transforme le principal handicap de l'observatoire — les trous de données — en
contenu public, et il le protège : on ne peut pas reprocher de dissimuler à qui publie ce
qu'il ne sait pas.

## Principe

> **L'absence de preuve n'est pas la preuve d'une absence.**
> Une donnée manquante n'est jamais un zéro, jamais un « non fait », jamais une
> présomption. Elle est enregistrée comme lacune, avec la recherche effectuée et sa date.

Distinguer systématiquement : `connu` · `inconnu` · `absent` · `sans objet` · `restreint`
· `contradictoire` · `non vérifiable`.

Cas particulier à ne jamais confondre avec un zéro : dans les bases de délinquance
enregistrée, les valeurs supprimées par le secret statistique. La règle de diffusion
limite aux communes ayant enregistré plus de cinq faits pendant trois années successives.
Une cellule absente ne signifie pas « aucun fait ». Elle interdit aussi de sommer les
communes pour reconstituer un total métropolitain.

## Lacunes constatées

| Lacune | Sphère | Situation | Action |
|---|---|---|---|
| **Restauration scolaire et périscolaire** — repas servis, fréquentation de la cantine, tarifs par quotient familial, effectifs ALSH | `ville` | **Aucune donnée ouverte nationale.** Compétence la plus directe, la plus coûteuse et la plus visible de la commune sur les écoles — et invisible | Demande directe, puis CADA |
| **Subventions de la Ville aux associations, détail par bénéficiaire** | `ville` | Le décret n° 2017-779 impose la publication des subventions ≥ 23 000 € depuis 2017. La Métropole publie ; **la Ville ne semble pas publier** | Demande appuyée sur la base légale ; couvrirait d'un coup culture, sport et vie associative |
| **Activité de la lecture publique 2014-2025** — prêts, inscrits, fréquentation, horaires, budget d'acquisition | `metropole` | Série impossible en données ouvertes : le millésime courant écrase le précédent et les synthèses ont des trous. **Mais les données existent** : la Métropole remplit le formulaire ministériel chaque année | Demande des données brutes transmises |
| **Fréquentation du réseau de transport** — voyages par an | `metropole` | Aucune série ouverte. L'offre est publiée, l'usage ne l'est pas | Rapport annuel du délégataire, document communicable |
| **Vidéoprotection** — nombre de caméras, coût, année de mise en service | `ville` | Aucune base nationale fiable | Reconstitution par délibérations et lignes budgétaires, puis demande |
| **Émissions de gaz à effet de serre du territoire** | `metropole` | Le bilan de la Ville s'arrête en 2021 ; l'inventaire territorial existe institutionnellement mais son accès ouvert n'est pas confirmé | Vérifier auprès de l'observatoire régional |
| **Structure de la dette** — taux fixe ou variable, classification, durée résiduelle, prêteurs | `ville` | Uniquement en annexe PDF du compte administratif | Extraction manuelle ou demande |
| **Détail des subventions de la Ville par bénéficiaire avant 2020** | `ville` | Le total est disponible par le compte 6574 ; le détail n'existe qu'en PDF | À arbitrer selon l'effort |
| **Justice à l'échelle communale** | `etat` | **Structurellement impossible** : le ressort du tribunal dépasse largement la commune | Aucune. À documenter comme impossibilité, pas comme lacune |

## Structure d'un enregistrement

Chaque lacune devrait porter, à terme :

| Champ | Contenu |
|---|---|
| `objet` | Ce qui devrait exister |
| `pourquoi` | À quelle question de l'observatoire cela répond |
| `sphere` | Sphère compétente ([13](13_SPHERES_DE_COMPETENCE.md)) |
| `base_legale` | Texte fondant l'obligation de publication, s'il existe |
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
   ses limites.

Sans ces garde-fous, il glisserait vers le classement d'acteurs — que ce projet s'interdit.

## Procédure de demande

1. Demande écrite et datée, adressée à l'autorité compétente, avec accusé de réception.
2. **Un mois** de délai de réponse ; le silence vaut refus.
3. Saisine de la CADA dans les **deux mois** suivant le refus — **jamais avant**
   l'expiration du délai d'un mois, sous peine d'irrecevabilité.
4. Avis de la CADA, puis suite donnée par l'administration.
5. En dernier recours, tribunal administratif — la saisine de la CADA étant un préalable
   obligatoire.

Chaque étape est enregistrée. Le processus lui-même est une donnée publique.

## Ce qui reste à établir

- Rédiger les trois premières demandes : restauration scolaire, subventions de la Ville,
  données brutes de la lecture publique.
- Décider du niveau de publicité du registre : public dès la première demande, ou publié
  après réponse.
- Formaliser l'enregistrement en format structuré.

## État actuel

Brouillon. Aucune demande n'a encore été déposée. Les lacunes listées proviennent du
relevé du 18 août 2026.

## Documents liés

- [10_INVENTAIRE_DES_SOURCES](10_INVENTAIRE_DES_SOURCES.md)
- [13_SPHERES_DE_COMPETENCE](13_SPHERES_DE_COMPETENCE.md)
- [15_SOURCES_DES_DECISIONS_MUNICIPALES](15_SOURCES_DES_DECISIONS_MUNICIPALES.md)
