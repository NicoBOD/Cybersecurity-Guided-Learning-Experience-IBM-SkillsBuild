# Spécifications des slides — Session 03 : Sécurité des systèmes & réseaux
Parcours : A 8 sessions  |  Module : Réseaux Sécurisés  |  Format : Spécifications Markdown

---

## Slide 1 : Page de garde
* **Layout** : Titre (Emphase visuelle, fond sombre)
* **Texte affiché sur la slide** :
  * **Sécurité des Systèmes & Réseaux**
  * Parcours A — Session 03
  * *Bâtir des barrières logiques : du pare-feu au chiffrement des communications*
  * Nom du Mentor / IBM SkillsBuild
* **Visuels suggérés** : Schéma épuré représentant un mur de briques incandescent (pare-feu) protégeant des serveurs contre un nuage Internet. Logo officiel dans un angle.
* **Notes du présentateur** :
  * Accueillir les apprenants.
  * Faire le point sur le travail autonome de la session A2 (les indices de phishing trouvés).
  * Introduire le sujet : comment structurer et chiffrer les flux de données pour empêcher les attaquants de s'immiscer dans notre réseau.

---

## Slide 2 : Objectifs de la séance & Sommaire
* **Layout** : Deux colonnes (Gauche : Objectifs, Droite : Sommaire)
* **Texte affiché sur la slide** :
  * **Nos objectifs aujourd'hui** :
    * Expliquer le rôle d'un pare-feu (*firewall*) et ses règles de filtrage.
    * Comprendre l'utilité et le fonctionnement d'un *VPN*.
    * Différencier les protocoles *HTTP* et *HTTPS / TLS*.
    * Structurer une architecture réseau sécurisée simple (*DMZ*).
  * **Sommaire de la séance** :
    * 1. Brise-glace : Le courrier postal vs le réseau (10 min)
    * 2. Le pare-feu : Le gardien du réseau (20 min)
    * 3. Le VPN et le protocole HTTPS (20 min)
    * 4. Activité pratique 1 : Architecture sécurisée (20 min)
    * 5. Démo 3 : Inspection de règles de pare-feu (10 min)
    * 6. Quiz de validation & Clôture (10 min)
* **Visuels suggérés** : Icônes cibles pour les objectifs et icône de liste pour le sommaire.
* **Notes du présentateur** :
  * Présenter les objectifs en rassurant sur le fait que l'on va vulgariser les notions techniques réseaux (ports, protocoles, etc.).

---

## Slide 3 : Rappel & Brise-glace interactif
* **Layout** : Plein écran interactif
* **Texte affiché sur la slide** :
  * **Brise-glace : La métaphore de la carte postale**
  * *Comment circule l'information sur Internet ?*
    * Imaginez que vous envoyez une carte postale par la poste sans enveloppe.
    * Qui peut la lire durant son voyage ? Le facteur, le trieur, le voisin ?
    * Quel protocole internet ressemble à cette carte postale ? Et comment la protéger ?
* **Visuels suggérés** : Photo ou dessin humoristique d'une carte postale classique avec des informations secrètes écrites au dos.
* **Notes du présentateur** :
  * Laisser 3 minutes de réflexion.
  * Faire le lien : le protocole HTTP classique est comme une carte postale (tout circule en texte clair). HTTPS est comme une lettre scellée dans une enveloppe blindée (le chiffrement).
  * Introduire l'idée que la sécurité réseau utilise le chiffrement des flux et le filtrage des accès.

---

## Slide 4 : Le pare-feu (Firewall)
* **Layout** : Contenu structuré avec tableau explicatif
* **Texte affiché sur la slide** :
  * **Le Pare-feu : Filtrer pour sécuriser**
  * *Il inspecte chaque paquet de données selon 3 critères :*
    * **Adresse IP source & destination** : D'où vient la donnée, où va-t-elle ?
    * **Port réseau** : Quel service est demandé (ex. Port 80/443 pour le Web, Port 22 pour l'accès distant).
    * **Action** : Autoriser (*Allow*) ou Bloquer (*Deny*).
  * **Exemple de règle de filtrage** :
    * *Règle* : Autoriser uniquement le trafic entrant depuis Internet vers le port 443 (HTTPS) de notre serveur web. Tout le reste est bloqué par défaut (*Default Deny*).
* **Visuels suggérés** : Représentation schématique d'un pare-feu laissant passer certains paquets (verts) et bloquant d'autres (rouges).
* **Notes du présentateur** :
  * Expliquer la notion de port réseau par la métaphore des boîtes aux lettres ou des portes d'un immeuble (ex. porte 80 pour le courrier public, porte 22 pour le technicien d'entretien).
  * Souligner l'importance de la règle "Tout ce qui n'est pas explicitement autorisé est interdit" (*Default Deny*).

---

## Slide 5 : Le tunnel sécurisé : Le VPN
* **Layout** : Deux colonnes comparatives
* **Texte affiché sur la slide** :
  * **VPN (Virtual Private Network) : Le tunnel sécurisé**
  * **Sans VPN (Connexion publique)** :
    * Vos données transitent en clair sur le réseau wifi public (ex. hôtel, café).
    * Risque d'interception par un attaquant situé sur le même réseau.
  * **Avec VPN (Tunnel chiffré)** :
    * Vos données sont chiffrées avant de quitter votre ordinateur.
    * Un tunnel sécurisé relie votre machine au serveur VPN de l'entreprise.
    * Vos données sont illisibles pour les intermédiaires.
