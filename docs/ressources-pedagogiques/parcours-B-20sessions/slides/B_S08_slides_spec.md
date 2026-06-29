# Spécifications des slides — Session B08 : Durcissement des systèmes & endpoints
Parcours : B 20 sessions  |  Module : C — Sécurité des Systèmes et Applications  |  Format : Spécifications Markdown

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Durcissement des systèmes & endpoints
  - Réduire la surface d'attaque des postes de travail et serveurs
  - Parcours B — Session B08
- **Notes orateur** : Bonjour et bienvenue à tous. Aujourd'hui, nous allons étudier la sécurisation des postes de travail et des serveurs, ce qu'on appelle la sécurité des "endpoints". Une fois que l'attaquant a passé les pare-feux réseau, les systèmes d'exploitation constituent le dernier rempart. Nous allons apprendre à les durcir, à configurer le principe du moindre privilège et à comprendre les outils modernes de protection de session.
- **Visuel suggéré** : Vue en gros plan d'un cadenas blindé s'intégrant au cœur d'une carte mère d'ordinateur stylisée avec des pistes de circuits intégrés rétroéclairés en vert.
  - **alt-text** : Graphisme de carte mère avec un verrou de sécurité cyber intégré.
- **Élément interactif** : Question sondage : "Qui utilise quotidiennement sa machine personnelle avec un compte administrateur ?"

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Appliquer le principe du moindre privilège sur Windows et Linux.
  - Établir une checklist méthodologique de durcissement (*hardening*) de machine.
  - Différencier le fonctionnement d'un antivirus classique et d'un EDR.
  - Évaluer une architecture réseau sécurisée via une évaluation par pairs (**Mini-projet 1**).
  - Sommaire : Moindre privilège (20 min), Durcissement système (25 min), Antivirus vs EDR (20 min), Lancement évaluation Mini-projet 1 (15 min), Quiz (10 min).
- **Notes orateur** : Au programme de cette séance : nous étudierons d'abord le principe du moindre privilège. Nous verrons ensuite comment durcir un système d'exploitation pas à pas. Nous comparerons les antivirus traditionnels et les EDR de nouvelle génération, avant de clôturer par les explications sur le Mini-projet 1 d'évaluation de sécurité réseau.
- **Visuel suggéré** : Les compétences visées sous forme d'une checklist graphique, avec à côté le planning temporel minuté de la séance.
  - **alt-text** : Tableau d'agenda minuté de la séance synchrone de 90 minutes.

---

### Slide 3 — Le Principe du Moindre Privilège (Least Privilege)
- **Type** : contenu
- **Points clés (bullets)** :
  - Règle fondamentale de sécurité : accorder uniquement les droits d'accès strictement nécessaires pour réaliser une tâche, et rien de plus.
  - **Pas de session quotidienne en administrateur** (`root` sous Linux, `Administrateur` sous Windows).
  - **Élévation temporaire de privilèges** :
    - Utilisation de `sudo` sous Linux.
    - Utilisation de l'**UAC** (Contrôle de compte d'utilisateur) sous Windows.
  - *Objectif* : Limiter les dégâts si le compte ou un logiciel de l'utilisateur est compromis.
- **Notes orateur** : Le moindre privilège est une règle d'hygiène fondamentale. On ne doit jamais travailler au quotidien avec un compte administrateur. Si vous naviguez sur le web ou lisez vos e-mails en tant qu'administrateur et que vous téléchargez par mégarde un malware, celui-ci s'exécutera avec tous les droits sur la machine. En utilisateur standard, l'impact est grandement confiné.
- **Visuel suggéré** : Illustration d'une clé de sécurité ouvrant une porte blindée contenant un panneau d'avertissement d'élévation de droits (UAC Windows/Sudo Linux).
  - **alt-text** : Schéma conceptuel du passage de droits d'accès limités à droits d'accès temporairement élevés.

---

### Slide 4 — Qu'est-ce que le Durcissement Système (Hardening) ?
- **Type** : contenu
- **Points clés (bullets)** :
  - Processus consistant à sécuriser un système en réduisant sa surface d'exposition aux attaques.
  - Par défaut, les OS sont livrés optimisés pour la facilité d'usage (services ouverts, ports activés, tolérances élevées).
  - *L'analogie* : Une voiture livrée avec toutes les vitres baissées et les portes déverrouillées par défaut.
  - Le durcissement consiste à fermer les fenêtres logicielles inutilisées et à verrouiller les configurations.
- **Notes orateur** : Quand vous installez un système d'exploitation, il est conçu pour que tout fonctionne tout de suite, facilement. Mais de nombreuses fonctionnalités activées par défaut ne vous serviront jamais et représentent autant de failles potentielles. Faire du durcissement, c'est désactiver tout ce qui n'est pas strictement requis par le rôle de la machine.
- **Visuel suggéré** : Une voiture neuve avec les fenêtres grandes ouvertes d'un côté, et à côté la même voiture fermée à clé avec un antivol de volant visible.
  - **alt-text** : Dessin conceptuel comparatif montrant une voiture exposée vs une voiture sécurisée.

