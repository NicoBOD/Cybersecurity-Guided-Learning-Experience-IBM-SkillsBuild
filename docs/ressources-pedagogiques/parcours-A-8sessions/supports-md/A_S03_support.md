# Support de cours — Session 03 : Sécurité des systèmes & réseaux
Parcours : A 8 sessions  |  Module : Réseau & Infrastructure  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Le filtrage réseau : Le pare-feu (*Firewall*)
    - Le tunnel sécurisé : Le VPN (*Virtual Private Network*)
    - HTTPS vs HTTP : Protéger la navigation web
    - La segmentation réseau et la DMZ
    - Le réseau en chiffres et deux cas réels : Target (2013) et Mirai/Dyn (2016)
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

Le réseau est le système nerveux de toute infrastructure informatique. Sécuriser les flux de données qui y transitent et contrôler les accès extérieurs sont des exigences opérationnelles incontournables. Ce support de cours examine les technologies clés de la sécurité réseau. Vous découvrirez le fonctionnement d'un pare-feu (*firewall*), barrière de contrôle des flux entrants et sortants. Nous aborderons les réseaux privés virtuels (*VPN*), indispensables pour le travail à distance sécurisé, et analyserons la différence essentielle entre les protocoles HTTP (en clair) et HTTPS (chiffré). Enfin, nous étudierons la segmentation réseau, une stratégie défensive qui consiste à diviser le réseau d'une entreprise en zones isolées pour empêcher un attaquant de s'y déplacer librement en cas d'intrusion — une leçon que le distributeur américain Target a payée plus de 200 millions de dollars, comme nous le verrons.

### Objectifs de la session

À l'issue de cette session, vous serez capable de :

- **Expliquer** le rôle de filtrage d'un pare-feu et la logique de ses règles (Default Deny, ordre d'application).
- **Identifier** les cas d'usage d'un VPN pour protéger les communications sur un réseau non maîtrisé (Wi-Fi public, télétravail).
- **Distinguer** le trafic chiffré (HTTPS/TLS, SSH) du trafic en clair (HTTP, Telnet) et expliquer le risque d'interception (*sniffing*).
- **Proposer** un plan de segmentation réseau simple (LAN, Wi-Fi invités, DMZ) pour confiner une intrusion.

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** Vous branchez sur Internet un serveur tout neuf, sans aucune protection. Combien de temps avant les premières tentatives de connexion malveillantes ?

    - A) Quelques minutes ✅
    - B) Quelques jours
    - C) Quelques semaines
    - D) Ça n'arrive que si l'on est ciblé

    **Débrief mentor :** Quelques minutes — parfois quelques secondes. Les études menées avec des « pots de miel » (*honeypots*, machines-appâts surveillées) montrent qu'Internet est balayé en permanence par des scanners automatisés. Rappel de la session A1 : les attaquants ne vous *choisissent* pas, ils testent tout ce qui est branché. La réponse D est le mythe à enterrer aujourd'hui : l'exposition suffit, pas besoin d'être « intéressant ».

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Modèle OSI et Sécurité en couches**
Prenez le temps d'expliquer les couches clés du modèle OSI (Liaison, Réseau, Transport, Application). Expliquez pourquoi un pare-feu traditionnel (Couche 3/4) ne peut pas bloquer une attaque d'injection SQL (Couche 7), justifiant ainsi le besoin d'un WAF (Web Application Firewall).

**2. Segmentation réseau et DMZ**
Illustrez à l'écran l'architecture d'un réseau sécurisé :
- La **DMZ** (Zone Démilitarisée) qui héberge les serveurs publics (Serveur Web).
- Le **LAN** interne qui héberge la base de données.
Expliquez la règle d'or : la DMZ peut être interrogée par Internet, mais ne doit jamais initier de connexion non sollicitée vers le LAN interne.

