# Plan de séance — Session B02 : Paysage des menaces & acteurs
Parcours : B 20 sessions  |  Module : A — Fondations  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (verbes d'action)
- **Catégoriser** les quatre principaux profils de cyberattaquants (cybercriminels, États-nations, hacktivistes, menaces internes) et expliquer leurs motivations respectives.
- **Expliquer** le fonctionnement de la cybercriminalité moderne comme une économie de services (*Ransomware-as-a-Service*, courtiers d'accès).
- **Identifier** les sources de renseignement sur les menaces (*Cyber Threat Intelligence* : CERT-FR, MITRE ATT&CK) et le rôle des IoC et des TTP.

## Prérequis & progression
- **Prérequis** : B01 (triade CIA — la grille d'analyse des impacts).
- **Lien de progression** : Cette session définit QUI attaque et POURQUOI ; la session B03 détaillera COMMENT (types d'attaques et vecteurs techniques utilisés par ces mêmes acteurs).

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama B02 ([spécifications](../slides/B_S02_slides_spec.md)).
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Premières victimes des rançongiciels en France (ANSSI) ? | C) TPE/PME/ETI et collectivités |
| 2 | 0:40 | Sondage | Lazarus Group : quelle famille d'attaquants ? | B) État-nation |
| 3 | 0:44 | Sondage | Pourquoi un groupe étatique braque-t-il des banques ? | B) Financer un État sous sanctions |
| 4 | 0:48 | Sondage | Que nous apprend le cas Lazarus ? | B) Les frontières entre catégories sont poreuses |
| 5 | 1:02 | Sondage | Faut-il payer la rançon ? | Opinion (pas de bonne réponse) |
| 6 | 1:17 | Sondage | Partage de la rançon dans le modèle RaaS ? | B) 70-80 % affilié / 20-30 % opérateur |
| 7 | 1:19 | Sondage | Qu'est-ce qu'un IoC ? | A) Un indice technique de compromission |
| 8 | 1:21 | Sondage | Pourquoi la menace interne est-elle difficile à détecter ? | B) Elle utilise des accès légitimes |
| 9 | Tampon | Sondage | Départ conflictuel d'un administrateur : action prioritaire ? | B) Révoquer les accès + revoir les journaux |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil & retour sur le self-paced | Chat : présence |
| 0:04–0:10 | Brise-glace : qui sont les victimes ? | 📊 Sondage n°1 |
| 0:10–0:14 | Le portrait-robot du pirate | 💬 Chat : un mot |
| 0:14–0:28 | Séquence 1 : Typologie des attaquants | Question rhétorique |
| 0:28–0:38 | Séquence 2 : L'économie du cybercrime (RaaS) & chiffres | 💬 Chat : réactions |
| 0:38–0:52 | Activité : La Fiche d'identité d'un attaquant (Lazarus) | 📊 Sondages n°2, 3, 4 |
| 0:52–1:02 | Deux affaires réelles : Bangladesh 2016 & Cronos 2024 | 💬 Chat : réactions |
| 1:02–1:07 | Le grand débat : faut-il payer la rançon ? | 📊 Sondage n°5 |
| 1:07–1:10 | Mini-scénario : la veille qui sauve | 🤔 Chat : A, B ou C |
| 1:10–1:17 | Séquence 3 : La Cyber Threat Intelligence | Question rhétorique |
| 1:17–1:23 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:23–1:26 | Exercice bonus : le départ de l'administrateur (tampon) | 📊 Sondage n°9 |
| 1:26–1:30 | Synthèse, devoirs & teaser B03 | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & retour sur le self-paced

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous, et bienvenue dans cette deuxième session ! La semaine dernière, vous avez appris à mesurer les dégâts d'une attaque avec la triade C-I-D. Ce soir, on change de camp : on va étudier l'adversaire. Qui nous attaque, pourquoi, et avec quels moyens. Pour commencer, dites-moi dans le chat : avez-vous eu le temps de suivre le module SkillsBuild ? Oui / pas encore / en cours. »

**Points à dérouler :**
- Lire 3-4 réponses du chat, dédramatiser pour les retardataires (les modules restent accessibles).
- Rappel express de B01 : la triade C-I-D, les trois familles d'impacts, les deux cas français (CHSF, France Travail).
- Annonce du programme : typologie des attaquants → économie du cybercrime → un braquage de banque à 81 millions de dollars → comment faire de la veille.

