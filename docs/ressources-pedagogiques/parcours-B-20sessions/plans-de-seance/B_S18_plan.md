# Plan de séance — Session B18
Parcours : B 20 sessions  |  Module : E — Opérations, détection & réponse  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## 1. Métadonnées de la session
* **Titre** : Introduction à la réponse aux incidents (et son préalable : la gestion des vulnérabilités)
* **Objectifs pédagogiques opérationnels** :
  * Décrire le cycle de gestion des vulnérabilités (CVE, score CVSS, remédiation, vérification) et prioriser des correctifs selon la gravité ET l'exposition.
  * Citer les phases du cycle de réponse aux incidents (NIST SP 800-61 / PICERL) et distinguer confinement, éradication et recouvrement.
  * Appliquer les gestes du premier répondant face à un rançongiciel (isoler sans éteindre, préserver la RAM, escalader) et co-rédiger la fiche réflexe correspondante.
* **Prérequis** : B12 (sauvegardes), B17 (journaux et valeur probante). Rappels mobilisés : B14 (criticité), B02 (LOPMI, ne pas payer), B08 (EDR).
* **Lien de progression** : B16-B17 ont appris à détecter ; B18 apprend à réagir. Cette armature (cycle NIST/PICERL, fiche réflexe) est exactement ce que la simulation de crise de B19 mettra à l'épreuve, avant le Grand Atelier d'Audit de B20.

## 2. Checklist technique Livestorm (avant la session)

- [ ] Les **9 sondages** sont pré-créés dans Livestorm, dans l'ordre du tableau ci-dessous.
- [ ] Le partage d'écran est testé avec le diaporama B18 ([spécifications](../slides/B_S18_slides_spec.md)) — les trois dossiers de l'activité de priorisation doivent être lisibles.
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
| :-- | :-- | :-- | :-- | :-- |
| 1 | 0:04 | Brise-glace | Combien de CVE publiées en 2024 ? | C — Plus de 40 000 |
| 2 | ~0:23 | Activité | CVSS 9.8 sur serveur exposé Internet ? | A — Corriger sous 24 h |
| 3 | ~0:26 | Activité | Même faille sur serveur de test isolé ? | B — Fenêtre planifiée |
| 4 | ~0:29 | Activité | Correctif qui risque de casser la production ? | B — Compenser + tester + déployer |
| 5 | 1:11 | Opinion | Votre organisation a-t-elle un plan de réponse ? | — (pas de bonne réponse) |
| 6 | 1:15 | Quiz | Différence CVE / CWE ? | B |
| 7 | 1:17 | Quiz | Rançongiciel actif : premier geste ? | C — Isoler sans éteindre |
| 8 | 1:19 | Quiz | Pourquoi ne jamais éteindre la machine ? | A — RAM volatile (preuves, clé) |
| 9 | 1:21 | Bonus | Correctif urgent vs production ? | B — Pilote 24 h puis déploiement |

## 3. Vue d'ensemble du déroulé

| Créneau | Séquence | Interactions |
| :-- | :-- | :-- |
| 0:00–0:04 | Accueil & réinvestissement du devoir (le confinement) | Chat |
| 0:04–0:09 | Brise-glace : plus de 40 000 CVE | 📊 Sondage n°1 |
| 0:09–0:22 | Avant l'incident : cycle des vulnérabilités, CVE/CVSS, zero-day | — |
| 0:22–0:33 | **Activité : le comité de priorisation des correctifs** | 📊 Sondages n°2, 3, 4 |
| 0:33–0:42 | Affaires réelles : Equifax & Log4Shell | 💬 Question chat |
| 0:42–0:53 | Le cycle de réponse : NIST SP 800-61 / PICERL | — |
| 0:53–1:00 | Préservation des preuves : la règle d'or de la RAM | — |
| 1:00–1:04 | Mini-scénario : l'appel du lundi matin | 🤔 Chat A/B/C |
| 1:04–1:11 | **Activité : la fiche réflexe co-rédigée** | 💬 Chat |
| 1:11–1:15 | Votre plan de réponse (opinion) | 📊 Sondage n°5 |
| 1:15–1:21 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:21–1:25 | Exercice bonus : patcher sans casser (tampon) | 📊 Sondage n°9 |
| 1:25–1:30 | Synthèse, devoirs & teaser B19 | Chat : « un mot retenu » |

