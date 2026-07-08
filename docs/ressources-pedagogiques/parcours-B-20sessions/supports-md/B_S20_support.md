# Support de cours — Session 20 : Grand Atelier d'Audit & Clôture du Parcours
Parcours : B 20 sessions  |  Module : Consolidation & Évaluation  |  Niveau : Intermédiaire / Avancé

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session de clôture. Vous y découvrirez :
    - La méthodologie de l'Atelier d'Audit Interactif MedDistri (Avancé)
    - Les clés d'une restitution managériale professionnelle et de gestion de crise
    - La valorisation de vos compétences et la suite de votre apprentissage

---

## 1. Introduction

Cette vingtième session marque l'achèvement du parcours B. Elle remplace la soutenance de groupe classique par un **Grand Atelier d'Audit Interactif et de Gestion de Crise** mené en direct en visioconférence sur Livestorm. L'objectif est de mobiliser l'ensemble des modules étudiés (fondations, réseaux sécurisés, identités & cloud, gouvernance, risques, opérations de sécurité SOC, analyse de logs, réponse aux incidents et exercices de crise tabletop) pour valider collectivement le plan de sécurité de MedDistri.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Restitution et Synthèse Managériale**
Expliquez aux apprenants comment vulgariser un concept cyber complexe pour convaincre un Comité de Direction. Le Comex ne comprend pas les adresses IP ou les CVSS, il comprend le risque financier, juridique et réputationnel. Montrez comment transformer "Vulnérabilité SQLi sur le serveur" en "Risque de vol de l'intégralité du fichier client entraînant une sanction CNIL de 500k€".

**2. Gestion de Crise Tabletop**
Menez l'exercice de crise en direct. Simulez l'attaque en cours (Ransomware), lancez les sondages sur les mesures à prendre (confinement réseau, préservation de la RAM, communication externe), puis expliquez pourquoi certaines décisions (éteindre le serveur, payer la rançon) aggravent la situation.

**3. Plan de développement des compétences**
Terminez la session (30 minutes) en orientant les apprenants vers l'avenir : quelles certifications viser (Sec+, CEH, CISSP) ? Comment configurer un laboratoire virtuel (TryHackMe, HackTheBox) pour continuer la pratique ? Comment suivre l'actualité cyber (veille technologique).

---

### Glossaire

*   **Audit de sécurité** — Évaluation formelle et technique de la conformité et de la vulnérabilité d'un système d'information.
*   **CERT-FR** — Centre de veille, d'alerte et de réponse aux attaques informatiques de l'État français, rattaché à l'ANSSI.
*   **CVE (Common Vulnerabilities and Exposures)** — Système d'identification et de référencement public des vulnérabilités logicielles connues.
*   **Plan de remédiation** — Document de synthèse ordonnant les mesures correctives techniques, physiques et organisationnelles pour corriger les failles.
*   **Playbook d'incident** — Fiche d'action réflexe décrivant précisément les étapes techniques de confinement, d'éradication et de restauration pour un type de menace donné.

---

### Concepts clés de l'Atelier MedDistri (Avancé)

#### 1. Architecture Réseau Cible
MedDistri doit abandonner son réseau local plat au profit d'un cloisonnement strict :
*   **VLANs internes** : Séparation du LAN administratif (compta, RH) et du LAN logistique (entrepôt).
*   **DMZ (Zone Démilitarisée)** : Hébergement des serveurs exposés à Internet (fichiers, commandes).
*   **Accès Nomade** : Fermeture des accès directs RDP/SSH au profit d'un VPN WireGuard ou IPsec protégé par MFA.

#### 2. Plan de Réaction face aux Rançongiciels (Playbook)
Lors d'une infection active :
*   **Isoler avant d'éteindre** : Débrancher le câble réseau RJ45 ou couper le Wi-Fi permet de stopper l'attaque sans effacer les preuves volatiles en mémoire vive (RAM), indispensables au forensics.
*   **Règle de Sauvegarde 3-2-1** : Utiliser des sauvegardes immuables locales et distantes.
*   **Communication centralisée** : La cellule de crise gère toute communication pour éviter les fuites d'informations stratégiques.

---

### Exercice d'application (Débat Décisionnel : Objections Métier - Livestorm)

**Consignes pour le mentor :** Lancez le sondage pour confronter le public aux réalités du terrain.

*   **Sondage :** La directrice refuse d'imposer l'authentification multifacteur (MFA) car elle craint que les commerciaux ne perdent du temps lors de leurs connexions quotidiennes. Quel argument de sensibilisation est le plus percutant ?
    *   A) Le MFA protège de 99% des attaques par vol d'identifiants, et l'arrêt d'activité en cas de piratage coûtera bien plus cher que 3 secondes par connexion *(Bonne réponse)*.
    *   B) Le MFA est obligatoire par la loi sur la protection des données personnelles.
    *   C) Les commerciaux n'ont pas leur mot à dire sur les choix de sécurité.

**Éléments de débriefing (pour le mentor) :**
- La sécurité doit être présentée sous l'angle du risque financier et opérationnel. Le MFA moderne (notifications push) est aujourd'hui très fluide.

---

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour tester la solidité d'une infrastructure cyber, mener des exercices de crise ou réaliser un audit technique final :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Immersive Labs / Mandiant Crisis Simulations** : Plateformes interactives de simulation de crises cyber en direct.
    *   **XM Cyber** : Solution commerciale de simulation d'attaque continue (BAS), révélant les chemins d'attaque menant aux actifs critiques.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **OpenEx** : Plateforme open-source de planification et d'exécution d'exercices de crise cyber (ANSSI/communauté).
    *   **CISA Tabletop Exercises** : Banque gratuite de scénarios et de guides d'animation d'exercices de crise.

---

## 3. Ressources complémentaires

*   **Après la formation** : Ajoutez vos certifications et badges de réussite **IBM SkillsBuild** sur votre profil LinkedIn.
*   **Veille continue** : Abonnez-vous aux bulletins du **CERT-FR** de l'ANSSI pour suivre les vulnérabilités critiques.

---

## 4. Exercice bonus (Sondage Bilan - Livestorm)

*   **Objectif :** Évaluation globale de la posture d'hygiène.
*   **Sondage Livestorm :** Quelle mesure de sécurité simple et gratuite présente le meilleur retour sur investissement immédiat pour une TPE/PME ?
    *   A) Acheter un pare-feu à 5 000 €.
    *   B) Mettre en œuvre une politique de mots de passe robustes associée au MFA gratuit et sensibiliser les collaborateurs *(Bonne réponse)*.
    *   C) Rédiger une charte informatique de 80 pages.
*   **Guide d'animation (pour le mentor) :** Rappelez que l'hygiène cyber de base bloque la majorité des attaques opportunistes sans nécessiter de budgets importants.

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Audit de sécurité** | Évaluation formelle et technique de la conformité et de la vulnérabilité d'un système d'information. |
| **CERT-FR** | Centre de veille, d'alerte et de réponse aux attaques informatiques de l'État français, rattaché à l'ANSSI. |
| **CVE (Common Vulnerabilities and Exposures)** | Système d'identification et de référencement public des vulnérabilités logicielles connues. |
| **Plan de remédiation** | Document de synthèse ordonnant les mesures correctives techniques, physiques et organisationnelles pour corriger les failles. |
| **Playbook d'incident** | Fiche d'action réflexe décrivant précisément les étapes techniques de confinement, d'éradication et de restauration. |
