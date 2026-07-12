# Support de cours — Session 04 : Sécurité du cloud, des données & des identités
Parcours : A 8 sessions  |  Module : Cloud & Données  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Contrôle d'accès logique : IAM, Moindre privilège et MFA
    - Le chiffrement des données : Au repos vs En transit
    - Le modèle de responsabilité partagée dans le Cloud
    - La résilience des données : La règle de sauvegarde 3-2-1
    - L'identité et le cloud en chiffres, et deux cas réels : l'incendie OVHcloud (2021) et Capital One (2019)
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

À mesure que les données migrent vers les serveurs distants, le périmètre traditionnel du réseau physique s'efface pour laisser place à la gestion logique des identités et à la protection granulaire de la donnée elle-même. Ce support de cours détaille les mécanismes de contrôle d'accès avec la gestion des identités et des accès (*IAM*), l'authentification multifacteur (*MFA*) et la mise en œuvre pratique du principe du moindre privilège. Vous étudierez la distinction clé entre le chiffrement des données au repos (*at rest*) et en transit (*in transit*). Nous clarifierons le modèle de responsabilité partagée dans le *cloud* pour savoir précisément ce qui incombe au fournisseur et au client — une répartition que deux affaires réelles rendront très concrète — et nous conclurons sur la règle de sauvegarde 3-2-1, ultime rempart opérationnel contre la perte définitive de vos actifs numériques.

### Objectifs de la session

À l'issue de cette session, vous serez capable de :

- **Appliquer** le principe du moindre privilège lors de la définition de rôles et d'accès utilisateurs (matrice RBAC).
- **Expliquer** pourquoi le MFA est la mesure de protection des comptes la plus rentable, ainsi que ses limites (SIM swapping, hameçonnage du code) et son évolution (passkeys/FIDO2).
- **Distinguer** la répartition des responsabilités entre client et fournisseur dans le modèle de responsabilité partagée du cloud, selon IaaS/PaaS/SaaS.
- **Concevoir** une politique de sauvegarde résiliente avec la règle 3-2-1 (dont une copie hors site, immuable ou déconnectée).

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** Selon Microsoft, quelle proportion des attaques automatisées de compromission de comptes l'activation du MFA bloque-t-elle ?

    - A) Environ 50 %
    - B) Environ 80 %
    - C) Plus de 99,9 % ✅
    - D) 100 %

    **Débrief mentor :** Plus de 99,9 % (étude Microsoft publiée en 2019, régulièrement réaffirmée depuis). Attention à la précision : ce chiffre porte sur les attaques **automatisées** (robots testant des mots de passe volés) — pas sur les attaques ciblées, qui savent parfois contourner le MFA (on verra comment, et comment s'en prémunir). Et non, ce n'est pas 100 % : en sécurité, rien ne l'est. Message de la session : le MFA est la mesure au meilleur rapport protection/effort qui existe — l'activer partout est votre devoir n°1.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Modèle de Responsabilité Partagée du Cloud**
Il est crucial de passer du temps sur ce concept. Détaillez les différences entre IaaS, PaaS et SaaS :
- En IaaS (ex : AWS EC2), l'entreprise doit patcher le système d'exploitation Windows/Linux et sécuriser les applications qu'elle déploie.
- En PaaS, le fournisseur gère l'OS et le middleware ; le client reste responsable de son code applicatif et de ses données.
- En SaaS (ex : Microsoft 365), le fournisseur gère l'infrastructure ET l'application ; l'entreprise reste responsable de la configuration du MFA, de la gestion des identités et de ses données (y compris leur sauvegarde).
Règle mnémotechnique : plus on monte vers le SaaS, plus le fournisseur en fait — mais **les identités, les accès et les données restent toujours la responsabilité du client**.

**2. IAM et Authentification Avancée**
Plongez dans le fonctionnement de l'IAM :
- Le cycle de vie d'une identité (Onboarding, JML - Joiner Mover Leaver) : le « Leaver » oublié — le compte de l'ex-salarié jamais désactivé — est un grand classique de l'audit.
- La différence entre l'Authentification (Qui suis-je ?) et l'Autorisation (Que puis-je faire ?).
- Le fonctionnement technique du MFA : TOTP avec application d'authentification vs clés matérielles FIDO2/YubiKey ; pourquoi les SMS ne sont plus considérés comme totalement sûrs (protocole SS7 vieillissant, **SIM swapping** — l'attaquant se fait transférer votre ligne mobile).
- L'état de l'art 2024-2025 : les **passkeys** (clés d'accès FIDO2), résistantes à l'hameçonnage car la clé cryptographique est liée au site légitime — un faux site n'obtient rien, même si l'utilisateur s'y laisse prendre. Les attaques modernes contre le MFA classique : *MFA fatigue* (bombardement de notifications jusqu'à ce que la victime accepte) et hameçonnage du code en temps réel (relais AiTM). Le message : le MFA reste indispensable, et le MFA « résistant au phishing » est la cible à viser.

