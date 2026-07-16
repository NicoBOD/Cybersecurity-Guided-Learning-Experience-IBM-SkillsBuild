# Spécifications des slides — Session B07 : Communications sécurisées
Parcours : B 20 sessions  |  Module : B — Systèmes & réseaux  |  Format : Spécifications Markdown

> **Principe** : le texte affiché reste minimal (mots-clés, chiffres, schémas) ; le contenu riche est dans les notes orateur et le [plan de séance minuté](../plans-de-seance/B_S07_plan.md). Toutes les interactions passent par les sondages et le chat Livestorm.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Communications sécurisées
  - Protéger les données qui voyagent : HTTPS, VPN, Wi-Fi
  - Parcours B — Session B07
- **Notes orateur** : Accueillir : les murailles sont construites (B06), mais les données voyagent hors les murs — ce soir on les protège en chemin. Retour self-paced : « qui a cliqué sur le cadenas ? Tapez le nom de l'autorité de certification vue. » (attendu : Let's Encrypt, DigiCert...) « Retenez ces noms — une des histoires de ce soir raconte ce qui arrive quand l'un de ces organismes se fait pirater. »
- **Visuel suggéré** : Ondes Wi-Fi stylisées se transformant en chaînes et cadenas à l'approche d'un ordinateur.
  - **alt-text** : Illustration d'ondes Wi-Fi sécurisées par des verrous de cryptographie autour d'un ordinateur portable.
- **Élément interactif** : 💬 Chat d'accueil — les autorités de certification repérées.

---

### Slide 2 — Objectifs & agenda
- **Type** : contenu
- **Points clés (bullets)** :
  - Expliquer le handshake TLS et le rôle des certificats.
  - Comparer les VPN (IPsec, OpenVPN, WireGuard) selon l'usage.
  - Préconiser le Wi-Fi moderne (WPA3, WPA-Enterprise).
  - Agenda : TLS → VPN → Wi-Fi → mission « 100 consultants » → Firesheep & DigiNotar → quiz.
- **Notes orateur** : Programme : décortiquer ce que le cadenas garantit vraiment (et ce qu'il ne garantit pas), construire les tunnels, sécuriser les ondes — puis une mission de consultant à résoudre par sondages, et deux affaires qui ont changé la confiance du web.
- **Visuel suggéré** : Deux colonnes présentant les objectifs et l'agenda de la séance.
  - **alt-text** : Tableau présentant les objectifs d'apprentissage et les étapes de la session.

---

### Slide 3 — Brise-glace : le web est-il chiffré ?
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **Sondage n°1** : quelle part des pages web est chargée en HTTPS aujourd'hui ?
  - A) ~30 % — B) ~60 % — C) Plus de 90 %
- **Notes orateur** : Lancer le sondage n°1 (60-90 s). Réponse C : plus de 90 % (rapport de transparence Google). Mais au début des années 2010, c'était l'inverse : les sessions circulaient en clair. Ce qui a fait basculer le web ? En bonne partie une petite extension de navigateur créée pour provoquer un scandale — l'histoire arrive en seconde partie.
- **Visuel suggéré** : Frise chronologique 2010 → aujourd'hui avec la proportion de cadenas qui grandit.
  - **alt-text** : Frise temporelle montrant la progression du chiffrement HTTPS sur le web depuis 2010.
- **Élément interactif** : 📊 Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — Le handshake TLS en 4 temps
- **Type** : schéma
- **Points clés (bullets)** :
  - 1. Négociation des algorithmes.
  - 2. **Authentification** : le certificat, garanti par une CA.
  - 3. Échange de la clé de session (asymétrique).
  - 4. Chiffrement rapide du trafic (symétrique).
- **Notes orateur** : L'analogie : HTTP = la carte postale (rappel du `password=Password123` de B05) ; HTTPS = le coffre portatif. Précision : SSL est mort — TLS 1.2 minimum, 1.3 recommandé (ANSSI) ; « certificat SSL » est un abus de langage. Question rhétorique : sans le certificat ? Vous chiffrez peut-être... vers l'attaquant. Option démo : cliquer sur le cadenas d'un site et montrer l'émetteur, la validité, la version.
- **Visuel suggéré** : Diagramme de séquence client-serveur en quatre flèches numérotées, avec un sceau de CA sur l'étape 2.
  - **alt-text** : Diagramme de séquence du handshake TLS entre navigateur et serveur en quatre étapes.
