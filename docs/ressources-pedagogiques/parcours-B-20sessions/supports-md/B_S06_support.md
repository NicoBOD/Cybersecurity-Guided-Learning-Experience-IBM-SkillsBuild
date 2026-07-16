# Session B06 — Défenses réseau
Parcours : B 20 sessions  |  Module : B — Systèmes & réseaux  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Les Pare-feux (Firewalls) et leurs évolutions
    - IDS et IPS : La surveillance du trafic
    - La segmentation réseau et la DMZ
    - Une affaire réelle : Target (2013), le géant piraté via son prestataire de chauffage
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Un pare-feu filtre les paquets selon le principe du **Default Deny** (tout ce qui n'est pas permis est interdit).
*   Les pare-feux évoluent du filtrage simple (*stateless*) au maintien de session (*stateful*), jusqu'à l'inspection applicative profonde (*NGFW*).
*   L'**IDS** détecte passivement les intrusions pour alerter, tandis que l'**IPS** s'interpose pour bloquer activement l'attaque en cours de route.
*   La **segmentation réseau** consiste à isoler les hôtes dans différentes zones (LAN, WAN, DMZ) pour confiner les incidents et empêcher les mouvements latéraux des attaquants.

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer le fonctionnement des pare-feux et comparer les technologies de filtrage sans état (*stateless*), à état (*stateful*) et de nouvelle génération (NGFW).
* Différencier le rôle, le fonctionnement et le positionnement architectural d'un IDS (détection passive) et d'un IPS (prévention active).
* Concevoir et modéliser une architecture réseau sécurisée et segmentée en réseaux WAN, LAN et DMZ (Zone Démilitarisée), complétée par sa table de filtrage pare-feu.

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** En 2013, le distributeur américain Target s'est fait voler 40 millions de numéros de cartes bancaires. Par où les attaquants sont-ils entrés ?

    - A) Une faille du site web de Target
    - B) Les identifiants volés d'un prestataire de chauffage et climatisation ✅
    - C) Un employé corrompu du service informatique

    **Débrief mentor :** Réponse B : les attaquants ont hameçonné un petit prestataire de chauffage/climatisation, récupéré ses identifiants d'accès au portail fournisseurs de Target... et de là, ont cheminé jusqu'aux caisses enregistreuses de près de 1 800 magasins. Entre le portail fournisseurs et les caisses, il aurait dû y avoir des **murailles internes**. Il n'y en avait pas assez. Construire ces murailles — pare-feux, zones, règles de filtrage — c'est exactement le programme de ce soir. L'histoire complète de Target arrive en seconde partie.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Le NGFW et l'inspection profonde**
Détaillez le fonctionnement d'un pare-feu de nouvelle génération (NGFW) : contrairement au pare-feu à état classique qui ne regarde que IP/port/état de session, le NGFW pratique le *Deep Packet Inspection* (DPI) — il reconnaît l'**application réelle** transportée. Exemple parlant : un flux sur le port 443 autorisé peut être du HTTPS normal... ou un tunnel malveillant ; seul le NGFW fait la différence. Limite à mentionner si la question vient : pour inspecter du trafic chiffré, le NGFW doit le déchiffrer (interception TLS), ce qui pose des questions de performance et de vie privée — arbitrage classique en entreprise.

**2. IDS/IPS : le compromis détection/blocage**
L'IDS (passif, sur copie du trafic) ne casse jamais rien mais ne bloque rien ; l'IPS (actif, sur le chemin) bloque en temps réel mais un **faux positif** coupe du trafic légitime — sur un système critique (hôpital, industrie), un IPS mal réglé peut faire plus de dégâts qu'une attaque. C'est pourquoi beaucoup d'organisations démarrent en mode détection avant d'activer la prévention, règle par règle.

