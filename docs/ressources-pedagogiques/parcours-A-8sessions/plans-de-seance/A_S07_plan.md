# Parcours A — Session 07 : Réponse aux incidents & introduction au forensics
Module : Réponse aux Incidents  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (4, verbes d'action)
- **Dérouler** les six étapes clés du cycle de réponse aux incidents (Préparation, Identification, Confinement, Éradication, Restauration, Leçons apprises) lors d'un scénario de compromission.
- **Isoler** les traces chronologiques d'une intrusion à partir d'un scénario d'alertes simplifié pour reconstituer le déroulement de l'attaque (patient zéro).
- **Expliquer** l'importance de l'ordre de volatilité et de la chaîne de contrôle (*chain of custody*) pour préserver la validité légale des preuves numériques.
- **Distinguer** le cadre légal du piratage éthique par rapport aux intrusions informatiques illégales (articles 323-1 et suivants du Code pénal).

## Prérequis
- Sessions précédentes : A1 à A6.
- Self-paced AVANT la séance (~60 min) : Lecture d'un article vulgarisé sur les notions fondamentales de forensics numérique. Découverte du cycle de réponse à incident (modèle NIST ou SANS).

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **10 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous). **Attention : les sondages n°1 et n°9 sont volontairement identiques** (mesure avant/après) — créez-les en double.
- [ ] Le partage d'écran est testé avec le diaporama S07 ([spécifications](../slides/A_S07_slides_spec.md)) — y compris les 5 cartes-événements de la Timeline (à afficher dans le désordre).
- [ ] Le [script de la Démo 7 — Une nuit en cellule de crise](../outils/A_scripts_demo.md#demo-7-incident) est relu ; les deux embranchements sont maîtrisés.
- [ ] Le chat est ouvert ; un modérateur remonte les questions si possible.
- [ ] Un minuteur est visible du mentor.

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Poste infecté : votre TOUT premier geste ? (vote AVANT — ne pas corriger) | B) Débrancher le réseau *(à taire)* |
| 2 | 0:28 | Sondage | Timeline : le point de départ réel de l'attaque ? | B) L'e-mail de lundi |
| 3 | 0:34 | Sondage | Quelle défense unique aurait cassé la chaîne ? | A) MFA sur le VPN |
| 4 | 0:54 | Sondage | Démo 7 — décision 1 : éteindre ou isoler ? | B) Isoler sans éteindre |
| 5 | 0:58 | Sondage | Démo 7 — décision 2 : restaurer tout de suite ? | B) Préserver puis restaurer sur base saine |
| 6 | 1:18 | Sondage | Que capture-t-on en premier ? | B) RAM et connexions actives |
| 7 | 1:20 | Sondage | À quoi sert le hachage dans la chaîne de contrôle ? | B) Prouver l'intégrité de la copie |
| 8 | 1:22 | Sondage | Tester le sous-traitant hors périmètre ? | B) Non : délit pénal |
| 9 | 1:24 | Sondage | Re-vote du n°1 (vote APRÈS — comparer) | B) Débrancher le réseau |
| 10 | Tampon | Sondage | Pourquoi ne pas réinstaller immédiatement ? | B) Préserver les traces |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil & fil rouge depuis A6 | Chat : alertes CERT-FR consultées |
| 0:04–0:10 | Le vote AVANT (sans correction) | 📊 Sondage n°1 |
| 0:10–0:15 | L'exercice d'évacuation | 💬 Chat : débat |
| 0:15–0:28 | Séquence 1 : Le cycle IR en 6 étapes | Question rhétorique |
| 0:28–0:40 | Activité : La Timeline du Détective | 📊 Sondages n°2, 3 |
| 0:40–0:52 | Séquence 2 : Forensics — volatilité & chaîne de contrôle | Question rhétorique |
| 0:52–1:02 | Démo 7 : Une nuit en cellule de crise | 📊 Sondages n°4, 5 |
| 1:02–1:10 | Séquence 3 : Cadre légal & doctrine de non-paiement | 💬 Chat : le chercheur zélé |
| 1:10–1:18 | Chiffres & cas réels (Maersk, retour CHSF) | 💬 Chat : la copie qui survivrait |
| 1:18–1:24 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:24–1:27 | Le vote APRÈS & comparaison | 📊 Sondage n°9 |
| 1:27–1:30 | Synthèse & consignes pour le Grand Atelier (A8) | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & fil rouge

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous ! Qui s'est abonné aux alertes du CERT-FR depuis la dernière fois ? Tapez dans le chat le titre d'une alerte que vous avez vue passer. [Lire 2-3 réponses.] Vous voilà branchés sur le système nerveux de la cyber française. La session A6 nous a appris à DÉTECTER. Aujourd'hui, le scénario que tout le monde redoute : l'attaque est confirmée, elle est en cours. Que fait-on dans les 60 premières minutes ? »

