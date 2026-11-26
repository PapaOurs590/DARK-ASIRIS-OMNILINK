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
- Accès distant via tunnel MCP

### 🛠️ Développement

Selon la plateforme et les outils installés sur la machine, OMNILINK peut interagir avec :

- **Git**
- **PowerShell / CMD**
- **Python**
- **Node.js / npm / npx**
- **.NET**
- **CMake**
- **Visual Studio**
- **Xcode / Swift**
- **WSL**
- **Homebrew**
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
- récupérer les sorties de compilation ;
- analyser les erreurs de build.

---

## 🛡️ Coding & Transaction Engine

Les modifications du code peuvent être effectuées avec une couche de sécurité supplémentaire.

Avant une modification, OMNILINK peut créer automatiquement un **snapshot du fichier original**.

### Workflow

**Analyse → Snapshot → Modification → Build → Validation**

Si une modification provoque un échec, le système peut restaurer la version sauvegardée selon le workflow utilisé.

Cela permet à ChatGPT de travailler sur un projet tout en conservant un moyen de revenir à son état précédent.

---

## 🔀 Git

L'utilisation de Git apporte un second niveau de contrôle :

- historique des modifications ;
- comparaison des fichiers ;
- suivi des changements ;
- baseline avant intervention ;
- contrôle du diff après intervention ;
- possibilité de revenir à une version connue du projet.

Pour les projets importants, l'utilisation de Git est fortement recommandée avant de permettre des modifications automatisées.

---

# 🌐 Accès à distance

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

Lorsque l'ordinateur et le tunnel OMNILINK sont actifs, ChatGPT peut piloter les opérations exposées par OMNILINK depuis un autre appareil compatible.

Cela permet notamment d'utiliser ChatGPT depuis un téléphone tout en exécutant les opérations de développement sur l'ordinateur distant.

---

# 📦 Téléchargement

Téléchargez la version correspondant à votre système depuis le dépôt ou la section **Releases** :

### 🪟 Windows

`DARK-ASIRIS-OMNILINK-WINDOWS-v1.0.zip`

### 🍎 macOS

`DARK-ASIRIS-OMNILINK-MAC-v1.0.zip`

---

# 🪟 Installation Windows

## Prérequis

- Windows 10 ou Windows 11
- Python 3
- Connexion Internet
- Compte ChatGPT/OpenAI compatible avec les tunnels MCP
- Votre propre **Runtime API Key**
- Votre propre **Tunnel ID**

Les outils supplémentaires comme Git, .NET, Node.js ou Visual Studio ne sont nécessaires que pour les fonctionnalités qui les utilisent.

---

## 1. Extraire l'archive

Téléchargez :

`DARK-ASIRIS-OMNILINK-WINDOWS-v1.0.zip`

Puis extrayez complètement son contenu dans un dossier local.

---

## 2. Ouvrir PowerShell

Ouvrez PowerShell dans le dossier extrait.

Autorisez temporairement l'exécution des scripts pour cette session :

```powershell
Set-ExecutionPolicy -Scope Process Bypass
```

Cette modification concerne uniquement la session PowerShell actuelle.

---

## 3. Installer OMNILINK

Exécutez :

```powershell
.\SETUP-OMNILINK.ps1
```

Le programme d'installation prépare automatiquement :

- l'environnement Python ;
- les dépendances MCP ;
- le tunnel-client ;
- les dossiers nécessaires ;
- le profil OMNILINK ;
- la configuration locale.

Pendant l'installation, OMNILINK demandera notamment :

- votre **Tunnel ID** ;
- votre **Runtime API Key**.

> ⚠️ Utilisez toujours **votre propre Tunnel ID et votre propre Runtime API Key**.

Ne partagez jamais ceux d'une autre personne.

---

## 4. Démarrer OMNILINK

Une fois l'installation terminée :

```powershell
.\START-OMNILINK.ps1
```

Le serveur MCP local et le tunnel OMNILINK seront alors démarrés.

Le serveur MCP écoute localement sur :

`127.0.0.1:8000`

---

## 5. Connecter ChatGPT

Dans ChatGPT, créez ou configurez votre plugin/connexion MCP :

**Nom recommandé :**

`DARK ASIRIS // OMNILINK WINDOWS`

**Connexion :**

`Tunnel`

**Tunnel :**

Sélectionnez votre propre tunnel OMNILINK.

**Authentification :**

`Sans authentification`

Une fois connecté, ChatGPT pourra découvrir les outils exposés par votre instance locale.

---

## 6. Arrêter OMNILINK

Pour arrêter proprement l'instance Windows :

```powershell
.\STOP-OMNILINK.ps1
```

---

## 🔐 Vérification Windows

### SHA-256

```text
9404d524b0df271139e943127195bb422b75f1e957e606ef7cd4bc3926d7f2b7
```

Vous pouvez vérifier l'intégrité du ZIP avec PowerShell :

