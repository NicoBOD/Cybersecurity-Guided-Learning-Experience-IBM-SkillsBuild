# Session B05 — Fondamentaux réseau pour la sécurité
Parcours : B 20 sessions  |  Module : B — Systèmes & réseaux  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Les Modèles OSI et TCP/IP sous l'angle de la sécurité
    - Protocoles et ports de communication majeurs
    - Adressage IP et En-têtes de paquets
    - Une affaire réelle : TV5 Monde (2015), la chaîne qui a failli mourir par son réseau
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Les couches réseau (Liaison, Réseau, Transport, Application) structurent la façon dont les données transitent et définissent les différents types d'attaques cyber.
*   Chaque service réseau standard écoute sur un **port de communication** spécifique (22 pour SSH, 53 pour DNS, 80/443 pour HTTP/S, 3389 pour RDP).
*   Une capture de paquets (trame réseau) révèle l'origine (IP/MAC source), la destination (IP/MAC destination), le protocole et le contenu applicatif du flux.
*   Bloquer les ports inutilisés et analyser le trafic anormal sont des réflexes indispensables pour assurer la sécurité réseau.

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer les couches clés des modèles OSI et TCP/IP à travers le prisme de la sécurité en identifiant où se situent les principales attaques et défenses.
* Décrire le rôle des protocoles réseaux majeurs (DNS, DHCP, ARP, ICMP) et identifier les ports de communication standards les plus exposés (22, 53, 80, 443, 3389).
* Lire et analyser la structure d'une adresse IP (partie réseau vs partie hôte) et interpréter les éléments clés d'un en-tête de paquet réseau simple (IP source/dest, ports, TTL).

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** Selon l'ANSSI (Panorama de la cybermenace 2024), quel est l'un des points d'entrée préférés des attaquants dans les réseaux d'entreprise ?

    - A) Les équipements de bordure exposés sur Internet (passerelles VPN, pare-feux, serveurs d'accès distant) ✅
    - B) Les clés USB piégées déposées à l'accueil
    - C) Le Bluetooth des téléphones des salariés

    **Débrief mentor :** Réponse A : l'ANSSI constate que les **équipements de bordure** — tout ce qui est directement joignable depuis Internet — sont un vecteur d'intrusion privilégié. La logique est simple : ce qui est exposé est scanné en permanence par des robots, et une seule faille ou un seul service oublié suffit. Ce soir, vous apprenez à raisonner comme le réseau : par où passent les données, quelles portes existent, et lesquelles devraient être fermées. C'est le début du module Systèmes & réseaux.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. DNS : l'annuaire... et le tunnel**
Approfondissez le fonctionnement du DNS (résolution de nom, hiérarchie des serveurs) et ses détournements : le *DNS spoofing* pour rediriger le trafic vers un faux site, et le *DNS tunneling* pour exfiltrer des données dans des requêtes apparemment inoffensives — les pare-feux laissent presque toujours sortir le port 53. Le paradoxe pédagogique à faire passer : le protocole le plus « banal » du réseau est aussi l'un des canaux d'exfiltration favoris (l'exemple d'application professionnelle plus bas le met en scène).

