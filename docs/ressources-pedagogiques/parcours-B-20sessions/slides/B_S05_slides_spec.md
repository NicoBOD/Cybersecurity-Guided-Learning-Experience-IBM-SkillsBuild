# Spécifications des slides — Session B05 : Fondamentaux réseau pour la sécurité
Parcours : B 20 sessions  |  Module : B — Systèmes & réseaux  |  Format : Spécifications Markdown

> **Principe** : le texte affiché reste minimal (mots-clés, chiffres, schémas) ; le contenu riche est dans les notes orateur et le [plan de séance minuté](../plans-de-seance/B_S05_plan.md). Toutes les interactions passent par les sondages et le chat Livestorm.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Fondamentaux réseau pour la sécurité
  - Comprendre comment circulent les données pour mieux les protéger
  - Parcours B — Session B05 · Ouverture du module Systèmes & réseaux
- **Notes orateur** : Accueillir : ouverture du module B — après quatre sessions sur les attaquants, on construit la défense, en commençant par le terrain : le réseau. Retour self-paced : « en un mot dans le chat, qu'est-ce qui distingue IPv6 d'IPv4 ? » (attendu : adresses plus longues/nombreuses — 32 vs 128 bits). Demander qui a adapté son kit « 5 réflexes ».
- **Visuel suggéré** : Fond sombre avec une illustration de câbles réseaux interconnectés et de flux de données représentés par des impulsions lumineuses.
  - **alt-text** : Graphisme de câblage de centre de données avec des flux de données lumineux connectés à des serveurs.
- **Élément interactif** : 💬 Chat d'accueil — IPv4 vs IPv6 en un mot.

---

### Slide 2 — Objectifs & agenda
- **Type** : contenu
- **Points clés (bullets)** :
  - Expliquer les couches OSI / TCP-IP sous l'angle sécurité.
  - Associer protocoles (DNS, DHCP, ARP, ICMP) et ports standards (22, 53, 80, 443, 3389).
  - Lire un en-tête de paquet (IP, ports, TTL).
  - Agenda : couches → protocoles & ports → adressage → activité « analyste de paquets » → TV5 Monde → quiz.
- **Notes orateur** : Programme : démystifier les modèles en couches avec une analogie postale, apprendre les portes numérotées du réseau, puis VOUS lirez de vraies captures de paquets — avant l'histoire de la chaîne de télévision française qui a failli disparaître par son réseau.
- **Visuel suggéré** : Deux colonnes listant les objectifs et l'agenda de la séance.
  - **alt-text** : Tableau présentant les objectifs d'apprentissage et les étapes de la session de 90 minutes.

---

### Slide 3 — Brise-glace : par où entrent-ils ?
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **Sondage n°1** : le point d'entrée préféré des attaquants (ANSSI 2024) ?
  - A) Équipements de bordure exposés — B) Clés USB piégées — C) Bluetooth
- **Notes orateur** : Lancer le sondage n°1 (60-90 s). Réponse A : tout ce qui est directement joignable depuis Internet — passerelles VPN, pare-feux, accès distants (ANSSI, Panorama 2024). Tout ce qui est exposé est scanné en permanence par des robots : la question n'est pas « suis-je visible ? » mais « qu'ai-je laissé ouvert ? ».
- **Visuel suggéré** : Muraille stylisée d'un réseau avec des portes numérotées, certaines entrouvertes, scannées par des faisceaux de projecteurs.
  - **alt-text** : Muraille de forteresse numérique aux portes numérotées balayées par des projecteurs symbolisant les scanners.
- **Élément interactif** : 📊 Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — Les couches : OSI & TCP/IP
- **Type** : schéma
- **Points clés (bullets)** :
  - OSI : 7 couches théoriques · TCP/IP : 4 couches pratiques.
  - Les données s'**encapsulent** en descendant les couches.
  - Analogie postale : la lettre → le recommandé → l'adresse → le coursier → le camion.
