# Spécifications des slides — Session B05 : Fondamentaux réseau pour la sécurité
Parcours : B 20 sessions  |  Module : A — Fondations  |  Format : Spécifications Markdown

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Fondamentaux réseau pour la sécurité
  - Comprendre comment circulent les données pour mieux les protéger
  - Parcours B — Session B05
- **Notes orateur** : Bienvenue dans cette cinquième session. Aujourd'hui, nous allons ouvrir le capot et regarder comment fonctionne le réseau informatique. C'est un prérequis incontournable : pour sécuriser des flux d'informations, nous devons d'abord comprendre comment ils sont structurés et comment ils transitent sur Internet.
- **Visuel suggéré** : Fond sombre avec une illustration complexe de câbles réseaux interconnectés et de flux de données représentés par des impulsions lumineuses vertes.
  - **alt-text** : Graphisme de câblage de centre de données avec des flux de données lumineux verts connectés à des serveurs virtuels.
- **Élément interactif** : Sondage rapide pour évaluer le niveau de confort des apprenants avec les notions d'adresse IP et de port de communication.

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Expliquer les modèles OSI et TCP/IP sous l'angle de la cybersécurité.
  - Identifier le rôle des protocoles majeurs (DNS, DHCP, ARP, ICMP).
  - Associer les ports standards à leurs services associés (22, 53, 80, 443, 3389).
  - Analyser un en-tête de paquet réseau simple (IP, ports, TTL).
  - Sommaire : Modèles réseau OSI & TCP/IP (20 min), Protocoles & Ports (20 min), Adressage & En-tête IP (15 min), Activité Analyse de paquets (25 min), Quiz (10 min).
- **Notes orateur** : Nous allons aujourd'hui démystifier les modèles OSI et TCP/IP à l'aide d'une analogie postale simple. Nous étudierons ensuite les ports réseau les plus exposés avant de réaliser un exercice pratique d'analyse de captures de paquets suspectes.
- **Visuel suggéré** : Deux colonnes listant les objectifs de la session synchrone et l'agenda minuté associé.
  - **alt-text** : Tableau d'agenda présentant les jalons de temps de la session synchrone de 90 minutes.

---

### Slide 3 — Modèles OSI et TCP/IP : Les couches réseau
- **Type** : schéma
- **Points clés (bullets)** :
  - **Modèle OSI (7 couches)** vs **Modèle TCP/IP (4 couches)**.
  - Organise la communication de manière modulaire.
  - Chaque couche ajoute un en-tête d'information (encapsulation).
  - En sécurité, chaque couche représente une surface d'attaque et des défenses dédiées.
- **Notes orateur** : Les données ne voyagent pas d'un bloc. Elles descendent à travers différentes couches logicielles et matérielles, de l'application jusqu'au câble physique. C'est l'encapsulation. Pour un professionnel de la sécurité, chaque couche possède ses propres menaces et nécessite des dispositifs de défense adaptés.
- **Visuel suggéré** : Schéma comparatif alignant verticalement les 7 couches OSI (Physique à Application) et les 4 couches TCP/IP (Accès Réseau, Internet, Transport, Application).
  - **alt-text** : Graphique de comparaison structurelle entre les couches des modèles OSI et TCP/IP sous forme d'empilement vertical.

---

### Slide 4 — L'analogie postale
- **Type** : schéma
- **Points clés (bullets)** :
  - **Couche Application** : Le texte rédigé et la langue choisie (Ex : HTTP, SMTP).
  - **Couche Transport** : Choix de la livraison (En recommandé/TCP ou normal/UDP).
  - **Couche Réseau** : L'adresse IP de destination écrite sur l'enveloppe.
  - **Couche Liaison** : Le coursier local transportant le pli d'un bureau à l'autre (MAC).
- **Notes orateur** : Pour bien comprendre, utilisons une analogie postale. La couche application est le contenu de votre lettre. La couche transport définit si vous l'envoyez avec signature (TCP) ou en envoi simple (UDP). La couche réseau est l'adresse écrite sur l'enveloppe, lue par le tri postal. Enfin, la couche liaison est le transport physique local entre deux points.
- **Visuel suggéré** : Une série de dessins montrant une personne écrivant une lettre, puis la mettant dans une enveloppe timbrée, prise en charge par un facteur sur un vélo.
  - **alt-text** : Bande dessinée conceptuelle illustrant le parcours d'une lettre pour modéliser l'encapsulation des données réseau.

---