## 4. Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & réinvestissement du devoir

**🎙️ Verbatim d'ouverture :**
> « Bonsoir à toutes et à tous ! B16 : l'équipe qui surveille. B17 : les traces qu'elle lit. Ce soir, la suite logique : l'alerte est confirmée, l'attaque est réelle — on fait quoi ? Vous aviez une recherche : le confinement d'une machine compromise. **Dans le chat : citez une action technique concrète pour isoler une machine !** »

**Points de contenu :**
- Récolter : câble débranché, Wi-Fi coupé, VLAN d'isolement, règle de pare-feu, isolement via l'EDR — valider, compléter.
- Annoncer le plan en deux temps : AVANT l'incident (colmater les failles), PENDANT et APRÈS (le cycle de réponse) — et deux exercices collectifs.

**Transition :** « Avant de répondre aux incidents, voyons d'où ils viennent. Un chiffre d'abord. »

### 0:04–0:09 — 📊 Sondage n°1 (brise-glace) : l'avalanche de failles

Lancer le sondage n°1 (CVE publiées en 2024). Laisser voter ~60 secondes.

**🎙️ Débrief scripté :**
> « Réponse C : plus de 40 000 CVE publiées en 2024 — plus de cent par jour, un record (programme CVE / base NVD). Corriger tout, tout de suite, partout ? Impossible, pour tout le monde. La vraie compétence, c'est le tri : quelle faille, sur quelle machine, dans quel délai. C'est notre première partie. »

**Transition :** « Posons d'abord le vocabulaire : CVE, CVSS, et le cycle en quatre temps. »

### 0:09–0:22 — Avant l'incident : gérer les vulnérabilités

**Points de contenu (support §1) :**
- Le cycle en 4 étapes : **identifier** (scanners : Nessus, OpenVAS — croisement avec la base CVE), **évaluer** (CVSS 0-10 ; marteler : le score technique SEUL ne suffit pas — l'exposition de l'actif fait la priorité, comme la criticité V×G de B14), **remédier** (patch = définitif ; mesure compensatoire = le collier de serrage temporaire ; acceptation = formelle, B14), **vérifier** (re-scanner ! des correctifs échouent en silence).
- CVE vs CWE en 30 secondes : le cas déclaré vs la maladie en général (l'analogie médicale du support).
- Le zero-day : pas de correctif → parades architecturales (EDR comportemental B08, segmentation B06, défense en profondeur).
- 🎙️ « Un score CVSS, c'est la dangerosité de la faille dans l'absolu. Votre priorité, c'est cette dangerosité multipliée par l'endroit où elle se trouve CHEZ VOUS. »

**Transition :** « Assez de théorie — vous êtes maintenant le comité sécurité d'EcoLog. Trois dossiers sur la table. »

### 0:22–0:33 — 📊 Activité : le comité de priorisation (sondages n°2, 3, 4)

Pour chaque dossier : afficher le contexte, 30 secondes de lecture, vote, débrief (détails dans le support).

1. **📊 n°2 — Dossier A (0:22–0:26)** : CVSS 9.8 sur le serveur web exposé Internet → **A, sous 24 h** : pire profil au pire endroit. 🎙️ « Retenez ce dossier : c'est exactement celui qu'Equifax a laissé traîner — l'affaire arrive dans dix minutes. »
2. **📊 n°3 — Dossier B (0:26–0:29)** : même faille, serveur de test isolé → **B, fenêtre planifiée** : le score environnemental en action. Répondre « urgence » partout = épuiser les équipes (la fatigue des alertes de B16, version patching).
3. **📊 n°4 — Dossier C (0:29–0:33)** : correctif qui risque de casser la facturation → **B, compenser-tester-déployer** : le faux dilemme « sécurité OU production » se résout par la séquence, pas par le dogme.

**Transition :** « Et maintenant, l'histoire de ce qui arrive quand ce comité ne fait pas son travail. 147 millions de personnes. »

### 0:33–0:42 — Affaires réelles : Equifax & Log4Shell

**Points de contenu (support §3) :**
- **Equifax (2017)** : dérouler la chaîne — faille Struts publiée en mars avec correctif (CVE-2017-5638) ; consigne interne envoyée mais serveur jamais patché ; re-scan qui rate ; intrusion mi-mai ; **76 jours** d'exfiltration invisibles (certificat expiré sur l'inspection du trafic — la leçon de B17) ; **147 millions** de personnes ; accord jusqu'à **700 M$** (FTC, 2019) ; PDG, DSI et RSSI démissionnent.
- 💬 **Question chat** : « quel maillon a cédé EN PREMIER, à votre avis ? » — récolter, puis montrer que TOUS ont cédé : inventaire, application, vérification, détection, communication de crise. 🎙️ « Pas un exploit de génie : une chaîne de négligences ordinaires. »
- **Log4Shell (décembre 2021)** en contrepoint rapide : CVSS 10.0, bibliothèque omniprésente — le week-end où le monde entier a découvert l'importance de l'**inventaire** ; mesures compensatoires immédiates puis campagne de patchs (CERT-FR/ANSSI).

