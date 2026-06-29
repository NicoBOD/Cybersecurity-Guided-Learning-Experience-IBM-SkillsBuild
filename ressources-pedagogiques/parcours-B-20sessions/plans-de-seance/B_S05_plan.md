# Plan de séance — Session B05
Parcours : B 20 sessions  |  Module : B — Systèmes & réseaux  |  Durée : 1h30 (90 minutes)

## 1. Métadonnées de la session
* **Titre** : Fondamentaux réseau pour la sécurité
* **Objectifs pédagogiques opérationnels** :
  * Expliquer les couches clés des modèles OSI et TCP/IP à travers le prisme de la sécurité (où se situent les attaques et les défenses).
  * Identifier le rôle des protocoles réseaux majeurs (DNS, DHCP, ARP, ICMP) et les ports de communication courants (22, 80, 443, 3389, 53).
  * Lire une adresse IP (réseau/hôte) et interpréter les éléments fondamentaux d'un en-tête de paquet réseau simple.
* **Prérequis** : Module A (Fondations).
* **Lien de progression** : Cette session technique fournit les connaissances d'infrastructure réseau indispensables pour aborder le filtrage et la segmentation par pare-feu (B06).

---

## 2. Déroulé minuté (90 minutes)

| Minutage | Séquence | Contenu théorique & Activités | Rôle du Mentor | Rôle de l'Apprenant | Méthode pédagogique | Livrable / Jalon |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **00 - 15 min** *(15')* | **Brise-glace & Revue** | *Brise-glace : Le paquet perdu.* Modélisation physique du réseau : les apprenants miment le cheminement d'un courrier papier pour comprendre l'encapsulation. | Anime la métaphore postale, fait la revue des devoirs et introduit le module Réseau. | Participe au mime ou à la discussion de groupe sur la circulation des données. | Interrogative / Active | Jalon : Schéma mental de l'encapsulation des données. |
| **15 - 35 min** *(20')* | **Apports Théoriques : Modèles** | *Modèles OSI vs TCP/IP.* Description des couches physiques, réseau, transport et application. Focus sur la sécurité par couche. | Présente les slides, montre à quel niveau agissent les menaces (ex. ARP spoofing au niveau 2, flood TCP au niveau 4). | Prend des notes, pose des questions d'infrastructure. | Explicative | - |
| **35 - 50 min** *(15')* | **Apports Théoriques : Protocoles** | *Protocoles et ports réseau.* Utilité de DNS, DHCP, ICMP. Notion de port réseau et liste des ports standards les plus ciblés. | Explique comment les protocoles légitimes peuvent être détournés (ex. exfiltration par tunnels DNS). | Apprend à associer un port à un service (ex. SSH = 22, RDP = 3389). | Explicative | - |
| **50 - 80 min** *(30')* | **Activité Pratique** | *Activité : Analyse d'un paquet tracé.* Analyse guidée de captures textuelles Wireshark simples (trames réseau) pour y repérer adresses IP et ports. | Projette une capture de trame DNS et de paquet TCP, explique la structure. | Identifie en groupe les adresses IP source/dest, ports source/dest et le protocole encapsulé. | Active / Guidée | **Livrable** : Fiche d'identification d'en-tête de paquet réseau complétée. |
| **80 - 90 min** *(10')* | **Quiz & Devoirs** | *Quiz de session & Devoirs.* Validation de la compréhension réseau et transition vers les pare-feux. | Lance le quiz interactif et présente le travail autonome SkillsBuild. | Répond au quiz et prend note des consignes de travail autonome. | Interrogative | Jalon : Score au quiz individuel. |

---

## 3. Travail en autonomie (Self-paced)
* **Avant la session suivante (B06)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Network Security - Part 1"* (durée estimée : 1h30).
  * **Exercice de réflexion** : Lister tous les appareils connectés au réseau Wi-Fi domestique (ordinateur, téléphone, IoT) et réfléchir à la façon dont on pourrait les isoler ou les protéger les uns des autres.
