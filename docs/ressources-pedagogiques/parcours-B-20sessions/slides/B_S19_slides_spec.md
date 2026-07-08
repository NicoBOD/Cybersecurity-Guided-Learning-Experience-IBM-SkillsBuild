# Spécifications des slides — Session B19 : Réponse aux incidents & bases du forensics
Parcours : B 20 sessions  |  Module : E — Opérations, détection & réponse  |  Format : Spécifications Markdown

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Réponse aux incidents & bases du forensics
  - Les 6 étapes du cycle SANS/NIST, préservation des preuves, bases du pentest et rapport préliminaire
  - Parcours B — Session B19
- **Notes orateur** : Bienvenue dans notre dix-neuvième session. Aujourd'hui, nous allons étudier la réponse aux incidents et l'investigation numérique, appelée *forensics*. C'est le cœur d'activité des équipes de crise. Nous allons apprendre à structurer une réponse en 6 étapes selon les standards du SANS et du NIST, à comprendre comment collecter des preuves numériques sans les corrompre, et à voir comment réaliser les premières étapes d'un rapport d'incident.
- **Visuel suggéré** : Illustration d'un ruban de scène de crime numérique virtuel de couleur vert cyberpunk entourant des serveurs informatiques, avec une clé USB d'extraction forensique lumineuse branchée sur un rack.
  - **alt-text** : Scène de crime numérique et outils d'investigation forensique.
- **Élément interactif** : Question sondage : "Selon vous, quelle est la première action à faire lorsqu'on s'aperçoit qu'un ordinateur est en train de chiffrer ses fichiers à cause d'un ransomware ?"

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Restituer les 6 étapes du processus de réponse aux incidents (SANS/NIST).
  - Expliquer les principes de préservation des preuves numériques (chaîne de contrôle, écriture protégée).
  - Identifier les phases clés d'un test d'intrusion (*pentesting*) et l'utilité d'un rapport préliminaire.
  - Sommaire : Le Cycle de réponse aux incidents (20 min), Principes de l'investigation numérique (20 min), Introduction au Pentest (20 min), Activité de rédaction de rapport préliminaire (20 min), Quiz (10 min).
- **Notes orateur** : Pendant cette session de 90 minutes, nous allons explorer le cycle de réponse aux incidents. Nous verrons comment préserver des preuves informatiques recevables en justice. Nous ferons une introduction aux bases du test d'intrusion, avant de travailler sur une activité pratique de rédaction de rapport d'incident et de terminer par notre quiz.
- **Visuel suggéré** : Emplacement de l'agenda et des objectifs synchrone présenté dans un tableau structuré à deux colonnes avec repères temporels.
  - **alt-text** : Tableau d'agenda minuté de la session synchrone d'incident response.

---

### Slide 3 — Les 6 étapes de la réponse aux incidents (SANS/NIST)
- **Type** : schéma
- **Points clés (bullets)** :
  - **1. Préparation** : Avoir les outils, les playbooks et l'équipe d'urgence prête.
  - **2. Identification** : Détecter l'incident et confirmer qu'il s'agit d'une attaque réelle.
  - **3. Confinement** : Limiter la propagation (isoler les machines, couper le réseau).
  - **4. Éradication** : Supprimer la cause de l'incident (nettoyer les malwares, patcher).
  - **5. Récupération** : Restaurer les systèmes à partir des sauvegardes saines.
  - **6. Leçons apprises** : Analyser l'incident pour améliorer les défenses futures.
- **Notes orateur** : Face à une crise, les équipes ne doivent pas improviser. On applique le cadre standardisé du SANS en six étapes. La première est la préparation. Lorsque l'attaque survient, on l'identifie, on la contient pour éviter qu'elle ne se propage, puis on éradique la menace. Une fois le danger écarté, on reconstruit les serveurs grâce à nos sauvegardes avant de faire un débriefing pour comprendre comment éviter que cela ne recommence.
- **Visuel suggéré** : Un schéma hexagonal ou une flèche cyclique reliant les 6 étapes numérotées de 1 à 6 avec des icônes d'outils, d'alerte, de barrière de confinement, de balai, de flèche montante et de cerveau.
  - **alt-text** : Les 6 phases logiques de la réponse aux incidents informatiques.

