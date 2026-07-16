# Plan de séance — Session B05 : Fondamentaux réseau pour la sécurité
Parcours : B 20 sessions  |  Module : B — Systèmes & réseaux  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (verbes d'action)
- **Expliquer** les couches clés des modèles OSI et TCP/IP à travers le prisme de la sécurité (où se situent les attaques et les défenses).
- **Identifier** le rôle des protocoles réseaux majeurs (DNS, DHCP, ARP, ICMP) et les ports de communication courants (22, 53, 80, 443, 3389).
- **Interpréter** une adresse IP (partie réseau / partie hôte) et les éléments fondamentaux d'un en-tête de paquet (IP source/destination, ports, TTL).

## Prérequis & progression
- **Prérequis** : Module A (Fondations, B01–B04).
- **Lien de progression** : Première session du module B — elle fournit le langage du réseau (couches, ports, paquets) indispensable pour concevoir le filtrage et la segmentation par pare-feu (B06), puis le chiffrement des communications (B07).

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama B05 ([spécifications](../slides/B_S05_slides_spec.md)) — les captures de paquets doivent être lisibles à l'écran (police à chasse fixe, grande taille).
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Point d'entrée préféré des attaquants (ANSSI 2024) ? | A) Les équipements de bordure exposés |
| 2 | 0:46 | Sondage | Capture A : port 53 en UDP = quel service ? | B) Un serveur DNS |
| 3 | 0:50 | Sondage | Capture A : le domaine à rallonge = quelle anomalie ? | B) Domaine trompeur d'hameçonnage |
| 4 | 0:54 | Sondage | Capture B : 45 tentatives RDP en 10 s = ? | C) Force brute sur RDP |
| 5 | 1:08 | Sondage | Connaissez-vous vos services exposés sur Internet ? | Opinion (pas de bonne réponse) |
| 6 | 1:16 | Sondage | Le rôle du DNS ? | B) Traduire les noms de domaine en IP |
| 7 | 1:18 | Sondage | Différence TCP / UDP ? | A) Fiable et ordonné vs rapide sans garantie |
| 8 | 1:20 | Sondage | À quoi sert le TTL ? | C) Limiter le nombre de routeurs traversés |
| 9 | Tampon | Sondage | `password=Password123` visible dans un paquet : quelle vulnérabilité ? | B) Identifiants en clair (HTTP) |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil, ouverture du module B & retour self-paced | 💬 Chat : IPv4 vs IPv6 |
| 0:04–0:10 | Brise-glace : par où entrent-ils ? | 📊 Sondage n°1 |
| 0:10–0:24 | Séquence 1 : Les couches OSI / TCP-IP | Question rhétorique |
| 0:24–0:36 | Séquence 2 : Protocoles & ports | 💬 Chat : associations |
| 0:36–0:44 | Séquence 3 : Adressage IP & en-têtes de paquets | Question rhétorique |
| 0:44–0:58 | Activité : L'analyste de paquets (captures A & B) | 📊 Sondages n°2, 3, 4 |
| 0:58–1:08 | Chiffres clés & affaire TV5 Monde (2015) | 💬 Chat : réactions |
| 1:08–1:12 | Et chez vous ? L'inventaire de l'exposition | 📊 Sondage n°5 |
| 1:12–1:16 | Mini-scénario : le RDP du prestataire | 🤔 Chat : A, B ou C |
| 1:16–1:22 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:22–1:26 | Exercice bonus : le mot de passe en clair (tampon) | 📊 Sondage n°9 |
| 1:26–1:30 | Synthèse, devoirs & teaser B06 | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & ouverture du module B

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous, et bienvenue dans le module Systèmes & réseaux ! Pendant quatre sessions, nous avons étudié les attaquants ; à partir de ce soir, on construit la défense — et ça commence par comprendre le terrain : le réseau. Question de la semaine dernière : en un mot dans le chat, qu'est-ce qui distingue IPv6 d'IPv4 ? »

