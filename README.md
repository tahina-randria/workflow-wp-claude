# Workflow : refonte d'un site WordPress avec Claude Code

> Guide réplicable de bout en bout — du brief client à la mise en ligne — en utilisant **Claude Code (Anthropic)** comme agent de développement principal.

---

## Pourquoi ce workflow

Refondre un site WordPress legacy (PHP, thème custom, plugins divers) demande typiquement plusieurs jours de dev, beaucoup de copier-coller et un contrôle qualité fastidieux.

En passant par **Claude Code** comme agent principal, j'ai industrialisé ce process pour livrer des refontes en **moins d'une journée**, avec un niveau de qualité supérieur et zéro régression visuelle.

Ce repo documente la méthodologie complète, telle qu'utilisée chez **[Mita Studio](https://mita-studio.com)** sur des projets clients réels.

---

## Stack utilisée

| Outil | Rôle |
|---|---|
| **Claude Code (Anthropic)** | Agent dev principal — lecture du legacy, génération du nouveau code, refactor |
| **WordPress** | CMS cible (avec ou sans builder type Bricks/Elementor) |
| **Tailwind CSS** | Framework styling pour les nouveaux thèmes custom |
| **PHP / Twig** | Templating thème |
| **Git / GitHub** | Versioning, branches feature, PRs |
| **Local by Flywheel** | Environnement de dev local |

---

## Les 7 étapes du workflow

### 1. Audit du site existant
- Inventaire des templates, custom post types, taxonomies
- Liste des plugins critiques vs killables
- Capture du DOM rendu (HTML / CSS) pour benchmark visuel
- Audit performance (Lighthouse, GTmetrix)

### 2. Cadrage du nouveau site avec le client
- Wireframes Figma (low-fi)
- Liste des pages livrables
- Choix techniques : nouveau thème custom vs starter (Underscores, Sage)

### 3. Setup local + repo
- Local by Flywheel pour l'env local
- Repo GitHub avec `.gitignore` standard WordPress
- Branche `main` protégée, branches `feature/*` pour chaque chantier

### 4. Génération assistée par Claude Code
- Brief Claude Code avec : design system Tailwind, structure des pages, conventions de nommage
- Génération itérative des templates (header, footer, single, archive, etc.)
- Refactor des plugins custom vers blocks Gutenberg ou shortcodes propres

### 5. Migration du contenu
- Export DB de l'ancien site
- Mapping des champs ACF / custom fields
- Script de migration via WP-CLI ou import / export Notion → WP

### 6. QA visuelle + perf
- Comparaison side-by-side avec l'ancien site (snapshot tests)
- Lighthouse cible : Performance ≥ 90, Accessibility 100, SEO 100
- Tests de régression sur formulaires, paniers, intégrations tierces

### 7. Mise en ligne + monitoring
- Migration via Migrate Guru ou WP Vivid
- DNS + SSL
- Setup monitoring (UptimeRobot, Plausible, GA4)
- Documentation de passation au client

---

## Métriques observées sur projets clients réels

- Temps moyen de refonte : **< 1 jour ouvré** vs ~5 jours sans Claude Code
- Score Lighthouse moyen post-refonte : **94 / 100 / 100 / 100**
- Zéro régression critique signalée par les clients post-livraison
- Coût client divisé par 3 grâce au gain de temps dev

---

## Pour qui

Ce workflow est utile pour :
- **Devs freelance / studios** qui veulent industrialiser leur livraison WordPress
- **Agences** qui cherchent à intégrer des agents IA dans leur process de production
- **Startups** qui héritent d'un site WordPress legacy et veulent moderniser sans tout refondre from scratch

---

## Liens

- 🎨 [Mita Studio](https://mita-studio.com) — où ce workflow est appliqué en production
- 💼 [LinkedIn](https://linkedin.com/in/tahina-randria)
- 📨 tahina.dmc@gmail.com pour échanger sur le sujet

---

*Maintenu par [Tahina Randrianandraina](https://github.com/tahina-randria).*