**3. Vulnérabilités des protocoles historiques**
Discutez des failles inhérentes aux vieux protocoles (Telnet, FTP, HTTP) qui font transiter les mots de passe en clair sur le réseau. Distinguez bien les deux niveaux d'attaque : l'**écoute passive** (*sniffing* — l'attaquant lit le trafic qui passe) et l'**interposition active** (*Man-in-the-Middle* — l'attaquant se place entre les deux interlocuteurs et peut modifier les échanges). Expliquez la transition obligatoire vers SSH, SFTP et HTTPS. Point de rigueur terminologique : on dit couramment « SSL », mais SSL est le prédécesseur **déprécié** de TLS (SSLv3 est cassé depuis 2014) — le protocole moderne s'appelle TLS.

**4. L'angle mort de 2024-2025 : les équipements de bordure**
L'ANSSI souligne dans son Panorama de la cybermenace 2024 que l'exploitation d'équipements exposés en bordure de réseau (passerelles VPN, pare-feux eux-mêmes) figure parmi les tout premiers vecteurs d'intrusion observés. Ironie pédagogique à exploiter : l'équipement de sécurité mal maintenu devient la porte d'entrée. La leçon : un pare-feu ou un VPN, ça se met à jour comme n'importe quel logiciel.

---

### Glossaire

*   **Déplacement latéral (Lateral Movement)** — Progression d'un attaquant d'une machine compromise vers les autres machines du même réseau, à la recherche des actifs de valeur.
*   **DMZ (Zone Démilitarisée / Demilitarized Zone)** — Sous-réseau isolé du réseau interne et d'Internet, hébergeant les serveurs devant être accessibles depuis l'extérieur (ex. serveur web public), afin qu'une compromission de ces serveurs ne donne pas accès aux postes internes.
*   **HTTPS (HyperText Transfer Protocol Secure)** — Version sécurisée du protocole HTTP utilisée pour le web, chiffrant les échanges entre le navigateur de l'utilisateur et le serveur web pour empêcher l'interception.
*   **Pare-feu (Firewall)** — Équipement ou logiciel réseau analysant et filtrant les paquets de données entrants et sortants selon des règles de sécurité prédéfinies.
*   **Port réseau** — Canal logique numéroté (0-65535) par lequel un service communique (ex. 443 pour HTTPS, 22 pour SSH) ; chaque port ouvert est une porte à surveiller.
*   **Segmentation réseau** — Technique consistant à partitionner un réseau informatique en plusieurs sous-réseaux (VLANs, DMZ) distincts pour limiter la propagation des menaces.
*   **Sniffing (Écoute réseau)** — Interception passive du trafic circulant sur un réseau ; redoutable sur les protocoles en clair (HTTP, Telnet, FTP) où identifiants et données sont lisibles directement.
*   **TLS (Transport Layer Security)** — Protocole de chiffrement des échanges sur Internet, socle de HTTPS. Successeur de SSL, aujourd'hui déprécié (on continue pourtant de dire « certificat SSL » par habitude).
*   **VLAN (Virtual Local Area Network)** — Technologie permettant de segmenter un réseau physique unique en plusieurs réseaux locaux logiques indépendants.
*   **VPN (Virtual Private Network)** — Technologie créant un tunnel chiffré et sécurisé sur un réseau public pour acheminer de manière confidentielle les données d'un poste de travail vers le réseau de l'entreprise.

---

### 1. Le filtrage réseau : Le pare-feu (*Firewall*)

!!! info "À retenir"
    Le principe fondateur de tout pare-feu bien configuré : **tout ce qui n'est pas explicitement autorisé est interdit** (*Default Deny*). On n'énumère pas le mal, on autorise le nécessaire.

Le pare-feu agit comme un douanier à la frontière du réseau de l'entreprise. Il inspecte chaque paquet de données qui se présente et prend une décision : **Autoriser** (*Accept/Allow*) ou **Bloquer** (*Drop/Deny*).

Le filtrage traditionnel s'appuie sur des règles basées sur trois critères principaux :

* **L'adresse IP source et destination** : Qui envoie le paquet et à qui est-il adressé ?
* **Le protocole** : Quel protocole est utilisé (TCP, UDP, ICMP) ?
* **Le port de communication** : Quel canal logique est ciblé (ex. le port 80 pour HTTP, 443 pour HTTPS, 22 pour SSH) ?

*Exemple de règle simple* : Autoriser tous les ordinateurs du réseau interne à envoyer du trafic vers Internet uniquement sur le port 443 (HTTPS), et bloquer toutes les connexions entrantes provenant d'Internet initiées vers le réseau interne.

Les règles s'appliquent **dans l'ordre, de haut en bas** : la première règle qui correspond au paquet l'emporte, et la dernière règle d'une table bien conçue est toujours « tout bloquer ». C'est exactement le fonctionnement d'un portier de soirée avec sa liste : il lit de haut en bas, et si vous n'êtes sur aucune ligne, vous restez dehors.

### 2. Le tunnel sécurisé : Le VPN (*Virtual Private Network*)

Lorsque vous naviguez sur Internet depuis un réseau Wi-Fi public (ex. dans un café ou une gare), n'importe quel attaquant situé sur le même réseau peut intercepter vos flux non chiffrés. De même, un employé travaillant depuis chez lui a besoin d'accéder aux fichiers internes de l'entreprise sans exposer ces ressources directement sur Internet.

Le VPN résout ce problème en créant un **tunnel chiffré** entre l'ordinateur de l'utilisateur et la passerelle VPN de l'entreprise.

* Les données quittent l'ordinateur sous forme chiffrée.
* Elles transitent par Internet de manière totalement illisible pour les intermédiaires (fournisseurs d'accès, pirates).
* Elles arrivent à la passerelle VPN de l'entreprise qui les déchiffre et les transmet au réseau interne comme si l'utilisateur était physiquement assis à son bureau dans l'entreprise.

Deux limites à connaître pour éviter les faux sentiments de sécurité : (1) le VPN protège le **transport** des données, pas le contenu — si votre machine télécharge un malware, le tunnel le livrera chiffré, mais le livrera quand même ; (2) la passerelle VPN elle-même est un équipement exposé sur Internet, qui doit être maintenu à jour (voir l'encadré « chiffres » plus bas : c'est devenu l'un des points d'entrée favoris des attaquants).

### 3. HTTPS vs HTTP : Protéger la navigation web

* Le protocole **HTTP** transmet toutes les données en clair. Si vous saisissez un mot de passe ou un numéro de carte bancaire sur un site HTTP, un pirate connecté sur le même réseau peut le lire sans effort (écoute passive, ou *sniffing*).
* Le protocole **HTTPS** utilise le protocole TLS pour chiffrer la communication. Même interceptées, les données apparaissent comme une suite incohérente de caractères aléatoires. De plus, HTTPS fournit un certificat numérique garantissant l'identité du site visité (pour éviter que l'utilisateur ne se connecte à un faux site se faisant passer pour le vrai — l'interposition active dite *Man-in-the-Middle*).

!!! tip "📊 Sondage Livestorm n°2 — Le Wi-Fi de l'hôtel"
    **Question :** Vous êtes connecté au Wi-Fi gratuit d'un hôtel et vous consultez votre banque sur un site en HTTPS. Le gérant de l'hôtel (qui administre le réseau) peut-il lire votre mot de passe ?

    - A) Oui, il voit tout ce qui passe sur son réseau
    - B) Non : il peut voir QUE vous parlez à votre banque, mais pas CE que vous échangez ✅
    - C) Oui, mais seulement s'il a des compétences d'administrateur

    **Débrief mentor :** Réponse B — et la nuance est importante. Le chiffrement TLS protège le **contenu** (identifiants, soldes, opérations), mais les **métadonnées** (quel site vous visitez, quand, combien de données) restent observables. C'est exactement ce que complète un VPN : il masque aussi la destination en enveloppant tout le trafic dans son tunnel. Attention enfin au piège inverse : le cadenas HTTPS garantit que la connexion est chiffrée, **pas** que le site est honnête — un site de phishing peut avoir son cadenas (certificat gratuit en quelques minutes).