**2. ARP et les attaques locales**
Rappelez le fonctionnement d'ARP (traduction IP → MAC sur le réseau local) et l'empoisonnement ARP (*ARP poisoning*) : l'attaquant local répond « c'est moi » à toutes les requêtes et intercepte le trafic du segment (position d'homme du milieu). C'est l'illustration parfaite de la différence couche 2 / couche 3 : ARP ne quitte jamais le réseau local — l'attaque non plus.

**3. Le scan permanent d'Internet**
Insistez sur une réalité contre-intuitive pour les débutants : toute machine exposée sur Internet est **scannée en continu** par des robots (moteurs de recherche de services exposés, botnets de force brute). Il n'y a pas de « personne ne connaît mon adresse » : les scanners parcourent tout l'espace d'adressage. Corollaire : changer un port standard (3389 → 3390) ne cache rien — c'est de la sécurité par l'obscurité, balayée en quelques secondes de scan. La seule vraie question : ce service DOIT-il être exposé ?

---

### Glossaire

*   **DNS Tunneling (Tunneling DNS)** — Technique de détournement consistant à encapsuler du trafic non-DNS dans des requêtes DNS pour contourner les pare-feux.
*   **IP Address (Adresse IP)** — Identifiant logique attribué à chaque machine connectée à un réseau, permettant son routage.
*   **MAC Address (Adresse MAC)** — Identifiant physique unique gravé en usine sur chaque carte réseau.
*   **Modèle OSI** — Cadre théorique décrivant en 7 couches distinctes le processus de communication des systèmes informatiques sur un réseau.
*   **Port de communication** — Porte d'entrée logique d'une machine (numérotée de 0 à 65535) sur laquelle un service réseau écoute (ex. 443 pour HTTPS).
*   **TCP (Transmission Control Protocol)** — Protocole de transport réseau orienté connexion garantissant la transmission fiable et ordonnée des paquets de données.
*   **TTL (Time To Live)** — Valeur dans l'en-tête IP indiquant le nombre maximal de sauts de routeurs autorisés avant la destruction du paquet.
*   **UDP (User Datagram Protocol)** — Protocole de transport réseau rapide sans connexion ne garantissant pas la livraison ni l'ordre des paquets.
*   **Wireshark** — Logiciel analyseur de protocoles réseau open-source permettant de capturer et d'inspecter les paquets circulant sur un segment de réseau.

---

### Concepts clés

!!! info "À retenir"
    Le réseau n'est pas un nuage magique : c'est une suite de couches, de protocoles et de **portes numérotées** (les ports). Savoir lire un paquet — qui parle à qui, sur quelle porte, avec quel protocole — est la compétence de base de toute la défense réseau : on ne protège bien que ce qu'on sait observer.

### 1. Les Modèles OSI et TCP/IP sous l'angle de la sécurité
Pour faire communiquer des ordinateurs, les données doivent être formatées et transmises selon des règles strictes. Le modèle théorique **OSI** (en 7 couches) et le modèle pratique **TCP/IP** (en 4 couches) décrivent ce processus. En cybersécurité, chaque couche représente une surface d'attaque spécifique et nécessite des défenses adaptées.

*   **Couche 2 : Liaison (*Data Link*)** — Gère la communication physique locale entre cartes réseau via les adresses **MAC** (*Media Access Control*).
    *   *Attaque* : L'usurpation ARP (*ARP spoofing*) permettant d'intercepter le trafic local.
    *   *Défense* : Sécurisation des ports de commutateurs (*Port Security*) et inspection ARP dynamique.
*   **Couche 3 : Réseau (*Network*)** — Assure le routage des paquets à travers Internet via les adresses **IP** (*Internet Protocol*).
    *   *Attaque* : L'usurpation d'adresse IP (*IP spoofing*) pour masquer l'identité de l'attaquant.
    *   *Défense* : Filtrage par pare-feu (*firewall*) et listes de contrôle d'accès (ACL).
*   **Couche 4 : Transport** — Assure la connexion de bout en bout (TCP pour les connexions fiables avec maintien d'état, UDP pour la rapidité sans garantie).
    *   *Attaque* : Inondation de paquets SYN (*SYN Flood*) pour saturer la mémoire d'un serveur et le rendre indisponible.
    *   *Défense* : Pare-feux à états (*stateful firewalls*) et limites de connexions par IP.
*   **Couche 7 : Application** — Les protocoles utilisés par les logiciels finaux (HTTP, DNS, SMTP, RDP).
    *   *Attaque* : Injections de code (SQL, XSS), usurpation de services.
    *   *Défense* : Pare-feu applicatif (WAF — *Web Application Firewall*), chiffrement TLS.

*   *Analogie postale* :
    *   Couche 2 (Liaison) = Le coursier qui transporte les enveloppes dans un même bâtiment.
    *   Couche 3 (Réseau) = L'adresse écrite sur l'enveloppe lue par le centre de tri national.
    *   Couche 4 (Transport) = Le choix d'envoyer la lettre en recommandé avec accusé de réception (TCP) ou en courrier simple (UDP).
    *   Couche 7 (Application) = La langue (français, anglais) et le contenu du message écrit à l'intérieur.

Souvenez-vous du DDoS vu en B03 : selon la couche visée (saturation de bande passante en couche 3-4, épuisement applicatif en couche 7), la parade n'est pas la même. **Diagnostiquer la couche, c'est choisir la défense.**

### 2. Protocoles et ports de communication majeurs
Les données circulent sur le réseau via des protocoles (langages) spécifiques, et arrivent à destination sur des **ports de communication** (portes d'entrée logiques sur une machine).

*   **DNS (*Domain Name System*) — Port 53** : L'annuaire d'Internet. Il traduit les noms de domaine lisibles (ex: `cyber.gouv.fr`) en adresses IP compréhensibles par les machines.
    *   *Risque* : Le tunneling DNS (*DNS tunneling*), utilisé par les attaquants pour exfiltrer discrètement des données dans des requêtes DNS légitimes.
*   **DHCP (*Dynamic Host Configuration Protocol*)** : Attribue automatiquement une configuration IP aux machines qui se connectent au réseau local.
    *   *Risque* : Un serveur DHCP pirate (*Rogue DHCP*) qui distribue de fausses configurations pour détourner le trafic.
*   **ARP (*Address Resolution Protocol*)** : Traduit une adresse IP connue en adresse MAC physique sur le réseau local.
    *   *Risque* : L'empoisonnement ARP (*ARP poisoning*), qui permet à un attaquant local de se placer en interception (position d'« homme du milieu »).
*   **ICMP (*Internet Control Message Protocol*)** : Utilisé pour les diagnostics réseau (comme la commande `ping`).
    *   *Risque* : La cartographie du réseau par balayages de `ping` (*ping sweeps*) — beaucoup d'entreprises filtrent l'ICMP pour compliquer cette reconnaissance.

#### Les ports courants à surveiller :
*   **Port 22 — SSH (*Secure Shell*)** : Connexion d'administration à distance sécurisée (souvent ciblé par attaques par force brute).
*   **Port 80 — HTTP** : Trafic web non chiffré (à proscrire pour les données sensibles).
*   **Port 443 — HTTPS** : Trafic web chiffré via TLS.
*   **Port 3389 — RDP (*Remote Desktop Protocol*)** : Prise de contrôle à distance graphique Windows (extrêmement recherché par les rançongiciels).

> 💡 **Bon à savoir : Les ports bien connus (*Well-Known Ports*)**
> Les ports de 0 à 1023 sont réservés par l'IANA (*Internet Assigned Numbers Authority*) pour les services système standard (comme HTTP sur le port 80). Les fermer s'ils ne sont pas activement utilisés est la première règle de réduction de surface d'attaque.

### 3. Adressage IP et En-têtes de paquets
Une adresse IPv4 est composée de 32 bits (ex. `192.168.1.50`). Elle est divisée en deux parties grâce au **masque de sous-réseau** (ex. `255.255.255.0`) :

1.  **L'adresse réseau** : identifie le réseau sur lequel se trouve la machine (la rue).
2.  **L'adresse hôte** : identifie la machine spécifique sur ce réseau (le numéro de maison).

Lorsqu'un paquet est envoyé, il contient un **en-tête IP** contenant les métadonnées de transmission :

*   **IP Source & IP Destination** : Qui envoie et qui reçoit.
*   **TTL (*Time To Live*)** : Une durée de vie sous forme de compteur de routeurs traversés. À chaque routeur, le TTL baisse de 1. S'il atteint 0, le paquet est détruit pour éviter qu'il ne tourne en boucle infinie sur Internet.
*   **Protocol** : Indique si le paquet de transport encapsulé est du TCP ou de l'UDP.

**Pourquoi c'est une compétence de sécurité ?** Parce qu'un défenseur passe son temps à lire ces en-têtes : une IP interne qui parle à une IP inconnue à l'étranger, un port de destination inhabituel, un volume anormal — tout part de là. Vérifions-le immédiatement.

### Activité — L'analyste de paquets (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Affichez successivement les deux captures de trames simplifiées ci-dessous, laissez 30 secondes de lecture silencieuse, puis lancez les sondages. Débriefez après chaque vote en relisant la ligne concernée de la capture.

#### Capture A
```text
[ FRAME LAYER 2 ] Source MAC: 00:1A:2B:3C:4D:5E -> Dest MAC: 00:1A:2B:99:88:77
[ IP LAYER 3 ] Source IP: 192.168.1.15 -> Dest IP: 8.8.8.8 | TTL: 64 | Proto: UDP
[ TRANSPORT LAYER 4 ] Source Port: 53120 -> Dest Port: 53
[ APPLICATION LAYER 7 ] DNS Query: secure-login.bank-online-security-update.com
```

#### Capture B
```text
[ FRAME LAYER 2 ] Source MAC: 00:1A:2B:3C:4D:5E -> Dest MAC: 00:1A:2B:99:88:77
[ IP LAYER 3 ] Source IP: 192.168.1.102 -> Dest IP: 192.168.1.200 | TTL: 128 | Proto: TCP
[ TRANSPORT LAYER 4 ] Source Port: 49215 -> Dest Port: 3389
[ APPLICATION LAYER 7 ] RDP Connection Request | Connection Attempt: 45th in the last 10 seconds
```

*   **📊 Sondage n°2 — Capture A, le service :** Le port de destination est 53, en UDP. Quel service la machine `192.168.1.15` est-elle en train de contacter ?
    *   A) Un serveur web (HTTP)
    *   B) Un serveur DNS — l'annuaire qui traduit les noms de domaine en adresses IP ✅
    *   C) Un serveur de bureau à distance (RDP)
