# Skills Formation Agents

Pack de skills pour former tes agents IA : **cadrer un plan**, **design d'interfaces**, **copywriting**. Un plugin Claude Code, une commande pour tout installer.

---

## Installation

Dans Claude Code (v2.1+) :

```
/plugin marketplace add Sofiane5900/skills-formation-agents
/plugin install formation@skills-formation-agents
```

---

## Le workflow

4 phases, du plan au texte final. Les skills s'enchaînent dans cet ordre :

| Phase | Skill | Commande | Action | Incluse |
|---|---|---|---|---|
| **1. Cadrer** | `grill-me` | `/grill-me` | Interview pour affûter un plan | ✅ |
| **2. Design UI** | `make-interfaces-feel-better` | `/make-interfaces-feel-better [quick\|full] [cible]` | Polish des détails UI | ✅ |
| **2. Design UI** | `impeccable` | `npx impeccable install` | Design system complet + itération live | ➕ |
| **3. Rédiger** | `copywriting` | `npx skills add coreyhanes31/marketingskills --skill copywriting` | Copy neuf (landing, pricing…) | ➕ |
| **3. Rédiger** | `copy-editing` | `npx skills add coreyhaines31/marketingskills --skill copy-editing` | Améliorer du copy existant | ➕ |
| **4. Nettoyer** | `humanizer` | `/humanizer [fichier]` | Retire l'écriture générée par IA | ✅ |

`✅` = dans le plugin · `➕` = install séparée (1 commande).

**Flow** : `grill-me` → `make-interfaces-feel-better` (+ `impeccable`) → `copywriting` / `copy-editing` → `humanizer`

---

## Référence des commandes

| Commande | Mode d'emploi |
|---|---|
| `/grill-me` | Lance l'interview, réponds une question à la fois |
| `/make-interfaces-feel-better` | Revue complète (défaut). `quick` = courte. Ajoute une cible : `full pricing page` |
| `/humanizer` | Colle du texte → draft + audit + version finale. `/humanizer fichier.md` → réécrit le fichier |
| `/impeccable <cmd>` | Après `npx impeccable install` : `polish`, `audit`, `distill`, `shape`, `typeset`… |

---

## Gestion du plugin

```
/plugin update      # mettre à jour
/plugin             # activer / désactiver / désinstaller
```

---

## Crédits

`make-interfaces-feel-better` © Jakub Krehel · `humanizer` © Siqi Chen · `grill-me`/`grilling` © Matt Pocock · `impeccable` © Paul Bakaus · `copywriting`/`copy-editing` © coreyhaines31. Repo © Sofiane5900 (MIT). Bumper `version` dans `.claude-plugin/plugin.json` à chaque release.
