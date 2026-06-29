# Spécifications des slides — Session B16 : Centre des opérations de sécurité (SOC) & supervision
Parcours : B 20 sessions  |  Module : E — Opérations, détection & réponse  |  Format : Spécifications Markdown

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Centre des opérations de sécurité (SOC) & supervision
  - Organisation humaine, rôles analystes, traitement des alertes et métriques de détection
  - Parcours B — Session B16
- **Notes orateur** : Bonjour et bienvenue à tous. Nous débutons aujourd'hui notre cinquième et avant-dernier module de formation consacré aux opérations, à la détection et à la réponse à incident. Dans cette seizième session, nous allons étudier le Centre des Opérations de Sécurité, ou SOC. Nous verrons comment s'organise cette équipe, quels sont les rôles des analystes de niveau 1, 2 et 3, et comment s'évalue la performance d'un SOC.
- **Visuel suggéré** : Vue d'une salle de contrôle de cybersécurité futuriste obscure avec un mur d'écrans géants affichant des cartes de menaces mondiales interactives en vert cyberpunk.
  - **alt-text** : Salle de surveillance de sécurité (SOC) avec écrans géants de monitoring.
- **Élément interactif** : Question sondage : "Selon vous, à quoi ressemble le quotidien d'un analyste SOC ?"

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Décrire l'organisation interne et les responsabilités des analystes (Niveaux L1, L2, L3) d'un SOC.
  - Expliquer le cycle de vie d'une alerte, du signal brut à l'escalade d'incident.
  - Différencier une vraie alerte d'un faux positif et interpréter les métriques MTTD / MTTR.
  - Sommaire : Qu'est-ce qu'un SOC ? (20 min), Les Niveaux d'analystes L1/L2/L3 (20 min), Cycle d'une alerte & Métriques (25 min), Activité de tri d'alertes (15 min), Quiz (10 min).
- **Notes orateur** : Nous commencerons par définir les missions globales d'un SOC. Nous verrons ensuite la répartition des rôles entre analystes L1, L2 et L3. Nous étudierons ensuite le traitement d'une alerte et les indicateurs clés comme le MTTD et le MTTR. Nous ferons une mise en situation de tri d'alertes avant de terminer par notre traditionnel quiz de validation.
- **Visuel suggéré** : Liste ordonnée de l'agenda et des objectifs synchrone présentés dans deux boîtes contrastées.
  - **alt-text** : Tableau d'agenda minuté de la session synchrone de 90 minutes.

---

### Slide 3 — Qu'est-ce qu'un SOC ?
- **Type** : contenu
- **Points clés (bullets)** :
  - **SOC** : Security Operations Center.
  - Centre opérationnel chargé de surveiller, détecter et analyser les menaces de sécurité en continu (souvent 24h/24, 7j/7).
  - **Les trois piliers d'un SOC** :
    - *Les Personnes* : Les analystes qualifiés qui qualifient les alertes.
    - *Les Processus* : Les procédures d'escalade et plans de réponse (playbooks).
    - *La Technologie* : Les outils de centralisation des logs (SIEM) et d'EDR.
- **Notes orateur** : Le SOC est la tour de contrôle de la sécurité. Sa mission est d'écouter les signaux faibles émis par le réseau et les serveurs pour détecter l'apparition d'un incident le plus tôt possible. Le SOC repose sur trois piliers : des analystes compétents, des processus clairs pour savoir comment réagir, et des technologies de pointe pour collecter les logs.
- **Visuel suggéré** : Schéma pyramidal reliant trois icônes : un profil humain (Personnes), des engrenages de processus (Processus) et une puce électronique (Technologie).
  - **alt-text** : Les 3 piliers fondateurs d'un SOC efficace.

---

### Slide 4 — L'organisation humaine : Les Niveaux d'analystes
- **Type** : schéma
- **Points clés (bullets)** :
  - **Niveau 1 (L1) — Le Triage** :
    - Reçoit les alertes brutes du SIEM. Trie et élimine les faux positifs. Escalade les vraies alertes.
  - **Niveau 2 (L2) — L'Investigation** :
    - Analyse en profondeur l'alerte escaladée. Détermine la portée de l'attaque et rédige des plans de confinement.
  - **Niveau 3 (L3) — L'Expertise** :
    - Chasse active aux menaces (*Threat Hunting*), rétro-ingénierie de codes malveillants et gestion de crise.
- **Notes orateur** : Travailler dans un SOC est un sport d'équipe organisé en trois niveaux. Les analystes L1 sont en première ligne. Ils reçoivent des centaines d'alertes par jour et doivent trier les vrais problèmes des faux positifs. S'il y a un vrai doute, ils escaladent au L2, qui mène l'enquête approfondie. Le L3 intervient pour les crises majeures ou pour traquer des menaces invisibles.
- **Visuel suggéré** : Pyramide humaine inversée ou diagramme en entonnoir de haut en bas représentant le flux de filtrage des alertes du L1 (large) vers le L3 (pointu).
  - **alt-text** : Structure hiérarchique et rôles au sein de l'équipe du SOC.