**Transition scriptée :** « Et justement, commençons par mesurer vos réflexes actuels — sans filet. »

### 0:04–0:10 — Le vote AVANT (Sondage n°1)

**Consigne :** Lancer le **📊 Sondage n°1** — *« Un poste affiche des signes d'infection active. Votre TOUT premier geste ? »* Laisser voter, **noter la répartition, ne PAS donner la réponse**.

**🎙️ Verbatim (après le vote) :**
> « Je vois vos réponses... et je ne dirai RIEN. Ni bravo, ni aïe. Je garde cette photographie au chaud, et nous referons exactement ce vote dans 80 minutes. Si cette session sert à quelque chose, la comparaison le montrera. Pression maximale sur moi, donc. Allons-y. »

### 0:10–0:15 — 💬 L'exercice d'évacuation

**Consigne :** Question chat — *« Dans vos bureaux ou votre école : que se passe-t-il quand l'alarme incendie sonne ? Qui fait quoi, et pourquoi ça marche ? »* Lire 3-4 réponses.

**🎙️ Formulation de synthèse :**
> « Tout le monde sait : on se lève, on suit les flèches vertes, on rejoint le point de rassemblement, le serre-file compte les présents. Pourquoi ça marche ? Parce que c'est ÉCRIT, RÉPÉTÉ et que chacun connaît son rôle — personne n'improvise. La réponse aux incidents cyber, c'est exactement cela : un plan d'évacuation pour vos données. Et il a 6 étapes. »

### 0:15–0:28 — Séquence 1 : Le cycle IR en 6 étapes

