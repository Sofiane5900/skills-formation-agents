# Skills Formation Agents

Le pack de compétences pour **former tes agents IA**. Trois domaines réunis dans un seul plugin Claude Code :

- **Cadrer un projet** — interviewer pour affûter un plan avant de coder
- **Design d'interfaces** — polir les détails qui font qu'une UI « marche »
- **Copywriting** — rédiger et nettoyer du texte sans la « sauce IA »

Une seule commande installe tout. Côté client, seul Claude Code est requis (Windows, macOS, Linux).

---

## Sommaire

1. [Installation en 3 étapes](#installation-en-3-étapes)
2. [Le workflow complet](#le-workflow-complet)
3. [Les 6 skills en détail](#les-6-skills-en-détail)
4. [Exemple d'enchaînement complet](#exemple-denchaînement-complet)
5. [Gestion du plugin](#gestion-du-plugin)
6. [Pour le mainteneur](#pour-le-mainteneur)
7. [Crédits](#crédits)

---

## Installation en 3 étapes

**Prérequis** : Claude Code v2.1 ou supérieur.

**Étape 1** — Ajouter le marketplace :

```
/plugin marketplace add Sofiane5900/skills-formation-agents
```

**Étape 2** — Installer le plugin :

```
/plugin install formation@skills-formation-agents
```

**Étape 3** — Vérifier. Tape `/plugin` pour voir la liste, puis teste un skill :

```
/humanizer
```

Colle un bout de texte → l'agent te rend une version nettoyée. Si ça répond, tout fonctionne.

> Les 3 skills `make-interfaces-feel-better`, `humanizer`, `grill-me`/`grilling` sont **inclus** dans le plugin. Les 3 autres (`impeccable`, `copywriting`, `copy-editing`) s'installent en une commande chacun — voir [Les 6 skills en détail](#les-6-skills-en-détail).

---

## Le workflow complet

Ce pack est pensé pour s'enchaîner. Voici comment les 6 skills s'articulent sur un projet, du cadrage jusqu'au texte final :

```
┌──────────────┐    ┌─────────────────────────────┐    ┌──────────────────────────┐    ┌──────────────┐
│  1. Cadrer   │ -> │      2. Design UI           │ -> │     3. Rédiger           │ -> │  4. Nettoyer │
│              │    │                             │    │                          │    │              │
│  /grill-me   │    │  /make-interfaces-feel-     │    │  copywriting             │    │  /humanizer  │
│  (interview) │    │  feel-better                │    │  (copy neuf)             │    │  (anti-slop) │
│              │    │  + impeccable*              │    │  copy-editing*           │    │              │
└──────────────┘    └─────────────────────────────┘    └──────────────────────────┘    └──────────────┘

* = install séparée (1 commande)
```

### Phase 1 — Cadrer le projet

Avant d'écrire la moindre ligne ou le moindre mot, tu affûtes l'idée.

- **`/grill-me`** (inclus) — lance un entretien sans relâche, une question à la fois. Il parcourt l'arbre des décisions, propose une réponse recommandée pour chacune, et cherche lui-même les faits que le code peut lui donner. À la fin, tu as un plan solide et un vocabulaire partagé, pas un brouillon vague.

### Phase 2 — Design UI

Tu construis les écrans avec Claude Code, puis tu les polis.

- **`/make-interfaces-feel-better`** (inclus) — passe de revue ciblée sur les détails : typographie, surfaces, animations, icônes, performance. Idéal pour traquer ce qui « cloche » sans que tu saches quoi.
- **`impeccable`** *(install séparée)* — va plus loin : design system complet, itération visuelle live dans le navigateur, audits de production. À utiliser quand tu veux pousser le design au niveau supérieur, pas juste corriger des détails.

### Phase 3 — Rédiger & nettoyer le copy

- **`copywriting`** *(install séparée)* — rédiger du copy neuf (homepage, landing, pricing, feature…).
- **`copy-editing`** *(install séparée)* — améliorer du copy existant, passe par passe, sans le réécrire de zéro.
- **`/humanizer`** (inclus) — la dernière passe. Retire les tics d'écriture générée par IA (em dashes à tout va, « règle de trois », formules promo, etc.) pour un texte qui sonne humain.

---

## Les 6 skills en détail

### `/grill-me` et `/grilling` — Cadrer un plan *(inclus)*

**Ce que ça fait.** Un entretien qui te questionnaire sans relâche sur ton plan ou ton design, une seule question à la fois. Il parcourt chaque branche de l'arbre de décisions, résout les dépendances avant d'avancer, et propose une réponse recommandée pour chaque question. Les faits que le code peut lui donner, il va les chercher lui-même plutôt que de te les demander.

**Comment l'invoquer.** `/grill-me` est un alias qui lance `/grilling` :

```
/grill-me
```

Puis réponds à chaque question. Il ne passe à la suivante que quand tu as répondu.

**Quand l'utiliser.** Au tout début d'un changement, quand le plan est encore flou et le vocabulaire pas fixé. Avant qu'écrive la moindre spec ou le moindre code.

---

### `/make-interfaces-feel-better` — Polish UI *(inclus)*

**Ce que ça fait.** Applique et révise 17 principes d'ingénierie design qui font qu'une interface « marche » : border-radius concentriques, alignement optique, ombres pour la profondeur vs bordures pour la structure, animations interruptibles, `scale(0.96)` au clic, font smoothing, tabular numbers, hit areas 44×44, etc. Couvre 5 catégories : typographie, surfaces, animations, icônes, performance.

**Comment l'invoquer.** Deux modes, une cible optionnelle :

```
/make-interfaces-feel-better                          # revue complète (défaut)
/make-interfaces-feel-better quick                    # revue courte
/make-interfaces-feel-better full pricing page        # revue complète sur la page pricing
```

**Exemples concrets de ce qu'il corrige.**
- Des border-radius incohérents entre un bouton et son conteneur → applique la règle *outer radius = inner radius + padding*.
- Des nombres qui font sauter la mise en page → ajoute `font-variant-numeric: tabular-nums`.
- Une icône qui change brusquement d'état → remplace par un cross-fade `opacity`/`scale`/`blur`.

**Quand l'utiliser.** Dès que tu as des écrans construits et que tu veux les rendre polishés. Pour un design system complet et de l'itération live, passe à `impeccable`.

---

### `/humanizer` — Nettoyer le copy *(inclus)*

**Ce que ça fait.** Identifie et retire les signes d'écriture générée par IA : emphase gonflée (« a pivotal moment »), analyses superficielles en « -ing », vocabulaire IA (« delve », « tapestry »), em dashes à tout va, rule of three, voix passive, conclusions génériques positives… Basé sur le guide Wikipedia « Signs of AI writing ».

**Comment l'invoquer.** Trois modes selon ce que tu lui donnes :

| Mode | Comment | Ce que tu reçois |
|---|---|---|
| **Texte collé** *(défaut)* | `/humanizer` puis colle ton texte | un brouillon + une liste des tics restants + la version finale |
| **Fichier** | `/humanizer chemin/vers-article.md` | le fichier réécrit en place (prose seule ; code/frontmatter/data intacts) + un résumé des changements |
| **Embedded** | invoqué par une autre tâche (commit, PR, doc) | uniquement le texte final, sans cérémonie |

**Voice calibration.** Si tu lui donnes un sample de ton écriture (un ancien article, par ex.), il calibre le ton dessus plutôt que d'appliquer un style générique. Le sample l'emporte même sur les règles du skill.

**Quand l'utiliser.** En toute fin de chaîne, sur tout texte que Claude a généré : landing pages, emails, docs, descriptions produits. La passe anti-slop finale.

---

### `impeccable` — Design system avancé *(install séparée)*

**Ce que ça fait.** Le skill de design frontend le plus abouti : il respecte ton design system existant (tokens, composants) au lieu de l'écraser, itère visuellement en live dans le navigateur, et fournit tout un vocabulaire de commandes (`polish`, `audit`, `distill`, `shape`, `typeset`, `colorize`, `animate`…). Inclut un détecteur de « slop » UI.

**Pourquoi en install séparée.** Il embarque un runtime (`npx impeccable`) et 60+ scripts, mis à jour très fréquemment. Le garder dans son canal officiel = tu profites des màj automatiques.

**Comment l'installer.**

```
npx impeccable install
```

Ou via marketplace Claude Code :

```
/plugin marketplace add pbakaus/impeccable
```

**Quand l'utiliser vs `/make-interfaces-feel-better`.** `make-interfaces` = revue focalisée sur les détails de polish, légère, déjà dans le pack. `impeccable` = design system complet + itération live + visuels ambitieux. Sur un projet sérieux, tu installes impeccable ; sur une revue rapide, `make-interfaces` suffit.

---

### `copywriting` — Rédiger du copy neuf *(install séparée)*

**Ce que ça fait.** Rédige du marketing copy orienté conversion : homepage, landing page, page pricing, page feature, page about. Pose les bonnes questions (but de la page, audience, offre) puis écrit.

**Comment l'installer.**

```
npx skills add coreyhaines31/marketingskills --skill copywriting
```

**Quand l'utiliser.** Quand tu pars de zéro et veux du copy neuf pour une page.

---

### `copy-editing` — Améliorer du copy existant *(install séparée)*

**Ce que ça fait.** Améliore du copy qui existe déjà, passe par passe (un objectif à la fois), sans le réécrire de zéro. Serre le message, traque ce qui est trop long ou maladroit.

**Comment l'installer.**

```
npx skills add coreyhaines31/marketingskills --skill copy-editing
```

**Quand l'utiliser.** Quand tu as déjà du copy et que tu veux le sharpen, pas repartir de zéro.

---

## Exemple d'enchaînement complet

Scénario : tu lances une landing page pour ton SaaS. Voici l'ordre des commandes, de l'idée au texte final.

**1. Cadrer** — tu affûtes l'offre et la structure :
```
/grill-me
```
L'agent te questionne (audience, proposition de valeur, points de friction). Tu sors avec un plan net.

**2. Construire & polir l'UI** — tu demandes à Claude Code de coder la page, puis :
```
/make-interfaces-feel-better full landing page
```
Pour pousser plus loin (design system, itération live dans le navigateur) :
```
npx impeccable install          # une seule fois
/impeccable polish landing page
```

**3. Rédiger le copy** — d'abord le neuf :
```
npx skills add coreyhaines31/marketingskills --skill copywriting
```
Puis « write copy for the hero section, audience = devs, tone = direct ». Si tu as déjà du copy à améliorer :
```
npx skills add coreyhaines31/marketingskills --skill copy-editing
```
« Sharpen the pricing section, it's too wordy. »

**4. La passe anti-slop finale** — sur tout le texte généré :
```
/humanizer src/content/landing.md
```
Le fichier est réécrit en place, les tics IA retirés.

Tu as une landing cadrée, designée, rédigée et nettoyée — avec un outil par phase.

---

## Gestion du plugin

**Mettre à jour** (récupère la dernière version du pack) :
```
/plugin update
```

**Activer / désactiver / désinstaller** : tout se gère depuis l'interface interactive :
```
/plugin
```

---

## Pour le mainteneur

### Ajouter un skill au pack

Chaque skill est un dossier avec un `SKILL.md` dans `skills/` :
```
skills/
└── mon-skill/
    ├── SKILL.md
    └── (fichiers de référence, scripts…)
```

Le dossier `skills/` est scanné automatiquement. Règle de nommage : minuscules, lettres/chiffres, tirets (`^[a-z0-9]+(-[a-z0-9]+)*$`). Pour que l'invocation directe `/mon-skill` marche, évite les noms de commandes Claude intégrées (`debug`, `code-review`, `run`, `verify`…).

### Versionnement

Le champ `version` dans `.claude-plugin/plugin.json` pilote les màj. **Bumper à chaque release** — sinon le client ne reçoit rien. Courant : `1.2.0`.

---

## Crédits

Skills redistribués (MIT) : `make-interfaces-feel-better` © Jakub Krehel · `humanizer` © Siqi Chen · `grill-me` / `grilling` © Matt Pocock. En install séparée : `impeccable` © Paul Bakaus · `copywriting` / `copy-editing` © coreyhaines31. Structure du repo © Sofiane5900 (MIT).
