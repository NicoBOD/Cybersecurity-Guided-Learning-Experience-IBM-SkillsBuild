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

### Approfondissement technique pour le mentor (Contenu dense)

**1. Modèle OSI et Sécurité en couches**
Prenez le temps d'expliquer les couches clés du modèle OSI (Liaison, Réseau, Transport, Application). Expliquez pourquoi un pare-feu traditionnel (Couche 3/4) ne peut pas bloquer une attaque d'injection SQL (Couche 7), justifiant ainsi le besoin d'un WAF (Web Application Firewall).

**2. Segmentation réseau et DMZ**
Illustrez sur un tableau blanc (ou virtuel) l'architecture d'un réseau sécurisé :
- La **DMZ** (Zone Démilitarisée) qui héberge les serveurs publics (Serveur Web).
- Le **LAN** interne qui héberge la base de données.
Expliquez la règle d'or : la DMZ peut être interrogée par Internet, mais ne doit jamais initier de connexion non sollicitée vers le LAN interne.

**3. Vulnérabilités des protocoles historiques**
Discutez des failles inhérentes aux vieux protocoles (Telnet, FTP, HTTP) qui font transiter les mots de passe en clair sur le réseau. Expliquez la mécanique d'interception (Sniffing) et la transition obligatoire vers SSH, SFTP et HTTPS.


---

### Glossaire

*   **DMZ (Demilitarized Zone)** — Zone réseau intermédiaire isolée du réseau interne et d'Internet, hébergeant les serveurs devant être accessibles depuis l'extérieur.
*   **DMZ (Zone Démilitarisée)** — Sous-réseau d'une entreprise isolé du réseau interne, hébergeant les serveurs devant être accessibles depuis Internet (ex. serveur web public) afin de protéger les postes internes de toute intrusion sur ces serveurs.
*   **Firewall (Pare-feu)** — Équipement ou logiciel réseau filtrant les paquets de données entrants et sortants selon des règles de sécurité prédéfinies.
*   **HTTPS (HyperText Transfer Protocol Secure)** — Version sécurisée du protocole HTTP utilisée pour le web, chiffrant les échanges entre le navigateur de l'utilisateur et le serveur web pour empêcher l'interception.
*   **Pare-feu (Firewall)** — Dispositif matériel ou logiciel analysant et filtrant les paquets de données circulant entre un réseau privé et un réseau public (Internet) selon des règles de sécurité.
*   **Segmentation réseau** — Technique consistant à partitionner un réseau informatique en plusieurs sous-réseaux (VLANs, DMZ) distincts pour limiter la propagation des menaces.
*   **SSL / TLS** — Protocoles de sécurisation des échanges sur Internet, servant de socle de chiffrement pour HTTPS.
*   **VLAN (Virtual Local Area Network)** — Technologie permettant de segmenter un réseau physique unique en plusieurs réseaux locaux logiques indépendants.
*   **VPN (Virtual Private Network)** — Technologie créant un tunnel chiffré et sécurisé sur un réseau public pour acheminer de manière confidentielle les données d'un poste de travail vers le réseau de l'entreprise.
*   **VPN (Virtual Private Network)** — Réseau privé virtuel créant un tunnel chiffré pour acheminer de manière sécurisée les communications sur un réseau non sûr comme Internet.

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


### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez que le réseau informatique de votre entreprise est un **grand immeuble de bureaux** :
    - **Le Pare-feu (Firewall)** est le guichet de réception à l'entrée. Il contrôle l'identité de chaque visiteur et refuse systématiquement ceux qui ne sont pas sur la liste d'invités.
    - **La DMZ (Zone Démilitarisée)** est la salle d'attente à l'accueil. Les visiteurs externes peuvent s'y installer, mais des portes blindées et verrouillées les empêchent d'accéder aux bureaux internes.
    - **La segmentation réseau (VLAN)** correspond aux badges d'accès par étage : la comptabilité ne peut pas monter à l'étage de la R&D sans badge spécifique.
    - **Le VPN** est un tunnel souterrain sécurisé et invisible menant directement de votre domicile à votre bureau, empêchant quiconque dans la rue de voir vos déplacements.

**Exemple d'application professionnelle :**
Une PME de logistique héberge son site web public sur un serveur en DMZ. Suite à une faille sur le site, le serveur est compromis. Grâce au pare-feu interne et à la segmentation réseau, le pirate est confiné dans la DMZ et ne peut pas rebondir vers le réseau interne où sont stockés les fichiers clients et les bases de données comptables.