**Transition scriptée :** « Première question, et je vous préviens : la réponse surprend. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (les premières victimes)

**Consigne :** Lancer le **📊 Sondage n°1** — quelles structures sont les premières victimes des rançongiciels en France ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse C : les TPE, PME, ETI et les collectivités territoriales, selon le Panorama de la cybermenace 2024 de l'ANSSI. Pas les géants du CAC 40. Pourquoi ? Parce que la majorité des attaquants sont des opportunistes : ils n'attaquent pas ce qui est prestigieux, ils attaquent ce qui est mal fermé. "Trop petit pour intéresser les pirates" est la phrase la plus dangereuse de la cybersécurité. Toute cette session sert à comprendre QUI attaque — pour calibrer sa défense. »

**Transition scriptée :** « Avant de vous donner la typologie officielle, j'aimerais voir l'image que VOUS avez de l'attaquant. »

### 0:10–0:14 — 💬 Le portrait-robot du pirate

**Consigne :** Question chat — *« Décrivez en UN mot le cyberattaquant tel que vous l'imaginez : capuche, génie, adolescent, solitaire... Tapez votre mot ! »* Lire 5-6 mots à voix haute, regrouper les clichés.

**🎙️ Formulation de synthèse :**
> « Beaucoup de "capuche", de "génie", de "solitaire"... C'est l'image du cinéma. La réalité que nous allons voir : des organisations avec des horaires de bureau, une division du travail et même un service client. Et le cliché le plus dangereux, c'est "génie" : la plupart des attaques réussissent par des moyens banals contre des cibles mal protégées. »

### 0:14–0:28 — Séquence 1 : Typologie des attaquants

**Points de contenu à dérouler (support §1) :**
- **Les cybercriminels** (motivation lucrative) : le groupe le plus représenté ; des opportunistes qui scannent Internet en masse — rançongiciels, vols de données bancaires.
- **Les États-nations / APT** (géopolitique, espionnage, sabotage) : ressources quasi illimitées, furtivité extrême, des mois de préparation ; expliquer chaque mot d'*Advanced Persistent Threat* — « persistant » = installé pendant des mois sans se faire détecter.
- **Les hacktivistes** (idéologie) : DDoS et défiguration de sites (*defacement*) pour la visibilité d'une cause.
- **La menace interne** (*insider threat*, motivation variée) : malveillance, appât du gain ou — cas le plus fréquent — simple négligence ; ses actions se fondent dans le trafic légitime.
- Ajouter les **script kiddies** : peu qualifiés, outils tout faits, dangereux par le nombre — le niveau d'entrée dans l'attaque n'a jamais été aussi bas.
- Question rhétorique : *« Se protège-t-on d'un voleur opportuniste comme d'un service de renseignement ? »* — non : hygiène de base contre l'un, détection avancée contre l'autre. C'est le fil rouge de la session.

**Transition scriptée :** « Zoomons sur la première famille, les cybercriminels — parce que leur organisation va vous surprendre. »

### 0:28–0:38 — Séquence 2 : L'économie du cybercrime

**Points de contenu à dérouler (support §2 et §3) :**
- Oublier le pirate solitaire : une industrie avec division du travail.
- **Le RaaS** : les opérateurs développent et louent le rançongiciel, les affiliés mènent l'intrusion ; partage type de la rançon 70-80 % / 20-30 %.
- **La spécialisation** : les *Initial Access Brokers* (courtiers qui revendent des accès), les négociateurs, les blanchisseurs en cryptomonnaies ; les places de marché du Dark Web ; le « support client » ; la gestion de réputation (un groupe qui ne livre pas la clé perd ses « clients »).
- **Les chiffres (support §3, sources à citer)** : plus d'un milliard de dollars de rançons payées dans le monde en 2023 — un record (Chainalysis) ; plus d'un milliard et demi de dollars en cryptomonnaies dérobés en une année par les groupes liés à la Corée du Nord au plus fort de leur activité (Chainalysis) ; février 2024, l'opération Cronos frappe LockBit (annoncer : « on y revient dans vingt minutes »).
- Relance chat : *« Un service client chez les rançonneurs — ça vous étonne ? »* — lire 2-3 réactions.

**Transition scriptée :** « Vous connaissez maintenant les familles et l'économie. Passons à la pratique : je vous présente un groupe réel, et c'est vous qui allez remplir sa fiche d'identité. »