*   **📊 Sondage n°3 — Capture A, l'anomalie :** En couche application, la requête demande la résolution de `secure-login.bank-online-security-update.com`. Que suspectez-vous ?
    *   A) Rien : le mot « secure » indique un site sécurisé
    *   B) Un nom de domaine trompeur typique d'une page d'hameçonnage bancaire ✅
    *   C) Une attaque par déni de service contre la banque
*   **📊 Sondage n°4 — Capture B, le comportement :** 45ᵉ tentative de connexion en 10 secondes vers le port 3389 d'une machine du même réseau local. Qu'observez-vous ?
    *   A) Un utilisateur pressé qui a oublié son mot de passe
    *   B) Une sauvegarde automatique de fichiers
    *   C) Une attaque par force brute sur le service de bureau à distance (RDP) ✅

**Éléments de débriefing (pour le mentor) :**

- N°2 : dérouler la lecture complète en couches — MAC (local), IP source/destination (`8.8.8.8` est un résolveur DNS public), UDP + port 53 = DNS. Vous venez de lire votre premier paquet.
- N°3 : le contenu applicatif révèle l'intention : ce domaine à rallonge imite une banque — probablement la résolution qui précède un clic d'hameçonnage (tout se recoupe avec B04 !). Le mot « secure » dans un domaine n'a AUCUNE valeur de sécurité.
- N°4 : 45 tentatives en 10 secondes, aucun humain ne tape si vite : robot de force brute. Notez que l'attaque vient d'une IP **interne** (`192.168.1.102`) — une machine déjà compromise attaque ses voisines : c'est le mouvement latéral, et l'affaire qui suit montre où cela mène.