---

### Slide 5 — Les 5 étapes indispensables du durcissement
- **Type** : schéma
- **Points clés (bullets)** :
  - 1. **Désactiver services et protocoles inutiles** : Supprimer SMBv1, Telnet, désactiver les services d'impression inutilisés.
  - 2. **Gestion des correctifs (Patch Management)** : Appliquer les correctifs système et applicatifs.
  - 3. **Politiques de sécurité locales** : Longueur de mots de passe, verrouillage de compte après échecs.
  - 4. **Chiffrement au repos** : Activer BitLocker (Windows) ou LUKS (Linux).
  - 5. **Pare-feu local actif** : Configurer Windows Defender Firewall ou UFW.
- **Notes orateur** : Le durcissement repose sur cinq piliers techniques. On élimine les protocoles anciens comme SMBv1 ou Telnet. On applique les correctifs pour boucher les vulnérabilités publiques connues. On configure des règles de mot de passe strictes. On chiffre le disque dur pour le protéger contre le vol physique, et on active un pare-feu local pour interdire les flux non sollicités.
- **Visuel suggéré** : Infographie présentant les 5 piliers sous forme d'une pyramide de sécurité ou d'un bouclier divisé en 5 segments distincts.
  - **alt-text** : Graphique présentant les 5 étapes clés du durcissement d'un système d'exploitation.

---

### Slide 6 — Focus : Le chiffrement au repos (BitLocker / LUKS)
- **Type** : contenu
- **Points clés (bullets)** :
  - **Menace** : Vol physique de l'ordinateur portable.
  - Sans chiffrement de disque :
    - Un voleur démonte le disque dur et le branche sur une autre machine.
    - Il accède à 100% des fichiers en clair, sans connaître le mot de passe Windows.
  - **Solution** : BitLocker / LUKS.
  - Chiffre la totalité du disque.
  - Nécessite la saisie de la clé de démarrage ou la validation par puce de sécurité matérielle (TPM).
- **Notes orateur** : Beaucoup de gens pensent que le mot de passe de leur session Windows protège leurs fichiers. C'est faux si le disque n'est pas chiffré. N'importe qui peut démonter le disque dur, le brancher sur un autre ordinateur et lire l'ensemble des fichiers sans aucun contrôle d'identité. Le chiffrement de disque BitLocker ou LUKS résout ce problème en rendant les données illisibles sans la clé de déverrouillage matérielle.
- **Visuel suggéré** : Un disque dur physique entouré d'une chaîne cadenassée, avec une clé insérée dans le verrou.
  - **alt-text** : Modélisation 3D d'un disque dur sécurisé par chiffrement matériel BitLocker.

---