**3. Du VLAN au Zero Trust**
La segmentation ne se limite pas à la DMZ : les **VLAN** cloisonnent le réseau interne lui-même (bureautique / production / administration / invités). Poussée à l'extrême, la logique donne la **micro-segmentation** et le modèle **Zero Trust** : ne plus faire confiance par défaut à rien, même à l'intérieur — chaque flux doit être justifié. Teaser utile : l'identité comme nouveau périmètre sera au cœur du module C (sessions IAM et cloud).

---

### Glossaire

*   **Default Deny (Rejet par défaut)** — Politique de sécurité réseau qui consiste à bloquer toutes les communications par défaut, sauf celles explicitement autorisées.
*   **DMZ (Zone Démilitarisée)** — Sous-réseau physique ou logique isolé contenant les serveurs exposés à l'extérieur, servant de zone tampon avec le réseau interne.
*   **Firewall (Pare-feu)** — Équipement filtrant les flux réseau entrants et sortants sur la base d'une politique de sécurité (ACL).
*   **IDS (Intrusion Detection System)** — Équipement ou logiciel réseau analysant le trafic de manière passive pour détecter des comportements suspects ou des signatures d'attaques.
*   **IPS (Intrusion Prevention System)** — Équipement réseau actif capable d'analyser les paquets et de bloquer immédiatement les flux identifiés comme malveillants.
*   **Mouvement latéral** — Progression d'un attaquant de machine en machine à l'intérieur d'un réseau compromis, à la recherche de cibles de valeur.
*   **NGFW (Next-Generation Firewall)** — Pare-feu combinant filtrage à état, inspection applicative profonde (DPI) et modules de sécurité intégrés.
*   **VLAN (Virtual LAN)** — Réseau local virtuel permettant de cloisonner logiquement des groupes de machines sur une même infrastructure physique.
*   **WAF (Web Application Firewall)** — Pare-feu spécialisé placé devant les serveurs web pour bloquer les attaques applicatives (injections SQL, XSS).

---

### Concepts clés

!!! info "À retenir"
    Un réseau défendu n'est pas un réseau entouré d'un seul grand mur : c'est un réseau découpé en **zones étanches** avec des règles de passage explicites entre chacune. Le pare-feu applique la loi (*Default Deny*), l'IDS/IPS surveille les passages, et la segmentation garantit qu'une zone compromise ne condamne pas les autres.

### 1. Les Pare-feux (Firewalls) et leurs évolutions
Un pare-feu est un équipement de sécurité réseau chargé de filtrer les flux d'informations entrants et sortants selon des règles prédéfinies. Le principe fondamental d'un pare-feu est le **Default Deny** (Rejet par défaut) : tout trafic qui n'est pas explicitement autorisé par une règle est bloqué.

On distingue plusieurs générations de pare-feux :

*   **Filtrage sans état (*Stateless*)** : Analyse chaque paquet individuellement sans aucun historique. Il vérifie uniquement si les adresses IP et ports correspondent à ses règles.
    *   *Analogie* : Un portier de boîte de nuit qui vérifie si votre nom est sur la liste d'invités, mais oublie votre visage dès que vous franchissez le pas de la porte.
*   **Filtrage à état (*Stateful*)** : Garde en mémoire le contexte des connexions initiées (table des états). Si une machine interne initie une connexion vers l'extérieur, le pare-feu s'en souvient et laisse passer le trafic de retour associé, tout en bloquant les paquets entrants non sollicités.
    *   *Analogie* : Le même portier qui vous remet un bracelet tamponné lors de votre sortie temporaire pour vous laisser re-rentrer sans contrôle d'identité.
*   **Nouvelle Génération (NGFW — *Next-Generation Firewall*)** : Il combine le filtrage à état avec l'analyse applicative profonde (*Deep Packet Inspection* — DPI). Il est capable de reconnaître l'application réelle utilisée (ex. différencier un transfert de fichier Dropbox d'un simple surf web, même s'ils utilisent tous deux le port 443) et d'intégrer des modules antivirus et de filtrage d'URL.
    *   *Analogie* : Un agent des douanes qui contrôle votre passeport (IP), se souvient de votre trajet (état) et ouvre votre valise pour inspecter son contenu (DPI).
