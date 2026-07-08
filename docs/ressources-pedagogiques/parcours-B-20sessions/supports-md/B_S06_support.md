# Session B06 — Défenses réseau

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Les Pare-feux (Firewalls) et leurs évolutions
    - IDS et IPS : La surveillance du trafic
    - La segmentation réseau et la DMZ
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Un pare-feu filtre les paquets selon le principe du **Default Deny** (tout ce qui n'est pas permis est interdit).
*   Les pare-feux évoluent du filtrage simple (*stateless*) au maintien de session (*stateful*), jusqu'à l'inspection applicative profonde (*NGFW*).
*   L'**IDS** détecte passivement les intrusions pour alerter, tandis que l'**IPS** s'interpose pour bloquer activement l'attaque en cours de route.
*   La **segmentation réseau** consiste à isoler les hôtes dans différentes zones (LAN, WAN, DMZ) pour confiner les incidents et empêcher les mouvements latéraux des attaquants.

---

## 2. Développement
Détaillez le fonctionnement d'un Pare-feu de Nouvelle Génération (NGFW). Contrairement à un firewall stateful classique qui regarde juste IP/Port, le NGFW fait du *Deep Packet Inspection* (DPI). Il peut voir qu'un flux sur le port 443 autorisé n'est pas du HTTPS normal, mais un tunnel malveillant. Expliquez la différence avec un IPS (actif) et un IDS (passif).

---

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer le fonctionnement des pare-feux et comparer les technologies de filtrage sans état (*stateless*), à état (*stateful*) et de nouvelle génération (NGFW).
* Différencier le rôle, le fonctionnement et le positionnement architectural d'un IDS (détection passive) et d'un IPS (prévention active).
* Concevoir et modéliser une architecture réseau sécurisée et segmentée en réseaux WAN, LAN et DMZ (Zone Démilitarisée), complétée par sa table de filtrage pare-feu.

---

### Glossaire

*   **Default Deny (Rejet par défaut)** — Politique de sécurité réseau qui consiste à bloquer toutes les communications par défaut, sauf celles explicitement autorisées.
*   **DMZ (Zone Démilitarisée)** — Sous-réseau physique ou logique isolé contenant les serveurs exposés à l'extérieur, servant de zone tampon avec le réseau interne.
*   **DMZ (Zone Démilitarisée)** — Sous-réseau isolé hébergeant les ressources publiques pour empêcher tout accès direct au réseau interne depuis Internet.
*   **Firewall (Pare-feu)** — Équipement filtrant les flux réseau entrants et sortants sur la base d'une politique de sécurité (ACL).
*   **IDS (Intrusion Detection System)** — Équipement ou logiciel réseau analysant le trafic de manière passive pour détecter des comportements suspects ou des signatures d'attaques.
*   **IDS (Intrusion Detection System)** — Système passif détectant et signalant les comportements réseau suspects ou les signatures d'attaques connues.
*   **IPS (Intrusion Prevention System)** — Équipement réseau actif capable d'analyser les paquets et de bloquer immédiatement les flux identifiés comme malveillants.
*   **IPS (Intrusion Prevention System)** — Système actif capable de détecter et de bloquer automatiquement les flux malveillants identifiés sur un réseau.

---

### Concepts clés

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

### 1. Les Pare-feux (Firewalls) et leurs évolutions
Un pare-feu est un équipement de sécurité réseau chargé de filtrer les flux d'informations entrants et sortants selon des règles prédéfinies. Le principe fondamental d'un pare-feu est le **Default Deny** (Rejet par défaut) : tout trafic qui n'est pas explicitement autorisé par une règle est bloqué.

On distingue plusieurs générations de pare-feux :

*   **Filtrage sans état (*Stateless*)** : Analyse chaque paquet individuellement sans aucun historique. Il vérifie uniquement si les adresses IP et ports correspondent à ses règles.
    *   *Analogie* : Un portier de boîte de nuit qui vérifie si votre nom est sur la liste d'invités, mais oublie votre visage dès que vous franchissez le pas de la porte.
*   **Filtrage à état (*Stateful*)** : Garde en mémoire le contexte des connexions initiées (table des états). Si une machine interne initie une connexion vers l'extérieur, le pare-feu s'en souvient et laisse passer le trafic de retour associé, tout en bloquant les paquets entrants non sollicités.
    *   *Analogie* : Le même portier qui vous remet un bracelet tamponné lors de votre sortie temporaire pour vous laisser re-rentrer sans contrôle d'identité.
*   **Nouvelle Génération (NGFW — *Next-Generation Firewall*)** : Il combine le filtrage à état avec l'analyse applicative profonde (*Deep Packet Inspection* — DPI). Il est capable de reconnaître l'application réelle utilisée (ex. différencier un transfert de fichier Dropbox d'un simple surf web, même s'ils utilisent tous deux le port 443) et d'intégrer des modules antivirus et de filtrage d'URL.
    *   *Analogie* : Un agent des douanes qui contrôle votre passeport (IP), se souvient de votre trajet (état) et ouvre votre valise pour inspecter son contenu (DPI).
*   **Pare-feu Applicatif Web (WAF — *Web Application Firewall*)** : Outil spécialisé placé devant les serveurs web pour analyser et bloquer les attaques de niveau applicatif (comme les injections SQL ou le Cross-Site Scripting — XSS).

### 2. IDS et IPS : La surveillance du trafic
Malgré les pare-feux, des flux autorisés peuvent contenir du trafic malveillant (ex. un exploit caché dans une requête HTTPS autorisée). C'est là qu'interviennent les systèmes de détection et de prévention :

*   **IDS (*Intrusion Detection System*)** : Système passif qui écoute une copie du trafic réseau (port miroir). Il compare le trafic à des signatures d'attaques connues ou détecte des comportements anormaux. S'il détecte une menace, il génère une alerte pour l'analyste de sécurité, mais **ne bloque pas** le trafic.
*   **IPS (*Intrusion Prevention System*)** : Système actif placé directement au milieu du flux réseau (*inline*). S'il détecte un paquet malveillant, il le détruit immédiatement pour empêcher l'attaque d'atteindre sa cible.

### 3. La segmentation réseau et la DMZ
Pour éviter qu'un pirate ayant compromis une machine n'accède facilement à tout le réseau de l'entreprise (mouvement latéral), il est impératif de diviser le réseau en zones isolées logiquement :

*   **WAN (*Wide Area Network*)** : Le réseau public non sûr (Internet).
*   **LAN (*Local Area Network*)** : Le réseau local interne de l'entreprise, contenant les ordinateurs des salariés et les données confidentielles.
*   **DMZ (*Demilitarized Zone* — Zone Démilitarisée)** : Zone réseau intermédiaire isolée du LAN. C'est ici que l'on place les serveurs qui doivent être accessibles depuis Internet (serveur Web public, serveur de messagerie).

> 💡 **Bon à savoir : La règle d'or de la DMZ**
> Les machines situées dans la DMZ sont par définition exposées et donc susceptibles d'être piratées. La règle d'or de sécurité consiste à **interdire toute connexion initiée depuis la DMZ vers le LAN**. Si un serveur web en DMZ est compromis, l'attaquant ne pourra pas s'en servir de rebond pour attaquer les ordinateurs internes de l'entreprise.

---

### Activités / exercices
### Exercice 1 — Zonage réseau et table de filtrage de l'entreprise "EcoLog"
**Objectif :** Concevoir le schéma d'architecture réseau segmenté et configurer la table de règles pare-feu de base pour protéger les infrastructures d'une entreprise.

**Consignes :**
L'entreprise EcoLog souhaite sécuriser son réseau composé de :

*   Un réseau interne (LAN) : ordinateurs des employés (`192.168.10.0/24`).
*   Une zone DMZ : un serveur web public (`192.168.20.5`) hébergeant le site e-commerce.
*   L'accès Internet (WAN) représenté par n'importe quelle adresse (`Any`).

Rédigez la table de règles du pare-feu central (contenant 4 règles clés + la règle de fermeture par défaut) en respectant les besoins métiers suivants :

1.  Les clients d'Internet (WAN) doivent pouvoir visiter le site web de l'entreprise en HTTPS (port 443).
2.  Les employés du LAN doivent pouvoir naviguer sur Internet en HTTP et HTTPS pour leurs recherches.
3.  Le serveur web en DMZ doit pouvoir télécharger ses mises à jour logicielles sur Internet (HTTPS uniquement).
4.  L'administrateur système situé sur le LAN doit pouvoir gérer le serveur web en DMZ via SSH (port 22).
5.  Appliquez le principe du *Default Deny*.

**Tableau à remplir :**

| N° Règle | Zone Source | IP Source | Zone Destination | IP Destination | Port / Service | Action |
|---|---|---|---|---|---|---|
| 1 | ... | ... | ... | ... | ... | ... |
| 2 | ... | ... | ... | ... | ... | ... |
| 3 | ... | ... | ... | ... | ... | ... |
| 4 | ... | ... | ... | ... | ... | ... |
| 5 | Any | Any | Any | Any | Any | Deny |

**Corrigé / Éléments de réponse :**

| N° Règle | Zone Source | IP Source | Zone Destination | IP Destination | Port / Service | Action | Explication |
|---|---|---|---|---|---|---|---|
| **1** | WAN | Any | DMZ | `192.168.20.5` | TCP/443 (HTTPS) | **Allow** | Autorise les clients externes à accéder au site e-commerce sécurisé. |
| **2** | LAN | `192.168.10.0/24` | WAN | Any | TCP/80, 443 (HTTP/S) | **Allow** | Permet aux employés internes de naviguer sur le web. |
| **3** | DMZ | `192.168.20.5` | WAN | Any | TCP/443 (HTTPS) | **Allow** | Permet au serveur web de chercher ses mises à jour en HTTPS. |
| **4** | LAN | `192.168.10.0/24` | DMZ | `192.168.20.5` | TCP/22 (SSH) | **Allow** | Permet à l'administrateur de gérer le serveur web depuis le réseau interne. |
| **5** | Any | Any | Any | Any | Any | **Deny** | Règle implicite de blocage de tout trafic non mentionné ci-dessus. |

---

### Questions de réflexion
1. Pourquoi est-il déconseillé de configurer une règle permettant à un serveur web situé en DMZ d'initier une connexion vers la base de données de production située dans le LAN interne ? Comment contourner ce besoin de manière sécurisée ?
2. Un pare-feu de nouvelle génération (NGFW) détecte un flux HTTPS sur le port 443 contenant un malware connu. Pourquoi un pare-feu traditionnel de type "stateful" n'aurait pas pu bloquer cette menace ?

**Corrigé / Éléments de réponse :**
1. La DMZ est plus exposée ; si le serveur web est compromis, il pourrait attaquer le LAN. Le LAN (BDD) doit initier la connexion vers la DMZ, ou bien on met un proxy inverse ultra-filtré.
2. Le pare-feu stateful ne regarde que les ports et adresses IP (ici 443 est autorisé). Le NGFW inspecte le contenu (DPI) pour y détecter le malware, même sur un port autorisé.

---


### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez les défenses et la segmentation d'un réseau comme la sécurité d'un **aéroport sécurisé** :
    - **La DMZ (Zone Démilitarisée)** est la zone publique d'accueil (enregistrement, boutiques). Tout le monde peut y entrer depuis la rue (Internet), mais des barrières de sécurité et des portiques de contrôle empêchent les visiteurs de passer plus loin sans vérification.
    - **Le Pare-feu (Firewall)** est le poste de contrôle des frontières. Il examine les billets (paquets de données) et vérifie si le passager est autorisé à passer.
    - **L'IDS / IPS** correspond aux agents de sécurité en patrouille. L'IDS surveille et signale un comportement louche. L'IPS intervient directement pour menotter et expulser l'intrus (bloquer la connexion).
    - **La segmentation par VLAN** correspond aux portes réservées aux employés avec lecteurs de badges : un passager du LAN public ne peut pas entrer dans la zone de tri des bagages.

**Exemple d'application professionnelle :**
Une entreprise sépare ses ordinateurs de bureau de son réseau industriel (machines-outils). Suite à l'infection d'un poste administratif par un rançongiciel, la segmentation réseau par VLAN et l'IDS/IPS détectent le trafic suspect et bloquent la propagation à la couche réseau, sauvant ainsi la chaîne de production d'un chiffrement catastrophique.


### Panorama des solutions du marché (Commerciales & Open-Source)

La mise en place de défenses réseau robustes s'appuie sur des équipements de routage et de filtrage NGFW :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Fortinet FortiGate** : Pare-feu de nouvelle génération (NGFW) leader mondial en termes de rapport performances/coût, très populaire auprès des PME et grandes entreprises.
    *   **Palo Alto Networks (PA-Series)** : Solution NGFW haut de gamme offrant le niveau de détection applicative le plus précis, leader historique du Magic Quadrant de Gartner.
    *   **Stormshield Network Security (SNS)** : Solution de pare-feu souveraine française (certifiée par l'ANSSI au plus haut niveau de sécurité), idéale pour la conformité et la protection des infrastructures critiques.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **pfSense Community Edition** : L'un des pare-feux open-source les plus puissants du marché. Basé sur FreeBSD, il offre des fonctionnalités d'administration complètes (filtrage, VPN, routage, IDS/IPS).
    *   **OPNsense** : Fork moderne de pfSense, apprécié pour son interface utilisateur intuitive et ses intégrations de sécurité régulières.
    *   **IPFire** : Pare-feu open-source basé sur Linux, réputé pour sa modularité et sa faible empreinte matérielle sur de petits serveurs.
    *   **VyOS** : Système d'exploitation réseau open-source basé sur Debian, permettant de créer des routeurs et pare-feux virtuels robustes.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Network Security - Part 2"* (durée estimée : 1h30).
*   **Ressource complémentaire** : Dessiner un schéma réseau simple à l'aide d'un outil en ligne gratuit (comme draw.io) en représentant une architecture comprenant un pare-feu, un switch, une DMZ et un LAN.


---

* [ANSSI - Passerelles d'accès à Internet](https://cyber.gouv.fr)
* [OWASP - Network Security](https://owasp.org/)

## 4. Exercice bonus

- **Objectif :** Conception de règles de filtrage pour pare-feu (ACL).
- **Consignes :**
    1. Vous devez configurer les règles de sécurité du pare-feu d'une PME. Remplissez le tableau de règles (Source, Destination, Port, Action) pour respecter les contraintes suivantes :
       - Autoriser les utilisateurs du LAN interne (`192.168.10.0/24`) à naviguer sur le Web (HTTP/HTTPS).
       - Autoriser les connexions depuis Internet vers le serveur web public de la DMZ (`10.0.5.8`) uniquement sur le port sécurisé HTTPS.
       - Interdire tout autre trafic par défaut (Implicit Deny).
- **Correction pour le mentor :** Le tableau final doit comprendre :
  - Règle 1 : Src=`192.168.10.0/24`, Dst=`Any`, Port=`80, 443`, Action=`ALLOW`
  - Règle 2 : Src=`Any`, Dst=`10.0.5.8`, Port=`443`, Action=`ALLOW`
  - Règle 3 : Src=`Any`, Dst=`Any`, Port=`Any`, Action=`DENY` (Implicit Deny en fin de liste). Le mentor validera la présence de la règle de rejet par défaut à la fin.

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Default Deny (Rejet par défaut)** | Politique de sécurité réseau qui consiste à bloquer toutes les communications par défaut, sauf celles explicitement autorisées. |
| **DMZ (Zone Démilitarisée)** | Sous-réseau physique ou logique isolé contenant les serveurs exposés à l'extérieur, servant de zone tampon avec le réseau interne. |
| **Firewall (Pare-feu)** | Équipement filtrant les flux réseau entrants et sortants sur la base d'une politique de sécurité (ACL). |
| **IDS (Intrusion Detection System)** | Équipement ou logiciel réseau analysant le trafic de manière passive pour détecter des comportements suspects ou des signatures d'attaques. |
| **IPS (Intrusion Prevention System)** | Équipement réseau actif capable d'analyser les paquets et de bloquer immédiatement les flux identifiés comme malveillants. |

