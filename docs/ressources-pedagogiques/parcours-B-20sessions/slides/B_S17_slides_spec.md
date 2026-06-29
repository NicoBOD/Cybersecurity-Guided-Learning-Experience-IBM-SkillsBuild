# Spécifications des slides — Session B17 : SIEM, journalisation & détection
Parcours : B 20 sessions  |  Module : E — Opérations, détection & réponse  |  Format : Spécifications Markdown

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - SIEM, journalisation & détection
  - Centralisation des logs, règles de corrélation, et Mini-projet 4
  - Parcours B — Session B17
- **Notes orateur** : Bienvenue dans notre dix-septième session. Aujourd'hui, nous allons plonger au cœur technique de la surveillance : le SIEM et la journalisation. Nous allons comprendre comment collecter des journaux d'événements, comment les corréler pour détecter des attaques complexes et comment analyser des lignes de logs en console. Enfin, nous lancerons le Mini-projet 4, notre dernier mini-projet avant le Capstone.
- **Visuel suggéré** : Des flux lumineux de logs numériques en lignes de texte vertes convergeant depuis des serveurs virtuels vers une console centrale d'analyse 3D de sécurité.
  - **alt-text** : Rapprochement et centralisation des flux de journaux vers un concentrateur sécurisé.
- **Élément interactif** : Question sondage : "Qui a déjà ouvert l'observateur d'événements Windows ou lu les fichiers de logs sous /var/log/ sous Linux ?"

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Expliquer le fonctionnement d'un SIEM (centralisation, normalisation, corrélation).
  - Identifier les logs système et applicatifs clés pour la sécurité d'une infrastructure.
  - Analyser et interpréter des lignes de logs pour isoler une attaque de type bruteforce.
  - Extraire et analyser des informations de logs pour le **Mini-projet 4**.
  - Sommaire : Principes du SIEM (20 min), Les Logs clés de sécurité (20 min), Analyse pratique de logs (20 min), Lancement du Mini-projet 4 (20 min), Quiz (10 min).
- **Notes orateur** : Nous étudierons en premier lieu l'architecture et les principes de fonctionnement d'un SIEM. Nous verrons ensuite quels sont les logs à collecter en priorité. Nous passerons à de l'analyse pratique en console pour repérer une attaque par force brute, avant d'expliquer les livrables du Mini-projet 4 et de réaliser le quiz de validation.
- **Visuel suggéré** : Planning de la séance minuté sous forme d'un tableau à droite, avec les compétences cibles illustrées à gauche par des icônes.
  - **alt-text** : Tableau d'agenda minuté de la session synchrone d'analyse de logs.

---

### Slide 3 — Qu'est-ce qu'un SIEM ?
- **Type** : contenu
- **Points clés (bullets)** :
  - **SIEM** : Security Information and Event Management.
  - Outil logiciel centralisé qui collecte, stocke et analyse les journaux d'événements (logs) de toute l'entreprise en temps réel.
  - **Les trois étapes logiques d'un SIEM** :
    - **1. Collecte (Ingestion)** : Réception des logs des pare-feux, serveurs, routeurs, applications.
    - **2. Normalisation** : Traduction de formats de logs différents dans un langage commun standardisé.
    - **3. Corrélation & Analyse** : Croisement des événements pour détecter des comportements suspects.
- **Notes orateur** : Si un pirate s'introduit chez vous, il va laisser une trace sur le pare-feu, une trace sur le serveur de fichiers, et une autre sur le contrôleur de domaine. Regarder ces machines individuellement est impossible. Le SIEM rassemble toutes ces traces éparpillées au même endroit, les traduit dans un format standardisé et les analyse ensemble pour reconstituer l'attaque.
- **Visuel suggéré** : Diagramme montrant des logs sources disparates (Windows XML, Linux Syslog, logs de pare-feu Cisco) entrant dans un entonnoir SIEM et ressortant sous une forme unifiée et propre.
  - **alt-text** : Schéma d'ingestion et de normalisation de logs par un SIEM.

---

### Slide 4 — Le moteur de corrélation du SIEM
- **Type** : schéma
- **Points clés (bullets)** :
  - **Définition** : Règle logique associant plusieurs événements distincts pour lever une alerte de sécurité.
  - Exemple de règle de corrélation simple :
    - Événement A : 10 échecs de connexion SSH sur un serveur en moins de 30 secondes.
    - Événement B : 1 connexion réussie sur ce même serveur depuis la même adresse IP dans la foulée.
    - **Règle** : Si Événement A + Événement B $\rightarrow$ Alerte : Attaque Brute Force Réussie !
- **Notes orateur** : Sans moteur de corrélation, un échec de connexion est un non-événement. Des utilisateurs qui se trompent de mot de passe, cela arrive tout le temps. Mais si le SIEM détecte 50 échecs de connexion sur des comptes différents depuis la même adresse IP externe en 2 minutes, le moteur de corrélation comprend qu'il s'agit d'un scan de force brute et génère une alerte d'urgence.
- **Visuel suggéré** : Une équation visuelle liant des icônes d'échecs répétés (cadenas rouges) suivis d'un succès (cadenas vert), pointant vers une sirène de sécurité d'alerte rouge.
  - **alt-text** : Exemple logique d'une règle de corrélation d'événements.