### 0:38–0:52 — Activité : La Fiche d'identité d'un attaquant (Sondages n°2 à 4)

**Consigne :** Afficher la description du **Lazarus Group** (support, activité « Fiche d'identité ») et la lire à voix haute : actif depuis 2009, lié à un État d'Asie de l'Est, Sony Pictures 2014, Banque du Bangladesh 2016, WannaCry 2017, cible banques et plateformes crypto. Puis lancer les **📊 Sondages n°2, 3, 4** l'un après l'autre (~4-5 min chacun : vote, puis débrief avant la rubrique suivante).

**🎙️ Verbatim de lancement :**
> « Vous êtes analystes en renseignement sur les menaces. Voici le dossier d'un groupe bien réel. Première rubrique de la fiche : dans quelle famille le classez-vous ? Attention, il y a un piège... »

**Débriefs scriptés (points obligatoires) :**
- N°2 (catégorie) : le piège est A — la motivation financière ne suffit pas à classer, c'est le **commanditaire** qui compte. Lazarus est un APT étatique qui braque des banques.
- N°3 (motivation) : un État sous sanctions internationales ne peut plus se financer par les circuits classiques — le braquage numérique devient une politique publique ; d'où le ciblage des cryptomonnaies (difficiles à geler).
- N°4 (la leçon) : les frontières entre catégories sont poreuses — un même groupe peut espionner, saboter ET braquer ; la classification sert à raisonner, pas à enfermer. Conclure la fiche complète (origine présumée : Corée du Nord ; attaques majeures : Sony 2014, Bangladesh 2016, WannaCry 2017).

**Transition scriptée :** « Le braquage du Bangladesh mérite qu'on s'y arrête : c'est l'histoire d'un milliard de dollars sauvé par une faute d'orthographe. »

### 0:52–1:02 — Deux affaires réelles

**Cas n°1 — Banque du Bangladesh, 2016 (5 min, support §4) :** raconter chronologiquement : des mois d'infiltration via le réseau SWIFT, l'étude des procédures, la neutralisation des impressions de confirmation, le choix du jeudi soir (quatre jours de battement entre les week-ends du Bangladesh et de New York), l'objectif de près d'un milliard de dollars, les 81 millions partis vers des casinos asiatiques — et la faute d'orthographe (« fandation » au lieu de « foundation ») qui a alerté une banque intermédiaire. Leçon d'humilité : les défenses ont échoué, c'est la chance qui a limité les dégâts. Face à un APT, la question n'est pas « comment l'empêcher d'entrer » mais « comment le détecter avant qu'il n'agisse » (teaser du threat hunting, B16).

**Cas n°2 — LockBit & l'opération Cronos, 2024 (5 min, support §4) :** février 2024, la bannière des forces de l'ordre sur le site du groupe le plus prolifique au monde — celui-là même qui avait frappé l'hôpital de Corbeil-Essonnes vu en B01. Coalition NCA/FBI/Europol/Gendarmerie nationale : serveurs saisis, code source, portefeuilles, **clés de déchiffrement remises aux victimes**, affiliés arrêtés, opérateur principal identifié et sanctionné. Le talon d'Achille du RaaS : son infrastructure et sa réputation. Punchline : « des victimes de 2022 qui n'avaient pas payé ont récupéré leurs données en 2024 — le dépôt de plainte n'est jamais inutile. »

**Transition scriptée :** « Ces deux histoires posent LA question que toute direction finit par poser un jour. Votez. »

### 1:02–1:07 — Le grand débat : Sondage n°5 (faut-il payer ?)

**Consigne :** Lancer le **📊 Sondage n°5** (opinion) — votre organisation est paralysée, faut-il payer la rançon ? Vote 60-90 s, annoncer qu'il n'y a pas de « bonne » réponse.

**🎙️ Débrief scripté :**
> « Sondage d'opinion — mais il y a des repères solides. L'ANSSI et les forces de l'ordre recommandent de ne pas payer : aucune garantie de récupérer une clé fonctionnelle, vous vous signalez comme "bon payeur", et chaque paiement alimente le milliard annuel qu'on vient de voir. En France, depuis la loi LOPMI de 2023, une entreprise ne peut être indemnisée d'une cyber-rançon par son assurance que si elle dépose plainte sous 72 heures. Et Cronos a fourni l'argument final : des victimes qui n'avaient PAS payé ont fini par récupérer leurs données gratuitement. »

### 1:07–1:10 — 🤔 Mini-scénario : la veille qui sauve

**Consigne :** Afficher le mini-scénario du support : votre veille signale que votre secteur est ciblé via une faille sur les passerelles VPN — rien d'anormal détecté chez vous. *« Tapez A, B ou C dans le chat. »*

**Débrief :** B — appliquer le correctif immédiatement ET vérifier les journaux des dernières semaines. A confond « pas détecté » et « pas attaqué » ; C (tout débrancher) est disproportionné. C'est exactement la définition de la CTI : transformer le renseignement en action AVANT l'attaque.

**Transition scriptée :** « Ce réflexe a un nom et des outils : la Cyber Threat Intelligence. »

### 1:10–1:17 — Séquence 3 : La Cyber Threat Intelligence

**Points de contenu à dérouler (support §5) :**
- **CTI** : collecter, analyser, organiser l'information sur les attaquants actifs — jouer avec un coup d'avance.
- **IoC** (indicateurs de compromission) : adresses IP, empreintes de fichiers, domaines — les indices laissés sur la scène ; les partager (MISP, CERT-FR), c'est vacciner la communauté avec l'expérience des victimes.
- **TTP** : le mode opératoire signature d'un groupe, documenté dans **MITRE ATT&CK** — l'encyclopédie mondiale des techniques, groupe par groupe (la fiche « Lazarus Group » y existe).
- **Le premier réflexe professionnel** : s'abonner aux alertes du **CERT-FR** (gratuit) — c'est d'ailleurs le devoir de la semaine.
- Question rhétorique : *« À quoi sert de connaître le mode opératoire d'un groupe qui ne nous a pas encore attaqués ? »* — à corriger en priorité ce que CE groupe exploite : la défense guidée par le renseignement.

**Transition scriptée :** « Vérifions que l'essentiel est en place : trois questions, trois votes. »

### 1:17–1:23 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : partage 70-80 % affilié / 20-30 % opérateur ; l'IoC est un indice technique ; la menace interne utilise des accès légitimes. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/B_S02_support.md).

### 1:23–1:26 — Exercice bonus (Sondage n°9) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°9** — l'administrateur systèmes qui part en mauvais termes vendredi soir : action prioritaire ? Débrief : révoquer tous les accès dès le départ effectif et revoir ses journaux d'activité (B) ; la clause de confidentialité (A) n'empêche rien techniquement ; attendre l'audit annuel (C) laisse des mois d'exposition. La menace interne se gère par des **processus** (*offboarding*). À couper en cas de retard.

### 1:26–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Ce soir, vous avez rencontré l'adversaire : quatre familles aux motivations différentes, une économie qui se mesure en milliards, un groupe étatique qui braque des banques — et la preuve, avec Cronos, que la riposte existe. Votre nouvelle règle d'or : connaître son ennemi pour calibrer sa défense. Avant de partir : tapez dans le chat UN mot que vous retenez de cette session. »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Self-paced : module IBM SkillsBuild *"Cybersecurity Threat Landscape"* (~1h30) + s'abonner aux alertes du CERT-FR et repérer une alerte récente de vulnérabilité majeure (elle servira en B03).
- Teaser B03 : « la semaine prochaine, on ouvre l'arsenal : malwares, hameçonnage, déni de service — et l'histoire du ver qui a paralysé des hôpitaux entiers en un week-end. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**Exercice bonus n°9** (1:23–1:26) — il est dans le support en exercice bonus.
2. Compresser « Le portrait-robot du pirate » (0:10–0:14) à 2 min (3 mots lus).
3. Raccourcir le débrief du sondage n°5 au seul message ANSSI + LOPMI (gagner 2 min).
4. Ne JAMAIS couper : l'activité Lazarus, les deux affaires réelles, le quiz.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°1 : défendre contre un opportuniste vs un APT — excellent débat de chat).
2. Montrer en partage d'écran la fiche « Lazarus Group » dans MITRE ATT&CK et une alerte active du CERT-FR (aperçu concret de la veille).
3. Questions/réponses libres.

## Travail en autonomie (Self-paced)
* **Avant la session suivante (B03)** :
  * **Sur IBM SkillsBuild** : Suivre le module *"Cybersecurity Threat Landscape"* (~1h30).
  * **Exercice de veille** : S'abonner aux alertes par e-mail ou flux RSS du CERT-FR (cyber.gouv.fr) et sélectionner une alerte récente de vulnérabilité majeure pour en discuter en session B03.
