# Concepts candidats à une remontée vers `project-iagora`

**Statut :** Brouillon
**Responsable :** Cinthia Coelho
**Dernière vérification :** 2026-08-18

## Objet

Ce dépôt est territorial et rédigé en français.
[`project-iagora`](https://github.com/ccoelhofize/project-iagora) est une plateforme
générique, rédigée en anglais, gouvernée par des décisions d'architecture formelles.

Plusieurs constats établis ici ne sont **pas territoriaux** : ils décrivent des propriétés
que présente toute collectivité française. S'ils restent uniquement ici, le modèle de
données de la plateforme reste aveugle à ces propriétés, et les deux dépôts divergent.

Ce fichier tient la liste de ces concepts, leur état, et l'artefact visé.

## Règle de partage

| Nature | Où | Exemple |
|---|---|---|
| Concept réutilisable par toute collectivité | `project-iagora` | La notion de rupture de série comme enregistrement canonique |
| Fait territorial clermontois | ici | La rupture de 2018 est la création de Clermont Auvergne Métropole |
| Vocabulaire normatif | `project-iagora` | L'énumération des sphères de compétence |
| Attribution concrète | ici | La culture relève de la Métropole |

Toute remontée doit être **rédigée en anglais**, suivre le gabarit d'ADR du dépôt cible,
et mettre à jour les index dans le même changement.

**Où se rédigent les remontées.** Elles sont écrites **ici**, dans ce répertoire, en
anglais et au format du dépôt cible. Elles ne sont pas poussées directement vers
`project-iagora` : c'est une décision humaine que de les y porter, et le processus de
décision de cette plateforme exige une proposition complète avant l'allocation d'un
numéro. Ce répertoire est donc une **zone de préparation**, pas une file d'attente
automatique.

## Candidats

### C1 — Latence de publication et continuité de série

**Artefact visé :** décision d'architecture (ADR)
**État :** à rédiger
**Source ici :** [11](../docs/11_LATENCE_ET_DEUX_HORLOGES.md), [12](../docs/12_RUPTURES_DE_SERIE.md)

Créerait deux enregistrements canoniques : un profil de latence par source (délai,
cadence du producteur, granularité temporelle) et une rupture de série. Poserait la règle
selon laquelle la fenêtre minimale d'évaluabilité se dérive de la latence des sources, et
qu'aucune comparaison ne franchit une rupture non résolue.

**Pourquoi c'est nécessaire :** le vocabulaire temporel de la plateforme est déjà riche
(temps de l'événement, de validité, de publication, d'acquisition, de traitement, date
d'observation) mais **la latence de publication n'y figure pas**, et le profil de source
ne décrit que la fréquence à laquelle la plateforme collecte, pas celle à laquelle le
producteur publie. Rien n'empêche donc aujourd'hui de construire un tableau de bord qui
présente comme actuelle une donnée vieille de trois ans, ni une courbe qui traverse
silencieusement 2018 ou 2023.

### C2 — Attribution de sphère de compétence

**Artefact visé :** ADR
**État :** à rédiger
**Source ici :** [13](../docs/13_SPHERES_DE_COMPETENCE.md)

Vocabulaire contrôlé des sphères, avec les valeurs `partagée` et `indéterminée`, et
obligation de déclarer la sphère compétente pour tout indicateur publié.

**Pourquoi c'est nécessaire :** la plateforme empêche déjà de **mélanger** des
institutions dans un même calcul, et fait de la compétence le premier critère d'autorité
d'une source. Mais rien n'exige de **déclarer** qui décide. Le seul champ exécutable
existant est figé sur un cas du pilote. Le risque est concret : une page de territoire
comportant un bloc « Culture » attribuerait implicitement à la Ville une politique
métropolitaine.

### C3 — Préservation des sources volatiles

**Artefact visé :** RFC, puis ADR
**État :** à rédiger — **le plus urgent**
**Source ici :** [14](../docs/14_VOLATILITE_DES_SOURCES.md)

Taxonomie de volatilité des sources, constat de perte irréversible, et options pour
concilier une capture périodique avec une admission validée par un humain : capture
planifiée vers la quarantaine, admission différée et groupée, rétention allongée, et
distinction nouvelle entre « capturé pour ne pas être perdu » et « admis comme preuve ».

**Pourquoi un RFC et non directement un ADR :** le sujet est large et n'est pas encore
réductible à un choix unique. Le RFC existant sur l'acquisition gouvernée interdit
explicitement toute collecte planifiée pour l'incrément courant et exige une décision
ultérieure — mais il laisse ouverte la question de savoir quelle preuve opérationnelle
déclencherait une telle proposition. **Le constat des ~70 % d'instantanés écrasants est
la réponse à cette question.** La contribution ne contredit pas ce RFC : elle referme
l'une de ses questions ouvertes.

### C4 — Registre des lacunes et des demandes d'accès

**Artefact visé :** ADR
**État :** à rédiger — peut attendre
**Source ici :** [17](../docs/17_REGISTRE_DES_LACUNES.md)

Entités « lacune de preuve » et « demande d'accès », avec le cycle légal complet
(demande, date, délai, réponse, silence, saisine) et l'indicateur de réactivité
administrative.

**Pourquoi cela peut attendre :** la discipline épistémique est déjà solidement établie
dans la plateforme — l'absence de preuve n'y vaut jamais preuve d'absence, une donnée
manquante n'est jamais un zéro — et l'inventaire du pilote tient déjà, en prose, une file
de priorité et un journal de recherches daté. Ce qui manque est la formalisation et
surtout le cycle de demande d'accès, totalement absent.

**Garde-fou à poser dès la conception :** l'indicateur de réactivité porte sur une
administration, jamais sur une personne, et ne doit jamais être agrégé dans un score
composite — la plateforme s'interdit explicitement le classement d'acteurs politiques.

### C5 — Inventaire de sources à l'échelle territoriale

**Artefact visé :** évolution de contrat (schéma de profils de sources)
**État :** bloqué par un verrou technique
**Source ici :** [10](../docs/10_INVENTAIRE_DES_SOURCES.md)

**Verrou identifié :** le schéma des profils de sources fixe le territoire à une valeur
constante — celle de Clermont-Ferrand — et l'énumération des fréquences d'acquisition ne
contient aucune valeur périodique. Le contrat est donc **littéralement incapable**
d'exprimer une source d'une autre échelle territoriale, qu'il s'agisse de la Métropole ou
d'un producteur national.

C'est le verrou unique qui bloque simultanément C2, C3, C5 et la comparaison territoriale.
Il doit être levé avant que tout inventaire hors périmètre du pilote devienne exécutable.

### C6 — Plafond juridique : absence de vote nominal

**Artefact visé :** mise à jour de spécification (périmètre exclu)
**État :** à rédiger — court, et à ne pas différer
**Source ici :** [15](../docs/15_SOURCES_DES_DECISIONS_MUNICIPALES.md)

Enregistrer que le vote au conseil municipal français se fait à main levée, que seul le
résultat agrégé est publié, et qu'aucune vue ne peut donc suggérer une responsabilité
individuelle dans un vote de conseil.

**Pourquoi ne pas différer :** c'est une contrainte sur le **produit**, pas sur la source.
Sans elle, il est seulement question de temps avant que quelqu'un conçoive une vue qui la
présuppose.

## Non candidat

**La comparaison inter-territoriale** n'est pas dans cette liste. Elle est explicitement
exclue du périmètre accepté de la plateforme. La méthodologie est enregistrée en
[16](../docs/16_TERRITOIRES_DE_COMPARAISON.md) et attend une révision de périmètre
décidée séparément — la proposer aujourd'hui reviendrait à contredire deux décisions
acceptées.

## Ordre suggéré

1. **C3** — le seul dont le coût de report est irréversible.
2. **C5** — verrou technique bloquant plusieurs autres.
3. **C1** et **C2** — fondations méthodologiques, un ADR chacun.
4. **C6** — court, à glisser dans le premier changement utile.
5. **C4** — quand le registre de lacunes aura fait ses preuves en prose.

Un artefact par pull request : le processus de décision de la plateforme est par décision,
et le relecteur est unique.
