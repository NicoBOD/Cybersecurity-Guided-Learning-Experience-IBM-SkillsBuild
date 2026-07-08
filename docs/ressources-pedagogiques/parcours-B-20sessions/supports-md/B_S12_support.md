# Session B12 — Sécurité & confidentialité des données

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - La Classification des données
    - Chiffrement au repos vs en transit
    - La Prévention des fuites de données (DLP — Data Loss Prevention)
    - La règle de sauvegarde 3-2-1
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   La **classification des données** (Publique, Interne, Confidentielle, Secrète) adapte l'effort et le coût de sécurité à la valeur réelle des informations.
*   Le **chiffrement en transit** protège les données circulant sur le réseau, tandis que le **chiffrement au repos** protège les données écrites sur des supports physiques contre le vol matériel.
*   Le **DLP** surveille activement les postes et réseaux pour bloquer les fuites d'informations confidentielles vers l'extérieur de l'entreprise.
*   La règle de sauvegarde **3-2-1** (3 copies, 2 supports différents, 1 copie hors site/hors ligne) est le rempart ultime contre la perte de données et les attaques par rançongiciel.

---

## 2. Développement

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Concevoir et appliquer un plan de classification des données d'entreprise sur 4 niveaux de sensibilité.
* Différencier et configurer le chiffrement des données au repos (*at rest*) et des données en transit (*in transit*).
* Expliquer le fonctionnement logique d'une solution de prévention des fuites de données (DLP).
* Appliquer la règle de sauvegarde 3-2-1 pour concevoir une architecture de sauvegarde résiliente face aux rançongiciels.
* Soutenir et évaluer le livrable du **Mini-projet 2 (Plan de protection et de sauvegarde des données)**.

---

### Glossaire
*   **Chiffrement au repos (At Rest)** — Protection des données écrites sur un support de stockage statique (disque dur, base de données) par chiffrement cryptographique.
*   **Chiffrement en transit (In Transit)** — Protection des données en cours de déplacement sur un réseau de communication à l'aide de protocoles sécurisés.
*   **DLP (Data Loss Prevention)** — Technologie logicielle de surveillance et de blocage conçue pour empêcher l'exfiltration accidentelle ou malveillante de données d'entreprise.
*   **Sauvegarde hors ligne (Offline Backup)** — Copie de sauvegarde stockée sur un support physiquement déconnecté du réseau informatique (bandes, disques débranchés), isolée des attaques cyber.

---

### Concepts clés

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

### 1. La Classification des données
Pour protéger efficacement les informations, il faut d'abord savoir ce que l'on possède et quelle est sa valeur. Il est impossible (et inutilement coûteux) de protéger une simple brochure publique avec le même niveau de sécurité qu'un brevet secret de fabrication.

La classification consiste à répartir les données en 4 niveaux types de sensibilité :

1.  **Publique** : Données qui peuvent être divulguées sans aucun risque pour l'entreprise (ex. site web externe, communiqués de presse, catalogues).
2.  **Interne** : Données réservées à l'usage exclusif des employés de l'entreprise. Leur divulgation externe causerait un embarras mineur ou une perte d'efficacité (ex. organigramme interne, notes de service, procédures techniques).
3.  **Confidentielle** : Données sensibles dont la divulgation externe porterait préjudice à l'entreprise, à ses clients ou à ses employés (ex. données de paie des RH, fichiers clients, bilans comptables non publiés, contrats de fournisseurs).
4.  **Secrète (ou Strictement Confidentielle)** : Données stratégiques vitales. Leur fuite menacerait directement la pérennité, la compétitivité ou la survie légale de l'entreprise (ex. brevets industriels non déposés, codes sources de logiciels propriétaires, projets de fusion-acquisition).

*   *L'analogie de la maison d'édition* :
    *   **Publique** : Les livres imprimés exposés en vitrine de la librairie.
    *   **Interne** : Le planning de travail des équipes éditoriales dans le couloir des bureaux.
    *   **Confidentielle** : Les coordonnées bancaires et contrats de droits d'auteur des écrivains.
    *   **Secrète** : Le manuscrit inédit du prochain best-seller mondial encore confidentiel.