**3. Chiffrement "At Rest" vs "In Transit"**
Expliquez l'utilisation de BitLocker / FileVault / LUKS pour protéger les données au repos sur un disque dur volé, par opposition au protocole TLS (vu en A3) utilisé pour protéger les données en transit sur le réseau.

---

### Glossaire

*   **Données au repos (At rest)** — Données stockées de façon persistante sur un support physique (disque dur, clé USB, serveur de stockage cloud).
*   **Données en transit (In transit)** — Données actives circulant à travers un réseau public ou privé (ex. lors d'un transfert de fichier ou de la saisie d'un formulaire web).
*   **Escalade de privilèges** — Technique par laquelle un attaquant, entré avec un compte ordinaire, cherche à obtenir des droits supérieurs (administrateur) pour étendre son emprise.
*   **IAM (Identity and Access Management)** — Ensemble des processus et outils technologiques servant à gérer l'identité des utilisateurs et à réguler leurs privilèges d'accès aux ressources informatiques.
*   **MFA (Multi-Factor Authentication)** — Processus d'authentification exigeant de l'utilisateur qu'il fournisse au moins deux facteurs de preuve de natures distinctes (ex. un mot de passe + un code généré sur smartphone) avant d'autoriser l'accès.
*   **Moindre privilège** — Principe de sécurité consistant à n'accorder à un utilisateur (ou à un processus) que les droits d'accès strictement nécessaires à l'accomplissement de sa tâche ou de sa fonction, et rien de plus.
*   **Passkey (Clé d'accès)** — Méthode d'authentification moderne (standard FIDO2) remplaçant le mot de passe par une clé cryptographique liée à l'appareil et au site légitime ; résistante à l'hameçonnage.
*   **RBAC (Role-Based Access Control)** — Modèle de contrôle d'accès où les droits sont attribués à des rôles métier (commercial, RH, développeur) plutôt qu'à des individus, puis les personnes affectées aux rôles.
*   **Responsabilité partagée (Cloud)** — Modèle de sécurité définissant la répartition des tâches de protection entre le fournisseur de services cloud (sécurité *du* cloud) et le client utilisant ces services (sécurité *dans* le cloud).
*   **Règle 3-2-1 (Sauvegarde)** — Règle d'or de la sauvegarde préconisant de posséder 3 copies de ses données, réparties sur 2 supports différents, dont 1 copie conservée hors site (ex. dans le cloud ou dans un autre bâtiment physique).
*   **SIM swapping** — Fraude consistant à convaincre un opérateur mobile de transférer la ligne de la victime vers la carte SIM de l'attaquant, qui reçoit alors ses SMS — y compris les codes de validation.
*   **SSO (Single Sign-On)** — Authentification unique : l'utilisateur se connecte une fois auprès d'un fournisseur d'identité et accède à tous ses services sans ressaisir de mot de passe.

---

### 1. Contrôle d'accès logique : IAM, Moindre privilège et MFA

!!! info "À retenir"
    Dans un système d'information moderne, **l'identité est le nouveau périmètre de sécurité** : la question n'est plus « êtes-vous dans le réseau ? » mais « qui êtes-vous, et qu'avez-vous le droit de faire ? ».

#### A. Le principe du moindre privilège
Le moindre privilège consiste à limiter les droits d'accès d'un utilisateur au strict minimum requis pour faire son travail.

* *Pourquoi ?* Si le compte d'un collaborateur est piraté, les dommages sont limités à ses droits personnels. Si un simple employé a des privilèges d'administrateur global sur le réseau, sa compromission met en danger l'intégralité du système de l'entreprise. C'est aussi une protection contre la maladresse : on ne supprime pas par erreur un dossier auquel on n'a pas accès en écriture.
* *Le réflexe de l'attaquant* : entrer par un compte ordinaire (souvent via le phishing vu en A2), puis tenter une **escalade de privilèges**. Le moindre privilège transforme cette escalade en parcours du combattant.

#### B. L'Authentification Multifacteur (MFA)
Le mot de passe simple est vulnérable (divulgation, hameçonnage, force brute). Le MFA renforce l'authentification en combinant des facteurs de natures différentes :

* **Ce que je sais** : Un mot de passe, un code PIN, une réponse à une question secrète.
* **Ce que je possède** : Un téléphone recevant un SMS, une application d'authentification (générant des OTP), une clé de sécurité physique (ex. YubiKey).
* **Ce que je suis** : Une empreinte digitale, la reconnaissance faciale (biométrie).

*Règle d'or (sourcée)* : Selon Microsoft (étude 2019, confirmée depuis), l'activation du MFA bloque **plus de 99,9 % des attaques automatisées** de compromission de comptes. C'est le meilleur rapport protection/effort de toute la cybersécurité.

*Les limites à connaître (pour ne pas s'endormir)* : le MFA par SMS est affaibli par le **SIM swapping** ; le MFA par notification peut céder à la **MFA fatigue** (acceptation sous le bombardement) ; et un code à 6 chiffres peut être hameçonné en temps réel — souvenez-vous de la démo vishing d'A2, où l'attaquant demandait précisément ce code. La réponse moderne : les **passkeys** (FIDO2), liées cryptographiquement au site légitime — un faux site n'obtient rien, même si l'utilisateur s'y laisse prendre. Hiérarchie pratique : passkey/clé physique > application d'authentification > SMS > mot de passe seul. Mais retenez : **même le MFA par SMS vaut mille fois mieux que pas de MFA du tout**.

### 2. Le chiffrement des données : Au repos vs En transit

Protéger la donnée nécessite d'appliquer des mécanismes cryptographiques à chaque étape de son cycle de vie.

* **Le chiffrement en transit (*in transit*)** sécurise la donnée pendant qu'elle voyage sur un réseau. Il empêche l'interception et l'écoute clandestine (*eavesdropping*). Il s'appuie principalement sur des protocoles comme TLS (ex. HTTPS pour le web, FTPS pour le transfert de fichiers) — c'est « l'enveloppe blindée » de la session A3.
* **Le chiffrement au repos (*at rest*)** protège la donnée stockée sur un disque dur, un smartphone ou une base de données. Si un ordinateur portable d'entreprise chiffré (avec des outils comme BitLocker ou FileVault) est égaré ou volé, le voleur ne pourra jamais lire les fichiers qui y sont stockés sans la clé de déchiffrement — c'est ce qui a sauvé le consultant du cas d'A1.

Moyen mnémotechnique : en transit = l'enveloppe pendant le voyage ; au repos = le coffre-fort à l'arrivée. Une protection complète exige les deux : une lettre blindée déposée dans une boîte ouverte ne protège rien.

### 3. Le modèle de responsabilité partagée dans le Cloud

Une erreur fréquente consiste à penser que l'hébergement de services dans le cloud décharge totalement l'entreprise de toute tâche de sécurité. La sécurité dans le cloud est une responsabilité conjointe.

* **Le fournisseur Cloud** (ex. AWS, Microsoft Azure, Google Cloud) est responsable de la **sécurité du cloud** : protection physique des centres de données, maintenance des serveurs matériels, sécurité des hyperviseurs et alimentation électrique.
* **L'entreprise cliente** reste responsable de la **sécurité dans le cloud** : gestion des identifiants et mots de passe des employés, politiques d'accès IAM, configuration des services, classification et chiffrement des données stockées — et, selon le modèle (IaaS/PaaS), mise à jour des systèmes et sécurité des applications qu'elle déploie.

La frontière glisse selon le modèle : en **IaaS**, le client patche l'OS et sécurise ses applications ; en **PaaS**, il ne gère plus que son code et ses données ; en **SaaS**, le fournisseur gère aussi l'application — mais **identités, accès et données restent au client dans tous les cas**. Deux idées reçues à enterrer : « c'est dans le cloud, donc c'est sécurisé » et « c'est dans le cloud, donc c'est sauvegardé ». Ni l'une ni l'autre n'est automatique — les deux cas réels ci-dessous le prouvent.

### 4. La résilience des données : La règle de sauvegarde 3-2-1

Face aux rançongiciels qui chiffrent et détruisent les serveurs d'une entreprise, les sauvegardes constituent le dernier rempart pour restaurer l'activité sans payer de rançon. Pour être efficace, une stratégie de sauvegarde doit appliquer la règle 3-2-1 :

1. **3 copies des données** : Conserver la copie de production originale et au moins deux copies de sauvegarde pour parer à la corruption de fichiers.
2. **2 supports différents** : Stocker ces sauvegardes sur des technologies distinctes (ex. un disque dur externe local et un serveur NAS en réseau) pour éviter qu'un seul type de panne matérielle ne détruise tout.
3. **1 copie hors site** : Conserver au moins une copie hors de l'infrastructure locale (ex. sauvegarde externalisée dans le cloud, ou disque dur physiquement stocké dans un autre bâtiment). Ainsi, en cas d'incendie, d'inondation ou d'attaque globale par ransomware chiffrant l'intégralité du réseau local, la copie hors site restera intacte.

Deux compléments modernes : la copie hors site doit être **immuable** (non modifiable, même par un administrateur — donc même par un ransomware qui a volé les droits d'administrateur) ou **déconnectée** (*air-gapped*) ; et la règle non écrite « 0 » : **une sauvegarde jamais testée en restauration n'est pas une sauvegarde, c'est un espoir**.

---

### Focus pratique
La matrice RBAC permet de cartographier de manière logique et synthétique les accès des différents rôles d'une entreprise aux répertoires partagés sur un espace Cloud.

| Rôle / Métier | Dossier Ventes | Dossier Salaires (RH) | Codes Sources (R&D) | Fiches Techniques |
| :--- | :--- | :--- | :--- | :--- |
| **Commercial** | Écriture / Lecture | Aucun accès | Aucun accès | Lecture seule |
| **Responsable RH** | Aucun accès | Écriture / Lecture | Aucun accès | Lecture seule |
| **Développeur** | Aucun accès | Aucun accès | Écriture / Lecture | Lecture seule |
| **Gérant / DG** | Lecture seule | Lecture seule | Aucun accès | Lecture seule |

*Note* : Notez que même le Directeur Général n'a pas accès en écriture aux répertoires techniques de R&D ou de développement (moindre privilège appliqué : il n'en a pas besoin pour piloter l'entreprise — et son compte, cible prioritaire des attaquants, est ainsi moins dangereux s'il tombe).

### Activité — Le Gardien des Accès (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Projetez la matrice RBAC ci-dessus, puis annoncez : « vous êtes l'administrateur des accès de cette PME. Trois demandes viennent d'arriver dans votre boîte — à vous de trancher, dans le respect du moindre privilège. » Lancez les trois sondages successivement, avec débrief après chacun.

*   **📊 Sondage n°2 :** Le commercial demande l'accès au dossier Salaires « pour vérifier le calcul de ses commissions ». Que faites-vous ?
    *   A) J'accorde un accès en lecture : la demande semble légitime
    *   B) Je refuse : c'est au service RH d'extraire et de lui transmettre la seule donnée qui le concerne ✅
    *   C) J'accorde un accès temporaire... que je penserai à retirer plus tard