- **Notes orateur** : Dérouler l'analogie postale complète : le contenu (couche application), recommandé avec accusé vs courrier simple (TCP vs UDP), l'adresse sur l'enveloppe (IP), le coursier du bâtiment (MAC), le signal physique (câble/fibre). Chaque couche ajoute son en-tête — c'est l'encapsulation.
- **Visuel suggéré** : Colonnes OSI et TCP/IP côte à côte, avec en parallèle les étapes de l'envoi d'une lettre postale.
  - **alt-text** : Comparaison visuelle des couches OSI et TCP/IP alignées avec les étapes d'un envoi postal.

---

### Slide 5 — À chaque couche, ses attaques et ses défenses
- **Type** : tableau
- **Points clés (bullets)** :
  - Couche 2 (MAC) : ARP spoofing → sécurité des ports de commutateurs.
  - Couche 3 (IP) : IP spoofing → pare-feu, ACL.
  - Couche 4 (TCP/UDP) : SYN flood → pare-feu à états.
  - Couche 7 (Application) : injections → WAF, chiffrement TLS.
- **Notes orateur** : Question rhétorique : pourquoi un modèle en couches aide-t-il le défenseur ? Parce que diagnostiquer la couche, c'est choisir la défense — rappel du DDoS de B03 : une saturation de bande passante (couches 3-4) et un épuisement applicatif (couche 7) ne se contrent pas de la même façon.
- **Visuel suggéré** : Tableau à trois colonnes « Couche → Attaque → Défense » avec un code couleur par couche.
  - **alt-text** : Tableau associant chaque couche réseau à son attaque typique et à sa défense adaptée.

---

### Slide 6 — Les protocoles à connaître
- **Type** : contenu
- **Points clés (bullets)** :
  - **DNS (53)** : l'annuaire d'Internet — détournable en tunnel d'exfiltration.
  - **DHCP** : la configuration automatique — attention au serveur pirate.
  - **ARP** : IP → MAC en local — l'empoisonnement ARP intercepte le trafic.
  - **ICMP** : le diagnostic (`ping`) — aussi un outil de cartographie pour l'attaquant.
- **Notes orateur** : Le paradoxe du DNS : le protocole le plus banal du réseau est un canal d'exfiltration favori, car le port 53 sort presque toujours (tunneling DNS). L'ARP illustre la couche 2 : l'attaque ne quitte jamais le réseau local. L'ICMP montre que même un outil de diagnostic renseigne l'attaquant (ping sweeps).
- **Visuel suggéré** : Quatre vignettes iconographiques : annuaire (DNS), distributeur de tickets (DHCP), badge local (ARP), stéthoscope (ICMP).
  - **alt-text** : Quatre vignettes illustrant les rôles du DNS, du DHCP, d'ARP et d'ICMP dans un réseau.

---

### Slide 7 — Les ports : des portes numérotées
- **Type** : schéma
- **Points clés (bullets)** :
  - **22** SSH · **53** DNS · **80** HTTP (en clair !) · **443** HTTPS · **3389** RDP.
  - Ports 0-1023 : réservés aux services standard (IANA).
  - Règle n°1 : **fermer tout port non utilisé**.
- **Notes orateur** : Chaque service écoute sur une porte numérotée. Le 80 transporte du web NON chiffré — à proscrire pour toute donnée sensible. Le 3389 (RDP) est le chouchou des rançongiciels. Relance chat : « sans regarder vos notes : le 443, c'est quoi ? Et le 22 ? » — corriger en direct.
- **Visuel suggéré** : Façade de bâtiment avec des portes numérotées 22, 53, 80, 443, 3389, certaines verrouillées, d'autres ouvertes.
  - **alt-text** : Façade symbolique d'un serveur avec des portes numérotées représentant les ports réseau standards.
- **Élément interactif** : 💬 Chat — quiz éclair d'association port/service.

---