**Transition :** « Malgré tout cela, un jour, une faille passe. L'alerte sonne, l'attaque est réelle. Voici la méthode. »

### 0:42–0:53 — Le cycle de réponse : NIST SP 800-61 / PICERL

**Points de contenu (support §4) :**
- Afficher le schéma de correspondance : NIST **4 phases** ↔ PICERL **6 étapes** (préciser la rigueur : le NIST regroupe confinement-éradication-recouvrement en UNE phase car on itère entre les trois ; PICERL est le moyen mnémotechnique).
- **Préparation** : tout ce qu'on a déjà construit — sauvegardes hors ligne (B12), playbooks, et la gestion des vulnérabilités de la première partie.
- **Détection & analyse** : B16-B17 — qualifier, évaluer, comprendre.
- **Confinement → éradication → recouvrement** avec l'analogie de l'incendie de cuisine : fermer la porte / éteindre à la source et déblayer / repeindre et remplacer la cuisinière. Insister sur l'éradication : supprimer AUSSI les portes dérobées et corriger la faille d'origine — sinon le recouvrement restaure un environnement piégé.
- **REX** : l'étape la plus sautée, la plus rentable. 🎙️ « Sans REX, vous ne sortez pas d'un incident — vous attendez le suivant. »

**Transition :** « Reste LE geste que tout le monde rate sous stress. Parlons de la RAM. »

### 0:53–1:00 — La règle d'or de la RAM

**Points de contenu (support §5) :**
- Le réflexe instinctif (éteindre) est l'erreur : la RAM volatile contient processus actifs, connexions, adresses des attaquants — parfois **la clé de chiffrement**.
- Le redémarrage peut aggraver (chiffrement des fichiers de démarrage).
- La bonne pratique : **isoler du réseau, laisser allumé** — puis les experts collectent selon l'ordre de volatilité (RAM → réseau → disques en copie → journaux déportés, déjà en lieu sûr grâce à B17).
- Enjeu juridique : chronologie factuelle, plainte — LOPMI 2023 : l'indemnisation assurantielle exige une plainte sous **72 h** (B02).

**Transition :** « Testons ça à chaud. Lundi matin, 10h04, le téléphone sonne. »

### 1:00–1:04 — 🤔 Mini-scénario : l'appel du lundi matin

Afficher le scénario (demande de rançon, fichiers qui se chiffrent) — réponses A/B/C dans le chat.

**🎙️ Débrief scripté :**
> « B — trois gestes, dans l'ordre : isoler (le câble, le Wi-Fi — stopper la propagation vers les partages), préserver (la machine reste ALLUMÉE : la RAM est votre coffre à preuves), escalader (le helpdesk n'investigue pas, il alerte). A détruit les preuves et peut-être la clé de déchiffrement ; C peut déclencher le chiffrement du démarrage. Ce script de 30 secondes a un nom : un playbook. Écrivons-le ensemble. »

### 1:04–1:11 — 💬 Activité : la fiche réflexe co-rédigée

**Séquençage :**
1. 🎙️ « Dans le chat : dans l'ordre, les 5 étapes que le technicien helpdesk déroule au téléphone. Une étape par message ! »
2. Récolter 2-3 minutes, reformuler à voix haute, écrire la fiche en direct à l'écran.
3. Afficher le modèle du support (isoler → maintenir l'alimentation → collecter → escalader → consigner) et comparer avec la production du chat.
4. Débrief : les trois qualités d'une fiche réflexe — **zéro jargon**, **interdits explicites** (ne pas éteindre, ne pas payer — position constante de l'ANSSI, B02 —, ne pas « nettoyer »), **escalade nominative**.

