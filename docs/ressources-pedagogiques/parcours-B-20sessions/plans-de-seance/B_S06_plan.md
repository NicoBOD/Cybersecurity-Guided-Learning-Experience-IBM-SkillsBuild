# Plan de séance — Session B06
Parcours : B 20 sessions  |  Module : B — Systèmes & réseaux  |  Durée : 1h30 (90 minutes)

## 1. Métadonnées de la session
* **Titre** : Défenses réseau
* **Objectifs pédagogiques opérationnels** :
  * Expliquer le fonctionnement d'un pare-feu et la différence entre un filtrage de paquets traditionnel (stateless/stateful) et un pare-feu de nouvelle génération (NGFW).
  * Différencier le rôle et le positionnement d'un IDS (détecter) et d'un IPS (bloquer) dans l'architecture réseau.
  * Modéliser un plan d'adressage et d'architecture réseau segmenté incluant un réseau local (LAN), Internet (WAN) et une zone démilitarisée (DMZ).
* **Prérequis** : B05.
* **Lien de progression** : Cette session formalise les techniques d'isolation logique réseau. Elle prépare la session B07, qui étudiera la sécurisation des flux circulant à travers ces infrastructures réseau (VPN et TLS).

---

## 2. Déroulé minuté (90 minutes)

| Minutage | Séquence | Contenu théorique & Activités | Rôle du Mentor | Rôle de l'Apprenant | Méthode pédagogique | Livrable / Jalon |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **00 - 15 min** *(15')* | **Brise-glace & Revue** | *Brise-glace : Le portier réseau.* Simulation de règles de filtrage simples : les apprenants écrivent un filtre basé sur le protocole et l'adresse IP. | Anime le jeu de rôle, valide les notions de ports et d'IP de B05. | Écrit ou propose des critères de filtrage réseau en direct. | Interrogative / Active | Jalon : Revue des notions de ports et protocoles. |
| **15 - 35 min** *(20')* | **Apports Théoriques : Firewalls** | *Fonctionnement des pare-feux.* Filtrage de paquets simple, maintien d'état (stateful), filtrage applicatif (WAF) et pare-feux nouvelle génération (NGFW). | Explique l'évolution technologique des pare-feux et le concept de filtrage par défaut (Default Deny). | Analyse la structure d'une table de règles de pare-feu. | Explicative | - |
| **35 - 50 min** *(15')* | **Apports Théoriques : IDS/IPS & DMZ** | *IDS, IPS et segmentation réseau (VLAN, DMZ).* Comment confiner la compromission d'un serveur public. | Décrit la position logique de l'IDS/IPS et l'architecture classique d'une DMZ. | Assimile l'importance du cloisonnement pour empêcher les mouvements latéraux des attaquants. | Explicative / Schématique | - |
| **50 - 80 min** *(30')* | **Activité Pratique** | *Activité : Zonage réseau.* À partir du cahier des charges d'une entreprise (serveurs internes + serveurs web), les apprenants tracent les frontières des zones (LAN, DMZ, WAN) et écrivent la table de règles pare-feu. | Fournit le cas pratique de l'entreprise "EcoLog", conseille sur l'isolation de la DMZ. | Dessine le schéma de zonage et rédige le tableau des 4 à 5 règles pare-feu de base. | Active / Collaborative | **Livrable** : Schéma d'architecture réseau segmenté et table de filtrage associée. |
| **80 - 90 min** *(10')* | **Quiz & Devoirs** | *Quiz de session & Devoirs.* Validation des concepts d'architecture réseau et présentation de la suite. | Lance le quiz interactif et présente les objectifs de travail autonome. | Participe au quiz et note les consignes de travail individuel. | Interrogative | Jalon : Score au quiz individuel. |

---

## 3. Travail en autonomie (Self-paced)
* **Avant la session suivante (B07)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Network Security - Part 2"* (durée estimée : 1h30).
  * **Observation pratique** : Inspecter le cadenas de sécurité du navigateur sur des sites internet courants pour identifier la version de TLS et l'autorité de certification émettrice.
