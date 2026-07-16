# Plan de séance — Session B13 : Gouvernance & cadres de sécurité
Parcours : B 20 sessions  |  Module : D — Gouvernance, risques & conformité  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (verbes d'action)
- **Expliquer** la structure, l'utilité et le portage d'une Politique de Sécurité des Systèmes d'Information (PSSI).
- **Comparer** les référentiels ISO 27001 (management certifiable, PDCA) et NIST CSF 2.0 (cadre opérationnel en 6 fonctions, dont *Govern*).
- **Distinguer** les rôles du RSSI (conseiller, orchestrer) et de la Direction Générale (décider, financer, assumer — y compris au sens de NIS2).

## Prérequis & progression
- **Prérequis** : Modules A à C — la technique est en place, reste à la piloter.
- **Lien de progression** : Ouverture du module D — cette session pose le cadre politique et stratégique, immédiatement suivie de l'analyse des risques (B14) et de la conformité juridique (B15, avec l'Atelier de Synthèse 3).

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama B13 ([spécifications](../slides/B_S13_slides_spec.md)).
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | La 6e fonction ajoutée par le NIST CSF 2.0 (2024) ? | A) Govern — Gouverner |
| 2 | 0:24 | Sondage | La meilleure règle PSSI « mots de passe » ? | B) Unique, 12+, gestionnaire obligatoire |
| 3 | 0:28 | Sondage | La meilleure règle PSSI « télétravail » ? | C) Matériel fourni uniquement, personnel interdit |
| 4 | 0:32 | Sondage | Ces règles suffisent-elles à faire une PSSI ? | B) Non : il manque le portage par la Direction |
| 5 | 1:08 | Sondage | Une charte signée existe-t-elle chez vous ? | Opinion (pas de bonne réponse) |
| 6 | 1:16 | Sondage | Qui accepte le risque résiduel et assume ? | B) La Direction Générale |
| 7 | 1:18 | Sondage | ISO 27001 vs NIST CSF : la différence ? | A) Management certifiable vs cadre opérationnel |
| 8 | 1:20 | Sondage | Le « C » de PDCA ? | B) Vérifier l'efficacité (audits, indicateurs) |
| 9 | Tampon | Sondage | Prouver la prise de connaissance de la charte ? | B) La charte signée individuellement |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil, ouverture du module D & retour PCA/PRA | 💬 Chat : définitions trouvées |
| 0:04–0:10 | Brise-glace : la 6e fonction | 📊 Sondage n°1 |
| 0:10–0:22 | Séquence 1 : La PSSI | 💬 Chat : pourquoi écrire les règles ? |
| 0:22–0:36 | Activité : Le comité de rédaction PSSI | 📊 Sondages n°2, 3, 4 |
| 0:36–0:48 | Séquence 2 : ISO 27001 vs NIST CSF 2.0 | Question rhétorique |
| 0:48–0:58 | Séquence 3 : Direction vs RSSI (& NIS2) | 💬 Chat : qui est responsable ? |
| 0:58–1:08 | Chiffres clés & affaires Uber CSO + Yahoo | 💬 Chat : réactions |
| 1:08–1:12 | Et chez vous ? La charte signée | 📊 Sondage n°5 |
| 1:12–1:16 | Mini-scénario : le faux bug bounty | 🤔 Chat : A, B ou C |
| 1:16–1:22 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:22–1:26 | Exercice bonus : la preuve d'audit (tampon) | 📊 Sondage n°9 |
| 1:26–1:30 | Synthèse, devoirs & teaser B14 | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & ouverture du module D

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous, et bienvenue dans le module Gouvernance, risques et conformité ! Depuis douze sessions, on configure : pare-feux, MFA, sauvegardes. À partir de ce soir, on PILOTE : qui décide, qui est responsable, selon quelles règles. Votre recherche de la semaine : PCA et PRA. En une phrase dans le chat : la différence entre les deux ? »

