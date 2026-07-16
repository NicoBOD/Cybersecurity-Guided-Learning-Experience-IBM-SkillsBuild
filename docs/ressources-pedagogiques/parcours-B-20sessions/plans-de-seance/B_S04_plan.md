# Plan de séance — Session B04 : Ingénierie sociale & facteur humain
Parcours : B 20 sessions  |  Module : A — Fondations  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (verbes d'action)
- **Décoder** les 5 principaux leviers psychologiques (autorité, urgence, sympathie, peur, preuve sociale) exploités par les attaquants.
- **Distinguer** les vecteurs d'ingénierie sociale : phishing, spear-phishing, smishing, vishing, baiting et fraude au président (BEC).
- **Structurer** des règles d'hygiène numérique simples et une procédure de vérification par canal indépendant.

## Prérequis & progression
- **Prérequis** : B01 à B03.
- **Lien de progression** : Cette session clôture le module A (Fondations) par le facteur humain — l'attaque qui contourne toute la technique. Elle ouvre le module B (Systèmes & réseaux) : à partir de B05, on étudie les protections techniques que l'ingénierie sociale cherche justement à contourner.

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama B04 ([spécifications](../slides/B_S04_slides_spec.md)) — l'e-mail de la « chasse aux indices » doit être lisible à l'écran.
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Temps médian pour tomber dans un phishing (DBIR 2024) ? | A) Moins d'une minute |
| 2 | 0:26 | Sondage | « L'avocat du PDG » : levier dominant ? | A) L'autorité |
| 3 | 0:30 | Sondage | Le SMS du colis à 1,95 € : levier dominant ? | B) L'urgence |
| 4 | 0:33 | Sondage | « Julien du support » : levier dominant ? | C) La sympathie / réciprocité |
| 5 | 0:58 | Sondage | Une procédure de contre-vérification chez vous ? | Opinion (pas de bonne réponse) |
| 6 | 1:17 | Sondage | Différence phishing / spear-phishing ? | A) Massif vs ciblé et personnalisé |
| 7 | 1:19 | Sondage | On vous demande votre code MFA au téléphone : que signifie cette demande ? | B) Fraude certaine |
| 8 | 1:21 | Sondage | Un collaborateur signale son erreur : réaction adaptée ? | B) Remercier et circonscrire |
| 9 | Tampon | Sondage | Facture fournisseur : quelle anomalie alerte en premier ? | B) Le domaine légèrement modifié |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil & retour sur Stuxnet (self-paced) | 💬 Chat : étapes repérées |
| 0:04–0:10 | Brise-glace : la victime tombe en 60 secondes | 📊 Sondage n°1 |
| 0:10–0:24 | Séquence 1 : Les 5 leviers psychologiques | 💬 Chat : « déjà reçu ? » |
| 0:24–0:36 | Activité : Décodez le levier | 📊 Sondages n°2, 3, 4 |
| 0:36–0:48 | Séquence 2 : Les canaux d'attaque + chasse aux indices | 💬 Chat : les indices du faux |
| 0:48–0:58 | Deux affaires réelles : Pathé & Arup | 💬 Chat : réactions |
| 0:58–1:03 | Et chez vous ? La procédure de contre-vérification | 📊 Sondage n°5 |
| 1:03–1:07 | Mini-scénario : le faux RIB fournisseur | 🤔 Chat : A, B ou C |
| 1:07–1:17 | Séquence 3 : Hygiène numérique & culture du signalement | Question rhétorique |
| 1:17–1:23 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:23–1:26 | Exercice bonus : l'anomalie qui alerte (tampon) | 📊 Sondage n°9 |
| 1:26–1:30 | Synthèse, clôture du module A & teaser B05 | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & retour sur le self-paced

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous ! Dernière session du module Fondations — et on garde le meilleur pour la fin : l'attaque qui ne vise ni vos machines, ni vos logiciels... mais vous. D'abord, la vidéo Stuxnet de la semaine : qui l'a vue ? Tapez dans le chat UNE étape de la Kill Chain que vous y avez reconnue. »

