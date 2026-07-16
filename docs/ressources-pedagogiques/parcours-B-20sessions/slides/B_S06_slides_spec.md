# Spécifications des slides — Session B06 : Défenses réseau
Parcours : B 20 sessions  |  Module : B — Systèmes & réseaux  |  Format : Spécifications Markdown

> **Principe** : le texte affiché reste minimal (mots-clés, chiffres, schémas) ; le contenu riche est dans les notes orateur et le [plan de séance minuté](../plans-de-seance/B_S06_plan.md). Toutes les interactions passent par les sondages et le chat Livestorm.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Défenses réseau
  - Filtrer, surveiller, cloisonner
  - Parcours B — Session B06
- **Notes orateur** : Accueillir : la semaine dernière on a appris à lire le trafic, ce soir on apprend à le filtrer. Retour self-paced : « combien d'appareils avez-vous comptés sur votre Wi-Fi domestique ? Le chiffre dans le chat ! » Lire 4-5 chiffres, souligner la surprise (TV, imprimante, ampoules...) — « retenez ce sentiment, on y revient avec une histoire d'aquarium. » Rappel express de B05 (couches, ports, TV5 Monde).
- **Visuel suggéré** : Forteresse moderne avec plusieurs remparts concentriques, chacun matérialisant une zone réseau.
  - **alt-text** : Représentation d'une forteresse à remparts concentriques illustrant la défense en profondeur d'un réseau.
- **Élément interactif** : 💬 Chat d'accueil — le nombre d'appareils du Wi-Fi domestique.

---

### Slide 2 — Objectifs & agenda
- **Type** : contenu
- **Points clés (bullets)** :
  - Comparer les générations de pare-feux (stateless, stateful, NGFW).
  - Différencier IDS (détecter) et IPS (bloquer).
  - Concevoir une architecture segmentée (WAN / LAN / DMZ) et sa table de filtrage.
  - Agenda : pare-feux → IDS/IPS → segmentation → table de filtrage EcoLog → Target & le thermomètre → quiz.
- **Notes orateur** : Ce soir on construit les murailles : le pare-feu qui applique la loi, les sentinelles qui surveillent, et les zones étanches qui confinent. Point d'orgue : vous écrirez ensemble, par sondages, une vraie table de filtrage — puis deux histoires vraies montreront ce que coûte son absence.
- **Visuel suggéré** : Deux colonnes présentant les objectifs et l'agenda de la séance.
  - **alt-text** : Tableau présentant les objectifs d'apprentissage et les étapes de la session.

---

### Slide 3 — Brise-glace : l'entrée improbable
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **Sondage n°1** : Target 2013, 40 millions de cartes volées — par où sont-ils entrés ?
  - A) Une faille du site web — B) Un prestataire de chauffage — C) Un employé corrompu
- **Notes orateur** : Lancer le sondage n°1 (60-90 s). Réponse B : un petit prestataire de chauffage/climatisation hameçonné, dont l'accès au portail fournisseurs a mené jusqu'aux caisses de 1 800 magasins. Comment passe-t-on d'un portail de facturation aux caisses ? Quand rien ne les sépare. L'histoire complète arrive en seconde partie.
- **Visuel suggéré** : Fourgon de chauffagiste stylisé garé devant un immense magasin, relié en pointillés rouges à une caisse enregistreuse.
  - **alt-text** : Camionnette de prestataire de chauffage reliée par un tracé d'intrusion à une caisse enregistreuse de supermarché.
- **Élément interactif** : 📊 Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — Le pare-feu : Default Deny
- **Type** : contenu
- **Points clés (bullets)** :
  - Filtrer les flux entrants ET sortants selon des règles.
  - **Default Deny** : tout ce qui n'est pas explicitement autorisé est interdit.
  - On autorise des **besoins**, on ne bloque pas des menaces.
