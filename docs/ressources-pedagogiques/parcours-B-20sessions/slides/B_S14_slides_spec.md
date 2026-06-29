# Spécifications des slides — Session B14 : Gestion des risques
Parcours : B 20 sessions  |  Module : D — Gouvernance, risque & conformité  |  Format : Spécifications Markdown

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Gestion des risques
  - Analyser les menaces, évaluer la criticité, construire un registre et traiter les risques
  - Parcours B — Session B14
- **Notes orateur** : Bienvenue dans cette quatorzième session. Aujourd'hui, nous allons étudier la gestion des risques. La sécurité absolue n'existe pas. Le rôle d'un professionnel en cybersécurité est d'évaluer les risques pour éclairer les choix de la direction générale. Nous allons apprendre à définir un risque, à évaluer sa criticité et à formaliser un registre des risques pragmatique.
- **Visuel suggéré** : Représentation d'une balance à deux plateaux équilibrant d'un côté un cube de données dorées et de l'autre une pile d'icônes de menaces rouges (virus, foudre, erreur humaine).
  - **alt-text** : Graphisme de balance mesurant les risques et la sécurité des données.
- **Élément interactif** : Question sondage : "Selon vous, qu'est-ce qu'un risque acceptable pour une entreprise ?"

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Articuler les notions fondamentales de menace, vulnérabilité, impact et probabilité.
  - Concevoir et alimenter un registre des risques cybersécurité pragmatique.
  - Classer et justifier les quatre options de traitement du risque (réduire, transférer, éviter, accepter).
  - Sommaire : L'Équation du Risque (20 min), Le Registre des risques (20 min), Les 4 Options de Traitement (25 min), Exercice de qualification de scénario (15 min), Quiz (10 min).
- **Notes orateur** : Nous commencerons par l'équation du risque pour comprendre de quoi il est composé. Puis, nous verrons comment structurer un registre des risques. Nous analyserons ensuite les quatre stratégies de traitement à notre disposition avant de réaliser une étude de cas en groupe et de finir par le quiz.
- **Visuel suggéré** : Liste structurée présentant d'un côté les objectifs opérationnels et de l'autre le minutage de la séance synchrone de 90 minutes.
  - **alt-text** : Tableau d'agenda minuté de la session synchrone sur la gestion des risques.

---

### Slide 3 — L'Équation fondamentale du risque
- **Type** : contenu
- **Points clés (bullets)** :
  - Un risque n'est pas une certitude, c'est un événement redouté potentiel.
  - **Formule du Risque** : $\text{Risque} = \text{Menace} \times \text{Vulnérabilité} \times \text{Impact}$
  - **Menace** : Facteur externe ou interne voulant causer un dommage (ex: attaquant, panne, incendie).
  - **Vulnérabilité** : Faiblesse interne du système exploitable par la menace (ex: absence de mise à jour, salarié non formé).
  - **Impact** : Gravité des conséquences si le scénario se produit (financière, réputation, juridique).
- **Notes orateur** : La gestion des risques repose sur une équation simple. Pour qu'un risque existe, il faut une menace, une vulnérabilité exploitable et des conséquences réelles. S'il n'y a pas d'impact ou pas de vulnérabilité, le risque est nul. Par exemple, un virus redoutable (menace) n'est pas un risque pour vous si vos ordinateurs ne possèdent pas la faille correspondante (vulnérabilité).
- **Visuel suggéré** : Schéma d'une multiplication visuelle de trois blocs (Menace $\times$ Vulnérabilité $\times$ Impact) aboutissant à une boîte rouge marquée "Risque".
  - **alt-text** : Schéma mathématique simplifié représentant les composantes d'un risque.

---

### Slide 4 — Évaluer la criticité du risque
- **Type** : schéma
- **Points clés (bullets)** :
  - La criticité d'un risque se calcule selon deux axes majeurs :
    - **Probabilité (ou Vraisemblance)** : Quelle est la chance que cela arrive ? (Échelle de 1 à 4).
    - **Gravité (ou Impact)** : Quel sera le niveau de dégâts si cela arrive ? (Échelle de 1 à 4).
  - **Criticité (C)** = $\text{Probabilité} \times \text{Gravité}$.
  - Les risques à traiter en priorité absolue sont ceux ayant une criticité maximale (Rouge).
- **Notes orateur** : Pour classer nos risques, on évalue la probabilité et la gravité de l'impact. On multiplie ces deux valeurs pour obtenir la criticité. Un risque rare mais aux conséquences désastreuses aura une criticité élevée. Un risque fréquent mais sans impact réel sera classé comme prioritaire bas.
- **Visuel suggéré** : Une matrice de criticité $4\times4$ colorée avec des cases vertes (risque faible), jaunes (risque moyen) et rouges (risque critique).
  - **alt-text** : Matrice $4\times4$ d'évaluation de la criticité des risques.

---

