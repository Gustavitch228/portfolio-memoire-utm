# 🔐 Infrastructure Réseau Multi-Sites Sécurisée & Gestion Unifiée des Menaces (UTM Sophos)

[![Technologies](https://img.shields.io/badge/Tech-Sophos%20UTM%20%7C%20Active%20Directory%20%7C%20IPsec%20VPN%20%7C%20VMware-blue)](#-technologies--outils)
[![Auteur](https://img.shields.io/badge/Auteur-Gustave%20AGBASSAH-orange)](#-auteur)
[![Diplôme](https://img.shields.io/badge/ESTM-Licence%20Téléinformatique-green)](#-contexte--problématique)

---

## 📌 À propos du Projet

Ce projet regroupe l'étude, la conception et la simulation d'une infrastructure réseau d'entreprise multi-sites centralisée et sécurisée via une appliance UTM (*Unified Threat Management*).

Ce travail fait suite à mon mémoire de fin de cycle pour l'obtention de la **Licence en Téléinformatique** (Option Réseaux Informatiques et Télécommunications) à l'**ESTM Dakar** (Année académique 2019-2020), sous la direction du **Dr. Moustapha MBAYE**.

---

## 🎯 Contexte & Problématique

Face à la complexité croissante des systèmes d'information et à la multiplication des menaces de cybersécurité, la gestion fragmentée des équipements (pare-feu dédiés, routeurs, serveurs de filtrage séparés) génère des risques opérationnels et alourdit les coûts d'administration.

### **Objectifs du Projet :**
- **Centralisation** : Réduire la complexité d'administration du SI en regroupant les fonctions de sécurité et de réseau au sein d'une console unique (Sophos UTM).
- **Interconnexion Sécurisée** : Relier deux sites distants (Dakar et Lomé) à travers Internet de manière chiffrée.
- **Isolation & Partitionnement** : Mettre en place des zones réseau étanches (LAN, DMZ, Wi-Fi Invités/Hotspot) pour protéger les ressources sensibles.
- **Haute Disponibilité & Contrôle** : Déployer un filtrage dynamique des accès, une authentification centralisée et un suivi en temps réel via journalisation/notifications.

---

## 🛠️ Architecture & Périmètre Technique

L'infrastructure a été modélisée et simulée dans un environnement virtuel avancé sous **VMware Workstation**.

### 🏛️ Topologie & Découpage Réseau

```text
                           ┌─────────────────────────┐
                           │        INTERNET         │
                           └────────────┬────────────┘
                                        │
                    ┌───────────────────┴───────────────────┐
                    │                                       │
         ┌──────────┴──────────┐                 ┌──────────┴──────────┐
         │  Sophos UTM (Dakar) │                 │  Sophos UTM (Lomé)  │
         └──────────┬──────────┘                 └──────────┬──────────┘
                    │                                       │
     ┌──────────────┼──────────────┐                        │
     │              │              │                        │
┌────┴────┐   ┌─────┴─────┐   ┌────┴────┐              ┌────┴────┐
│   LAN   │   │    DMZ    │   │  Wi-Fi  │              │   LAN   │
│  Dakar  │   │ (AD/DNS)  │   │ Invités │              │  Lomé   │
└─────────┘   └───────────┘   └─────────┘              └─────────┘

```

1. **Site Principal (Dakar)** :
* **Zone LAN** : Réseau d'entreprise local pour les utilisateurs et équipements internes.
* **Zone DMZ** : Hébergement du Contrôleur de Domaine Active Directory (`sps.net`) et des services d'annuaire.
* **Zone Wi-Fi Invités / Hotspot** : Accès Internet isolé pour les visiteurs sans accès au LAN/DMZ.


2. **Site Distant (Lomé)** :
* **Zone LAN** : Filiale distante nécessitant un accès sécurisé aux ressources de la maison mère.



---

## 🔒 Fonctionnalités & Configurations Déployées

* **Interconnexion & Nomadisme** :
* **VPN IPsec Site-à-Site** : Interconnexion permanente et chiffrée entre les appliances Sophos de Dakar et Lomé.
* **VPN SSL & Portail HTML5** : Accès à distance sécurisé pour les collaborateurs nomades (PC & Mobiles).


* **Sécurité Périmétrique & Applicative** :
* **NextGen Firewall** : Contrôle d'accès basé sur les politiques utilisateurs et réseaux.
* **IPS (Intrusion Prevention System)** & **ATP (Advanced Threat Protection)** : Détection et blocage dynamique des tentatives d'intrusion et trafics malveillants.
* **Filtrage Web & Applicatif** : Inspection HTTPS, contrôle des catégories de sites et restriction d'applications non autorisées.


* **Services Réseau Centraux & Annuaire** :
* **DNS & DHCP** : Gestion intégrée des adressages et de la résolution de noms.
* **NAT / Masquerading** : Routage et translation d'adresses pour les sorties Internet.
* **Authentification Distante** : Liaison directe de Sophos UTM avec Active Directory (zone DMZ) pour la gestion des droits utilisateurs.


* **Supervision & Auditing** :
* Centralisation des logs, mécanismes de notification et génération de rapports d'activité.



---

## 🧰 Technologies & Outils

| Catégorie | Outils / Technologies |
| --- | --- |
| **Appliance UTM / Firewall** | Sophos UTM SG Series / UTM OS |
| **Services d'Annuaire / OS** | Microsoft Windows Server (Active Directory, DNS), Linux |
| **Protocole VPN & Sécurité** | IPsec, SSL VPN, HTML5 User Portal, IPS, ATP, NAT |
| **Hyperviseur / Lab** | VMware Workstation Pro |

---

## 📄 Livrables & Téléchargement

* 📘 **Mémoire Complet (PDF)** : [Télécharger le Mémoire PDF](./MEMOIRE_AGB_FIN.pdf)
* 📑 **Titre Officiel** : *Mise en place d'une plate-forme de gestion unifiée d'un système d'information*
* 🎓 **Établissement** : École Supérieure de Technologie et de Management (ESTM Dakar)

---

## 👤 Auteur

**Gustave AGBASSAH**

*Administrateur Systèmes, Réseaux & Sécurité*

- 💼 **LinkedIn** : [linkedin.com/in/gustave-agbassah](https://www.linkedin.com/in/gustave-agbassah)
- 📜 **Profil Credly** : [credly.com/users/gustave-agbassah](https://www.credly.com/users/gustave-agbassah)
- ✉️ **Email** : gustavoagbassah@gmail.com

```

```