### 4. La segmentation réseau et la DMZ

Dans un réseau non segmenté (appelé "réseau plat"), si le poste d'un commercial est infecté par un malware, ce dernier peut se propager immédiatement aux serveurs de production, aux bases de données RH et à la comptabilité. C'est ce qu'on appelle le **déplacement latéral**.

Pour empêcher cela, on segmente le réseau en zones logiques étanches séparées par un pare-feu :

1. **La zone LAN interne** : Les ordinateurs des employés de bureau.
2. **La zone Wi-Fi invités** : Destinée aux visiteurs (sans accès au LAN interne).
3. **La DMZ (Zone Démilitarisée)** : Contient les serveurs ouverts sur l'extérieur (site internet, serveur e-mail). Si le serveur web de la DMZ est piraté, les règles du pare-feu lui interdisent d'initier des connexions vers le LAN interne, stoppant net la progression de l'attaquant.

La segmentation est la déclinaison réseau de la **défense en profondeur** vue en session A1 : on accepte l'idée qu'une zone puisse tomber, et on s'organise pour que sa chute n'entraîne pas les autres. Comme les portes coupe-feu d'un bâtiment : elles n'empêchent pas l'incendie de démarrer, elles l'empêchent de tout dévorer.

---

### Focus pratique
Voici comment se structure une table de filtrage (règles ordonnées de haut en bas ; la première règle correspondante s'applique) :

| Priorité | Source | Destination | Protocole / Port | Action | Commentaire |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **1** | Interne (LAN) | Externe (Internet) | TCP / 443 (HTTPS) | **AUTORISER** | Permet la navigation web sécurisée des employés. |
| **2** | Externe (Internet) | Serveur Web (DMZ) | TCP / 443 (HTTPS) | **AUTORISER** | Permet aux internautes d'accéder au site web public. |
| **3** | Serveur Web (DMZ) | Interne (LAN) | Tout | **BLOQUER** | Empêche le serveur web compromis d'attaquer les postes internes. |
| **4** | Tout | Tout | Tout | **BLOQUER** | Règle par défaut (Bloquer tout ce qui n'est pas explicitement autorisé). |

### Activité — L'Architecte Réseau (Sondages Livestorm n°3 à 5)

**Consignes pour le mentor :** Projetez le schéma du réseau « plat » d'une PME fictive (tous les équipements sur le même réseau : postes de bureau, serveur web public, base de données comptable, borne Wi-Fi clients). Annoncez : « ce réseau est une catastrophe annoncée — vous êtes l'architecte chargé de le sauver, décision par décision. » Lancez les trois sondages successivement, avec débrief après chacun.

*   **📊 Sondage n°3 :** Un client de passage connecte son téléphone (infecté) à la borne Wi-Fi. Sur ce réseau plat, quel est le risque principal ?
    *   A) Le débit Internet de l'entreprise sera ralenti
    *   B) Le malware peut se déplacer latéralement jusqu'aux serveurs internes ✅
    *   C) Aucun : un téléphone ne peut pas infecter un serveur
    *   D) Le client peut être remboursé de son forfait