**Points à dérouler :**
- Lire 3-4 réponses (attendues : livraison par clé USB, exploitation de failles, propagation de ver).
- Rappel express de B03 : le zoo des malwares, la Kill Chain, « briser un maillon suffit ».
- Teaser tenu : « la semaine dernière, je vous ai promis l'histoire d'une entreprise de cinéma qui a perdu 19 millions d'euros sans un seul malware. C'est pour ce soir. »

**Transition scriptée :** « Commençons par un chiffre qui explique pourquoi ces attaques marchent si bien. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (60 secondes chrono)

**Consigne :** Lancer le **📊 Sondage n°1** — le temps médian entre l'ouverture d'un phishing et la saisie des identifiants. Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse A : moins d'une minute — environ 21 secondes pour cliquer, 28 de plus pour saisir ses identifiants, selon le rapport Verizon DBIR 2024. Voilà l'ennemi de ce soir : pas un super-logiciel, mais un scénario conçu pour vous faire agir AVANT de réfléchir. Notre objectif : installer le réflexe qui fait gagner LA minute qui déjoue presque tout. »

**Transition scriptée :** « Pour désamorcer une manipulation, il faut d'abord savoir la nommer. Voici la boîte à outils psychologique des attaquants. »

### 0:10–0:24 — Séquence 1 : Les 5 leviers psychologiques

