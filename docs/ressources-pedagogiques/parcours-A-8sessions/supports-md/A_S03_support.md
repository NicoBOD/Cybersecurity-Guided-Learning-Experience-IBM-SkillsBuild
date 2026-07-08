# Support de cours — Session 03 : Sécurité des systèmes & réseaux
Parcours : A 8 sessions  |  Module : Réseau & Infrastructure  |  Niveau : Débutant

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Le filtrage réseau : Le pare-feu (*Firewall*)
    - Le tunnel sécurisé : Le VPN (*Virtual Private Network*)
    - HTTPS vs HTTP : Protéger la navigation web
    - La segmentation réseau et la DMZ
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

Le réseau est le système nerveux de toute infrastructure informatique. Sécuriser les flux de données qui y transitent et contrôler les accès extérieurs sont des exigences opérationnelles incontournables. Ce support de cours examine les technologies clés de la sécurité réseau. Vous découvrirez le fonctionnement d'un pare-feu (*firewall*), barrière de contrôle des flux entrants et sortants. Nous aborderons les réseaux privés virtuels (*VPN*), indispensables pour le travail à distance sécurisé, et analyserons la différence essentielle entre les protocoles HTTP (en clair) et HTTPS (chiffré). Enfin, nous étudierons la segmentation réseau, une stratégie défensive qui consiste à diviser le réseau d'une entreprise en zones isolées pour empêcher un attaquant de s'y déplacer librement en cas d'intrusion.

---

## 2. Développement

### Glossaire
* **Pare-feu (Firewall)** : Dispositif matériel ou logiciel analysant et filtrant les paquets de données circulant entre un réseau privé et un réseau public (Internet) selon des règles de sécurité.
* **VPN (Virtual Private Network)** : Technologie créant un tunnel chiffré et sécurisé sur un réseau public pour acheminer de manière confidentielle les données d'un poste de travail vers le réseau de l'entreprise.
* **HTTPS (HyperText Transfer Protocol Secure)** : Version sécurisée du protocole HTTP utilisée pour le web, chiffrant les échanges entre le navigateur de l'utilisateur et le serveur web pour empêcher l'interception.
* **SSL / TLS** : Protocoles de sécurisation des échanges sur Internet, servant de socle de chiffrement pour HTTPS.
* **Segmentation réseau** : Technique consistant à partitionner un réseau informatique en plusieurs sous-réseaux (VLANs, DMZ) distincts pour limiter la propagation des menaces.
* **DMZ (Zone Démilitarisée)** : Sous-réseau d'une entreprise isolé du réseau interne, hébergeant les serveurs devant être accessibles depuis Internet (ex. serveur web public) afin de protéger les postes internes de toute intrusion sur ces serveurs.

---

### 1. Le filtrage réseau : Le pare-feu (*Firewall*)

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.


Le pare-feu agit comme un douanier à la frontière du réseau de l'entreprise. Il inspecte chaque paquet de données qui se présente et prend une décision : **Autoriser** (*Accept/Allow*) ou **Bloquer** (*Drop/Deny*).

Le filtrage traditionnel s'appuie sur des règles basées sur trois critères principaux :

* **L'adresse IP source et destination** : Qui envoie le paquet et à qui est-il adressé ?
* **Le protocole** : Quel protocole est utilisé (TCP, UDP, ICMP) ?
* **Le port de communication** : Quel canal logique est ciblé (ex. le port 80 pour HTTP, 443 pour HTTPS, 22 pour SSH) ?

*Exemple de règle simple* : Autoriser tous les ordinateurs du réseau interne à envoyer du trafic vers Internet uniquement sur le port 443 (HTTPS), et bloquer toutes les connexions entrantes provenant d'Internet initiées vers le réseau interne.



### 2. Le tunnel sécurisé : Le VPN (*Virtual Private Network*)

Lorsque vous naviguez sur Internet depuis un réseau Wi-Fi public (ex. dans un café ou une gare), n'importe quel attaquant situé sur le même réseau peut intercepter vos flux non chiffrés. De même, un employé travaillant depuis chez lui a besoin d'accéder aux fichiers internes de l'entreprise sans exposer ces ressources directement sur Internet.

Le VPN résout ce problème en créant un **tunnel chiffré** entre l'ordinateur de l'utilisateur et la passerelle VPN de l'entreprise.

* Les données quittent l'ordinateur sous forme chiffrée.
* Elles transitent par Internet de manière totalement illisible pour les intermédiaires (fournisseurs d'accès, pirates).
* Elles arrivent à la passerelle VPN de l'entreprise qui les déchiffre et les transmet au réseau interne comme si l'utilisateur était physiquement assis à son bureau dans l'entreprise.



### 3. HTTPS vs HTTP : Protéger la navigation web

* Le protocole **HTTP** transmet toutes les données en clair. Si vous saisissez un mot de passe ou un numéro de carte bancaire sur un site HTTP, un pirate connecté sur le même réseau peut le lire sans effort.
* Le protocole **HTTPS** utilise le protocole TLS pour chiffrer la communication. Même interceptées, les données apparaissent comme une suite incohérente de caractères aléatoires. De plus, HTTPS fournit un certificat numérique garantissant l'identité du site visité (pour éviter que l'utilisateur ne se connecte à un faux site).