---

### Slide 4 — Le Confinement : Isoler sans éteindre
- **Type** : contenu
- **Points clés (bullets)** :
  - Objectif : Stopper l'attaquant avant qu'il ne compromette d'autres systèmes.
  - **La règle d'or** : **Isoler du réseau, mais ne pas éteindre la machine**.
  - Pourquoi ne pas éteindre ?
    - Éteindre la machine efface le contenu de la mémoire vive (**RAM**).
    - Or, les preuves d'attaques modernes (processus en cours, clés de chiffrement de ransomwares) ne se trouvent souvent que dans la RAM.
- **Notes orateur** : C'est une erreur classique : voir un ransomware chiffrer ses données et appuyer sur le bouton d'alimentation pour éteindre l'ordinateur. En faisant cela, vous détruisez toutes les preuves stockées dans la mémoire vive, la RAM. Les adresses IP de connexion du pirate, les clés de déchiffrement temporaires et les logiciels malveillants actifs s'évaporent. Le réflexe est de débrancher le câble réseau ou de couper le Wi-Fi, mais de laisser la machine allumée.
- **Visuel suggéré** : Illustration montrant une prise réseau débranchée d'un ordinateur allumé, barré d'une croix rouge sur le bouton "Power OFF".
  - **alt-text** : Principe d'isolation réseau d'une machine compromise sans coupure d'alimentation.

---

### Slide 5 — Forensics : La préservation des preuves numériques
- **Type** : contenu
- **Points clés (bullets)** :
  - **Forensics** : Science de l'investigation numérique légale.
  - Les deux règles cardinales pour que les preuves soient acceptées en justice :
    - **1. Utilisation d'un bloqueur d'écriture** : Pour faire une copie conforme du disque sans modifier un seul bit de la source.
    - **2. Calcul d'empreintes numériques (Hashs)** : Calculer le hash (ex: SHA-256) du disque original et de la copie. S'ils sont identiques, la preuve n'a pas été altérée.
    - **Chaîne de contrôle (Chain of Custody)** : Documenter qui a manipulé la preuve, quand et comment.
- **Notes orateur** : Si vous devez aller devant les tribunaux ou faire marcher vos assurances, vos preuves doivent être incontestables. Vous ne devez jamais analyser le disque dur d'origine directement sous peine de modifier ses métadonnées. On utilise un bloqueur d'écriture physique ou logique pour copier le disque. On calcule ensuite l'empreinte SHA-256 de l'original et de la copie. Si les signatures concordent, cela prouve devant le juge que l'enquêteur n'a rien modifié.
- **Visuel suggéré** : Schéma d'une copie de disque dur sécurisée passant par un bloqueur d'écriture, avec affichage des empreintes SHA-256 identiques sur l'original et la copie.
  - **alt-text** : Processus d'acquisition forensique préservant l'intégrité des preuves.

---

