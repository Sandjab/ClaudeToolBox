# MCP - Model Context Protocol Servers

Guide complet des serveurs MCP (Model Context Protocol) recommandés pour développer avec Claude Code, organisés par catégorie.

Le Model Context Protocol (MCP) est un standard ouvert introduit par Anthropic en novembre 2024 pour standardiser l'intégration des systèmes d'IA avec des outils externes, des systèmes et des sources de données. Souvent décrit comme "l'USB-C de l'IA", les serveurs MCP agissent comme des ponts permettant aux agents IA d'effectuer diverses tâches.

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

# MCP Génériques

Serveurs MCP essentiels pour tout développeur, indépendamment du langage ou de la plateforme.

## 1. GitHub MCP Server

Le serveur MCP officiel de GitHub pour interagir avec l'écosystème GitHub complet.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟡 Moyenne (Docker requis) |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (GitHub) |

**Fonctionnalités** : Gestion des commits, branches, PRs, issues, workflows CI/CD, analyse de code

| Ressource | Lien |
|-----------|------|
| GitHub | [github/github-mcp-server](https://github.com/github/github-mcp-server) |
| Guide d'installation | [install-claude.md](https://github.com/github/github-mcp-server/blob/main/docs/installation-guides/install-claude.md) |

```bash
claude mcp add github -e GITHUB_PERSONAL_ACCESS_TOKEN=<token> -- \
  docker run -i --rm -e GITHUB_PERSONAL_ACCESS_TOKEN ghcr.io/github/github-mcp-server
```

---

## 2. Context7

Documentation à jour et spécifique aux versions injectée directement dans le contexte.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Upstash) |

**Fonctionnalités** : Documentation à jour, exemples de code versionnés, recherche intelligente

