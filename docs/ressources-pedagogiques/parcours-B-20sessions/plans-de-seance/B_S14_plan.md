# Plan de séance — Session B14 : Gestion des risques
Parcours : B 20 sessions  |  Module : D — Gouvernance, risques & conformité  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (verbes d'action)
- **Articuler** les composantes d'un risque cyber : actif, menace, vulnérabilité, impact, vraisemblance.
- **Coter** un risque dans une matrice qualitative 4x4 (criticité brute puis résiduelle) au sein d'un registre des risques.
- **Choisir et justifier** une stratégie de traitement parmi les 4 options : réduire, transférer, éviter, accepter (par écrit).

## Prérequis & progression
- **Prérequis** : B13 (gouvernance — le RSSI conseille, la Direction décide).
- **Lien de progression** : Cette session fournit la méthode d'arbitrage qui alimente la conformité (B15) et l'**Atelier de Synthèse 3** (cotation des risques de MedDistri, la semaine prochaine).

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama B14 ([spécifications](../slides/B_S14_slides_spec.md)) — la ligne de registre vide doit pouvoir être remplie à l'écran pendant l'activité.
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Un assureur peut-il invoquer un « acte de guerre » pour une cyberattaque ? | A) Oui, c'est déjà arrivé |
| 2 | 0:46 | Sondage | Cotation brute (V=4, G=3) : quelle criticité ? | B) 12/16 — critique |
| 3 | 0:50 | Sondage | Charte + blocage + IA interne : quelle stratégie ? | C) Réduire / Atténuer |
| 4 | 0:54 | Sondage | Cotation résiduelle (V=1, G=3) — et pourquoi G ne bouge pas ? | A) 3/16 : on réduit la probabilité, pas les conséquences |
| 5 | 1:08 | Sondage | Votre organisation a-t-elle une assurance cyber ? | Opinion (pas de bonne réponse) |
| 6 | 1:16 | Sondage | Pourquoi le résiduel n'est-il jamais nul ? | B) La sécurité parfaite n'existe pas |
| 7 | 1:18 | Sondage | Que transfère une cyber-assurance ? | C) L'impact financier, dans les limites du contrat |
| 8 | 1:20 | Sondage | La formulation correcte d'un risque ? | B) Menace × vulnérabilité × actif → impact |
| 9 | Tampon | Sondage | Groupe électrogène à 50 k€ pour une perte de 5 k€ ? | B) Accepter (ou assurer) |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil & retour sur le risque non-IT observé | 💬 Chat : exemples du quotidien |
| 0:04–0:10 | Brise-glace : l'assureur et l'« acte de guerre » | 📊 Sondage n°1 |
| 0:10–0:24 | Séquence 1 : L'équation du risque | 💬 Chat : perception du risque |
| 0:24–0:34 | Séquence 2 : Le registre & la matrice 4x4 | 💬 Chat : cotation express |
| 0:34–0:44 | Séquence 3 : Les 4 traitements | Question rhétorique |
| 0:44–0:58 | Activité : La ligne de registre (IA générative chez EcoLog) | 📊 Sondages n°2, 3, 4 |
| 0:58–1:08 | Chiffres clés & affaires Mondelez + Merck | 💬 Chat : réactions |
| 1:08–1:12 | Et chez vous ? L'assurance cyber | 📊 Sondage n°5 |
| 1:12–1:16 | Mini-scénario : l'acceptation orale du DG | 🤔 Chat : A, B ou C |
| 1:16–1:22 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:22–1:26 | Exercice bonus : le groupe électrogène (tampon) | 📊 Sondage n°9 |
| 1:26–1:30 | Synthèse, devoirs & teaser B15 | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & retour sur le self-paced

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous ! Votre mission de la semaine : observer un risque NON informatique de votre quotidien professionnel. Tapez-le dans le chat — retard fournisseur, panne, accident... »