- **Notes orateur** : Le principe fondateur, à marteler : par défaut, tout est fermé. La table de règles n'est pas une liste noire de menaces (impossible à maintenir) mais une liste blanche de besoins métier justifiés. C'est une philosophie de sécurité, pas un détail technique — et la dernière ligne de toute table de filtrage.
- **Visuel suggéré** : Grande porte fermée par défaut avec une petite liste blanche de laissez-passer à côté.
  - **alt-text** : Porte massive fermée accompagnée d'une courte liste de laissez-passer symbolisant la politique de rejet par défaut.

---

### Slide 5 — Trois générations de portiers
- **Type** : schéma
- **Points clés (bullets)** :
  - **Stateless** : vérifie la liste d'invités... et oublie votre visage.
  - **Stateful** : le bracelet tamponné — se souvient des connexions initiées.
  - **NGFW** : l'agent des douanes — passeport, trajet, et **ouverture de la valise (DPI)**.
  - (+ le **WAF**, spécialiste posté devant les serveurs web.)
- **Notes orateur** : Dérouler les trois analogies. Le stateful bloque tout paquet entrant non sollicité — relance chat : « le portier stateful laisse-t-il entrer un paquet qui ne répond à aucune connexion sortante ? Oui ou non. » (Non — c'est sa valeur ajoutée.) Le NGFW reconnaît l'application réelle même sur le port 443 : un tunnel malveillant en HTTPS ne lui échappe pas. Le WAF cible les attaques applicatives (injections SQL de B03, XSS).
- **Visuel suggéré** : Trois portiers côte à côte : liste papier, bracelet tamponné, scanner à bagages.
  - **alt-text** : Trois personnages de portiers illustrant les générations de pare-feux, du filtrage simple à l'inspection profonde.
- **Élément interactif** : 💬 Chat — quiz éclair sur le portier stateful.

---

### Slide 6 — IDS & IPS : les sentinelles
- **Type** : schéma
- **Points clés (bullets)** :
  - **IDS** : passif, sur copie du trafic — détecte et **alerte**.
  - **IPS** : actif, sur le chemin — **bloque** en temps réel.
  - Le compromis : le passif n'arrête rien ; l'actif peut couper du trafic légitime (faux positif).
- **Notes orateur** : Pourquoi ces sentinelles ? Parce qu'un flux AUTORISÉ peut transporter une attaque. L'IDS écoute un port miroir et ne casse jamais rien ; l'IPS inline détruit le paquet malveillant, mais un faux positif sur un système critique fait des dégâts — d'où la pratique : démarrer en détection, activer la prévention règle par règle. Question rhétorique à garder pour Target : « une alerte que personne ne lit, ça vaut combien ? »
- **Visuel suggéré** : Schéma de flux réseau : l'IDS en dérivation avec une loupe, l'IPS sur le chemin avec un bouclier.
  - **alt-text** : Schéma montrant un IDS placé en dérivation du flux réseau et un IPS placé en coupure sur le chemin.

---

### Slide 7 — Segmentation : WAN, LAN, DMZ
- **Type** : schéma
- **Points clés (bullets)** :
  - **WAN** : Internet, non sûr · **LAN** : l'interne · **DMZ** : la zone tampon exposée.
  - **Règle d'or : aucun flux initié DMZ → LAN.**
  - La DMZ est conçue pour être « perdable ».
  - VLAN : la segmentation à l'intérieur du LAN (bureautique / production / IoT / invités).
- **Notes orateur** : L'ennemi : le mouvement latéral — rappel TV5 Monde et son réseau à plat. Dérouler l'analogie de l'aéroport (support) : la DMZ est le hall public, le LAN la zone à badges. Question rhétorique : chez Target, dans quelle zone aurait dû vivre le portail fournisseurs ? Une zone étanche, sans aucun chemin vers les caisses.
- **Visuel suggéré** : Schéma d'architecture : nuage Internet, pare-feu central, DMZ avec serveur web, LAN avec postes — flux autorisés en vert, flux DMZ vers LAN barré en rouge.
  - **alt-text** : Schéma d'architecture réseau montrant les zones WAN, DMZ et LAN avec le flux DMZ vers LAN interdit.

---

### Slide 8 — Activité : la table de filtrage d'EcoLog
- **Type** : activité (sondages)
- **Points clés (bullets)** :
  - LAN employés `192.168.10.0/24` · DMZ serveur web `192.168.20.5` · WAN.
  - Trois besoins métier → trois règles à voter.
  - 📊 **Sondages n°2, 3, 4** : clients → site ? mises à jour ? administration SSH ?
- **Notes orateur** : « Le pare-feu d'EcoLog vient d'être branché : TOUT est bloqué. Ouvrons uniquement le justifié. » Lancer les trois sondages avec débrief entre chaque : la question clé est QUI INITIE la connexion. Pièges : ouvrir le LAN au monde (n°2-B), violer la règle d'or DMZ→LAN (n°3-C), exposer SSH à Internet (n°4-C). Conclure en remplissant la table complète à l'écran, avec la ligne finale Any→Any : Deny — « c'est elle qui transforme une liste de règles en politique de sécurité. »
- **Visuel suggéré** : Table de filtrage vide à cinq lignes projetée, remplie ligne par ligne au fil des votes.
  - **alt-text** : Tableau de règles de pare-feu à compléter progressivement pendant l'activité collective.
- **Élément interactif** : 📊 Sondages Livestorm n°2 à 4 — construction collective de la table.

---

### Slide 9 — Le paysage en chiffres
- **Type** : chiffres clés
- **Points clés (bullets)** :
  - **40 M de cartes** + ~70 M de dossiers clients : Target, 2013.
  - **> 200 M$** de coûts cumulés · accord de 18,5 M$ avec 47 États (2017) · démission du PDG.
  - **~10 Go** exfiltrés via un thermomètre d'aquarium connecté (Darktrace, 2018).
- **Notes orateur** : Trois lectures : le maillon faible peut être un fournisseur (le pare-feu n'y peut rien — l'accès est légitime) ; la segmentation manquante se chiffre en centaines de millions ; et chaque objet connecté est une porte — si rien ne le sépare des données, la porte mène au coffre. Transition : les deux histoires en détail.
- **Visuel suggéré** : Trois grands chiffres en typographie XXL avec leurs sources et années en petit.
  - **alt-text** : Trois statistiques géantes sur les défaillances de segmentation réseau avec leurs sources.

---

### Slide 10 — Affaire n°1 : Target (2013)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Un prestataire de chauffage hameçonné → le portail fournisseurs.
  - Mouvement latéral → les **caisses de 1 800 magasins**, à Noël.
  - Les alertes de détection : générées... **mais pas traitées**.
- **Notes orateur** : Dérouler la chaîne complète : identifiants du prestataire → portail de facturation → cheminement interne → malware sur les caisses lisant les cartes en mémoire au moment du paiement. Le détail accablant : les outils avaient détecté, personne n'a agi à temps — une alerte non traitée ne vaut rien. Conclusion : avec une vraie segmentation (portail dans une zone étanche, Default Deny vers le reste), l'attaque s'arrêtait à la facturation.
- **Visuel suggéré** : Chaîne d'intrusion en cinq maillons illustrés, du fourgon du prestataire à la caisse enregistreuse, avec une cloison manquante en évidence.
  - **alt-text** : Chaîne d'intrusion illustrée depuis le prestataire hameçonné jusqu'aux caisses enregistreuses, soulignant l'absence de cloisonnement.

---

### Slide 11 — Affaire n°2 : le casino et le thermomètre (2017)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Un thermomètre d'aquarium connecté... sur le réseau métier.
  - Tremplin vers la base des clients VIP.
  - **~10 Go exfiltrés — par le thermomètre** (rapporté par Darktrace).
- **Notes orateur** : L'objet IoT anodin comme porte d'entrée : la question n'est pas « qui pirate un thermomètre ? » mais « une fois compromis, que peut-il JOINDRE ? ». Boucler avec l'inventaire Wi-Fi du début : votre téléviseur, vos ampoules — que peuvent-ils joindre chez vous ? Un VLAN IoT étanche transforme l'anecdote en non-événement. Relance chat : « quel détail vous marque le plus ? »
- **Visuel suggéré** : Aquarium de hall d'hôtel avec un thermomètre connecté relié en pointillés rouges à une base de données de coffre-fort.
  - **alt-text** : Aquarium décoratif dont le thermomètre connecté est relié par un tracé d'intrusion à une base de données sécurisée.
- **Élément interactif** : 💬 Chat — réactions aux deux affaires.

---

### Slide 12 — Et chez vous ? La segmentation
- **Type** : sondage (opinion)
- **Points clés (bullets)** :
  - 📊 **Sondage n°5** : le réseau que vous connaissez le mieux est-il segmenté ?
  - A) Zones étanches — B) Un Wi-Fi invité, sans plus — C) Tout à plat / je ne sais pas.