### 2. Chiffrement au repos vs en transit
Pour préserver la confidentialité des données à travers leur cycle de vie, la cryptographie s'applique à deux états différents :

*   **Chiffrement en transit (*in transit*)** : Concerne les données en cours de déplacement sur un réseau (ex. entre votre navigateur et un site web, ou entre deux serveurs). On utilise des protocoles de transport chiffrés comme **TLS (HTTPS)**, **SSH**, ou des **VPN** pour empêcher l'interception passive des flux (écoute clandestine).
*   **Chiffrement au repos (*at rest*)** : Concerne les données stockées de manière statique sur un support physique (disque dur d'ordinateur, serveurs de stockage NAS, bases de données, clés USB). On utilise des logiciels comme **BitLocker** (Windows), **LUKS** (Linux) ou le chiffrement natif des bases de données pour empêcher la lecture des données si le disque physique est volé ou accédé directement hors du système d'exploitation.

### 3. La Prévention des fuites de données (DLP — Data Loss Prevention)
Une solution de **DLP** est un outil logiciel qui inspecte automatiquement le trafic réseau, les terminaux utilisateurs et les serveurs de stockage pour détecter et empêcher l'extraction non autorisée d'informations sensibles en dehors du périmètre de l'entreprise.

*   *Fonctionnement* : Le DLP utilise des règles d'analyse de contenu (regex, mots-clés, empreintes de fichiers). Si un employé tente de copier un fichier de R&D contenant le mot "PROTOTYPE" sur une clé USB personnelle ou d'envoyer par email une liste contenant des numéros de cartes de crédit, le DLP bloque l'action et alerte l'équipe de sécurité.

### 4. La règle de sauvegarde 3-2-1
Face à la recrudescence des rançongiciels (*ransomwares*) qui chiffrent les serveurs de l'entreprise pour réclamer une rançon, la seule garantie de reprise d'activité réside dans les sauvegardes. La règle d'or industrielle est la méthodologie **3-2-1** :

*   **3 copies** : Conserver au moins trois exemplaires de vos données (la donnée originale de production + au moins deux copies de sauvegarde indépendantes).
*   **2 supports différents** : Stocker ces sauvegardes sur au moins deux types de médias technologiques distincts (ex. un disque dur externe branché localement et un serveur de stockage réseau NAS). Cela protège contre la défaillance matérielle d'une technologie spécifique.
*   **1 copie hors site** : Conserver au moins une copie des sauvegardes dans un lieu géographique différent de l'original (ex. dans le Cloud sécurisé ou sur un disque transporté physiquement dans un autre bâtiment).
*   *Mesure moderne anti-ransomware* : Cette copie hors site doit être **hors ligne** (sauvegarde déconnectée physiquement du réseau ou immuable), car les ransomwares modernes recherchent activement les serveurs de sauvegarde connectés au réseau pour les détruire avant de chiffrer la production.

---

### Activités / exercices
### Exercice 1 — Application pratique de la règle de sauvegarde 3-2-1
**Objectif :** Concevoir une architecture de sauvegarde physique et logique pour une agence d'architecture gérant des données de CAO (plans géographiques et structures) sensibles.

**Consignes :**
L'agence d'architecture "ArchiTech" emploie 5 dessinateurs. Ils créent des plans 3D complexes stockés sur un serveur local commun dans leur bureau. La perte de ces données équivaudrait à la faillite de l'agence.
Proposez une mise en œuvre concrète de la règle 3-2-1 en complétant le schéma logique ci-dessous (définissez la nature de chaque copie, le support matériel utilisé et la localisation physique).

**Questionnaire à remplir :**

*   **Copie n°1 (Production)** : Quel support ? Où est-elle située ?
*   **Copie n°2 (Sauvegarde locale)** : Quel support ? Où est-elle située ? Comment protège-t-elle contre une panne du serveur de production ?
*   **Copie n°3 (Sauvegarde hors site/hors ligne)** : Quel support ? Où est-elle située ? Contre quels risques majeurs (locaux et réseau) protège-t-elle ?

**Corrigé / Éléments de réponse :**

*   **Copie n°1 (Production)** :
    *   *Support* : Disques SSD en configuration RAID installés sur le serveur de fichiers local du bureau d'ArchiTech.
    *   *Rôle* : Utilisée au quotidien par les dessinateurs via le réseau local LAN.
*   **Copie n°2 (Sauvegarde locale - Support n°2)** :
    *   *Support* : Serveur de stockage réseau (NAS) installé dans une pièce technique distincte du bureau.
    *   *Rôle* : Un script de sauvegarde automatique (ex. toutes les nuits à 2h du matin) copie l'intégralité du serveur de production vers le NAS. Si le disque dur du serveur de production lâche, les données sont récupérées instantanément sur le NAS local à grande vitesse.
*   **Copie n°3 (Sauvegarde hors site / hors ligne - Support n°3)** :
    *   *Support* : Stockage Cloud chiffré (ex. AWS S3 Glacier avec politique d'immuabilité "Object Lock") ou rotation hebdomadaire de disques durs externes stockés dans un coffre-fort dans une banque.
    *   *Rôle* : Protège l'entreprise contre un incendie ou une inondation totale des bureaux qui détruirait à la fois le serveur de production et le NAS local. De plus, l'accès déconnecté ou immuable protège cette sauvegarde d'un chiffrement par ransomware qui se serait propagé sur tout le réseau local.

---

### Questions de réflexion
1. Si vous chiffrez un disque dur externe au repos à l'aide de BitLocker, et que vous le laissez branché en permanence sur un ordinateur de bureau infecté par un malware actif, le chiffrement empêchera-t-il le malware de voler ou de modifier vos fichiers ? Justifiez votre réponse.
2. Pourquoi la classification des données est-elle considérée comme un prérequis indispensable avant de configurer les règles d'un logiciel de prévention des fuites de données (DLP) ?

**Corrigé / Éléments de réponse :**
1. Non, si l'ordinateur est allumé et la session ouverte, le disque est déchiffré à la volée. Le malware peut donc accéder aux fichiers en clair.
2. Le DLP a besoin de savoir quelles données sont sensibles (confidentielles, restreintes) pour appliquer les bonnes règles ; sans classification, tout est bloqué ou rien n'est bloqué.

---

## 3. Ressources Complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Data Security and Privacy"* (durée estimée : 1h30).
*   **Recherche complémentaire** : Renseignez-vous sur la directive de conformité **RGPD** (Règlement Général sur la Protection des Données). Identifiez comment la classification et la pseudonymisation des données personnelles aident à se conformer à la législation européenne.

* [ANSSI - Agence Nationale de la Sécurité des Systèmes d'Information](https://www.ssi.gouv.fr/)
* [Cybermalveillance.gouv.fr](https://www.cybermalveillance.gouv.fr/)
* [OWASP - Open Worldwide Application Security Project](https://owasp.org/)

---

## 4. Exercice Bonus

- **Objectif :** Mise en pratique autonome.
- **Consignes :** Réfléchissez à un exemple réel ou une actualité récente liée au sujet de cette session. Discutez en groupe de la manière dont les concepts vus s'appliquent à cet exemple.
- **Correction :** Le mentor validera les réflexions et apportera son expertise.

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Chiffrement au repos (At Rest)** | Protection des données écrites sur un support de stockage statique (disque dur, base de données) par chiffrement cryptographique. |
| **Chiffrement en transit (In Transit)** | Protection des données en cours de déplacement sur un réseau de communication à l'aide de protocoles sécurisés. |
| **DLP (Data Loss Prevention)** | Technologie logicielle de surveillance et de blocage conçue pour empêcher l'exfiltration accidentelle ou malveillante de données d'entreprise. |
| **Sauvegarde hors ligne (Offline Backup)** | Copie de sauvegarde stockée sur un support physiquement déconnecté du réseau informatique (bandes, disques débranchés), isolée des attaques cyber. |