### 4. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **Les équipements de bordure** (passerelles VPN, pare-feux, accès distants exposés) figurent parmi les vecteurs d'intrusion privilégiés des attaquants (ANSSI, *Panorama de la cybermenace 2024*).
    - **Plusieurs milliards** de tentatives d'attaques par force brute sur le protocole RDP ont été détectées sur la seule année 2020, dopées par le télétravail (télémétrie Kaspersky).
    - **De l'ordre de 5 M€** la première année, puis plusieurs millions les années suivantes : le coût de la reconstruction du réseau de TV5 Monde après l'attaque de 2015 (chiffres communiqués par la chaîne — cas détaillé ci-dessous).

**Comment lire ces chiffres ?** (1) Tout ce qui est exposé sur Internet est scanné en permanence — la question n'est pas « qui connaît mon adresse ? » mais « qu'ai-je laissé ouvert ? ». (2) Le RDP de la capture B n'est pas un exercice théorique : c'est l'une des attaques les plus massives du monde réel. (3) Un réseau mal conçu ne coûte pas cher... jusqu'au jour où il faut le reconstruire entièrement.

### 5. Une affaire réelle : TV5 Monde (2015), la chaîne qui a failli mourir par son réseau

Le soir du **8 avril 2015**, les douze chaînes de **TV5 Monde** passent à l'écran noir : plus de diffusion, messagerie hors service, systèmes de production paralysés. L'attaque est revendiquée par un mystérieux « CyberCaliphate », mais l'enquête orientera vers un groupe étatique connu sous le nom d'**APT28** — retour à la leçon de B02 : les fausses bannières existent, l'attribution est un métier.

