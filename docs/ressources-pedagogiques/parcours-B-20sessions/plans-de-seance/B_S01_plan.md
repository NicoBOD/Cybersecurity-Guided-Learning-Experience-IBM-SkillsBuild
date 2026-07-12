# Plan de séance — Session B01 : Introduction à la cybersécurité & triade CIA
Parcours : B 20 sessions  |  Module : A — Fondations  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (verbes d'action)
- **Définir** les trois piliers de la triade CIA (Confidentialité, Intégrité, Disponibilité) avec des exemples d'incidents réels.
- **Expliquer** les impacts business (financiers, juridiques, réputationnels) des cyberattaques sur les entreprises.
- **Identifier** la diversité des métiers de la cybersécurité (Red Team, Blue Team, RSSI) et les opportunités de carrière.

## Prérequis & progression
- **Prérequis** : Aucun (première session du parcours).
- **Lien de progression** : Socle de toute la formation — la triade CIA est la grille d'analyse obligatoire pour aborder le paysage des menaces (B02) et tout le reste du parcours.

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama B01 ([spécifications](../slides/B_S01_slides_spec.md)).
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:05 | Sondage | Part du facteur humain dans les violations ? | C) ~60 % |
| 2 | 0:30 | Sondage | Rançongiciel sur hôpital → premier pilier touché ? | C) Disponibilité |
| 3 | 0:34 | Sondage | Note modifiée de 08 à 18 → pilier violé ? | B) Intégrité |
| 4 | 0:38 | Sondage | Fichier clients publié par erreur → pilier ? | A) Confidentialité |
| 5 | 1:10 | Sondage | Quelle posture cyber vous attire ? | Opinion (pas de bonne réponse) |
| 6 | 1:14 | Sondage | Impact le plus destructeur à long terme ? | C) Réputationnel |
| 7 | 1:16 | Sondage | La règle du maillon le plus faible ? | A) Force = composant le plus faible |
| 8 | 1:18 | Sondage | Qui simule des attaques dans un cadre légal ? | B) La Red Team |
| 9 | Tampon | Sondage | Ransomware sur hôpital : première action ? | B) Isoler le réseau |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:05 | Accueil & cadre du parcours B | Chat : présence |
| 0:05–0:11 | Brise-glace : le facteur humain | 📊 Sondage n°1 |
| 0:11–0:16 | Le monde sans sécurité | 💬 Chat : brainstorming |
| 0:16–0:30 | Séquence 1 : La triade CIA | 💬 Chat : « C, I ou D ? » |
| 0:30–0:44 | Activité : Qualification d'incidents | 📊 Sondages n°2, 3, 4 |
| 0:44–0:54 | Séquence 2 : Les impacts business | Question rhétorique |
| 0:54–1:04 | Chiffres & cas réels (CHSF, France Travail) | 💬 Chat : réactions |
| 1:04–1:14 | Séquence 3 : Les métiers de la cyber | 📊 Sondage n°5 |
| 1:14–1:20 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:20–1:25 | Dilemme décisionnel (tampon) | 📊 Sondage n°9 |
| 1:25–1:30 | Synthèse, devoirs & teaser B02 | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:05 — Accueil & cadre du parcours

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous, et bienvenue dans la première des vingt sessions de votre parcours cybersécurité ! Je suis [Prénom], votre mentor. Le format : tout se passe dans le **chat** et via les **sondages** — vous êtes nombreux, et c'est ainsi que chacun pourra participer. Test immédiat : écrivez dans le chat la ville d'où vous nous suivez. »

**Points à dérouler :**
- Se présenter (30 secondes), lire 3-4 villes du chat.
- Le cadre : 20 sessions de 1h30, 6 modules (fondations → réseau → identités/cloud → gouvernance → opérations → grand atelier final MedDistri), 4 ateliers de synthèse intermédiaires.
- Règle d'or : pas de question bête ; le chat est ouvert en permanence.

**Transition scriptée :** « On commence par un chiffre qui va donner le ton des vingt semaines. »

### 0:05–0:11 — Brise-glace : Sondage n°1 (le facteur humain)

