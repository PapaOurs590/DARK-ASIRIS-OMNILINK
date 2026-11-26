# ⚡ DARK ASIRIS // OMNILINK

**Passerelle MCP sécurisée entre ChatGPT et votre environnement de développement local.**

DARK ASIRIS // OMNILINK permet à ChatGPT d'interagir avec une machine **Windows ou macOS** à travers une connexion MCP contrôlée.

L'objectif est simple : pouvoir travailler sur ses projets locaux avec ChatGPT, y compris à distance, tout en conservant des mécanismes de contrôle, de sauvegarde et de validation avant et après les modifications.

---

## 🚀 Fonctionnalités

### 💻 Accès à l'environnement local

- Informations système et matérielles
- Navigation dans les fichiers et dossiers
- Lecture et recherche de fichiers
- Création et modification contrôlée de fichiers
- Détection des outils de développement installés
- Exécution d'actions locales autorisées

### 🛠️ Développement

OMNILINK peut interagir avec différents outils selon la plateforme :

- **Git**
- **PowerShell / CMD**
- **Python**
- **Node.js / npm / npx**
- **.NET**
- **CMake**
- **Visual Studio**
- **Xcode / Swift**
- **WSL**
- Outils système Windows et macOS

---

## 🧠 Project Engine

Le moteur de projet permet à ChatGPT de :

- détecter les projets présents sur la machine ;
- analyser leur structure ;
- lire les fichiers source ;
- vérifier l'état Git ;
- lancer des builds ;
- exécuter des tests compatibles ;
- récupérer et analyser les erreurs de compilation.

---

## 🛡️ Coding & Transaction Engine

Les modifications de code peuvent être effectuées avec une couche de sécurité supplémentaire.

Avant une modification, OMNILINK peut créer automatiquement un **snapshot du fichier original**.

Workflow :

**Analyse → Snapshot → Modification → Build → Validation**

Si une modification provoque un échec, le système peut restaurer la version sauvegardée selon le workflow utilisé.

Cela permet à ChatGPT de travailler sur un projet tout en conservant un moyen de revenir à l'état précédent.

---

## 🔀 Git

L'utilisation de Git apporte un second niveau de contrôle :

- historique des modifications ;
- comparaison des fichiers ;
- suivi des changements ;
- baseline avant intervention ;
- possibilité de revenir à une version connue du projet.

---

## 🌐 Accès à distance

OMNILINK utilise un **tunnel MCP sécurisé** entre ChatGPT et le serveur MCP exécuté localement.

```text
ChatGPT
   │
   ▼
DARK ASIRIS // OMNILINK
   │
   ▼
Secure MCP Tunnel
   │
   ▼
Ordinateur local
   │
   ├── Fichiers
   ├── Git
   ├── Builds
   ├── Outils de développement
   └── Projets
```

Lorsque la machine et le tunnel OMNILINK sont actifs, les outils peuvent également être utilisés depuis ChatGPT sur un autre appareil compatible, notamment pour piloter des tâches exécutées sur la machine distante.

---

## 🪟 Windows

La version Windows prend notamment en charge :

- PowerShell
- CMD
- Git
- .NET
- Visual Studio
- Python
- Node.js
- npm / npx
- CMake
- WSL
- NVIDIA
- inventaire matériel
- gestion et compilation de projets

---

## 🍎 macOS

Une version dédiée à macOS est également disponible.

Elle prévoit notamment :

- Apple Silicon et Mac Intel
- Git
- Python
- Node.js
- .NET
- Swift
- Xcode
- CMake
- Homebrew
- détection de projets
- fichiers et dossiers
- snapshots
- builds compatibles

Le programme d'installation détecte automatiquement l'architecture du Mac afin de sélectionner les composants adaptés.

---

## 🔐 Sécurité

OMNILINK n'a pas vocation à fournir un accès administrateur illimité à ChatGPT.

Le projet privilégie :

- des outils MCP aux responsabilités précises ;
- des commandes autorisées explicitement ;
- des snapshots avant édition ;
- la validation des chemins ;
- des limites sur certaines opérations ;
- la journalisation des modifications ;
- Git comme niveau de protection supplémentaire.

Les clés d'API, secrets et identifiants personnels **ne doivent jamais être intégrés au dépôt GitHub**.

---

## 📦 Installation

Les packages d'installation seront disponibles dans la section **Releases** du dépôt.

### macOS

1. Télécharger la dernière version macOS.
2. Extraire l'archive.
3. Exécuter `SETUP.command`.
4. Configurer son propre Tunnel ID et sa propre Runtime API Key.
5. Démarrer OMNILINK avec `START-OMNILINK.command`.
6. Connecter le tunnel à ChatGPT.

### Windows

La distribution automatisée Windows sera publiée séparément.

---

## ⚠️ Projet en développement

DARK ASIRIS // OMNILINK est actuellement en développement actif.

Certaines fonctionnalités peuvent évoluer rapidement et les différentes plateformes peuvent ne pas encore proposer exactement les mêmes outils.

Il est fortement recommandé d'utiliser **Git et les snapshots OMNILINK** avant toute modification importante.

---

## 📜 Licence

**Aucune licence open source n'est actuellement accordée.**

Le code source est visible publiquement à des fins de consultation et de développement du projet.

Tous droits réservés sauf autorisation explicite du propriétaire du projet.

---

## 🖤 DARK ASIRIS

**DARK ASIRIS // OMNILINK**

*Your machine. Your projects. Your control.*