Le mode opératoire, reconstitué notamment avec l'aide de l'**ANSSI**, est un cas d'école réseau : entrés **des semaines plus tôt** via un accès de prestataire, les attaquants ont patiemment cartographié le réseau — machines, flux, comptes d'administration — avant de saboter les équipements au cœur de la diffusion. Le réseau, conçu pour la production audiovisuelle, était largement « à plat » : depuis un point d'entrée périphérique, on pouvait atteindre les machines les plus critiques. La chaîne n'a survécu que grâce à des techniciens présents sur place cette nuit-là, qui ont **débranché** les équipements compromis — puis des mois de reconstruction, avec un coût de l'ordre de 5 M€ la première année et une facture qui s'est prolongée les années suivantes.

Détail resté célèbre : quelques semaines après l'attaque, lors d'un reportage télévisé tourné dans les locaux, des **mots de passe étaient visibles sur des post-it** en arrière-plan. La sécurité réseau la plus sophistiquée ne survit pas aux fondamentaux négligés.

**Ce que ce cas illustre :** un point d'entrée périphérique (accès prestataire) + un réseau à plat = la compromission peut atteindre le cœur ; la reconnaissance réseau silencieuse précède le sabotage (les captures que vous venez d'apprendre à lire sont exactement ce qu'il aurait fallu surveiller) ; et le débranchement d'urgence a sauvé la chaîne — parfois, la couche physique est la dernière défense. La suite logique — cloisonner le réseau pour qu'une intrusion ne se propage pas — est précisément l'objet de la session B06.

!!! tip "📊 Sondage Livestorm n°5 — Et chez vous ? (sondage d'opinion, pas de bonne réponse)"
    **Question :** Dans votre organisation, sauriez-vous dire quels services (ports) sont aujourd'hui exposés sur Internet ?

    - A) Oui : un inventaire est tenu et revu régulièrement
    - B) Partiellement : on connaît les principaux, sans inventaire formel
    - C) Aucune idée / Je ne sais pas qui le sait

    **Débrief mentor :** Sondage d'opinion — l'objectif est le réflexe d'inventaire. On ne défend pas ce qu'on ne connaît pas : la première action de tout responsable réseau est la cartographie de sa propre surface exposée (ce que les attaquants, eux, font déjà en continu avec leurs scanners). Les réponses C sont normales à ce stade du parcours — l'atelier de synthèse B08 vous fera précisément concevoir cette cartographie.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Un audit révèle que le serveur de votre PME expose son service **RDP (port 3389) directement sur Internet** : le prestataire informatique s'en sert pour la maintenance à distance. **Tapez A, B ou C dans le chat :**

    - A) Ne rien changer : le prestataire en a besoin pour son travail.
    - B) Fermer l'exposition directe et faire passer la maintenance par un accès sécurisé (VPN ou bastion) avec double authentification. ✅
    - C) Déplacer le service sur le port 3390 pour le cacher des attaquants.

    **Débrief mentor :** B — le besoin du prestataire est légitime, c'est l'exposition directe qui ne l'est pas : on garde la fonction, on change le chemin (VPN/bastion + MFA + journalisation). A ignore les milliards de tentatives de force brute annuelles sur RDP ; C est de la **sécurité par l'obscurité** : les scanners parcourent tous les ports en quelques secondes — un service déplacé n'est pas un service protégé. Et rappelez TV5 Monde : l'accès prestataire est un vecteur d'entrée classique.

---