**Points à dérouler :**
- Lire 2-3 réponses (attendu : des adresses beaucoup plus longues / plus nombreuses ; valider : IPv4 = 32 bits, épuisé ; IPv6 = 128 bits).
- Demander aussi : « qui a adapté son kit "5 réflexes" ? » — féliciter brièvement.
- Annonce du programme : le langage du réseau (couches, protocoles, ports), puis VOUS lirez de vraies captures de paquets, et l'histoire de la chaîne de télévision française qui a failli disparaître par son réseau.

**Transition scriptée :** « D'abord, une question stratégique : par où entrent les attaquants ? »

### 0:04–0:10 — Brise-glace : Sondage n°1 (les équipements de bordure)

**Consigne :** Lancer le **📊 Sondage n°1** — le point d'entrée préféré des attaquants selon l'ANSSI. Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse A : les équipements de bordure — tout ce qui est directement joignable depuis Internet : passerelles VPN, pare-feux, accès distants (ANSSI, Panorama 2024). Pourquoi ? Parce que tout ce qui est exposé est scanné en PERMANENCE par des robots. Il n'existe pas de "personne ne connaît mon adresse" : les scanners parcourent tout Internet, méthodiquement. La question de ce module n'est donc pas "suis-je visible ?" mais "qu'ai-je laissé ouvert ?". Pour y répondre, il faut parler le langage du réseau. C'est parti. »

**Transition scriptée :** « Premier outil : un modèle en couches, plus simple qu'il n'en a l'air. »

### 0:10–0:24 — Séquence 1 : Les couches OSI / TCP-IP

**Points de contenu à dérouler (support §1) :**
- L'idée : les données descendent des couches en s'encapsulant — dérouler l'**analogie postale** complète (la lettre = le contenu applicatif ; recommandé vs courrier simple = TCP vs UDP ; l'adresse sur l'enveloppe = IP ; le coursier du bâtiment = MAC ; le signal physique = le câble).
- **Couche 2 (Liaison / MAC)** : communication locale — attaque : ARP spoofing (interception locale) ; défense : sécurité des ports de commutateurs.
- **Couche 3 (Réseau / IP)** : routage mondial — attaque : IP spoofing ; défense : pare-feu, ACL.
- **Couche 4 (Transport / TCP-UDP)** : la connexion de bout en bout — attaque : SYN flood ; défense : pare-feu à états.
- **Couche 7 (Application)** : HTTP, DNS, SMTP, RDP — attaque : injections ; défense : WAF, chiffrement TLS.
- Question rhétorique : *« Pourquoi un modèle en couches aide-t-il le DÉFENSEUR ? »* — parce que diagnostiquer la couche, c'est choisir la défense (rappel du DDoS de B03 : saturation couche 3-4 vs épuisement couche 7 — parades différentes).

**Transition scriptée :** « Dans ces couches circulent des protocoles — des langages. Voici les cinq à connaître absolument. »

### 0:24–0:36 — Séquence 2 : Protocoles & ports

**Points de contenu à dérouler (support §2) :**
- **DNS (port 53)** : l'annuaire d'Internet — et son détournement (tunneling DNS : exfiltrer des données dans des requêtes anodines, car le port 53 sort presque toujours).
- **DHCP** : la distribution automatique de configuration — risque : le serveur DHCP pirate.
- **ARP** : IP → MAC en local — risque : l'empoisonnement ARP (l'homme du milieu local).
- **ICMP** : le diagnostic (`ping`) — risque : la cartographie par balayage.
- **Les ports = des portes numérotées** : 22 SSH, 80 HTTP (en clair !), 443 HTTPS, 3389 RDP (le chouchou des rançongiciels).
- La règle IANA : ports 0-1023 réservés ; fermer tout port non utilisé = première réduction de surface d'attaque.
- Relance chat (0:33) : *« Sans regarder vos notes : le port 443, c'est quoi ? Et le 22 ? »* — lire et corriger en direct.

**Transition scriptée :** « Dernière pièce du puzzle avant la pratique : savoir lire l'enveloppe elle-même. »

### 0:36–0:44 — Séquence 3 : Adressage IP & en-têtes