- **Notes orateur** : Sondage d'opinion. B est déjà un vrai progrès — le Wi-Fi invité est la segmentation la plus accessible (la plupart des box la proposent). Pour les C : TV5, Target, le casino — trois histoires, une cause racine. L'atelier B08 fera dessiner votre schéma segmenté. Enchaîner sur le mini-scénario de l'alerte de 2h du matin : « tapez A, B ou C » (réponse B — confiner le poste puis investiguer ; A = l'erreur de Target ; C = le déni de service auto-infligé).
- **Visuel suggéré** : Plan de maison avec des pièces cloisonnées ou ouvertes, symbolisant les niveaux de segmentation.
  - **alt-text** : Plan d'habitation illustrant des réseaux plus ou moins cloisonnés selon les pièces.
- **Élément interactif** : 📊 Sondage Livestorm n°5 (opinion) puis 🤔 mini-scénario en chat (A/B/C).

---

### Slide 13 — Quiz de validation
- **Type** : quiz (sondages)
- **Points clés (bullets)** :
  - 📊 **Sondage n°6** : stateful vs stateless ?
  - 📊 **Sondage n°7** : IDS vs IPS ?
  - 📊 **Sondage n°8** : qu'apporte un NGFW ?
- **Notes orateur** : Lancer les trois sondages à la suite (~2 min chacun), débriefs scriptés dans le support : le bracelet tamponné (mémoire des connexions) ; détecter/alerter vs bloquer en temps réel — et le compromis du faux positif ; l'inspection profonde du contenu, même sur un port autorisé. Rappeler : les défenses s'empilent, elles ne se remplacent pas. Si le temps le permet, enchaîner sur le bonus n°9 (le confinement DMZ).
- **Visuel suggéré** : Trois cartes de quiz numérotées 6, 7, 8 avec l'icône de sondage Livestorm.
  - **alt-text** : Trois cartes de questions de quiz numérotées, associées à des sondages en direct.