**Points de contenu à dérouler (support §1) :**
- Définition : l'ingénierie sociale attaque la **décision humaine**, pas la machine — l'attaquant fabrique un contexte où la victime contourne elle-même les règles.
- **L'autorité** : le PDG, l'avocat, le policier — on obéit par réflexe hiérarchique (exemple : l'arnaque au président).
- **L'urgence** : le compte suspendu « dans 2 heures » — la panique temporelle court-circuite la vérification.
- **La sympathie / réciprocité** : le faux support qui « rend service » — la gentillesse endort la méfiance.
- **La peur / l'intimidation** : l'amende, les poursuites — la menace force l'action.
- **La preuve sociale** : « tous vos collègues l'ont déjà fait » — le troupeau rassure.
- Les leviers se **combinent** : autorité + urgence + secret = le cocktail du BEC (annonce des cas réels).
- Pour les curieux : ces leviers viennent de la psychologie sociale (principes d'influence de Robert Cialdini) — le marketing utilise les mêmes.
- Relance chat (0:20) : *« Lequel de ces leviers avez-vous déjà vu dans un message reçu ? Tapez son nom. »* — lire 3-4 réponses.

**Transition scriptée :** « Théorie terminée. Voyons si vous savez les reconnaître en situation : trois messages piégés, trois votes. »

### 0:24–0:36 — Activité : Décodez le levier (Sondages n°2 à 4)

**Consigne :** Afficher chaque message (support, activité « Décodez le levier »), le lire à voix haute **avec le ton** (pressant pour le n°2, anodin pour le n°3, chaleureux pour le n°4), puis lancer les **📊 Sondages n°2, 3, 4** (~4 min chacun : lecture, vote, débrief).

**🎙️ Verbatim de lancement :**
> « Je vous lis trois vrais scénarios d'attaque. Pour chacun, votez : quel est le levier psychologique DOMINANT ? Premier message — imaginez qu'il arrive un jeudi à 15h40 : "Maître Durand, avocat de votre PDG..." »

**Débriefs scriptés (points obligatoires) :**
- N°2 (l'avocat du PDG → autorité) : le trio du BEC — autorité + urgence + **injonction au secret**. Le secret est le signal d'alarme n°1 : une procédure légitime n'interdit jamais de vérifier.
- N°3 (le colis à 1,95 € → urgence) : le génie du piège est le montant dérisoire — qui se méfie pour 1,95 € ? Mais l'objectif n'est pas 1,95 € : c'est votre numéro de carte complet. Canal : smishing.
- N°4 (Julien du support → sympathie) : il « rend service »... et demande « le code qui s'affiche sur votre téléphone » — votre code MFA, celui qui valide la connexion qu'IL est en train de faire à votre place. Règle absolue : ce code ne se communique jamais, à personne.

**Transition scriptée :** « Vous savez maintenant décoder le POURQUOI ça marche. Passons au COMMENT ça arrive : les canaux. »

### 0:36–0:48 — Séquence 2 : Les canaux d'attaque

**Points de contenu à dérouler (support §2) :**
- **Phishing** : massif, impersonnel (banque, impôts, livraison) — la pêche au filet.
- **Spear-phishing** : ciblé, personnalisé grâce à l'**OSINT** (LinkedIn, site de l'entreprise) — la pêche au harpon.
- **Smishing** : le SMS (faux colis, fausse amende ANTAI) — l'écran de téléphone masque les indices.
- **Vishing** : la voix — extorsion de codes MFA, faux conseillers bancaires.
- **Baiting** : la clé USB « Salaires 2026 » sur le parking — la curiosité comme vecteur.
- **BEC / fraude au président** : l'aboutissement — usurpation ou compromission de la messagerie d'un dirigeant ou fournisseur pour ordonner des virements.

**Interaction (0:43) — 💬 La chasse aux indices :** afficher l'e-mail piégé du support (« Service Comptabilité — URGENT ») : *« Tapez dans le chat TOUS les indices qui trahissent le faux. »* Lire les réponses et compléter : domaine modifié (typosquatting), urgence artificielle, lien vers un domaine tiers, formulation impersonnelle, prétexte vague. Conclure : aucun indice ne demande de compétence technique — juste une minute d'attention.

**Transition scriptée :** « Ces mécanismes ont l'air simples ? Ils ont coûté 19 millions d'euros à Pathé et 25 millions de dollars à Arup. Deux histoires vraies. »

### 0:48–0:58 — Deux affaires réelles : Pathé & Arup

**Cas n°1 — Pathé, 2018 (5 min, support §4) :** raconter : les dirigeants de la filiale néerlandaise du groupe de cinéma français ; les e-mails « du siège parisien » évoquant une acquisition confidentielle à Dubaï ; un mois de virements successifs, plus de 19 millions d'euros ; aucun système piraté — uniquement autorité + urgence + secret ; les deux dirigeants licenciés. Leçon : le BEC ne cible pas les naïfs, il cible des cadres expérimentés avec un scénario cohérent ; un seul contre-appel au siège aurait tout arrêté.

**Cas n°2 — Arup, 2024 (5 min, support §4) :** raconter : l'employé de Hong Kong reçoit un e-mail suspect du « directeur financier » ; méfiant, il demande une visioconférence — bon réflexe ! — et l'obtient : à l'écran, le directeur financier et des collègues qu'il reconnaît ; rassuré, il exécute une quinzaine de virements, ~25 millions de dollars ; tout était **deepfake** — chaque visage, chaque voix, générés par IA à partir d'enregistrements publics. Leçon : il a vérifié... sur le canal que l'attaquant contrôlait. À l'ère des deepfakes, reconnaître un visage ne prouve plus rien — seule la vérification par un canal **indépendant** compte. Relance chat : *« Auriez-vous été piégé ? Honnêtement. »*

**Transition scriptée :** « La question qui fâche, maintenant : et chez vous ? »

### 0:58–1:03 — Sondage n°5 : la procédure de contre-vérification

**Consigne :** Lancer le **📊 Sondage n°5** (opinion) — existe-t-il chez vous une procédure formalisée de contre-vérification des virements et changements de RIB ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Pas de bonne réponse — un diagnostic. Pathé et Arup prouvent que la vigilance individuelle ne suffit pas face à un scénario professionnel : il faut une PROCÉDURE qui tienne même quand l'humain est convaincu — double validation au-dessus d'un seuil, contre-appel obligatoire sur un numéro connu, aucun changement de RIB traité sans vérification. Si vous avez répondu B ou C, vous savez quoi proposer lundi matin. »

### 1:03–1:07 — 🤔 Mini-scénario : le faux RIB fournisseur

**Consigne :** Afficher le mini-scénario du support : l'e-mail du fournisseur habituel avec un « nouveau RIB » — vraie adresse, vraie facture. *« Tapez A, B ou C dans le chat. »*

**Débrief :** B — rappeler le fournisseur au numéro **habituel**. A tombe dans le piège : une boîte compromise envoie de vrais e-mails avec un faux RIB. C est le piège subtil : si la boîte est compromise, c'est l'attaquant qui répondra « tout est bon ». C'est l'arnaque au faux RIB, l'une des fraudes les plus courantes contre les PME françaises.

**Transition scriptée :** « Dernière brique : les réflexes du quotidien qui rendent tout cela beaucoup plus difficile. »

### 1:07–1:17 — Séquence 3 : Hygiène numérique & culture du signalement

**Points de contenu à dérouler (support §5) :**
- **Mots de passe** : longs (12-15+), uniques, dans un gestionnaire.
- **MFA partout** : la mesure qui bloque plus de 99,9 % des attaques automatisées (Microsoft, 2019) — et sa règle d'or : le code ne se communique jamais (rappel du sondage n°4).
- **La vérification hors canal** : LE réflexe de la session — raccrocher, rappeler un numéro connu.
- **La culture du signalement** : question rhétorique — *« que préférez-vous : une victime qui signale en 5 minutes, ou un "bon élève" qui se tait 3 jours ? »* Punir la victime garantit que la prochaine se taira.
- Présenter la **Boîte à outils** du support : le kit d'onboarding « 5 réflexes » (EcoLog) — annoncer l'exercice de la semaine : l'adapter à sa propre organisation.

**Transition scriptée :** « Vérifions que les réflexes sont en place : trois questions, trois votes. »

### 1:17–1:23 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : massif vs ciblé ; fraude certaine (le code MFA valide une opération en cours) ; remercier et circonscrire. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/B_S04_support.md).

### 1:23–1:26 — Exercice bonus (Sondage n°9) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°9** — la facture du fournisseur habituel : quelle anomalie alerte en premier ? Débrief : le domaine légèrement modifié (`st0rmshield.fr` — un zéro à la place du « o ») : le typosquatting, même mécanisme que la chasse aux indices. Ni le montant ni l'heure ne sont des indices fiables. À couper en cas de retard.

### 1:26–1:30 — Synthèse & clôture du module A

**🎙️ Verbatim de synthèse :**
> « Ce soir : cinq leviers psychologiques que vous savez désormais nommer, six canaux d'attaque, deux affaires à plusieurs dizaines de millions — et UN réflexe qui les déjoue presque toutes : vérifier par un canal indépendant. Et avec cette session se termine le module Fondations : vous savez ce qu'on protège (B01), qui attaque (B02), comment (B03) et par où passe le maillon humain (B04). Avant de partir : un mot que vous retenez, dans le chat ! »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Self-paced : module IBM SkillsBuild *"Introduction to Cybersecurity Tools & Cyber Attacks - Social Engineering"* (~1h) + adapter le kit « 5 réflexes » à son organisation + préparation réseau (IP, IPv4 vs IPv6).
- Teaser B05 : « la semaine prochaine, changement de décor : on passe côté technique avec le module Systèmes & réseaux. Vous découvrirez comment vos données voyagent sur Internet — et à quel point il est facile de les lire au passage quand rien n'est chiffré. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**Exercice bonus n°9** (1:23–1:26) — il est dans le support en exercice bonus.
2. Compresser la « chasse aux indices » à 3 min (3 indices lus).
3. Présenter le kit « 5 réflexes » en 1 min (renvoi au support pour le détail).
4. Ne JAMAIS couper : l'activité « Décodez le levier », les deux affaires réelles, le quiz.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°3 : pourquoi la vérification d'Arup a échoué).
2. Approfondir l'OSINT : que trouve-t-on sur une entreprise via LinkedIn et son site web ? (teaser du travail autonome).
3. Questions/réponses libres.

## Travail en autonomie (Self-paced)
* **Avant la session suivante (B05)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Introduction to Cybersecurity Tools & Cyber Attacks - Social Engineering"* (~1h00).
  * **Exercice d'application** : Adapter le kit d'onboarding « 5 réflexes de sécurité » du support à votre propre organisation (ou à une PME fictive).
  * **Préparation Module Réseau** : Identifier le fonctionnement théorique de l'adresse IP et la différence entre IPv4 et IPv6 (ressource vidéo optionnelle fournie).