**Points à dérouler :**
- Lire 3-4 exemples du chat : « remarquez : pour chacun, quelqu'un a déjà décidé — consciemment ou non — de le réduire, l'assurer, l'éviter ou le subir. Ce soir, on applique la même logique au cyber, mais MÉTHODIQUEMENT. »
- Rappel express de B13 : la PSSI signée, les référentiels, le RSSI qui conseille et la Direction qui assume — et l'enquête charte (« qui a posé les trois questions ? »).
- Annonce du programme : l'équation du risque, la matrice, les 4 traitements — et deux procès d'assurance à un milliard.

**Transition scriptée :** « Et justement, première question : l'assurance. Accrochez-vous. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (l'« acte de guerre »)

**Consigne :** Lancer le **📊 Sondage n°1** — un assureur peut-il refuser d'indemniser une cyberattaque au titre d'un « acte de guerre » ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse A : c'est déjà arrivé — après NotPetya, l'attaque de 2017 que vous connaissez depuis B03, attribuée à un sabotage étatique. Des assureurs ont invoqué l'exclusion de guerre de leurs contrats : 100 millions en jeu pour Mondelez, 1,4 MILLIARD pour Merck. Les deux affaires arrivent en seconde partie. Moralité d'ouverture : "transférer" un risque ne le fait pas disparaître — encore faut-il lire la police. Ce soir, vous apprenez le métier d'arbitre des risques. »

**Transition scriptée :** « Tout commence par savoir dire ce qu'EST un risque — avec une grammaire précise. »

### 0:10–0:24 — Séquence 1 : L'équation du risque

**Points de contenu à dérouler (support §1) :**
- Relance chat d'entrée (2 min) : *« Rouler sans ceinture, stocker le code de sa carte dans son téléphone : pourquoi certains le font-ils ? »* — la perception du risque est subjective et biaisée ; la méthode existe pour corriger ces biais.
- **Les 5 composantes** : l'actif (ce qui a de la valeur), la menace (l'événement redouté — B02), la vulnérabilité (la faiblesse — B03-B08), l'impact (la conséquence business — B01), la vraisemblance.
- **La grammaire du risque** (admonition du support) : « la MENACE exploite la VULNÉRABILITÉ pour atteindre l'ACTIF et causer un IMPACT » — faire reformuler un exemple par le chat.
- Insister : « le pare-feu est vieux » n'est PAS un risque (c'est une vulnérabilité) — il manque le scénario et la conséquence. C'est la question n°8 du quiz.

**Transition scriptée :** « On sait nommer. Maintenant, on mesure — avec seize cases. »

### 0:24–0:34 — Séquence 2 : Le registre & la matrice 4x4

**Points de contenu à dérouler (support §2) :**
- **Le registre des risques** : le document qui centralise, cote et suit — la mémoire de l'arbitrage.
- **La matrice** : Vraisemblance (1-4) × Gravité (1-4) = criticité 1 à 16 ; les trois zones (faible 1-4, moyen 5-8, critique 9-16).
- La cotation est **qualitative et collégiale** : sa valeur vient de la discussion qu'elle force et de la priorisation qu'elle produit — on traite le 12 avant le 4.
- Relance chat (0:31) : *« Cotez : "incendie du local serveur" — V ? G ? »* — lire 3-4 cotations, souligner les écarts : « vos désaccords sont exactement la discussion qu'une entreprise doit avoir. »

**Transition scriptée :** « Un risque coté appelle une décision. Il n'en existe que quatre. »

### 0:34–0:44 — Séquence 3 : Les 4 traitements

