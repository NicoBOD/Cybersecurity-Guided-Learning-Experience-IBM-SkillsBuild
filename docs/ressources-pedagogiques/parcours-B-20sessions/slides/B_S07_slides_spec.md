# Spécifications des slides — Session B07 : Communications sécurisées
Parcours : B 20 sessions  |  Module : B — Sécurité Réseau  |  Format : Spécifications Markdown

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Communications sécurisées
  - Chiffrer les flux de données sur le web, les réseaux sans fil et à distance
  - Parcours B — Session B07
- **Notes orateur** : Bienvenue dans cette septième session. Aujourd'hui, nous allons étudier la protection des données en transit. Lorsque les informations circulent sur Internet ou sur les ondes Wi-Fi, elles peuvent être lues ou interceptées. Nous allons voir comment le chiffrement web (HTTPS), les tunnels chiffrés (VPN) et la sécurisation des connexions sans fil permettent de garantir la confidentialité et l'intégrité de nos échanges.
- **Visuel suggéré** : Représentation d'ondes radio Wi-Fi virtuelles se transformant en chaînes et cadenas dorés au fur et à mesure qu'elles s'approchent d'un ordinateur.
  - **alt-text** : Illustration d'ondes Wi-Fi stylisées et sécurisées par des verrous de cryptographie.
- **Élément interactif** : Question sondage : "Qui s'est déjà connecté à un Wi-Fi public gratuit dans un café ou une gare sans activer de VPN ?"

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Expliquer les étapes du protocole de négociation (*handshake*) TLS/SSL et le rôle des autorités de certification.
  - Comparer les architectures VPN (IPsec, OpenVPN, WireGuard) en fonction des cas d'usage.
  - Identifier les faiblesses des protocoles Wi-Fi anciens (WEP, WPA2-PSK) et préconiser WPA3 ou WPA-Enterprise.
  - Sommaire : Sécuriser le Web avec TLS/SSL (20 min), Les VPN (20 min), Sécurité Wi-Fi (20 min), Exercice Scénarisation VPN & Mobilité (20 min), Quiz (10 min).
- **Notes orateur** : Notre séance sera divisée en trois parties majeures : le chiffrement web HTTPS, la mise en œuvre des réseaux privés virtuels (VPN) et le chiffrement du Wi-Fi local. Nous terminerons par un atelier pratique sur un cas concret de sécurisation d'une flotte de consultants nomades.
- **Visuel suggéré** : Liste ordonnée de l'agenda et des objectifs synchrone présentés dans deux boîtes contrastées.
  - **alt-text** : Tableau d'agenda minuté de la session de 90 minutes.

---

### Slide 3 — Sécuriser le Web : L'analogie de la carte postale
- **Type** : contenu
- **Points clés (bullets)** :
  - **HTTP (HyperText Transfer Protocol)** : Les données transitent en texte clair.
    - *Analogie* : Envoyer une carte postale sans enveloppe. N'importe quel intermédiaire peut la lire.
  - **HTTPS (HTTP Secure)** : Les données sont encapsulées dans un tunnel TLS.
    - *Analogie* : Placer le message dans un coffre-fort portatif verrouillé. Seul le destinataire légitime peut l'ouvrir.
- **Notes orateur** : Par défaut, le web historique utilise le HTTP. C'est le protocole de la carte postale : le facteur, les centres de tri, n'importe qui peut lire vos identifiants ou vos informations bancaires en route. Le HTTPS rajoute une enveloppe blindée de chiffrement appelée TLS.
- **Visuel suggéré** : À gauche, une carte postale manuscrite lisible. À droite, un coffre-fort métallique blindé scellé d'un cadenas.
  - **alt-text** : Comparatif visuel simple entre un message exposé (HTTP) et un message sous coffre (HTTPS).

---

