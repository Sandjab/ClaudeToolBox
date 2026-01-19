# conversation-export

Outil CLI pour exporter les conversations Claude Code en Markdown.

## Description

`conversation-export` permet de :
- Naviguer dans l'historique des conversations Claude Code via une interface TUI
- Lister toutes les conversations disponibles
- Exporter une conversation spécifique en fichier Markdown lisible

## Prérequis

- macOS
- `jq` (parsing JSON) - requis
- `fzf` (recherche floue) - optionnel mais recommandé

### Installation des dépendances

```bash
# jq (requis)
brew install jq

# fzf (optionnel - active la recherche floue)
brew install fzf
```

## Installation

```bash
# Le script est déjà exécutable
./conversation-export

# Ou ajoutez-le à votre PATH
ln -s "$(pwd)/conversation-export" /usr/local/bin/
```

## Utilisation

### Mode interactif

```bash
./conversation-export
```

**Avec fzf** (si installé) :
- Tapez pour filtrer les conversations (recherche floue)
- `↑/↓` : Naviguer dans les résultats
- `Enter` : Exporter la conversation sélectionnée
- `Ctrl+C` : Quitter

**TUI intégré** (sans fzf ou avec `--no-fzf`) :
- `↑/↓` ou `k/j` : Naviguer dans la liste
- `Enter` : Exporter la conversation sélectionnée
- `Page Up/Down` : Navigation rapide
- `q` : Quitter

```bash
# Forcer le TUI intégré même si fzf est installé
./conversation-export --no-fzf
```

### Lister les conversations

```bash
./conversation-export -l
./conversation-export --list
```

Affiche toutes les conversations avec leur numéro, date, projet et titre.

### Exporter une conversation spécifique

```bash
# Export vers un fichier auto-nommé (<slug>.md)
./conversation-export -e 3

# Export vers un fichier spécifique
./conversation-export -e 3 -o ma-conversation.md

# Export avec les blocs de code inclus
./conversation-export -e 3 --with-code

# Export vers stdout
./conversation-export -e 3 -o -
```

### Filtrer par projet

```bash
./conversation-export --project ClaudeToolBox
./conversation-export -l --project deck
```

## Options

| Option | Description |
|--------|-------------|
| (aucune) | Mode interactif (fzf si disponible, sinon TUI) |
| `-l, --list` | Liste les conversations (sans interactivité) |
| `-e, --export <id>` | Exporte la conversation numéro `<id>` |
| `-o, --output <file>` | Fichier de sortie (défaut: `<slug>.md`, `-` pour stdout) |
| `--with-code` | Inclut les blocs de code (défaut: texte seul) |
| `--project <name>` | Filtre par nom de projet |
| `--no-fzf` | Force le TUI intégré (désactive fzf) |
| `-h, --help` | Affiche l'aide |
| `-v, --version` | Affiche la version |

## Format de sortie

Le fichier Markdown généré contient :

```markdown
# Conversation: titre-de-la-conversation

**Projet**: NomDuProjet
**Date**: 2026-01-18

---

**Utilisateur** :

Premier message de l'utilisateur...

*Claude* :

Réponse de Claude...

**Utilisateur** :

Suite de la conversation...
```

## Structure des données Claude Code

Les conversations sont stockées dans :
```
~/.claude/projects/<chemin-projet-encodé>/<session-id>.jsonl
```

Chaque fichier `.jsonl` contient une ligne JSON par événement :
- `type: "user"` - Message de l'utilisateur
- `type: "assistant"` - Réponse de Claude
- `type: "progress"` - Événements de progression
- `type: "file-history-snapshot"` - Snapshots de fichiers

## Exemples

Voir le répertoire `examples/` pour des exemples de conversations exportées.

## Limitations

- Les pensées de Claude (`thinking`) sont exclues par défaut
- Les appels d'outils (`tool_use`) sont exclus par défaut
- Seul le contenu textuel est exporté (pas les images)
