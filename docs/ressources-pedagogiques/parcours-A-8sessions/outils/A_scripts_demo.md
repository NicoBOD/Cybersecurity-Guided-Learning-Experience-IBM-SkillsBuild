# Guide des Démonstrations — Parcours A (8 sessions)
Parcours : A 8 sessions  |  Module : Démonstrations Mentor  |  Format : Scripts de démonstrations pas-à-pas

---

## Démo 1 (Session A1) : Cartographie passive de la surface d'exposition (OSINT) {#demo-1-osint}

* **Objectif** : Montrer aux apprenants ce qu'un attaquant peut voir sur une entreprise à partir de sources publiques et d'outils légaux, sans commettre d'intrusion active.
* **Durée estimée** : 10 minutes.
* **Outils utilisés** : Outils de requête DNS en ligne (ex. dnschecker.org) ou commande système `nslookup`, et portails publics d'OSINT.

### Script pas-à-pas :

1. **Introduction orale (1 min)** :
   * *"Bonjour à tous. Avant de mener une attaque, un pirate cherche à cartographier sa cible. C'est la phase de Reconnaissance de la Cyber Kill Chain. Nous allons voir comment un pirate rassemble des pièces du puzzle sur MedDistri (ou une cible de test) à l'aide d'outils publics."*

2. **Étape 1 : Recherche DNS passive (3 min)** :
   * Ouvrir une console ou utiliser un service web public de requête DNS.
   * Exécuter la commande ou soumettre le domaine :
     ```bash
     nslookup -type=mx entreprise-cible.fr
     ```
   * *Explication en direct* :
     *"Ici, nous demandons les enregistrements MX (Mail Exchange) de l'entreprise. Cela nous indique quel serveur de messagerie elle utilise. Nous pouvons voir si elle héberge ses propres serveurs de messagerie (exposant des vulnérabilités potentielles) ou si elle utilise une solution managée cloud comme Office 365 ou Google Workspace."*

3. **Étape 2 : Cartographier les serveurs publics (3 min)** :
   * Exécuter :
     ```bash
     nslookup -type=txt entreprise-cible.fr
     ```
   * Relever l'enregistrement SPF (Sender Policy Framework).
   * *Explication en direct* :
     *"L'enregistrement SPF contient la liste des serveurs autorisés à envoyer des e-mails au nom de cette entreprise. Un attaquant l'analyse pour repérer des services tiers sous-traitants (comme des outils d'envoi de newsletters ou de facturation) afin d'usurper leur identité."*

4. **Étape 3 : Synthèse pédagogique (3 min)** :
   * Rappeler que ces requêtes ne laissent aucune trace suspecte chez la victime.
   * *"Cette phase de reconnaissance passive donne à l'attaquant la liste des employés (via LinkedIn) et l'architecture de base (via DNS). Il a maintenant tout en main pour préparer son e-mail de phishing de la session suivante."*

---

## Démo 2 (Session A2) : Simulation de Vishing (Jeu de rôle vocal) {#demo-2-vishing}