### Panorama des solutions du marché (Commerciales & Open-Source)

La sécurité des systèmes et réseaux repose sur des pare-feux et des outils de chiffrement des communications :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Fortinet FortiGate** : Pare-feu de nouvelle génération (NGFW) leader mondial en termes de rapport performances/coût, très populaire auprès des PME et grandes entreprises.
    *   **Palo Alto Networks (PA-Series)** : Solution NGFW haut de gamme offrant le niveau de détection applicative le plus précis, leader historique du Magic Quadrant de Gartner.
    *   **Stormshield Network Security (SNS)** : Solution de pare-feu souveraine française (certifiée par l'ANSSI au plus haut niveau de sécurité), idéale pour la conformité et la protection des infrastructures critiques.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **pfSense Community Edition** : L'un des pare-feux open-source les plus puissants du marché. Basé sur FreeBSD, il offre des fonctionnalités d'administration complètes (filtrage, VPN, routage, IDS/IPS).
    *   **OPNsense** : Fork moderne de pfSense, apprécié pour son interface utilisateur intuitive et ses intégrations de sécurité régulières.
    *   **OpenVPN / WireGuard** : Protocoles et logiciels VPN open-source pour sécuriser les accès distants et connecter des sites distants de manière chiffrée.

## 3. Ressources complémentaires

* **IBM SkillsBuild** : Cours "Network Security Fundamentals".
* **ANSSI** : Recommandations sur la sécurisation des architectures réseaux.
* **Wireshark (outil tiers)** : Outil d'analyse de protocoles réseaux (pour observer la structure des paquets).


---

* [ANSSI - Guide hygiène informatique](https://cyber.gouv.fr/publications/guide-dhygiene-informatique)
* [OWASP - Top 10](https://owasp.org/www-project-top-ten/)

## 4. Exercice bonus

- **Objectif :** Conception d'architecture réseau sécurisée.
- **Consignes :**
    1. Vous devez concevoir le schéma réseau simplifié d'une clinique. Placez les éléments suivants dans les bonnes zones (Internet, DMZ, LAN Interne, Réseau Médical) : Serveur web public, Postes des secrétaires, Appareils d'imagerie médicale (IRM/Scanners), Base de données des patients.
    2. Justifiez la séparation du Réseau Médical par rapport au LAN Interne classique.
    3. Indiquez quelle règle de filtrage principale doit s'appliquer sur le pare-feu pour protéger la base de données des patients.
- **Correction pour le mentor :** Le serveur web va en DMZ ; les postes des secrétaires dans le LAN Interne ; les IRM et la base de données dans le Réseau Médical (zone ultra-sécurisée). La séparation protège les dispositifs de santé critiques d'une infection provenant d'une secrétaire ayant cliqué sur un mail malveillant. La règle principale doit être : interdire tout trafic direct depuis Internet vers la base de données, et n'autoriser que les requêtes provenant de l'application métier validée.

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **DMZ (Zone Démilitarisée)** | Sous-réseau d'une entreprise isolé du réseau interne, hébergeant les serveurs devant être accessibles depuis Internet (ex. serveur web public) afin de protéger les postes internes de toute intrusion sur ces serveurs. |
| **Firewall (Pare-feu)** | Équipement ou logiciel réseau filtrant les paquets de données entrants et sortants selon des règles de sécurité prédéfinies. |
| **HTTPS (HyperText Transfer Protocol Secure)** | Version sécurisée du protocole HTTP utilisée pour le web, chiffrant les échanges entre le navigateur de l'utilisateur et le serveur web pour empêcher l'interception. |
| **Pare-feu (Firewall)** | Dispositif matériel ou logiciel analysant et filtrant les paquets de données circulant entre un réseau privé et un réseau public (Internet) selon des règles de sécurité. |
| **Segmentation réseau** | Technique consistant à partitionner un réseau informatique en plusieurs sous-réseaux (VLANs, DMZ) distincts pour limiter la propagation des menaces. |
| **SSL / TLS** | Protocoles de sécurisation des échanges sur Internet, servant de socle de chiffrement pour HTTPS. |
| **VLAN (Virtual Local Area Network)** | Technologie permettant de segmenter un réseau physique unique en plusieurs réseaux locaux logiques indépendants. |
| **VPN (Virtual Private Network)** | Technologie créant un tunnel chiffré et sécurisé sur un réseau public pour acheminer de manière confidentielle les données d'un poste de travail vers le réseau de l'entreprise. |

