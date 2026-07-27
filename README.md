# Skills Formation Agents

Pack de skills pour former tes agents IA, organisé en **3 boîtes à outils** indépendantes : piloter un plan, design d'interfaces, copywriting. Pas de pipeline global — tu choisis l'outil selon le besoin.

---

## Installation

Dans Claude Code (v2.1+) :

```
/plugin marketplace add Sofiane5900/skills-formation-agents
/plugin install formation@skills-formation-agents
```

---

## Les 3 boîtes à outils

| Domaine | Skill | Commande | Quand l'utiliser | Incluse |
|---|---|---|---|---|
| **Piloter / réfléchir** | `grill-me` | `/grill-me` | Un plan ou un design est flou, tu veux l'affûter par interview | ✅ |
| **Frontend / UI** | `impeccable` | `npx impeccable install` | Design system complet + itération live (**OU**, pas après) | ➕ |
| **Frontend / UI** | `make-interfaces-feel-better` | `/make-interfaces-feel-better [quick\|full] [cible]` | Polish UI rapide (typo, surfaces, animations, icônes) | ✅ |
| **Texte / copy** | `copywriting` | `npx skills add coreyhaines31/marketingskills --skill copywriting` | Écrire du copy neuf (landing, pricing…) | ➕ |
| **Texte / copy** | `copy-editing` | `npx skills add coreyhaines31/marketingskills --skill copy-editing` | Améliorer du copy existant | ➕ |
| **Texte / copy** | `humanizer` | `/humanizer [fichier]` | Passe finale anti-slop IA | ✅ |

`✅` = dans le plugin · `➕` = install séparée (1 commande).

### Comment les choisir

- **Frontend** : `impeccable` **OU** `make-interfaces-feel-better`, selon la profondeur. Design system + live → `impeccable` ; revue rapide → `make-interfaces-feel-better`. Pas l'un après l'autre.
- **Texte** : `copywriting` (neuf) **OU** `copy-editing` (existant). Seule séquence possible — optionnelle — `copywriting`/`copy-editing` → `humanizer` pour la passe anti-IA.
- **Piloter** : `grill-me` est autonome, s'utilise quand un plan est flou, indépendamment du reste.

---

## Référence des commandes

| Commande | Mode d'emploi |
|---|---|
| `/grill-me` | Lance l'interview, réponds une question à la fois |
| `/make-interfaces-feel-better` | Revue complète (défaut). `quick` = courte. Ajoute une cible : `full pricing page` |
| `/humanizer` | Colle du texte → draft + audit + version finale. `/humanizer fichier.md` → réécrit le fichier |
| `/impeccable <sous-cmd> [cible]` | Après `npx impeccable install`. Une **sous-commande** puis la cible : `/impeccable polish`, `/impeccable audit pricing page`, `/impeccable distill` |

---

## Gestion du plugin

```
/plugin update      # mettre à jour
/plugin             # activer / désactiver / désinstaller
```

---

## Crédits

`make-interfaces-feel-better` © Jakub Krehel · `humanizer` © Siqi Chen · `grill-me`/`grilling` © Matt Pocock · `impeccable` © Paul Bakaus · `copywriting`/`copy-editing` © coreyhaines31. Repo © Sofiane5900 (MIT). Bumper `version` dans `.claude-plugin/plugin.json` à chaque release.
