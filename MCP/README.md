# MCP - Model Context Protocol Servers

Liste des 10 serveurs MCP (Model Context Protocol) les plus recommandés pour développer avec Claude Code.

Le Model Context Protocol (MCP) est un standard ouvert introduit par Anthropic en novembre 2024 pour standardiser l'intégration des systèmes d'IA avec des outils externes, des systèmes et des sources de données. Souvent décrit comme "l'USB-C de l'IA", les serveurs MCP agissent comme des ponts permettant aux agents IA d'effectuer diverses tâches.

---

## 1. GitHub MCP Server

**Description** : Le serveur MCP officiel de GitHub permet à Claude Code d'interagir directement avec l'écosystème GitHub. Il offre un accès complet aux dépôts, issues, pull requests, actions et fonctionnalités de sécurité. C'est probablement le MCP le plus essentiel pour tout développeur.

**Fonctionnalités principales** :
- Gestion des commits, branches et pull requests
- Lecture et création d'issues
- Déclenchement de workflows CI/CD
- Analyse de commits

| Ressource | Lien |
|-----------|------|
| GitHub | [github/github-mcp-server](https://github.com/github/github-mcp-server) |
| Guide d'installation Claude | [install-claude.md](https://github.com/github/github-mcp-server/blob/main/docs/installation-guides/install-claude.md) |

**Installation pour Claude Code** :
```bash
claude mcp add github -e GITHUB_PERSONAL_ACCESS_TOKEN=<your-token> -- \
  docker run -i --rm -e GITHUB_PERSONAL_ACCESS_TOKEN ghcr.io/github/github-mcp-server
```

---

## 2. Context7

**Description** : Context7 injecte de la documentation à jour et spécifique aux versions directement dans le contexte du prompt. Cela garantit que l'IA utilise des informations précises provenant des bibliothèques actuelles plutôt que des données d'entraînement potentiellement obsolètes.

**Fonctionnalités principales** :
- Documentation à jour pour les bibliothèques
- Exemples de code spécifiques aux versions
- Recherche intelligente dans la documentation

| Ressource | Lien |
|-----------|------|
| GitHub | [upstash/context7](https://github.com/upstash/context7) |
| Site web | [context7.com](https://context7.com) |
| Documentation | [context7.com/docs/installation](https://context7.com/docs/installation) |

**Installation pour Claude Code** :
```bash
claude mcp add context7 -- npx -y @upstash/context7-mcp
```

> [!TIP]
> Ajoutez `use context7` à vos prompts pour activer l'utilisation du serveur MCP.

---

## 3. Sequential Thinking

**Description** : Le serveur Sequential Thinking révolutionne l'approche de Claude Code face aux problèmes complexes en introduisant un processus de réflexion structuré et réflexif. Il permet de travailler méthodiquement à travers les problèmes, de réviser les approches si nécessaire et de maintenir le contexte tout au long du raisonnement.

**Fonctionnalités principales** :
- Résolution de problèmes étape par étape
- Capacité de révision et de branchement
- Maintien du contexte sur des chaînes de raisonnement étendues

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../sequentialthinking](https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking) |

**Installation pour Claude Code** :
```bash
claude mcp add sequentialthinking -- npx -y @modelcontextprotocol/server-sequentialthinking
```

---

## 4. Playwright

**Description** : Le serveur MCP Playwright officiel de Microsoft révolutionne l'automatisation web et les tests en permettant à Claude Code d'interagir avec des applications web. Essentiel pour les développeurs construisant des tests end-to-end ou automatisant des workflows web.

**Fonctionnalités principales** :
- Automatisation de navigateur complète
- Capture d'écran et interaction avec les éléments
- Support multi-navigateurs (Chrome, Firefox, Safari)
- Mode headless ou avec interface

| Ressource | Lien |
|-----------|------|
| GitHub | [microsoft/playwright-mcp](https://github.com/microsoft/playwright-mcp) |
| npm | [@playwright/mcp](https://www.npmjs.com/package/@playwright/mcp) |

**Installation pour Claude Code** :
```bash
claude mcp add playwright -- npx @playwright/mcp@latest
```

---

## 5. Filesystem

**Description** : Serveur MCP officiel fournissant des opérations sécurisées sur les fichiers avec des contrôles d'accès configurables. Idéal pour les opérations de code local, le traitement par lots de fichiers et les migrations de projets.

**Fonctionnalités principales** :
- Lecture/écriture de fichiers sécurisée
- Navigation dans l'arborescence de répertoires
- Contrôle d'accès granulaire
- Support des chemins configurables

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../filesystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) |

**Installation pour Claude Code** :
```bash
claude mcp add filesystem -- npx -y @modelcontextprotocol/server-filesystem /chemin/vers/repertoire
```

---

## 6. Memory (Knowledge Graph)

**Description** : Système de mémoire persistante basé sur un graphe de connaissances local. Permet à Claude de se souvenir d'informations sur l'utilisateur et le projet à travers les sessions de conversation.

**Fonctionnalités principales** :
- Mémoire persistante entre les sessions
- Graphe de connaissances local
- Stockage de contexte utilisateur

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../memory](https://github.com/modelcontextprotocol/servers/tree/main/src/memory) |

**Installation pour Claude Code** :
```bash
claude mcp add memory -- npx -y @modelcontextprotocol/server-memory
```

---

## 7. Brave Search

**Description** : Serveur MCP officiel de Brave intégrant l'API Brave Search. Fournit des capacités de recherche web complètes incluant recherche web, locale, images, vidéos, actualités et résumés alimentés par l'IA.

**Fonctionnalités principales** :
- Recherche web et locale
- Recherche d'images et de vidéos
- Recherche d'actualités
- Résumés IA

| Ressource | Lien |
|-----------|------|
| GitHub | [brave/brave-search-mcp-server](https://github.com/brave/brave-search-mcp-server) |

**Installation pour Claude Code** :
```bash
claude mcp add brave-search -e BRAVE_API_KEY=<your-api-key> -- \
  npx -y @brave/brave-search-mcp-server
```

> [!NOTE]
> Une clé API Brave Search est requise. Obtenez-en une sur [brave.com/search/api](https://brave.com/search/api/).

---

## 8. PostgreSQL

**Description** : Connecte Claude à des bases de données PostgreSQL pour interroger des données, gérer des schémas et analyser le contenu de la base de données en langage naturel. Idéal pour l'analyse de données, l'optimisation de base de données et le développement backend.

**Fonctionnalités principales** :
- Requêtes en lecture (mode sécurisé par défaut)
- Gestion des schémas
- Analyse de performances
- Support du pooling de connexions

| Ressource | Lien |
|-----------|------|
| GitHub (officiel) | [modelcontextprotocol/servers/.../postgres](https://github.com/modelcontextprotocol/servers/tree/main/src/postgres) |
| GitHub (Postgres MCP Pro) | [crystaldba/postgres-mcp](https://github.com/crystaldba/postgres-mcp) |

**Installation pour Claude Code** :
```bash
claude mcp add postgres -- npx -y @modelcontextprotocol/server-postgres \
  postgresql://user:password@localhost:5432/database
```

---

## 9. Puppeteer

**Description** : Serveur MCP offrant des capacités d'automatisation de navigateur via Puppeteer. Permet à Claude d'interagir avec des pages web, de prendre des captures d'écran et d'exécuter du JavaScript dans un environnement de navigateur réel.

**Fonctionnalités principales** :
- Contrôle complet du navigateur Chrome/Chromium
- Capture d'écran
- Exécution de JavaScript
- Navigation et interaction avec les pages

| Ressource | Lien |
|-----------|------|
| GitHub (officiel) | [modelcontextprotocol/servers/.../puppeteer](https://github.com/modelcontextprotocol/servers/tree/main/src/puppeteer) |
| GitHub (Claude optimisé) | [jaenster/puppeteer-mcp-claude](https://github.com/jaenster/puppeteer-mcp-claude) |

**Installation pour Claude Code** :
```bash
claude mcp add puppeteer -- npx -y @modelcontextprotocol/server-puppeteer
```

---

## 10. Fetch

**Description** : Serveur MCP de référence pour la récupération de contenu web et sa conversion pour une utilisation efficace par les LLM. Transforme le contenu HTML en markdown optimisé pour le contexte.

**Fonctionnalités principales** :
- Récupération de pages web
- Conversion HTML vers Markdown
- Optimisation du contenu pour les LLM
- Support des en-têtes personnalisés

| Ressource | Lien |
|-----------|------|
| GitHub | [modelcontextprotocol/servers/.../fetch](https://github.com/modelcontextprotocol/servers/tree/main/src/fetch) |

**Installation pour Claude Code** :
```bash
claude mcp add fetch -- npx -y @modelcontextprotocol/server-fetch
```

---

## Ressources supplémentaires

### Répertoires de serveurs MCP

| Ressource | Description |
|-----------|-------------|
| [MCP Registry](https://github.com/modelcontextprotocol/servers) | Dépôt officiel des serveurs de référence |
| [Awesome MCP Servers](https://github.com/punkpeye/awesome-mcp-servers) | Liste communautaire de serveurs MCP |
| [MCP Awesome](https://mcp-awesome.com/) | Répertoire de 1200+ serveurs MCP |
| [MCPcat](https://mcpcat.io/guides/best-mcp-servers-for-claude-code/) | Guide des meilleurs MCP pour Claude Code |

### Documentation officielle

| Ressource | Lien |
|-----------|------|
| Introduction au MCP | [anthropic.com/news/model-context-protocol](https://www.anthropic.com/news/model-context-protocol) |
| Qu'est-ce que le MCP ? | [claude.com/blog/what-is-model-context-protocol](https://claude.com/blog/what-is-model-context-protocol) |

---

## Bonnes pratiques

> [!TIP]
> **Sélection des MCP** : Choisissez 2-3 MCP correspondant à vos tâches de développement principales plutôt que d'installer tout. Trop de MCP peuvent ralentir le démarrage de Claude Code.

> [!IMPORTANT]
> **Critères de sélection** : Privilégiez les MCP qui sont :
> - Maintenus et de confiance
> - Offrant de réels gains de productivité
> - Faciles à intégrer
> - Bien documentés

---

*Dernière mise à jour : Janvier 2025*