### Questions de réflexion
1. Dans l'affaire TV5 Monde, les attaquants ont pu atteindre les équipements de diffusion critiques depuis un simple point d'entrée périphérique. Qu'est-ce qu'un réseau « à plat », et pourquoi la séparation des réseaux (bureautique / production) est-elle considérée comme LA leçon de cette affaire ?
2. Si un pare-feu bloque le trafic sur le port 80 (HTTP) mais laisse passer le trafic sur le port 53 (DNS), comment un attaquant peut-il utiliser cette configuration pour exfiltrer des fichiers ?

**Corrigé / Éléments de réponse :**

1. Un réseau « à plat » est un réseau sans cloisonnement interne : toutes les machines peuvent se joindre entre elles. Une seule machine compromise peut alors atteindre n'importe quelle cible (mouvement latéral) — c'est ce qui a permis de passer d'un accès prestataire aux encodeurs de diffusion. La séparation en zones étanches (bureautique / production / administration) confine l'intrusion : c'est la segmentation, objet de la session B06.
2. En encapsulant les données volées à l'intérieur de requêtes DNS légitimes (tunneling DNS), le pare-feu verra du trafic DNS normal et le laissera passer — d'où l'intérêt de surveiller aussi le **volume** et la destination des requêtes DNS, pas seulement leur existence.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez le fonctionnement d'un réseau informatique et le modèle OSI comme l'envoi d'une **lettre par la poste** :
    - **Couches Applicative / Présentation / Session** : Vous écrivez votre lettre en français (Données), la pliez et l'insérez dans une enveloppe scellée.
    - **Couche Transport (TCP/UDP)** : Vous décidez d'envoyer la lettre en recommandé avec accusé de réception (TCP, fiable et ordonné) ou par courrier normal sans garantie (UDP, rapide mais sans suivi).
    - **Couche Réseau (IP)** : Vous inscrivez l'adresse IP de destination et de départ sur l'enveloppe.
    - **Couche Liaison de données (MAC / Ethernet)** : Le facteur trie l'enveloppe et l'associe au camion postal physique correspondant à votre rue (liaison physique locale).
    - **Couche Physique** : La lettre circule sous forme de signaux physiques (impulsions électriques sur fils de cuivre ou lumière dans la fibre optique).

**Exemple d'application professionnelle :**
Un administrateur réseau utilise l'outil Wireshark pour analyser les paquets de données qui transitent sur le réseau de son entreprise. Il repère une anomalie : un serveur interne effectue des requêtes DNS (port 53 UDP) anormalement fréquentes vers une adresse IP inconnue à l'étranger. Cette analyse au niveau des couches transport et réseau lui permet de détecter une tentative d'exfiltration de données masquée par tunnel DNS.

### Panorama des solutions du marché (Commerciales & Open-Source)

L'analyse de protocoles et la surveillance de la couche réseau reposent sur les solutions de captures de paquets suivantes :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **NetScout nGeniusONE** : Solution d'analyse réseau d'entreprise haut de gamme pour surveiller les performances et identifier les anomalies de flux sur les réseaux télécoms et bancaires.
    *   **Riverbed AppResponse** : Outil d'analyse du trafic réseau permettant de capturer tous les paquets à des vitesses très élevées pour le diagnostic et la sécurité.
    *   **Cisco DNA Center / Cisco ThousandEyes** : Visibilité réseau approfondie et surveillance active des connexions utilisateur multi-sites.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **Wireshark** : L'analyseur de paquets réseau open-source standard du marché, incontournable pour capturer et disséquer les protocoles réseau locaux.
    *   **tcpdump** : Outil d'analyse en ligne de commande ultra-léger disponible sur tous les systèmes Linux/Unix pour capturer des paquets sans interface graphique.
    *   **Zeek (anciennement Bro)** : Framework d'analyse réseau open-source qui convertit le trafic réseau brut en logs structurés hautement qualifiés pour la détection de menaces.
    *   **Suricata** : Moteur d'IDS/IPS open-source capable d'analyser le trafic réseau en temps réel et de générer des alertes de sécurité.

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après le mini-scénario.

*   **📊 Sondage n°6 :** Quel est le rôle du DNS (port 53) ?
    *   A) Chiffrer les communications entre deux machines
    *   B) Traduire les noms de domaine lisibles en adresses IP ✅
    *   C) Attribuer automatiquement une adresse IP aux machines du réseau local