*   **Pare-feu Applicatif Web (WAF — *Web Application Firewall*)** : Outil spécialisé placé devant les serveurs web pour analyser et bloquer les attaques de niveau applicatif (comme les injections SQL vues en B03, ou le Cross-Site Scripting — XSS).

### 2. IDS et IPS : La surveillance du trafic
Malgré les pare-feux, des flux autorisés peuvent contenir du trafic malveillant (ex. un exploit caché dans une requête HTTPS autorisée). C'est là qu'interviennent les systèmes de détection et de prévention :

*   **IDS (*Intrusion Detection System*)** : Système passif qui écoute une copie du trafic réseau (port miroir). Il compare le trafic à des signatures d'attaques connues ou détecte des comportements anormaux. S'il détecte une menace, il génère une alerte pour l'analyste de sécurité, mais **ne bloque pas** le trafic.
*   **IPS (*Intrusion Prevention System*)** : Système actif placé directement au milieu du flux réseau (*inline*). S'il détecte un paquet malveillant, il le détruit immédiatement pour empêcher l'attaque d'atteindre sa cible.

**Le compromis à comprendre** : l'IDS ne casse jamais rien... mais n'arrête rien ; l'IPS bloque en temps réel... mais un faux positif coupe du trafic légitime. Et surtout : une alerte n'a de valeur que si quelqu'un la **traite** — l'affaire Target ci-dessous en est la démonstration cruelle.

### 3. La segmentation réseau et la DMZ
Pour éviter qu'un pirate ayant compromis une machine n'accède facilement à tout le réseau de l'entreprise (**mouvement latéral** — souvenez-vous du réseau « à plat » de TV5 Monde en B05), il est impératif de diviser le réseau en zones isolées logiquement :

*   **WAN (*Wide Area Network*)** : Le réseau public non sûr (Internet).
*   **LAN (*Local Area Network*)** : Le réseau local interne de l'entreprise, contenant les ordinateurs des salariés et les données confidentielles.
*   **DMZ (*Demilitarized Zone* — Zone Démilitarisée)** : Zone réseau intermédiaire isolée du LAN. C'est ici que l'on place les serveurs qui doivent être accessibles depuis Internet (serveur Web public, serveur de messagerie).
*   **Les VLAN** : à l'intérieur même du LAN, des réseaux virtuels cloisonnent les usages (bureautique / production / administration / invités) sur la même infrastructure physique.

> 💡 **Bon à savoir : La règle d'or de la DMZ**
> Les machines situées dans la DMZ sont par définition exposées et donc susceptibles d'être piratées. La règle d'or de sécurité consiste à **interdire toute connexion initiée depuis la DMZ vers le LAN**. Si un serveur web en DMZ est compromis, l'attaquant ne pourra pas s'en servir de rebond pour attaquer les ordinateurs internes de l'entreprise.

### Activité — La table de filtrage d'EcoLog (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Affichez le contexte : l'entreprise EcoLog possède un LAN employés (`192.168.10.0/24`), une DMZ avec un serveur web e-commerce (`192.168.20.5`), et l'accès Internet (WAN, `Any`). Vous allez construire ensemble sa table de filtrage, règle par règle, par sondages. Pour chaque besoin métier, les participants votent la règle correcte ; débriefez après chaque vote en remplissant la table à l'écran.

*   **📊 Sondage n°2 — Besoin 1 :** « Les clients d'Internet doivent pouvoir visiter le site e-commerce en HTTPS. » Quelle règle ?
    *   A) Source WAN (Any) → Destination DMZ (`192.168.20.5`), port TCP/443 : Allow ✅
    *   B) Source WAN (Any) → Destination LAN (`192.168.10.0/24`), port TCP/443 : Allow
    *   C) Source DMZ (`192.168.20.5`) → Destination WAN (Any), port TCP/443 : Allow