**Points de contenu à dérouler (support §1) :**
- Dérouler les 6 étapes du modèle SANS avec l'analogie pompiers filée : Préparation (les consignes affichées), Identification (l'alarme), Confinement (les portes coupe-feu), Éradication (éteindre le foyer ET les braises), Restauration (rouvrir les bureaux), Leçons apprises (la commission de sécurité).
- Précision de rigueur : 6 étapes = modèle **SANS** ; le **NIST** regroupe en 4 phases — les deux se valent, ne pas paniquer si un document en cite 4.
- Marteler l'ordre : restaurer avant d'éradiquer = réinstaller la maison pendant que le cambrioleur a le double des clés (écho du dilemme final d'A1).
- Confinement ≠ extinction : isoler du réseau, JAMAIS éteindre — teaser : « la démo de tout à l'heure vous fera vivre ce choix. »
- La Préparation inclut le canal de communication de secours : « si la messagerie est chiffrée, comment se parle la cellule de crise ? » (à préparer avant, pas à 3h du matin).

**Question rhétorique (0:26) :** *« Quelle étape est la plus souvent sautée, à votre avis ? »* — « la 6e, les leçons apprises — celle qui rapporte le plus. On y reviendra. »

### 0:28–0:40 — Activité : La Timeline du Détective (Sondages n°2 et 3)

**Consigne :** Projeter les **5 cartes-événements dans le désordre** (ordre d'affichage conseillé : C, A, E, B, D — le contenu des cartes est dans le [support, section « La Timeline du Détective »](../supports-md/A_S07_support.md)). Lancer le **📊 Sondage n°2** (le point de départ réel), débriefer en reconstituant la chronologie complète B → D → E → C → A à voix haute, puis le **📊 Sondage n°3** (la défense qui aurait cassé la chaîne).

**🎙️ Verbatim de lancement :**
> « Le SOC vous transmet cinq constats en vrac — un e-mail, des connexions, une alerte. Votre mission de détective : remettre l'histoire dans l'ordre. Premier vote : lequel de ces événements est le POINT DE DÉPART réel de l'attaque ? »

**Débriefs scriptés (points obligatoires) :**
- N°2 : l'alerte SIEM n'est pas l'attaque, elle en est la découverte — **41 heures plus tard**. Dérouler la chronologie complète en nommant les sessions : phishing (A2) → identifiants volés (A4) → déplacement latéral (A3) → exfiltration → alerte (A6).
- N°3 : le MFA sur le VPN — rejouer la hiérarchie d'A4. Leçon à marteler : **la réponse aux incidents commence des mois avant l'incident, dans l'architecture.** Et la phase 6 du cycle est ce qui transforme 41 heures d'aveuglement en correctif d'architecture.

**Transition scriptée :** « Vous savez reconstituer l'histoire. Encore faut-il que les preuves existent toujours quand l'enquêteur arrive. Bienvenue au forensics. »

### 0:40–0:52 — Séquence 2 : Forensics — volatilité & chaîne de contrôle

**Points de contenu à dérouler (support §2 + Focus pratique) :**
- La scène de crime numérique : collecter sans modifier — le forensics est la police scientifique du numérique.
- **L'ordre de volatilité** : dérouler le tableau du Focus pratique — RAM (mots de passe en clair, clés de chiffrement, connexions de l'attaquant : tout s'évapore à l'extinction) → connexions/processus actifs → fichiers temporaires → disque dur.
- D'où LE réflexe : **débrancher le réseau isole l'attaquant ; éteindre détruit les preuves.** Deux gestes qui se ressemblent, deux conséquences opposées.
- **La chaîne de contrôle** : copie bit-à-bit + empreinte SHA-256 (le « cachet de cire » d'A1 au service de la justice) + original scellé + journal des manipulations. Sans elle, la meilleure preuve est irrecevable.

**Question rhétorique (0:50) :** *« Pourquoi analyse-t-on toujours la copie et jamais l'original ? »* — « parce qu'analyser, c'est déjà modifier — et une preuve modifiée est une preuve morte. »

### 0:52–1:02 — Démo 7 : Une nuit en cellule de crise (Sondages n°4 et 5)

**Consigne :** Dérouler la [Démo 7 — Une nuit en cellule de crise](../outils/A_scripts_demo.md#demo-7-incident) : un scénario « livre dont vous êtes le héros » à deux embranchements, voté en direct. Lancer le **📊 Sondage n°4** à la première décision, raconter les conséquences du choix majoritaire ET du choix écarté, puis le **📊 Sondage n°5**.

**🎙️ Verbatim de lancement :**
> « Il est 3h12 du matin. Vous êtes d'astreinte. Le téléphone sonne : le serveur de fichiers chiffre ses propres données, un fichier TXT réclame une rançon. Vous êtes seul pour les dix prochaines minutes — et l'histoire s'écrit selon VOS votes. Première décision... »

**Points de débrief obligatoires :**
- N°4 (éteindre vs isoler) : dérouler les deux branches — celle qui éteint perd les clés de chiffrement en RAM et les preuves ; celle qui isole stoppe la propagation ET garde tout.
- N°5 (restaurer immédiatement vs préserver puis restaurer sur base saine) : la branche pressée restaure... avec la porte dérobée encore en place — re-compromission dans la semaine ; la branche méthodique clone, hache, puis restaure sur une infrastructure assainie.
- Conclure : « vous venez de vivre les étapes 3, 4 et 5 du cycle — et leurs pièges. En A8, vous revivrez cela à l'échelle d'une entreprise entière. »

### 1:02–1:10 — Séquence 3 : Cadre légal & doctrine

**Points de contenu à dérouler (support §3) :**
- Les articles 323-1 et suivants (STAD) : accès/maintien frauduleux = jusqu'à **2 ans et 60 000 €** ; avec altération de données = **3 ans et 100 000 €** ; entrave au fonctionnement = **5 ans et 150 000 €**. « La porte ouverte n'autorise pas le cambriolage » — un système mal sécurisé n'est pas une excuse légale.
- Le piratage éthique : ordre de mission ÉCRIT, périmètre, période, outils — hors du périmètre, même « pour aider », c'est un délit (rappel du scénario RDP d'A1 et du pentest d'A6).
- **La doctrine de non-paiement** : payer ne garantit rien, finance le crime, désigne un payeur récidivable (ANSSI) ; le dépôt de plainte conditionne désormais l'indemnisation par les cyber-assurances en France.

**Interaction (1:08) — 💬 Question chat :**
> « Un chercheur en sécurité découvre une faille critique sur le site de sa banque et l'exploite "pour prouver qu'il dit vrai" avant de la signaler. Héros ou délinquant ? Votez H ou D dans le chat. » — débrief : délinquant au sens pénal (accès frauduleux), quelle que soit l'intention ; la voie légale : signalement responsable sans exploitation.

### 1:10–1:18 — Chiffres & cas réels

**Chiffres (2 min, support §4) :** plusieurs mois pour confiner en moyenne (IBM 2025, rappel A1) vs l'objectif de l'IR : des heures ; les 72 h de la CNIL qui démarrent à la découverte (A5×A6) ; la doctrine de non-paiement ; annoncer Maersk.

**Cas n°1 — Maersk / NotPetya, 2017 (4 min, support §5) :** raconter : 27 juin 2017, ~4 000 serveurs et 45 000 postes irrécupérables en minutes, ports à l'arrêt, réservations au papier ; les sauvegardes de l'annuaire central détruites... sauf UNE — le contrôleur de domaine du **Ghana**, hors ligne grâce à une coupure de courant ; reconstruction mondiale en **10 jours** ; ~**300 M$** de pertes. Punchlines : « sauvés par une panne d'électricité » ; « ne confiez pas votre survie à une coupure de courant au Ghana : c'est ce que le 3-2-1 immuable d'A4 institutionnalise. »

**Cas n°2 — Retour à Corbeil-Essonnes (2 min, support §5) :** relire le cas d'A1 avec la grille de la session : identification nocturne, confinement et mode dégradé, refus de payer (doctrine), mois de reconstruction, leçons apprises nationales. Punchline : « la réponse aux incidents est un sport de direction générale autant que d'ingénieurs. »

**Interaction (1:16) — 💬 Question chat :** *« Existe-t-il chez vous une copie de données qui survivrait à un incident détruisant TOUT ce qui est connecté ? oui / non / je ne sais pas. »* — commenter : « les "je ne sais pas" sont la vraie majorité — c'est ce qu'un exercice révèle avant la réalité. »

### 1:18–1:24 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : la RAM d'abord ; prouver l'intégrité de la copie ; non, délit pénal. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/A_S07_support.md).

### 1:24–1:27 — Le vote APRÈS (Sondage n°9)

**Consigne :** Relancer **le sondage identique au n°1** (📊 Sondage n°9). Afficher les deux répartitions côte à côte.

**🎙️ Débrief scripté :**
> « Regardez le chemin parcouru : [commenter les deux répartitions]. La bonne réponse est B — débrancher le réseau, JAMAIS éteindre : l'extinction détruit la RAM, donc les clés et les preuves. Le scan antivirus laisse l'attaquant connecté trois heures ; l'e-mail collectif alerte tout le monde... y compris, parfois, l'attaquant. Ce delta entre vos deux votes, c'est exactement ce que vous emportez ce soir. »

### 1:27–1:30 — Synthèse & consignes pour le Grand Atelier

**🎙️ Verbatim de synthèse :**
> « Trois réflexes à emporter : ISOLER, jamais éteindre ; PRÉSERVER — la RAM d'abord, le hachage comme preuve ; et PRÉPARER — le plan, le canal de secours, l'exercice : tout se gagne avant l'incident. La semaine prochaine : le Grand Atelier final. Vous serez les auditeurs de la PME MedDistri — TOUT ce que nous avons vu en 7 sessions y passera, et c'est vous qui voterez chaque décision. Relisez vos aide-mémoires : la direction de MedDistri compte sur vous. Un dernier mot dans le chat : ce que vous retenez de ce soir. »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Consignes A8 : relire les aide-mémoires A1-A7 + le [dossier MedDistri](../projet/A_capstone.md) (contexte de l'entreprise).
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Compresser le cas CHSF (1:16) à 60 secondes (c'est un rappel — les apprenants le connaissent).
2. Réduire la séquence légale (1:02–1:10) : donner les peines sans le débat chat « héros ou délinquant ».
3. Ne JAMAIS couper : la Timeline, la démo 7, le vote APRÈS (n°9) — c'est la mesure de la session.
4. Le **📊 Sondage n°10** (bonus réinstallation) est le tampon officiel : en autonomie si besoin.

**Si vous êtes en avance :**
1. Lancer le **📊 Sondage n°10** (pourquoi ne pas réinstaller immédiatement ?) — reboucle avec la Timeline.
2. Dérouler les **Questions de réflexion** du support (notamment la n°3 : le canal de crise — très concret).
3. Ouvrir une séquence questions/réponses libre sur l'atelier A8 à venir.

## Articulation avec l'atelier de fin de parcours
- Cette session fournit les concepts de réponse à incident nécessaires pour le scénario de crise de l'Atelier d'Audit Interactif de la session A08 (confinement, sauvegardes saines, décision de non-paiement, communication de crise).

## Self-paced APRÈS la séance (~120 min) & évaluation formative
- Revoir les supports des sessions A01 à A07 (aide-mémoires en priorité) pour se préparer au Grand Atelier d'Audit et au Quiz de Synthèse.
- Lire le contexte de l'entreprise MedDistri dans le dossier d'atelier (`A_capstone.md`).
- Quiz d'auto-évaluation en ligne (10 questions théoriques sur la réponse aux incidents et le cadre légal).
