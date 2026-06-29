# Spécifications des slides — Session B18 : Gestion des vulnérabilités
Parcours : B 20 sessions  |  Module : E — Opérations, détection & réponse  |  Format : Spécifications Markdown

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Gestion des vulnérabilités
  - Cycle de vie des failles, référentiels CVE/CWE, calcul de score CVSS et plans de remédiation
  - Parcours B — Session B18
- **Notes orateur** : Bonjour et bienvenue dans notre dix-huitième session. Aujourd'hui, nous allons étudier la gestion des vulnérabilités. Les failles logicielles sont l'un des principaux moyens d'entrée pour les pirates. Nous allons apprendre à structurer un processus de veille et de scan, à utiliser les bases de données mondiales CVE et CWE, à décoder un score de gravité CVSS et à concevoir un plan de correction technique réaliste.
- **Visuel suggéré** : Illustration d'une loupe numérique holographique verte pointée sur une ligne de code source affichant un bug surligné en rouge, avec le mot "CVE" en relief.
  - **alt-text** : Détection et analyse d'une vulnérabilité dans du code logiciel.
- **Élément interactif** : Question sondage : "Qui sait ce que signifie le terme 'Zero-Day' en cybersécurité ?"

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Expliquer les étapes du cycle de gestion des vulnérabilités (détection, évaluation, remédiation).
  - Distinguer et utiliser les dictionnaires de vulnérabilités CVE et de faiblesses CWE.
  - Interpréter les sous-scores d'un vecteur CVSSv3 pour évaluer la criticité réelle d'une faille.
  - Sommaire : Le Cycle des vulnérabilités (20 min), Référentiels CVE & CWE (25 min), Le Score de gravité CVSS (25 min), Exercice de calcul de score (10 min), Quiz (10 min).
- **Notes orateur** : Au cours de ces 90 minutes, nous allons tout d'abord présenter le cycle complet de gestion des vulnérabilités. Nous détaillerons ensuite les dictionnaires CVE et CWE. Nous apprendrons ensuite à lire et calculer un score CVSS pour prioriser nos actions, avant de faire un exercice pratique et notre quiz traditionnel de fin de séance.
- **Visuel suggéré** : Agenda de la session affiché sous forme d'un tableau à droite, avec les 3 compétences clés présentées à gauche par des icônes de progression.
  - **alt-text** : Tableau d'agenda minuté de la session synchrone de gestion des vulnérabilités.

---

### Slide 3 — Le Cycle de gestion des vulnérabilités
- **Type** : schéma
- **Points clés (bullets)** :
  - Processus continu visant à identifier, évaluer, traiter et signaler les faiblesses de sécurité.
  - Les 4 grandes étapes opérationnelles :
    - **1. Identification** : Scans de vulnérabilités automatisés (ex: Nessus, OpenVAS).
    - **2. Évaluation** : Mesure de la gravité de la faille et de son impact sur les actifs de l'entreprise.
    - **3. Remédiation (Traitement)** : Application d'un correctif (patch), mise en place de mesures compensatoires ou acceptation.
    - **4. Vérification** : Rescanner pour s'assurer que la faille est bien corrigée.
- **Notes orateur** : Gérer les vulnérabilités n'est pas une action ponctuelle. C'est un cycle sans fin car de nouvelles failles sont découvertes chaque jour. Nous scannons notre réseau, nous évaluons la dangerosité des failles trouvées, nous appliquons les correctifs et nous vérifions par un nouveau scan que la correction est efficace.
- **Visuel suggéré** : Diagramme circulaire représentant les 4 étapes sous forme de flèches formant un anneau d'amélioration continue.
  - **alt-text** : Cycle de vie de la gestion continue des vulnérabilités.

---