---

### Slide 5 — Cycle de vie d'une alerte de sécurité
- **Type** : schéma
- **Points clés (bullets)** :
  - 1. **Collecte** : Log brut enregistré (ex: tentative de connexion échouée).
  - 2. **Détection** : Le SIEM applique une règle de corrélation et génère une alerte.
  - 3. **Triage (L1)** : L'analyste examine le contexte. Décision : Faux Positif $\rightarrow$ clôture ; Vrai Positif $\rightarrow$ escalade.
  - 4. **Analyse & Réponse (L2)** : Confinement de la menace (ex: couper l'accès réseau de l'hôte compromis).
- **Notes orateur** : Une alerte ne surgit pas par magie. Elle part d'un événement brut sur un équipement, qui est centralisé et corrélé par notre outil de supervision. L'analyste L1 intervient alors pour qualifier l'événement. S'il confirme la menace, l'incident est déclaré et l'analyste L2 applique le protocole de confinement prévu.
- **Visuel suggéré** : Frise chronologique horizontale reliant les 4 étapes avec des flèches, montrant le traitement logique d'une connexion suspecte.
  - **alt-text** : Cycle de vie d'une alerte, du journal système brut jusqu'à la résolution.

---

### Slide 6 — Vrais vs Faux Positifs : Le grand défi du L1
- **Type** : contenu
- **Points clés (bullets)** :
  - **Faux Positif (FP)** :
    - L'outil lève une alerte de sécurité pour un comportement légitime.
    - *Exemple* : Un développeur exécute un script d'automatisation réseau inhabituel.
  - **Vrai Positif (VP)** :
    - L'outil lève une alerte pour une attaque réelle en cours.
    - *Exemple* : Un pirate tente de forcer un mot de passe administrateur par force brute.
  - *Conséquence des FP* : La fatigue des alertes (*Alert Fatigue*), qui peut amener à rater une vraie attaque perdue au milieu du bruit.
- **Notes orateur** : Le plus grand ennemi de l'analyste de niveau 1 est le faux positif. Si votre système d'alarme sonne chaque fois qu'un oiseau passe devant la fenêtre, vous finirez par l'éteindre. C'est ce qu'on appelle la fatigue des alertes. Le but du SOC est de régler finement ses outils de détection pour minimiser les faux positifs sans rater les vraies attaques.
- **Visuel suggéré** : Une boîte aux lettres virtuelle débordante d'enveloppes rouges "Alerte", avec un analyste fatigué se tenant la tête.
  - **alt-text** : Représentation du phénomène de fatigue des alertes chez les analystes.

---

### Slide 7 — Évaluer la performance du SOC : MTTD & MTTR
- **Type** : contenu
- **Points clés (bullets)** :
  - **MTTD (Mean Time To Detect)** :
    - Temps moyen s'écoulant entre le début d'une intrusion et sa détection par le SOC.
    - *Objectif* : Le plus bas possible (quelques minutes/heures maximum).
  - **MTTR (Mean Time To Respond)** :
    - Temps moyen nécessaire pour contenir et neutraliser l'attaque après détection.
    - *Objectif* : Réduire au minimum pour limiter la propagation (confinement rapide).
- **Notes orateur** : Comment savoir si un SOC est efficace ? On mesure deux indicateurs de temps fondamentaux. Le MTTD mesure notre rapidité à voir l'attaquant s'introduire. Le MTTR mesure notre rapidité à réagir pour couper ses accès et nettoyer les systèmes. En cybersécurité, chaque minute gagnée réduit le coût financier de l'impact de l'attaque.
- **Visuel suggéré** : Un chronomètre numérique double : à gauche, MTTD en vert ; à droite, MTTR en bleu, avec des flèches temporelles.
  - **alt-text** : Indicateurs temporels clés de performance de détection et de réponse.

---

