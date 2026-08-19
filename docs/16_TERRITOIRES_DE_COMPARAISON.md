# Territoires de comparaison

**Statut :** Brouillon — méthodologie enregistrée, **mise en œuvre non autorisée**
**Responsable :** Cinthia Coelho
**Dernière vérification :** 2026-08-18
**Date d'observation :** 2026-08-18

## Objet

Établir la méthodologie de comparaison territoriale, et enregistrer le conflit de
périmètre qui en interdit aujourd'hui la mise en œuvre.

## Pourquoi la comparaison est indispensable

Un indicateur seul ne signifie rien. « Le taux de X a augmenté de 0,8 point » n'est ni une
bonne ni une mauvaise nouvelle tant qu'on ignore ce qu'ont fait les territoires
comparables. Si la moyenne des villes semblables a augmenté de 3,5 points, la même valeur
raconte l'histoire inverse.

C'est aussi le principal correctif au problème d'imputation traité en
[13_SPHERES_DE_COMPETENCE](13_SPHERES_DE_COMPETENCE.md) : la comparaison neutralise
partiellement les effets de conjoncture nationale, que le maire ne contrôle pas.

## Deux comparateurs, deux questions différentes

### A. Strate démographique de la DGFiP

Les comptes individuels des communes classent chaque commune dans l'un de **31 groupes de
référence**, définis par trois critères cumulatifs : tranche de population, appartenance à
un EPCI à fiscalité propre, et régime fiscal de cet EPCI. Les moyennes diffusées sont
**nationales**.

**Avantages :** officiel, citable, publié par le producteur lui-même, disponible pour
toutes les séries financières.

**Limite décisive :** la strate ne contrôle **pas** l'effet « ville-centre de métropole ».
Or la répartition des compétences entre la ville-centre et la métropole varie fortement
d'une métropole à l'autre. Comparer Clermont-Ferrand à une moyenne nationale de sa strate
mélange des villes qui ont transféré leur voirie et d'autres non.

Avertissement du producteur lui-même : les moyennes de strate masquent des situations et
des modes de gestion très divers ; elles servent à poser des questions, pas à juger.

### B. Panel de villes-centres, choisi et gelé

Puisque les données sont disponibles commune par commune pour l'ensemble des sources
nationales, il est possible de calculer la médiane et les quartiles d'un panel choisi.
C'est plus honnête et plus explicable qu'une moyenne opaque.

**Critères de sélection proposés** — à publier avec le panel :

1. commune-centre d'une métropole ou d'une communauté urbaine ;
2. population communale comprise entre 100 000 et 200 000 habitants ;
3. préfecture de département ;
4. présence universitaire significative ;
5. hors Île-de-France et hors les trois plus grandes villes du pays.

**Candidates identifiées :** Dijon, Grenoble, Angers, Le Mans, Nîmes, Brest, Tours,
Limoges, Metz, Besançon, Orléans, Rouen, Amiens, Caen. Retenir **10 à 12**.

## Règles méthodologiques

1. **Le panel est publié avec ses critères.** Un panel dont on ne connaît pas la règle de
   composition n'est pas un comparateur, c'est un argument.
2. **Le panel est gelé.** Le modifier ultérieurement pour appuyer une démonstration est
   l'accusation la plus facile à porter et la plus difficile à réfuter. Le gel est ce qui
   rend l'observatoire insensible à ce reproche.
3. **Un panel qui change de composition réintroduit une rupture de série sur l'axe
   territorial.** C'est exactement le mécanisme décrit en
   [12_RUPTURES_DE_SERIE](12_RUPTURES_DE_SERIE.md), appliqué à l'espace au lieu du temps.
   Si le panel doit évoluer, l'évolution est datée, motivée et traitée comme une rupture.
4. **Les deux comparateurs sont affichés côte à côte et nommés.** Le lecteur doit pouvoir
   distinguer « moyenne officielle de la strate » de « médiane du panel de l'observatoire ».
5. **Comparer exige la compatibilité des définitions**, des périmètres, des périodes et
   des institutions. Une commune-centre dont la métropole exerce des compétences
   différentes n'est pas comparable poste par poste sans retraitement.
6. **Un comparateur n'est pas un contrefactuel.** Dire que Clermont fait mieux que la
   médiane du panel ne dit rien de ce qui se serait passé sous une autre politique. Aucune
   formulation causale ne doit s'appuyer sur une comparaison seule.

## Conflit de périmètre — à traiter avant toute mise en œuvre

Le dépôt `project-iagora` exclut explicitement de son périmètre accepté la
« comparaison avec d'autres villes ou territoires » (ADR-0001 et périmètre produit).

**Conséquence :** la méthodologie ci-dessus est enregistrée ici comme travail préparatoire.
Elle ne doit pas être proposée en amont, ni implémentée, tant qu'une révision explicite de
périmètre n'a pas été décidée du côté de la plateforme.

Ce document existe précisément pour que cette méthodologie soit prête le jour où cette
décision sera prise, plutôt que d'être improvisée sous pression — et pour que le conflit
soit visible dès maintenant plutôt que découvert au moment de l'implémentation.

## Ce qui reste à établir

- Arrêter la liste définitive du panel et la figer par une décision datée.
- Identifier le code de strate DGFiP exact de Clermont-Ferrand.
- Vérifier, pour chaque ville du panel, la répartition réelle des compétences avec sa
  métropole — sans quoi la comparaison financière reste biaisée.
- Ouvrir, si souhaité, la révision de périmètre côté `project-iagora`.

## État actuel

Brouillon. Méthodologie proposée, panel non arrêté, mise en œuvre **bloquée** par le
conflit de périmètre décrit ci-dessus.

## Documents liés

- [00_PERIMETRE](00_PERIMETRE.md)
- [12_RUPTURES_DE_SERIE](12_RUPTURES_DE_SERIE.md)
- [13_SPHERES_DE_COMPETENCE](13_SPHERES_DE_COMPETENCE.md)