### Slide 4 — Différence fondamentale : CVE vs CWE
- **Type** : contenu
- **Points clés (bullets)** :
  - **CVE (Common Vulnerabilities and Exposures)** :
    - Identifiant unique mondial attribué à une faille de sécurité spécifique dans un logiciel précis.
    - *Exemple* : **CVE-2021-44228** (Log4Shell dans la bibliothèque Apache Log4j).
  - **CWE (Common Weakness Enumeration)** :
    - Dictionnaire décrivant les catégories de faiblesses conceptuelles à l'origine des failles (le "défaut de fabrication" ou type de bug).
    - *Exemple* : **CWE-79** (Cross-site Scripting - XSS) ou **CWE-89** (Injection SQL).
- **Notes orateur** : Il ne faut pas confondre CVE et CWE. La CVE est un bug précis dans une version précise d'un produit (ex: Log4Shell chez Apache). La CWE est la catégorie générale du défaut de conception (ex: une mauvaise validation des entrées utilisateur). Pour faire une analogie médicale : la CWE est la maladie en général, la CVE est le cas d'infection constaté chez un patient précis.
- **Visuel suggéré** : Comparatif visuel : à gauche, une fiche d'identité de bug précis (CVE). À droite, un catalogue de concepts de faiblesses de code (CWE).
  - **alt-text** : Comparaison conceptuelle entre les identifiants CVE et les faiblesses logicielles CWE.

---