**Points à dérouler :**
- Lire 2-3 réponses (attendu : continuité = continuer pendant la crise ; reprise = redémarrer après) — « on y reviendra en B19 ; gardez ces définitions. »
- Rappel express de B12 : la donnée sur son cycle de vie, OVHcloud, l'Atelier 2.
- Annonce du programme : la PSSI, les grands référentiels, les rôles — et deux affaires où la gouvernance a menti.

**Transition scriptée :** « Première question — et elle date de l'année dernière. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (la 6e fonction)

**Consigne :** Lancer le **📊 Sondage n°1** — la fonction ajoutée par le NIST CSF 2.0 en 2024. Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse A : GOUVERNER. Après dix ans, le référentiel technique le plus utilisé au monde a officialisé ce que le terrain criait : sans stratégie, sans rôles clairs, sans arbitrages assumés par la direction, les cinq fonctions techniques — identifier, protéger, détecter, répondre, restaurer — finissent par échouer. La gouvernance n'est pas une sixième étape : c'est le socle sous les cinq autres. Bienvenue dans le module D. »

**Transition scriptée :** « Et l'outil n°1 de la gouvernance, c'est un document. Pas n'importe lequel. »

### 0:10–0:22 — Séquence 1 : La PSSI

**Points de contenu à dérouler (support §1) :**
- Relance chat d'entrée : *« Pourquoi écrire des règles si les salariés sont de bonne foi ? »* — lire 2-3 réponses (attendu : harmoniser, prouver, sanctionner, survivre aux départs).
- La **PSSI** : le document stratégique ET juridique — l'analogie du Code de la Route (support).
- **La structure** : champ d'application, rôles et responsabilités, règles d'usage (mots de passe, messagerie, télétravail), sanctions.
- **Le portage** : sans validation et signature de la Direction Générale (et annexion au règlement intérieur), ce n'est pas une politique — c'est une liste de conseils de la DSI.
- **Le test d'une bonne règle** : claire, mesurable, réaliste — une règle inapplicable sera contournée et décrédibilise tout le document (rappel B08 : la sécurité qui dit toujours non finit contournée).

**Transition scriptée :** « Passons de la théorie à la plume : EcoLog rédige sa PSSI, et c'est vous le comité de relecture. »

### 0:22–0:36 — Activité : Le comité de rédaction PSSI (Sondages n°2 à 4)

**Consigne :** Pour chaque sujet, afficher les trois formulations candidates (support, activité « Le comité de rédaction »), lancer le vote (**📊 n°2, 3, 4**, ~4-5 min chacun), débriefer sur les critères.

**🎙️ Verbatim de lancement :**
> « Trois versions d'une même règle : une seule mérite d'entrer dans la PSSI. Votre grille de lecture : est-elle claire ? mesurable ? réaliste ? Premier sujet : les mots de passe. »

**Débriefs scriptés (points obligatoires) :**
- N°2 : A est un vœu pieux (rien de mesurable) ; C est irréaliste — la règle inapplicable finit sur un post-it, et c'est TOUTE la PSSI qui perd sa crédibilité. B : claire, mesurable, réaliste.
- N°3 : « à éviter dans la mesure du possible » n'a aucune valeur d'audit ni juridique. C interdit ET s'explique : le durcissement de B08 (EDR, chiffrement) n'existe que sur le matériel maîtrisé.
- N°4 : LE point de gouvernance de la soirée — sans validation de la Direction, sanctions prévues et intégration au règlement intérieur, ces belles règles ne sont pas opposables. Une PSSI est un acte de direction. (Et le piège C confond politique et documentation technique : la PSSI fixe le « quoi », pas le « comment ».)

**Transition scriptée :** « Notre PSSI est bien née. Mais sur quoi s'appuyer pour structurer TOUTE la démarche ? Deux boussoles mondiales. »

### 0:36–0:48 — Séquence 2 : ISO 27001 vs NIST CSF 2.0

