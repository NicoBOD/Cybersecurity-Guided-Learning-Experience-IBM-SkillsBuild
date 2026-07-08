# Support de cours — Session 04 : Sécurité du cloud, des données & des identités
Parcours : A 8 sessions  |  Module : Cloud & Données  |  Niveau : Débutant

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Contrôle d'accès logique : IAM, Moindre privilège et MFA
    - Le chiffrement des données : Au repos vs En transit
    - Le modèle de responsabilité partagée dans le Cloud
    - La résilience des données : La règle de sauvegarde 3-2-1
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

À mesure que les données migrent vers les serveurs distants, le périmètre traditionnel du réseau physique s'efface pour laisser place à la gestion logique des identités et à la protection granulaire de la donnée elle-même. Ce support de cours détaille les mécanismes de contrôle d'accès avec la gestion des identités et des accès (*IAM*), l'authentification multifacteur (*MFA*) et la mise en œuvre pratique du principe du moindre privilège. Vous étudierez la distinction clé entre le chiffrement des données au repos (*at rest*) et en transit (*in transit*). Nous clarifierons le modèle de responsabilité partagée dans le *cloud* pour savoir précisément ce qui incombe au fournisseur et au client, et nous conclurons sur la règle de sauvegarde 3-2-1, ultime rempart opérationnel contre la perte définitive de vos actifs numériques.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Modèle de Responsabilité Partagée du Cloud**
Il est crucial de passer 20 minutes sur ce concept. Détaillez les différences entre IaaS, PaaS et SaaS. 
- En IaaS (ex: AWS EC2), l'entreprise doit patcher le système d'exploitation Windows/Linux.
- En SaaS (ex: Microsoft 365), Microsoft gère l'OS, mais l'entreprise reste responsable de la configuration du MFA, de la gestion des identités, et de la sauvegarde de ses e-mails.

**2. IAM et Authentification Avancée**
Plongez dans le fonctionnement de l'IAM :
- Le cycle de vie d'une identité (Onboarding, JML - Joiner Mover Leaver).
- La différence entre l'Authentification (Qui suis-je ?) et l'Autorisation (Que puis-je faire ?).
- Le fonctionnement technique du MFA (TOTP avec Google Authenticator vs clés matérielles FIDO2/YubiKey) et pourquoi les SMS (SS7) ne sont plus considérés comme totalement sécurisés.

**3. Chiffrement "At Rest" vs "In Transit"**
Expliquez l'utilisation de BitLocker / LUKS pour protéger les données au repos sur un disque dur volé, par opposition au protocole TLS utilisé pour protéger les données en transit sur le réseau Internet.


---

### Glossaire

*   **Données au repos (At rest)** — Données stockées de façon persistante sur un support physique (disque dur, clé USB, serveur de stockage cloud).
*   **Données en transit (In transit)** — Données actives circulant à travers un réseau public ou privé (ex. lors d'un transfert de fichier ou de la saisie d'un formulaire web).
*   **IAM (Identity and Access Management)** — Ensemble des processus et outils technologiques servant à gérer l'identité des utilisateurs et à réguler leurs privilèges d'accès aux ressources informatiques.
*   **IAM (Identity and Access Management)** — Ensemble des politiques et technologies garantissant que les bonnes personnes accèdent aux bonnes ressources informatiques.
*   **MFA (Multi-Factor Authentication)** — Processus d'authentification exigeant de l'utilisateur qu'il fournisse au moins deux facteurs de preuve distincts (ex. un mot de passe + un code unique envoyé sur smartphone) avant d'autoriser l'accès.
*   **MFA (Multi-Factor Authentication)** — Méthode de validation d'identité exigeant la présentation d'au moins deux facteurs de preuve distincts.
*   **Moindre privilège** — Principe de sécurité consistant à n'accorder à un utilisateur (ou à un processus) que les droits d'accès strictement nécessaires à l'accomplissement de sa tâche ou de sa fonction, et rien de plus.
*   **Responsabilité partagée** — Modèle de sécurité du cloud répartissant les tâches de protection entre le fournisseur cloud (sécurité du cloud) et le client (sécurité dans le cloud).
*   **Responsabilité partagée (Cloud)** — Modèle de sécurité définissant la répartition des tâches de protection entre le fournisseur de services cloud (sécurité *du* cloud) et le client utilisant ces services (sécurité *dans* le cloud).
*   **Règle 3-2-1 (Sauvegarde)** — Règle d'or de la sauvegarde préconisant de posséder 3 copies de ses données, réparties sur 2 supports différents, dont 1 copie conservée hors site (ex. dans le cloud ou dans un autre bâtiment physique).
*   **Sauvegarde 3-2-1** — Règle de résilience consistant à conserver 3 copies des données, sur 2 supports différents, dont 1 copie stockée hors-site.