*   **📊 Sondage n°7 :** Quelle est la différence fondamentale entre TCP et UDP ?
    *   A) TCP garantit une transmission fiable et ordonnée (avec accusés de réception) ; UDP privilégie la rapidité sans garantie ✅
    *   B) TCP est chiffré, UDP ne l'est pas
    *   C) TCP sert au web, UDP sert uniquement aux jeux vidéo
*   **📊 Sondage n°8 :** À quoi sert le champ TTL d'un en-tête IP ?
    *   A) À chiffrer le contenu du paquet
    *   B) À indiquer la taille maximale du paquet
    *   C) À limiter le nombre de routeurs traversés pour éviter qu'un paquet ne circule indéfiniment ✅

**Éléments de débriefing (pour le mentor) :**

- N°6 : le piège est C (c'est le DHCP). DNS = l'annuaire — et souvenez-vous : un annuaire, ça se surveille (tunneling, domaines trompeurs de la capture A).
- N°7 : « chiffré » n'a rien à voir avec TCP/UDP — le chiffrement arrive au-dessus (TLS, session B07). Recommandé avec accusé (TCP) vs courrier simple (UDP).
- N°8 : le TTL décroît de 1 à chaque routeur ; c'est aussi un indice de diagnostic (la commande `ping` de votre travail en autonomie l'affiche).

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Network Security - Part 1"* (durée estimée : 1h30).
*   **Action pratique** : Ouvrez un terminal sur votre machine et tapez la commande `ping -c 4 cyber.gouv.fr` (ou `ping cyber.gouv.fr` sous Windows). Observez le temps de réponse et la valeur de TTL renvoyée par le serveur.
*   [ANSSI — Recommandations réseaux](https://cyber.gouv.fr)
*   [CERT-FR — Menaces réseaux](https://www.cert.ssi.gouv.fr/)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Lecture de requêtes HTTP non sécurisées.
*   **📊 Sondage Livestorm n°9 :** Le mentor montre à l'écran une capture de paquet contenant la ligne : `POST /login.php HTTP/1.1` suivie de `username=admin&password=Password123`. Quelle vulnérabilité est visible ?
    *   A) Une attaque par déni de service.
    *   B) Une transmission d'identifiants en clair via le protocole HTTP non chiffré ✅
    *   C) Une tentative d'injection SQL.
*   **Guide d'animation (pour le mentor) :** Le mot de passe est lisible par quiconque observe le trafic (port 80 = HTTP, aucun chiffrement) : c'est le *sniffing*, l'écoute passive. Soulignez l'importance du protocole TLS (HTTPS, port 443) pour chiffrer les données en transit — c'est exactement le sujet de la session B07. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **DNS Tunneling (Tunneling DNS)** | Technique de détournement consistant à encapsuler du trafic non-DNS dans des requêtes DNS pour contourner les pare-feux. |
| **IP Address (Adresse IP)** | Identifiant logique attribué à chaque machine connectée à un réseau, permettant son routage. |
| **MAC Address (Adresse MAC)** | Identifiant physique unique gravé en usine sur chaque carte réseau. |
| **Modèle OSI** | Cadre théorique en 7 couches du processus de communication réseau — à chaque couche ses attaques et ses défenses. |
| **Port de communication** | Porte d'entrée logique numérotée d'une machine (22 SSH, 53 DNS, 80 HTTP, 443 HTTPS, 3389 RDP). |
| **TCP (Transmission Control Protocol)** | Transport fiable et ordonné, avec accusés de réception (le « recommandé »). |
| **TTL (Time To Live)** | Compteur de sauts de routeurs — le paquet est détruit quand il atteint 0. |
| **UDP (User Datagram Protocol)** | Transport rapide sans connexion ni garantie de livraison (le « courrier simple »). |
| **Wireshark** | L'analyseur de paquets open-source de référence pour capturer et inspecter le trafic. |

**La règle d'or de la session :** on ne défend que ce qu'on observe — sachez lire un paquet (qui, vers qui, quel port, quel protocole), inventoriez ce que vous exposez sur Internet, et fermez toute porte qui n'a pas de raison d'être ouverte.
