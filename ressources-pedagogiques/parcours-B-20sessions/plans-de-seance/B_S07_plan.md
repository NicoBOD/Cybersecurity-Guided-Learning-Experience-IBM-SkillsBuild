# Plan de séance — Session B07
Parcours : B 20 sessions  |  Module : B — Systèmes & réseaux  |  Durée : 1h30 (90 minutes)

## 1. Métadonnées de la session
* **Titre** : Communications sécurisées
* **Objectifs pédagogiques opérationnels** :
  * Expliquer le rôle et le fonctionnement simplifié du protocole TLS/SSL dans la sécurisation des flux web (HTTPS).
  * Comparer les protocoles et architectures VPN (IPsec, OpenVPN, WireGuard) pour le chiffrement des accès distants et l'interconnexion de sites.
  * Identifier les faiblesses des chiffrements Wi-Fi obsolètes (WEP, WPA2-PSK) et appliquer les recommandations WPA3/WPA-Enterprise.
* **Prérequis** : B05 et B06.
* **Lien de progression** : Cette session finalise la protection des données en transit. Elle ouvre sur la sécurisation physique et logique des hôtes terminaux (B08) qui clôture le module Systèmes et Réseaux.

---

## 2. Déroulé minuté (90 minutes)

| Minutage | Séquence | Contenu théorique & Activités | Rôle du Mentor | Rôle de l'Apprenant | Méthode pédagogique | Livrable / Jalon |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **00 - 15 min** *(15')* | **Brise-glace & Revue** | *Brise-glace : Le secret de l'enveloppe.* Métaphore sur la différence entre le chiffrement des données de transport (l'enveloppe opaque) et le chiffrement du contenu (la lettre codée). | Guide la métaphore, fait le pont avec la sécurité des réseaux physiques de B06. | Analyse la métaphore et identifie ce qui doit être chiffré dans un paquet réseau. | Interrogative / Métaphorique | Jalon : Compréhension de la différence chiffrement de flux / chiffrement de données. |
| **15 - 35 min** *(20')* | **Apports Théoriques : TLS & HTTPS** | *Fonctionnement de TLS.* Le Handshake TLS simplifié, le rôle des autorités de certification (CA), et la validation de l'identité du serveur. | Présente les étapes clés du handshake TLS et explique les attaques d'interception (MitM). | Assimile la logique des clés publiques/privées appliquées aux flux web. | Explicative / Schématique | - |
| **35 - 50 min** *(15')* | **Apports Théoriques : VPN & Wi-Fi** | *Technologies VPN et sécurité sans-fil.* VPN IPsec (site-à-site) vs OpenVPN/WireGuard (accès utilisateur). Évolution des protocoles Wi-Fi. | Compare l'ergonomie, la performance et le niveau de sécurité des solutions de communication. | Découvre comment sécuriser la connexion des télétravailleurs. | Explicative | - |
| **50 - 80 min** *(30')* | **Activité Pratique** | *Activité : Scénarisation de connexions distantes.* Les apprenants conçoivent la politique de connexion sans-fil et distante sécurisée pour une flotte de 100 commerciaux mobiles. | Distribue le cahier des charges opérationnel d'une entreprise nomade, conseille sur le choix du VPN. | Compare les technologies et rédige la préconisation technique et d'usage pour la direction. | Active / Collaborative | **Livrable** : Fiche de recommandations techniques pour le chiffrement des flux mobiles. |
| **80 - 90 min** *(10')* | **Quiz & Devoirs** | *Quiz de session & Devoirs.* Validation des connaissances de sécurité de transport et présentation de la suite. | Lance le quiz de fin de session et présente le travail autonome pour la session B08. | Complète le quiz en ligne et note les devoirs. | Interrogative | Jalon : Score au quiz individuel. |

---

## 3. Travail en autonomie (Self-paced)
* **Avant la session suivante (B08)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Secure Protocols & Cryptography Basics"* (durée estimée : 1h30).
  * **Préparation du Mini-projet 1** : Relire les consignes globales de sécurité réseau et concevoir une première liste d'équipements de sécurité requis pour une infrastructure d'entreprise simple.