**Points de contenu à dérouler (support §3) :**
- Dérouler l'**analogie de l'alpinisme** : réduire (casque, corde, guide), transférer (l'assurance hélicoptère — en vérifiant l'altitude couverte !), éviter (renoncer au sommet), accepter (y aller en le disant à voix haute... par écrit).
- **Réduire** : abaisser la vraisemblance (EDR, MFA) ou l'impact (sauvegardes 3-2-1) — la stratégie par défaut.
- **Transférer** : l'assurance (financier) ou l'externalisation (opérationnel — avec la responsabilité partagée de B11 en tête) ; la limite : on transfère des euros, pas la réputation ni les données.
- **Éviter** : renoncer — parfois la meilleure décision (l'application douteuse, le projet trop exposé).
- **Accepter** : légitime, MAIS formalisé, signé par la Direction, daté et réexaminé (rappel B13 : un risque non arbitré est un risque accepté par accident).
- Question rhétorique : *« Quelle stratégie choisit-on le plus souvent... sans s'en rendre compte ? »* — accepter, par silence. D'où le registre.

**Transition scriptée :** « À vous d'arbitrer : un cas 100 % actuel — l'IA générative sauvage chez EcoLog. »

### 0:44–0:58 — Activité : La ligne de registre (Sondages n°2 à 4)

**Consigne :** Afficher le contexte (support, activité « La ligne de registre ») : le marketing d'EcoLog soumet contrats et données clients à des IA publiques gratuites, sans validation DSI. Lancer les **📊 Sondages n°2, 3, 4** (~4-5 min chacun : énoncé, vote, débrief), puis afficher la ligne de registre complète.

**🎙️ Verbatim de lancement :**
> « Du Shadow IT au goût du jour : vos collègues du marketing collent les contrats clients dans une IA gratuite en ligne. Construisons la ligne de registre de ce risque, étape par étape. D'abord : l'usage est quotidien — vraisemblance 4 ; une fuite serait majeure — gravité 3. Criticité brute ? »

**Débriefs scriptés (points obligatoires) :**
- N°2 : on **multiplie** — 12/16, zone critique, traitement immédiat. (L'addition écraserait les écarts.)
- N°3 : la nuance — on n'a pas renoncé à l'IA (Éviter) : on garde l'usage en abaissant la vraisemblance par trois leviers — technique (blocage), organisationnel (charte), alternative sécurisée (sinon contournement, rappel B08). C'est Réduire.
- N°4 : la leçon la plus fine — le résiduel n'est jamais nul, et ici les mesures n'agissent que sur la vraisemblance : SI la fuite survient, l'impact légal reste entier. Abaisser la gravité demanderait d'autres leviers (minimiser les données, pseudonymiser — teaser B15).
- **Afficher la ligne complète** (support) : « une ligne de registre professionnelle — exactement l'exercice de l'Atelier de Synthèse 3, la semaine prochaine, sur MedDistri. »

**Transition scriptée :** « Vous savez coter et traiter. Voyons ce qui arrive quand le traitement choisi... ne tient pas ses promesses. »

### 0:58–1:08 — Chiffres clés & deux affaires réelles

**Chiffres (2 min, support §4) :** ~100 M$ en jeu pour Mondelez (litige 2018, accord confidentiel 2022) ; 1,4 Md$ pour Merck — la justice donne raison à l'assuré (2023), accord final en 2024 ; 2023 : le marché (Lloyd's) réécrit ses clauses d'exclusion.

**Cas n°1 — Mondelez vs Zurich (4 min, support §5) :** raconter : NotPetya ravage Mondelez (serveurs détruits, logistique paralysée, ~100 M$ déclarés) ; l'assureur refuse — exclusion des « actes de guerre », l'attaque venant d'être attribuée à un État ; quatre ans de procédure, accord confidentiel. Leçons : le contrat a des exclusions ; l'attribution géopolitique (B02) peut se retourner contre la victime ; l'incertitude juridique est elle-même un risque.

**Cas n°2 — Merck (4 min, support §5) :** même attaque, même clause, autre issue : 1,4 Md$ réclamés, et les tribunaux donnent **raison à Merck** — une clause écrite pour des conflits armés ne s'applique pas telle quelle à une cyberattaque touchant des civils ; accord définitif en 2024 ; et le marché réécrit ses exclusions (Lloyd's, 2023). Leçons : le langage contractuel du monde physique s'applique mal au cyber ; faire relire ses clauses par un juriste coûte quelques milliers d'euros — contre 1,4 milliard d'incertitude. Relance chat : *« Quel détail vous marque le plus ? »*

### 1:08–1:12 — Sondage n°5 : et chez vous, l'assurance ?