### Slide 5 — Attaques et défenses par couche
- **Type** : contenu
- **Points clés (bullets)** :
  - **Couche 2 (Liaison)** :
    - *Attaque* : Usurpation ARP (intercepter le trafic local). *Défense* : Port Security.
  - **Couche 3 (Réseau)** :
    - *Attaque* : Usurpation d'adresse IP (IP Spoofing). *Défense* : Filtrage par pare-feu.
  - **Couche 4 (Transport)** :
    - *Attaque* : SYN Flood (saturation). *Défense* : Pare-feu à états (Stateful).
  - **Couche 7 (Application)** :
    - *Attaque* : Injections web. *Défense* : Pare-feu applicatif (WAF).
- **Notes orateur** : Voyons maintenant les attaques typiques de chaque couche. Au niveau physique local (couche 2), on peut usurper les adresses physiques. Au niveau Internet (couche 3), on peut masquer son IP. Au niveau transport (couche 4), on peut saturer les connexions TCP. Au niveau applicatif (couche 7), on s'attaque au code de l'application. La défense doit donc être présente à chaque niveau.
- **Visuel suggéré** : Tableau à double entrée récapitulant les attaques et les mécanismes de protection pour les couches Liaison, Réseau, Transport et Application.
  - **alt-text** : Tableau structuré listant les types d'attaques cyber et leurs mesures de remédiation associées par couche réseau.

---

### Slide 6 — Protocoles critiques : DNS & DHCP
- **Type** : contenu
- **Points clés (bullets)** :
  - **DNS (Domain Name System) — Port 53** :
    - L'annuaire d'Internet : traduit les noms de domaine en adresses IP.
    - *Risque* : Détournement de requêtes, Tunneling DNS pour exfiltrer des données.
  - **DHCP (Dynamic Host Configuration Protocol)** :
    - Distribue automatiquement les configurations réseau (IP, passerelle, DNS).
    - *Risque* : Serveur DHCP pirate redistribuant de mauvaises configurations.
- **Notes orateur** : Certains protocoles sont le cœur du fonctionnement d'un réseau. Le DNS est l'annuaire qui traduit nos saisies web en adresses IP. Le DHCP configure automatiquement nos machines à leur connexion. Les attaquants adorent cibler ces deux services pour détourner le trafic ou voler des informations confidentielles.
- **Visuel suggéré** : Illustration d'un annuaire téléphonique virtuel ouvert traduisant un domaine web en une série de chiffres IP, à côté d'un engrenage DHCP distribuant des adresses à des ordinateurs.
  - **alt-text** : Graphique illustrant la traduction DNS (Nom de domaine $\rightarrow$ IP) et la configuration automatique par un serveur DHCP.

---

### Slide 7 — ARP & ICMP : Les outils du réseau local
- **Type** : contenu
- **Points clés (bullets)** :
  - **ARP (Address Resolution Protocol)** :
    - Associe une adresse IP (logique) à une adresse MAC (physique locale).
    - Ne possède aucun mécanisme de sécurité natif (vulnérable par conception).
  - **ICMP (Internet Control Message Protocol)** :
    - Utilisé pour le diagnostic et le contrôle réseau (Ex : commande `ping`).
    - Souvent bloqué par les entreprises pour éviter le repérage de serveurs par les pirates.
- **Notes orateur** : L'ARP permet de trouver l'adresse physique locale de la machine qui détient une IP. Créé à une époque où le réseau local était considéré comme sûr, il est très simple à usurper. Quant à l'ICMP, c'est le langage des diagnostics réseau, utilisé notamment par la commande `ping`, mais qu'on désactive souvent en entrée de réseau pour rester discret vis-à-vis des scans d'attaquants.
- **Visuel suggéré** : Représentation d'une commande ping envoyée depuis un terminal et de la réponse système reçue, avec un schéma de table de correspondance IP/MAC.
  - **alt-text** : Capture de console montrant le retour d'une commande ping réseau réussie avec les valeurs de temps et de TTL.

---

### Slide 8 — Les ports de communication à surveiller
- **Type** : contenu
- **Points clés (bullets)** :
  - Un port est une porte d'entrée logique sur une machine pour un service donné.
  - **Port 22 — SSH (Secure Shell)** : Administration sécurisée en console.
  - **Port 80 / 443 — HTTP / HTTPS** : Trafic web non chiffré et chiffré.
  - **Port 3389 — RDP (Remote Desktop Protocol)** : Bureau à distance Windows.
  - Règle d'or : Fermer systématiquement tous les ports inutilisés.
- **Notes orateur** : Pensez aux ports de communication comme aux portes d'une maison. Si vous laissez le port 3389 de contrôle à distance Windows ouvert directement sur Internet, les attaquants s'y engouffreront par force brute pour tenter de s'introduire. Une bonne pratique consiste à fermer tous les accès et à n'ouvrir que les flux strictement indispensables.
- **Visuel suggéré** : Graphisme de façade de bâtiment avec des portes portant des numéros de ports (22, 80, 443, 3389), certaines ouvertes en rouge et d'autres fermées à clé en vert.
  - **alt-text** : Illustration conceptuelle de ports réseau modélisés sous forme de portes d'accès numérotées et verrouillées.