*   **📊 Sondage n°4 :** Où placer le serveur web public dans la nouvelle architecture ?
    *   A) Sur le réseau local interne (LAN), avec les postes de travail
    *   B) Dans une zone démilitarisée (DMZ) séparée du réseau interne par un pare-feu ✅
    *   C) Directement sur Internet, sans aucune protection
*   **📊 Sondage n°5 :** Quelle règle appliquer à la zone Wi-Fi invités ?
    *   A) Accès à Internet uniquement, aucun accès au réseau interne ✅
    *   B) Accès à Internet et aux imprimantes internes (c'est pratique)
    *   C) Même réseau que les employés, mais avec un mot de passe différent

**Éléments de débriefing (pour le mentor) :**

- N°3 : introduire le terme **déplacement latéral** — le réseau plat est une maison sans portes intérieures. Annoncer : « retenez ce mot, le cas réel de tout à l'heure en est l'illustration à 200 millions de dollars. »
- N°4 : la DMZ est un sas — accessible de l'extérieur, mais sans porte vers l'intérieur. Rejouer la règle 3 de la table de filtrage.
- N°5 : « c'est pratique » est l'ennemi juré de la segmentation ; chaque passerelle de confort est un pont pour l'attaquant. Le Wi-Fi invités est un réseau d'inconnus : on le traite comme Internet.
- Conclure en affichant l'architecture cible (LAN / Wi-Fi invités / DMZ, pare-feu central) : « en trois votes, vous venez de faire le travail d'un architecte sécurité. »

