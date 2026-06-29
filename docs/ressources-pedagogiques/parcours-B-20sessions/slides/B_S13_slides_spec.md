# Spécifications des slides — Session B13 : Gouvernance & cadres de sécurité
Parcours : B 20 sessions  |  Module : D — Gouvernance, risque & conformité  |  Format : Spécifications Markdown

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Gouvernance & cadres de sécurité
  - PSSI, cadres ISO 27001 et NIST CSF, et rôles de gouvernance en entreprise
  - Parcours B — Session B13
- **Notes orateur** : Bonjour et bienvenue à tous. Nous démarrons aujourd'hui notre quatrième module consacré à la Gouvernance, au Risque et à la Conformité (GRC). Dans cette treizième session, nous allons étudier comment structurer la sécurité à l'échelle d'une organisation : qu'est-ce qu'une PSSI, comment utiliser les standards internationaux comme l'ISO 27001 et le NIST CSF, et quel est le rôle du responsable de la sécurité des systèmes d'information (RSSI).
- **Visuel suggéré** : Vue d'une salle de conseil d'administration futuriste avec une table holographique affichant des structures de gouvernance, des logos de conformité et des boucliers verts de sécurité.
  - **alt-text** : Salle de réunion d'entreprise avec des éléments graphiques de gouvernance de sécurité.
- **Élément interactif** : Question sondage : "Qui a déjà entendu parler de la norme ISO 27001 ou du cadre NIST ?"

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Expliquer le rôle et la structure d'une Politique de Sécurité des Systèmes d'Information (PSSI).
  - Présenter de manière vulgarisée les cadres internationaux ISO/IEC 27001 et NIST CSF.
  - Définir les responsabilités et la posture du RSSI dans la gouvernance d'une entreprise.
  - Sommaire : La PSSI, brique fondatrice (25 min), Les Cadres de référence : ISO 27001 & NIST (25 min), Le Rôle stratégique du RSSI (20 min), Exercice de rédaction d'une règle de PSSI (10 min), Quiz (10 min).
- **Notes orateur** : Nous allons commencer par étudier la PSSI, qui est la loi interne de l'entreprise en matière de sécurité. Ensuite, nous analyserons les deux grands référentiels mondiaux : l'ISO 27001 et le NIST CSF. Nous verrons ensuite le rôle clé du RSSI avant de faire un exercice pratique de rédaction de règle de sécurité et notre quiz final.
- **Visuel suggéré** : Les compétences visées sous forme d'une checklist graphique, avec à côté le planning temporel minuté de la séance.
  - **alt-text** : Tableau d'agenda minuté de la session synchrone de gouvernance de 90 minutes.

---

### Slide 3 — Qu'est-ce qu'une PSSI ?
- **Type** : contenu
- **Points clés (bullets)** :
  - **PSSI** : Politique de Sécurité des Systèmes d'Information.
  - Document stratégique qui définit les objectifs, les règles de sécurité et les responsabilités d'un organisme.
  - **La "Loi" interne de l'entreprise** en matière de cybersécurité.
  - Rédigée par le RSSI, mais **obligatoirement signée et validée par la Direction Générale** pour avoir une force exécutoire.
  - S'adresse à tous les utilisateurs (collaborateurs, prestataires, partenaires).
- **Notes orateur** : La PSSI n'est pas un document technique pour les administrateurs système. C'est la charte officielle de sécurité de l'entreprise. Elle définit ce qui est autorisé et ce qui est interdit. Pour qu'elle ait une valeur réelle, elle doit être signée par le PDG. Si la direction générale ne la soutient pas, personne ne l'appliquera.
- **Visuel suggéré** : Un document officiel relié affichant le titre "PSSI" avec une signature manuscrite dorée et un sceau de cire officiel de l'entreprise.
  - **alt-text** : Livre de règles PSSI validé et signé par la direction de l'entreprise.

---

### Slide 4 — Structure type d'une PSSI
- **Type** : schéma
- **Points clés (bullets)** :
  - Une PSSI s'organise en plusieurs chapitres thématiques :
    - **Règles utilisateurs** : Usage des mots de passe, télétravail, utilisation du matériel informatique personnel (BYOD).
    - **Règles techniques** : Durcissement des serveurs, politique de correctifs, chiffrement des disques.
    - **Gestion des incidents** : Signalement des anomalies, procédure en cas de violation de données.
    - **Sanctions** : Conséquences juridiques et disciplinaires en cas de non-respect volontaire.
- **Notes orateur** : Une PSSI couvre l'ensemble des aspects de l'entreprise. Elle s'organise par grands thèmes. Elle définit l'usage des mots de passe pour les collaborateurs, les méthodes de durcissement technique pour les informaticiens et les procédures d'alerte en cas d'attaque informatique. Elle doit aussi mentionner les sanctions en cas de violation des règles.
- **Visuel suggéré** : Organigramme montrant le tronc commun d'une PSSI se divisant en quatre branches thématiques colorées.
  - **alt-text** : Arborescence thématique d'un document complet de PSSI.