### Slide 5 — Qu'est-ce qu'un registre des risques ?
- **Type** : contenu
- **Points clés (bullets)** :
  - Tableau de suivi centralisant l'analyse des risques d'une organisation.
  - Colonnes minimales d'un registre pragmatique :
    - **ID / Nom du scénario** (ex: R01 - Attaque par Ransomware).
    - **Actif support** (ex: Serveurs de fichiers).
    - **Criticité brute** (Probabilité $\times$ Gravité avant mesures).
    - **Mesures existantes / prévues** (ex: Sauvegarde 3-2-1, EDR).
    - **Criticité résiduelle** (Le niveau de risque restant après application des protections).
    - **Propriétaire du risque** (Le manager responsable du suivi).
- **Notes orateur** : Le registre des risques est le tableau de bord du RSSI. Il recense tous les scénarios redoutés, leur niveau de dangerosité initial (risque brut), les défenses en place pour les atténuer, et le niveau de danger restant après ces efforts (le risque résiduel). Enfin, chaque risque doit avoir un responsable métier affecté pour s'assurer du suivi.
- **Visuel suggéré** : Capture d'écran épurée d'un tableau de registre des risques avec des lignes colorées et des indicateurs de criticité brute vs résiduelle.
  - **alt-text** : Structure type d'un tableau de suivi de registre des risques.

---

### Slide 6 — Les 4 Stratégies de Traitement du Risque
- **Type** : schéma
- **Points clés (bullets)** :
  - **Réduire (ou Atténuer)** : Mettre en œuvre des contrôles de sécurité (ex: installer un pare-feu).
  - **Transférer (ou Partager)** : Déplacer l'impact financier (ex: souscrire une cyber-assurance).
  - **Éviter** : Supprimer l'activité risquée (ex: refuser d'héberger une base de données trop sensible).
  - **Accepter** : Décider de ne rien faire car le coût de protection dépasse la valeur de l'actif ou parce que le risque résiduel est jugé tolérable par la direction.
- **Notes orateur** : Une fois le risque évalué, que fait-on ? On a quatre options. Le plus souvent, on réduit le risque avec des outils de sécurité. On peut aussi le transférer en prenant une assurance. On peut l'éviter en renonçant au projet trop dangereux. Enfin, on peut l'accepter consciemment, parce que le sécuriser coûterait plus cher que ce qu'il peut nous faire perdre.
- **Visuel suggéré** : Un panneau de signalisation routière quadri-directionnel avec les quatre flèches étiquetées : Réduire, Transférer, Éviter, Accepter.
  - **alt-text** : Les 4 voies de traitement d'un risque de sécurité.

---

### Slide 7 — Réduire vs Transférer : Exemples concrets
- **Type** : contenu
- **Points clés (bullets)** :
  - **Scénario** : Risque de vol d'ordinateurs portables de commerciaux en déplacement.
  - **Option Réduction** :
    - Action : Activer le chiffrement BitLocker sur tous les postes + imposer un mot de passe fort.
    - Résultat : Les données sont protégées, le risque de fuite de données est réduit.
  - **Option Transfert** :
    - Action : Prendre un contrat d'assurance vol de matériel.
    - Résultat : L'assurance rembourse le matériel volé, mais ne protège pas contre la fuite de données !
- **Notes orateur** : Il est crucial de comprendre la différence entre réduire et transférer. Si vous chiffrez le disque, vous réduisez le risque de fuite. Si vous prenez une assurance, vous transférez le coût du vol du PC. L'assurance rembourse le matériel, mais elle ne pourra jamais effacer le fait que vos données clients ont été lues par un tiers. Les deux options sont souvent complémentaires.
- **Visuel suggéré** : Comparaison face-à-face : à gauche, un PC portable avec un bouclier BitLocker (Réduction). À droite, un contrat d'assurance papier tamponné (Transfert).
  - **alt-text** : Comparatif pratique entre la réduction et le transfert du risque.

---

### Slide 8 — Le concept de Risque Acceptable (Appétence au risque)
- **Type** : contenu
- **Points clés (bullets)** :
  - Il est impossible et trop coûteux de réduire tous les risques à zéro $\rightarrow$ la sécurité totale n'existe pas.
  - **Appétence au risque** : Le niveau de risque qu'une organisation est prête à supporter pour atteindre ses objectifs.
  - L'acceptation du risque doit être une **décision formelle de la Direction Générale**, signée et documentée.
  - Le RSSI conseille, mais ne signe pas l'acceptation finale des risques (pas de délégation de responsabilité juridique).
- **Notes orateur** : Le risque zéro n'existe pas. L'entreprise doit définir sa tolérance ou appétence au risque. Ce choix n'incombe pas au RSSI. C'est le rôle de la direction générale de décider si elle accepte un risque ou si elle veut investir pour le réduire. Le RSSI est là pour apporter les faits et les chiffrages nécessaires à cette décision.
- **Visuel suggéré** : Une ligne rouge horizontale "Seuil d'acceptabilité" sur un graphique, avec des barres de risques passant au-dessus (à traiter) et d'autres restant en dessous (acceptées).
  - **alt-text** : Graphique de représentation du seuil d'acceptation du risque en entreprise.