*   **📊 Sondage n°3 :** Un stagiaire arrive pour une semaine et doit consulter deux contrats. Quel accès au dossier Contrats ?
    *   A) Écriture/Lecture sur tout le dossier : c'est plus simple
    *   B) Lecture seule, limitée aux deux contrats concernés, avec expiration automatique en fin de mission ✅
    *   C) Les mêmes accès que son tuteur, par héritage
*   **📊 Sondage n°4 :** Le Directeur Général exige un accès en écriture à TOUS les dossiers, « parce que c'est lui le patron ». Votre réaction ?
    *   A) C'est le DG : tous les droits, sans discussion
    *   B) Lecture étendue si nécessaire, écriture au strict besoin — et je lui explique que son compte est la cible n°1 des attaquants ✅
    *   C) Je refuse tout accès au DG par principe

**Éléments de débriefing (pour le mentor) :**

- N°2 : la demande est légitime, l'accès ne l'est pas — on répond au **besoin** (sa commission), pas à la **demande** (le dossier entier). C'est la subtilité clé du moindre privilège.
- N°3 : les trois mots magiques : **minimal, nominatif, temporaire**. L'option C (héritage du tuteur) est le péché originel de la plupart des dérives de droits.
- N°4 : le moindre privilège n'est pas une question de hiérarchie mais d'exposition — plus le compte est puissant, plus sa compromission coûte cher (rappel A2 : c'est le DG qu'on usurpe dans l'arnaque au président, c'est aussi son compte qu'on vise). Un bon DG comprend cet argument en 30 secondes.

### 5. L'identité et le cloud en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **Plus de 99,9 %** : la part des attaques automatisées de compromission de comptes bloquées par l'activation du MFA (Microsoft, 2019 — chiffre régulièrement réaffirmé depuis).
    - **Les identifiants volés restent l'un des tout premiers vecteurs d'accès initial** dans les violations de données, devant l'exploitation de failles (Verizon, *Data Breach Investigations Report*, 2025) — voler une clé est plus simple que percer un mur.
    - **~106 millions** : le nombre de clients touchés par la fuite Capital One (2019), causée par une mauvaise configuration cloud (cas détaillé ci-dessous).
    - **Mars 2021** : l'incendie du centre de données OVHcloud de Strasbourg détruit intégralement un bâtiment — et avec lui les données des clients qui n'avaient pas de copie ailleurs (cas détaillé ci-dessous).

**Comment lire ces chiffres ?** (1) L'attaquant moderne ne « pirate » pas, il **se connecte** — avec vos identifiants ; d'où le MFA partout. (2) Le cloud ne tombe pas souvent en panne, mais quand la responsabilité est mal comprise, le client paie l'addition. (3) La sauvegarde hors site n'est pas de la paranoïa : c'est de l'assurance incendie, au sens propre.

### 6. Deux cas réels : le feu et la faille de configuration

#### Cas n°1 — L'incendie OVHcloud de Strasbourg (2021) : la règle 3-2-1 à l'épreuve du feu

Dans la nuit du 9 au 10 mars 2021, un incendie ravage le site strasbourgeois d'OVHcloud, premier hébergeur européen : le bâtiment **SBG2 est intégralement détruit**, un second partiellement. Des centaines de milliers de sites web et services français et européens se retrouvent hors ligne. Pour la plupart des clients, l'interruption dure quelques heures ou jours. Mais pour certains, la perte est **définitive** : leurs « sauvegardes » étaient hébergées... dans le même bâtiment que leurs serveurs, parfois sur la même machine. Ni fraude, ni piratage, ni malveillance : un incendie — le sinistre le plus banal du monde physique.

**Ce que ce cas illustre :** la lettre exacte de la règle 3-2-1 (le « 1 hors site » signifie *vraiment* hors site — un autre bâtiment, une autre région) ; et le modèle de responsabilité partagée dans sa version la plus crue : le fournisseur loue l'infrastructure, mais **la stratégie de sauvegarde des données reste la responsabilité du client**, sauf service de sauvegarde explicitement souscrit. « C'est dans le cloud » n'a jamais signifié « c'est sauvegardé ».

#### Cas n°2 — Capital One (2019) : une seule mauvaise configuration, 106 millions de clients

En 2019, la banque américaine Capital One — pourtant réputée pour sa maturité cloud — subit le vol des données d'environ **106 millions de clients** (demandes de crédit, revenus, numéros de sécurité sociale pour certains). L'attaquante, une ancienne employée d'un grand fournisseur cloud, exploite une **mauvaise configuration du pare-feu applicatif (WAF)** de l'entreprise pour faire exécuter des requêtes internes au serveur (technique dite SSRF), récupérer des identifiants temporaires **trop privilégiés**, et lister puis télécharger le contenu des espaces de stockage. Bilan : 80 millions de dollars d'amende du régulateur bancaire américain et 190 millions de dollars d'accord d'indemnisation.

**Ce que ce cas illustre :** ce n'est pas le cloud qui a failli, c'est la **configuration du client** — illustration parfaite de la « sécurité *dans* le cloud ». Et le facteur aggravant est un défaut de **moindre privilège** : le rôle technique compromis avait des droits bien supérieurs à son besoin réel. Si la matrice d'accès avait été aussi stricte que celle que vous venez de construire, la faille de configuration n'aurait ouvert qu'une porte de placard, pas la salle des coffres.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Votre PME héberge sa base clients chez un grand fournisseur cloud. Votre prestataire informatique vous affirme : « pas besoin de sauvegarde, c'est dans le cloud, c'est répliqué ». **Que répondez-vous ? Tapez A, B ou C dans le chat :**

    - A) Il a raison : les fournisseurs cloud ne perdent jamais de données.
    - B) Je demande ce qui est réellement souscrit : la réplication protège de la panne de disque, pas de l'incendie, du ransomware ni de l'erreur humaine — il me faut une vraie sauvegarde 3-2-1, testée. ✅
    - C) Je fais une copie sur un disque USB branché en permanence au serveur.

    **Débrief mentor :** B. La réplication synchronise tout — y compris les suppressions accidentelles et les fichiers chiffrés par un ransomware (répliqués en quelques secondes !). Et C reproduit le piège du NAS connecté : le disque branché sera chiffré avec le reste. Reboucler avec OVHcloud : les clients qui avaient répondu A ont tout perdu.

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez le modèle de responsabilité partagée dans le cloud comme la **location d'un appartement** :
    - **Le Propriétaire (Fournisseur Cloud - AWS/Azure/GCP)** est responsable des murs, de la solidité du toit, de la porte d'entrée de l'immeuble et des canalisations (sécurité physique et de l'infrastructure globale).
    - **Le Locataire (Votre entreprise)** est responsable d'installer une serrure robuste sur sa propre porte, de fermer les fenêtres en partant, et de décider qui a le droit d'entrer dans l'appartement (sécurité des données, des accès et des configurations).
    - Si vous laissez votre porte grande ouverte et que vous vous faites cambrioler, c'est de votre responsabilité, pas de celle du propriétaire de l'immeuble.
    - Et l'assurance habitation, c'est votre sauvegarde 3-2-1 : le propriétaire reconstruira l'immeuble, pas vos meubles.

**Exemple d'application professionnelle :**
Une start-up stocke les factures de ses clients sur un service de stockage cloud (S3). Lors d'un audit de sécurité, le responsable s'aperçoit que les factures sont accessibles publiquement sans mot de passe suite à une erreur humaine de configuration. Il applique immédiatement le modèle de responsabilité partagée en modifiant la politique d'accès du bucket pour exiger une authentification forte (MFA) et active le chiffrement automatique des données au repos. C'est le scénario Capital One... rattrapé à temps par l'audit — toute la différence entre un rapport d'audit et un communiqué de crise.

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

### Exercice d'application — Le NAS piégé (Sondages Livestorm n°5 et 6)

**Consignes pour le mentor :** Présentez le cas et lancez les deux sondages à la suite.

*   **📊 Sondage n°5 :** Un administrateur système sauvegarde ses bases de données tous les soirs sur un NAS de stockage réseau connecté en permanence. Un ransomware s'exécute le week-end avec des privilèges élevés. Quel est le risque majeur pour les sauvegardes ?
    *   A) Les sauvegardes sont protégées car elles sont sur un serveur différent (NAS).
    *   B) Le ransomware va chiffrer les sauvegardes accessibles sur le réseau local ✅
    *   C) La sauvegarde hebdomadaire va échouer par manque de place.
