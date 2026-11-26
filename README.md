# ⚡ DARK ASIRIS // OMNILINK

**Passerelle MCP sécurisée entre ChatGPT et votre environnement de développement local Windows ou macOS.**

DARK ASIRIS // OMNILINK permet à ChatGPT d'interagir avec votre ordinateur à travers un serveur MCP local et un tunnel sécurisé.

L'objectif est de pouvoir travailler avec ChatGPT directement sur vos projets locaux, y compris à distance, tout en conservant des mécanismes de contrôle, de sauvegarde, de validation et de restauration.

---

# 🚀 Fonctionnalités

## 💻 Accès local contrôlé

- Informations système et matérielles
- Navigation dans les fichiers et dossiers
- Lecture et recherche de fichiers
- Création et modification contrôlée
- Détection des outils de développement
- Exécution d'actions locales autorisées
- Accès distant via tunnel MCP

## 🛠️ Développement

Selon votre système et les logiciels installés :

- Git
- PowerShell / CMD
- Python
- Node.js / npm / npx
- .NET
- CMake
- Visual Studio
- Xcode / Swift
- WSL
- Homebrew
- Outils système Windows et macOS

---

# 🧠 Project Engine

OMNILINK peut :

- détecter les projets présents sur la machine ;
- analyser leur structure ;
- lire les fichiers source ;
- inspecter Git ;
- lancer des builds ;
- exécuter des tests compatibles ;
- récupérer les erreurs de compilation ;
- fournir le contexte du projet à ChatGPT.

---

# 🛡️ Coding & Transaction Engine

OMNILINK peut créer automatiquement un **snapshot** avant certaines modifications.

Workflow :

**Analyse → Snapshot → Modification → Build → Validation**

En cas de problème, les snapshots permettent de restaurer les fichiers précédents selon le workflow utilisé.

L'utilisation de **Git** est également fortement recommandée afin de disposer d'un second niveau de protection.

---

# 🌐 Comment fonctionne OMNILINK ?

```text
ChatGPT
   │
   ▼
Plugin OMNILINK
   │
   ▼
Tunnel OpenAI
   │
   ▼
tunnel-client
   │
   ▼
Serveur MCP OMNILINK
   │
   ▼
Votre ordinateur
   │
   ├── Projets
   ├── Fichiers
   ├── Git
   ├── Builds
   └── Outils de développement
```

Le serveur MCP reste local sur votre ordinateur.

---

# 📋 Avant l'installation

Chaque utilisateur doit impérativement disposer de :

1. son propre compte OpenAI compatible ;
2. son propre **Tunnel ID** ;
3. sa propre **Runtime API Key** ;
4. OMNILINK installé sur sa machine.

> ⚠️ Le Tunnel ID et la Runtime API Key sont deux éléments différents.

Ne partagez jamais votre Runtime API Key avec une autre personne.

---

# 🌐 ÉTAPE 1 — Créer votre Tunnel OpenAI

Connectez-vous à votre compte OpenAI Platform.

Ouvrez :

**Settings → Organization → Tunnels**

Lien officiel :

https://platform.openai.com/settings/organization/tunnels

Créez un nouveau tunnel.

Vous pouvez lui donner par exemple le nom :

`DARK ASIRIS // OMNILINK`

ou :

`DARK ASIRIS // OMNILINK - MON PC`

Une fois créé, OpenAI fournit un identifiant ressemblant à :