### Slide 6 — La pyramide de volatilité des données
- **Type** : schéma
- **Points clés (bullets)** :
  - Les données numériques s'effacent plus ou moins vite après l'incident.
  - De la plus volatile (s'efface en premier) à la moins volatile (persiste longtemps) :
    - 1. Registres du processeur & Cache (microsecondes).
    - 2. Table de routage & Mémoire vive (RAM) (secondes/minutes).
    - 3. Fichiers temporaires du système (heures).
    - 4. Disque dur / Stockage persistant (années).
    - 5. Sauvegardes hors ligne (indéfini).
- **Notes orateur** : En forensics, le temps joue contre nous. Les données disparaissent à des vitesses différentes. C'est l'ordre de volatilité. Les informations du processeur et de la mémoire vive s'effacent instantanément si on éteint la machine, tandis que les fichiers stockés sur le disque dur persistent. L'enquêteur doit donc d'abord capturer la RAM avant de toucher au disque dur.
- **Visuel suggéré** : Pyramide de volatilité de bas en haut : base large et stable (Disques durs) vers un sommet pointu et instable (Registres CPU, RAM).
  - **alt-text** : Ordre de volatilité des données informatiques lors d'une investigation.

---

### Slide 7 — Introduction aux tests d'intrusion (Pentest)
- **Type** : contenu
- **Points clés (bullets)** :
  - **Pentest** : Simulation d'une attaque réelle autorisée par l'entreprise pour identifier ses faiblesses avant les vrais pirates.
  - **Les trois approches classiques** :
    - **Boîte Noire (Black Box)** : Le pentester n'a aucune information préalable (simule un pirate externe).
    - **Boîte Blanche (White Box)** : Accès total aux codes sources et architectures (audit approfondi).
    - **Boîte Grise (Grey Box)** : Accès limité (simule un employé mécontent ou un partenaire externe).
- **Notes orateur** : Pour tester nos processus de réponse à incident, nous pouvons faire appel à des pentesters. Ce sont des "hackers éthiques" payés pour s'introduire dans le système d'information. Ils peuvent travailler en boîte noire, c'est-à-dire sans aucune information, en boîte grise avec un simple compte utilisateur, ou en boîte blanche avec les plans du réseau et le code des applications sous les yeux.
- **Visuel suggéré** : Trois boîtes physiques de couleurs différentes (Noire, Grise, Blanche) illustrant les trois niveaux d'accès à l'information.
  - **alt-text** : Les 3 méthodes de tests d'intrusion en entreprise.

---

### Slide 8 — Le déroulement d'une cyber-attaque (Cyber Kill Chain)
- **Type** : schéma
- **Points clés (bullets)** :
  - Les étapes suivies par un attaquant lors d'un pentest ou d'une intrusion réelle :
    - 1. **Reconnaissance** : Recherche d'informations sur la cible (OSINT).
    - 2. **Armement** : Conception de la charge malveillante.
    - 3. **Livraison** : Envoi de l'attaque (ex: e-mail de phishing).
    - 4. **Exploitation** : Déclenchement de la faille sur la machine cible.
    - 5. **Installation** : Dépôt d'une porte dérobée (backdoor) pour rester dans le réseau.
    - 6. **Actions sur objectifs** : Vol de données ou chiffrement.
- **Notes orateur** : Les attaquants et les pentesters suivent un chemin méthodique appelé la Cyber Kill Chain de Lockheed Martin. Elle se compose de six étapes. Tout commence par la reconnaissance passive. Puis l'attaquant arme sa charge, la livre via un mail de phishing par exemple, exploite la faille, installe un outil de persistance pour ne pas se faire éjecter, et enfin réalise ses objectifs de vol ou de sabotage.
- **Visuel suggéré** : Frise chronologique descendante reliant les six étapes de la Kill Chain avec des icônes d'attaque ciblée.
  - **alt-text** : Les étapes d'intrusion de la Cyber Kill Chain de Lockheed Martin.

---

### Slide 9 — Le rapport préliminaire d'incident (RPI)
- **Type** : contenu
- **Points clés (bullets)** :
  - Rédigé rapidement après la détection d'une attaque majeure pour informer la direction.
  - Doit être concis, factuel et éviter le jargon trop technique.
  - Structure type du RPI :
    - **Description succincte** : Qu'est-ce qui s'est passé ? (ex: Ransomware actif sur 5 postes).
    - **Impact estimé** : Quels services sont à l'arrêt ?
    - **Actions déjà menées** : Qu'avons-nous fait pour contenir la crise ?
    - **Prochaines étapes** : Quelles investigations sont prévues ?
- **Notes orateur** : En pleine gestion de crise, la direction générale a besoin de comprendre la situation sans se noyer dans des détails techniques. C'est l'objectif du Rapport Préliminaire d'Incident. Ce document d'une ou deux pages résume ce que l'on sait, l'impact sur l'activité de l'entreprise, les mesures de confinement déjà prises, et les prochaines actions prévues par l'équipe de réponse.
- **Visuel suggéré** : Un modèle de document d'une page avec des en-têtes clairs : Résumé, Impact, Actions prises, Recommandations.
  - **alt-text** : Modèle de rapport préliminaire de gestion d'incident de sécurité.

---

### Slide 10 — Activité pratique : Rédiger un mémo de crise
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **Scénario** : L'équipe de comptabilité d'EcoLog signale que trois ordinateurs affichent un écran rouge exigeant une rançon de 500 dollars pour débloquer les dossiers financiers.
  - **Mission** : Rédiger le plan d'action immédiat en 3 points en appliquant les principes vus aujourd'hui.
    - Quelle est l'action de confinement prioritaire ?
    - Que faites-vous des ordinateurs ?
    - Quel message envoyez-vous au reste de l'entreprise ?
- **Notes orateur** : Nous allons faire une simulation de crise. Le ransomware s'est déclaré chez les comptables d'EcoLog. Rédigez le mémo d'urgence. Quelles sont vos trois actions prioritaires ? Comment isolez-vous le problème ? Comment communiquez-vous pour éviter que d'autres collaborateurs ne cliquent à leur tour ?
- **Visuel suggéré** : Un post-it virtuel rouge marqué "Urgence Ransomware EcoLog" à côté d'un bloc-notes de rédaction de plan de crise.
  - **alt-text** : Exercice de rédaction d'un mémo de crise cybersécurité.
- **Élément interactif** : Discussion interactive de 20 minutes avec partage des plans de crise rédigés par les apprenants.

---

### Slide 11 — Quiz de validation
- **Type** : quiz
- **Points clés (bullets)** :
  - 1. Quelle étape du cycle SANS de réponse aux incidents consiste à isoler les hôtes infectés pour bloquer la propagation ?
  - 2. Pourquoi un analyste forensique évite-t-il d'éteindre brutalement une machine en cours d'attaque ?
  - 3. À quoi sert le calcul de l'empreinte SHA-256 lors de la copie d'un disque dur compromis ?
- **Notes orateur** : Validons nos acquis sur la gestion d'incidents et le forensics. Répondez aux trois questions pour vérifier vos connaissances sur le confinement, la conservation de la mémoire vive et l'intégrité des preuves.
- **Visuel suggéré** : QR Code d'accès au système de vote à gauche et questions interactives à droite.
  - **alt-text** : QR Code d'accès au vote synchrone de validation.
- **Élément interactif** : Quiz interactif avec statistiques de réponses et débriefing oral.

---

### Slide 12 — Conclusion & Clôture du module
- **Type** : récap
- **Points clés (bullets)** :
  - **Résumé** : Processus SANS/NIST de réponse, isolation réseau (pas d'extinction brute), forensics (chaîne de contrôle, hashs d'intégrité), approche de pentest et structure du RPI.
  - **Devoirs** : Compléter le module *"Incident Response Fundamentals"* sur IBM SkillsBuild (~1h30).
  - **Préparation** : Relire les supports de cours des sessions B01 à B19 pour se préparer au **Grand Atelier d'Audit Final** (Session B20).
  - Prochaine session : *Grand Atelier d'Audit & Clôture du parcours (B20)*.
- **Notes orateur** : Nous avons terminé notre module dédié aux opérations de détection et de réponse à incident ! Validez votre cours SkillsBuild et révisez bien les notions du parcours. La semaine prochaine sera notre dernière session synchrone. Ce sera notre grand atelier d'audit interactif MedDistri et la clôture de ce parcours de formation en cybersécurité. Révisez bien et à la semaine prochaine pour le grand final !
- **Visuel suggéré** : Badge d'achèvement de cours d'IBM SkillsBuild pour la réponse aux incidents de sécurité.
  - **alt-text** : Badge de réussite du cours Incident Response d'IBM SkillsBuild.