*   **📊 Sondage n°6 :** Quelle est la solution la plus efficace pour bloquer ce risque dans la règle 3-2-1 ?
    *   A) Faire des sauvegardes deux fois par jour sur le même NAS.
    *   B) Utiliser une sauvegarde externalisée immuable (non modifiable) ou déconnectée physiquement du réseau ✅
    *   C) Utiliser des clés USB alternées laissées branchées sur le serveur.

**Éléments de débriefing (pour le mentor) :**
- Les ransomwares modernes cherchent et chiffrent systématiquement les sauvegardes accessibles en réseau — c'est même leur priorité, avant les données de production. Une copie hors ligne (*air-gapped*) ou immuable est indispensable.
- Relier au déplacement latéral d'A3 : le NAS joignable depuis le réseau compromis fait partie du réseau compromis.

### Quiz de validation (Sondages Livestorm n°7 à 9)

**Consignes pour le mentor :** À lancer en fin de session, après les études de cas.

*   **📊 Sondage n°7 :** Quel principe consiste à donner aux utilisateurs uniquement les accès nécessaires à leur travail ?
    *   A) Le moindre privilège ✅
    *   B) La responsabilité partagée
    *   C) La règle 3-2-1
    *   D) Le Single Sign-On
*   **📊 Sondage n°8 :** Pourquoi une application d'authentification est-elle préférable au SMS pour le MFA ?
    *   A) Elle est plus rapide à utiliser
    *   B) Le SMS peut être détourné par SIM swapping ; le code généré localement, non ✅
    *   C) Le SMS est payant