*   **📊 Sondage n°3 — Besoin 2 :** « Le serveur web doit pouvoir télécharger ses mises à jour logicielles sur Internet en HTTPS. » Quelle règle ?
    *   A) Source WAN (Any) → Destination DMZ, port TCP/443 : Allow
    *   B) Source DMZ (`192.168.20.5`) → Destination WAN (Any), port TCP/443 : Allow ✅
    *   C) Source DMZ (`192.168.20.5`) → Destination LAN, port TCP/443 : Allow
*   **📊 Sondage n°4 — Besoin 3 :** « L'administrateur, situé sur le LAN, doit gérer le serveur web en SSH. » Quelle règle ?
    *   A) Source LAN (`192.168.10.0/24`) → Destination DMZ (`192.168.20.5`), port TCP/22 : Allow ✅
    *   B) Source DMZ (`192.168.20.5`) → Destination LAN (`192.168.10.0/24`), port TCP/22 : Allow
    *   C) Source WAN (Any) → Destination DMZ (`192.168.20.5`), port TCP/22 : Allow

**Éléments de débriefing (pour le mentor) :**

- N°2 : la question clé d'une règle est **qui initie la connexion** — ici le client sur Internet, vers le serveur exposé. La réponse B ouvrirait le LAN au monde entier : erreur fatale.
- N°3 : même flux HTTPS, mais direction inversée — c'est le serveur qui initie. La réponse C violerait la règle d'or (DMZ → LAN interdit).
- N°4 : l'administration se fait DEPUIS la zone de confiance VERS la zone exposée, jamais l'inverse (B). La réponse C exposerait le SSH au monde entier — retour au scénario force brute de B05.
- **Conclure en affichant la table complète** (support, corrigé ci-dessous), avec la règle n°2 des employés (LAN → WAN, 80/443) ajoutée à l'oral et la ligne finale : `Any → Any : Deny` — le *Default Deny* qui transforme la liste de règles en politique de sécurité.

**Table de filtrage complète (corrigé de référence) :**

| N° Règle | Zone Source | IP Source | Zone Destination | IP Destination | Port / Service | Action | Explication |
|---|---|---|---|---|---|---|---|
| **1** | WAN | Any | DMZ | `192.168.20.5` | TCP/443 (HTTPS) | **Allow** | Autorise les clients externes à accéder au site e-commerce sécurisé. |
| **2** | LAN | `192.168.10.0/24` | WAN | Any | TCP/80, 443 (HTTP/S) | **Allow** | Permet aux employés internes de naviguer sur le web. |
| **3** | DMZ | `192.168.20.5` | WAN | Any | TCP/443 (HTTPS) | **Allow** | Permet au serveur web de chercher ses mises à jour en HTTPS. |
| **4** | LAN | `192.168.10.0/24` | DMZ | `192.168.20.5` | TCP/22 (SSH) | **Allow** | Permet à l'administrateur de gérer le serveur web depuis le réseau interne. |
| **5** | Any | Any | Any | Any | Any | **Deny** | Règle de blocage par défaut de tout trafic non mentionné ci-dessus. |

### 4. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **40 millions de numéros de cartes bancaires** et environ 70 millions de dossiers clients dérobés chez Target fin 2013 (chiffres communiqués par l'entreprise).
    - **Plus de 200 millions de dollars** de coûts cumulés pour Target, dont un accord de 18,5 M$ avec 47 États américains en 2017 — et le départ du PDG.
    - **Une dizaine de gigaoctets** de données exfiltrées d'un casino nord-américain... via le thermomètre connecté de l'aquarium du hall (cas rapporté par la société de cybersécurité Darktrace, 2018).

**Comment lire ces chiffres ?** (1) Le maillon faible peut être un fournisseur : votre pare-feu ne protège pas des accès que vous avez légitimement ouverts. (2) La facture d'une segmentation manquante se chiffre en centaines de millions. (3) Chaque objet connecté au réseau est une porte — si rien ne le sépare des données, la porte mène au coffre.