### Slide 8 — Lire une adresse IP et un en-tête de paquet
- **Type** : schéma
- **Points clés (bullets)** :
  - IPv4 = 32 bits : la **rue** (réseau) + le **numéro de maison** (hôte), séparés par le masque.
  - En-tête : IP source / IP destination · protocole (TCP/UDP) · **TTL**.
  - TTL : -1 à chaque routeur, destruction à 0 — l'anti-boucle d'Internet.
- **Notes orateur** : Pourquoi un défenseur lit-il des en-têtes toute la journée ? Une IP interne qui parle à une IP inconnue à l'étranger, un port de destination inhabituel, un volume anormal : tout signal de détection part de là. Le TTL sera visible dans le `ping` du travail en autonomie.
- **Visuel suggéré** : Enveloppe postale annotée : expéditeur (IP source), destinataire (IP destination), timbre-compteur (TTL), mention recommandé (TCP).
  - **alt-text** : Enveloppe postale annotée dont les champs correspondent aux éléments d'un en-tête de paquet IP.

---

### Slide 9 — Activité : L'analyste de paquets
- **Type** : activité (sondages)
- **Points clés (bullets)** :
  - Deux captures réelles simplifiées, affichées à l'écran.
  - 📊 **Sondages n°2, 3, 4** : quel service ? quelle anomalie ? quel comportement ?
  - Lisez couche par couche : MAC → IP → port → contenu.
- **Notes orateur** : Afficher la capture A, 30 s de lecture silencieuse, puis sondages n°2 (port 53 UDP = DNS) et n°3 (domaine à rallonge = hameçonnage — le mot « secure » n'a aucune valeur). Puis capture B, sondage n°4 (45 tentatives RDP en 10 s = force brute — et l'origine est une IP INTERNE : mouvement latéral, teaser du cas TV5). Débriefs complets dans le support.
- **Visuel suggéré** : Les captures textuelles affichées en police à chasse fixe sur fond sombre, une couche surlignée à la fois.
  - **alt-text** : Capture de trame réseau affichée en console avec les couches successivement mises en évidence.
- **Élément interactif** : 📊 Sondages Livestorm n°2 à 4 — analyse collective par votes.

---

### Slide 10 — Le paysage en chiffres
- **Type** : chiffres clés
- **Points clés (bullets)** :
  - **Équipements de bordure** : parmi les vecteurs d'intrusion privilégiés (ANSSI 2024).
  - **Plusieurs milliards** de tentatives de force brute RDP sur la seule année 2020 (Kaspersky).
  - **~5 M€** la première année : la reconstruction du réseau de TV5 Monde (2015).
- **Notes orateur** : La capture B n'était pas un exercice théorique : le RDP exposé est l'une des attaques les plus massives du monde réel, dopée par le télétravail. Et un réseau mal conçu ne coûte rien... jusqu'au jour où il faut le reconstruire entièrement — transition vers l'affaire TV5 Monde.
- **Visuel suggéré** : Trois grands chiffres en typographie XXL avec leurs sources et années en petit.
  - **alt-text** : Trois statistiques géantes sur les intrusions réseau avec leurs sources.

---

### Slide 11 — Affaire : TV5 Monde (2015)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - 8 avril 2015 : **douze chaînes à l'écran noir**.
  - Entrée par un accès **prestataire**, des semaines de reconnaissance.
  - Un réseau « à plat » : du point d'entrée au cœur de la diffusion.
  - Sauvée par le **débranchement** — reconstruite avec l'ANSSI (~5 M€ la 1ʳᵉ année).
- **Notes orateur** : Raconter : la revendication « CyberCaliphate », l'enquête orientant vers APT28 (rappel B02 : les fausses bannières) ; la cartographie patiente du réseau avant le sabotage des équipements de diffusion ; les techniciens qui débranchent dans la nuit — parfois la couche physique est la dernière défense ; et le détail resté célèbre : les mots de passe sur post-it visibles dans un reportage tourné dans les locaux. La leçon — cloisonner pour que l'intrusion ne se propage pas — c'est la session B06. Relance chat : « quel détail vous marque le plus ? »
- **Visuel suggéré** : Mire d'écran noir de télévision avec le plan schématique d'un réseau à plat traversé par un chemin d'intrusion rouge.
  - **alt-text** : Écran de télévision noir devant un schéma de réseau non segmenté traversé par un tracé d'intrusion rouge.