---

### 1. Contrôle d'accès logique : IAM, Moindre privilège et MFA

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.


Dans un système d'information moderne, l'identité est le nouveau périmètre de sécurité.

#### A. Le principe du moindre privilège
Le moindre privilège consiste à limiter les droits d'accès d'un utilisateur au strict minimum requis pour faire son travail.

* *Pourquoi ?* Si le compte d'un collaborateur est piraté, les dommages sont limités à ses droits personnels. Si un simple employé a des privilèges d'administrateur global sur le réseau, sa compromission met en danger l'intégralité du système de l'entreprise.

#### B. L'Authentification Multifacteur (MFA)
Le mot de passe simple est vulnérable (divulgation, hameçonnage, force brute). Le MFA renforce l'authentification en combinant des facteurs de natures différentes :

* **Ce que je sais** : Un mot de passe, un code PIN, une réponse à une question secrète.
* **Ce que je possède** : Un téléphone recevant un SMS, une application d'authentification (générant des OTP), une clé de sécurité physique (ex. YubiKey).
* **Ce que je suis** : Une empreinte digitale, la reconnaissance faciale (biométrie).

*Règle d'or* : L'activation du MFA bloque plus de 99% des tentatives d'usurpation de compte automatisées.



### 2. Le chiffrement des données : Au repos vs En transit

Protéger la donnée nécessite d'appliquer des mécanismes cryptographiques à chaque étape de son cycle de vie.

* **Le chiffrement en transit (*in transit*)** sécurise la donnée pendant qu'elle voyage sur un réseau. Il empêche l'interception et l'écoute clandestine (écoute de type *eavesdropping*). Il s'appuie principalement sur des protocoles comme TLS (ex. HTTPS pour le web, FTPS pour le transfert de fichiers).
* **Le chiffrement au repos (*at rest*)** protège la donnée stockée sur un disque dur, un smartphone ou une base de données. Si un ordinateur portable d'entreprise chiffré (avec des outils comme BitLocker ou FileVault) est égaré ou volé, le voleur ne pourra jamais lire les fichiers qui y sont stockés sans la clé de déchiffrement.



### 3. Le modèle de responsabilité partagée dans le Cloud

Une erreur fréquente consiste à penser que l'hébergement de services dans le cloud décharge totalement l'entreprise de toute tâche de sécurité. La sécurité dans le cloud est une responsabilité conjointe.

* **Le fournisseur Cloud** (ex. AWS, Microsoft Azure, Google Cloud) est responsable de la **sécurité du cloud** : protection physique des centres de données, maintenance des serveurs matériels, sécurité des hyperviseurs et alimentation électrique.
* **L'entreprise cliente** reste responsable de la **sécurité dans le cloud** : gestion des identifiants et mots de passe des employés, politiques d'accès IAM, configuration des pare-feux logiciels, classification et chiffrement des données stockées.



### 4. La résilience des données : La règle de sauvegarde 3-2-1

Face aux rançongiciels qui chiffrent et détruisent les serveurs d'une entreprise, les sauvegardes constituent le dernier rempart pour restaurer l'activité sans payer de rançon. Pour être efficace, une stratégie de sauvegarde doit appliquer la règle 3-2-1 :

1. **3 copies des données** : Conserver la copie de production originale et au moins deux copies de sauvegarde pour parer à la corruption de fichiers.
2. **2 supports différents** : Stocker ces sauvegardes sur des technologies distinctes (ex. un disque dur externe local et un serveur NAS en réseau) pour éviter qu'un seul type de panne matérielle ne détruise tout.
3. **1 copie hors site** : Conserver au moins une copie hors de l'infrastructure locale (ex. sauvegarde externalisée dans le cloud, ou disque dur physiquement stocké dans un autre bâtiment). Ainsi, en cas d'incendie, d'inondation ou d'attaque globale par ransomware chiffrant l'intégralité du réseau local, la copie hors site restera intacte.