### Slide 4 — Le Handshake TLS : Établir la confiance
- **Type** : schéma
- **Points clés (bullets)** :
  - 1. **Négociation** : Accord sur la version TLS et les algorithmes de chiffrement.
  - 2. **Authentification** : Le serveur fournit son certificat numérique (carte d'identité).
  - 3. **Échange de clés** : Négociation asymétrique d'une clé symétrique temporaire.
  - 4. **Chiffrement symétrique** : Utilisation de la clé de session pour crypter les données échangées.
- **Notes orateur** : Avant d'échanger des données, le client et le serveur effectuent une "poignée de main" ou Handshake TLS. Ils s'accordent sur le langage cryptographique, le serveur prouve son identité avec un certificat, puis ils négocient une clé secrète temporaire pour chiffrer la suite de la session.
- **Visuel suggéré** : Schéma d'échange de messages (flèches aller-retour) entre un navigateur client et un serveur web, représentant les 4 étapes du handshake.
  - **alt-text** : Diagramme temporel d'échange de messages pour le Handshake TLS.

---

### Slide 5 — Le rôle critique des Autorités de Certification (CA)
- **Type** : contenu
- **Points clés (bullets)** :
  - **Problème** : Comment savoir si la clé publique du serveur appartient bien au bon site ?
  - **Solution** : L'Autorité de Certification (CA).
  - Tiers de confiance qui vérifie l'identité réelle d'un domaine.
  - Signe numériquement le certificat d'identité pour éviter l'interception *Man-in-the-Middle* (MitM).
- **Notes orateur** : N'importe qui peut fabriquer une clé publique au nom de votre banque. C'est pour cela que nous avons besoin de tiers de confiance, les Autorités de Certification. Ce sont elles qui vérifient l'identité des serveurs et signent numériquement leurs certificats pour nous garantir que nous ne sommes pas victimes d'un détournement.
- **Visuel suggéré** : Tampon officiel virtuel vert "Vérifié par la CA" apposé sur un document numérique scellé par une clé de sécurité.
  - **alt-text** : Certificat numérique scellé par la signature cryptographique d'une autorité de confiance.

---

### Slide 6 — Les VPN (Virtual Private Network) : Tunnels chiffrés
- **Type** : schéma
- **Points clés (bullets)** :
  - Crée un canal de communication chiffré à travers Internet.
  - Masque l'IP de l'utilisateur et sécurise le trafic.
  - Deux architectures majeures :
    - **Accès distant (Client-to-Site)** : Un salarié nomade se connecte au réseau de son entreprise.
    - **Site-à-site (Site-to-Site)** : Liaison permanente de deux implantations géographiques d'une entreprise.
- **Notes orateur** : Un réseau privé virtuel ou VPN permet de créer un tunnel de communication chiffré à travers un réseau public non sûr comme Internet ou un Wi-Fi public. On utilise le VPN soit pour connecter un ordinateur distant au bureau (Client-to-Site), soit pour relier deux réseaux locaux d'entreprise de manière permanente (Site-to-Site).
- **Visuel suggéré** : Schéma montrant un ordinateur connecté à travers un tuyau transparent (tunnel) traversant un nuage d'Internet flou pour arriver à un serveur d'entreprise sécurisé.
  - **alt-text** : Représentation schématique d'un tunnel VPN chiffré traversant le réseau public Internet.

---

### Slide 7 — Comparatif des protocoles VPN
- **Type** : contenu
- **Points clés (bullets)** :
  - **IPsec (IP Security)** :
    - Opère au niveau de la couche réseau (Couche 3).
    - Norme industrielle pour les tunnels permanents site-à-site.
  - **OpenVPN** :
    - Très flexible et sécurisé (Couche 4), mais lourd et complexe à configurer.
  - **WireGuard** :
    - Protocole moderne, léger (quelques milliers de lignes de code).
    - Extrêmement rapide, économe en batterie, reconnexion instantanée.
- **Notes orateur** : Trois protocoles dominent le monde du VPN. IPsec est la référence pour relier deux sites d'entreprises. OpenVPN est une solution robuste mais un peu lourde pour les postes de travail. WireGuard est le nouveau standard moderne : il est extrêmement rapide, léger en code et gère très bien les connexions mobiles instables.
- **Visuel suggéré** : Tableau comparant IPsec, OpenVPN et WireGuard selon les critères suivants : performance, légèreté du code, cas d'usage et niveau de couche réseau.
  - **alt-text** : Tableau comparatif technique des caractéristiques des protocoles VPN IPsec, OpenVPN et WireGuard.

---

### Slide 8 — Sécurité Wi-Fi : L'évolution historique
- **Type** : contenu
- **Points clés (bullets)** :
  - Les ondes radio Wi-Fi se propagent hors des murs $\rightarrow$ interception passive facile.
  - **WEP** : Premier protocole. **Totalement obsolète et dangereux** (se pirate en 30 secondes).
  - **WPA2-PSK (Pre-Shared Key)** : Le plus répandu à la maison. Clé unique partagée. Vulnérable aux attaques par dictionnaire si la clé est trop simple.
- **Notes orateur** : Le Wi-Fi utilise des ondes radio. Tout le monde à proximité physique peut capter les signaux. C'est pourquoi le chiffrement est obligatoire. Le protocole WEP est obsolète et ne doit plus jamais être utilisé. WPA2-PSK est la clé unique que nous avons tous sur nos box Internet. Elle est efficace mais vulnérable si le mot de passe est trop simple et facile à deviner par force brute.
- **Visuel suggéré** : Une chronologie visuelle montrant les générations de Wi-Fi de WEP (avec un cadenas cassé rouge) à WPA2 (avec un cadenas jaune).
  - **alt-text** : Ligne temporelle présentant l'évolution de la sécurité des protocoles Wi-Fi.

---

### Slide 9 — Protocoles Wi-Fi modernes : WPA3 & Enterprise
- **Type** : schéma
- **Points clés (bullets)** :
  - **WPA3** :
    - Utilise le protocole d'échange de clés SAE (*Simultaneous Authentication of Equals*).
    - Empêche le piratage du mot de passe Wi-Fi par interception passive et attaque hors ligne.
  - **WPA-Enterprise (802.1X)** :
    - Pas de clé partagée unique pour tous.
    - Chaque utilisateur se connecte avec son propre compte (identifiant/mot de passe ou certificat).
    - Authentification centralisée par un serveur de type **RADIUS**.
- **Notes orateur** : Pour les entreprises, la clé partagée unique de WPA2 pose problème : si un salarié s'en va, il faut changer la clé Wi-Fi de tout le monde. La solution est le WPA-Enterprise (ou 802.1X). Chaque salarié se connecte avec ses propres identifiants. De plus, le standard moderne WPA3 corrige les faiblesses d'échanges de clés de WPA2 pour bloquer les tentatives de piratage hors ligne.
- **Visuel suggéré** : Schéma montrant trois employés se connectant à une borne Wi-Fi avec des identifiants différents, la borne relayant les requêtes vers un serveur d'authentification central RADIUS.
  - **alt-text** : Schéma fonctionnel d'une authentification Wi-Fi d'entreprise 802.1X avec serveur RADIUS.

---

### Slide 10 — Activité pratique : Sécurisation d'une flotte nomade
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **Scénario** : L'entreprise possède 100 consultants mobiles travaillant en déplacement.
  - **Problématiques** :
    - Connexion aux serveurs internes confidentiels.
    - Travail sur des réseaux Wi-Fi publics gratuits de gares ou d'hôtels.
  - **Objectif** : Déterminer le protocole Wi-Fi pour les bureaux du siège, la technologie VPN d'accès nomade et les 3 règles de comportement pour l'usage du Wi-Fi public en déplacement.
- **Notes orateur** : Passons à notre atelier. Vous êtes les consultants en cybersécurité de cette entreprise nomade. Vous devez proposer des préconisations concrètes : quelle technologie de VPN installer sur les postes de travail, quelle configuration de Wi-Fi déployer au siège, et quelles consignes donner aux consultants travaillant dans un café.
- **Visuel suggéré** : Silhouette d'un consultant travaillant sur son ordinateur portable dans un café avec des icônes représentant le Wi-Fi public, le tunnel VPN et les serveurs d'entreprise.
  - **alt-text** : Illustration conceptuelle d'un consultant en télétravail devant sécuriser ses flux réseau.
- **Élément interactif** : Travail en sous-groupes de 15 minutes suivi d'une mise en commun par un rapporteur.

---

### Slide 11 — Quiz de validation
- **Type** : quiz
- **Points clés (bullets)** :
  - 1. Quel protocole VPN est le plus léger et le plus performant pour les connexions mobiles instables ?
  - 2. Pourquoi le WPA-Enterprise est-il préférable au WPA-PSK en entreprise ?
  - 3. À quelle étape du handshake TLS le client vérifie-t-il la validité de l'identité du serveur ?
- **Notes orateur** : C'est l'heure du quiz. Préparez vos smartphones ou vos fenêtres de vote pour valider ces notions de protocoles VPN, de chiffrement Wi-Fi et de poignée de main TLS.
- **Visuel suggéré** : QR Code d'accès au quiz à gauche et questions à choix multiples à droite.
  - **alt-text** : Code QR vert cyberpunk de connexion au quiz synchrone.
- **Élément interactif** : Quiz interactif avec correction en direct par le mentor.

---

### Slide 12 — Conclusion & Travail autonome
- **Type** : récap
- **Points clés (bullets)** :
  - **Résumé** : HTTPS/TLS (cryptographie mixte), VPN (WireGuard/IPsec) pour les tunnels distants, et WPA3-Enterprise pour la sécurité Wi-Fi.
  - **Devoirs** : Compléter le cours IBM SkillsBuild *"Secure Protocols & Cryptography Basics"* (~1h30).
  - **Recherche** : Rechercher le cas historique du piratage de l'Autorité de Certification *DigiNotar* en 2011 pour comprendre les enjeux géopolitiques de la confiance.
  - Prochaine session : *Durcissement des systèmes & endpoints (B08)*.
- **Notes orateur** : Nous avons sécurisé nos communications en transit ! Pour approfondir, terminez le cours SkillsBuild. Je vous invite également à chercher l'histoire fascinante de la faillite de la CA DigiNotar pour comprendre à quel point la sécurité d'Internet repose sur la confiance dans ces autorités. À la semaine prochaine !
- **Visuel suggéré** : Badge d'achèvement de cours d'IBM SkillsBuild et logo de l'autorité Let's Encrypt.
  - **alt-text** : Visuel du badge IBM SkillsBuild pour l'achèvement du module Secure Protocols.