- **Élément interactif** : 💬 Chat — réactions au cas TV5 Monde.

---

### Slide 12 — Et chez vous ? L'inventaire de l'exposition
- **Type** : sondage (opinion)
- **Points clés (bullets)** :
  - 📊 **Sondage n°5** : sauriez-vous dire quels services sont exposés sur Internet chez vous ?
  - A) Oui, inventaire tenu — B) Partiellement — C) Aucune idée.
- **Notes orateur** : Sondage d'opinion : on ne défend pas ce qu'on ne connaît pas — la cartographie de sa surface exposée est la première action (les attaquants la font déjà pour vous). Réponse C normale à ce stade : l'atelier B08 la fera construire. Enchaîner sur le mini-scénario du RDP prestataire : « tapez A, B ou C » (réponse B — VPN/bastion + MFA ; C = sécurité par l'obscurité, balayée en secondes de scan).
- **Visuel suggéré** : Carte radar circulaire avec des points de services exposés, certains identifiés, d'autres marqués d'un point d'interrogation.
  - **alt-text** : Radar de cartographie réseau montrant des services exposés identifiés et inconnus.
- **Élément interactif** : 📊 Sondage Livestorm n°5 (opinion) puis 🤔 mini-scénario en chat (A/B/C).

---

### Slide 13 — Quiz de validation
- **Type** : quiz (sondages)
- **Points clés (bullets)** :
  - 📊 **Sondage n°6** : le rôle du DNS ?
  - 📊 **Sondage n°7** : la différence TCP / UDP ?
  - 📊 **Sondage n°8** : à quoi sert le TTL ?
- **Notes orateur** : Lancer les trois sondages à la suite (~2 min chacun), débriefs scriptés dans le support : le piège du n°6 est le DHCP ; pour le n°7, le chiffrement n'a rien à voir avec TCP/UDP — il arrive au-dessus (TLS, teaser B07) ; le TTL est le compteur de sauts, visible dans le `ping` du devoir. Si le temps le permet, enchaîner sur le bonus n°9 (le mot de passe en clair).
- **Visuel suggéré** : Trois cartes de quiz numérotées 6, 7, 8 avec l'icône de sondage Livestorm.
  - **alt-text** : Trois cartes de questions de quiz numérotées, associées à des sondages en direct.
- **Élément interactif** : 📊 Sondages Livestorm n°6 à 8 (+ n°9 en tampon).

---

### Slide 14 — Synthèse & prochaine session
- **Type** : récap
- **Points clés (bullets)** :
  - Des couches — à chacune ses attaques et ses défenses.
  - Des ports — des portes à inventorier et à fermer.
  - Des paquets — que vous savez désormais lire.
  - Self-paced : SkillsBuild *« Network Security - Part 1 »* + `ping cyber.gouv.fr` + inventaire Wi-Fi domestique.
  - Prochaine session — B06 : Défenses réseau (pare-feux, DMZ, segmentation).
- **Notes orateur** : Faire écrire dans le chat UN mot retenu, en lire 4-5. Rappeler le triple devoir (cours, ping avec lecture du TTL, inventaire des appareils du Wi-Fi domestique — préparation directe de B06). Teaser B06 : « on construit les murailles — pare-feux, DMZ, segmentation — et l'histoire d'un géant américain de la distribution piraté via... son prestataire de chauffage. » Terminer à l'heure exacte.
- **Visuel suggéré** : Récapitulatif en trois vignettes (couches, ports, paquets) et un panneau « B06 » fléché.
  - **alt-text** : Synthèse en trois vignettes des thèmes de la session avec un panneau indiquant la prochaine session B06.
- **Élément interactif** : Chat de clôture — « un mot que vous retenez ».
