# Banque de Quiz — Parcours A (8 sessions)
Parcours : A 8 sessions  |  Module : Validation des connaissances  |  Format : Banque de QCM résolus

---

## Session 01 : Découverte de la cybersécurité & paysage des menaces

### Question 1 : Le pilier de la Confidentialité
Quelle technologie permet de garantir le pilier de la **Confidentialité** au sein de la triade CIA ?

* A. La duplication des serveurs de base de données.
* B. Le chiffrement des données de santé stockées.
* C. La signature numérique des e-mails.
* **Réponse correcte : B**
* *Explication* : Le chiffrement transforme l'information en texte illisible pour toute personne ne possédant pas la clé d'accès. Cela garantit le secret (la Confidentialité). La réponse A garantit la Disponibilité et la C garantit l'Intégrité et l'authenticité.

### Question 2 : Menace vs Vulnérabilité
Dans l'évaluation des risques cyber, comment qualifie-t-on un système d'exploitation obsolète et non mis à jour ?

* A. Une menace.
* B. Une vulnérabilité.
* C. Un impact.
* **Réponse correcte : B**
* *Explication* : Une vulnérabilité est une faiblesse interne d'un système que des attaquants peuvent exploiter. Un OS obsolète est une vulnérabilité. La menace est l'acteur malveillant ou le malware qui va tenter de tirer profit de cette vulnérabilité.

### Question 3 : Profil d'attaquant
Quel groupe d'attaquants est principalement motivé par des gains financiers rapides à travers des campagnes massives de ransomwares ?

* A. Les hacktivistes.
* B. Les États-nations.
* C. Les cybercriminels.
* **Réponse correcte : C**
* *Explication* : Les cybercriminels agissent pour l'argent (rançons, vol de cartes de crédit). Les hacktivistes sont motivés par l'idéologie ou la politique, et les États-nations par l'espionnage, le renseignement ou le sabotage géopolitique.

---

## Session 02 : Menaces, attaques & ingénierie sociale

### Question 1 : Hameçonnage par téléphone
Quel terme désigne une attaque d'ingénierie sociale menée spécifiquement par téléphone ?

* A. Le Spear-phishing.
* B. Le Smishing.
* C. Le Vishing.
* **Réponse correcte : C**
* *Explication* : Le *Vishing* (Hameçonnage vocal / Voice Phishing) utilise le téléphone pour usurper l'identité de conseillers bancaires ou de techniciens. Le *Smishing* utilise les SMS, et le *Spear-phishing* désigne des e-mails d'hameçonnage ultra-ciblés.

### Question 2 : Le Cheval de Troie
Quelle est la caractéristique d'un malware de type "Cheval de Troie" (Trojan) ?

* A. Il se propage de machine en machine de manière totalement autonome.
* B. Il se cache à l'intérieur d'un programme légitime pour infecter la machine.
* C. Il chiffre le disque dur et réclame une rançon sous 48h.
* **Réponse correcte : B**
* *Explication* : Comme dans le mythe grec, le cheval de Troie se fait passer pour un logiciel utile (ex. utilitaire de nettoyage gratuit) mais contient des fonctions cachées malveillantes. Un malware qui chiffre est un ransomware, et un malware autonome est un ver.

### Question 3 : La Cyber Kill Chain
Dans la méthodologie de la Cyber Kill Chain, à quelle étape correspond l'envoi d'un e-mail de phishing à une cible ?

* A. L'Armement.
* B. La Livraison.
* C. L'Exploitation.
* **Réponse correcte : B**
* *Explication* : La livraison (*Delivery*) consiste à transmettre l'arme cyber à la cible (par e-mail, USB, etc.). L'armement est la phase antérieure de conception du malware, et l'exploitation est l'exécution effective du malware sur la machine de la victime.

---

## Session 03 : Sécurité des systèmes & réseaux