```powershell
Get-FileHash ".\DARK-ASIRIS-OMNILINK-WINDOWS-v1.0.zip" -Algorithm SHA256
```

Le hash retourné doit correspondre exactement à celui indiqué ci-dessus.

---

# 🍎 Installation macOS

## Compatibilité

La version macOS est prévue pour :

- **Apple Silicon** : M1, M2, M3, M4, M5
- **Mac Intel**

Le setup détecte automatiquement l'architecture du Mac afin de sélectionner le composant tunnel correspondant.

---

## Prérequis

- macOS
- Python 3
- Connexion Internet
- Compte ChatGPT/OpenAI compatible avec les tunnels MCP
- Votre propre **Runtime API Key**
- Votre propre **Tunnel ID**

Xcode, Swift, Homebrew, Git, Node.js, .NET et CMake sont détectés lorsqu'ils sont présents.

---

## 1. Extraire l'archive

Téléchargez :

`DARK-ASIRIS-OMNILINK-MAC-v1.0.zip`

Puis extrayez complètement l'archive.

---

## 2. Installer OMNILINK

Dans le dossier extrait, effectuez un clic droit sur :

`SETUP.command`

puis choisissez :

**Ouvrir**

Le programme prépare automatiquement l'environnement OMNILINK et télécharge le tunnel-client correspondant à l'architecture du Mac.

Pendant l'installation, utilisez :

- **votre propre Tunnel ID** ;
- **votre propre Runtime API Key**.

> ⚠️ N'utilisez jamais le Tunnel ID ou la Runtime API Key d'une autre personne.

La Runtime API Key est stockée dans le **Trousseau macOS**.

---

## 3. Démarrer OMNILINK

Double-cliquez sur :

`START-OMNILINK.command`

Le serveur MCP local sera démarré sur :

`127.0.0.1:8000`

puis le tunnel sera connecté.

---

## 4. Connecter ChatGPT

Créez votre connexion dans ChatGPT :

**Nom recommandé :**

`DARK ASIRIS // OMNILINK MAC`

**Connexion :**

`Tunnel`

**Tunnel :**

Sélectionnez le tunnel créé pour votre Mac.

**Authentification :**

`Sans authentification`

---

## 5. Arrêter OMNILINK

Pour arrêter l'instance macOS :

`STOP-OMNILINK.command`

---

## 🔐 Vérification macOS

### SHA-256

```text
dc18077db5f5d4045d7d73f468cf87d2c8e882a8a02949613932f093a99e5b77
```

Sur macOS, le fichier peut être vérifié avec :

```bash
shasum -a 256 DARK-ASIRIS-OMNILINK-MAC-v1.0.zip
```

Le hash obtenu doit être identique à celui indiqué ci-dessus.

---

# 🔐 Sécurité

OMNILINK n'a pas vocation à fournir un accès administrateur illimité à ChatGPT.

Le projet privilégie :

- des outils MCP aux responsabilités précises ;
- des commandes contrôlées ;
- des snapshots avant certaines éditions ;
- la validation des chemins ;
- des limites sur certaines opérations ;
- la journalisation des modifications ;
- Git comme niveau de protection supplémentaire ;
- un serveur MCP accessible uniquement localement ;
- un tunnel sortant vers ChatGPT.

---

## ⚠️ Secrets et identifiants

Ne publiez **jamais** dans GitHub :

- Runtime API Key ;
- clés API privées ;
- tokens GitHub ;
- mots de passe ;
- fichiers `.env` contenant des secrets ;
- identifiants personnels ;
- fichiers de configuration générés contenant des informations sensibles.

Chaque utilisateur d'OMNILINK doit utiliser **ses propres identifiants et son propre tunnel**.

---

# 📱 Utilisation à distance

Lorsque :

- l'ordinateur est allumé ;
- OMNILINK fonctionne ;
- le tunnel est connecté ;
- le plugin est disponible dans ChatGPT ;

les opérations exposées par OMNILINK peuvent être pilotées depuis ChatGPT sur un autre appareil compatible.

Le travail est exécuté sur la machine hébergeant OMNILINK.

---

# ⚠️ Projet en développement

DARK ASIRIS // OMNILINK est actuellement en développement actif.

Certaines fonctionnalités peuvent évoluer rapidement et les versions Windows et macOS peuvent ne pas proposer exactement les mêmes outils.

Il est fortement recommandé :

1. d'utiliser Git ;
2. d'avoir une baseline propre ;
3. de vérifier les diffs ;
4. de conserver les snapshots ;
5. de valider les builds après modification.

---

# 📜 Licence

**Aucune licence open source n'est actuellement accordée.**

La publication du code ou des packages ne constitue pas automatiquement une autorisation de modification, redistribution ou utilisation commerciale.

**Tous droits réservés sauf autorisation explicite du propriétaire du projet.**

---

# 🖤 DARK ASIRIS

**DARK ASIRIS // OMNILINK**

*Your machine. Your projects. Your control.*