### 5. Le réseau en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **Quelques minutes** : le délai typique avant qu'une machine exposée sans protection sur Internet ne reçoive ses premières tentatives de connexion malveillantes (études par *honeypots* ; le « bruit de fond » d'Internet est un balayage permanent).
    - **L'exploitation d'équipements exposés en bordure de réseau** (passerelles VPN, pare-feux) figure parmi les premiers vecteurs d'intrusion observés en France (ANSSI, *Panorama de la cybermenace 2024*) — l'équipement de sécurité non maintenu devient lui-même la porte d'entrée.
    - **~1 térabit par seconde** : l'ordre de grandeur des attaques DDoS records lancées dès 2016 par le botnet Mirai, constitué de centaines de milliers d'objets connectés compromis (caméras, box) utilisant leurs mots de passe d'usine.
    - **Plus de 200 millions de dollars** : les coûts cumulés de la violation Target (2013) pour l'entreprise — enquêtes, dédommagements, procès — pour une intrusion partie d'un simple prestataire de climatisation (cas détaillé ci-dessous).

**Comment lire ces chiffres ?** (1) L'exposition est immédiate : brancher, c'est être attaqué — d'où le Default Deny. (2) Les protections elles-mêmes doivent être protégées (mises à jour des VPN et pare-feux). (3) Le maillon faible n'est pas toujours chez vous : prestataires et objets connectés font partie de VOTRE surface d'attaque.

### 6. Deux cas réels : quand l'architecture fait la différence

#### Cas n°1 — Target (2013) : le climatiseur qui a coûté 200 millions de dollars