```text
tunnel_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

C'est votre :

**Tunnel ID**

Copiez-le et conservez-le.

OMNILINK vous le demandera pendant l'installation.

---

# 🔑 ÉTAPE 2 — Créer votre Runtime API Key

Ouvrez ensuite les paramètres des clés API OpenAI :

https://platform.openai.com/settings/organization/api-keys

Créez une clé destinée au fonctionnement du tunnel.

Lorsque les permissions sont configurables, utilisez une clé **Restricted** disposant des permissions nécessaires au tunnel, notamment :

- Tunnels → Read
- Tunnels → Use

La clé obtenue ressemble à une clé OpenAI classique.

C'est votre :

**Runtime API Key**

> ⚠️ Cette clé est secrète.

Ne la mettez jamais :

- dans GitHub ;
- dans le README ;
- dans un message Discord ;
- dans une capture d'écran ;
- dans un fichier public.

Chaque utilisateur doit générer **sa propre Runtime API Key**.

---

# 📦 ÉTAPE 3 — Télécharger OMNILINK

Téléchargez la version correspondant à votre système depuis **Releases**.

## 🪟 Windows

```text
DARK-ASIRIS-OMNILINK-WINDOWS-v1.0.zip
```

## 🍎 macOS

```text
DARK-ASIRIS-OMNILINK-MAC-v1.0.zip
```

Extrayez complètement l'archive avant de continuer.

---

# 🪟 INSTALLATION WINDOWS

## Prérequis

- Windows 10 ou Windows 11
- Python 3
- Connexion Internet
- Tunnel ID créé à l'étape 1
- Runtime API Key créée à l'étape 2

---

## 1. Ouvrir PowerShell

Ouvrez PowerShell dans le dossier OMNILINK extrait.

Exécutez :

```powershell
Set-ExecutionPolicy -Scope Process Bypass
```

Cette autorisation est limitée à la session PowerShell actuelle.

---

## 2. Lancer l'installation

```powershell
.\SETUP-OMNILINK.ps1
```

Le setup prépare automatiquement :

- l'environnement Python ;
- l'environnement virtuel ;
- les dépendances MCP ;
- tunnel-client ;
- la configuration locale ;
- les dossiers OMNILINK.

Le programme demandera :

```text
Tunnel ID OpenAI:
```

Collez le Tunnel ID créé précédemment.

Puis :

```text
Runtime API key OpenAI:
```

Collez votre propre Runtime API Key.

---

## 3. Démarrer OMNILINK

Une fois l'installation terminée :

```powershell
.\START-OMNILINK.ps1
```

Le serveur MCP local sera lancé.

Adresse locale :

```text
127.0.0.1:8000
```

Endpoint MCP :

```text
http://127.0.0.1:8000/mcp
```

Puis tunnel-client établira la connexion avec votre tunnel OpenAI.

---

## 4. Arrêter OMNILINK

```powershell
.\STOP-OMNILINK.ps1
```

---

# 🍎 INSTALLATION macOS

## Compatibilité

- Apple Silicon M1 / M2 / M3 / M4 / M5
- Mac Intel

Le setup détecte automatiquement l'architecture.

---

## Prérequis

- macOS
- Python 3
- Connexion Internet
- Tunnel ID créé à l'étape 1
- Runtime API Key créée à l'étape 2

---

## 1. Extraire l'archive

Téléchargez :

```text
DARK-ASIRIS-OMNILINK-MAC-v1.0.zip
```

Extrayez complètement le dossier.

---

## 2. Installer OMNILINK

Effectuez un clic droit sur :

```text
SETUP.command
```

puis :

**Ouvrir**

Le programme prépare automatiquement :

- l'environnement Python ;
- les dépendances ;
- tunnel-client pour votre architecture ;
- le profil OMNILINK ;
- la configuration locale.

Lorsque demandé, entrez votre :

```text
Tunnel ID
```

puis votre :

```text
Runtime API Key
```

La Runtime API Key est enregistrée dans le **Trousseau macOS**.

---

## 3. Démarrer OMNILINK

Double-cliquez sur :

```text
START-OMNILINK.command
```

Le serveur MCP démarre localement sur :

```text
127.0.0.1:8000
```

avec l'endpoint :

```text
http://127.0.0.1:8000/mcp
```

Le tunnel OpenAI est ensuite démarré.

---

## 4. Arrêter OMNILINK

Exécutez :

```text
STOP-OMNILINK.command
```

---

# 🤖 ÉTAPE 4 — Ajouter OMNILINK dans ChatGPT

Une fois :

- OMNILINK démarré ;
- le serveur MCP actif ;
- tunnel-client connecté ;

ouvrez ChatGPT.

Accédez aux paramètres des connecteurs/plugins.

Créez une nouvelle connexion.

## Nom recommandé Windows

```text
DARK ASIRIS // OMNILINK WINDOWS
```

## Nom recommandé macOS

```text
DARK ASIRIS // OMNILINK MAC
```

## Type de connexion

```text
Tunnel
```

## Tunnel

Sélectionnez le tunnel créé à **l'étape 1**.

## Authentification

```text
Sans authentification
```

Validez ensuite la connexion.

ChatGPT doit alors découvrir automatiquement les outils MCP exposés par OMNILINK.

---

# ✅ ÉTAPE 5 — Vérifier la connexion

Dans un nouveau chat, activez OMNILINK.

Demandez :

```text
Utilise OMNILINK et vérifie son statut.
```

Puis :

```text
Utilise tool_inventory et liste les outils détectés sur mon ordinateur.
```

Si OMNILINK retourne les informations de votre ordinateur, la connexion fonctionne.

---

# 📱 Utilisation depuis un téléphone

Lorsque :

- votre ordinateur est allumé ;
- OMNILINK est lancé ;
- tunnel-client est connecté ;
- votre connexion OMNILINK est disponible dans ChatGPT ;

vous pouvez utiliser ChatGPT depuis un autre appareil compatible pour demander à OMNILINK d'effectuer des opérations sur l'ordinateur distant.

Exemple :

```text
Analyse mon projet et vérifie son état Git.
```

Les commandes sont exécutées sur l'ordinateur sur lequel OMNILINK fonctionne.

---

# 🔐 SÉCURITÉ

OMNILINK n'a pas vocation à donner à ChatGPT un accès administrateur illimité.

Le projet privilégie :

- des outils MCP ciblés ;
- des commandes contrôlées ;
- des snapshots avant modification ;
- la validation des chemins ;
- des limites opérationnelles ;
- la journalisation ;
- Git comme second niveau de protection.

---

## ⚠️ Ne publiez jamais vos secrets

Ne publiez jamais :

```text
Runtime API Key
OpenAI API Key
GitHub Token
Mot de passe
.env contenant des secrets
Clés privées
Credentials
```

Chaque utilisateur doit utiliser ses **propres identifiants**.

---

# 🔐 Vérification des téléchargements

## 🪟 Windows v1.0

SHA-256 :

```text
9404d524b0df271139e943127195bb422b75f1e957e606ef7cd4bc3926d7f2b7
```

Vérification :

```powershell
Get-FileHash ".\DARK-ASIRIS-OMNILINK-WINDOWS-v1.0.zip" -Algorithm SHA256
```

---

## 🍎 macOS v1.0

SHA-256 :

```text
dc18077db5f5d4045d7d73f468cf87d2c8e882a8a02949613932f093a99e5b77
```

Vérification :

```bash
shasum -a 256 DARK-ASIRIS-OMNILINK-MAC-v1.0.zip
```

---

# 🆘 Dépannage

## Le serveur MCP ne répond pas

Vérifiez que le port local est disponible :

```text
127.0.0.1:8000
```

---

## ChatGPT ne voit pas les nouveaux outils

Redémarrez :

1. OMNILINK ;
2. tunnel-client ;
3. puis reconnectez/actualisez votre connexion OMNILINK dans ChatGPT.

---

## Le tunnel n'apparaît pas

Vérifiez :

- que le Tunnel ID utilisé pendant le setup est correct ;
- que la Runtime API Key appartient au bon compte/organisation ;
- que tunnel-client fonctionne ;
- que votre compte dispose des permissions nécessaires au tunnel.

---

# ⚠️ PROJET EN DÉVELOPPEMENT

DARK ASIRIS // OMNILINK est actuellement en développement actif.

Avant toute intervention importante sur un projet :

1. utilisez Git ;
2. créez une baseline ;
3. vérifiez votre diff ;
4. conservez les snapshots ;
5. validez le build après modification.

---

# 📜 LICENCE

**Aucune licence open source n'est actuellement accordée.**

La présence publique du code et des packages ne constitue pas automatiquement une autorisation de modification, redistribution ou utilisation commerciale.

**Tous droits réservés sauf autorisation explicite du propriétaire du projet.**

---

# 🖤 DARK ASIRIS

**DARK ASIRIS // OMNILINK**

*Your machine. Your projects. Your control.*