---

### Slide 5 — Les journaux d'événements (Logs) clés à surveiller
- **Type** : contenu
- **Points clés (bullets)** :
  - On ne peut pas tout stocker (limites de bande passante et de stockage).
  - Les logs prioritaires pour la cybersécurité :
    - **Logs d'authentification** : Connexions réussies/échouées, créations de comptes, élévations de privilèges (ex: sudo, connexions Active Directory).
    - **Logs réseau** : Flux refusés par les pare-feux, requêtes DNS suspectes.
    - **Logs système d'exécution** : Lancement de processus inhabituels (ex: PowerShell lancé par Word).
- **Notes orateur** : Récupérer l'intégralité des logs de toutes les machines de l'entreprise coûte trop cher en stockage et ralentit le réseau. Le rôle du RSSI est de cibler les logs d'intérêt. On se concentre en priorité sur l'authentification (qui se connecte ?), le réseau (qui communique avec l'extérieur ?) et les lancements de processus système critiques.
- **Visuel suggéré** : Tableau à trois colonnes détaillant pour chaque source de logs (OS, Réseau, Application) les types d'événements spécifiques à collecter.
  - **alt-text** : Tableau récapitulatif des logs clés de sécurité à surveiller.

---

### Slide 6 — Anatomie d'une ligne de log brute
- **Type** : contenu
- **Points clés (bullets)** :
  - Une ligne de log standard doit répondre aux questions : Qui, Quand, Où, Quoi ?
  - Exemple de log de connexion Linux (Auth.log) :
    - `Jun 29 22:15:30 srv-paye sshd[4012]: Failed password for invalid user admin from 198.51.100.42 port 52345 ssh2`
  - Découpage analytique :
    - **Date/Heure** : `Jun 29 22:15:30` (Quand)
    - **Hôte cible** : `srv-paye` (Où)
    - **Processus source** : `sshd[4012]`
    - **Événement** : `Failed password for invalid user admin` (Quoi)
    - **IP source** : `198.51.100.42` (Qui)
- **Notes orateur** : Pour être capable d'enquêter, il faut savoir lire un journal d'événements brut. Regardez cette ligne issue d'un serveur Linux. On y trouve l'heure précise de l'attaque, le nom de la machine cible, le protocole utilisé, l'identifiant que l'attaquant a essayé de forcer, et l'adresse IP publique d'où provient la tentative de piratage.
- **Visuel suggéré** : La ligne de log affichée en grand avec des couleurs différentes pour chaque champ (Date en jaune, Machine en bleu, Événement en rouge, IP en vert) associées à des bulles d'explications.
  - **alt-text** : Découpage et explication des champs d'une ligne de journal Linux SSH.

---

### Slide 7 — Détection d'une attaque par Brute Force en console
- **Type** : schéma
- **Points clés (bullets)** :
  - Analyse d'un extrait de logs réels :
    - `22:10:01 - Failed password for user root from 203.0.113.5`
    - `22:10:03 - Failed password for user root from 203.0.113.5`
    - `22:10:05 - Failed password for user root from 203.0.113.5`
    - `22:10:08 - Accepted password for user root from 203.0.113.5`
  - **Constat** : 3 échecs suivis d'une connexion réussie en 7 secondes.
  - **Diagnostic** : Attaque par brute force réussie sur le compte administrateur. **Alerte critique immédiate.**
- **Notes orateur** : Cet enchaînement de lignes de logs est typique d'une attaque par dictionnaire ou force brute réussie. On observe plusieurs échecs de connexion rapprochés sur le même compte, suivis d'un message "Accepted password" provenant de la même adresse IP. L'attaquant a trouvé le bon mot de passe. Il est désormais dans le système avec les droits d'administration complets.
- **Visuel suggéré** : Les lignes de logs formatées dans un terminal de commande avec les lignes d'échecs encadrées en orange et la ligne de succès finale clignotant en rouge d'alerte.
  - **alt-text** : Enchaînement de logs illustrant une compromission par force brute réussie.

---

### Slide 8 — Présentation du Mini-projet 4 : Analyse de logs chez EcoLog
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **Contexte** : EcoLog a mis en place un concentrateur de logs. Cette nuit, le SOC a levé une alerte suspecte d'élévation de privilèges sur le serveur de fichiers de production.
  - **Objectif** : Analyser l'extrait de logs fourni pour reconstituer le scénario de l'attaque.
- **Notes orateur** : C'est le moment d'aborder le Mini-projet 4. Vous allez recevoir un fichier de logs d'EcoLog correspondant à un incident survenu la nuit dernière. Votre rôle en tant qu'analyste de sécurité est de mener l'enquête : comprendre comment le pirate s'est connecté, quel compte il a compromis et ce qu'il a tenté de faire sur le serveur.
- **Visuel suggéré** : Silhouette d'un détective numérique observant des lignes de logs à la loupe avec le logo d'EcoLog en arrière-plan.
  - **alt-text** : Fiche d'introduction du Mini-projet 4 d'analyse forensique de logs.

---

### Slide 9 — Livrables attendus pour le Mini-projet 4
- **Type** : contenu
- **Points clés (bullets)** :
  - Votre rapport d'analyse d'incident doit détailler :
    - 1. **La chronologie précise de l'attaque** (Date, heure, minutes de chaque événement clé).
    - 2. **Le vecteur d'entrée et la méthode de compromission** (ex: force brute, exploitation de faille).
    - 3. **L'évaluation de l'impact** (Quels fichiers ont été accédés ou modifiés ?).
    - 4. **Trois recommandations de sécurité immédiates** pour empêcher que cette attaque ne se reproduise chez EcoLog.
- **Notes orateur** : Ce mini-projet va vous initier à la rédaction de rapports d'incident. Vous devez livrer une frise chronologique précise des événements, expliquer comment l'attaquant s'est introduit, mesurer l'étendue des dégâts sur les fichiers d'EcoLog et proposer trois mesures techniques concrètes pour bloquer cette faille.
- **Visuel suggéré** : Icône de rapport d'audit tamponné "Résolu" avec la liste ordonnée des 4 sections attendues dans le livrable.
  - **alt-text** : Plan de rédaction et livrables requis pour le Mini-projet 4.

---

### Slide 10 — Atelier de lecture de logs en groupe
- **Type** : étude de cas
- **Points clés (bullets)** :
  - En groupes de 3 ou 4 apprenants (durée : 15 min).
  - **Exercice** : Analyser les lignes de logs suivantes et répondre :
    - `10:05:12 - Firewall blocked traffic from 198.51.100.12 to Port 80`
    - `10:05:14 - Firewall blocked traffic from 198.51.100.12 to Port 443`
    - `10:05:16 - Firewall blocked traffic from 198.51.100.12 to Port 22`
  - **Question** : Quel comportement suspect l'adresse IP `198.51.100.12` adopte-t-elle ?
- **Notes orateur** : Commençons par un entraînement collectif. Regardez ces trois lignes de logs réseau issues de notre pare-feu. Une même adresse IP externe tente de se connecter successivement à différents ports fermés de notre entreprise. Que fait ce système distant à votre avis ? Oui, il réalise un scan de ports pour chercher une entrée.
- **Visuel suggéré** : Tableau des événements du pare-feu avec l'IP externe surlignée en jaune pour faire ressortir la répétition.
  - **alt-text** : Exercice pratique de détection de scan de ports à partir de logs pare-feu.
- **Élément interactif** : Analyse participative en équipe avec mise en commun orale.

---

### Slide 11 — Quiz de validation
- **Type** : quiz
- **Points clés (bullets)** :
  - 1. Quel processus du SIEM permet de convertir des logs de formats différents (XML, Syslog) en un format unifié ?
  - 2. Pourquoi est-il déconseillé de collecter absolument tous les logs de tous les équipements d'un réseau ?
  - 3. Dans le log SSH étudié, que signifie le terme `Failed password` ?
- **Notes orateur** : Testons vos compétences sur la journalisation et le fonctionnement des SIEM. Connectez-vous et votez pour valider les notions de normalisation, de sélection des logs et de déchiffrement d'événements.
- **Visuel suggéré** : QR Code d'accès au vote synchrone à gauche et questions interactives à droite.
  - **alt-text** : QR Code vert d'accès au questionnaire d'évaluation.
- **Élément interactif** : Quiz interactif avec correction en direct par le mentor.

---

### Slide 12 — Conclusion & Travail autonome
- **Type** : récap
- **Points clés (bullets)** :
  - **Résumé** : SIEM (collecte, normalisation, corrélation), ciblage des logs d'intérêt, lecture de logs (Qui, Quand, Où, Quoi), et Mini-projet 4.
  - **Travail personnel** : Rédaction et dépôt de votre rapport d'analyse d'incident (Mini-projet 4).
  - **IBM SkillsBuild** : Suivre le cours *"Security Monitoring and Log Analysis"* (~1h30).
  - Prochaine session : *Gestion des vulnérabilités (B18)*.
- **Notes orateur** : Nous avons posé les bases de l'analyse de logs ! C'est maintenant à vous de jouer pour rédiger le rapport d'incident d'EcoLog du Mini-projet 4. N'oubliez pas de suivre le module SkillsBuild associé. La semaine prochaine, nous verrons comment identifier et corriger les vulnérabilités de nos systèmes avant que les attaquants ne les exploitent. Bonne semaine !
- **Visuel suggéré** : Badge d'achèvement de cours d'IBM SkillsBuild pour la surveillance et l'analyse de logs.
  - **alt-text** : Badge de réussite du cours Log Analysis d'IBM SkillsBuild.
