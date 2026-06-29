# Spécifications des slides — Session B01 : Introduction à la cybersécurité & triade CIA
Parcours : B 20 sessions  |  Module : A — Fondations  |  Format : Spécifications Markdown

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Introduction à la cybersécurité
  - Le socle fondamental : la Triade CIA
  - Parcours B — Session B01
- **Notes orateur** : Bienvenue à tous dans cette première session synchrone du parcours Cybersécurité. Aujourd'hui, nous posons les fondations indispensables qui guideront tout notre parcours. Nous allons explorer les trois concepts clés de la protection des données et voir comment ils se traduisent dans le monde professionnel.
- **Visuel suggéré** : Un fond sobre gris anthracite et blanc avec une touche de vert cyberpunk. Une illustration abstraite représentant des réseaux connectés de manière sécurisée.
  - **alt-text** : Graphisme abstrait montrant des lignes de connexion lumineuses vertes sur un fond sombre de circuit imprimé.
- **Élément interactif** : Sondage de bienvenue à main levée pour vérifier la bonne réception audio et vidéo.

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Définir les trois piliers de la Triade CIA (CID).
  - Évaluer l'impact financier, juridique et réputationnel d'une cyberattaque.
  - Différencier les postures offensives (Red Team) et défensives (Blue Team).
  - Sommaire : Brise-glace (15 min), Théorie & CIA (20 min), Impacts business (15 min), Activité Qualification d'incidents (30 min), Quiz & Devoirs (10 min).
- **Notes orateur** : Voici la feuille de route pour nos 90 minutes ensemble. Nous allons allier théorie et pratique, en terminant par une étude de cas en sous-groupes. L'objectif est qu'en sortant d'ici, vous sachiez qualifier n'importe quel incident informatique et compreniez les rôles au sein d'une équipe cyber.
- **Visuel suggéré** : Disposition en deux colonnes. À gauche, une icône de cible pour les objectifs. À droite, une icône de liste ordonnée pour le sommaire.
  - **alt-text** : Icône de cible verte à gauche et une liste de cinq points à droite sur fond clair.

---

### Slide 3 — Brise-glace : Le monde sans sécurité
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Que se passerait-il si votre smartphone cessait de fonctionner ?
  - Et si le système de feux de signalisation d'une ville était piraté ?
  - Imaginez vos données bancaires publiées en ligne.
- **Notes orateur** : Pour commencer, réfléchissons à notre dépendance vis-à-vis du numérique. Imaginez un monde où plus aucun appareil connecté n'est protégé. Partagez dans le chat vos réflexions sur le premier impact auquel vous pensez si l'un de ces scénarios se produisait aujourd'hui.
- **Visuel suggéré** : Image conceptuelle contrastée montrant un smartphone affichant un signal d'avertissement et un carrefour routier encombré.
  - **alt-text** : Illustration d'un écran de smartphone avec une alerte rouge et d'une ville en arrière-plan aux feux de circulation éteints.
- **Élément interactif** : Tempête d'idées (brainstorming) dans le chat avec partage oral de deux apprenants.

---

### Slide 4 — Le pilier de base : La Triade CIA / CID
- **Type** : schéma
- **Points clés (bullets)** :
  - **C**onfidentialité (Confidentiality)
  - **I**ntégrité (Integrity)
  - **A**uthenticité ou **D**isponibilité (Availability)
  - Un modèle universel pour qualifier le besoin de sécurité.
- **Notes orateur** : En cybersécurité, tout commence par ce modèle fondamental nommé CIA ou CID en français. Il structure l'analyse de tous les risques informatiques. Voyons en détail chacun de ces concepts avec des analogies simples de notre vie quotidienne.
- **Visuel suggéré** : Schéma d'un triangle équilatéral dont chaque sommet représente l'un des piliers : C (cadenas), I (clé plate/validation), A (sablier/horloge).
  - **alt-text** : Schéma montrant un triangle reliant Confidentialité, Intégrité et Disponibilité avec des icônes explicatives pour chaque notion.