### Question 1 : HTTP vs HTTPS
Quelle est la différence fondamentale entre le protocole HTTP et le protocole HTTPS ?

* A. HTTPS est beaucoup plus rapide pour charger des fichiers vidéo.
* B. HTTPS chiffre les flux d'informations échangés entre le navigateur et le serveur.
* C. HTTP n'est utilisable que sur les réseaux locaux d'entreprise.
* **Réponse correcte : B**
* *Explication* : HTTPS utilise les protocoles TLS/SSL pour chiffrer l'ensemble des échanges web, rendant les données illisibles pour un espion sur le réseau. HTTP fait transiter les données (mots de passe, numéros de cartes) en texte clair.

### Question 2 : Rôle du Pare-feu
Sur quel critère principal un pare-feu traditionnel prend-il sa décision d'autoriser ou de bloquer un paquet réseau ?

* A. La présence ou l'absence d'une signature de virus dans le message.
* B. Les adresses IP (source/destination) et les ports réseaux demandés.
* C. La longueur du mot de passe de l'utilisateur connecté.
* **Réponse correcte : B**
* *Explication* : Les pare-feux traditionnels filtrent la circulation réseau au niveau des couches de transport et réseau en se basant sur les adresses IP et les ports de communication (ex. fermer le port SSH 22). L'analyse de signatures de virus est réalisée par l'antivirus ou une passerelle de sécurité avancée (IDS/IPS).

### Question 3 : Emplacement des serveurs publics
Où doit-on placer le serveur web public d'une entreprise pour éviter qu'une intrusion sur ce serveur ne contamine immédiatement le réseau local des salariés ?

* A. Directement dans le réseau local interne (LAN).
* B. Dans une zone démilitarisée (DMZ).
* C. Sur le poste de travail de l'administrateur.
* **Réponse correcte : B**
* *Explication* : La DMZ isole les serveurs devant être accessibles depuis Internet. Si le serveur web est piraté, le pare-feu bloque les tentatives de connexion du pirate depuis la DMZ vers le réseau interne (LAN), agissant ainsi comme un sas de confinement.

---

## Session 04 : Sécurité du cloud, des données & des identités

### Question 1 : Le principe du moindre privilège
Dans une politique d'IAM (Identity and Access Management), qu'implique le "Principe du moindre privilège" ?

* A. Permettre à tous les employés de lire tous les fichiers pour encourager le partage d'informations.
* B. Limiter les accès d'un utilisateur aux seuls outils et dossiers strictement nécessaires à sa mission.
* C. Changer son mot de passe tous les vendredis matins.
* **Réponse correcte : B**
* *Explication* : Ce principe réduit la surface d'attaque en s'assurant qu'aucun compte n'a de privilèges inutiles. Ainsi, si un compte utilisateur simple est compromis par un pirate, les dégâts restent circonscrits à sa zone d'accès.

### Question 2 : L'authentification MFA
Quel groupe d'éléments représente une configuration MFA (authentification multifacteur) valide ?

* A. Deux mots de passe différents saisis l'un après l'autre.
* B. Un mot de passe (savoir) et un code reçu sur une application d'authentification mobile (possession).
* C. Une empreinte digitale (être) et une reconnaissance faciale (être).
* **Réponse correcte : B**
* *Explication* : Le MFA exige d'associer des facteurs de natures **différentes**. Saisir deux mots de passe utilise deux fois le facteur de connaissance ("ce que je sais"). L'empreinte et le visage utilisent deux fois le facteur d'inhérence ("ce que je suis"). Seule la réponse B associe deux facteurs distincts : connaissance + possession.

### Question 3 : La règle de sauvegarde 3-2-1
Selon la règle de sauvegarde 3-2-1, combien de supports physiques ou types de supports différents doit-on utiliser pour stocker ses sauvegardes ?

