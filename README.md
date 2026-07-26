# Skills Formation Agents

Pack de **skills** (compétences) pour la formation d'agents IA, distribué comme un **plugin marketplace Claude Code** natif.

Une seule commande installe tout le pack de skills sur la machine du client. Aucune dépendance Node requise — seul Claude Code est nécessaire (compatible Windows, macOS et Linux).

---

## Installation (côté client)

Dans **Claude Code**, taper ces deux commandes :

```
/plugin marketplace add Sofiane5900/skills-formation-agents
```

```
/plugin install formation@skills-formation-agents
```

C'est tout. Les skills sont disponibles immédiatement, invoquables sous la forme `/formation:<nom-du-skill>`.

> Prérequis : Claude Code v2.1 ou supérieur.

## Mettre à jour

Les skills reçoivent les mises à jour automatiquement. Pour forcer une mise à jour manuelle :

```
/plugin update
```

## Activer / désactiver / désinstaller

Tout se gère depuis l'interface `/plugin` de Claude Code :

```
/plugin
```

---

## Ajouter un skill au pack

Chaque skill est un dossier contenant un fichier `SKILL.md`, placé dans `skills/` :

```
skills/
└── mon-skill/
    └── SKILL.md
```

Exemple de `SKILL.md` :

```markdown
---
description: Décrit ce que fait le skill et quand l'utiliser. Troisième personne.
---

## Instructions

Le contenu détaillé que Claude suit quand le skill est invoqué.
```

Règles de nommage : nom de dossier en minuscules, lettres et chiffres, séparés par des tirets (`^[a-z0-9]+(-[a-z0-9]+)*$`). Le dossier `skills/` est scanné automatiquement, aucun paramétrage supplémentaire à faire.

Un skill peut contenir plusieurs fichiers (références, scripts, modèles) aux côtés de `SKILL.md`.

---

## Structure du dépôt

```
skills-formation-agents/
├── .claude-plugin/
│   ├── marketplace.json     # catalogue du marketplace
│   └── plugin.json          # manifeste du plugin
├── skills/                  # les skills du pack
│   └── <nom>/SKILL.md
├── README.md
└── LICENSE
```

## Versionnement

Le plugin est versionné via le champ `version` de `.claude-plugin/plugin.json`. **Bumper ce numéro à chaque release** — sinon le client ne reçoit pas la mise à jour.

## Licence

MIT — voir [LICENSE](LICENSE).