* **Objectif** : Sensibiliser les apprenants à la rapidité et à la force de persuasion de la manipulation humaine par téléphone.
* **Durée estimée** : 10 minutes.
* **Rôles (format webinaire Livestorm)** : Le mentor joue théâtralement les deux voix en changeant de ton (l'attaquant / la victime), ou donne la réplique au modérateur du chat s'il y en a un. Les apprenants observent et notent dans le chat le moment où ils auraient raccroché.

### Script pas-à-pas :

1. **Mise en situation (2 min)** :
   * Annoncer le principe : « vous allez assister à un appel téléphonique reconstitué ; votre mission : repérer le moment précis où il fallait raccrocher, et l'écrire dans le chat. »
   * *Le ton du mentor pour l'attaquant* : Pressé, sérieux, directif, mais chaleureux et rassurant à la fois.

2. **Le Dialogue simulé (5 min)** :
   * **Mentor** : *"Bonjour Thomas ? C'est Alexandre du support informatique central. Je t'appelle en urgence parce que notre SIEM vient de détecter une tentative d'intrusion russe sur ton compte Office 365. Tu as dû recevoir une notification ou un SMS d'alerte à l'instant, c'est bien le cas ?"*
   * **Thomas** (Victime) : *"Ah, attendez... oui, je viens de recevoir un SMS avec un code à 6 chiffres."*
   * **Mentor** : *"Parfait, c'est ce que je voulais vérifier. La connexion pirate est bloquée en attente. Pour la rejeter définitivement et réinitialiser tes accès, j'ai besoin que tu me dictes les 6 chiffres du SMS immédiatement. Faisons vite pour éviter qu'ils n'accèdent à tes emails commerciaux."*
   * **Thomas** : *"D'accord, c'est le 458 962."*
   * **Mentor** : *"Super, c'est validé de mon côté, la menace est écartée. Tu peux reprendre ton travail normalement. Merci pour ta réactivité, bonne journée !"*

3. **Débriefing collectif (3 min)** :
   * Arrêter la simulation. Lire dans le chat les « moments de rupture » notés par les apprenants, puis interroger la classe.
   * *Questions au groupe* :
     * *"Qu'est-ce qui s'est réellement passé ?"* (L'attaquant a tenté de se connecter au compte Office de Thomas, ce qui a déclenché l'envoi d'un SMS MFA de sécurité. L'attaquant a appelé pour subtiliser ce code et valider sa connexion pirate).
     * *"Quels leviers ont été utilisés ?"* (L'urgence artificielle, l'autorité usurpée du support informatique, la confiance).
     * *"Quelle est la consigne d'hygiène cyber ?"* (Un administrateur informatique n'a **jamais** besoin de demander votre code MFA ou votre mot de passe par téléphone. Si on vous le demande, raccrochez).

---

## Démo 3 (Session A3) : Audit et logique de filtrage Pare-feu (Firewall) {#demo-3-firewall}

* **Objectif** : Expliquer aux apprenants le concept de filtrage réseau et l'importance cruciale de l'ordre de priorité des règles.
* **Durée estimée** : 10 minutes.
* **Outils utilisés** : Projection d'un simulateur de tableau de règles ou fichier texte contenant les règles.

### Script pas-à-pas :

1. **Introduction orale (2 min)** :
   * *"Un pare-feu est comme le portier d'une discothèque. Il lit des consignes strictes écrites sur sa fiche de haut en bas. Dès qu'une consigne correspond au client qui se présente, il l'applique et s'arrête de lire la suite."*

2. **Étape 1 : Analyse de la configuration initiale (4 min)** :
   * Projeter le tableau de règles suivant :
     ```text
     [ RÈGLE 1 ] Source: LAN_Interne | Dest: Internet | Port: ANY | Action: ALLOW
     [ RÈGLE 2 ] Source: Internet   | Dest: Serv_Web | Port: 443 | Action: ALLOW
     [ RÈGLE 3 ] Source: Internet   | Dest: ANY      | Port: ANY | Action: DENY
     ```
   * *Explication en direct* :
     * *"La règle 1 permet à tous les salariés du réseau local (LAN) de naviguer sur Internet (tous ports autorisés en sortie)."*
     * *"La règle 2 permet aux clients extérieurs d'accéder au site web public de l'entreprise uniquement sur le port sécurisé HTTPS 443."*
     * *"La règle 3 est notre bouclier par défaut : tout le trafic entrant restant depuis Internet est bloqué (*Default Deny*)."*

3. **Étape 2 : Le piège de l'ordre d'application (3 min)** :
   * Poser la question aux apprenants :
     *"Imaginons que je commette une erreur et que je déplace la règle 3 tout en haut du tableau (en RÈGLE 1). Que se passe-t-il ?"*

   * *Explication en direct après réponse des élèves* :
     *"Si la règle interdisant tout trafic de manière globale est lue en premier, elle va correspondre à toutes les connexions. Les règles d'autorisation situées en dessous ne seront jamais lues. Les serveurs web seront inaccessibles et le réseau sera totalement paralysé. L'ordre des règles de pare-feu est donc tout aussi important que le contenu des règles elles-mêmes."*

4. **Synthèse pédagogique (1 min)** :
   * Résumer la consigne : toujours ordonner les règles du pare-feu de la plus spécifique (en haut) à la plus générale (en bas), en terminant toujours par le blocage implicite total.

---

## Démo 4 (Session A4) : Sécuriser une identité de A à Z (MFA & gestionnaire de mots de passe) {#demo-4-identites}

* **Objectif** : Montrer concrètement comment vérifier l'exposition d'une identité, activer une authentification multifacteur par application (TOTP) et déléguer la mémoire des mots de passe à un gestionnaire.
* **Durée estimée** : 8 minutes.
* **Outils utilisés** : Un navigateur (site public de vérification de fuites type Have I Been Pwned), un **compte de démonstration** créé pour l'occasion (jamais un compte réel du mentor), une application d'authentification (ex. FreeOTP, Aegis, Google/Microsoft Authenticator) et un gestionnaire de mots de passe (ex. Bitwarden en compte de démonstration).
* **Préparation indispensable** : réaliser la démo à blanc et **capturer chaque écran** ; en cas de problème technique en direct, la démo se raconte intégralement avec les captures.

### Script pas-à-pas :

1. **Étape 1 : Vérifier l'exposition (2 min)** :
   * Ouvrir le site de vérification de fuites et saisir l'adresse du compte de démonstration.
   * *Explication en direct* :
     *"Ce site agrège les fuites de données publiques. Si votre adresse apparaît, cela signifie qu'un mot de passe associé circule quelque part — et les attaquants testent ces mots de passe partout où vous les avez réutilisés. C'est pour cela que la réutilisation d'un mot de passe est le péché capital de l'hygiène numérique."*
   * Rappeler que les apprenants ont fait cette vérification en devoir (session A3) : relier à leurs résultats.

2. **Étape 2 : Enrôler le MFA par application (3 min)** :
   * Sur le compte de démonstration, ouvrir les paramètres de sécurité et lancer l'activation de la validation en deux étapes par application.
   * Montrer le **QR code** d'enrôlement, le scanner avec l'application d'authentification, montrer le **code à 6 chiffres qui change toutes les 30 secondes**.
   * *Explication en direct* :
     *"Le secret est désormais partagé entre le service et mon téléphone. Le code est généré LOCALEMENT : rien ne transite par SMS, donc rien à intercepter par SIM swapping. Et souvenez-vous de la démo vishing de la session A2 : ce code, on ne le dicte JAMAIS à personne."*
   * Montrer les **codes de secours** générés et expliquer où les conserver (imprimés ou dans le gestionnaire — pas en note sur le téléphone lui-même).

3. **Étape 3 : Le gestionnaire de mots de passe (2 min)** :
   * Dans le gestionnaire (compte de démonstration), générer un mot de passe de 20 caractères aléatoires pour un site, l'enregistrer, puis montrer le remplissage automatique à la connexion suivante.
   * *Explication en direct* :
     *"Le gestionnaire résout l'équation impossible : unique + long + mémorisable. Vous ne retenez plus qu'UN mot de passe maître — long, sous forme de phrase — et la machine retient tout le reste. Bonus : le remplissage automatique refuse de fonctionner sur un site de phishing, car le domaine ne correspond pas. Votre gestionnaire est aussi un détecteur de typosquatting."*

4. **Synthèse pédagogique (1 min)** :
   * Les trois gestes à reproduire chez soi (c'est le self-paced de la session) : vérifier son exposition, activer le MFA sur sa messagerie en priorité, adopter un gestionnaire.
   * *"La messagerie d'abord : c'est la clé de toutes les autres serrures — celui qui la contrôle peut réinitialiser tous vos autres comptes."*

---

## Démo 5 (Session A5) : Construire une matrice de risques en direct {#demo-5-matrice-risques}

* **Objectif** : Rendre tangible la cotation des risques (Criticité = Vraisemblance × Impact) et visualiser l'effet du traitement : le passage de la criticité brute à la criticité résiduelle.
* **Durée estimée** : 8 minutes.
* **Outils utilisés** : Une feuille de calcul préparée (LibreOffice Calc, Excel ou Google Sheets) contenant : une matrice 4×4 avec mise en forme conditionnelle (vert 1-3, orange 4-9, rouge 12-16) et un petit registre de risques (colonnes : Scénario, Vraisemblance, Impact, Criticité brute, Traitement choisi, Criticité résiduelle).
* **Préparation indispensable** : pré-remplir les trois scénarios votés pendant l'activité « Le Comité des Risques » (portable volé 3×3=9 ; rançongiciel facturation 3×4=12 ; inondation 1×4=4).

### Script pas-à-pas :

1. **Étape 1 : Du vote à la matrice (3 min)** :
   * Projeter le registre pré-rempli et faire apparaître les trois pastilles dans la matrice 4×4.
   * *Explication en direct* :
     *"Voici vos trois votes du comité des risques, projetés dans la matrice. Le rançongiciel est en zone rouge : traitement obligatoire — vous avez voté 'réduire puis transférer', voyons ce que cela produit."*

2. **Étape 2 : L'effet du traitement (3 min)** :
   * Saisir en direct les mesures décidées (sauvegardes immuables + EDR pour le rançongiciel) et la nouvelle cotation : la vraisemblance d'un impact critique chute, la criticité résiduelle passe par exemple de 12 à 6 — la pastille glisse du rouge vers l'orange.
   * *Explication en direct* :
     *"C'est LA slide qui justifie un budget en comité de direction : voilà ce que vos 20 000 euros achètent — un passage du rouge à l'orange. Sans matrice, la sécurité est une dépense ; avec la matrice, c'est un investissement mesurable."*

3. **Étape 3 : Cotation participative (2 min)** :
   * Demander au chat de proposer un 4e scénario (ou utiliser en secours : « fuite d'un fichier RH envoyé au mauvais destinataire »).
   * Faire voter la vraisemblance puis l'impact via le chat (« tapez deux chiffres, ex. 3-2 »), saisir la cotation médiane en direct et laisser la matrice classer le risque.
   * *Synthèse* :
     *"Vous venez de faire en deux minutes ce qu'un comité des risques fait chaque trimestre. La méthode complète, côté professionnel, s'appelle EBIOS Risk Manager — c'est la méthode de l'ANSSI, référencée dans votre support."*

---

## Démo 6 (Session A6) : Lire une attaque dans les logs {#demo-6-analyse-logs}

* **Objectif** : Apprendre à repérer une attaque par force brute dans un journal d'authentification et comprendre comment un SIEM la détecte automatiquement.
* **Durée estimée** : 8 minutes.
* **Outils utilisés** : Un simple extrait de journal (fictif) projeté à l'écran — aucun outil technique requis. Préparer des captures de secours.

### Script pas-à-pas :

1. **Mise en situation (1 min)** :
   * *"Voici 60 secondes de la vie d'un serveur SSH exposé sur Internet — un journal d'authentification reconstitué. Lisez avec moi, et écrivez dans le chat ce que vous voyez. Ne vous censurez pas : toutes les hypothèses sont bonnes."*

2. **Étape 1 : Projection et lecture collective (3 min)** :
   * Projeter l'extrait (révéler les lignes progressivement si possible) :
     ```text
     03:14:07 | sshd | IP: 203.0.113.42 | user: admin   | FAILED_LOGIN
     03:14:08 | sshd | IP: 203.0.113.42 | user: admin   | FAILED_LOGIN
     03:14:09 | sshd | IP: 203.0.113.42 | user: root    | FAILED_LOGIN
     03:14:10 | sshd | IP: 203.0.113.42 | user: test    | FAILED_LOGIN
        [ ... 214 lignes similaires en 45 secondes ... ]
     03:14:55 | sshd | IP: 203.0.113.42 | user: backup  | LOGIN_SUCCESS
     03:15:12 | bash | user: backup | commande : téléchargement d'un outil depuis un site inconnu
     03:15:48 | bash | user: backup | commande : lecture du fichier des utilisateurs du système
     ```
   * Lire à voix haute, lentement, en s'arrêtant sur trois indices : la **cadence** (plusieurs essais par seconde — aucun humain ne tape si vite), la **rotation des comptes** (admin, root, test, backup — un dictionnaire), et **l'heure** (3h du matin).

3. **Étape 2 : Révélation et débrief (2 min)** :
   * Lire les hypothèses du chat, valider : **attaque par force brute automatisée**, réussie sur le compte `backup` (mot de passe faible).
   * *Explication en direct* :
     *"Et regardez ce qui compte vraiment : ce n'est pas la rafale d'échecs — c'est ce qui vient APRÈS le succès. Un vrai utilisateur consulte ses fichiers ; celui-ci télécharge un outil et lit la liste des comptes. L'attaque commence maintenant."*

4. **Étape 3 : La règle SIEM (2 min)** :
   * Afficher (ou écrire en direct) la règle de corrélation :
     ```text
     SI plus de 20 FAILED_LOGIN depuis la même IP en moins de 60 secondes
     ET LOGIN_SUCCESS depuis cette même IP dans les 5 minutes suivantes
     ALORS alerte CRITIQUE "Force brute réussie présumée" → SOC niveau 1
     ```
   * *Synthèse pédagogique* :
     *"Un humain ne peut pas lire des millions de lignes ; le SIEM, si — et il ne lit pas les lignes, il lit les combinaisons. Dernier rappel, venu de la session A3 : la vraie question n'est pas 'comment détecter la force brute sur ce port SSH exposé', c'est 'pourquoi ce port est-il exposé sans filtrage ni MFA ?'. La détection rattrape ce que l'architecture n'a pas empêché."*