---

### Focus pratique
La matrice RBAC permet de cartographier de manière logique et synthétique les accès des différents rôles d'une entreprise aux répertoires partagés sur un espace Cloud.

| Rôle / Métier | Dossier Ventes | Dossier Salaires (RH) | Codes Sources (R&D) | Fiches Techniques |
| :--- | :--- | :--- | :--- | :--- |
| **Commercial** | Écriture / Lecture | Aucun accès | Aucun accès | Lecture seule |
| **Responsable RH** | Aucun accès | Écriture / Lecture | Aucun accès | Lecture seule |
| **Développeur** | Aucun accès | Aucun accès | Écriture / Lecture | Lecture seule |
| **Gérant / DG** | Lecture seule | Lecture seule | Aucun accès | Lecture seule |

*Note* : Notez que même le Directeur Général n'a pas accès en écriture aux répertoires techniques de R&D ou de développement (moindre privilège appliquée : il n'en a pas besoin pour piloter l'entreprise).

---

### Exercice d'application (Dilemme d'Architecture de Sauvegarde - Livestorm)

**Consignes pour le mentor :** Présentez le cas et lancez le sondage.

*   **Sondage :** Un administrateur système sauvegarde ses bases de données tous les soirs sur un NAS de stockage réseau connecté en permanence. Un ransomware s'exécute le week-end avec des privilèges élevés. Quel est le risque majeur pour les sauvegardes ?
    *   A) Les sauvegardes sont protégées car elles sont sur un serveur différent (NAS).
    *   B) Le ransomware va chiffrer les sauvegardes accessibles sur le réseau local *(Bonne réponse)*.
    *   C) La sauvegarde hebdomadaire va échouer par manque de place.
*   **Sondage 2 :** Quelle est la solution la plus efficace pour bloquer ce risque dans la règle 3-2-1 ?
    *   A) Faire des sauvegardes deux fois par jour sur le même NAS.
    *   B) Utiliser une sauvegarde externalisée immuable (non modifiable) ou déconnectée physiquement du réseau *(Bonne réponse)*.
    *   C) Utiliser des clés USB alternées laissées branchées sur le serveur.