- **Élément interactif** : Démonstration en direct du certificat d'un site (optionnelle).

---

### Slide 5 — Pourquoi deux cryptographies ?
- **Type** : schéma
- **Points clés (bullets)** :
  - **Asymétrique** : échange un secret sans rencontre — mais lente.
  - **Symétrique** : ultra-rapide — mais il faut partager la clé.
  - Le handshake combine : l'asymétrique **livre la clé**, la symétrique **fait le travail**.
- **Notes orateur** : Le point subtil de la session, à ancrer avec l'image du coffret : on utilise le cadenas à clé publique (asymétrique) une seule fois, pour livrer la combinaison ; ensuite tout le monde utilise le coffre à combinaison (symétrique), des milliers de fois plus rapide. C'est la question n°7 du quiz.
- **Visuel suggéré** : Coffret livré par un cadenas doré (asymétrique) contenant une clé de combinaison, puis flux rapide de coffres à combinaison (symétrique).
  - **alt-text** : Illustration du principe hybride : un cadenas asymétrique livre la clé qui ouvre un chiffrement symétrique rapide.

---

### Slide 6 — Les VPN : tunnels chiffrés
- **Type** : schéma
- **Points clés (bullets)** :
  - **Client-to-site** : le télétravailleur → l'entreprise.
  - **Site-to-site** : relier durablement deux sites.
  - Protocoles : **IPsec** (le robuste), **OpenVPN** (le flexible), **WireGuard** (le moderne).
  - ⚠️ La passerelle VPN est un équipement de bordure — ciblé (ANSSI).
- **Notes orateur** : L'analogie : l'autoroute souterraine blindée — personne ne voit qui circule ni ce que transportent les camions. WireGuard excelle en mobilité : léger, économe en batterie, reconnexion instantanée. La mise en garde : la passerelle VPN exposée se maintient à jour et se protège par MFA — sinon le tunnel des employés devient celui des attaquants (rappel B05). Relance chat : « qui utilise un VPN d'entreprise en télétravail ? »
- **Visuel suggéré** : Coupe de terrain montrant un tunnel blindé sous une rue passante, reliant une maison à un immeuble d'entreprise.
  - **alt-text** : Tunnel souterrain sécurisé reliant un domicile à une entreprise sous un réseau public symbolisé par la rue.
- **Élément interactif** : 💬 Chat — usage du VPN en télétravail.

---

### Slide 7 — Wi-Fi : du WEP au WPA3
- **Type** : tableau
- **Points clés (bullets)** :
  - **WEP** : mort — cassé en quelques secondes.
  - **WPA2-PSK** : clé partagée — dictionnaire, faille KRACK.
  - **WPA3** : le standard moderne (échange SAE).
  - **WPA-Enterprise (802.1X)** : identifiants **nominatifs**, serveur RADIUS.
- **Notes orateur** : Le problème physique d'abord : les ondes traversent les murs — l'interception se fait depuis le parking. Dérouler la généalogie. Question rhétorique : pourquoi une clé partagée est-elle un problème en entreprise, même robuste ? Un départ = changer le Wi-Fi de tous ; aucune traçabilité — la réponse complète arrive dans l'activité.
- **Visuel suggéré** : Frise d'évolution des protocoles Wi-Fi avec un code couleur rouge (WEP) → orange (WPA2) → vert (WPA3/Enterprise).
  - **alt-text** : Frise chronologique des protocoles de sécurité Wi-Fi, du WEP obsolète au WPA3 moderne.

---

### Slide 8 — Activité : Mission « 100 consultants nomades »
- **Type** : activité (sondages)
- **Points clés (bullets)** :
  - 100 consultants mobiles · gares, hôtels, sites clients · données confidentielles.
  - Trois décisions à voter :
  - 📊 **Sondage n°2** : le Wi-Fi du siège ? · 📊 **n°3** : l'accès nomade ? · 📊 **n°4** : au café, la première action ?