### 4. La segmentation réseau et la DMZ

Dans un réseau non segmenté (appelé "réseau plat"), si le poste d'un commercial est infecté par un malware, ce dernier peut se propager immédiatement aux serveurs de production, aux bases de données RH et à la comptabilité. C'est ce qu'on appelle le **déplacement latéral**.

Pour empêcher cela, on segmente le réseau en zones logiques étanches séparées par un pare-feu :

1. **La zone LAN interne** : Les ordinateurs des employés de bureau.
2. **La zone Wi-Fi invités** : Destinée aux visiteurs (sans accès au LAN interne).
3. **La DMZ (Zone Démilitarisée)** : Contient les serveurs ouverts sur l'extérieur (site internet, serveur e-mail). Si le serveur web de la DMZ est piraté, les règles du pare-feu lui interdisent d'initier des connexions vers le LAN interne, stoppant net la progression de l'attaquant.

---

### Focus pratique
Voici comment se structure une table de filtrage (règles ordonnées de haut en bas ; la première règle correspondante s'applique) :

| Priorité | Source | Destination | Protocole / Port | Action | Commentaire |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **1** | Interne (LAN) | Externe (Internet) | TCP / 443 (HTTPS) | **AUTORISER** | Permet la navigation web sécurisée des employés. |
| **2** | Externe (Internet) | Serveur Web (DMZ) | TCP / 443 (HTTPS) | **AUTORISER** | Permet aux internautes d'accéder au site web public. |
| **3** | Serveur Web (DMZ) | Interne (LAN) | Tout | **BLOQUER** | Empêche le serveur web compromis d'attaquer les postes internes. |
| **4** | Tout | Tout | Tout | **BLOQUER** | Règle par défaut (Bloquer tout ce qui n'est pas explicitement autorisé). |

---

### Exercice d'application
**Titre** : Modélisation d'une architecture réseau sécurisée pour un commerce

### Énoncé
Vous devez concevoir la segmentation réseau d'une boutique connectée comprenant :

- 2 caisses enregistreuses informatiques (traitant des données financières sensibles).
- 1 ordinateur de bureau pour le gérant (utilisé pour les commandes fournisseurs et la comptabilité).
- 1 borne Wi-Fi gratuite mise à la disposition des clients de la boutique.

1. Proposez un schéma logique de segmentation en créant 3 zones réseau distinctes.
2. Définissez les droits d'accès réseau :
   * La borne Wi-Fi clients peut-elle communiquer avec les caisses ?
   * Les caisses peuvent-elles communiquer avec l'ordinateur du gérant ?
   * Quelles zones doivent avoir accès à Internet ?



### Corrigé de l'exercice
1. **Zones proposées** :
   * *Zone 1 : Réseau Caisses (Strictement sécurisé)*
   * *Zone 2 : Réseau Gestion (Gérant)*
   * *Zone 3 : Réseau Invités (Clients)*
2. **Droits d'accès et règles de filtrage** :
   * **Non**, la borne Wi-Fi clients doit être totalement isolée du réseau des caisses et du réseau gestion pour éviter toute tentative d'intrusion de la part de clients malveillants.
   * **Non**, les caisses ne doivent pas initier de communications vers l'ordinateur du gérant. Elles doivent uniquement envoyer les transactions vers le serveur de paiement externe.
   * **Accès Internet** : La zone Clients doit avoir accès à Internet uniquement (ports 80/443). La zone Caisses doit avoir un accès limité uniquement aux adresses IP du serveur de traitement des cartes bancaires. La zone Gestion doit avoir un accès web global pour son activité.

---

## 3. Ressources Complémentaires

* **IBM SkillsBuild** : Cours "Network Security Fundamentals".
* **ANSSI** : Recommandations sur la sécurisation des architectures réseaux.
* **Wireshark (outil tiers)** : Outil d'analyse de protocoles réseaux (pour observer la structure des paquets).

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
| **Pare-feu (Firewall)** | Dispositif matériel ou logiciel analysant et filtrant les paquets de données circulant entre un réseau privé et un réseau public (Internet) selon des règles de sécurité. |
| **VPN (Virtual Private Network)** | Technologie créant un tunnel chiffré et sécurisé sur un réseau public pour acheminer de manière confidentielle les données d'un poste de travail vers le réseau de l'entreprise. |
| **HTTPS (HyperText Transfer Protocol Secure)** | Version sécurisée du protocole HTTP utilisée pour le web, chiffrant les échanges entre le navigateur de l'utilisateur et le serveur web pour empêcher l'interception. |
| **SSL / TLS** | Protocoles de sécurisation des échanges sur Internet, servant de socle de chiffrement pour HTTPS. |
| **Segmentation réseau** | Technique consistant à partitionner un réseau informatique en plusieurs sous-réseaux (VLANs, DMZ) distincts pour limiter la propagation des menaces. |
| **DMZ (Zone Démilitarisée)** | Sous-réseau d'une entreprise isolé du réseau interne, hébergeant les serveurs devant être accessibles depuis Internet (ex. serveur web public) afin de protéger les postes internes de toute intrusion sur ces serveurs. |
