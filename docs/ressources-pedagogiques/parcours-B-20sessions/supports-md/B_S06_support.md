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

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer le fonctionnement des pare-feux et comparer les technologies de filtrage sans état (*stateless*), à état (*stateful*) et de nouvelle génération (NGFW).
* Différencier le rôle, le fonctionnement et le positionnement architectural d'un IDS (détection passive) et d'un IPS (prévention active).
* Concevoir et modéliser une architecture réseau sécurisée et segmentée en réseaux WAN, LAN et DMZ (Zone Démilitarisée), complétée par sa table de filtrage pare-feu.

---

### Glossaire
*   **Default Deny (Rejet par défaut)** — Politique de sécurité réseau qui consiste à bloquer toutes les communications par défaut, sauf celles explicitement autorisées.
*   **DMZ (Zone Démilitarisée)** — Sous-réseau physique ou logique isolé contenant les serveurs exposés à l'extérieur, servant de zone tampon avec le réseau interne.
*   **IDS (Intrusion Detection System)** — Équipement ou logiciel réseau analysant le trafic de manière passive pour détecter des comportements suspects ou des signatures d'attaques.
*   **IPS (Intrusion Prevention System)** — Équipement réseau actif capable d'analyser les paquets et de bloquer immédiatement les flux identifiés comme malveillants.

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

## 3. Ressources Complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Network Security - Part 2"* (durée estimée : 1h30).
*   **Ressource complémentaire** : Dessiner un schéma réseau simple à l'aide d'un outil en ligne gratuit (comme draw.io) en représentant une architecture comprenant un pare-feu, un switch, une DMZ et un LAN.

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
| **Default Deny (Rejet par défaut)** | Politique de sécurité réseau qui consiste à bloquer toutes les communications par défaut, sauf celles explicitement autorisées. |
| **DMZ (Zone Démilitarisée)** | Sous-réseau physique ou logique isolé contenant les serveurs exposés à l'extérieur, servant de zone tampon avec le réseau interne. |
| **IDS (Intrusion Detection System)** | Équipement ou logiciel réseau analysant le trafic de manière passive pour détecter des comportements suspects ou des signatures d'attaques. |
| **IPS (Intrusion Prevention System)** | Équipement réseau actif capable d'analyser les paquets et de bloquer immédiatement les flux identifiés comme malveillants. |
