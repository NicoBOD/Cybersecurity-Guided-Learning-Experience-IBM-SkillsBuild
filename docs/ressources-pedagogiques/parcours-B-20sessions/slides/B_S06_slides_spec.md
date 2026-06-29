# Spécifications des slides — Session B06 : Défenses réseau et segmentation
Parcours : B 20 sessions  |  Module : B — Sécurité Réseau  |  Format : Spécifications Markdown

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Défenses réseau et segmentation
  - Filtrer, surveiller et cloisonner les infrastructures de communication
  - Parcours B — Session B06
- **Notes orateur** : Bonjour à tous. Après avoir étudié les bases des réseaux, nous allons aujourd'hui voir comment concevoir une architecture réseau hautement sécurisée. Nous allons découvrir les pare-feux, les systèmes d'analyse et de détection d'intrusions, et surtout comment cloisonner notre réseau pour éviter qu'une faille mineure ne paralyse toute l'entreprise.
- **Visuel suggéré** : Représentation graphique d'une forteresse médiévale moderne avec plusieurs remparts concentriques, chacun matérialisant une zone réseau séparée par des douves lumineuses vertes.
  - **alt-text** : Graphisme 3D abstrait représentant des remparts et des ponts-levis lumineux pour illustrer le concept de défense en profondeur.
- **Élément interactif** : Question orale rapide : "Selon vous, quelle est la première chose que fait un pirate informatique après avoir infecté un ordinateur du secrétariat ?"

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Expliquer le fonctionnement et comparer les générations de pare-feux (sans état, à état, NGFW).
  - Différencier le rôle et le positionnement d'un IDS (détection) et d'un IPS (prévention).
  - Concevoir et modéliser une architecture réseau segmentée (WAN, LAN, DMZ) avec sa table de règles de filtrage.
  - Sommaire : Les Pare-feux (20 min), IDS/IPS (20 min), Architecture & DMZ (20 min), Exercice table de filtrage (20 min), Quiz (10 min).
- **Notes orateur** : Nous commencerons par l'évolution des pare-feux. Puis nous verrons les systèmes de détection d'intrusions avant d'aborder le concept crucial de DMZ et de mettre en œuvre vos compétences lors d'un atelier pratique d'écriture de règles de sécurité.
- **Visuel suggéré** : Colonnes structurées séparant les compétences visées à gauche et l'agenda minuté de la session synchrone à droite.
  - **alt-text** : Tableau d'agenda minuté présentant le déroulement pas à pas de la séance de 90 minutes.

---

### Slide 3 — Les Pare-feux : Le principe du Default Deny
- **Type** : contenu
- **Points clés (bullets)** :
  - Dispositif filtrant les flux réseau entrants/sortants selon des règles.
  - **Règle d'or : Default Deny (Rejet par défaut)**.
  - Tout ce qui n'est pas explicitement autorisé est bloqué.
  - Minimise l'exposition aux attaques non identifiées.
- **Notes orateur** : Le pare-feu est le gardien de notre réseau. Pour être efficace, il doit obéir à la politique du "Default Deny" : on ferme tout par défaut et on n'ouvre que ce qui est strictement nécessaire pour le travail des utilisateurs. Si une communication n'est pas explicitement listée dans nos règles, elle est rejetée sans ménagement.
- **Visuel suggéré** : Un mur pare-feu virtuel composé de briques lumineuses vertes bloquant des flux réseau rouges (non autorisés) et laissant passer uniquement un flux bleu (autorisé).
  - **alt-text** : Mur de briques technologiques bloquant et filtrant des flux de données de différentes couleurs.

---

### Slide 4 — Génération 1 : Le filtrage sans état (Stateless)
- **Type** : contenu
- **Points clés (bullets)** :
  - Examine chaque paquet indépendamment, sans historique.
  - Filtre selon : IP Source/Dest et Port Source/Dest.
  - Très rapide, mais incapable de comprendre le contexte.
  - *Analogie* : Un portier de discothèque qui vérifie votre identité à l'entrée, mais oublie votre visage dès que vous avez franchi le seuil.
- **Notes orateur** : La première génération de pare-feu est le filtrage sans état ou "Stateless". Il traite chaque paquet de façon isolée. C'est rapide, mais il est facile de le tromper en imitant des paquets de réponse, car il n'a aucune mémoire des connexions passées. C'est comme un portier qui relirait sa liste à chaque fois que vous faites un pas.
- **Visuel suggéré** : Illustration d'un portier de boîte de nuit lisant une liste papier d'invités devant un ordinateur qui envoie des paquets isolés.
  - **alt-text** : Illustration humoristique représentant un portier vérifiant une liste à chaque paquet réseau.

---

