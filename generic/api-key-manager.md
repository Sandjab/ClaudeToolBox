# API Key Manager

Gestionnaire sécurisé de clés d'API pour macOS utilisant le Trousseau (Keychain).

## Description

Cet outil permet de stocker des clés d'API de manière sécurisée dans le Trousseau macOS et configure automatiquement leur export en tant que variables d'environnement dans le shell zsh.

## Fonctionnalités

- Stockage sécurisé dans le Trousseau macOS
- Export automatique en variables d'environnement
- Mode interactif avec saisie masquée
- Gestion complète : ajout, liste, suppression

## Prérequis

- macOS
- Shell zsh

## Installation

Rendre le script exécutable :

```bash
chmod +x api-key-manager
```

## Utilisation

### Mode interactif

```bash
./api-key-manager
```

Le script demande le nom et la valeur de la clé (saisie masquée).

### Mode direct

```bash
./api-key-manager NOM_CLE valeur_secrete
```

### Lister les clés configurées

```bash
./api-key-manager -l
./api-key-manager --list
```

### Supprimer une clé

```bash
./api-key-manager -d NOM_CLE
./api-key-manager --delete NOM_CLE
```

### Aide

```bash
./api-key-manager -h
./api-key-manager --help
```

## Exemples

```bash
# Ajouter une clé OpenAI
./api-key-manager OPENAI_API_KEY sk-xxxxxxxxxxxxxxxx

# Ajouter une clé Anthropic en mode interactif
./api-key-manager
# > Nom: ANTHROPIC_API_KEY
# > Valeur: (saisie masquée)

# Lister toutes les clés
./api-key-manager -l

# Supprimer une clé
./api-key-manager -d OPENAI_API_KEY
```

## Fonctionnement technique

1. **Stockage** : Les clés sont stockées dans le Trousseau macOS avec le préfixe `api-key-`
2. **Configuration** : Un fichier `~/.api_keys.zsh` est créé avec les commandes d'export
3. **Chargement** : Le fichier est sourcé automatiquement dans `~/.zshrc`
4. **Récupération** : À chaque ouverture de terminal, les clés sont extraites du Trousseau

## Fichiers

| Fichier | Description |
|---------|-------------|
| `~/.api_keys.zsh` | Contient les exports des variables (permissions 600) |
| `~/.zshrc` | Modifié pour sourcer le fichier de clés |

## Sécurité

- Les clés ne sont jamais stockées en clair sur le disque
- Le fichier `~/.api_keys.zsh` a des permissions restrictives (600)
- La saisie en mode interactif est masquée
- Les clés sont protégées par le Trousseau macOS (chiffrement natif)

> [!CAUTION]
> **Le mode direct expose vos clés d'API** dans l'historique du shell (`~/.zsh_history`, `~/.bash_history`), la table des processus (`ps aux`) et potentiellement les logs système. **Utilisez le mode interactif** pour éviter ce risque.

```bash
# Recommandé : mode interactif (clé masquée)
./api-key-manager

# À éviter : mode direct (clé visible dans l'historique)
./api-key-manager OPENAI_API_KEY sk-xxx
```

Si vous devez utiliser le mode direct, préfixez la commande avec un espace pour éviter l'enregistrement dans l'historique (selon la configuration de votre shell) :

```bash
 ./api-key-manager OPENAI_API_KEY sk-xxx  # espace en début de ligne
```

## Convention de nommage

Les noms de clés doivent respecter le format des variables d'environnement :
- Majuscules uniquement
- Underscores autorisés
- Doit commencer par une lettre ou un underscore

Exemples valides : `OPENAI_API_KEY`, `ANTHROPIC_API_KEY`, `AWS_SECRET_KEY`