### 5. Deux affaires réelles : le chauffagiste de Target et le thermomètre du casino

#### Cas n°1 — Target (2013) : des caisses enregistreuses accessibles depuis le portail fournisseurs

Fin novembre 2013, en pleine période d'achats de Noël, des attaquants s'installent dans le réseau du géant américain de la distribution **Target**. Leur point d'entrée, révélé par l'enquête : les identifiants d'un petit **prestataire de chauffage et climatisation**, hameçonné quelques semaines plus tôt, qui disposait d'un accès au portail fournisseurs de Target (facturation, gestion de projets). De ce portail périphérique, les attaquants ont progressé de proche en proche — le fameux **mouvement latéral** — jusqu'au réseau des **caisses enregistreuses** de près de 1 800 magasins, où un malware a collecté en mémoire les données de cartes au moment du paiement : **40 millions de cartes**, plus environ 70 millions de dossiers clients.

Détail accablant : les outils de détection de Target ont bien **généré des alertes** pendant l'attaque... mais elles n'ont pas été traitées à temps. Bilan : plus de 200 M$ de coûts cumulés, un accord à 18,5 M$ avec 47 États, et la démission du PDG — l'une des premières fois qu'une cyberattaque coûte son poste au dirigeant d'un grand groupe.

**Ce que ce cas illustre :** un accès fournisseur légitime est un point d'entrée comme un autre (le pare-feu périmétrique n'y peut rien — il l'autorise) ; sans segmentation, un portail de facturation peut mener aux caisses ; et une alerte IDS sans humain pour la traiter ne vaut rien. Avec une vraie segmentation — le portail fournisseurs dans une zone étanche, les caisses dans une autre, *Default Deny* entre les deux — l'attaque s'arrêtait au portail.

#### Cas n°2 — Le casino et le thermomètre (2017) : l'objet connecté comme porte d'entrée

Rapporté par la société de cybersécurité Darktrace : un casino nord-américain se fait dérober sa base de données de clients VIP. Le point d'entrée ? Le **thermomètre connecté de l'aquarium** du hall d'accueil — un objet IoT anodin, connecté au même réseau que les systèmes métier. Les attaquants l'ont compromis, s'en sont servis de tremplin vers la base de données, puis ont exfiltré environ **10 Go** de données... en les faisant transiter par le thermomètre.

**Ce que ce cas illustre :** chaque objet connecté est une machine comme une autre — souvent moins bien sécurisée ; la question n'est pas « qui penserait à pirater un thermomètre ? » mais « une fois le thermomètre compromis, que peut-il joindre ? ». Un VLAN dédié aux objets connectés, étanche au réseau métier, aurait transformé l'anecdote en non-événement. Pensez-y en regardant la liste des appareils de votre Wi-Fi domestique (votre inventaire de la semaine !).

!!! tip "📊 Sondage Livestorm n°5 — Et chez vous ? (sondage d'opinion, pas de bonne réponse)"
    **Question :** Le réseau que vous connaissez le mieux (professionnel ou domestique) est-il segmenté ?

    - A) Oui : plusieurs zones étanches (invités, production, administration...)
    - B) Partiellement : un réseau invité ou un Wi-Fi séparé, sans plus
    - C) Tout est à plat / Je ne sais pas

    **Débrief mentor :** Sondage d'opinion — et un diagnostic utile. B est déjà un vrai progrès : le Wi-Fi invité est la segmentation la plus accessible qui soit (la box de la plupart des foyers le propose). Pour les réponses C : après TV5 Monde (B05) et Target (ce soir), vous savez pourquoi « à plat » est le mot qui fait peur. L'atelier de synthèse B08 vous fera concevoir votre propre schéma segmenté — ce sondage est votre point de départ.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Vous êtes d'astreinte, il est 2h du matin. L'IDS remonte une alerte : un poste du LAN bureautique établit des connexions répétées vers le serveur de paie, sur un port inhabituel. Le poste appartient à un salarié en congés. **Tapez A, B ou C dans le chat :**

    - A) Classer l'alerte : personne ne travaille à 2h du matin, c'est sûrement une mise à jour.
    - B) Vérifier immédiatement, et en cas de doute isoler le poste du réseau (le confiner), puis investiguer au matin avec l'équipe. ✅
    - C) Éteindre tout le réseau de l'entreprise par précaution.

    **Débrief mentor :** B — l'alerte a toutes les caractéristiques d'un mouvement latéral (poste inactif, cible sensible, port inhabituel, heure creuse) : on **confine d'abord** (isoler UN poste coûte peu), on investigue ensuite. A est exactement l'erreur de Target : une alerte générée mais non traitée. C est disproportionné — couper toute l'entreprise pour un poste suspect, c'est réaliser le déni de service à la place de l'attaquant. La réponse graduée est au programme de la session B19 (réponse aux incidents).