*   **📊 Sondage n°9 :** Un espace de stockage cloud mal configuré expose publiquement des données clients. Qui est responsable ?
    *   A) Le fournisseur cloud : c'est son infrastructure
    *   B) Le client : la configuration des accès relève de la sécurité DANS le cloud ✅
    *   C) Personne : c'est un cas de force majeure

**Éléments de débriefing (pour le mentor) :**

- N°7 : re-balayer les trois décisions du Gardien des Accès en 20 secondes (minimal, nominatif, temporaire).
- N°8 : rejouer la hiérarchie — passkey/clé physique > application > SMS > rien ; et rappeler que même le SMS vaut mieux que rien.
- N°9 : reboucler avec Capital One et l'analogie du locataire : la serrure de VOTRE porte, c'est vous.

### Questions de réflexion

1. Dans votre organisation, combien de personnes ont des droits d'administrateur ? Le savez-vous ? Qui vérifie que les comptes des partants sont désactivés (le « L » de JML) ?
2. Après l'incendie OVHcloud, certains clients ont attaqué l'hébergeur en justice. Jusqu'où va, selon vous, la responsabilité du fournisseur — et où commence la négligence du client ?
3. Le MFA ajoute une friction à chaque connexion. Comment convaincre des équipes réticentes de l'adopter, sans se contenter de l'imposer ?
4. Votre téléphone personnel contient votre application d'authentification. Que se passe-t-il si vous le perdez ? Avez-vous préparé ce scénario (codes de secours, second facteur de repli) ?