**Points de contenu à dérouler (support §2) :**
- **ISO 27001** : la norme du **management** — elle ne prescrit aucun outil, elle impose un SMSI : politiques écrites, processus, audits, preuves, direction impliquée ; le cycle **PDCA** (planifier, déployer, **vérifier**, ajuster) ; et à la clé : la **certification** — opposable aux clients.
- **NIST CSF 2.0** : le cadre **opérationnel** — dérouler les 6 fonctions : **Govern** (2024 — transversale : stratégie, rôles, politiques, chaîne d'approvisionnement), Identify, Protect, Detect (B16 !), Respond (B19 !), Recover (les sauvegardes de B12, vos PCA/PRA).
- L'**analogie du bâtiment** : ISO = le code de la construction et le manuel de gestion ; NIST = le plan d'action des pompiers — et depuis 2.0, qui dirige et rend des comptes.
- Question rhétorique : *« Faut-il choisir ? »* — non : beaucoup pilotent avec le CSF et se certifient ISO. Les deux se complètent.

**Transition scriptée :** « Ces référentiels disent tous la même chose au fond : quelqu'un doit décider — et assumer. Qui ? »

### 0:48–0:58 — Séquence 3 : Direction vs RSSI (& NIS2)

**Points de contenu à dérouler (support §3) :**
- **Le RSSI** : l'expert, le conseiller, le chef d'orchestre — il analyse, rédige, recommande, sensibilise... mais **ne décide pas** des arbitrages stratégiques.
- **La Direction Générale** : elle valide les budgets, accepte formellement le risque résiduel, et **assume** — civilement, et désormais plus personnellement encore avec **NIS2** (la directive européenne rend les organes de direction responsables de la supervision des risques cyber).
- **Le rattachement du RSSI** : sous la DSI, il juge son propre patron (production vs sécurité) — les organisations matures le rattachent à la direction générale ou aux risques.
- Relance chat (0:55) : *« Dans votre organisation, qui serait tenu responsable d'une fuite majeure ? Tapez le poste. »* — lire 3-4 réponses ; conclure : la bonne réponse tend vers « la direction », pas « l'informaticien ».

**Transition scriptée :** « Et quand la gouvernance ment ? Deux histoires — un casier judiciaire et 350 millions de dollars. »

### 0:58–1:08 — Chiffres clés & deux affaires réelles

**Chiffres (2 min, support §4) :** février 2024 — le CSF 2.0 et la fonction Govern ; 350 M$ de décote + 35 M$ d'amende SEC pour Yahoo ; 2022 — la première condamnation pénale d'un CSO pour la gestion d'une violation.

**Cas n°1 — Uber, 2016-2022 (4 min, support §5) :** raconter : la fuite de 2016, l'entreprise déjà sous enquête du régulateur ; le CSO qui organise le silence — 100 000 $ aux attaquants maquillés en « bug bounty », accord de confidentialité ; la révélation un an plus tard par la nouvelle direction ; la condamnation fédérale en 2022 (obstruction et dissimulation). Leçons : la gestion d'incident est un acte de gouvernance ; le bug bounty ne blanchit pas une extorsion ; et le professionnel doit savoir dire non — par écrit — à sa hiérarchie. « Dans dix minutes, ce sera VOTRE dilemme. »

**Cas n°2 — Yahoo, 2013-2017 (4 min, support §5) :** raconter : les fuites géantes de 2013-2014 (jusqu'à 3 milliards de comptes), le silence interne ; la vérité qui éclate en pleine négociation du rachat par Verizon → **350 M$ de décote** ; l'amende SEC de 35 M$ (2018) — la première pour défaut d'information des investisseurs sur une cyberattaque. Leçons : une violation est une information financière majeure ; la dissimulation a transformé l'incident en scandale de gouvernance ; la cybersécurité est un sujet de conseil d'administration — exactement ce qu'actent CSF 2.0 et NIS2. Relance chat : *« Quel détail vous marque le plus ? »*

### 1:08–1:12 — Sondage n°5 : et chez vous, la charte ?

**Consigne :** Lancer le **📊 Sondage n°5** (opinion) — une charte informatique signée existe-t-elle chez vous ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « B est extrêmement répandu : le document existe, le portage n'existe pas. Or une charte non signée n'est ni opposable, ni auditable. Trois questions pour lundi matin : où est notre charte ? qui l'a signée ? la Direction l'a-t-elle validée ? Trois minutes — et souvent trois surprises. »

### 1:12–1:16 — 🤔 Mini-scénario : le faux bug bounty

**Consigne :** Afficher le mini-scénario du support : le prestataire propose de payer les pirates 50 000 € déguisés en bug bounty pour « ne rien avoir à notifier ». *« Tapez A, B ou C dans le chat. »*

**Débrief :** B — c'est mot pour mot le scénario Uber, qui a valu au CSO une condamnation pénale. La notification CNIL sous **72 heures** est une obligation légale (RGPD — approfondi en B15) ; la dissimulation transforme la victime en fautif ; et l'écrit protège le professionnel qui a alerté. C supprime même la traçabilité — le pire des trois. La formule à retenir : on ne négocie pas sa transparence.

**Transition scriptée :** « Trois questions pour ancrer les fondations du module. »

### 1:16–1:22 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : la Direction décide et assume ; ISO = management certifiable vs CSF = cadre opérationnel ; Check = vérifier l'efficacité. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/B_S13_support.md).

### 1:22–1:26 — Exercice bonus (Sondage n°9) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°9** — prouver à l'auditeur la prise de connaissance de la charte ? Débrief : la charte signée individuellement (B) — en audit, ce qui n'est pas prouvé n'existe pas (*accountability*). Le prolongement direct du sondage n°5. À couper en cas de retard.

### 1:26–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Ce soir, vous avez pris de la hauteur : une politique qui n'est une politique que signée par la Direction ; deux référentiels complémentaires — le management certifiable et les six fonctions ; des rôles clairs — le RSSI conseille, la Direction assume ; et deux affaires qui tiennent en une phrase : cacher coûte toujours plus cher que réparer. Un mot que vous retenez, dans le chat ! »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Self-paced : cours IBM SkillsBuild *"Cybersecurity Governance and Risk Management - Part 1"* (~1h30) + poser les trois questions de la charte dans son organisation + réfléchir à un risque NON informatique de son quotidien professionnel et comment il est géré (préparation directe de B14).
- Teaser B14 : « la semaine prochaine : combien vaut un risque ? Une formule qui tient sur un ticket de métro, une matrice à seize cases — et l'histoire de l'assureur qui a refusé de payer 100 millions de dollars en invoquant... un acte de guerre. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**Exercice bonus n°9** (1:22–1:26) — il est dans le support en exercice bonus.
2. Compresser la relance chat de la séquence 3 (1 réponse lue).
3. Raccourcir le débrief du sondage n°5 à 1 min.
4. Ne JAMAIS couper : l'activité PSSI, les deux affaires, le quiz.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°1 : le rattachement du RSSI et le conflit d'intérêts).
2. Faire rédiger par le chat une 5ᵉ règle PSSI (usage de l'IA générative en entreprise — sujet d'actualité, excellent débat).
3. Questions/réponses libres.

## Travail en autonomie (Self-paced)
* **Avant la session suivante (B14)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Cybersecurity Governance and Risk Management - Part 1"* (durée estimée : 1h30).
  * **Enquête interne** : Poser les trois questions de la charte dans votre organisation (où est-elle ? qui l'a signée ? la Direction l'a-t-elle validée ?).
  * **Préparation de B14** : Identifier un risque NON informatique de votre quotidien professionnel (retard fournisseur, panne, accident) et observer comment il est géré — la même logique s'appliquera aux risques cyber.