---

### Questions de réflexion
1. Pourquoi est-il déconseillé de configurer une règle permettant à un serveur web situé en DMZ d'initier une connexion vers la base de données de production située dans le LAN interne ? Comment contourner ce besoin de manière sécurisée ?
2. Un pare-feu de nouvelle génération (NGFW) détecte un flux HTTPS sur le port 443 contenant un malware connu. Pourquoi un pare-feu traditionnel de type "stateful" n'aurait pas pu bloquer cette menace ?
3. Dans l'affaire Target, les alertes de détection ont été générées mais pas traitées. Qu'est-ce que cela nous apprend sur la différence entre « avoir des outils de sécurité » et « avoir une sécurité opérationnelle » ?

**Corrigé / Éléments de réponse :**

1. La DMZ est plus exposée ; si le serveur web est compromis, il pourrait attaquer le LAN. Le LAN (BDD) doit initier la connexion vers la DMZ, ou bien on place un serveur intermédiaire ultra-filtré — jamais de flux initié DMZ → LAN.
2. Le pare-feu stateful ne regarde que les ports et adresses IP (ici 443 est autorisé). Le NGFW inspecte le contenu (DPI) pour y détecter le malware, même sur un port autorisé.
3. Un outil sans processus ni humain pour traiter ses alertes ne produit que du bruit. La détection n'a de valeur que si elle déclenche une action dans un délai maîtrisé — c'est tout l'objet du SOC (session B16) : des outils + des personnes + des procédures.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez les défenses et la segmentation d'un réseau comme la sécurité d'un **aéroport sécurisé** :
    - **La DMZ (Zone Démilitarisée)** est la zone publique d'accueil (enregistrement, boutiques). Tout le monde peut y entrer depuis la rue (Internet), mais des barrières de sécurité et des portiques de contrôle empêchent les visiteurs de passer plus loin sans vérification.
    - **Le Pare-feu (Firewall)** est le poste de contrôle des frontières. Il examine les billets (paquets de données) et vérifie si le passager est autorisé à passer.
    - **L'IDS / IPS** correspond aux agents de sécurité en patrouille. L'IDS surveille et signale un comportement louche. L'IPS intervient directement pour menotter et expulser l'intrus (bloquer la connexion).
    - **La segmentation par VLAN** correspond aux portes réservées aux employés avec lecteurs de badges : un passager de la zone publique ne peut pas entrer dans la zone de tri des bagages.

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

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après le mini-scénario.

*   **📊 Sondage n°6 :** Qu'est-ce qui distingue un pare-feu à état (*stateful*) d'un pare-feu sans état (*stateless*) ?
    *   A) Il garde en mémoire le contexte des connexions initiées et laisse passer le trafic de retour associé ✅
    *   B) Il est plus rapide car il n'analyse qu'un paquet sur deux
    *   C) Il chiffre automatiquement les paquets qu'il laisse passer