---

### Slide 9 — Méthodes d'analyse de risques officielles
- **Type** : contenu
- **Points clés (bullets)** :
  - Pour structurer l'analyse, on utilise des cadres reconnus :
  - **EBIOS RM** (France - ANSSI) :
    - Axé sur les scénarios de menace par rapport aux objectifs stratégiques et aux sources de menaces.
  - **ISO 27005** :
    - Standard international fournissant les lignes directrices pour gérer les risques liés à l'information.
  - **MEHARI** (Clusif) :
    - Méthode d'évaluation quantitative et qualitative basée sur des bases de connaissances d'attaques.
- **Notes orateur** : Pour faire une analyse de risques professionnelle, nous ne partons pas d'une page blanche. Nous utilisons des méthodologies structurées. En France, EBIOS RM de l'ANSSI est la référence incontournable. À l'international, c'est l'ISO 27005 qui sert de guide méthodologique pour mettre en place la gestion des risques de notre SMSI.
- **Visuel suggéré** : Logotypes des référentiels EBIOS RM, ISO 27005 et MEHARI présentés de façon harmonieuse.
  - **alt-text** : Les principaux référentiels méthodologiques de gestion des risques.

---

### Slide 10 — Activité pratique : Remplir une ligne de registre
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **Scénario** : L'entreprise EcoLog stocke ses dossiers financiers dans un partage réseau accessible par tous les salariés, sans sauvegarde externe.
  - **Objectifs de l'activité** :
    - 1. Qualifier la menace et la vulnérabilité de ce scénario.
    - 2. Estimer la Probabilité (1 à 4) et la Gravité (1 à 4) brute.
    - 3. Proposer deux mesures de réduction réalistes.
    - 4. Estimer la criticité résiduelle après ces mesures.
- **Notes orateur** : Passons à la pratique. Nous allons analyser un scénario critique pour EcoLog : le stockage de ses fichiers financiers sans restriction d'accès et sans sauvegarde déconnectée. Remplissez en équipe la ligne de registre des risques correspondante en calculant la criticité avant et après vos propositions de sécurité.
- **Visuel suggéré** : Ligne de tableau de registre vierge avec des champs éditables à remplir pendant l'exercice.
  - **alt-text** : Ligne d'exercice d'un registre des risques à remplir en équipe.
- **Élément interactif** : Travail collaboratif en sous-groupes de 15 minutes avec mise en commun au tableau blanc.

---

### Slide 11 — Quiz de validation
- **Type** : quiz
- **Points clés (bullets)** :
  - 1. Quel élément de l'équation du risque correspond à l'absence de correctifs sur un serveur ?
  - 2. Si un risque a une Probabilité de 3 et une Gravité de 4, quelle est sa criticité brute sur une échelle de 16 ?
  - 3. Quelle option de traitement correspond à l'achat d'une police de cyber-assurance ?
- **Notes orateur** : C'est le moment de tester votre compréhension de la gestion des risques. Répondez au quiz depuis vos postes de travail. Pensez bien à l'équation fondamentale et à la différence entre réduction et transfert.
- **Visuel suggéré** : QR Code d'accès au questionnaire à gauche et questions à choix multiples à droite.
  - **alt-text** : QR Code vert d'accès au système de vote en direct.
- **Élément interactif** : Vote synchrone en temps réel avec commentaire de correction par le mentor.

---

### Slide 12 — Conclusion & Travail autonome
- **Type** : récap
- **Points clés (bullets)** :
  - **Résumé** : $\text{Risque} = \text{Menace} \times \text{Vulnérabilité} \times \text{Impact}$, Criticité ($P\times G$), 4 options de traitement (réduire, transférer, éviter, accepter), et rôle consultatif du RSSI.
  - **Devoirs** : Compléter le module *"Cybersecurity Risk Management"* sur IBM SkillsBuild (~1h30).
  - **Préparation** : Lire le document d'introduction à EBIOS RM sur le site de l'ANSSI.
  - Prochaine session : *Conformité & réglementations vie privée (B15)*.
- **Notes orateur** : Nous avons bouclé les bases de la gestion des risques ! Réalisez le module SkillsBuild pour approfondir. La semaine prochaine, nous aborderons le cadre légal et la conformité, en particulier le RGPD et le rôle de la CNIL, ce qui marquera la fin de notre module GRC et le lancement du Mini-projet 3. Bonne semaine !
- **Visuel suggéré** : Badge d'achèvement de cours d'IBM SkillsBuild pour la gestion des risques de sécurité.
  - **alt-text** : Badge de réussite du cours Risk Management d'IBM SkillsBuild.