### Slide 5 — Génération 2 & 3 : Stateful et NGFW
- **Type** : schéma
- **Points clés (bullets)** :
  - **Filtrage à état (Stateful)** :
    - Suit l'état des connexions dans une table dynamique.
    - Se rappelle qu'une machine interne a initié la connexion et laisse passer le retour.
  - **Next-Generation Firewall (NGFW)** :
    - *Deep Packet Inspection (DPI)* : Analyse le contenu réel des paquets.
    - Reconnaît les applications (distingue Dropbox du protocole HTTPS brut).
    - Intègre des modules d'antivirus de flux et de filtrage d'URL.
- **Notes orateur** : Le pare-feu "Stateful" garde en mémoire le contexte : si vous ouvrez un site web, le pare-feu s'en souvient et laisse le site vous répondre. Le NGFW va encore plus loin : il ouvre les paquets pour analyser leur contenu. Si vous téléchargez un virus sur le port HTTPS 443 autorisé, le NGFW va l'intercepter grâce à son antivirus de flux intégré.
- **Visuel suggéré** : Schéma montrant un douanier ouvrant une valise (DPI) à côté d'une table d'états réseau (mémoire des flux).
  - **alt-text** : Comparatif visuel de l'inspection de paquets basique (Stateful) vs inspection profonde applicative (NGFW).

---

### Slide 6 — WAF (Web Application Firewall) : Spécialiste du Web
- **Type** : contenu
- **Points clés (bullets)** :
  - Pare-feu spécialisé placé devant les serveurs web.
  - Analyse le protocole HTTP/HTTPS en profondeur.
  - Protège contre les attaques de niveau applicatif (ex. OWASP Top 10).
  - Bloque les tentatives d'injections SQL et de Cross-Site Scripting (XSS).
- **Notes orateur** : Le WAF est un pare-feu ultra-spécialisé pour le web. Contrairement à un pare-feu réseau classique qui se contente de dire "le port 443 est ouvert", le WAF analyse la requête HTTP elle-même. Si un utilisateur essaie de taper du code malveillant dans un formulaire de connexion pour pirater la base de données, le WAF le détecte et bloque la requête.
- **Visuel suggéré** : Un bouclier positionné juste devant un serveur web, interceptant des requêtes malveillantes marquées d'un symbole d'injection SQL.
  - **alt-text** : Schéma fonctionnel montrant le WAF filtrant les attaques applicatives web avant qu'elles n'atteignent le serveur de production.

---

### Slide 7 — IDS et IPS : Surveiller et Intervenir
- **Type** : contenu
- **Points clés (bullets)** :
  - **IDS (Intrusion Detection System)** :
    - Système passif (écoute une copie du réseau).
    - Repère les signatures suspectes et génère des alertes.
    - *Ne bloque pas le trafic*.
  - **IPS (Intrusion Prevention System)** :
    - Système actif positionné en coupure (*inline*).
    - Analyse en temps réel et détruit les paquets malveillants immédiatement.
- **Notes orateur** : Les pare-feux contrôlent les accès, mais ils ne voient pas tout. L'IDS et l'IPS analysent le trafic à la recherche de signatures d'attaques. L'IDS agit comme une alarme de maison : il sonne mais n'arrête pas le cambrioleur. L'IPS est un gardien actif : il est sur le passage et neutralise directement l'agresseur en détruisant les paquets malveillants.
- **Visuel suggéré** : Un système d'alarme de sécurité (pour l'IDS) à côté d'un agent de sécurité physique interceptant activement un intrus (pour l'IPS).
  - **alt-text** : Comparaison métaphorique entre la surveillance passive (alarme/IDS) et l'intervention active (gardien/IPS).

---

### Slide 8 — Segmentation réseau et concept de DMZ
- **Type** : schéma
- **Points clés (bullets)** :
  - Empêche les mouvements latéraux des attaquants.
  - Division du réseau en trois zones principales :
    - **WAN** : Internet public (zone non sûre).
    - **LAN** : Réseau local interne (ordinateurs des salariés, données sensibles).
    - **DMZ (Zone Démilitarisée)** : Zone tampon exposée hébergeant les serveurs publics (Web, e-mail).
- **Notes orateur** : Si tout votre réseau est à plat, le piratage d'une seule machine de bureau donne accès à vos serveurs les plus critiques. C'est pourquoi nous segmentons le réseau. Nous isolons les serveurs web publics dans une DMZ, une zone tampon. Ainsi, si le serveur web est piraté, l'attaquant est confiné dans la DMZ et ne peut pas atteindre le réseau interne.
- **Visuel suggéré** : Schéma d'architecture réseau à trois branches connectées à un pare-feu central : Internet (WAN), le réseau interne (LAN) et la zone tampon (DMZ).
  - **alt-text** : Schéma d'architecture réseau segmenté présentant le WAN, le LAN et la DMZ séparés par un pare-feu.