---

### Slide 5 — Confidentialité : Protéger le secret
- **Type** : contenu
- **Points clés (bullets)** :
  - **Définition** : L'information n'est accessible qu'aux personnes autorisées.
  - **Analogie** : Une lettre scellée avec de la cire.
  - **Exemples de contrôle** : Chiffrement des données, gestion des mots de passe.
  - **Incident type** : Fuite de données médicales ou vol de secrets de fabrication.
- **Notes orateur** : La confidentialité garantit que seuls ceux qui ont le droit de voir l'information peuvent y accéder. Si une personne non autorisée y accède, le secret est rompu, même si les données ne sont pas modifiées.
- **Visuel suggéré** : Une enveloppe de courrier classique scellée par un cachet de cire rouge.
  - **alt-text** : Enveloppe en papier kraft fermée par un sceau de cire rouge traditionnel sur fond texturé.

---

### Slide 6 — Intégrité : Garantir l'exactitude
- **Type** : contenu
- **Points clés (bullets)** :
  - **Définition** : La donnée n'est pas modifiée, corrompue ou falsifiée.
  - **Analogie** : Un registre écrit à l'encre indélébile où aucune rature n'est possible.
  - **Exemples de contrôle** : Hachage, signatures numériques, droits d'accès limités.
  - **Incident type** : Modification malveillante d'un RIB sur une facture.
- **Notes orateur** : L'intégrité concerne la fiabilité de l'information. Si un attaquant modifie un chiffre dans une base de données financière sans que personne ne s'en aperçoive, c'est l'intégrité qui est directement violée.
- **Visuel suggéré** : Un document officiel signé avec un stylo plume à côté d'un symbole de validation ou de coche verte.
  - **alt-text** : Feuille de papier avec une signature manuscrite élégante et un tampon de validation vert.

---

### Slide 7 — Disponibilité : Assurer l'accès
- **Type** : contenu
- **Points clés (bullets)** :
  - **Définition** : Les systèmes et données sont accessibles quand les utilisateurs en ont besoin.
  - **Analogie** : L'interrupteur électrique qui allume instantanément la pièce.
  - **Exemples de contrôle** : Sauvegardes régulières, serveurs redondants.
  - **Incident type** : Attaque DDoS bloquant l'accès à un site de e-commerce.
- **Notes orateur** : Enfin, la disponibilité s'assure que le service fonctionne. Si les serveurs tombent en panne ou sont surchargés par une attaque, l'information peut être confidentielle et intègre, mais elle est inutile si personne ne peut y accéder.
- **Visuel suggéré** : Un serveur informatique avec des voyants verts allumés et une flèche circulaire indiquant le fonctionnement continu.
  - **alt-text** : Baie de serveurs dans un centre de données avec des indicateurs LED de fonctionnement au vert.

---

### Slide 8 — Activité pratique : Qualification d'incidents
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Scénario A : Rançongiciel dans un hôpital (fichiers chiffrés).
  - Scénario B : Modification illégitime d'une note d'examen par un étudiant.
  - Scénario C : Fichier client stocké sur un serveur web public.
  - **Consignes** : Identifiez le pilier rompu et proposez une action corrective en sous-groupes (30 min).
- **Notes orateur** : Nous allons maintenant passer à la pratique. En sous-groupes, vous analyserez ces trois situations concrètes. Votre tâche est de définir quel pilier de la triade a été brisé en premier et de proposer une solution de bon sens pour que cela ne se reproduise pas.
- **Visuel suggéré** : Les trois scénarios présentés sous forme de fiches ou de cartes colorées. Un chronomètre affichant 30 minutes.
  - **alt-text** : Trois panneaux représentant chacun un scénario d'incident cyber avec des bordures colorées distinctives.