**Consigne :** Lancer le **📊 Sondage n°1** — la part du facteur humain dans les violations. Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse C : environ 60 %, selon le rapport Verizon DBIR 2025. Six violations sur dix impliquent une erreur, un clic, un mot de passe volé. Retenez ce chiffre : la cybersécurité est d'abord une affaire de personnes. Et la bonne nouvelle : en vous formant, vous devenez une ligne de défense — et peut-être un futur professionnel du secteur, on en reparle en fin de session. »

**Transition scriptée :** « Avant la théorie, une expérience de pensée. »

### 0:11–0:16 — 💬 Le monde sans sécurité

**Consigne :** Question chat — *« Imaginez : votre smartphone cesse de fonctionner, les feux de signalisation de la ville sont piratés, vos données bancaires sont publiées. Quel est le PREMIER impact auquel vous pensez ? Un mot ou une phrase dans le chat. »* Lire 4-5 réponses à voix haute.

**🎙️ Formulation de synthèse :**
> « Vos réponses parlent d'argent, de vie privée, de sécurité physique, de confiance... Tout cela tient en trois lettres que vous allez utiliser pendant vingt semaines : C, I, D. »

### 0:16–0:30 — Séquence 1 : La triade CIA

**Points de contenu à dérouler (support §1) :**
- L'acronyme : CIA vient de l'anglais (*Confidentiality, Integrity, Availability*) — en français CID, le « D » pour Disponibilité.
- **Confidentialité** : la lettre scellée à la cire ; exemple : dossiers médicaux revendus sur le darknet.
- **Intégrité** : le grand livre comptable à l'encre indélébile ; exemple : l'IBAN modifié dans le système de facturation.
- **Disponibilité** : l'électricité domestique ; exemple : le DDoS qui sature le site d'une banque.
- La **règle du maillon le plus faible** : l'attaquant ne force pas la porte blindée, il cherche la porte ouverte — souvent humaine (rappel du sondage n°1).

**Interaction (0:27) — 💬 Question chat :**
> « Pensez à votre métier : laquelle des trois lettres — C, I ou D — serait la plus grave à perdre pour vous ? Tapez la lettre, avec votre secteur si vous voulez. » — lire 4-5 réponses ; conclure : la réponse dépend du métier (hôpital → D, banque → I, avocat → C).

**Transition scriptée :** « La boussole est en main. Vérifions qu'elle fonctionne : trois enquêtes, trois votes. »

### 0:30–0:44 — Activité : Qualification d'incidents (Sondages n°2 à 4)