| Ressource | Lien |
|-----------|------|
| GitHub | [upstash/context7](https://github.com/upstash/context7) |
| Site web | [context7.com](https://context7.com) |
| Documentation | [Installation](https://context7.com/docs/installation) |

```bash
claude mcp add context7 -- npx -y @upstash/context7-mcp
```

> [!TIP]
> Ajoutez `use context7` à vos prompts pour activer le serveur.

---

## 3. Sequential Thinking

Résolution de problèmes complexes avec un processus de réflexion structuré.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Résolution étape par étape, révision et branchement, maintien du contexte

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../sequentialthinking](https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking) |

```bash
claude mcp add sequentialthinking -- npx -y @modelcontextprotocol/server-sequentialthinking
```

---

## 4. Filesystem

Opérations sécurisées sur les fichiers avec contrôles d'accès configurables.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Lecture/écriture sécurisée, navigation répertoires, contrôle d'accès granulaire

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../filesystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) |

```bash
claude mcp add filesystem -- npx -y @modelcontextprotocol/server-filesystem /chemin/vers/repertoire
```

---

## 5. Memory (Knowledge Graph)

Mémoire persistante basée sur un graphe de connaissances local.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Mémoire persistante entre sessions, graphe de connaissances, stockage contexte

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../memory](https://github.com/modelcontextprotocol/servers/tree/main/src/memory) |

```bash
claude mcp add memory -- npx -y @modelcontextprotocol/server-memory
```

---

## 6. Brave Search

Recherche web complète via l'API Brave Search.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Brave) |

**Fonctionnalités** : Recherche web/locale/images/vidéos/actualités, résumés IA

| Ressource | Lien |
|-----------|------|
| GitHub | [brave/brave-search-mcp-server](https://github.com/brave/brave-search-mcp-server) |

```bash
claude mcp add brave-search -e BRAVE_API_KEY=<api-key> -- npx -y @brave/brave-search-mcp-server
```

> [!NOTE]
> Clé API requise : [brave.com/search/api](https://brave.com/search/api/)

---

## 7. Fetch

Récupération de contenu web optimisée pour les LLM.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Récupération web, conversion HTML→Markdown, optimisation contexte

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../fetch](https://github.com/modelcontextprotocol/servers/tree/main/src/fetch) |

```bash
claude mcp add fetch -- npx -y @modelcontextprotocol/server-fetch
```

---

# MCP Développement iOS

Serveurs MCP spécialisés pour le développement d'applications iOS.

## 1. XcodeBuildMCP

Le serveur MCP de référence pour l'intégration Xcode.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Build et run de projets iOS, gestion des simulateurs, intégration CocoaPods/SPM

| Ressource | Lien |
|-----------|------|
| GitHub | [cameroncooke/XcodeBuildMCP](https://github.com/cameroncooke/XcodeBuildMCP) |
| Article | [Agentic iOS workflow](https://levelup.gitconnected.com/agentic-ios-workflow-with-xcodebuildmcp-and-cursor-4cee793845a3) |

```bash
claude mcp add xcodebuild -- npx -y xcodebuildmcp
```

---

## 2. Apple Developer Documentation MCP

Accès complet à la documentation officielle Apple.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Recherche docs iOS/macOS/SwiftUI/UIKit, vidéos WWDC 2014-2025, exemples de code

| Ressource | Lien |
|-----------|------|
| GitHub | [kimsungwhee/apple-docs-mcp](https://github.com/kimsungwhee/apple-docs-mcp) |

```bash
claude mcp add apple-docs -- npx -y apple-docs-mcp
```

---

## 3. Xcode MCP Server (PolarVista)

Build et tests pour simulateurs iOS avec configuration par défaut iPhone 15 Pro.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Build/test simulateurs, spécification schemes/configurations, code coverage

| Ressource | Lien |
|-----------|------|
| PulseMCP | [Xcode MCP Server](https://www.pulsemcp.com/servers/polarvista-xcode) |

---

## 4. Xcode MCP Server (r-huijts)

Intégration Xcode complète avec gestion de projets multi-plateformes.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Création projets (iOS, macOS, watchOS, tvOS), ajout fichiers, gestion targets

| Ressource | Lien |
|-----------|------|
| GitHub | [r-huijts/xcode-mcp-server](https://github.com/r-huijts/xcode-mcp-server) |

---

## 5. iOS Simulator MCP

Contrôle avancé des simulateurs iOS.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐ |
| Documentation | 📄 Minimale |
| Installation | 🟡 Moyenne |
| Fiabilité | 🧪 Expérimental |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Gestion simulateurs, installation apps, capture d'écran, logs

---

# MCP Développement Swift

Serveurs MCP pour le développement Swift et les plateformes Apple.

## 1. Swift SDK MCP (Officiel)

Le SDK officiel pour créer des serveurs et clients MCP en Swift.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Implémentation client/serveur MCP, Swift 6.0+, spécification 2025-03-26

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/swift-sdk](https://github.com/modelcontextprotocol/swift-sdk) |

**Prérequis** : Swift 6.0+ (Xcode 16+)

---

## 2. Apple Docs MCP

Documentation Apple complète avec support visionOS.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : SwiftUI, UIKit, APIs Swift/Objective-C, WWDC sessions, visionOS

| Ressource | Lien |
|-----------|------|
| GitHub | [kimsungwhee/apple-docs-mcp](https://github.com/kimsungwhee/apple-docs-mcp) |

---

## 3. mcp-swift-sdk (gsabran)

SDK Swift alternatif avec implémentation client complète.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Client MCP complet, connexion à tout serveur MCP

| Ressource | Lien |
|-----------|------|
| GitHub | [gsabran/mcp-swift-sdk](https://github.com/gsabran/mcp-swift-sdk) |

---

## 4. Memory MCP Server (Swift)

Implémentation Swift du serveur de mémoire avec graphe de connaissances.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Mémoire persistante, optimisé macOS, installation one-liner

| Ressource | Lien |
|-----------|------|
| GitHub | [okooo5km/memory-mcp-server](https://github.com/okooo5km/memory-mcp-server) |

---

## 5. MCP Template (Swift)

Template pour créer facilement des serveurs MCP en Swift.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Template EasyMCP, gestion lifecycle, App Store safe

| Ressource | Lien |
|-----------|------|
| Article | [Building a MCP server in Swift](https://adamwulf.me/2025/03/building-a-mcp-server-in-swift/) |

---

# MCP Développement Python

Serveurs MCP pour l'écosystème Python et ses frameworks.

## 1. FastMCP

Le framework Python de référence pour créer des serveurs MCP.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (intégré au SDK) |

**Fonctionnalités** : Création servers/clients, outils, ressources, prompts, code Pythonique

| Ressource | Lien |
|-----------|------|
| GitHub | [jlowin/fastmcp](https://github.com/jlowin/fastmcp) |
| PyPI | [fastmcp](https://pypi.org/project/fastmcp/) |
| Documentation | [gofastmcp.com](https://gofastmcp.com) |

```bash
pip install fastmcp
```

---

## 2. FastAPI-MCP

Convertit automatiquement les endpoints FastAPI en outils MCP.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Conversion automatique endpoints, support authentification, extension native FastAPI

| Ressource | Lien |
|-----------|------|
| GitHub | [tadata-org/fastapi_mcp](https://github.com/tadata-org/fastapi_mcp) |
| PyPI | [fastapi-mcp](https://pypi.org/project/fastapi-mcp/) |

```bash
pip install fastapi-mcp
```

---

## 3. Django MCP Server

Extension Django pour exposer apps et APIs via MCP.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Exposition modèles Django, conversion DRF APIs, WSGI/ASGI, OAuth2

| Ressource | Lien |
|-----------|------|
| GitHub | [omarbenhamid/django-mcp-server](https://github.com/omarbenhamid/django-mcp-server) |
| Guide | [MCP Server Django Implementation](https://docs.agentinterviews.com/blog/mcp-server-django-implementation/) |

---

## 4. Python SDK MCP (Officiel)

Le SDK Python officiel pour le Model Context Protocol.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Implémentation complète MCP, async/await, transports stdio/HTTP

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/python-sdk](https://github.com/modelcontextprotocol/python-sdk) |
| PyPI | [@modelcontextprotocol/sdk](https://pypi.org/project/mcp/) |

```bash
pip install mcp
```

---

## 5. Jupyter MCP

Intégration MCP pour les notebooks Jupyter.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Exécution notebooks, gestion kernels, visualisations

---

# MCP Design d'IHM

Serveurs MCP pour le design UI/UX et l'intégration avec les outils de design.

## 1. Figma MCP Server (Officiel)

Le serveur MCP officiel de Figma pour l'intégration design-to-code.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Figma) |

**Fonctionnalités** : Métadonnées design, design tokens, contraintes layout, génération code

| Ressource | Lien |
|-----------|------|
| Documentation | [developers.figma.com/docs/figma-mcp-server](https://developers.figma.com/docs/figma-mcp-server/) |
| Blog | [Introducing Figma MCP Server](https://www.figma.com/blog/introducing-figma-mcp-server/) |

> [!TIP]
> Disponible en mode Remote (hébergé Figma) ou Desktop (local via app Figma).

---

## 2. Figma Context MCP (Framelink)

Optimisé pour fournir le contexte de design aux agents IA.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Simplification réponses API, layout et styling optimisés, intégration Cursor

| Ressource | Lien |
|-----------|------|
| GitHub | [GLips/Figma-Context-MCP](https://github.com/GLips/Figma-Context-MCP) |

---

## 3. Cursor Talk to Figma

Contrôle direct de Figma via commandes en langage naturel.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : ~20 opérations Figma, création formes, modification texte, gestion couleurs

---

## 4. Storybook MCP

Intégration avec Storybook pour les composants UI.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Accès aux stories, documentation composants, variants

---

## 5. Design Tokens MCP

Gestion des design tokens pour la cohérence UI.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐ |
| Documentation | 📄 Minimale |
| Installation | 🟡 Moyenne |
| Fiabilité | 🧪 Expérimental |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Tokens couleurs/typographie/espacement, export multi-format

---

# MCP JavaScript/TypeScript

Serveurs MCP pour l'écosystème JavaScript et TypeScript.

## 1. TypeScript SDK MCP (Officiel)

Le SDK officiel pour créer des serveurs et clients MCP en TypeScript.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Client/serveur MCP complet, transports stdio/HTTP, middlewares Express/Hono

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/typescript-sdk](https://github.com/modelcontextprotocol/typescript-sdk) |
| npm | [@modelcontextprotocol/sdk](https://www.npmjs.com/package/@modelcontextprotocol/sdk) |

```bash
npm install @modelcontextprotocol/sdk zod
```

---

## 2. MCP-Use (TypeScript)

Framework MCP avec focus sur l'expérience développeur.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Client/Server SDK, React hooks, UI widgets, inspector intégré

| Ressource | Lien |
|-----------|------|
| GitHub | [mcp-use/mcp-use-ts](https://github.com/mcp-use/mcp-use-ts) |

```bash
npx create-mcp-use-app my-mcp-app
```

---

## 3. React MCP

Création et modification d'applications React via Claude.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Création apps React, templates TypeScript/PWA, intégration Claude Desktop

| Ressource | Lien |
|-----------|------|
| GitHub | [kalivaraprasad-gonapa/react-mcp](https://github.com/kalivaraprasad-gonapa/react-mcp) |

---

## 4. Node.js MCP Middleware

Middleware officiel pour les applications Node.js.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Transport HTTP Streamable, helpers Express/Hono

| Ressource | Lien |
|-----------|------|
| npm | [@modelcontextprotocol/node](https://www.npmjs.com/package/@modelcontextprotocol/node) |

---

## 5. Azure Functions MCP (TypeScript)

Déploiement de serveurs MCP sur Azure Functions.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Microsoft) |

**Fonctionnalités** : Déploiement cloud, debugging local, azd up

| Ressource | Lien |
|-----------|------|
| Documentation | [Microsoft Learn](https://learn.microsoft.com/en-us/azure/developer/ai/build-mcp-server-ts) |

---

# MCP Bases de données

Serveurs MCP pour l'interaction avec les bases de données.

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
| Alternative | [crystaldba/postgres-mcp](https://github.com/crystaldba/postgres-mcp) |

```bash
claude mcp add postgres -- npx -y @modelcontextprotocol/server-postgres \
  postgresql://user:password@localhost:5432/database
```

---

## 2. MongoDB MCP Server (Officiel)

Le serveur MCP officiel de MongoDB.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (MongoDB) |

**Fonctionnalités** : Atlas/Community/Enterprise, opérations CRUD, langage naturel

| Ressource | Lien |
|-----------|------|
| GitHub | [mongodb-js/mongodb-mcp-server](https://github.com/mongodb-js/mongodb-mcp-server) |
| Documentation | [MongoDB MCP Server Docs](https://www.mongodb.com/docs/mcp-server/get-started/) |
| Blog | [Announcing MongoDB MCP Server](https://www.mongodb.com/company/blog/announcing-mongodb-mcp-server) |

---

## 3. Redis MCP Server (Officiel)

Le serveur MCP officiel de Redis.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Redis) |

**Fonctionnalités** : Hashes, lists, sets, sorted sets, streams, recherche

| Ressource | Lien |
|-----------|------|
| GitHub | [redis/mcp-redis](https://github.com/redis/mcp-redis) |

---

## 4. Multi-Database MCP Server

Support de 40+ bases de données via une interface unifiée.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : PostgreSQL, MySQL, MongoDB, Redis, SQLite, introspection schéma

| Ressource | Lien |
|-----------|------|
| GitHub | [Nam088/mcp-database-server](https://github.com/Nam088/mcp-database-server) |

---

## 5. SQLite MCP

Support des bases de données SQLite.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Requêtes SQL, gestion fichiers .db, mode lecture/écriture

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../sqlite](https://github.com/modelcontextprotocol/servers/tree/main/src/sqlite) |

---

# MCP DevOps & Infrastructure

Serveurs MCP pour les opérations DevOps et la gestion d'infrastructure.

## 1. Docker MCP (Officiel)

Le serveur MCP officiel de Docker.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Docker) |

**Fonctionnalités** : Build/run containers, inspection, génération Dockerfiles, sécurité

| Ressource | Lien |
|-----------|------|
| Documentation | [Docker MCP](https://www.docker.com/blog/the-model-context-protocol-simplifying-building-ai-apps-with-anthropic-claude-desktop-and-docker/) |

---

## 2. Kubernetes MCP Server

Serveur MCP natif pour Kubernetes et OpenShift.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Red Hat) |

**Fonctionnalités** : Multi-clusters, API native (pas kubectl wrapper), Linux/macOS/Windows

| Ressource | Lien |
|-----------|------|
| GitHub | [containers/kubernetes-mcp-server](https://github.com/containers/kubernetes-mcp-server) |

---

## 3. Argo CD MCP Server

Intégration avec Argo CD pour les workflows GitOps.

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

## 4. CircleCI MCP Server

Gestion des pipelines CI/CD CircleCI.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Déclenchement pipelines, monitoring, gestion workflows

---

## 5. Terraform MCP

Infrastructure as Code avec Terraform.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Plan/apply, gestion state, modules

---

# MCP Tests & Qualité

Serveurs MCP pour les tests et l'assurance qualité.

## 1. Playwright MCP (Officiel Microsoft)

Automatisation web et tests via Playwright.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Microsoft) |

**Fonctionnalités** : Automatisation navigateur, arbre d'accessibilité, multi-navigateurs, headless

| Ressource | Lien |
|-----------|------|
| GitHub | [microsoft/playwright-mcp](https://github.com/microsoft/playwright-mcp) |
| npm | [@playwright/mcp](https://www.npmjs.com/package/@playwright/mcp) |

```bash
claude mcp add playwright -- npx @playwright/mcp@latest
```

---

## 2. Selenium MCP Server

Automatisation navigateur via Selenium WebDriver.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Chrome/Firefox, interactions navigateur, bridge frameworks traditionnels

---

## 3. Puppeteer MCP

Automatisation Chrome/Chromium via Puppeteer.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Contrôle Chrome, screenshots, exécution JavaScript

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../puppeteer](https://github.com/modelcontextprotocol/servers/tree/main/src/puppeteer) |

```bash
claude mcp add puppeteer -- npx -y @modelcontextprotocol/server-puppeteer
```

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

**Fonctionnalités** : Tests E2E UI/API, planification IA, génération automatique, debugging

| Ressource | Lien |
|-----------|------|
| Site web | [testsprite.com](https://www.testsprite.com) |

---

## 5. mabl MCP Server

Tests automatisés avec capacités IA mabl.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (mabl) |

**Fonctionnalités** : Interface langage naturel, automatisation workflows, intégration IDE

| Ressource | Lien |
|-----------|------|
| Site web | [mabl MCP Server](https://www.mabl.com/mabl-mcp-server) |

---

# MCP Observabilité & Monitoring

Serveurs MCP pour le monitoring et l'observabilité.

## 1. Datadog MCP Server

Connexion aux données d'observabilité Datadog.

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
| Blog | [Datadog Remote MCP Server](https://www.datadoghq.com/blog/datadog-remote-mcp-server/) |

---

## 2. Grafana MCP Observability

Monitoring MCP via Grafana Cloud.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta (preview) |
| Support | ✅ Officiel (Grafana Labs) |

**Fonctionnalités** : Dashboard MCP, health protocole, analytics outils, sessions

| Ressource | Lien |
|-----------|------|
| Documentation | [Grafana MCP Observability](https://grafana.com/docs/grafana-cloud/monitor-applications/ai-observability/mcp-observability/) |

---

## 3. Grafana Tempo MCP

Accès aux données de tracing distribué via TraceQL.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta (preview) |
| Support | ✅ Officiel (Grafana Labs) |

**Fonctionnalités** : TraceQL queries, exploration services, langage naturel

| Ressource | Lien |
|-----------|------|
| Documentation | [Tempo MCP Server](https://grafana.com/docs/tempo/latest/api_docs/mcp-server/) |

---

## 4. Prometheus MCP

Accès aux métriques Prometheus.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : PromQL queries, métriques, alertes

---

## 5. PagerDuty MCP

Gestion des incidents via PagerDuty.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Gestion incidents, escalation, coordination équipe

---

# MCP Productivité & Communication

Serveurs MCP pour les outils de productivité et communication.

## 1. Notion MCP (Officiel)

Accès sécurisé aux workspaces Notion.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Notion) |

**Fonctionnalités** : Lecture/écriture pages, bases de données, API Markdown optimisée

| Ressource | Lien |
|-----------|------|
| Documentation | [Notion MCP](https://developers.notion.com/docs/mcp) |

---

## 2. Slack MCP Server (Officiel)

Intégration native avec Slack.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Slack) |

**Fonctionnalités** : Monitoring channels, résumés threads, notifications, archivage

| Ressource | Lien |
|-----------|------|
| Blog | [Slack Agentic Era](https://slack.com/blog/news/powering-agentic-collaboration) |
| PulseMCP | [Slack MCP Server](https://www.pulsemcp.com/servers/slack) |

---

## 3. Linear MCP

Gestion de projets et issues avec Linear.

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

## 4. Google Drive MCP

Accès aux fichiers Google Drive.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Lecture fichiers, recherche, métadonnées

---

## 5. Jira MCP

Intégration avec Atlassian Jira.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Issues, projets, sprints, recherche JQL

---

# MCP Contrôle de version

Serveurs MCP pour la gestion de version au-delà de GitHub.

## 1. GitLab MCP Server

Intégration avec GitLab.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Repos, merge requests, issues, pipelines

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../gitlab](https://github.com/modelcontextprotocol/servers/tree/main/src/gitlab) |
| PulseMCP | [GitLab MCP Server](https://www.pulsemcp.com/servers/modelcontextprotocol-gitlab) |

---

## 2. Bitbucket MCP Server

Intégration avec Atlassian Bitbucket.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Workspaces, repos, PRs, commentaires, recherche

| Ressource | Lien |
|-----------|------|
| GitHub | [aashari/mcp-server-atlassian-bitbucket](https://github.com/aashari/mcp-server-atlassian-bitbucket) |
| Alternative | [MatanYemini/bitbucket-mcp](https://github.com/MatanYemini/bitbucket-mcp) |

---

## 3. Git MCP Server (Officiel)

Opérations Git de base.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟢 Simple |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Anthropic) |

**Fonctionnalités** : Clone, commit, push, pull, branches, diff

| Ressource | Lien |
|-----------|------|
| PulseMCP | [Git MCP Server](https://www.pulsemcp.com/servers/modelcontextprotocol-git) |

---

## 4. Azure DevOps MCP

Intégration avec Azure DevOps.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Repos, work items, pipelines, boards

---

## 5. Gitea MCP

Support pour les instances Gitea auto-hébergées.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐ |
| Documentation | 📄 Minimale |
| Installation | 🟡 Moyenne |
| Fiabilité | 🧪 Expérimental |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Repos, issues, PRs, API Gitea

---

# MCP Cloud

Serveurs MCP pour les principales plateformes cloud.

## 1. AWS API MCP Server

Accès aux APIs AWS via MCP.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta (preview) |
| Support | ✅ Officiel (AWS) |

**Fonctionnalités** : Appels API AWS, langage naturel, IAM intégré

> [!NOTE]
> Developer preview lancé juillet 2025

---

## 2. Azure MCP Server

Serveur MCP consolidé pour Azure.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐⭐ |
| Documentation | 📚 Complète |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (Microsoft) |

**Fonctionnalités** : RBAC, Azure Monitor, Cosmos DB, multi-services

| Ressource | Lien |
|-----------|------|
| Documentation | [Microsoft Learn](https://learn.microsoft.com/en-us/azure/developer/ai/build-mcp-server-ts) |

---

## 3. Google Cloud MCP

Accès aux services GCP.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Cloud SQL, Spanner, BigQuery, Vertex AI

---

## 4. Amazon MSK MCP Server

Interface pour Apache Kafka sur AWS.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟢 Active |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | 🛡️ Stable |
| Support | ✅ Officiel (AWS) |

**Fonctionnalités** : Métriques Kafka, gestion clusters, IAM, OpenTelemetry

---

## 5. Cloudflare MCP

Gestion des services Cloudflare.

| Critère | Évaluation |
|---------|------------|
| Maintenance | 🟡 Modérée |
| Popularité | ⭐⭐⭐ |
| Documentation | 📖 Basique |
| Installation | 🟡 Moyenne |
| Fiabilité | ⚠️ Beta |
| Support | 🏠 Communautaire |

**Fonctionnalités** : Workers, KV, R2, DNS

---

# Ressources supplémentaires

## Répertoires de serveurs MCP

| Ressource | Description |
|-----------|-------------|
| [MCP Registry](https://github.com/modelcontextprotocol/servers) | Dépôt officiel Anthropic |
| [Awesome MCP Servers](https://github.com/punkpeye/awesome-mcp-servers) | Liste communautaire |
| [MCP Awesome](https://mcp-awesome.com/) | 1200+ serveurs |
| [PulseMCP](https://www.pulsemcp.com/servers) | 7700+ serveurs |
| [Awesome DevOps MCP](https://github.com/rohitg00/awesome-devops-mcp-servers) | Focus DevOps |

## Documentation officielle

| Ressource | Lien |
|-----------|------|
| Introduction MCP | [anthropic.com/news/model-context-protocol](https://www.anthropic.com/news/model-context-protocol) |
| Qu'est-ce que le MCP ? | [claude.com/blog/what-is-model-context-protocol](https://claude.com/blog/what-is-model-context-protocol) |
| Spécification MCP | [modelcontextprotocol.io](https://modelcontextprotocol.io) |

---

## Bonnes pratiques

> [!TIP]
> **Sélection des MCP** : Choisissez 2-3 MCP correspondant à vos tâches principales. Trop de MCP peuvent ralentir Claude Code.

> [!WARNING]
> **Sécurité** : Testez d'abord les MCP avec des permissions en lecture seule avant d'activer l'écriture. CVE-2025-53110 et CVE-2025-6514 ont révélé des risques d'exécution de code à distance.

> [!IMPORTANT]
> **Critères de sélection** :
> - Privilégiez les MCP officiels (✅) quand disponibles
> - Vérifiez la date du dernier commit
> - Consultez les issues ouvertes sur GitHub
> - Testez en environnement de développement d'abord

---

*Dernière mise à jour : Janvier 2025*
