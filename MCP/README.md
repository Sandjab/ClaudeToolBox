# MCP - Model Context Protocol Servers

Guide des serveurs MCP (Model Context Protocol) pour le **workflow de développement** avec Claude Code.

Ce guide se concentre sur les MCP **utilitaires** qui aident concrètement à documenter, développer, construire, tester et déployer des applications.

---

## Légende des critères d'évaluation

| Critère | Description | Notation |
|---------|-------------|----------|
| **Maintenance** | Fréquence des mises à jour, réactivité aux issues | 🟢 Active / 🟡 Modérée / 🔴 Inactive |
| **Popularité** | Étoiles GitHub, téléchargements | ⭐⭐⭐⭐⭐ (1-5) |
| **Documentation** | Qualité et exhaustivité | 📚 Complète / 📖 Basique / 📄 Minimale |
| **Installation** | Complexité de mise en place | 🟢 Simple / 🟡 Moyenne / 🔴 Complexe |
| **Fiabilité** | Stabilité et retours utilisateurs | 🛡️ Stable / ⚠️ Beta / 🧪 Expérimental |
| **Support** | Type de maintenance | ✅ Officiel / 🏠 Communautaire |

---

# Documentation & Recherche

MCP pour accéder à la documentation technique et rechercher des informations.

## 1. Context7

Documentation à jour et spécifique aux versions pour les bibliothèques et frameworks.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Upstash) |

**Fonctionnalités** : Documentation versionnée, exemples de code à jour, recherche intelligente dans 1000+ bibliothèques