---

### Slide 5 — Norme ISO/IEC 27001 : Le SMSI
- **Type** : contenu
- **Points clés (bullets)** :
  - Référence mondiale pour la gestion de la sécurité de l'information.
  - Ne définit pas des règles techniques strictes, mais une **méthode organisationnelle**.
  - **SMSI (Système de Management de la Sécurité de l'Information)**.
  - Repose sur l'amélioration continue (Roue de Deming / PDCA) :
    - *Plan* : Planifier les objectifs et risques.
    - *Do* : Mettre en œuvre les mesures de sécurité.
    - *Check* : Auditer et mesurer l'efficacité.
    - *Act* : Améliorer les processus.
- **Notes orateur** : L'ISO 27001 est la norme internationale la plus connue. Elle ne vous dit pas "configurez tel pare-feu", elle vous dit "comment gérer la sécurité en continu". Elle utilise le concept de SMSI et la méthode d'amélioration continue PDCA. On planifie, on applique, on contrôle l'efficacité et on corrige ce qui ne va pas pour redémarrer un cycle.
- **Visuel suggéré** : Représentation graphique de la roue de Deming (PDCA : Plan, Do, Check, Act) tournant de manière continue le long d'une flèche de progression.
  - **alt-text** : La roue du PDCA appliquée à l'amélioration continue du SMSI.

---

### Slide 6 — NIST CSF (Cybersecurity Framework)
- **Type** : schéma
- **Points clés (bullets)** :
  - Cadre de sécurité pragmatique créé par le gouvernement américain.
  - Divise les activités de cybersécurité en **5 fonctions clés** :
    - **Identify (Identifier)** : Cartographier les actifs, risques et processus.
    - **Protect (Protéger)** : Mettre en œuvre les barrières de défense (pare-feux, IAM).
    - **Detect (Détecter)** : Surveiller pour identifier l'apparition d'incidents (SIEM).
    - **Respond (Répondre)** : Contenir l'attaque et communiquer.
    - **Recover (Restaurer)** : Reconstruire et reprendre l'activité.
- **Notes orateur** : Le cadre NIST CSF est très apprécié pour son approche opérationnelle. Il classe tout ce que doit faire un service cyber en 5 fonctions claires. De la cartographie des risques au début, jusqu'à la reconstruction après une attaque à la fin. C'est une excellente grille de lecture pour auditer la maturité d'une entreprise.
- **Visuel suggéré** : Un pentagone divisé en 5 segments de couleurs différentes représentant les fonctions du NIST : Identify (bleu), Protect (violet), Detect (jaune), Respond (orange), Recover (rouge).
  - **alt-text** : Représentation circulaire des 5 fonctions du NIST Cybersecurity Framework.

---

### Slide 7 — Le rôle du RSSI (CISO)
- **Type** : contenu
- **Points clés (bullets)** :
  - **RSSI** : Responsable de la Sécurité des Systèmes d'Information.
  - **Rôle transverse** : Il n'est pas qu'un profil technique, c'est un communicant et un gestionnaire de risques.
  - Ses missions majeures :
    - Analyser les risques et proposer des solutions à la direction.
    - Rédiger et faire appliquer la PSSI.
    - Sensibiliser et former les collaborateurs.
    - Coordonner la réponse aux incidents de sécurité.
  - Il doit aligner la sécurité sur les objectifs métier de l'entreprise.
- **Notes orateur** : Le RSSI est souvent vu à tort comme le censeur technique qui dit "non" à tout. Un bon RSSI est au contraire un facilitateur d'activité. Son rôle est de traduire les risques techniques en risques métier compréhensibles pour la direction et de proposer des mesures de sécurité réalistes qui n'empêchent pas les collaborateurs de travailler.
- **Visuel suggéré** : Silhouette d'un professionnel en costume tenant une tablette de sécurité, servant de pont entre une équipe technique (serveurs) et une équipe de direction (bureau de réunion).
  - **alt-text** : Le positionnement transverse du RSSI entre la technique et les métiers.

---

### Slide 8 — Le positionnement du RSSI dans l'organisation
- **Type** : schéma
- **Points clés (bullets)** :
  - **Mauvaise pratique** : Rattaché directement au Directeur Informatique (DSI).
    - *Conflit d'intérêts* : Le DSI veut de la vitesse et du budget pour les projets ; le RSSI veut de la sécurité qui peut ralentir les projets.
  - **Bonne pratique** : Rattaché à la Direction Générale (DG) ou à la Direction des Risques.
    - Garantit l'indépendance du RSSI et lui donne le poids nécessaire pour imposer des règles de sécurité à la DSI si besoin.
- **Notes orateur** : Où doit-on placer le RSSI dans l'organigramme ? Si vous le rattachez au DSI, il y a un conflit d'intérêts permanent. Le DSI cherche à livrer des outils rapidement et à moindre coût, ce qui s'oppose parfois aux exigences de sécurité du RSSI. Pour éviter cela, le RSSI doit être rattaché à la direction générale pour pouvoir alerter de manière indépendante.
- **Visuel suggéré** : Organigramme comparant le rattachement direct sous le DSI (marqué d'une croix rouge) et le rattachement sous la Direction Générale (marqué d'une coche verte).
  - **alt-text** : Organigrammes de structure de rattachement du RSSI en entreprise.

---

### Slide 9 — Sensibilisation des utilisateurs : Le maillon humain
- **Type** : contenu
- **Points clés (bullets)** :
  - Les meilleures protections techniques s'effondrent si les utilisateurs ne sont pas formés.
  - **Ingénierie sociale** : Manipulation psychologique pour pousser à l'erreur (ex: Phishing).
  - Moyens d'action du RSSI :
    - Campagnes de faux phishing internes pour évaluer et éduquer.
    - Formations courtes et ludiques (micro-learning).
    - Charte informatique claire annexée au règlement intérieur.
- **Notes orateur** : On dit souvent que l'utilisateur est le maillon faible de la sécurité. En réalité, c'est surtout le premier rempart s'il est bien formé. L'ingénierie sociale exploite la confiance des gens. Le rôle du RSSI est de sensibiliser régulièrement les collaborateurs pour qu'ils sachent repérer un e-mail de phishing et sachent à qui le signaler immédiatement.
- **Visuel suggéré** : Illustration d'un hameçon de pêche numérique (phishing) tentant d'attraper un mot de passe devant un utilisateur attentif qui clique sur un bouton d'alerte rouge.
  - **alt-text** : Graphisme de sensibilisation contre les attaques de phishing.

---

### Slide 10 — Activité pratique : Rédiger une règle de PSSI
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **Scénario** : EcoLog veut interdire l'usage des clés USB personnelles sur les ordinateurs de l'entreprise en raison des risques de vol de données et de malwares.
  - **Mission** : Rédiger la règle de PSSI correspondante.
  - **Consignes de rédaction** :
    - La règle doit être courte, claire et compréhensible par un non-technicien.
    - Elle doit expliquer la règle (quoi), la justification (pourquoi) et la sanction en cas de non-respect.
- **Notes orateur** : Dans cet atelier pratique, vous allez vous mettre dans la peau d'un RSSI. Vous devez rédiger une règle de PSSI pour interdire l'usage des clés USB personnelles chez EcoLog. Gardez à l'esprit que ce texte sera lu par tous les salariés, des ingénieurs aux secrétaires. Il doit être simple, expliquer le danger réel et fixer les limites claires de l'usage autorisé.
- **Visuel suggéré** : Page blanche de traitement de texte avec un modèle de paragraphe de PSSI surligné pour l'exercice.
  - **alt-text** : Gabarit d'écriture d'une règle de sécurité PSSI.
- **Élément interactif** : Travail individuel ou en binôme de 10 minutes avec lecture et critique constructive des règles produites.

---

### Slide 11 — Quiz de validation
- **Type** : quiz
- **Points clés (bullets)** :
  - 1. Qui doit obligatoirement valider et signer la PSSI pour lui donner une force exécutoire ?
  - 2. Quelle est la différence majeure d'approche entre l'ISO 27001 et le NIST CSF ?
  - 3. Pourquoi le rattachement du RSSI au DSI peut-il poser un problème de gouvernance ?
- **Notes orateur** : Passons au quiz pour valider ces notions essentielles de gouvernance d'entreprise. Connectez-vous sur votre outil de vote habituel et répondez aux questions.
- **Visuel suggéré** : QR Code d'accès au vote interactif à gauche, questions à choix multiples à droite.
  - **alt-text** : QR Code d'accès aux votes synchrones de validation.
- **Élément interactif** : Vote en ligne en direct avec restitution immédiate des résultats.

---

### Slide 12 — Conclusion & Travail autonome
- **Type** : récap
- **Points clés (bullets)** :
  - **Résumé** : PSSI (loi interne d'entreprise), ISO 27001 (SMSI/amélioration continue), NIST CSF (5 fonctions d'évaluation), et RSSI (gestionnaire transverse de risques rattaché à la DG).
  - **Devoirs** : Compléter le cours *"Information Security Governance"* sur IBM SkillsBuild (~1h30).
  - **Lecture** : Parcourir le site de l'ANSSI pour découvrir le *"Guide d'élaboration d'une PSSI"*.
  - Prochaine session : *Gestion des risques (B14)*.
- **Notes orateur** : Nous avons posé les bases de la gouvernance de la sécurité ! Prenez le temps de faire le cours SkillsBuild et de regarder les documents méthodologiques de l'ANSSI. La semaine prochaine, nous verrons comment identifier et évaluer concrètement les risques pour décider des investissements de sécurité à mener. À la semaine prochaine !
- **Visuel suggéré** : Badge d'achèvement de cours d'IBM SkillsBuild pour la gouvernance de la sécurité.
  - **alt-text** : Badge de réussite du cours Security Governance d'IBM SkillsBuild.