Fin 2013, en pleine période des fêtes, le géant américain de la distribution Target subit l'un des vols de données bancaires les plus célèbres de l'histoire : environ **40 millions de numéros de cartes bancaires** dérobés (et les données personnelles d'environ 70 millions de clients). Le point d'entrée ? Ni un serveur de Target, ni un employé de Target : les identifiants volés d'un **prestataire de chauffage-climatisation** (HVAC), qui disposait d'un accès au réseau de l'enseigne pour la télémaintenance. Une fois entrés par cette porte de service, les attaquants ont pu se **déplacer latéralement** jusqu'aux systèmes d'encaissement des magasins — car le réseau était insuffisamment segmenté — et y installer un malware qui aspirait les cartes à chaque paiement. Coûts cumulés pour Target : **plus de 200 millions de dollars**, sans compter le départ du PDG et du DSI.

**Ce que ce cas illustre :** exactement les trois votes de votre activité « Architecte réseau ». Un accès tiers mal cloisonné (le Wi-Fi invités version industrielle), un réseau trop plat (déplacement latéral), et l'absence de sas entre les zones de sensibilité différentes. Avec une segmentation stricte, l'intrusion chez le prestataire serait restée... chez le prestataire.

#### Cas n°2 — Mirai et l'attaque Dyn (2016) : quand les caméras éteignent Internet

En septembre-octobre 2016, le botnet **Mirai** — un ver qui se propageait en testant simplement les mots de passe d'usine (admin/admin, root/12345) sur les objets connectés exposés à Internet — enrôle des centaines de milliers de caméras de surveillance, enregistreurs vidéo et routeurs domestiques. Résultat : des attaques DDoS d'une puissance inédite (~1 Tbit/s), d'abord contre l'hébergeur français **OVH**, puis contre **Dyn**, un fournisseur DNS majeur. Conséquence de cette seconde attaque : Twitter, Netflix, Spotify, Reddit et des dizaines de grands services deviennent inaccessibles pendant des heures pour une grande partie des États-Unis. Ce jour-là, des caméras de vidéosurveillance à 40 € ont mis à genoux une partie du web mondial.

**Ce que ce cas illustre :** le brise-glace de ce début de session (tout équipement exposé est scanné en quelques minutes — Mirai ne faisait que ça, en continu) ; l'importance des mots de passe par défaut (revoir A1/A2) ; et la notion de **Disponibilité** de la triade C-I-D, attaquée ici à l'échelle d'Internet. Rappel : le DDoS est aussi l'arme favorite des hacktivistes vus en A1.

!!! question "💬 Question chat — Transition"
    Chez Target, QUI aurait dû empêcher le déplacement latéral entre l'accès du prestataire et les caisses ? **Tapez votre réponse dans le chat** (une règle ? un équipement ? une personne ?). Réponse mentor : la règle 3 de notre table de filtrage — un pare-feu interne interdisant à la zone « prestataires » d'initier des connexions vers la zone « paiement ». La technologie existait ; c'est l'architecture qui a manqué.

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez que le réseau informatique de votre entreprise est un **grand immeuble de bureaux** :
    - **Le Pare-feu (Firewall)** est le guichet de réception à l'entrée. Il contrôle l'identité de chaque visiteur et refuse systématiquement ceux qui ne sont pas sur la liste d'invités.
    - **La DMZ (Zone Démilitarisée)** est la salle d'attente à l'accueil. Les visiteurs externes peuvent s'y installer, mais des portes blindées et verrouillées les empêchent d'accéder aux bureaux internes.
    - **La segmentation réseau (VLAN)** correspond aux badges d'accès par étage : la comptabilité ne peut pas monter à l'étage de la R&D sans badge spécifique.
    - **Le VPN** est un tunnel souterrain sécurisé et invisible menant directement de votre domicile à votre bureau, empêchant quiconque dans la rue de voir vos déplacements.

**Exemple d'application professionnelle :**
Une PME de logistique héberge son site web public sur un serveur en DMZ. Suite à une faille sur le site, le serveur est compromis. Grâce au pare-feu interne et à la segmentation réseau, le pirate est confiné dans la DMZ et ne peut pas rebondir vers le réseau interne où sont stockés les fichiers clients et les bases de données comptables. C'est l'anti-Target : même intrusion initiale, dégâts confinés — la différence entre un incident technique et une crise d'entreprise.

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

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après les études de cas.

*   **📊 Sondage n°6 :** Pour appliquer le principe du moindre privilège sur un pare-feu d'entreprise, quelle règle de base devez-vous configurer ?
    *   A) Tout autoriser par défaut, et bloquer uniquement les adresses IP suspectes signalées
    *   B) Tout interdire par défaut, et autoriser uniquement les flux et ports explicitement nécessaires au métier ✅
    *   C) Autoriser tout le trafic provenant des employés sans restriction
*   **📊 Sondage n°7 :** Le VPN de votre entreprise empêche-t-il votre ordinateur de télécharger un virus ?
    *   A) Oui, le tunnel chiffré bloque les malwares
    *   B) Non : il protège le transport des données, pas leur contenu ✅
    *   C) Oui, mais seulement les virus connus
*   **📊 Sondage n°8 :** Vrai ou faux : un site web affichant le cadenas HTTPS est forcément un site de confiance.
    *   A) Vrai : le cadenas certifie le site
    *   B) Faux : le cadenas garantit le chiffrement de la connexion, pas l'honnêteté du site ✅

**Éléments de débriefing (pour le mentor) :**

- N°6 : Default Deny, le fondement — on autorise le nécessaire, on n'énumère jamais le mal (liste infinie).
- N°7 : le tunnel livre ce qu'on y met, chiffré... y compris un malware. Le VPN complète l'antivirus, il ne le remplace pas.
- N°8 : un site de phishing obtient un certificat gratuit en quelques minutes ; le cadenas dit « conversation privée », pas « interlocuteur honnête » — reboucler avec la Chasse au phishing d'A2.