- **Élément interactif** : Travail collaboratif en sous-salles virtuelles.

---

### Slide 9 — Impacts business d'une cyberattaque
- **Type** : contenu
- **Points clés (bullets)** :
  - **Impact financier direct** : Perte d'exploitation, frais d'experts, rançons.
  - **Impact juridique** : Sanctions RGPD, litiges avec les clients et partenaires.
  - **Impact réputationnel** : Perte de confiance définitive, fuite des clients.
- **Notes orateur** : Une cyberattaque n'est pas qu'un problème informatique. C'est un séisme pour toute l'entreprise. En moyenne, une cyberattaque peut conduire au dépôt de bilan pour les PME les plus fragiles, principalement à cause de la perte de réputation et de la baisse des ventes.
- **Visuel suggéré** : Graphique en secteurs ou en barres illustrant la répartition des coûts après une intrusion (remédiation, perte d'exploitation, amende).
  - **alt-text** : Graphique illustrant les coûts financiers, juridiques et réputationnels d'une faille de sécurité.

---

### Slide 10 — Les métiers de la cybersécurité
- **Type** : contenu
- **Points clés (bullets)** :
  - **Red Team** : Posture offensive (simuler les attaques, tests d'intrusion).
  - **Blue Team** : Posture défensive (surveillance, SOC, réaction sur incident).
  - **RSSI / CISO** : Management et gouvernance, lien avec la direction générale.
- **Notes orateur** : Pour se défendre, une entreprise doit organiser ses équipes. Nous avons d'un côté la Blue Team, les protecteurs au quotidien, et de l'autre la Red Team, qui joue le rôle de l'attaquant pour tester nos failles. Le RSSI pilote le tout pour assurer la conformité et la stratégie globale.
- **Visuel suggéré** : Deux personnages ou silhouettes stylisées représentant la défense (bouclier bleu) et l'attaque (couteau/cible rouge), sous la direction d'un gestionnaire de projet (RSSI).
  - **alt-text** : Schéma divisé en deux sections : Blue Team avec bouclier bleu et Red Team avec épée rouge, surmontées par le rôle du RSSI.

---

### Slide 11 — Quiz de session
- **Type** : quiz
- **Points clés (bullets)** :
  - Question 1 : Le chiffrement garantit-il la disponibilité ?
  - Question 2 : Le vol de mots de passe enfreint-il la confidentialité ?
  - Question 3 : Quelle équipe simule des cyberattaques ?
- **Notes orateur** : Testons vos connaissances immédiates avant de nous quitter. Connectez-vous à l'outil de vote à l'aide du lien affiché. C'est anonyme et cela permet de faire le point.
- **Visuel suggéré** : Un QR code volumineux pointant vers l'interface de vote interactif et les trois questions listées clairement.
  - **alt-text** : QR code de grande taille à gauche et trois questions à choix multiples à droite.
- **Élément interactif** : Quiz en temps réel via l'application interactive.

---

### Slide 12 — Conclusion & Travail autonome
- **Type** : récap
- **Points clés (bullets)** :
  - **Triade CIA** : Confidentialité, Intégrité, Disponibilité.
  - **Devoirs autonomes** : Cours IBM SkillsBuild "Cybersecurity Fundamentals - Part 1" (~1h30).
  - **Veille** : Lire le dernier rapport de menace de l'ANSSI.
  - Prochaine session : *Paysage des menaces & acteurs (B02)*.
- **Notes orateur** : Merci pour votre participation aujourd'hui ! Pour préparer notre prochaine session sur les attaquants et leurs motivations, n'oubliez pas de valider le module sur IBM SkillsBuild. Excellente fin de journée à tous et à la semaine prochaine !
- **Visuel suggéré** : Icône de validation de badge de cours SkillsBuild et logo de l'ANSSI.
  - **alt-text** : Badge de complétion de cours numérique et logo institutionnel de l'ANSSI.