- **Notes orateur** : Lancer les trois sondages avec débrief entre chaque. N°2 : WPA3-Enterprise — le mot-clé est NOMINATIF (révocation individuelle, traçabilité RADIUS). N°3 : le piège est « HTTPS suffit » — il ne cache ni les métadonnées ni les applications non-web ; WireGuard pour la mobilité. N°4 : l'ordre des opérations EST la réponse — VPN d'abord, tout le reste ensuite. Conclure en affichant la fiche de préconisations complète du support : « un livrable de consultant. »
- **Visuel suggéré** : Silhouette de consultant en gare avec trois panneaux de décision (Wi-Fi siège, VPN, café).
  - **alt-text** : Consultant nomade devant trois choix de sécurisation représentés par des panneaux.
- **Élément interactif** : 📊 Sondages Livestorm n°2 à 4 — décisions collectives par votes.

---

### Slide 9 — Le paysage en chiffres
- **Type** : chiffres clés
- **Points clés (bullets)** :
  - **> 90 %** des pages web en HTTPS aujourd'hui (Google) — l'exception il y a 15 ans.
  - **100 000 téléchargements en 24 h** : Firesheep, octobre 2010.
  - **~300 000 internautes** espionnés via les faux certificats DigiNotar (Fox-IT, 2011).
- **Notes orateur** : Trois lectures : le chiffrement généralisé est une conquête récente, obtenue en partie par l'électrochoc ; quand la démonstration d'une faille est à la portée de tous, l'industrie bouge en quelques mois ; et la confiance du web repose sur les CA — quand l'une tombe, le cadenas lui-même ment. Transition : les deux histoires.
- **Visuel suggéré** : Trois grands chiffres en typographie XXL avec leurs sources et années en petit.
  - **alt-text** : Trois statistiques géantes sur le chiffrement du web avec leurs sources.

---

### Slide 10 — Affaire n°1 : Firesheep (2010)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Une extension Firefox gratuite, sur un Wi-Fi ouvert.
  - La liste des comptes Facebook/Twitter des voisins — **un double-clic pour entrer**.
  - Le mécanisme : le **cookie de session** circulait en clair.
  - Résultat : le web bascule en HTTPS intégral en quelques mois.
- **Notes orateur** : Raconter : le développeur lassé de dix ans d'avertissements ignorés ; le café, la liste des sessions voisines, le session hijacking sans aucune compétence ; 100 000 téléchargements en 24h, scandale mondial — et c'était le but. Facebook puis Twitter passent au HTTPS intégral ; Let's Encrypt achèvera la généralisation. Leçons : l'écoute passive est indétectable ; le chiffrement partiel (page de connexion seule) est une illusion.
- **Visuel suggéré** : Fenêtre de navigateur stylisée listant des avatars de comptes « disponibles » au-dessus d'une tasse de café.
  - **alt-text** : Interface de l'extension Firesheep listant des sessions de réseaux sociaux capturées dans un café.

---

### Slide 11 — Affaire n°2 : DigiNotar (2011)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Une autorité de certification piratée.
  - **500+ faux certificats**, dont `*.google.com` — valides pour tous les navigateurs.
  - ~300 000 comptes Gmail espionnés en Iran — **cadenas affiché**.
  - Confiance retirée par les navigateurs → **faillite en quelques semaines**.
- **Notes orateur** : Raconter : l'avertissement étrange d'un internaute iranien, l'enquête, le MitM parfait (certificat valide = surveillance invisible, rapport Fox-IT). La sanction du marché : les navigateurs invalident tout — y compris les certificats de l'État néerlandais, principal client. Leçons : toute la confiance du web repose sur quelques centaines de CA ; quand on vend de la confiance, on ne survit pas à sa perte (écho au RaaS de B02). Relance chat : « quel détail vous marque le plus ? »
- **Visuel suggéré** : Cadenas doré fissuré se reflétant dans un écran affichant une page de connexion de messagerie.
  - **alt-text** : Cadenas de sécurité fissuré devant une page de connexion, symbolisant la confiance rompue d'une autorité de certification.