**Consigne :** Lancer le **📊 Sondage n°5** (opinion) — votre organisation a-t-elle une assurance cyber ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Selon les baromètres du secteur (AMRAE), l'assurance cyber reste concentrée sur les grandes entreprises — dans les PME, "non ou je ne sais pas" domine. Deux messages : l'assurance exige désormais un socle de sécurité à la souscription — MFA, sauvegardes, EDR : le questionnaire ressemble à notre parcours ! Et si vous avez répondu B — "oui mais je ne sais pas ce qu'elle couvre" — la question de lundi s'impose : que couvre notre police... et qu'exclut-elle ? Mondelez l'a découvert après le sinistre. »

### 1:12–1:16 — 🤔 Mini-scénario : l'acceptation orale

**Consigne :** Afficher le mini-scénario du support : le DG tranche à l'oral — « trop cher, on prend le risque, point suivant ». *« Tapez A, B ou C dans le chat. »*

**Débrief :** B — accepter est une stratégie légitime, mais c'est une décision de gouvernance : fiche d'acceptation, cotation, motivation, signature, date de réexamen (rappel B13 : ce qui n'est pas écrit n'existe pas). A laisse le RSSI porter de fait une décision qui n'est pas la sienne ; C est une faute professionnelle. La formule : l'acceptation orale n'engage que celui qui l'écoute.

**Transition scriptée :** « Trois questions pour ancrer la méthode. »

### 1:16–1:22 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : la sécurité parfaite n'existe pas ; l'assurance transfère l'impact financier (dans les limites du contrat) ; la grammaire menace-vulnérabilité-actif-impact. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/B_S14_support.md).

### 1:22–1:26 — Exercice bonus (Sondage n°9) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°9** — 50 k€ de groupe électrogène pour 5 k€ de perte potentielle ? Débrief : accepter ou assurer (B) — la sécurité se proportionne aux enjeux ; dépenser 10 fois la perte est une mauvaise gestion. Et l'acceptation se formalise par écrit. À couper en cas de retard.

### 1:26–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Ce soir, vous avez appris le métier d'arbitre : une grammaire — menace, vulnérabilité, actif, impact ; une mesure — seize cases ; quatre décisions — réduire, transférer, éviter, accepter... par écrit. Et deux procès à un milliard pour retenir qu'un transfert mal lu est une acceptation déguisée. Un mot que vous retenez, dans le chat ! »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Self-paced : cours IBM SkillsBuild *"Cybersecurity Governance and Risk Management - Part 2"* (~1h30) + relire ses notes B13-B14 (PSSI, matrice) — **préparation directe de l'Atelier de Synthèse 3** + repérer les mentions RGPD/cookies sur deux sites web visités cette semaine.
- Teaser B15 : « la semaine prochaine : la conformité — RGPD, CNIL, et l'Atelier de Synthèse 3 où VOUS coterez les risques de MedDistri. Avec des amendes bien réelles : 50 millions pour Google, 1,2 milliard pour Meta. La loi a des dents. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**Exercice bonus n°9** (1:22–1:26) — il est dans le support en exercice bonus.
2. Compresser la relance « perception du risque » (séquence 1) à 1 min.
3. Compresser le cas Merck à 2 min (l'essentiel : même clause, issue inverse, le marché réécrit ses contrats).
4. Ne JAMAIS couper : l'activité ligne de registre, le cas Mondelez, le quiz.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°3 : que vérifier avant de signer une police cyber).
2. Faire coter par sondage improvisé un deuxième risque proposé par le chat (ex. vol du portable d'un commercial).
3. Questions/réponses libres.

## Travail en autonomie (Self-paced)
* **Avant la session suivante (B15)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Cybersecurity Governance and Risk Management - Part 2"* (durée estimée : 1h30).
  * **Préparation de l'Atelier de Synthèse 3** : Relire ses notes B13 (PSSI) et B14 (matrice, traitements) — l'atelier de B15 cotera les risques de MedDistri.
  * **Observation** : Repérer les mentions RGPD et bandeaux cookies sur deux sites web visités cette semaine — que vous demande-t-on d'accepter ?
