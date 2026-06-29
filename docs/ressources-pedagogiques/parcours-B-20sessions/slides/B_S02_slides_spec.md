# Spécifications des slides — Session B02 : Paysage des menaces & acteurs
Parcours : B 20 sessions  |  Module : A — Fondations  |  Format : Spécifications Markdown

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Paysage des menaces & acteurs de la cybercriminalité
  - Qui nous attaque et pourquoi ?
  - Parcours B — Session B02
- **Notes orateur** : Bonjour et bienvenue à cette deuxième session. Aujourd'hui, nous sortons du cadre théorique de la triade CIA pour explorer le profil réel des attaquants. Comprendre l'ennemi, ses motivations et ses ressources est la clé d'une défense ciblée et efficace.
- **Visuel suggéré** : Fond sombre avec une illustration stylisée montrant des silhouettes floues devant des écrans de contrôle.
  - **alt-text** : Silhouettes floutées d'acteurs de menace devant des écrans rétroéclairés de serveurs informatiques.
- **Élément interactif** : Sondage rapide sur la perception du profil type d'un cyberattaquant moderne.

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Catégoriser les quatre profils clés de cyberattaquants.
  - Comprendre l'économie criminelle moderne (Ransomware-as-a-Service).
  - Découvrir la Cyber Threat Intelligence (CTI) et ses outils de veille.
  - Sommaire : Activité introductive (10 min), Typologie des acteurs (25 min), L'économie cybercriminelle (20 min), Activité Fiche APT (25 min), Quiz (10 min).
- **Notes orateur** : Nous allons aujourd'hui casser certains clichés sur le "hacker" et analyser le modèle économique derrière la cybercriminalité moderne. Nous ferons ensuite un exercice pratique pour étudier le profil d'un groupe étatique réel.
- **Visuel suggéré** : Deux colonnes claires séparant les objectifs opérationnels et le minutage de l'agenda.
  - **alt-text** : Tableau ordonné présentant les objectifs d'apprentissage à gauche et les jalons horaires de la séance à droite.

---

### Slide 3 — Pourquoi attaque-t-on ?
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Quel est le point commun entre toutes les cyberattaques ?
  - La diversité des motivations sous-jacentes.
  - L'argent, la géopolitique, l'idéologie, la vengeance.
- **Notes orateur** : Avant de détailler les profils, interrogeons-nous : qu'est-ce qui pousse des personnes à passer des semaines à chercher des vulnérabilités dans des systèmes informatiques ? Échangeons sur ce sujet.
- **Visuel suggéré** : Schéma conceptuel reliant un globe terrestre, un symbole monétaire (dollar/euro), un mégaphone et une clé d'accès.
  - **alt-text** : Diagramme conceptuel liant les quatre piliers de motivation cyber : gain financier, espionnage étatique, idéologie hacktiviste et rancœur interne.
- **Élément interactif** : Discussion ouverte et recueil d'hypothèses sur le chat ou par micro.

---

### Slide 4 — Les quatre familles d'attaquants
- **Type** : schéma
- **Points clés (bullets)** :
  - **Cybercriminels** : Gain financier.
  - **États-nations (APT)** : Espionnage et géopolitique.
  - **Hacktivistes** : Idéologie et contestation.
  - **Menaces internes** : Malveillance ou négligence d'employés.
- **Notes orateur** : On classe les attaquants en quatre grandes catégories distinctes. Chacune a des motivations, des cibles et des ressources différentes. Analysons comment cette distinction influence nos stratégies de défense.
- **Visuel suggéré** : Une matrice ou un schéma en 4 quadrants présentant les profils avec des icônes distinctives : sac de pièces, radar géopolitique, poing levé et silhouette d'un utilisateur interne.
  - **alt-text** : Grille à 4 quadrants présentant les types d'attaquants, leurs cibles principales et leurs budgets respectifs.

---

### Slide 5 — Les Cybercriminels : Une industrie lucrative
- **Type** : contenu
- **Points clés (bullets)** :
  - Motivation unique : le gain financier.
  - Cibles : tout système vulnérable contenant de la valeur.
  - Méthodes reines : Ransomware-as-a-Service, vols de cartes bancaires.
  - La professionnalisation des services de support et de blanchiment.