- **Élément interactif** : 💬 Chat — réactions aux deux affaires.

---

### Slide 12 — Et vous ? Le Wi-Fi public
- **Type** : sondage (opinion)
- **Points clés (bullets)** :
  - 📊 **Sondage n°5** : votre pratique sur Wi-Fi public (gare, hôtel, café) ?
  - A) VPN systématique — B) Attention au cadenas — C) Je ne me pose pas la question.
- **Notes orateur** : Sondage d'opinion, sans jugement — C est la réponse la plus courante avant cette session. B protège déjà le contenu (merci Firesheep) ; il manque les métadonnées et le non-web — ce que le VPN ajoute. Objectif : que le réflexe A devienne automatique en déplacement professionnel. Enchaîner sur le mini-scénario des deux Wi-Fi de l'hôtel : « tapez A, B ou C » (réponse B — vérifier le nom à la réception + VPN dans tous les cas ; le signal le plus fort peut être le jumeau maléfique).
- **Visuel suggéré** : Panneau « Wi-Fi gratuit » de café avec trois personnages illustrant les trois pratiques.
  - **alt-text** : Trois usagers d'un café illustrant des niveaux différents de précaution sur Wi-Fi public.
- **Élément interactif** : 📊 Sondage Livestorm n°5 (opinion) puis 🤔 mini-scénario en chat (A/B/C).

---

### Slide 13 — Quiz de validation
- **Type** : quiz (sondages)
- **Points clés (bullets)** :
  - 📊 **Sondage n°6** : à quoi sert le certificat dans le handshake ?
  - 📊 **Sondage n°7** : pourquoi asymétrique PUIS symétrique ?
  - 📊 **Sondage n°8** : l'avantage décisif du WPA-Enterprise ?
- **Notes orateur** : Lancer les trois sondages à la suite (~2 min chacun), débriefs scriptés dans le support : le certificat authentifie (il ne chiffre pas) — sans lui, on chiffre peut-être vers l'attaquant ; l'asymétrique livre la clé, la symétrique fait le travail ; le WPA-Enterprise = identifiants nominatifs révocables (RADIUS). Si le temps le permet, enchaîner sur le bonus n°9 (VPN vs proxy).
- **Visuel suggéré** : Trois cartes de quiz numérotées 6, 7, 8 avec l'icône de sondage Livestorm.
  - **alt-text** : Trois cartes de questions de quiz numérotées, associées à des sondages en direct.
- **Élément interactif** : 📊 Sondages Livestorm n°6 à 8 (+ n°9 en tampon).

---

### Slide 14 — Synthèse & prochaine session
- **Type** : récap
- **Points clés (bullets)** :
  - Le cadenas : authentifier PUIS chiffrer — et ses garants (CA).
  - Le VPN : chiffrer TOUT le trafic en mobilité — VPN d'abord.
  - Le Wi-Fi : WPA3, accès nominatifs — et méfiance en public.
  - Self-paced : SkillsBuild *« Secure Protocols & Cryptography Basics »* + réviser B05-B07 + compléter le schéma draw.io.
  - Prochaine session — B08 : **Atelier de Synthèse 1** : le réseau sécurisé complet.
- **Notes orateur** : Faire écrire dans le chat UN mot retenu, en lire 4-5. Insister sur la préparation de B08 : « pas de nouveau chapitre la semaine prochaine — ON ASSEMBLE TOUT : vous concevrez de A à Z le réseau sécurisé d'une PME. Venez avec vos notes et votre schéma. » Terminer à l'heure exacte.
- **Visuel suggéré** : Récapitulatif en trois vignettes (cadenas, tunnel, ondes) et un panneau « B08 — Atelier » fléché.
  - **alt-text** : Synthèse en trois vignettes des thèmes de la session avec un panneau annonçant l'atelier de synthèse B08.
- **Élément interactif** : Chat de clôture — « un mot que vous retenez ».