### 1:11–1:15 — 📊 Sondage n°5 (opinion) : votre plan de réponse

Lancer le sondage n°5 (plan testé / plan papier / aucun). Annoncer qu'il n'y a pas de bonne réponse.

**🎙️ Débrief scripté :**
> « Un plan jamais testé est une hypothèse, pas un plan. Les rapports IBM *Cost of a Data Breach* le confirment année après année : équipe de réponse + plan testé = des violations nettement moins coûteuses. Et le test ne coûte rien : il se fait sur table, sans toucher à la production. C'est exactement ce que nous ferons la semaine prochaine — vous êtes prévenus. »

### 1:15–1:21 — 📊 Quiz de validation (sondages n°6, 7, 8)

Enchaîner les trois sondages, débrief de 30 secondes chacun (éléments dans le support) :
- N°6 → B : CVE = le cas déclaré ; CWE = la maladie en général.
- N°7 → C : confiner d'abord, restaurer APRÈS l'éradication — sinon on restaure dans un environnement piégé.
- N°8 → A : l'ordre de volatilité — éteindre, c'est passer l'éponge sur la scène de crime.

### 1:21–1:25 — 📊 Sondage n°9 (bonus tampon) : patcher sans casser

Lancer si le temps le permet (sinon : « à faire en autonomie, il est dans le support »).

**🎙️ Débrief scripté :**
> « B : périmètre pilote 24 h, puis déploiement en anneaux — ni jamais (la porte reste ouverte), ni brutalement (le risque cyber devient une panne certaine). Et si la faille est activement exploitée : mesure compensatoire EN ATTENDANT, comme au dossier C. »

### 1:25–1:30 — Synthèse, devoirs & teaser B19

**Points de clôture :**
- 🎙️ « Trois choses à retenir : priorisez par gravité × exposition ; isolez sans éteindre ; et faites le REX — Equifax, c'est une faille connue, un correctif disponible, et 700 millions de dollars de négligences ordinaires. »
- Chat : « un mot que vous retenez de la session ».
- Self-paced : cours IBM SkillsBuild *"Incident Response Fundamentals"* (~1h30) + réflexion préparatoire : « si votre organisation était frappée demain à 8h par un rançongiciel, quelles 4-5 fonctions mettriez-vous dans la cellule de crise ? » (notez votre liste — elle servira dès l'ouverture de B19).
- Teaser B19 : « la semaine prochaine, on ne prend plus de notes : on VIT une crise. Exercice sur table interactif — le scénario se déroulera en temps réel, et c'est VOUS qui prendrez chaque décision, par sondages. Rendez-vous en cellule de crise. »
- Terminer à l'heure exacte.

## 5. Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**exercice bonus n°9** (1:21–1:25) — il est dans le support.
2. Compresser Log4Shell à une phrase (renvoyer au support), garder Equifax entier.
3. Raccourcir le débrief du sondage n°5 (opinion) à 90 secondes.

**Ne JAMAIS couper :** l'activité de priorisation (n°2-4), la règle d'or de la RAM, le mini-scénario, la fiche réflexe co-rédigée, le quiz n°6-8, la clôture avec devoirs et teaser.

**Si vous êtes en avance :**
- Poser les questions de réflexion du support (le REX sacrifié, la restauration sans éradication, les maillons d'Equifax).
- Pour les curieux : décoder ensemble le vecteur CVSS `AV:N/AC:L/PR:N/UI:N` (bloc mentor) — le profil « ver » de WannaCry (B03).

## 6. Travail en autonomie (Self-paced)
* **Avant la session suivante (B19)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Incident Response Fundamentals"* (durée estimée : 1h30).
  * **Préparation de la simulation** : Réfléchir — si votre organisation (ou une PME type MedDistri) était frappée demain matin par un rançongiciel, quelles 4-5 fonctions composeraient la cellule de crise ? Notez votre liste : elle sera mise à l'épreuve dès l'ouverture de B19.