---

### Slide 9 — Adressage IP & En-tête de paquet
- **Type** : schéma
- **Points clés (bullets)** :
  - **Adresse IP (ex: 192.168.1.50)** : Divisée en partie Réseau (la rue) et partie Hôte (la maison) via le masque de sous-réseau (ex: 255.255.255.0).
  - **L'En-tête IP** : Contient les métadonnées de transmission indispensables.
    - IP Source & IP Destination.
    - Protocole de transport encapsulé (TCP ou UDP).
    - **TTL (Time To Live)** : Compteur de routeurs autorisés pour éviter les boucles infinies.
- **Notes orateur** : Chaque paquet qui circule sur Internet possède une enveloppe d'en-tête IP. Celle-ci précise qui envoie et qui reçoit. Elle intègre également une valeur essentielle : le TTL. Le TTL est une durée de vie sous forme de compteur : à chaque routeur traversé, cette valeur baisse de 1. Si elle atteint 0, le paquet est détruit pour éviter de saturer Internet.
- **Visuel suggéré** : Structure d'un en-tête IP sous forme de paquet postal cartonné avec des étiquettes détaillées pour l'IP source, l'IP destination, le TTL et le type de protocole.
  - **alt-text** : Graphique détaillant la composition d'une enveloppe de paquet IP avec ses métadonnées techniques.

---

### Slide 10 — Activité pratique : Analyse de captures de paquets
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **Objectif** : Analyser deux captures simplifiées (Capture A et Capture B).
  - Identifier les adresses IP et ports source/dest.
  - Repérer l'anomalie de sécurité cachée dans les paquets.
  - Durée : 25 minutes en groupes de 3.
- **Notes orateur** : Nous allons maintenant jouer le rôle d'un analyste de sécurité réseau. Dans les captures fournies dans votre support de cours, vous devez repérer les anomalies. L'une d'elles concerne une requête DNS très suspecte ressemblant à du phishing, et l'autre est une attaque de brute force sur le protocole RDP de prise de contrôle à distance.
- **Visuel suggéré** : Les deux extraits de captures réseau A et B affichés dans des fenêtres de terminaux virtuelles avec des lignes de texte colorées.
  - **alt-text** : Captures réseau textuelles simplifiées montrant des détails de trames Ethernet, IP et TCP/UDP.
- **Élément interactif** : Analyse collaborative en sous-salles virtuelles.

---

### Slide 11 — Quiz de validation
- **Type** : quiz
- **Points clés (bullets)** :
  - 1. Quel port est utilisé par le service SSH ?
  - 2. Que se passe-t-il lorsque le TTL d'un paquet atteint 0 ?
  - 3. À quelle couche du modèle OSI se situe le protocole IP ?
- **Notes orateur** : Faisons notre quiz de fin de session pour valider ces fondamentaux réseau. Connectez-vous à la plateforme de vote. Prenez le temps de bien lire les questions avant de répondre.
- **Visuel suggéré** : QR Code d'accès au vote avec les trois questions à choix multiples affichées à droite.
  - **alt-text** : Code QR vert cyberpunk de connexion au quiz synchrone.
- **Élément interactif** : Quiz interactif de clôture.

---

### Slide 12 — Conclusion & Travail autonome
- **Type** : récap
- **Points clés (bullets)** :
  - **Résumé** : Utilité du modèle en couches (OSI/TCP-IP), surveillance des ports sensibles (22, 3389) et analyse de trames IP.
  - **Devoirs** : Suivre le cours IBM SkillsBuild *"Network Security - Part 1"* (~1h30).
  - **Action pratique** : Faire un test de commande ping dans son terminal vers cyber.gouv.fr et observer le TTL.
  - Prochaine session : *Introduction à la sécurité des systèmes d'exploitation (B06)*.
- **Notes orateur** : Félicitations pour vos analyses de trames ! Le réseau n'a maintenant plus de secrets pour vous. Pour aller plus loin, complétez le cours SkillsBuild indiqué à l'écran et testez par vous-même la commande ping dans votre terminal personnel. Bonne semaine et à la prochaine session !
- **Visuel suggéré** : Icône de réussite du cours Network Security d'IBM SkillsBuild et capture d'une commande ping exécutée sur un terminal de commande.
  - **alt-text** : Badge de réussite SkillsBuild et capture d'écran d'un terminal de commande exécutant un ping réseau.
