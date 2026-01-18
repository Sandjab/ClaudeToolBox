# ClaudeToolBox

Collection d'outils utilitaires pour macOS.

## Structure

```
ClaudeToolBox/
├── generic/          # Outils génériques multi-usage
│   ├── api-key-manager      # Gestionnaire de clés API (Trousseau macOS)
│   └── api-key-manager.md   # Documentation
└── README.md
```

## Conventions

### Scripts Bash
- Shebang : `#!/bin/bash`
- Variables locales avec `local`
- Validation des entrées utilisateur (regex pour éviter les injections)
- Couleurs : RED, GREEN, YELLOW, NC pour l'affichage
- Fonctions : `info()`, `warn()`, `error()` pour les messages
- Permissions sécurisées : `umask 077` à la création, `chmod 600` pour les fichiers sensibles

### Documentation
- Un fichier `.md` par script
- Utiliser les alertes GitHub (`> [!CAUTION]`, `> [!WARNING]`, etc.) pour les avertissements de sécurité
- Sections : Description, Prérequis, Installation, Utilisation, Sécurité

### Sécurité
- Ne jamais stocker de secrets en clair
- Valider toutes les entrées utilisateur avant utilisation dans sed/grep/commandes
- Préférer le mode interactif avec saisie masquée (`read -s`)
- Avertir l'utilisateur des risques (historique shell, table des processus)

## Langue

- Code : anglais (noms de variables, fonctions)
- Messages utilisateur : français
- Documentation : français