* **Visuels suggérés** : Schéma d'une connexion sans VPN (données exposées aux yeux d'un attaquant) vs connexion avec VPN (représentée par un tunnel bleu protégeant les données du regard extérieur).
* **Notes du présentateur** :
  * Détailler l'importance du VPN pour le télétravail.
  * Expliquer qu'un VPN protège le transport des données, mais ne garantit pas que la machine à l'extrémité n'est pas infectée par un virus.

---

## Slide 6 : Le standard du Web chiffré : HTTPS & TLS
* **Layout** : Deux colonnes
* **Texte affiché sur la slide** :
  * **HTTP vs HTTPS : Repérer le cadenas**
  * **HTTP (Non sécurisé)** :
    * Les mots de passe et données bancaires circulent en clair.
    * Risque d'écoute clandestine (*Man-in-the-Middle*).
  * **HTTPS (Chiffré via TLS)** :
    * Chiffrement des échanges entre le navigateur et le serveur.
    * Authenticité du site web certifiée par un certificat numérique.
    * Cadenas visible dans la barre d'adresse du navigateur.
* **Visuels suggérés** : Captures d'écran de barre d'adresse de navigateur : l'une montrant "Non sécurisé" avec un panneau rouge (HTTP), l'autre montrant le cadenas fermé vert (HTTPS).
* **Notes du présentateur** :
  * Insister sur le fait que HTTPS garantit que la communication est privée et que le site est bien celui qu'il prétend être (authenticité), mais n'empêche pas un site malveillant d'être en HTTPS (un pirate peut aussi obtenir un certificat gratuit).

---

## Slide 7 : Zone Démilitarisée (DMZ)
* **Layout** : Architecture réseau graphique
* **Texte affiché sur la slide** :
  * **La DMZ : Protéger le cœur du réseau**
  * *Ne mélangez pas vos serveurs publics et vos données internes !*
  * **Réseau Externe (Internet)** ➔ Accède au serveur Web public situé dans la **DMZ**.
  * **DMZ (Zone Démilitarisée)** ➔ Zone tampon isolant les serveurs exposés à Internet.
  * **Réseau Interne (LAN)** ➔ Zone hautement sécurisée hébergeant les bases de données et les ordinateurs de l'entreprise.
* **Visuels suggérés** : Schéma à trois branches reliant Internet, la DMZ et le réseau local, séparés par un pare-feu double ou triple interface.
* **Notes du présentateur** :
  * Expliquer pourquoi un serveur Web public piraté dans la DMZ ne doit pas permettre d'accéder directement au réseau de l'entreprise (étanchéité).
  * Utiliser la métaphore du sas d'entrée d'une banque ou de l'accueil d'un bâtiment d'entreprise.

---

## Slide 8 : Démo 3 — Analyse de règles de pare-feu
* **Layout** : Console textuelle / Liste de règles
* **Texte affiché sur la slide** :
  * **Démonstration : Audit d'une table de filtrage**
  * *Que font ces règles de pare-feu ?*
    1. `Source: LAN | Dest: Internet | Port: ANY | Action: ALLOW`
    2. `Source: Internet | Dest: Server_Web | Port: 443 | Action: ALLOW`
    3. `Source: Internet | Dest: LAN | Port: ANY | Action: DENY`
  * **Objectif** : Identifier quelle règle bloque les pirates et laquelle permet aux employés de naviguer sur Internet.
* **Visuels suggérés** : Extrait de console d'administration de pare-feu simulée.
* **Notes du présentateur** :
  * Suivre les instructions du script de démo `A_scripts_demo.md#demo-3-firewall`.
  * Expliquer l'ordre d'application des règles (généralement du haut vers le bas).
  * Poser la question : "Que se passe-t-il si j'inverse la règle 2 et la règle 3 ?" (Tout accès au serveur web public est bloqué car la règle d'interdiction globale s'applique en premier).

---

## Slide 9 : Quiz rapide & Validation
* **Layout** : Contenu interactif (Quiz)
* **Texte affiché sur la slide** :
  * **Quiz : Validez vos acquis !**
  * 1. *Quel protocole devez-vous utiliser pour naviguer en toute sécurité sur un site bancaire ?* ➔ **[HTTP / HTTPS / FTP ?]**
  * 2. *Le VPN empêche-t-il votre ordinateur de télécharger un virus ?* ➔ **[Oui / Non ?]**
  * 3. *Quel est l'emplacement idéal pour héberger le serveur web public d'une entreprise ?* ➔ **[Le LAN interne / La DMZ / Le cloud privé uniquement ?]**
* **Visuels suggérés** : Code QR Kahoot/Wooclap de la session.
* **Notes du présentateur** :
  * Lancer le quiz. Corriger à voix haute.
  * *Réponses* : 1. HTTPS ; 2. Non (il protège le transport, pas le contenu) ; 3. La DMZ.

---

## Slide 10 : Clôture & Devoirs
* **Layout** : Fin de session / Devoirs
* **Texte affiché sur la slide** :
  * **Vos devoirs avant la prochaine séance (Self-paced)** :
    * Suivre le module IBM SkillsBuild : *Principes de la sécurité des identités et du cloud*.
    * Durée estimée : ~75 min.
    * Exercice pratique de préparation : Vérifier si votre e-mail personnel a été compromis dans une fuite connue (recherche sur un site de type *Have I Been Pwned*).
  * **Prochaine séance** : *Sécurité du cloud, des données & des identités (A4)*.
  * Merci à tous, restez connectés de manière sécurisée !
* **Visuels suggérés** : Logo IBM SkillsBuild. Capture de l'interface Have I Been Pwned.
* **Notes du présentateur** :
  * Expliquer brièvement comment fonctionne la vérification d'adresse e-mail compromise.
  * Clôturer la séance.