**Éléments de débriefing (pour le mentor) :**
- Les ransomwares modernes cherchent et chiffrent systématiquement les sauvegardes accessibles en réseau. Une copie hors ligne (Air-gapped) ou immuable est indispensable.

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez le modèle de responsabilité partagée dans le cloud comme la **location d'un appartement** :
    - **Le Propriétaire (Fournisseur Cloud - AWS/Azure/GCP)** est responsable des murs, de la solidité du toit, de la porte d'entrée de l'immeuble et des canalisations (sécurité physique et de l'infrastructure globale).
    - **Le Locataire (Votre entreprise)** est responsable d'installer une serrure robuste sur sa propre porte, de fermer les fenêtres en partant, et de décider qui a le droit d'entrer dans l'appartement (sécurité des données, des accès et des configurations).
    - Si vous laissez votre porte grande ouverte et que vous vous faites cambrioler, c'est de votre responsabilité, pas de celle du propriétaire de l'immeuble.

**Exemple d'application professionnelle :**
Une start-up stocke les factures de ses clients sur un service de stockage cloud (S3). Lors d'un audit de sécurité, le responsable s'aperçoit que les factures sont accessibles publiquement sans mot de passe suite à une erreur humaine de configuration. Il applique immédiatement le modèle de responsabilité partagée en modifiant la politique d'accès du bucket pour exiger une authentification forte (MFA) et active le chiffrement automatique des données au repos.


### Panorama des solutions du marché (Commerciales & Open-Source)

La sécurisation du cloud, des données et de l'identité exige des solutions de sauvegarde et de contrôle d'accès :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Veeam Backup & Replication** : Le leader absolu de la sauvegarde d'entreprise, offrant des sauvegardes physiques, virtuelles et cloud avec gestion de l'immuabilité contre les ransomwares.
    *   **Microsoft Entra ID (anciennement Azure Active Directory)** : La solution cloud leader pour l'IAM, l'authentification multifacteur (MFA) et le Single Sign-On (SSO) en entreprise.
    *   **Okta Workforce Identity Cloud** : Plateforme IAM indépendante majeure, reconnue pour sa simplicité d'intégration SSO multi-cloud.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **Keycloak** : Solution open-source robuste d'IAM et de Single Sign-On (SSO) développée par Red Hat, supportant OpenID Connect et SAML 2.0.
    *   **Duplicati / BorgBackup** : Outils de sauvegarde open-source chiffrés et incrémentaux, parfaits pour sécuriser les données locales vers un stockage distant de manière économique.
    *   **Vaultwarden (Bitwarden)** : Gestionnaire de mots de passe auto-hébergé open-source, permettant de stocker et partager les identifiants d'entreprise de manière hautement sécurisée sans licence payante.

## 3. Ressources complémentaires

* **IBM SkillsBuild** : Cours sur l'IAM (Identity and Access Management) et la sécurité Cloud.
* **ANSSI** : Recommandations pour la sécurisation des sauvegardes contre les rançongiciels.
* **Cloud Security Alliance (CSA)** : Le guide des menaces critiques liées au cloud computing (notamment les configurations défaillantes).


---

* [CNIL - Recommandations mots de passe](https://www.cnil.fr/fr/mots-de-passe-une-nouvelle-recommandation-pour-maitriser-sa-securite)
* [ANSSI - Authentification multifacteur](https://cyber.gouv.fr/publications/recommandations-relatives-lauthentification-multifacteur-et-aux-mots-de-passe)

## 4. Exercice bonus (Dilemme Sauvegarde 3-2-1 - Livestorm)

*   **Objectif :** Application de la résilience opérationnelle.
*   **Sondage Livestorm :** Un incendie détruit intégralement les bureaux de l'entreprise. Vos sauvegardes sont stockées sur deux disques durs externes dans les mêmes locaux. Que se passe-t-il ?
    *   A) Les données sont sauvées car il y a deux disques.
    *   B) Les données sont définitivement perdues car aucun support n'était externalisé *(Bonne réponse)*.
    *   C) Les données peuvent être récupérées dans le cloud automatiquement sans configuration préalable.
*   **Guide d'animation (pour le mentor) :** Utilisez ce cas tragique mais classique pour justifier l'obligation d'avoir au moins une copie hors site (physique ou cloud) dans la règle 3-2-1.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Données au repos (At rest)** | Données stockées de façon persistante sur un support physique (disque dur, clé USB, serveur de stockage cloud). |
| **Données en transit (In transit)** | Données actives circulant à travers un réseau public ou privé (ex. lors d'un transfert de fichier ou de la saisie d'un formulaire web). |
| **IAM (Identity and Access Management)** | Ensemble des processus et outils technologiques servant à gérer l'identité des utilisateurs et à réguler leurs privilèges d'accès aux ressources informatiques. |
| **MFA (Multi-Factor Authentication)** | Processus d'authentification exigeant de l'utilisateur qu'il fournisse au moins deux facteurs de preuve distincts (ex. un mot de passe + un code unique envoyé sur smartphone) avant d'autoriser l'accès. |
| **Moindre privilège** | Principe de sécurité consistant à n'accorder à un utilisateur (ou à un processus) que les droits d'accès strictement nécessaires à l'accomplissement de sa tâche ou de sa fonction, et rien de plus. |
| **Responsabilité partagée (Cloud)** | Modèle de sécurité définissant la répartition des tâches de protection entre le fournisseur de services cloud (sécurité *du* cloud) et le client utilisant ces services (sécurité *dans* le cloud). |
| **Règle 3-2-1 (Sauvegarde)** | Règle d'or de la sauvegarde préconisant de posséder 3 copies de ses données, réparties sur 2 supports différents, dont 1 copie conservée hors site (ex. dans le cloud ou dans un autre bâtiment physique). |
| **Sauvegarde 3-2-1** | Règle de résilience consistant à conserver 3 copies des données, sur 2 supports différents, dont 1 copie stockée hors-site. |