- **Notes orateur** : Les cybercriminels représentent la majorité des cyberattaques quotidiennes. Ce ne sont pas des pirates isolés, mais des organisations structurées comme des entreprises traditionnelles, dotées de développeurs, de négociateurs et même de services clients d'aide au paiement.
- **Visuel suggéré** : Une image de coffre-fort numérique ouvert révélant des lignes de code et des pièces de monnaie numériques.
  - **alt-text** : Coffre-fort virtuel entrouvert avec des flux de données et des symboles de cryptomonnaie dorés sur fond sombre.

---

### Slide 6 — Les États-nations & Groupes APT
- **Type** : contenu
- **Points clés (bullets)** :
  - **APT** : *Advanced Persistent Threat* (Menace persistante avancée).
  - Motivation : Espionnage industriel, politique et sabotage géopolitique.
  - Ressources : budgets gouvernementaux illimités, exploits inconnus (*zero-days*).
  - Approche : persistance discrète pendant des mois ou des années.
- **Notes orateur** : Les groupes APT sont parrainés par des gouvernements. Contrairement aux cybercriminels ordinaires, ils cherchent la discrétion absolue pour voler de la propriété intellectuelle ou se positionner dans des infrastructures critiques (réseaux d'eau, d'électricité) en vue de sabotages futurs.
- **Visuel suggéré** : Icône de radar militaire ou de loupe analysant une cible discrète dans un système.
  - **alt-text** : Radar circulaire vert scannant une carte du monde stylisée avec des points de connexion.

---

### Slide 7 — Hacktivistes & Menaces internes
- **Type** : contenu
- **Points clés (bullets)** :
  - **Hacktivisme** : Pirater pour une cause politique ou sociale (Ex : DDoS, défiguration de sites).
  - **Menace interne** : Un utilisateur légitime (employé, prestataire) qui abuse de ses accès.
  - Motivation interne : appât du gain, vengeance de salarié licencié, ou simple négligence.
  - La menace interne est la plus difficile à détecter car les actions sont légitimes au départ.
- **Notes orateur** : D'un côté, les hacktivistes veulent de la visibilité pour leur cause en bloquant des sites web ou en publiant des documents confidentiels. De l'autre, la menace interne utilise ses privilèges existants au sein du réseau, ce qui la rend extrêmement difficile à détecter par des outils de sécurité réseau standards.
- **Visuel suggéré** : Division verticale montrant à gauche un écran affichant un site défiguré (mégaphone) et à droite un badge d'accès d'entreprise posé à côté d'une clé USB.
  - **alt-text** : Illustration comparative : à gauche un écran piraté avec un logo militant, à droite une clé USB insérée par un employé de bureau.

---

### Slide 8 — L'économie criminelle moderne : Le RaaS
- **Type** : schéma
- **Points clés (bullets)** :
  - **Ransomware-as-a-Service (RaaS)** : Modèle d'affiliation cybercriminel.
  - **Les Opérateurs** : Développent le logiciel malveillant et l'infrastructure.
  - **Les Affiliés** : Achètent l'accès, pénètrent le réseau cible et déploient l'attaque.
  - Partage des gains : 70-80 % pour l'affilié, 20-30 % pour l'opérateur.
- **Notes orateur** : Le modèle du RaaS a révolutionné la cybercriminalité en permettant à des attaquants peu techniques de louer des outils de pointe. C'est cette division du travail qui explique l'explosion du nombre d'attaques par rançongiciel ces dernières années.
- **Visuel suggéré** : Schéma conceptuel du flux RaaS : Opérateur (Code) $\rightarrow$ Plateforme de distribution $\rightarrow$ Affilié (Intrusion) $\rightarrow$ Victime (Rançon) $\rightarrow$ Partage des profits.
  - **alt-text** : Diagramme du cycle d'affaires du Ransomware-as-a-Service décrivant les rôles de l'opérateur, de l'affilié et le flux de partage des cryptomonnaies.

---