**Points de contenu à dérouler (support §3) :**
- L'adresse IPv4 : 32 bits, deux parties séparées par le masque — la **rue** (adresse réseau) et le **numéro de maison** (adresse hôte).
- L'en-tête IP : IP source / IP destination, **TTL** (le compteur de sauts : -1 à chaque routeur, destruction à 0 — l'anti-boucle d'Internet), protocole encapsulé (TCP/UDP).
- Question rhétorique : *« Pourquoi un défenseur lit-il des en-têtes toute la journée ? »* — une IP interne qui parle à une IP inconnue à l'étranger, un port inhabituel, un volume anormal : tout signal part de là.

**Transition scriptée :** « Assez de théorie. Deux captures de paquets s'affichent — c'est vous, les analystes. »

### 0:44–0:58 — Activité : L'analyste de paquets (Sondages n°2 à 4)

**Consigne :** Afficher la **Capture A** (support, activité « L'analyste de paquets »), laisser 30 secondes de lecture silencieuse, puis lancer les **📊 Sondages n°2 puis 3**. Afficher ensuite la **Capture B** et lancer le **📊 Sondage n°4** (~4-5 min par sondage : lecture, vote, débrief).

**🎙️ Verbatim de lancement :**
> « Voici une trame réseau réelle, simplifiée pour la lecture. Prenez 30 secondes : couche par couche, qui parle, à qui, sur quelle porte ? ... Premier vote : le port de destination est 53, en UDP — quel service est contacté ? »

**Débriefs scriptés (points obligatoires) :**
- N°2 (DNS) : dérouler la lecture complète en couches — MAC local, IP source interne vers `8.8.8.8` (résolveur DNS public), UDP + port 53 = DNS. « Vous venez de lire votre premier paquet. »
- N°3 (le domaine trompeur) : la couche application révèle l'intention — ce domaine à rallonge imite une banque ; c'est probablement la résolution DNS qui précède un clic d'hameçonnage (tout se recoupe avec B04). Le mot « secure » dans un domaine n'a AUCUNE valeur.
- N°4 (force brute RDP) : 45 tentatives en 10 secondes — aucun humain ne tape si vite. Et notez l'origine : une IP **interne**. Une machine déjà compromise attaque ses voisines — le mouvement latéral. « Gardez cette image : l'histoire qui suit, c'est exactement ça, en vrai. »

**Transition scriptée :** « Quelques chiffres pour mesurer l'enjeu — puis direction avril 2015, dans une chaîne de télévision française. »

### 0:58–1:08 — Chiffres clés & affaire TV5 Monde

**Chiffres (3 min, support §4) :** les équipements de bordure parmi les vecteurs d'intrusion privilégiés (ANSSI 2024) ; plusieurs milliards de tentatives de force brute RDP détectées sur la seule année 2020, dopées par le télétravail (Kaspersky) — « la capture B n'était pas un exercice théorique » ; et le coût d'un réseau à reconstruire : de l'ordre de 5 M€ la première année pour TV5 Monde.

**Cas — TV5 Monde, 2015 (7 min, support §5) :** raconter chronologiquement : le 8 avril 2015 au soir, les douze chaînes passent à l'écran noir ; revendication « CyberCaliphate », mais l'enquête oriente vers le groupe APT28 (rappel B02 : les fausses bannières existent) ; l'intrusion remontait à des semaines — entrée par un accès de **prestataire**, cartographie patiente du réseau, puis sabotage des équipements de diffusion ; un réseau « à plat » où tout communiquait avec tout ; le sauvetage : des techniciens présents cette nuit-là **débranchent** les machines compromises ; des mois de reconstruction avec l'ANSSI ; et le détail resté célèbre — les **mots de passe sur post-it** visibles dans un reportage télévisé tourné dans les locaux. Relance chat : *« Quel détail vous marque le plus ? »*

**Transition scriptée :** « TV5 ne savait pas ce qui était exposé ni ce qui pouvait parler à quoi. Et vous ? »

### 1:08–1:12 — Sondage n°5 : l'inventaire de l'exposition

**Consigne :** Lancer le **📊 Sondage n°5** (opinion) — sauriez-vous dire quels services de votre organisation sont exposés sur Internet ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Pas de bonne réponse — un réflexe à installer : on ne défend pas ce qu'on ne connaît pas. La première action d'un responsable réseau, c'est de cartographier sa propre surface exposée... ce que les attaquants font déjà en continu à votre place. Si vous avez répondu C, c'est normal à ce stade — l'atelier de synthèse B08 vous fera précisément construire cette cartographie. »

### 1:12–1:16 — 🤔 Mini-scénario : le RDP du prestataire

**Consigne :** Afficher le mini-scénario du support : le RDP du serveur exposé sur Internet « parce que le prestataire en a besoin ». *« Tapez A, B ou C dans le chat. »*

**Débrief :** B — garder la fonction, changer le chemin : VPN ou bastion + MFA + journalisation. A ignore les milliards de tentatives de force brute annuelles ; C (changer de port) est de la **sécurité par l'obscurité** — les scanners parcourent tous les ports en quelques secondes. Et rappeler TV5 : l'accès prestataire est un vecteur d'entrée classique.

**Transition scriptée :** « Trois questions pour valider le langage du réseau. »

### 1:16–1:22 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : le DNS traduit les noms en IP (le piège est le DHCP) ; TCP fiable et ordonné vs UDP rapide sans garantie (le chiffrement n'a rien à voir — c'est TLS, teaser B07) ; le TTL limite les sauts de routeurs. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/B_S05_support.md).

### 1:22–1:26 — Exercice bonus (Sondage n°9) — *segment tampon*

**Consigne :** Afficher la capture `POST /login.php` avec `password=Password123` visible, puis lancer le **📊 Sondage n°9**. Débrief : des identifiants en clair sur HTTP (port 80) — quiconque écoute le trafic les lit : c'est le *sniffing*, l'écoute passive. La parade s'appelle TLS (HTTPS, port 443)... et c'est exactement le programme de B07. À couper en cas de retard.

### 1:26–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Ce soir, vous avez appris le langage du réseau : des couches — à chacune ses attaques et ses défenses ; des ports — des portes numérotées à inventorier et à fermer ; des paquets — que vous savez désormais lire. Et TV5 Monde vous a montré ce qui arrive quand un réseau est à plat et exposé. Un mot que vous retenez, dans le chat ! »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Self-paced : cours IBM SkillsBuild *"Network Security - Part 1"* (~1h30) + action pratique `ping cyber.gouv.fr` (observer le TTL) + lister les appareils connectés à son Wi-Fi domestique et réfléchir à leur isolement (préparation directe de B06).
- Teaser B06 : « la semaine prochaine, on construit les murailles : pare-feux, DMZ, segmentation — et l'histoire d'un géant américain de la distribution piraté via... son prestataire de chauffage. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**Exercice bonus n°9** (1:22–1:26) — il est dans le support en exercice bonus.
2. Compresser la séquence 3 (adressage) à 5 min en renvoyant le détail du masque de sous-réseau au support.
3. Raccourcir le débrief du sondage n°5 à 1 min.
4. Ne JAMAIS couper : l'activité d'analyse de paquets, le cas TV5 Monde, le quiz.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°2 : l'exfiltration par tunnel DNS).
2. Démonstration en direct : `ping cyber.gouv.fr` dans un terminal partagé — lire ensemble le TTL renvoyé.
3. Questions/réponses libres.

## Travail en autonomie (Self-paced)
* **Avant la session suivante (B06)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Network Security - Part 1"* (durée estimée : 1h30).
  * **Action pratique** : Dans un terminal, taper `ping -c 4 cyber.gouv.fr` (ou `ping cyber.gouv.fr` sous Windows) et observer le temps de réponse et la valeur de TTL.
  * **Exercice de réflexion** : Lister tous les appareils connectés au réseau Wi-Fi domestique (ordinateur, téléphone, IoT) et réfléchir à la façon dont on pourrait les isoler ou les protéger les uns des autres.