| Ressource | Lien |
|-----------|------|
| GitHub | [upstash/context7](https://github.com/upstash/context7) |
| Site web | [context7.com](https://context7.com) |

```bash
claude mcp add context7 -- npx -y @upstash/context7-mcp
```

> [!TIP]
> Ajoutez `use context7` à vos prompts pour activer la recherche de documentation.

---

## 2. MDN Web Docs MCP

Documentation officielle Mozilla pour les technologies web (HTML, CSS, JavaScript, APIs).

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Mozilla) |

**Fonctionnalités** : Recherche MDN, documentation APIs web, compatibilité navigateurs (BCD)

| Ressource | Lien |
|-----------|------|
| GitHub | [mdn/mcp](https://github.com/mdn/mcp) |

```bash
claude mcp add --transport http mdn https://mdn-mcp-0445ad8e765a.herokuapp.com/mcp
```

---

## 3. DevDocs MCP

Agrégateur de documentation technique avec crawling intelligent de sites.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ (~285k downloads) |
| Documentation | 📚 Complète |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Crawling de sites de documentation, découverte URLs jusqu'au niveau 5, support documentation interne/externe

| Ressource | Lien |
|-----------|------|
| GitHub | [cyberagiinc/DevDocs](https://github.com/cyberagiinc/DevDocs) |

---

## 4. Microsoft Learn MCP

Documentation officielle Microsoft (Azure, .NET, TypeScript, etc.).

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Microsoft) |

**Fonctionnalités** : Documentation Azure, .NET, TypeScript, VS Code, PowerShell

| Ressource | Lien |
|-----------|------|
| Documentation | [Microsoft Learn MCP](https://learn.microsoft.com/en-us/training/support/mcp-developer-reference) |

---

## 5. Apple Developer Documentation MCP

Documentation officielle Apple pour iOS, macOS, SwiftUI, UIKit, visionOS.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Documentation iOS/macOS/SwiftUI/UIKit, vidéos WWDC 2014-2025, exemples de code

| Ressource | Lien |
|-----------|------|
| GitHub | [kimsungwhee/apple-docs-mcp](https://github.com/kimsungwhee/apple-docs-mcp) |

```bash
claude mcp add apple-docs -- npx -y apple-docs-mcp
```

---

## 6. Brave Search

Recherche web complète avec résumés IA.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Brave) |

**Fonctionnalités** : Recherche web/images/vidéos/actualités, recherche locale, résumés IA

| Ressource | Lien |
|-----------|------|
| GitHub | [brave/brave-search-mcp-server](https://github.com/brave/brave-search-mcp-server) |

```bash
claude mcp add brave-search -e BRAVE_API_KEY=<api-key> -- npx -y @brave/brave-search-mcp-server
```

> [!NOTE]
> Clé API gratuite requise : [brave.com/search/api](https://brave.com/search/api/)

---

# Build, Compilation & Packages

MCP pour construire, compiler et gérer les dépendances de vos projets.

## 1. XcodeBuildMCP

Build et run de projets iOS/macOS avec Xcode.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Build/run projets Xcode, gestion simulateurs, intégration CocoaPods/SPM, schemes et configurations

| Ressource | Lien |
|-----------|------|
| GitHub | [cameroncooke/XcodeBuildMCP](https://github.com/cameroncooke/XcodeBuildMCP) |
| Guide | [Agentic iOS workflow](https://levelup.gitconnected.com/agentic-ios-workflow-with-xcodebuildmcp-and-cursor-4cee793845a3) |

```bash
claude mcp add xcodebuild -- npx -y xcodebuildmcp
```

---

## 2. npm Helper MCP

Gestion des packages npm et mise à jour des dépendances.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Recherche npm registry, gestion dépendances, support npm/yarn/pnpm/bun

| Ressource | Lien |
|-----------|------|
| GitHub | [pinkpixel-dev/npm-helper-mcp](https://github.com/pinkpixel-dev/npm-helper-mcp) |

---

## 3. Desktop Commander

Exécution de commandes terminal avec contrôle complet du système.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Exécution terminal (timeout, background), gestion processus, édition fichiers diff, exécution code en mémoire (Python, Node.js, R)

| Ressource | Lien |
|-----------|------|
| GitHub | [wonderwhy-er/DesktopCommanderMCP](https://github.com/wonderwhy-er/DesktopCommanderMCP) |
| Site web | [desktopcommander.app](https://desktopcommander.app/) |

```bash
npx -y @smithery/cli install @wonderwhy-er/desktop-commander --client claude
```

---

# Linting & Analyse de code

MCP pour l'analyse statique, le linting et le formatage du code.

## 1. ESLint MCP (Officiel)

Linting JavaScript/TypeScript directement depuis Claude.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (ESLint) |

**Fonctionnalités** : Linting à la demande, suggestions contextuelles, intégration VS Code Copilot

| Ressource | Lien |
|-----------|------|
| Documentation | [ESLint MCP Setup](https://eslint.org/docs/latest/use/mcp) |
| npm | [@eslint/mcp](https://www.npmjs.com/package/@eslint/mcp) |

```bash
npx @eslint/mcp@latest
```

---

## 2. Claude LSP (TypeScript + ESLint + Prettier)

Analyse de code en temps réel combinant TypeScript LSP, ESLint et Prettier.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Analyse TypeScript en temps réel, erreurs de type, linting ESLint, formatage Prettier, checks GraphQL

| Ressource | Lien |
|-----------|------|
| npm | [@juanpprieto/claude-lsp](https://www.npmjs.com/package/@juanpprieto/claude-lsp) |

---

## 3. MCP Basics (ESLint + Prettier centralisé)

Serveur MCP centralisé pour le linting et formatage cross-projets.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Linting ESLint centralisé, formatage Prettier cross-projets, traduction

| Ressource | Lien |
|-----------|------|
| Glama | [MCP Basics](https://glama.ai/mcp/servers/@caroline-davis/mcp-basics) |

---

# Simulateurs & Émulateurs

MCP pour contrôler les simulateurs iOS et émulateurs Android.

## 1. Mobile MCP (iOS + Android)

Automatisation mobile multi-plateforme (simulateurs, émulateurs, appareils réels).

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : iOS Simulator + Android Emulator + appareils réels, liste devices, screenshots, installation/lancement apps, orientation

| Ressource | Lien |
|-----------|------|
| GitHub | [mobile-next/mobile-mcp](https://github.com/mobile-next/mobile-mcp) |

---

## 2. iOS Simulator MCP

Contrôle avancé des simulateurs iOS.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ (~20k downloads) |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Interactions UI, inspection éléments, info simulateurs, utilise Facebook IDB

| Ressource | Lien |
|-----------|------|
| GitHub | [joshuayoes/ios-simulator-mcp](https://github.com/joshuayoes/ios-simulator-mcp) |

> [!WARNING]
> Mettez à jour vers v1.3.3+ pour corriger les vulnérabilités d'injection de commandes.

---

## 3. iOS Simulator MCP (Inditex)

Contrôle des simulateurs iOS via langage naturel.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (InditexTech) |

**Fonctionnalités** : Commandes langage naturel, IDBManager, parsing NL, orchestration MCP

| Ressource | Lien |
|-----------|------|
| GitHub | [InditexTech/mcp-server-simulator-ios-idb](https://github.com/InditexTech/mcp-server-simulator-ios-idb) |

---

## 4. Appium MCP

Automatisation mobile cross-platform via Appium.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : iOS + Android, start/end session, launch app, find/tap elements

| Ressource | Lien |
|-----------|------|
| npm | [@gavrix/appium-mcp](https://www.npmjs.com/package/@gavrix/appium-mcp) |

---

# Tests & Automatisation

MCP pour les tests automatisés et l'automatisation web.

## 1. Playwright MCP (Officiel Microsoft)

Automatisation web et tests E2E via Playwright.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Microsoft) |

**Fonctionnalités** : Automatisation Chrome/Firefox/Safari, arbre d'accessibilité (pas de screenshots), mode headless, tests E2E

| Ressource | Lien |
|-----------|------|
| GitHub | [microsoft/playwright-mcp](https://github.com/microsoft/playwright-mcp) |
| npm | [@playwright/mcp](https://www.npmjs.com/package/@playwright/mcp) |

```bash
claude mcp add playwright -- npx @playwright/mcp@latest
```

---

## 2. Puppeteer MCP

Automatisation Chrome/Chromium via Puppeteer.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Contrôle Chrome, screenshots, exécution JavaScript, navigation

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../puppeteer](https://github.com/modelcontextprotocol/servers/tree/main/src/puppeteer) |

```bash
claude mcp add puppeteer -- npx -y @modelcontextprotocol/server-puppeteer
```

---

## 3. Selenium MCP

Automatisation navigateur via Selenium WebDriver.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Chrome/Firefox, bridge avec frameworks de tests existants

---

## 4. TestSprite MCP

Plateforme de tests autonome AI-first.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (TestSprite) |

**Fonctionnalités** : Tests E2E UI/API autonomes, planification IA, génération automatique, debugging

| Ressource | Lien |
|-----------|------|
| Site web | [testsprite.com](https://www.testsprite.com) |

---

## 5. mabl MCP

Tests automatisés avec capacités IA mabl intégrées à l'IDE.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (mabl) |

**Fonctionnalités** : Interface langage naturel, automatisation workflows, sans quitter l'IDE

| Ressource | Lien |
|-----------|------|
| Site web | [mabl MCP Server](https://www.mabl.com/mabl-mcp-server) |

---

# Design & Prototypage

MCP pour l'intégration avec les outils de design UI/UX.

## 1. Figma MCP (Officiel)

Intégration design-to-code avec Figma.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Figma) |

**Fonctionnalités** : Métadonnées design, design tokens, contraintes layout, génération code, règles design system automatiques

| Ressource | Lien |
|-----------|------|
| Documentation | [developers.figma.com/docs/figma-mcp-server](https://developers.figma.com/docs/figma-mcp-server/) |
| Blog | [Introducing Figma MCP Server](https://www.figma.com/blog/introducing-figma-mcp-server/) |

> [!TIP]
> Disponible en mode Remote (hébergé) ou Desktop (local via app Figma).

---

## 2. Figma Context MCP (Framelink)

Contexte de design optimisé pour les agents IA.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Simplification réponses API Figma, layout et styling optimisés pour LLM

| Ressource | Lien |
|-----------|------|
| GitHub | [GLips/Figma-Context-MCP](https://github.com/GLips/Figma-Context-MCP) |

---

# Debugging & Monitoring

MCP pour le debugging et le suivi des erreurs.

## 1. Sentry MCP (Officiel)

Debugging assisté par IA avec Sentry.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Sentry) |

**Fonctionnalités** : Contexte issues complet, stack traces, intégration Seer pour debugging automatique, OAuth

| Ressource | Lien |
|-----------|------|
| GitHub | [getsentry/sentry-mcp](https://github.com/getsentry/sentry-mcp) |
| Documentation | [Sentry MCP Server](https://docs.sentry.io/product/sentry-mcp/) |

```bash
claude mcp add --transport http sentry https://mcp.sentry.dev/mcp
```

---

## 2. Datadog MCP (Officiel)

Observabilité complète avec Datadog.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Datadog) |

**Fonctionnalités** : Métriques, logs, traces, monitors, SLOs, dashboards

| Ressource | Lien |
|-----------|------|
| Documentation | [Datadog MCP Server](https://docs.datadoghq.com/bits_ai/mcp_server/) |

---

## 3. Grafana MCP

Monitoring et observabilité via Grafana Cloud.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta (preview) |
| Support | ✅ Officiel (Grafana Labs) |

**Fonctionnalités** : Dashboard MCP health, analytics outils, TraceQL queries

| Ressource | Lien |
|-----------|------|
| Documentation | [Grafana MCP Observability](https://grafana.com/docs/grafana-cloud/monitor-applications/ai-observability/mcp-observability/) |

---

# Contrôle de version

MCP pour la gestion de version et les plateformes Git.

## 1. GitHub MCP (Officiel)

Intégration complète avec GitHub.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟡 Moyenne (Docker) |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (GitHub) |

**Fonctionnalités** : Repos, commits, branches, PRs, issues, Actions, code review

| Ressource | Lien |
|-----------|------|
| GitHub | [github/github-mcp-server](https://github.com/github/github-mcp-server) |
| Guide Claude | [install-claude.md](https://github.com/github/github-mcp-server/blob/main/docs/installation-guides/install-claude.md) |

```bash
claude mcp add github -e GITHUB_PERSONAL_ACCESS_TOKEN=<token> -- \
  docker run -i --rm -e GITHUB_PERSONAL_ACCESS_TOKEN ghcr.io/github/github-mcp-server
```

---

## 2. GitLab MCP

Intégration avec GitLab.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Repos, merge requests, issues, pipelines CI/CD

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../gitlab](https://github.com/modelcontextprotocol/servers/tree/main/src/gitlab) |

---

## 3. Bitbucket MCP

Intégration avec Atlassian Bitbucket.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Workspaces, repos, PRs, commentaires

| Ressource | Lien |
|-----------|------|
| GitHub | [aashari/mcp-server-atlassian-bitbucket](https://github.com/aashari/mcp-server-atlassian-bitbucket) |

---

# Bases de données

MCP pour interagir avec les bases de données.

## 1. PostgreSQL MCP

Connexion aux bases de données PostgreSQL.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Requêtes SQL, gestion schémas, mode lecture seule par défaut

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../postgres](https://github.com/modelcontextprotocol/servers/tree/main/src/postgres) |

```bash
claude mcp add postgres -- npx -y @modelcontextprotocol/server-postgres \
  postgresql://user:password@localhost:5432/database
```

---

## 2. MongoDB MCP (Officiel)

Intégration MongoDB Atlas/Community/Enterprise.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (MongoDB) |

**Fonctionnalités** : Opérations CRUD, requêtes langage naturel, support Atlas

| Ressource | Lien |
|-----------|------|
| GitHub | [mongodb-js/mongodb-mcp-server](https://github.com/mongodb-js/mongodb-mcp-server) |
| Documentation | [MongoDB MCP Docs](https://www.mongodb.com/docs/mcp-server/get-started/) |

---

## 3. Redis MCP (Officiel)

Intégration Redis pour cache et données temps réel.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Redis) |

**Fonctionnalités** : Hashes, lists, sets, streams, recherche

| Ressource | Lien |
|-----------|------|
| GitHub | [redis/mcp-redis](https://github.com/redis/mcp-redis) |

---

## 4. SQLite MCP

Support des bases de données SQLite locales.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Requêtes SQL, fichiers .db, lecture/écriture

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../sqlite](https://github.com/modelcontextprotocol/servers/tree/main/src/sqlite) |

---

# DevOps & Déploiement

MCP pour les conteneurs, CI/CD et infrastructure.

## 1. Docker MCP (Officiel)

Gestion des conteneurs Docker.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Docker) |

**Fonctionnalités** : Build/run containers, inspection, génération Dockerfiles, isolation sécurisée

| Ressource | Lien |
|-----------|------|
| Blog | [Docker MCP](https://www.docker.com/blog/the-model-context-protocol-simplifying-building-ai-apps-with-anthropic-claude-desktop-and-docker/) |

---

## 2. Kubernetes MCP

Gestion clusters Kubernetes et OpenShift.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Red Hat) |

**Fonctionnalités** : Multi-clusters, API native Go (pas wrapper kubectl), Linux/macOS/Windows

| Ressource | Lien |
|-----------|------|
| GitHub | [containers/kubernetes-mcp-server](https://github.com/containers/kubernetes-mcp-server) |

---

## 3. Argo CD MCP

Workflows GitOps avec Argo CD.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Akuity) |

**Fonctionnalités** : Gestion applications, sync, rollback, langage naturel

---

# Productivité

MCP pour les outils collaboratifs et de gestion de projet.

## 1. Notion MCP (Officiel)

Accès aux workspaces Notion.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Notion) |

**Fonctionnalités** : Lecture/écriture pages, bases de données, API Markdown

| Ressource | Lien |
|-----------|------|
| Documentation | [Notion MCP](https://developers.notion.com/docs/mcp) |

---

## 2. Slack MCP (Officiel)

Intégration native avec Slack.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Slack) |

**Fonctionnalités** : Monitoring channels, résumés threads, notifications

| Ressource | Lien |
|-----------|------|
| Blog | [Slack Agentic Era](https://slack.com/blog/news/powering-agentic-collaboration) |

---

## 3. Linear MCP

Gestion de projets et issues.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Issues, projets, cycles, roadmaps

---

# Utilitaires

MCP utilitaires pour des tâches courantes.

## 1. Filesystem MCP

Opérations sécurisées sur les fichiers.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Lecture/écriture sécurisée, navigation répertoires, contrôle d'accès

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../filesystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) |

```bash
claude mcp add filesystem -- npx -y @modelcontextprotocol/server-filesystem /chemin
```

---

## 2. Memory MCP (Knowledge Graph)

Mémoire persistante entre sessions.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Graphe de connaissances local, mémoire persistante, contexte utilisateur

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../memory](https://github.com/modelcontextprotocol/servers/tree/main/src/memory) |

```bash
claude mcp add memory -- npx -y @modelcontextprotocol/server-memory
```

---

## 3. Time MCP

Gestion du temps et des fuseaux horaires.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Heure actuelle, conversion fuseaux horaires IANA, détection automatique timezone

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../time](https://github.com/modelcontextprotocol/servers/tree/main/src/time) |

---

## 4. Fetch MCP

Récupération de contenu web optimisée pour LLM.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Récupération web, conversion HTML→Markdown, en-têtes personnalisés

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../fetch](https://github.com/modelcontextprotocol/servers/tree/main/src/fetch) |

```bash
claude mcp add fetch -- npx -y @modelcontextprotocol/server-fetch
```

---

## 5. Sequential Thinking

Résolution de problèmes complexes étape par étape.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Réflexion structurée, révision et branchement, maintien du contexte

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../sequentialthinking](https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking) |

```bash
claude mcp add sequentialthinking -- npx -y @modelcontextprotocol/server-sequentialthinking
```

---

# Ressources

## Répertoires de serveurs MCP

| Ressource | Description |
|-----------|-------------|
| [MCP Registry](https://github.com/modelcontextprotocol/servers) | Dépôt officiel Anthropic |
| [Awesome MCP Servers](https://github.com/punkpeye/awesome-mcp-servers) | Liste communautaire |
| [PulseMCP](https://www.pulsemcp.com/servers) | 7700+ serveurs avec évaluations |
| [Smithery](https://smithery.ai/) | Installation simplifiée |
| [MCP.so](https://mcp.so/) | Répertoire avec recherche |

## Documentation officielle

| Ressource | Lien |
|-----------|------|
| Introduction MCP | [anthropic.com/news/model-context-protocol](https://www.anthropic.com/news/model-context-protocol) |
| Spécification | [modelcontextprotocol.io](https://modelcontextprotocol.io) |

---

## Bonnes pratiques

> [!TIP]
> **Sélection** : Choisissez 3-5 MCP correspondant à votre workflow quotidien. Trop de MCP ralentissent Claude Code.

> [!WARNING]
> **Sécurité** : Testez d'abord en lecture seule. Mettez à jour régulièrement (CVE-2025-53110, CVE-2025-6514).

> [!IMPORTANT]
> **Critères de choix** :
> - Privilégiez les MCP officiels (✅)
> - Vérifiez le dernier commit GitHub
> - Consultez les issues ouvertes
> - Testez en dev avant prod

---

*Dernière mise à jour : Janvier 2025*
