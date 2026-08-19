# Contrat de travail des agents

**Statut :** Brouillon
**Responsable :** Cinthia Coelho
**Dernière vérification :** 2026-08-18
**S'applique à :** tout agent automatisé travaillant sur ce dépôt

Ce document est lu par les agents avant toute contribution. Il définit qui fait quoi,
comment le travail passe de l'un à l'autre, et ce qu'aucun des deux ne peut faire.

---

## 1. Le dépôt est le canal

Les agents qui travaillent sur ce projet **ne communiquent pas directement**. Il n'existe
pas de session partagée, pas de mémoire commune, pas de conversation.

Tout ce qui doit passer d'un agent à l'autre passe par un artefact versionné : une issue,
une branche, une pull request, un document. Ce qui n'est pas écrit dans le dépôt n'existe
pas pour l'autre agent.

Ce n'est pas une contrainte technique subie, c'est la règle de fonctionnement voulue. Un
projet dont la raison d'être est la traçabilité ne peut pas se coordonner par des échanges
privés et non enregistrés.

**Conséquence pratique :** une contribution qui suppose un contexte non écrit est une
contribution défectueuse, même si le code fonctionne.

---

## 2. Domaines

| | **Agent de recherche et de méthode** | **Agent d'implémentation** |
|---|---|---|
| Rôle type | Claude | Codex |
| Question à laquelle il répond | *Est-ce vrai du monde réel ?* | *Est-ce que ça fonctionne ?* |
| Domaine | Sources publiques, vérification, méthodologie, latences, ruptures, compétences, droit d'accès, documentation, revue méthodologique | Contrats exécutables, schémas, pipeline, tests, interface, refactorisation, revue technique |
| Produit | Documents, inventaires, briefs d'issue, avis de revue | Code, contrats, tests, pull requests |
| Accès au monde extérieur | Oui — consultation des sources publiques | Non supposé |

**Zone commune :** le modèle de données. Ni l'un ni l'autre ne le modifie seul. Une
évolution du modèle se propose par un document, se discute en issue, et s'implémente
ensuite.

---

## 3. Cycle de travail

```
constat vérifié
      ↓
document (docs/)              ← agent de recherche
      ↓
issue avec critères d'acceptation
      ↓
branche + implémentation      ← agent d'implémentation
      ↓
pull request
      ↓
revue croisée                 ← méthodologique + technique
      ↓
décision humaine
```

**Aucun agent ne fusionne dans `main`.** La fusion est une décision humaine.

### Ce que doit contenir une issue destinée à l'autre agent

Une issue mal spécifiée produit du travail inutile, et le travail inutile n'est visible
qu'après coup. Toute issue transmise contient :

1. le problème, exprimé du point de vue de l'usage — pas de la solution ;
2. le ou les documents de référence qui l'établissent ;
3. ce qui est **vérifié** et ce qui reste **hypothèse** ;
4. les critères d'acceptation, vérifiables ;
5. ce qui est explicitement **hors périmètre** de l'issue ;
6. les invariants applicables (section 4).

### Ce que doit contenir une pull request

Le problème traité, les documents affectés, ce qui a été vérifié et comment, les
limitations subsistantes, et les index mis à jour dans le même changement.

---

## 4. Invariants — non négociables

Aucun agent ne peut les contourner, même sur demande, même pour faire fonctionner
quelque chose. Une demande qui les viole se refuse et s'escalade.

1. **Aucun fait civique inventé.** Une source non consultée est marquée « à vérifier ».
   Une URL non vérifiée n'est pas écrite. L'incertitude s'affiche, elle ne se comble pas.
2. **Toute valeur porte sa date de référence, sa date de publication et sa sphère de
   compétence.** Voir [11](docs/11_LATENCE_ET_DEUX_HORLOGES.md) et
   [13](docs/13_SPHERES_DE_COMPETENCE.md).
3. **Aucune série ne franchit une rupture non résolue** sans marque explicite. Voir
   [12](docs/12_RUPTURES_DE_SERIE.md).
4. **Une donnée manquante n'est jamais un zéro**, jamais un « non fait », jamais une
   présomption. Voir [17](docs/17_REGISTRE_DES_LACUNES.md).