* A. 3 supports différents.
* B. 2 supports différents.
* C. 1 seul support à condition qu'il soit situé dans le cloud.
* **Réponse correcte : B**
* *Explication* : La règle 3-2-1 spécifie : 3 copies des données, stockées sur **2 supports physiques distincts** (ex. le disque dur du serveur local et une clé USB ou un NAS déconnecté), avec **1 copie hors site** (ex. dans le cloud).

---

## Session 05 : Gouvernance, risque, conformité & vie privée

### Question 1 : Le rôle de la PSSI
Qu'est-ce qu'une PSSI (Politique de Sécurité des Systèmes d'Information) ?

* A. Un logiciel antivirus centralisé sur les postes de travail.
* B. Un document stratégique définissant les règles et exigences de sécurité obligatoires au sein de l'entreprise.
* C. Une assurance protégeant contre le vol de données.
* **Réponse correcte : B**
* *Explication* : La PSSI formalise l'organisation et les règles de sécurité d'une structure. Signée par la direction générale, elle s'applique à tous les employés comme une loi interne.

### Question 2 : Traitement des risques
Une entreprise décide de ne pas héberger un fichier client hautement confidentiel et renonce au projet de prospection associé pour éliminer tout risque de fuite de données. Quelle stratégie de traitement de risques applique-t-elle ?

* A. Réduire le risque.
* B. Transférer le risque.
* C. Éviter le risque.
* **Réponse correcte : C**
* *Explication* : Éviter le risque consiste à abandonner l'activité ou le système qui génère le risque. En renonçant au projet et au fichier, le risque est supprimé à sa source.

### Question 3 : Principe du RGPD
Dans le cadre du RGPD, qu'impose le principe de "Minimisation des données" ?

* A. Stocker les données sur des serveurs miniatures à faible consommation d'énergie.
* B. Collecter uniquement les données strictement nécessaires au but poursuivi.
* C. Conserver les données pendant une durée d'un an maximum.
* **Réponse correcte : B**
* *Explication* : La minimisation exige de ne collecter que les données indispensables. Par exemple, demander la date de naissance d'un utilisateur pour sa simple inscription à une newsletter commerciale contrevient à ce principe.

---

## Session 06 : Opérations de sécurité & gestion des vulnérabilités

### Question 1 : Rôle du SIEM
Au sein d'un centre d'opérations de sécurité (SOC), quel est le rôle d'un outil SIEM ?

* A. Installer les correctifs de sécurité automatiquement sur les postes des employés.
* B. Bloquer le trafic réseau suspect directement au niveau du pare-feu périphérique.
* C. Centraliser et corréler les logs de divers systèmes pour détecter les comportements suspects.
* **Réponse correcte : C**
* *Explication* : Le SIEM (Security Information and Event Management) est un outil de centralisation et de corrélation de logs. Il ne patche pas (rôle du WSUS/Patch Manager) et ne bloque pas lui-même le réseau en direct (rôle du Firewall/IPS), mais il alerte les analystes SOC.

### Question 2 : Évaluation des failles (CVSS)
Un scanneur de vulnérabilités découvre une faille de sécurité sur un serveur et lui attribue un score CVSS de 9.8. Comment classe-t-on cette faille ?

* A. Faible.
* B. Élevée.
* C. Critique.
* **Réponse correcte : C**
* *Explication* : Le score CVSS va de 0.0 à 10.0. Les scores compris entre 9.0 et 10.0 sont qualifiés de critiques. Ils exigent un traitement en urgence absolue car la faille est simple à exploiter et présente des impacts majeurs sur la triade CIA.

### Question 3 : Scan de vulnérabilités vs Pentest
Quelle est la limite principale d'un scan de vulnérabilités automatique par rapport à un test d'intrusion (Pentest) ?

* A. Il est beaucoup plus long à exécuter (plusieurs semaines).
* B. Il génère des faux positifs et ne détecte pas les failles de logique complexe.
* C. Il exige l'arrêt complet de tous les serveurs de l'entreprise.
* **Réponse correcte : B**
* *Explication* : Les scanners automatiques comparent les numéros de version logicielle avec une base de CVE. Ils manquent de discernement contextuel, d'où la présence de faux positifs. Seul un pentester humain peut exploiter et enchaîner des vulnérabilités complexes de manière logique.

---

## Session 07 : Réponse aux incidents & introduction au forensics

### Question 1 : Ordre de volatilité
Dans une enquête de police scientifique informatique (Forensics), pourquoi récupère-t-on la mémoire vive (RAM) avant le disque dur ?

* A. Car la RAM est plus volumineuse et contient plus de photos.
* B. Car la RAM s'efface dès que l'ordinateur est mis hors tension (donnée hautement volatile).
* C. Car le disque dur est plus fragile et risque de se casser s'il est manipulé en premier.
* **Réponse correcte : B**
* *Explication* : La RAM contient des preuves cruciales (processus en cours d'exécution, clés de chiffrement de ransomware, connexions réseau). Ces données disparaissent à l'extinction. On parle de mémoire hautement volatile. Le disque dur conserve ses données hors tension, il est donc moins volatil.

### Question 2 : La chaîne de contrôle (Chain of Custody)
À quoi sert d'établir la chaîne de contrôle d'une preuve numérique ?

* A. À accélérer la réinstallation du système informatique nettoyé.
* B. À garantir que la preuve n'a pas été modifiée ni altérée lors de sa manipulation ou de son analyse.
* C. À masquer l'identité des analystes de sécurité ayant travaillé sur le dossier.
* **Réponse correcte : B**
* *Explication* : Pour qu'une preuve soit légalement recevable devant un tribunal, l'enquêteur doit prouver sa traçabilité stricte et son intégrité (par calcul de hachage SHA-256).

### Question 3 : Cadre pénal en France
En France, le fait d'accéder ou de se maintenir frauduleusement dans un système informatique sans contrat préalable constitue-t-il une infraction pénale ?

* A. Non, tant qu'aucune donnée n'est volée ou modifiée.
* B. Oui, c'est un délit (atteinte à un STAD) passible de prison et d'amende.
* C. Uniquement si le système piraté appartient à l'État ou à une banque.
* **Réponse correcte : B**
* *Explication* : L'accès non autorisé à un STAD (Système de Traitement Automatisé de Données) est puni pénalement dès l'intrusion, sans condition de vol ou de sabotage. Un audit (Pentest) exige un contrat écrit strict.

---

## Session 08 : Projet capstone — restitution & synthèse

### Question 1 : L'argumentaire de remédiation
Face à un client refusant de déployer le MFA car il le juge trop coûteux et contraignant, quel argumentaire de cybersécurité devez-vous employer ?

* A. Menacer le client d'appeler directement la police s'il ne coopère pas.
* B. Expliquer que le coût d'une paralysie par rançongiciel ou d'un vol de compte est infiniment supérieur à la gêne occasionnée par le MFA.
* C. Abandonner la mission car on ne peut pas forcer un client à se protéger.
* **Réponse correcte : B**
* *Explication* : La cybersécurité doit s'exprimer en termes financiers de réduction du risque. L'arbitrage bénéfice/risque montre que le MFA (souvent gratuit ou inclus dans les abonnements) évite des sinistres à plusieurs milliers d'euros.

### Question 2 : La feuille de route de remédiation
Dans une feuille de route de remédiation, à quel horizon temporel doit-on classer le déploiement du MFA sur les comptes administrateurs d'une PME ?

* A. À long terme (Mois 6+).
* B. À moyen terme (Mois 2-3).
* C. À court terme (Priorité immédiate - Mois 1).
* **Réponse correcte : C**
* *Explication* : Le MFA pour les administrateurs est une action critique, rapide à déployer et ayant un impact d'atténuation de risque immédiat et massif. C'est le fondement de l'hygiène cyber de premier jour.