*   **📊 Sondage n°7 :** Quelle est la différence fondamentale entre un IDS et un IPS ?
    *   A) L'IDS protège le web, l'IPS protège la messagerie
    *   B) L'IDS détecte et alerte (passif) ; l'IPS bloque en temps réel (actif, sur le chemin du trafic) ✅
    *   C) L'IDS est gratuit, l'IPS est payant
*   **📊 Sondage n°8 :** Qu'apporte un pare-feu de nouvelle génération (NGFW) par rapport à un pare-feu à état classique ?
    *   A) Il supprime le besoin d'antivirus sur les postes
    *   B) Il rend la segmentation réseau inutile
    *   C) L'inspection profonde du contenu (DPI) : il reconnaît l'application réelle, même sur un port autorisé ✅

**Éléments de débriefing (pour le mentor) :**

- N°6 : l'analogie du bracelet tamponné — le portier se souvient de qui est sorti. C'est ce qui permet de bloquer tout paquet entrant non sollicité.
- N°7 : le compromis à retenir : le passif n'arrête rien, l'actif peut se tromper (faux positif = trafic légitime coupé). Et une alerte sans humain pour la traiter ne vaut rien — Target l'a payé 200 M$.
- N°8 : le port 443 autorisé peut transporter n'importe quoi — seule l'inspection du contenu fait la différence. Ni A ni B : les défenses s'empilent, elles ne se remplacent pas (défense en profondeur).

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Network Security - Part 2"* (durée estimée : 1h30).
*   **Action pratique** : Dessiner un schéma réseau simple à l'aide d'un outil en ligne gratuit (comme draw.io) représentant une architecture avec un pare-feu, un switch, une DMZ et un LAN — il servira de brouillon pour l'atelier B08.
*   [ANSSI — Passerelles d'accès à Internet](https://cyber.gouv.fr)
*   [OWASP — Sécurité applicative](https://owasp.org/)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Compréhension du cloisonnement réseau.
*   **📊 Sondage Livestorm n°9 :** Un serveur web situé en DMZ est compromis par un pirate. Qu'est-ce qui l'empêche d'accéder au serveur de comptabilité interne ?
    *   A) L'antivirus du serveur web.
    *   B) La règle de pare-feu interdisant tout flux initié de la DMZ vers le réseau interne ✅
    *   C) Le mot de passe du serveur web.
*   **Guide d'animation (pour le mentor) :** Rappelez que même si un serveur exposé est compromis, la segmentation réseau limite strictement les mouvements latéraux du pirate : la DMZ est conçue pour être « perdable » sans que le cœur du réseau tombe. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Default Deny (Rejet par défaut)** | Tout bloquer par défaut, n'autoriser que l'explicitement permis — la ligne finale de toute table de filtrage. |
| **DMZ (Zone Démilitarisée)** | Zone tampon isolée pour les serveurs exposés — règle d'or : aucun flux initié DMZ → LAN. |
| **Firewall (Pare-feu)** | Filtre les flux selon une politique de sécurité ; générations : stateless → stateful → NGFW (DPI). |
| **IDS (Intrusion Detection System)** | Surveillance passive du trafic : détecte et alerte, ne bloque pas. |
| **IPS (Intrusion Prevention System)** | Surveillance active sur le chemin du trafic : bloque immédiatement les flux malveillants. |
| **Mouvement latéral** | Progression de l'attaquant de machine en machine à l'intérieur du réseau — ce que la segmentation confine. |
| **NGFW** | Pare-feu de nouvelle génération : filtrage à état + inspection applicative profonde (DPI). |
| **VLAN** | Cloisonnement logique du réseau interne (bureautique / production / IoT / invités). |
| **WAF** | Pare-feu applicatif dédié aux serveurs web (anti-injections SQL, XSS). |

**La règle d'or de la session :** découpez votre réseau en zones étanches et n'autorisez que les flux justifiés (*Default Deny*) — pour qu'un fournisseur hameçonné ou un thermomètre compromis reste une anecdote, et non l'antichambre de vos caisses enregistreuses.