## 3. Ressources complémentaires

* **IBM SkillsBuild** : Cours sur l'IAM (Identity and Access Management) et la sécurité Cloud.
* **[ANSSI — Recommandations relatives à l'authentification multifacteur et aux mots de passe](https://cyber.gouv.fr/publications/recommandations-relatives-lauthentification-multifacteur-et-aux-mots-de-passe)** : le guide de référence français.
* **[CNIL — Recommandations sur les mots de passe](https://www.cnil.fr/fr/mots-de-passe-une-nouvelle-recommandation-pour-maitriser-sa-securite)** : les règles actualisées (longueur plutôt que complexité).
* **ANSSI** : Recommandations pour la sécurisation des sauvegardes contre les rançongiciels.
* **Cloud Security Alliance (CSA)** : Le guide des menaces critiques liées au cloud computing (notamment les configurations défaillantes).

## 4. Exercice bonus (Dilemme Sauvegarde 3-2-1 - Livestorm)

*   **Objectif :** Application de la résilience opérationnelle.
*   **📊 Sondage Livestorm n°10 :** Un incendie détruit intégralement les bureaux de l'entreprise. Vos sauvegardes sont stockées sur deux disques durs externes dans les mêmes locaux. Que se passe-t-il ?
    *   A) Les données sont sauvées car il y a deux disques.
    *   B) Les données sont définitivement perdues car aucun support n'était externalisé ✅
    *   C) Les données peuvent être récupérées dans le cloud automatiquement sans configuration préalable.