### Questions de réflexion

1. Chez Target, l'alerte du logiciel de détection aurait été émise mais pas traitée. À quoi sert la meilleure architecture si personne ne regarde les alarmes ? (Pont vers les sessions A6/A7 : SOC et réponse aux incidents.)
2. Votre entreprise autorise le télétravail depuis les ordinateurs personnels via VPN. Qu'est-ce que le tunnel protège... et qu'est-ce qu'il ne protège pas dans ce scénario ?
3. Mirai a exploité des mots de passe d'usine jamais changés. Qui est responsable : le fabricant qui les configure, le client qui ne les change pas, ou le régulateur qui n'impose rien ? Argumentez.
4. « Notre réseau est sûr : nous avons un excellent pare-feu en frontière. » Citez deux scénarios vus aujourd'hui où cette affirmation ne suffit pas.

## 3. Ressources complémentaires

* **IBM SkillsBuild** : Cours "Network Security Fundamentals".
* **[ANSSI — Guide d'hygiène informatique](https://cyber.gouv.fr/publications/guide-dhygiene-informatique)** : les 42 mesures essentielles, dont plusieurs concernent directement la segmentation et le filtrage.
* **ANSSI** : Recommandations sur la sécurisation des architectures réseaux (publications « architecture » du site cyber.gouv.fr).
* **[OWASP — Top 10](https://owasp.org/www-project-top-ten/)** : le classement de référence des risques applicatifs web (complément couche 7 du pare-feu).
* **Wireshark (outil tiers)** : Outil d'analyse de protocoles réseaux (pour observer la structure des paquets).

## 4. Exercice bonus (Quiz Confinement DMZ - Livestorm)

*   **Objectif :** Compréhension du cloisonnement réseau.
*   **📊 Sondage Livestorm n°9 :** Un serveur web situé en DMZ est compromis par un pirate. Qu'est-ce qui l'empêche d'accéder au serveur de comptabilité interne ?
    *   A) L'antivirus du serveur web.
    *   B) La règle de pare-feu interdisant tout flux initié de la DMZ vers le réseau interne ✅
    *   C) Le mot de passe du serveur web.
*   **Guide d'animation (pour le mentor) :** Rappelez que même si un serveur exposé est compromis, la segmentation réseau limite strictement les mouvements latéraux du pirate. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Déplacement latéral** | Progression d'un attaquant de machine en machine à l'intérieur d'un réseau compromis, à la recherche des actifs de valeur. |
| **DMZ (Zone Démilitarisée)** | Sous-réseau isolé hébergeant les serveurs accessibles depuis Internet, sans porte vers le réseau interne. |
| **HTTPS (HyperText Transfer Protocol Secure)** | Version sécurisée du protocole HTTP, chiffrant les échanges navigateur-serveur pour empêcher l'interception. |
| **Pare-feu (Firewall)** | Équipement ou logiciel filtrant les paquets entrants et sortants selon des règles ordonnées (Default Deny en dernière ligne). |
| **Port réseau** | Canal logique numéroté par lequel un service communique (443 = HTTPS, 22 = SSH) ; chaque port ouvert est une porte à surveiller. |
| **Segmentation réseau** | Partitionnement du réseau en zones étanches (VLANs, DMZ) pour limiter la propagation des menaces. |
| **Sniffing (Écoute réseau)** | Interception passive du trafic ; lit en clair tout ce qui transite en HTTP, Telnet ou FTP. |
| **TLS** | Protocole de chiffrement socle de HTTPS ; successeur de SSL (déprécié). |
| **VLAN (Virtual Local Area Network)** | Segmentation logique d'un réseau physique unique en plusieurs réseaux indépendants. |
| **VPN (Virtual Private Network)** | Tunnel chiffré acheminant de manière confidentielle les données sur un réseau public ; protège le transport, pas le contenu. |

**La règle d'or de la session :** tout ce qui n'est pas explicitement autorisé est interdit — et chaque zone du réseau doit pouvoir tomber sans entraîner les autres.
