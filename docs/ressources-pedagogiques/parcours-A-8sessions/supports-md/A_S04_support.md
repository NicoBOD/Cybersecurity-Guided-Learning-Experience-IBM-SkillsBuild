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

### Glossaire
* **IAM (Identity and Access Management)** : Ensemble des processus et outils technologiques servant à gérer l'identité des utilisateurs et à réguler leurs privilèges d'accès aux ressources informatiques.
* **MFA (Multi-Factor Authentication)** : Processus d'authentification exigeant de l'utilisateur qu'il fournisse au moins deux facteurs de preuve distincts (ex. un mot de passe + un code unique envoyé sur smartphone) avant d'autoriser l'accès.
* **Moindre privilège** : Principe de sécurité consistant à n'accorder à un utilisateur (ou à un processus) que les droits d'accès strictement nécessaires à l'accomplissement de sa tâche ou de sa fonction, et rien de plus.
* **Responsabilité partagée (Cloud)** : Modèle de sécurité définissant la répartition des tâches de protection entre le fournisseur de services cloud (sécurité *du* cloud) et le client utilisant ces services (sécurité *dans* le cloud).
* **Données au repos (At rest)** : Données stockées de façon persistante sur un support physique (disque dur, clé USB, serveur de stockage cloud).
* **Données en transit (In transit)** : Données actives circulant à travers un réseau public ou privé (ex. lors d'un transfert de fichier ou de la saisie d'un formulaire web).
* **Règle 3-2-1 (Sauvegarde)** : Règle d'or de la sauvegarde préconisant de posséder 3 copies de ses données, réparties sur 2 supports différents, dont 1 copie conservée hors site (ex. dans le cloud ou dans un autre bâtiment physique).

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

### Exercice d'application
**Titre** : Audit de résilience et plan de sauvegarde 3-2-1 d'une petite agence web

### Énoncé
Une petite agence de création web stocke ses créations graphiques et ses bases de données clients sur un serveur NAS local installé dans sa salle de réunion. Chaque soir, un script automatique copie les dossiers du serveur NAS sur un disque dur USB externe branché en permanence sur ce même serveur.

1. Identifiez les failles majeures de cette politique de sauvegarde.
2. Proposez une réorganisation conforme à la règle 3-2-1 en indiquant précisément les supports et l'emplacement des 3 copies requises.



### Corrigé de l'exercice
1. **Failles identifiées** :
   * *Risque physique commun* : Si un incendie ou un dégât des eaux touche la salle de réunion, le serveur NAS et son disque dur externe associé seront tous deux détruits simultanément.
   * *Risque cyber (Ransomware)* : Le disque dur de sauvegarde externe étant branché en permanence en USB sur le NAS, un rançongiciel qui infecterait le serveur NAS chiffrera également et immédiatement les données du disque externe connecté.
   * *Absence de copie hors site* : Aucune copie n'est externalisée en dehors des locaux physiques de l'agence.
2. **Proposition de plan de sauvegarde 3-2-1** :
   * **Copie 1 (Production)** : Les fichiers de travail actifs sur les postes des graphistes et sur le serveur de stockage actif de l'agence.
   * **Copie 2 (Sauvegarde locale sur support différent)** : Sauvegarde automatisée sur le serveur NAS de l'agence (déconnecté des postes de travail ordinaires sauf lors de la tâche de sauvegarde), ou sur une bande magnétique stockée localement dans une armoire ignifugée.
   * **Copie 3 (Sauvegarde hors site)** : Sauvegarde chiffrée automatisée envoyée chaque nuit vers un espace de stockage cloud sécurisé (ex. AWS S3 Glacier ou Microsoft Azure Archive), configurée en mode "lecture seule" (sauvegardes immuables) pour empêcher un ransomware local de la supprimer.

---


### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Pour bien comprendre ces concepts techniques, imaginez l'analogie suivante : la cybersécurité de votre entreprise est comme la sécurité d'une maison physique.
    - **Le Pare-feu (Firewall)** agit comme la porte d'entrée blindée : il filtre qui entre et qui sort.
    - **L'Antivirus / EDR** est comme le système d'alarme intérieur : s'il détecte un mouvement suspect, il bloque l'intrus.
    - **La Politique de mots de passe et le MFA** correspondent aux serrures multipoints et au digicode : posséder la clé ne suffit pas toujours, il faut aussi connaître le code secret.

**Exemple d'application professionnelle :**
Dans une PME, un attaquant tentera rarement de forcer les serveurs directement. Il enverra un e-mail frauduleux (Phishing) à un employé des ressources humaines. Si l'employé clique, le logiciel malveillant tente de s'installer. C'est ici que la *défense en profondeur* intervient : le filtre anti-spam aurait dû bloquer l'e-mail, l'antivirus aurait dû bloquer l'exécution, et l'absence de droits administrateurs de l'employé aurait empêché l'installation. Chaque couche est vitale.


## 3. Ressources complémentaires

* **IBM SkillsBuild** : Cours sur l'IAM (Identity and Access Management) et la sécurité Cloud.
* **ANSSI** : Recommandations pour la sécurisation des sauvegardes contre les rançongiciels.
* **Cloud Security Alliance (CSA)** : Le guide des menaces critiques liées au cloud computing (notamment les configurations défaillantes).


---

* [CNIL - Recommandations mots de passe](https://www.cnil.fr/fr/mots-de-passe-une-nouvelle-recommandation-pour-maitriser-sa-securite)
* [ANSSI - Authentification multifacteur](https://cyber.gouv.fr/publications/recommandations-relatives-lauthentification-multifacteur-et-aux-mots-de-passe)

## 4. Exercice bonus

- **Objectif :** Mise en pratique autonome.
- **Consignes :** Réfléchissez à un exemple réel ou une actualité récente liée au sujet de cette session. Discutez en groupe de la manière dont les concepts vus s'appliquent à cet exemple.
- **Correction :** Le mentor validera les réflexions et apportera son expertise.

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **IAM (Identity and Access Management)** | Ensemble des processus et outils technologiques servant à gérer l'identité des utilisateurs et à réguler leurs privilèges d'accès aux ressources informatiques. |
| **MFA (Multi-Factor Authentication)** | Processus d'authentification exigeant de l'utilisateur qu'il fournisse au moins deux facteurs de preuve distincts (ex. un mot de passe + un code unique envoyé sur smartphone) avant d'autoriser l'accès. |
| **Moindre privilège** | Principe de sécurité consistant à n'accorder à un utilisateur (ou à un processus) que les droits d'accès strictement nécessaires à l'accomplissement de sa tâche ou de sa fonction, et rien de plus. |
| **Responsabilité partagée (Cloud)** | Modèle de sécurité définissant la répartition des tâches de protection entre le fournisseur de services cloud (sécurité *du* cloud) et le client utilisant ces services (sécurité *dans* le cloud). |
| **Données au repos (At rest)** | Données stockées de façon persistante sur un support physique (disque dur, clé USB, serveur de stockage cloud). |
| **Données en transit (In transit)** | Données actives circulant à travers un réseau public ou privé (ex. lors d'un transfert de fichier ou de la saisie d'un formulaire web). |
| **Règle 3-2-1 (Sauvegarde)** | Règle d'or de la sauvegarde préconisant de posséder 3 copies de ses données, réparties sur 2 supports différents, dont 1 copie conservée hors site (ex. dans le cloud ou dans un autre bâtiment physique). |