### Slide 8 — L'importance des Playbooks (Fiches réflexes)
- **Type** : contenu
- **Points clés (bullets)** :
  - Procédures opérationnelles documentées détaillant précisément comment réagir face à un type d'alerte spécifique.
  - Garantit la cohérence et la rapidité de la réponse, quel que soit l'analyste de garde.
  - Exemple de Playbook Ransomware :
    - 1. Isoler la machine du réseau local (via l'EDR).
    - 2. Identifier le compte utilisateur compromis.
    - 3. Révoquer ses identifiants.
    - 4. Prendre un instantané (snapshot) de la VM pour analyse.
- **Notes orateur** : En cas d'attaque, la panique est notre pire ennemie. C'est pour cela que le SOC utilise des playbooks. Ce sont des fiches réflexes écrites à l'avance. Quand une alerte de type ransomware se déclenche à 3 heures du matin, l'analyste de garde applique scrupuleusement la fiche étape par étape : isolation de l'ordinateur, blocage du compte, sauvegarde de la mémoire.
- **Visuel suggéré** : Un classeur ouvert étiqueté "Playbook SOC" avec une checklist d'actions d'urgence de confinement réseau.
  - **alt-text** : Fiche playbook de procédure d'urgence en cas d'attaque cyber.

---

### Slide 9 — Les typologies de SOC : Interne vs Externe
- **Type** : contenu
- **Points clés (bullets)** :
  - **SOC Interne (Dédié)** :
    - Propre à l'entreprise. Connaissance fine du métier.
    - *Inconvénient* : Très coûteux à maintenir (nécessite au moins 5 à 8 analystes pour couvrir le 24/7).
  - **SOC Externe (MSSP)** :
    - Externalisé chez un prestataire spécialisé surveillant plusieurs clients.
    - *Avantage* : Moins cher, bénéficie de la vision globale du prestataire sur d'autres attaques.
- **Notes orateur** : Toutes les entreprises n'ont pas les moyens d'avoir leur propre SOC interne. Maintenir une équipe d'analystes éveillés et opérationnels 24h sur 24 nécessite au moins 5 à 8 personnes à plein temps. Beaucoup de PME et d'ETI choisissent d'externaliser leur surveillance auprès d'un prestataire de services de sécurité managés (un MSSP).
- **Visuel suggéré** : Schéma comparatif montrant un bureau de SOC interne unique face à un grand centre de surveillance externe centralisé relié à plusieurs entreprises.
  - **alt-text** : Comparaison organisationnelle entre SOC interne et SOC partagé chez un MSSP.

---

### Slide 10 — Activité pratique : Qualification et Triage d'alerte
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **Alerte brute** : Connexion SSH réussie sur le serveur de paye de l'entreprise à 02h15 du matin depuis une adresse IP publique située à l'étranger.
  - **Ressources disponibles** : Annuaire interne, planning d'astreinte, historique de connexion de l'utilisateur.
  - **Mission (Analyste L1)** :
    - 1. Lister les questions pour valider s'il s'agit d'un Vrai ou d'un Faux Positif.
    - 2. Rédiger la décision finale motivée (Faux Positif ou Escalade L2).
- **Notes orateur** : Place à l'exercice de triage. Vous êtes analyste de niveau 1 de garde cette nuit. Vous recevez cette alerte de connexion tardive depuis l'étranger sur un serveur critique. Quelles investigations menez-vous pour savoir s'il s'agit d'une attaque réelle ou d'une astreinte légitime d'un de vos ingénieurs ?
- **Visuel suggéré** : Capture d'écran factice de console de tri d'alertes affichant la ligne d'événement SSH à analyser.
  - **alt-text** : Tableau de bord d'investigation d'un événement de connexion suspecte.
- **Élément interactif** : Analyse collective de 15 minutes avec mise en commun et débat sur la décision de tri.

---

### Slide 11 — Quiz de validation
- **Type** : quiz
- **Points clés (bullets)** :
  - 1. Quel rôle au sein du SOC est principalement chargé du triage initial et du filtrage des alertes ?
  - 2. Quelle est la conséquence majeure d'un taux trop élevé de faux positifs dans la console d'un analyste ?
  - 3. Qu'indique un MTTD très bas dans un rapport d'audit de SOC ?
- **Notes orateur** : C'est le moment de tester vos connaissances sur l'organisation des centres opérationnels de sécurité. Répondez au questionnaire depuis vos écrans pour valider ces notions de triage et de métriques.
- **Visuel suggéré** : QR Code d'accès au vote interactif à gauche, questions à choix multiples à droite.
  - **alt-text** : QR Code d'accès au vote synchrone de validation des acquis.
- **Élément interactif** : Quiz en ligne interactif avec affichage des scores en temps réel.

---

### Slide 12 — Conclusion & Travail autonome
- **Type** : récap
- **Points clés (bullets)** :
  - **Résumé** : Rôles du SOC (L1 triage, L2 enquête, L3 expertise), indicateurs temporels (MTTD et MTTR), importance des playbooks de réaction, et gestion de la fatigue des alertes.
  - **Devoirs** : Compléter le module *"Security Operations Center (SOC) Fundamentals"* sur IBM SkillsBuild (~1h30).
  - **Recherche** : Trouver la définition d'un **SOAR** et expliquer comment il permet d'automatiser l'exécution des playbooks.
  - Prochaine session : *SIEM, journalisation & détection (B17)*.
- **Notes orateur** : Nous avons exploré le fonctionnement humain et organisationnel de la détection ! Faites le cours associé sur SkillsBuild et renseignez-vous sur les outils de type SOAR qui automatisent l'exécution des playbooks. La semaine prochaine, nous rentrerons dans le détail de l'outil technique principal du SOC : le SIEM. Bonne semaine à tous !
- **Visuel suggéré** : Badge d'achèvement de cours d'IBM SkillsBuild pour le module Security Operations Center (SOC).
  - **alt-text** : Badge de réussite du cours SOC d'IBM SkillsBuild.