### Slide 9 — Cyber Threat Intelligence (CTI) : Connaître son ennemi
- **Type** : contenu
- **Points clés (bullets)** :
  - **CTI** : Collecte et analyse d'informations sur les menaces actives.
  - **IoC (Indicateurs de compromission)** : Signes techniques laissés par l'attaquant (IP, signatures de fichiers).
  - Sources fiables : Bulletins d'alerte du CERT-FR, base de connaissances MITRE ATT&CK.
  - Permet d'anticiper les attaques plutôt que de simplement y réagir.
- **Notes orateur** : Pour se défendre efficacement, il faut faire de la veille. La Cyber Threat Intelligence nous donne les armes nécessaires : en étudiant les signatures de fichiers et les adresses IP utilisées par les groupes d'attaquants, nous pouvons bloquer proactivement leurs tentatives avant qu'ils n'atteignent nos systèmes.
- **Visuel suggéré** : Logo de la base de données MITRE ATT&CK ou extrait d'un tableau d'indicateurs de compromission (IoC).
  - **alt-text** : Capture de tableau structurant des indicateurs de compromission techniques avec des adresses IP malveillantes et des hashs MD5 associés.

---

### Slide 10 — Activité pratique : Fiche d'identité APT
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **Cas d'étude** : Lazarus Group (APT38).
  - Analyse d'un rapport de Threat Intelligence simplifié.
  - **Consignes** : Remplir la fiche d'identité (25 min en groupes).
    - Identifier : Catégorie d'acteur, origines, motivations, cibles et techniques clés.
- **Notes orateur** : Nous allons maintenant réaliser une activité pratique. Vous allez étudier un résumé opérationnel sur le groupe Lazarus. Votre objectif est de dresser sa fiche d'identité afin de comprendre comment un État-nation peut utiliser la cybercriminalité financière pour contourner des sanctions internationales.
- **Visuel suggéré** : Fiche d'identité à remplir affichant des champs vides (Nom, Origine, Cibles, Méthodes) à côté d'une photo conceptuelle de carte du monde.
  - **alt-text** : Gabarit de document de renseignement cyber avec des zones de saisie vides pour documenter un profil d'attaquant.
- **Élément interactif** : Travail collaboratif en équipe avec restitution sur un tableau partagé.

---

### Slide 11 — Quiz de validation
- **Type** : quiz
- **Points clés (bullets)** :
  - 1. Quel profil d'attaquant est motivé par l'espionnage géopolitique ?
  - 2. Qu'est-ce qu'un "Initial Access Broker" ?
  - 3. Que signifie l'acronyme CTI ?
- **Notes orateur** : Évaluons rapidement ce que nous avons appris aujourd'hui. Lisez les questions affichées et sélectionnez la bonne réponse sur vos smartphones. Nous analyserons ensuite les points qui ont posé problème.
- **Visuel suggéré** : QR code d'accès au questionnaire interactif avec trois questions à choix multiples à côté.
  - **alt-text** : Code QR stylisé vert clair et questions de quiz affichées dans une police moderne sans-serif.
- **Élément interactif** : Questionnaire de fin de session en temps réel.

---

### Slide 12 — Conclusion & Travail autonome
- **Type** : récap
- **Points clés (bullets)** :
  - **Points clés** : 4 profils d'attaquants, modèle RaaS, utilisation des IoC et de la veille.
  - **Devoirs** : Suivre le cours IBM SkillsBuild *"Cybersecurity Threat Landscape"* (~1h30).
  - **Action pratique** : Consulter les alertes actives du CERT-FR sur leur site officiel.
  - Prochaine session : *Types d'attaques & vecteurs (B03)*.
- **Notes orateur** : Merci pour votre attention et vos échanges pertinents aujourd'hui ! Pour la prochaine fois, veuillez compléter le module SkillsBuild indiqué à l'écran. Cela vous préparera techniquement à analyser le déroulement précis d'une attaque lors de la session B03. Bonne semaine !
- **Visuel suggéré** : Illustration d'un écran d'ordinateur affichant le portail d'IBM SkillsBuild et la page d'accueil du CERT-FR.
  - **alt-text** : Visuel montrant les interfaces web d'IBM SkillsBuild et du site gouvernemental de cybersécurité CERT-FR.