- **Élément interactif** : 📊 Sondages Livestorm n°6 à 8 (+ n°9 en tampon).

---

### Slide 14 — Synthèse & prochaine session
- **Type** : récap
- **Points clés (bullets)** :
  - Un pare-feu qui n'autorise que le justifié : **Default Deny**.
  - Des sentinelles : IDS alerte, IPS bloque — encore faut-il traiter les alertes.
  - Des zones étanches : DMZ, VLAN — le mouvement latéral confiné.
  - Self-paced : SkillsBuild *« Network Security - Part 2 »* + schéma draw.io + observer le cadenas TLS.
  - Prochaine session — B07 : Communications sécurisées (TLS, VPN).
- **Notes orateur** : Faire écrire dans le chat UN mot retenu, en lire 4-5. Rappeler le triple devoir (cours, schéma d'architecture en brouillon pour B08, inspection du cadenas TLS du navigateur — préparation directe de B07). Teaser B07 : « vos murailles sont en place — mais qui LIT vos données pendant qu'elles voyagent ? Chiffrement, TLS, VPN — et l'histoire de la petite extension de navigateur qui a forcé le web entier à passer au HTTPS. » Terminer à l'heure exacte.
- **Visuel suggéré** : Récapitulatif en trois vignettes (pare-feu, sentinelles, zones) et un panneau « B07 » fléché.
  - **alt-text** : Synthèse en trois vignettes des thèmes de la session avec un panneau indiquant la prochaine session B07.
- **Élément interactif** : Chat de clôture — « un mot que vous retenez ».
