# 🏭 IndustrialHMI

> **IndustrialHMI** est un framework open-source développé en **Node.js** permettant de créer des Interfaces Homme-Machine (HMI) industrielles modernes, performantes et multiplateformes.

L'objectif du projet est de proposer une alternative libre aux solutions propriétaires comme **TwinCAT HMI**, **WinCC**, **Ignition** ou **FactoryTalk**, tout en restant simple à développer, extensible et indépendante des constructeurs d'automates.

---

# ✨ Fonctionnalités

- ⚡ Communication temps réel avec les automates
- 🌐 Interface accessible depuis n'importe quel navigateur
- 🖥️ Compatible Windows, Linux et Raspberry Pi
- 📱 Interface responsive
- 🧩 Architecture modulaire
- 🎨 Thèmes personnalisables
- 🔌 Support de plusieurs protocoles industriels
- 📊 Bibliothèque de composants HMI
- 👥 Gestion des utilisateurs
- 🚨 Gestion des alarmes
- 📈 Historisation des données
- 📋 Gestion des recettes

---

# 🎯 Philosophie

IndustrialHMI est un **framework**, pas une simple HMI.

Le moteur reste identique pour toutes les machines.

Chaque projet contient uniquement :

- 📝 Les pages
- 🖼️ Les images
- ⚙️ La configuration
- 📡 Les variables PLC
- 📋 Les recettes

Le Framework s'occupe de tout le reste.

---

# 🏗️ Architecture

```text
IndustrialHMI/
│
├── framework/
│
├── projects/
│
├── data/
│
├── workspace/
│
└── README.md
```

---

# 📦 Structure du Framework

```text
framework/
│
├── server/
│
├── client/
│
├── components/
│
├── drivers/
│
├── services/
│
└── package.json
```

Le Framework ne contient **aucune logique métier**.

Il fournit uniquement les outils nécessaires au fonctionnement des HMI.

---

# 📁 Structure d'un projet

```text
MachineA/

config/

pages/

css/

js/

images/

recipes/

variables.json
```

Chaque machine est totalement indépendante.

---

# 🖥️ Interface

L'interface est composée de quatre parties.

```text
┌──────────────────────────────────────┐
│ Header                               │
├──────────────────────────────────────┤
│                                      │
│          Contenu de la page          │
│                                      │
├──────────────────────────────────────┤
│ Navigation                           │
├──────────────────────────────────────┤
│ Commandes                            │
└──────────────────────────────────────┘
```

## 📌 Header

Affiche en permanence :

- Nom de la machine
- Utilisateur connecté
- Heure
- État PLC
- Mode machine

---

## 📄 Pages

Chaque projet peut posséder ses propres pages.

Exemple :

- 🏠 Home
- 🏭 Production
- 📋 Recipe
- 🚨 Alarm
- ⚙️ Setup
- 🛠️ Maintenance
- 🧪 Debug
- 🔌 I/O
- 📈 Trends

---

## 🧭 Navigation

La barre de navigation permet de changer de page.

Elle est toujours visible.

---

## 🎮 Barre de commandes

Toujours présente.

Exemple :

- ▶️ Start
- ⏹️ Stop
- 🔄 Reset
- 🔧 Maintenance
- ✔️ Ack
- 🤖 Auto
- ✋ Manuel
- 👤 Login

---

# 🔌 Drivers supportés

## ✔️ Disponibles

- Beckhoff ADS *(priorité)*
- Driver Simulation

## 🚧 À venir

- OPC-UA
- Modbus TCP
- Siemens S7
- MQTT

---

# 🧩 Composants

Le framework fournit une bibliothèque de widgets.

## Commandes

- 🔘 Button
- 🎚️ Switch
- ☑️ Checkbox
- 📋 ComboBox
- 🔢 Numeric Input
- 🔤 TextBox

---

## Indicateurs

- 💡 Lamp
- 📊 Gauge
- 📈 Trend
- 📉 Chart
- 📶 Progress Bar
- 🖼️ Image
- 🎥 Camera

---

## Production

- 🚨 Alarm Table
- 📋 Recipe Table
- ⚙️ Axis Viewer
- 🧭 Joystick

---

## Utilisateurs

- 🔑 Login
- 🔒 Password
- 👥 User Manager

---

# 📡 Communication

```text
PLC

↓

Driver

↓

Variable Manager

↓

WebSocket

↓

Frontend

↓

Widgets
```

Les composants ne connaissent jamais le protocole utilisé.

Ils communiquent uniquement avec le **VariableManager**.

---

# 🧠 Variable Manager

Toutes les variables passent par une API unique.

```javascript
VariableManager.get("Machine.Auto");

VariableManager.set("Machine.Start", true);

VariableManager.subscribe("Axis.X.Position", callback);
```

Ainsi, changer de protocole ne nécessite aucune modification des pages HTML.

---

# ⚙️ CLI

IndustrialHMI possède son propre générateur de projets.

Créer le Framework

```bash
ihmi create
```

Créer un projet

```bash
ihmi new ChocolateMachine
```

Ouvrir un projet

```bash
ihmi open ChocolateMachine
```

Créer une page

```bash
ihmi add page Production
```

Créer un composant

```bash
ihmi add component Gauge
```

Créer un service

```bash
ihmi add service AlarmManager
```

Lancer le serveur

```bash
ihmi serve
```

Créer une version de production

```bash
ihmi build
```

---

# 📂 Données

Le dossier **Data** contient les informations persistantes.

```text
data/

alarms/

historian/

recipes/

users/

logs/
```

---

# 🚀 Roadmap

## ✅ Phase 1

- [ ] CLI
- [ ] Générateur du Framework
- [ ] Générateur de projets
- [ ] Générateur de pages
- [ ] Serveur Express
- [ ] WebSocket
- [ ] Navigation

---

## ⚙️ Phase 2

- [ ] Driver Beckhoff ADS
- [ ] Variable Manager
- [ ] Alarm Manager
- [ ] Historian
- [ ] Gestion des utilisateurs
- [ ] Authentification

---

## 🧩 Phase 3

- [ ] Bibliothèque de composants
- [ ] Trend
- [ ] Alarm Table
- [ ] Recipe Manager
- [ ] Graphiques
- [ ] Thèmes

---

## 🌍 Phase 4

- [ ] Driver OPC-UA
- [ ] Driver Modbus
- [ ] Mode Simulation
- [ ] Internationalisation
- [ ] Export de projets

---

## 🎨 Phase 5

- [ ] Éditeur graphique Drag & Drop
- [ ] Générateur automatique de pages
- [ ] Marketplace de composants
- [ ] Déploiement automatique

---

# 💡 Vision

IndustrialHMI a pour ambition de devenir un **framework complet de développement d'IHM industrielles**.

À terme, créer une nouvelle machine devra simplement consister à :

- 📡 Déclarer les variables PLC
- 📄 Créer les pages HTML
- 🖼️ Ajouter les images
- ⚙️ Configurer le projet

Le Framework prendra en charge automatiquement :

- 🔌 Communication automate
- 🌐 WebSocket
- 👥 Utilisateurs
- 🚨 Alarmes
- 📈 Historisation
- 📋 Recettes
- 🧩 Widgets
- 🎨 Thèmes
- 🧭 Navigation
- 🔒 Authentification

---

# 📜 Licence

Projet en cours de développement.

**IndustrialHMI © 2026**