---

### Slide 9 — La règle d'or de la DMZ
- **Type** : contenu
- **Points clés (bullets)** :
  - Les machines de la DMZ sont exposées sur Internet et considérées comme vulnérables par défaut.
  - **Règle absolue : Interdire toute connexion initiée depuis la DMZ vers le LAN**.
  - Si un serveur en DMZ est compromis, le pirate ne peut pas s'en servir de rebond pour attaquer les ordinateurs internes.
  - Les données nécessaires au LAN doivent être poussées par le LAN ou récupérées de façon contrôlée.
- **Notes orateur** : C'est la règle d'or la plus importante en architecture réseau : une machine située en DMZ ne doit jamais pouvoir initier une connexion vers le LAN. Si vous devez mettre à jour une base de données interne, c'est le LAN qui doit initier la connexion pour interroger la DMZ, jamais l'inverse. C'est ce qui garantit l'étanchéité de notre sécurité.
- **Visuel suggéré** : Schéma montrant un sens interdit rouge et une flèche bloquée partant de la DMZ vers le LAN, contrastant avec une flèche verte autorisée du LAN vers la DMZ.
  - **alt-text** : Représentation graphique du flux bloqué DMZ $\rightarrow$ LAN et du flux autorisé LAN $\rightarrow$ DMZ.

---

### Slide 10 — Activité pratique : Configuration pare-feu de "EcoLog"
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **Scénario** : L'entreprise EcoLog doit configurer les règles de son pare-feu.
  - **Zones** : LAN (`192.168.10.0/24`), DMZ (`192.168.20.5`), WAN (`Any`).
  - **Objectifs** :
    - Autoriser les visites HTTPS externes sur la DMZ.
    - Permettre la navigation web sécurisée du LAN vers le WAN.
    - Autoriser l'administration SSH du LAN vers la DMZ.
    - Bloquer tout le reste (Default Deny).
- **Notes orateur** : Place à la pratique. Vous allez concevoir la table de règles pare-feu de l'entreprise EcoLog. Vous devez définir précisément les adresses sources, destinations, les ports correspondants et l'action à mener (Autoriser ou Bloquer). Attention à bien ordonner vos règles et à finir par le blocage par défaut.
- **Visuel suggéré** : Tableau vide présentant les colonnes : N° Règle, Zone Source, IP Source, Zone Dest, IP Dest, Port/Service, Action.
  - **alt-text** : Tableau d'exercice à remplir pour la création de règles de sécurité de pare-feu.
- **Élément interactif** : Remplissage collaboratif de la table de filtrage en sous-groupes de travail.

---

### Slide 11 — Quiz de validation
- **Type** : quiz
- **Points clés (bullets)** :
  - 1. Quelle technologie de pare-feu inspecte le contenu applicatif des paquets (DPI) ?
  - 2. Quelle est la différence majeure entre un IDS et un IPS ?
  - 3. Un serveur en DMZ peut-il initier une connexion vers un poste du LAN ?
- **Notes orateur** : Passons au quiz pour valider vos acquis. Répondez sur votre application. Pensez bien à la différence fondamentale d'action entre l'IDS et l'IPS et aux règles de cloisonnement de la DMZ.
- **Visuel suggéré** : QR Code d'accès au vote synchrone à gauche, questions à choix multiples à droite.
  - **alt-text** : QR Code de vote pour la validation des compétences réseau.
- **Élément interactif** : Vote synchrone en direct avec affichage des résultats.

---

### Slide 12 — Conclusion & Travail en autonomie
- **Type** : récap
- **Points clés (bullets)** :
  - **Résumé** : Pare-feux (Default Deny, à états, NGFW, WAF), surveillance active (IPS) ou passive (IDS) et cloisonnement par DMZ.
  - **Travail personnel** : Suivre le cours IBM SkillsBuild *"Network Security - Part 2"* (~1h30).
  - **Exercice maison** : Modéliser le schéma d'EcoLog avec un outil de dessin (Ex : draw.io) en y incluant le pare-feu.
  - Prochaine session : *Introduction à la détection d'intrusions et analyse de logs (B07)*.
- **Notes orateur** : Nous avons posé les briques de la défense réseau. Pour consolider ces connaissances, suivez le module de cours IBM SkillsBuild et dessinez le schéma réseau d'EcoLog chez vous. La semaine prochaine, nous verrons comment mettre cela en œuvre concrètement en installant un pare-feu et en analysant des paquets. Merci et à bientôt !
- **Visuel suggéré** : Exemple de schéma réseau propre dessiné sur un tableau blanc virtuel avec des icônes d'équipements informatiques.
  - **alt-text** : Capture d'un schéma d'architecture réseau DMZ/LAN/WAN propre et structuré.