*   **Guide d'animation (pour le mentor) :** Utilisez ce cas tragique mais classique pour justifier l'obligation d'avoir au moins une copie hors site (physique ou cloud) dans la règle 3-2-1 — et rebouclez avec l'incendie OVHcloud : le scénario n'a rien de théorique. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Données au repos (At rest)** | Données stockées de façon persistante sur un support physique (disque dur, clé USB, serveur de stockage cloud). |
| **Données en transit (In transit)** | Données actives circulant à travers un réseau public ou privé (transfert de fichier, formulaire web). |
| **Escalade de privilèges** | Progression d'un attaquant d'un compte ordinaire vers des droits d'administrateur. |
| **IAM (Identity and Access Management)** | Processus et outils gérant l'identité des utilisateurs et régulant leurs privilèges d'accès aux ressources. |
| **MFA (Multi-Factor Authentication)** | Authentification exigeant au moins deux facteurs de natures distinctes (savoir / posséder / être) ; bloque plus de 99,9 % des attaques automatisées (Microsoft). |
| **Moindre privilège** | N'accorder que les droits strictement nécessaires à la tâche — minimal, nominatif, temporaire. |
| **Passkey (Clé d'accès)** | Authentification FIDO2 sans mot de passe, liée au site légitime ; résistante à l'hameçonnage. |
| **RBAC (Role-Based Access Control)** | Droits attribués à des rôles métier plutôt qu'à des individus. |
| **Responsabilité partagée (Cloud)** | Le fournisseur sécurise LE cloud (infrastructure) ; le client sécurise DANS le cloud (identités, accès, configurations, données). |
| **Règle 3-2-1 (Sauvegarde)** | 3 copies, 2 supports différents, 1 copie hors site — idéalement immuable ou déconnectée, et testée en restauration. |
| **SIM swapping** | Détournement de la ligne mobile de la victime pour intercepter ses SMS de validation. |
| **SSO (Single Sign-On)** | Connexion unique auprès d'un fournisseur d'identité donnant accès à tous les services. |

**La règle d'or de la session :** activez le MFA partout où c'est possible — et souvenez-vous que « c'est dans le cloud » ne signifie ni « c'est sécurisé », ni « c'est sauvegardé ».