5. **Une capture n'écrase jamais la précédente.** Ajout seul, empreinte de contenu,
   horodatage de capture. Voir [14](docs/14_VOLATILITE_DES_SOURCES.md).
6. **Ce dépôt documente l'action publique.** Il ne fait pas campagne, ne classe pas les
   élus, ne prescrit pas de choix politique, et ne présente aucune corrélation comme une
   causalité.
7. **Documenter une source n'autorise pas à la collecter.** L'acquisition relève d'une
   décision distincte.

---

## 5. Ce que chaque agent ne fait pas

**L'agent de recherche** n'écrit pas de code de production, ne modifie pas de contrat
exécutable, et ne décide pas d'architecture technique seul. Il propose ; il ne tranche pas
à la place de l'agent d'implémentation.

**L'agent d'implémentation** n'invente pas de source, ne comble pas une lacune de données
par une valeur plausible, ne modifie pas une règle méthodologique pour faire passer un
test, et ne change pas le sens d'un indicateur sans passer par un document.

**Aucun des deux** ne fusionne dans `main`, ne publie quoi que ce soit à l'extérieur, ne
contacte une administration, ne dépose une demande d'accès, ni ne modifie la visibilité du
dépôt.

---

## 6. Désaccord

Si deux artefacts acceptés se contredisent, ou si un agent estime qu'une instruction viole
un invariant : **arrêter, écrire le désaccord dans une issue, escalader.** Ne jamais
trancher silencieusement, ne jamais choisir l'interprétation la plus commode.

Deux conflits connus sont déjà enregistrés et ne doivent pas être « résolus » par un agent :

- la comparaison inter-territoriale, exclue du périmètre accepté de la plateforme —
  voir [16](docs/16_TERRITOIRES_DE_COMPARAISON.md) ;
- la capture périodique de sources volatiles, interdite pour l'incrément courant —
  voir [14](docs/14_VOLATILITE_DES_SOURCES.md).

---

## 7. Conventions d'écriture

- **Langue :** français pour tout ce dépôt. Les remontées vers `project-iagora` se
  rédigent en anglais, selon les conventions de ce dépôt-là. Voir
  [`upstream/`](upstream/README.md).
- **En-tête de document :** `Statut`, `Responsable`, `Dernière vérification`, et
  `Date d'observation` lorsque le document dépend d'un relevé.
- **Sections de fin :** `État actuel` — déclaration honnête de ce qui est établi et de ce
  qui ne l'est pas — puis `Documents liés`.
- **Termes administratifs français** conservés en français.
- **Une seule définition normative par notion.** Les autres documents pointent vers elle.
- **Ajouter, déplacer ou renommer un document** oblige à mettre à jour
  [`docs/99_INDEX.md`](docs/99_INDEX.md) **dans le même changement**.
- **Étiqueter les exemples :** `réel`, `illustratif`, `synthétique` ou `provisoire`.

---

## 8. Terminé, cela veut dire quoi

Une contribution est terminée quand :

- le problème est traité et le périmètre respecté ;
- chaque affirmation nouvelle est sourcée, ou explicitement marquée non vérifiée ;
- les invariants de la section 4 sont respectés ;
- les index et documents liés sont à jour ;
- la section `État actuel` du document touché dit la vérité sur ce qui reste incertain ;
- ce qui reste à faire est écrit, pas seulement su.

Une fusion n'est ni une publication, ni une validation méthodologique.

---

## 9. Relation avec `project-iagora`

Ce dépôt est **territorial** : Clermont-Ferrand, en français.
[`project-iagora`](https://github.com/ccoelhofize/project-iagora) est la **plateforme** :
générique, en anglais, gouvernée par des décisions d'architecture formelles, avec son
propre contrat d'agents.

Un agent qui travaille ici et remarque qu'un constat est générique — donc valable pour
n'importe quelle collectivité — l'inscrit dans [`upstream/`](upstream/README.md) au lieu
de l'implémenter ici. La frontière exacte est en [00](docs/00_PERIMETRE.md).

**Un agent ne contribue jamais aux deux dépôts dans le même changement.**