### Slide 5 — Comprendre le score de gravité CVSS
- **Type** : contenu
- **Points clés (bullets)** :
  - **CVSS (Common Vulnerability Scoring System)** :
    - Standard mondial de calcul de la gravité d'une faille.
  - Le score final va de **0.0** (aucun risque) à **10.0** (danger critique).
  - Divisé en trois groupes de métriques :
    - **Score de base (Base Score)** : Caractéristiques intrinsèques de la faille (ne changent pas dans le temps ni selon l'entreprise).
    - **Score temporel** : Évolution de la faille (y a-t-il un exploit public ? un correctif disponible ?).
    - **Score environnemental** : Impact réel de la faille sur les systèmes spécifiques de l'entreprise.
- **Notes orateur** : Comment prioriser nos mises à jour ? On utilise le score CVSS. Il va de 0 à 10. Le score de base mesure la dangerosité technique absolue de la faille. Le score temporel regarde si les pirates ont déjà écrit un outil d'attaque publique. Le score environnemental adapte cette gravité à votre entreprise : une faille critique sur un serveur de test sans importance n'est pas prioritaire par rapport à une faille moyenne sur votre serveur de production.
- **Visuel suggéré** : Une jauge colorée en forme de thermomètre graduée de 0 à 10 passant du vert au jaune, puis à l'orange et au rouge vif pour la note maximale.
  - **alt-text** : Échelle de notation de la gravité des failles CVSS.

---

### Slide 6 — Décoder le vecteur CVSSv3
- **Type** : schéma
- **Points clés (bullets)** :
  - Le score est calculé à partir d'une chaîne de caractères appelée **vecteur**.
  - Exemple de vecteur : `CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H`
  - Les paramètres clés à savoir déchiffrer :
    - **AV (Attack Vector)** : D'où vient l'attaque ? Network (N) $\rightarrow$ exploitables par Internet (le plus dangereux).
    - **AC (Attack Complexity)** : Facilité d'exploit ? Low (L) $\rightarrow$ facile.
    - **PR (Privileges Required)** : Faut-il un compte ? None (N) $\rightarrow$ aucun compte requis.
- **Notes orateur** : Derrière un score de 9.8 se cache une chaîne de caractères précise appelée vecteur CVSS. Elle décrit comment l'attaque fonctionne. Si vous lisez "AV:N", cela signifie que l'attaque se fait par le réseau, donc par Internet. Si vous lisez "PR:N", cela signifie qu'aucun identifiant n'est requis. C'est la combinaison de ces facteurs qui donne une note de dangerosité maximale.
- **Visuel suggéré** : Le vecteur CVSS décomposé avec des flèches explicatives reliant chaque lettre à sa signification textuelle (Vecteur d'attaque, complexité, privilèges requis).
  - **alt-text** : Analyse détaillée de la syntaxe d'un vecteur de calcul CVSSv3.

---

### Slide 7 — La remédiation : Patching, mesures de contournement ou acceptation
- **Type** : contenu
- **Points clés (bullets)** :
  - Face à une vulnérabilité qualifiée, trois choix de traitement :
  - **1. Application du correctif (Patching)** : Solution idéale et définitive fournie par l'éditeur.
  - **2. Mesure compensatoire (Mitigation)** : Si le patch ne peut pas être appliqué tout de suite (risque de bloquer la production).
    - *Exemple* : Ajouter une règle de filtrage sur le pare-feu pour bloquer le port ciblé.
  - **3. Acceptation** : Si le système est isolé et le risque résiduel faible.
- **Notes orateur** : Corriger une vulnérabilité n'est pas toujours simple. Parfois, appliquer un correctif nécessite d'arrêter le serveur de production, ce que la direction refuse. Dans ce cas, nous mettons en place des mesures compensatoires temporaires, comme fermer un port réseau ou bloquer le protocole vulnérable sur le pare-feu, en attendant la prochaine maintenance planifiée.
- **Visuel suggéré** : Schéma à trois branches montrant une route se divisant vers : Appliquer le patch (route goudronnée), Mesure compensatoire (pont temporaire), Acceptation (panneau de tolérance).
  - **alt-text** : Options de traitement et de remédiation d'une faille de sécurité.

---

### Slide 8 — Les vulnérabilités "Zero-Day" (0-Day)
- **Type** : contenu
- **Points clés (bullets)** :
  - Faille de sécurité récemment découverte qui n'est **pas encore connue de l'éditeur** du logiciel.
  - Aucun correctif officiel n'est disponible.
  - **"Zero-Day"** $\rightarrow$ l'éditeur a eu "zéro jour" pour préparer une correction.
  - Très recherchées par les attaquants étatiques et revendues très cher sur le marché noir.
  - Protection : Analyse comportementale (EDR) et segmentation réseau pour confiner l'intrusion.
- **Notes orateur** : Qu'est-ce qu'une faille Zero-Day ? C'est une vulnérabilité exploitée par les pirates avant même que l'éditeur du logiciel n'en soit informé. L'éditeur a donc eu zéro jour pour développer un correctif. Face à ces menaces inconnues, les antivirus classiques par signature sont inefficaces ; nous devons compter sur l'analyse comportementale de nos EDR et sur une bonne segmentation réseau.
- **Visuel suggéré** : Un sablier numérique affichant le chiffre "0" avec des lignes de codes sombres se désintégrant sous l'action d'une alerte.
  - **alt-text** : Concept graphique représentant une vulnérabilité logicielle Zero-Day.

---

### Slide 9 — La priorisation des correctifs
- **Type** : schéma
- **Points clés (bullets)** :
  - Appliquer toutes les mises à jour en même temps est impossible (risque de pannes).
  - **Matrice de priorisation** :
    - Faille critique + Serveur exposé sur Internet $\rightarrow$ **Priorité 1** (Correction sous 24h).
    - Faille critique + Poste interne isolé $\rightarrow$ **Priorité 2** (Correction sous 1 semaine).
    - Faille moyenne + Serveur de test $\rightarrow$ **Priorité 3** (Correction sous 1 mois).
- **Notes orateur** : Un scanner de vulnérabilités sur un grand réseau d'entreprise peut remonter des milliers de failles. Comment ne pas se noyer ? Il faut prioriser. Une vulnérabilité critique sur un serveur web accessible par tous sur Internet doit être corrigée en urgence absolue sous 24h. La même faille sur une machine de test sans données sensibles et non accessible peut attendre la prochaine session de mise à jour mensuelle.
- **Visuel suggéré** : Tableau croisé liant la sensibilité de l'actif (Exposé, Interne, Test) et la gravité de la faille (Critique, Haute, Moyenne) avec des pastilles de priorité colorées.
  - **alt-text** : Matrice de décision pour la priorisation de l'application des correctifs.

---

### Slide 10 — Activité pratique : Décoder un vecteur CVSS
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **Vecteur à analyser** : `CVSS:3.1/AV:N/AC:L/PR:N/UI:R/S:U/C:H/I:H/A:H`
  - **Paramètres fournis pour l'exercice** :
    - `AV:N` (Network), `AC:L` (Complexity: Low)
    - `PR:N` (Privileges: None), `UI:R` (User Interaction: Required)
  - **Objectifs de l'activité** :
    - 1. Expliquer si l'attaque peut être lancée à distance par Internet.
    - 2. Expliquer si l'utilisateur cible doit réaliser une action pour déclencher la faille.
    - 3. Estimer si le score de gravité est plutôt faible, moyen ou très élevé.
- **Notes orateur** : Pour ce cas pratique, je vous donne ce vecteur CVSS. À l'aide de la légende des paramètres, vous devez m'expliquer comment se déroule l'attaque. Est-elle réalisable à distance ? L'attaquant a-t-il besoin de convaincre l'utilisateur de faire une action, comme cliquer sur un lien ? Déterminez si cette faille doit être corrigée en urgence.
- **Visuel suggéré** : Tableau récapitulatif des quatre variables clés avec des choix à cocher pour l'exercice.
  - **alt-text** : Fiche d'exercice pour l'interprétation des composants d'un vecteur CVSS.
- **Élément interactif** : Analyse individuelle ou par binôme de 10 minutes avec restitution orale.

---

### Slide 11 — Quiz de validation
- **Type** : quiz
- **Points clés (bullets)** :
  - 1. Quelle est la différence majeure entre une CVE et une CWE ?
  - 2. Que signifie l'indicateur "AV:N" dans un vecteur de vulnérabilité CVSS ?
  - 3. Quel terme désigne une faille de sécurité activement exploitée mais pour laquelle aucun patch n'existe ?
- **Notes orateur** : C'est l'heure du quiz pour valider vos compétences en gestion des vulnérabilités. Connectez-vous et votez. Portez une attention particulière aux acronymes CVE et CWE pour éviter les confusions classiques.
- **Visuel suggéré** : QR Code d'accès au vote à gauche, questions interactives à droite.
  - **alt-text** : QR Code vert d'accès au quiz interactif en direct.
- **Élément interactif** : Vote synchrone en temps réel avec debriefing des résultats par le mentor.

---

### Slide 12 — Conclusion & Travail autonome
- **Type** : récap
- **Points clés (bullets)** :
  - **Résumé** : Cycle des vulnérabilités (détecter, évaluer, corriger, vérifier), CVE (failles spécifiques), CWE (faiblesses de code), score CVSS (gravité $0$ à $10$), et traitement (patch, mesures compensatoires).
  - **Devoirs** : Compléter le module *"Vulnerability Assessment and Remediation"* sur IBM SkillsBuild (~1h30).
  - **Recherche** : Visiter le site de la base de données de référence du NIST (NVD - National Vulnerability Database) et rechercher la fiche de la célèbre faille *Log4Shell*.
  - Prochaine session : *Réponse aux incidents & bases du forensics (B19)*.
- **Notes orateur** : Nous avons terminé notre session sur les vulnérabilités ! Pour aller plus loin, faites le cours SkillsBuild et allez jeter un œil au site officiel de la NVD américaine pour voir à quoi ressemble une vraie fiche de vulnérabilité. La semaine prochaine, nous verrons comment réagir lorsqu'une vulnérabilité a été exploitée avec succès et qu'une attaque s'est déclarée. À la semaine prochaine !
- **Visuel suggéré** : Badge d'achèvement de cours d'IBM SkillsBuild pour la gestion des vulnérabilités.
  - **alt-text** : Badge de réussite du cours Vulnerability Management d'IBM SkillsBuild.
