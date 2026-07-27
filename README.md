# Skills Formation Agents

Pack de **skills** (compétences) pour la formation d'agents IA, distribué comme un **plugin marketplace Claude Code** natif.

Une seule commande installe tout le pack de skills sur la machine du client. Aucune dépendance Node requise côté client — seul Claude Code est nécessaire (compatible Windows, macOS et Linux).

---

## Installation (côté client)

Dans **Claude Code**, taper ces deux commandes :

```
/plugin marketplace add Sofiane5900/skills-formation-agents
```

```
/plugin install formation@skills-formation-agents
```

> Prérequis : Claude Code v2.1 ou supérieur.

## Comment invoquer les skills

Les skills s'utilisent **normalement**, par leur nom direct :

```
/humanizer
/make-interfaces-feel-better
/grill-me
```

La forme `/formation:<nom-du-skill>` est un **fallback garanti sans conflit**, utile uniquement si une commande Claude intégrée porte le même nom. En pratique, le nom direct fonctionne pour tous les skills de ce pack (aucun ne collide avec les commandes intégrées `debug`, `code-review`, `run`, etc.).

---

## Skills inclus

| Skill | Domaine | Description | Source |
|---|---|---|---|
| `make-interfaces-feel-better` | Frontend | Détails de polish UI : animations, typographie, icônes, hover, ombres, bordures | [jakubkrehel/make-interfaces-feel-better](https://github.com/jakubkrehel/make-interfaces-feel-better) |
| `humanizer` | Copywriting | Retire les signes d'écriture générée par IA (v2.9.1) | [blader/humanizer](https://github.com/blader/humanizer) |
| `grill-me` | Project management | Interview sans relâche pour affûter un plan ou un design (invoque `/grilling`) | [mattpocock/skills](https://github.com/mattpocock/skills) |
| `grilling` | Project management | Le moteur d'interview utilisé par `grill-me` | [mattpocock/skills](https://github.com/mattpocock/skills) |

---

## Installs complémentaires recommandées

Ces skills ne sont **pas bundlés** dans le pack (runtime externe ou licence non redistribuable). Le client les installe séparément, à la demande :

### Frontend — Impeccable
Skill de design frontend avancé (dépend du runtime `npx impeccable` + ses scripts).

```
npx impeccable install
```

ou via marketplace Claude Code :

```
/plugin marketplace add pbakaus/impeccable
```

### Copywriting — Marketing skills
Le dépôt source n'a pas de licence explicite, donc non redistribué ici. Installer directement depuis l'auteur :

```
npx skills add coreyhaines31/marketingskills --skill copywriting
```

```
npx skills add coreyhaines31/marketingskills --skill copy-editing
```

---

## Gestion du plugin

**Mettre à jour** :

```
/plugin update
```

**Activer / désactiver / désinstaller** : tout depuis l'interface `/plugin`.

---

## Ajouter un skill au pack

Chaque skill est un dossier contenant un fichier `SKILL.md`, placé dans `skills/` :

```
skills/
└── mon-skill/
    ├── SKILL.md
    └── (fichiers de référence, scripts...)
```

Exemple de `SKILL.md` :

```markdown
---
description: Décrit ce que fait le skill et quand l'utiliser. Troisième personne.
---

## Instructions

Le contenu détaillé que Claude suit quand le skill est invoqué.
```

Règles de nommage : dossier en minuscules, lettres et chiffres, séparés par des tirets (`^[a-z0-9]+(-[a-z0-9]+)*$`). Le dossier `skills/` est scanné automatiquement. Pour éviter qu'une commande intégrée écrase le nom direct, choisir un nom qui ne figure pas parmi les commandes Claude intégrées.

---

## Crédits et licences

Ce pack redistribute des skills sous licence MIT de leurs auteurs respectifs. Chaque dossier de skill contient son propre fichier `LICENSE` préservant le copyright d'origine :

- `make-interfaces-feel-better` — © 2026 **Jakub Krehel** (MIT)
- `humanizer` — © 2025 **Siqi Chen** (MIT)
- `grill-me`, `grilling` — © 2026 **Matt Pocock** (MIT)

Le reste du dépôt (structure du marketplace, README) — © 2026 **Sofiane5900** (MIT).

## Versionnement

Le plugin est versionné via `version` dans `.claude-plugin/plugin.json`. **Bumper ce numéro à chaque release** — sinon le client ne reçoit pas la mise à jour.

## Licence

MIT — voir [LICENSE](LICENSE).