### Slide 7 — La détection de malwares : L'antivirus classique
- **Type** : contenu
- **Points clés (bullets)** :
  - Fonctionne principalement par **signatures**.
  - Calcule l'empreinte de hachage d'un fichier suspect (ex: MD5, SHA-256).
  - Compare l'empreinte à une base de données mondiale de malwares connus.
  - *Limites* :
    - Totalement inefficace face aux menaces inconnues (attaques Zero-Day).
    - Incapable de détecter les malwares polymorphes (qui changent d'empreinte à la volée).
- **Notes orateur** : L'antivirus classique fonctionne comme la police aux frontières avec une liste de passeports volés : il calcule l'empreinte numérique du fichier et regarde s'il est dans sa base de données d'infractions connues. C'est efficace pour le "tout-venant", mais inefficace si l'attaquant a modifié un tout petit détail du code du malware ou utilise une faille non répertoriée.
- **Visuel suggéré** : Un poster "Recherché" avec la photo d'un fichier suspect et son hash SHA-256 écrit en dessous.
  - **alt-text** : Graphisme symbolisant la détection par signatures de malwares connus.

---

### Slide 8 — L'EDR (Endpoint Detection and Response)
- **Type** : schéma
- **Points clés (bullets)** :
  - Agit comme une boîte noire et un détective comportemental sur l'hôte.
  - Surveille les actions en continu : modifications de la base de registre, processus enfants, connexions réseau inhabituelles.
  - Détecte les **anomalies comportementales**.
  - Capable de bloquer automatiquement le processus suspect et d'isoler la machine du réseau local.
- **Notes orateur** : L'EDR ne se soucie pas seulement de l'identité du fichier, il regarde ce qu'il fait. Si un fichier Word inoffensif démarre soudainement un script PowerShell invisible pour chiffrer vos documents de travail, l'EDR détecte ce comportement anormal, tue le processus suspect, et isole l'ordinateur du reste du réseau pour éviter que l'infection ne se propage aux autres serveurs.
- **Visuel suggéré** : Une loupe numérique analysant des liens de dépendances entre processus système suspects (ex: Word $\rightarrow$ PowerShell $\rightarrow$ chiffrement de fichiers).
  - **alt-text** : Arbre de processus suspect détecté par un outil de surveillance EDR.

---

### Slide 9 — Antivirus vs EDR : Tableau comparatif
- **Type** : contenu
- **Points clés (bullets)** :
  - **Antivirus traditionnel** :
    - Détection : Par signatures.
    - Cible : Malwares connus.
    - Réaction : Suppression du fichier.
  - **EDR (Endpoint Detection and Response)** :
    - Détection : Par analyse comportementale (heuristique).
    - Cible : Attaques avancées, ransomwares, menaces Zero-Day.
    - Réaction : Blocage des processus, isolation réseau de la machine, alerte SOC.
- **Notes orateur** : Ce tableau compare l'antivirus traditionnel et l'EDR. L'antivirus est un outil de nettoyage de premier niveau. L'EDR est un système d'analyse et de réaction en temps réel, capable d'endiguer une cyberattaque complexe en coupant l'accès réseau de la machine compromise pour protéger le reste de l'entreprise.
- **Visuel suggéré** : Tableau comparatif à colonnes détaillant les différences de détection, de cibles et d'actions menées.
  - **alt-text** : Tableau de comparaison des fonctionnalités clés entre un antivirus classique et un agent EDR.

---

### Slide 10 — Activité pratique : Checklist de durcissement d'EcoLog
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **Scénario** : EcoLog déploie 50 ordinateurs portables sous Windows 11 pour ses salariés.
  - **Objectif** : Configurer la politique de groupe (GPO) pour sécuriser ces terminaux.
  - **Tâche** : Associer chaque règle technique au risque de sécurité qu'elle atténue.
    - 1. Désactiver le stockage USB de masse externe.
    - 2. Activer BitLocker.
    - 3. Pare-feu local actif en mode restrictif.
    - 4. Verrouillage automatique de session après 5 minutes.
    - 5. Compte utilisateur standard (non administrateur).
- **Notes orateur** : Nous allons travailler sur la configuration de sécurité des nouveaux ordinateurs d'EcoLog. Dans cette activité, vous devez justifier pourquoi chaque mesure de durcissement technique est indispensable en reliant la configuration technique au risque de vol de données, d'intrusion locale ou d'infection par clé USB.
- **Visuel suggéré** : Copie d'écran d'une console de gestion de stratégie de groupe Windows (GPO) floutée avec des icônes de cadenas.
  - **alt-text** : Interface utilisateur simplifiée d'un configurateur de sécurité système d'exploitation.
- **Élément interactif** : Discussion et restitution collective de la checklist de durcissement.

---

### Slide 11 — Quiz de validation
- **Type** : quiz
- **Points clés (bullets)** :
  - 1. Pourquoi l'UAC ou la commande sudo respectent-elles le principe du moindre privilège ?
  - 2. Quel est l'avantage de la détection comportementale de l'EDR sur l'antivirus classique ?
  - 3. Contre quel risque majeur le chiffrement de disque BitLocker protège-t-il ?
- **Notes orateur** : C'est parti pour le quiz. Prenez vos boîtiers de vote interactifs et validez vos compétences sur les privilèges système, le chiffrement BitLocker et l'apport des outils de détection comportementale EDR.
- **Visuel suggéré** : Code QR vert cyberpunk de connexion au quiz synchrone à gauche, questions à choix multiples à droite.
  - **alt-text** : QR Code d'accès au vote interactif synchrone.
- **Élément interactif** : Quiz de fin de session en direct.

---

### Slide 12 — Conclusion & Mini-projet 1
- **Type** : récap
- **Points clés (bullets)** :
  - **Résumé** : Moindre privilège (sudo/UAC), durcissement d'hôte (mises à jour, ports fermés, chiffrement de disque), et surveillance Endpoint (EDR vs Antivirus).
  - **Mini-projet 1 (Évaluation par pairs)** :
    - Analyser les schémas d'architecture réseau produits par vos camarades lors de la session précédente.
    - Remplir la grille d'évaluation fournie en appliquant les critères du cours.
  - **Travail autonome** : Compléter le module *"System Hardening and Patch Management"* sur IBM SkillsBuild (~1h30).
  - Prochaine session : *Gestion des identités et des accès (IAM) (B09)*.
- **Notes orateur** : Nous avons bouclé la sécurisation des endpoints. N'oubliez pas de réaliser l'évaluation par pairs du Mini-projet 1 : vous devez analyser et noter de manière constructive les schémas d'architecture réseau de vos camarades. Suivez également le cours SkillsBuild associé. La semaine prochaine, nous aborderons la gestion des accès et des identités (IAM). Merci et bon travail à tous !
- **Visuel suggéré** : Illustration d'une loupe numérique pointée sur une copie de rendu de schéma d'architecture réseau à évaluer.
  - **alt-text** : Graphisme représentant l'évaluation d'un projet étudiant avec une liste de critères de réussite.