**Consigne :** Lancer les **📊 Sondages n°2, 3, 4** l'un après l'autre (~4-5 min chacun : présentation du scénario, vote, débrief). Scénarios et débriefs complets : voir le [support, section « Qualification d'incidents »](../supports-md/B_S01_support.md).

**🎙️ Verbatim de lancement :**
> « Vous êtes désormais analystes. Trois incidents viennent de tomber ; pour chacun, votre diagnostic : quel pilier est touché EN PREMIER ? Incident n°1 : un hôpital, des écrans de rançon, des dossiers chiffrés... »

**Débriefs scriptés (points obligatoires) :**
- N°2 (hôpital) : Disponibilité d'abord ; introduire la « double extorsion » (le vol avant chiffrement) ; mesure : sauvegardes hors ligne. Teaser : « ce scénario, on le retrouve en vrai dans vingt minutes. »
- N°3 (note d'étudiant) : Intégrité — l'attaque la plus discrète : rien de volé, rien de bloqué, juste une donnée faussée ; mesure : droits d'écriture restreints + journalisation.
- N°4 (fichier e-commerce) : Confidentialité — sans intrusion : une simple erreur de configuration ; mesure : moindre privilège + audits des partages.

### 0:44–0:54 — Séquence 2 : Les impacts business

**Points de contenu à dérouler (support §2) :**
- Les trois familles d'impacts : **financier direct** (perte d'exploitation, remédiation, rançon — déconseillée), **juridique** (RGPD : jusqu'à 20 M€ ou 4 % du CA mondial, approfondi en B15 ; litiges), **réputationnel** (le plus dur à chiffrer, le plus destructeur à long terme).
- Question rhétorique : *« Lequel des trois ruine une entreprise deux ans après l'attaque ? »* — la réputation : l'argent se réemprunte, la confiance ne se rachète pas.

**Transition scriptée :** « Des impacts théoriques ? Voyons les chiffres officiels — puis deux histoires vraies, françaises, récentes. »

### 0:54–1:04 — Chiffres & cas réels

**Chiffres (3 min, support §3) :** l'ANSSI et ses ~4 400 événements traités en 2024 (+15 %) avec les PME et collectivités en premières victimes ; ~4,4 M$ de coût moyen d'une violation et plusieurs mois pour confiner (IBM 2025) ; record de notifications CNIL en 2024. Message : l'attaque est un flux industriel qui vise d'abord ceux qui se croient trop petits.

**Cas n°1 — CHSF, 2022 (4 min, support §4) :** raconter chronologiquement : nuit du 20 au 21 août, LockBit, mode dégradé et retour au papier, 10 M$ exigés, refus (doctrine française), ~11 Go publiés en représailles, des mois de reconstruction. Relier au sondage n°2 : « votre diagnostic était le bon — Disponibilité, puis Confidentialité. »

**Cas n°2 — France Travail, 2024 (3 min, support §4) :** ~43 millions de personnes, comptes de partenaires usurpés, ni mot de passe ni RIB volés — et pourtant des années d'hameçonnage crédible en perspective. Punchline : « les données volées aujourd'hui sont les attaques de demain — rendez-vous en B04 pour voir comment. »

### 1:04–1:14 — Séquence 3 : Les métiers de la cybersécurité

**Points de contenu à dérouler (support §5) :**
- **Red Team** (offensive, sous contrat), **Blue Team** (défensive : SOC en B16, réponse aux incidents en B18), **RSSI** (stratégie et budgets, gouvernance en B13).
- Le marché : un déficit mondial de l'ordre de 4 à 5 millions de professionnels (études (ISC)², 2024) — « peu de secteurs offrent une telle sécurité de parcours ».

**Interaction (1:10) :** Lancer le **📊 Sondage n°5** (opinion) — quelle posture vous attire ? Débrief : aucune mauvaise réponse ; le parcours couvre les trois ; les « je ne sais pas encore » ont 19 sessions pour se décider.

### 1:14–1:20 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : réputationnel ; force = composant le plus faible ; Red Team. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/B_S01_support.md).

### 1:20–1:25 — Dilemme décisionnel (Sondage n°9) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°9** — le rançongiciel sur l'hôpital : première action d'urgence ? Débrief : isoler le réseau (B) coupe la propagation ; payer (A) ne garantit rien et finance le crime — le choix écarté par le CHSF ; restaurer sur un réseau compromis (C) = reconstruire la maison pendant l'incendie. À couper en cas de retard.

### 1:25–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Votre première boîte à outils : une boussole à trois lettres — C, I, D ; trois familles d'impacts — l'argent, la loi, la confiance ; et une carte des métiers. Deux histoires vraies ont prouvé que rien de tout cela n'est théorique. Avant de partir : tapez dans le chat UN mot que vous retenez de ce soir. »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Self-paced : cours IBM SkillsBuild *"Cybersecurity Fundamentals - Part 1"* (~1h30) + lire la synthèse du Panorama de la cybermenace de l'ANSSI.
- Teaser B02 : « la semaine prochaine : QUI nous attaque — cybercriminels, États, hacktivistes — et une histoire de braquage de banque à 81 millions de dollars... sans arme ni cagoule. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper le **Dilemme n°9** (1:20–1:25) — il est dans le support en exercice bonus.
2. Compresser « Le monde sans sécurité » (0:11–0:16) à 3 min (2 réponses lues).
3. Ne JAMAIS couper : la Qualification d'incidents, les deux cas réels, le quiz.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°3 : fallait-il payer la rançon ? — excellent débat de chat).
2. Approfondir la séquence métiers (parcours de formation, certifications — teaser du fil rouge du parcours).
3. Questions/réponses libres.

## Travail en autonomie (Self-paced)
* **Avant la session suivante (B02)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Cybersecurity Fundamentals - Part 1"* (durée estimée : 1h30).
  * **Lecture complémentaire** : Lire la synthèse du *Panorama de la cybermenace* de l'ANSSI (cyber.gouv.fr) — repérer un incident récent touchant une PME ou une collectivité.
