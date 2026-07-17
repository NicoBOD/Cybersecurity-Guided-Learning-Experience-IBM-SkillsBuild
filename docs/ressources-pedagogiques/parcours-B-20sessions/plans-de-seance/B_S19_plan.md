# Plan de séance — Session B19
Parcours : B 20 sessions  |  Module : E — Opérations, détection & réponse  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## 1. Métadonnées de la session
* **Titre** : Simulation de crise cyber (Tabletop exercise) — « la crise GigaVolt », en direct et par sondages
* **Objectifs pédagogiques opérationnels** :
  * Expliquer le fonctionnement d'un exercice de crise sur table (maître du jeu, injects, RETEX).
  * Prendre collectivement des décisions de crise opérationnelles, juridiques et de communication sous contrainte de temps (simulation GigaVolt, décisions par sondages).
  * Construire un communiqué de crise externe factuel et conforme (RGPD), et formuler un RETEX exploitable.
* **Prérequis** : B15 (RGPD, 72 h), B18 (cycle de réponse, fiche réflexe). Rappels mobilisés : B02 (LOPMI, double extorsion), B12 (sauvegardes, PCA/PRA), B14 (assurance).
* **Lien de progression** : B18 a donné la méthode ; B19 la met sous pression en conditions simulées. Dernière répétition générale avant le Grand Atelier d'Audit de B20, qui clôt le parcours.
* **Spécificité d'animation** : session-exercice — les deux tiers du temps sont pilotés par le scénario. Le mentor joue le maître du jeu ET tous les personnages (l'astreinte, le dirigeant, le journaliste). L'audience est LA cellule de crise : chaque décision passe par un vote ou par le chat.

## 2. Checklist technique Livestorm (avant la session)

- [ ] Les **9 sondages** sont pré-créés dans Livestorm, dans l'ordre du tableau ci-dessous.
- [ ] Le partage d'écran est testé avec le diaporama B19 ([spécifications](../slides/B_S19_slides_spec.md)) — les slides d'injects horodatés doivent s'enchaîner sans latence (elles portent la dramaturgie).
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures propositions pendant le communiqué collectif.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute — la pression temporelle fait partie de l'exercice).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
| :-- | :-- | :-- | :-- | :-- |
| 1 | 0:04 | Brise-glace | Économie moyenne avec équipe + plan testé (IBM 2022) ? | C — ~2,66 M$ |
| 2 | ~0:33 | Tabletop | Décision 1 : première action à 8h00 ? | B — Confiner sans éteindre + activer la cellule |
| 3 | ~0:39 | Tabletop | Décision 2 : qui prévenir dans l'heure ? | B — Cellule complète + assureur + prestataire |
| 4 | ~0:47 | Tabletop | Décision 3 : payer la rançon ? | B — Non : plainte 72 h, CNIL, restauration |
| 5 | 1:08 | Opinion | Votre organisation paierait-elle, sous pression réelle ? | — (pas de bonne réponse) |
| 6 | 1:16 | Quiz | Qu'est-ce qu'un « inject » ? | B |
| 7 | 1:18 | Quiz | Ordre de remise en service ? | B — Éradiquer puis restaurer |
| 8 | 1:20 | Quiz | Qui s'exprime publiquement ? | C — Porte-parole unique |
| 9 | 1:21 | Bonus | Pourquoi ne pas réinstaller immédiatement ? | B — Préserver les traces |

## 3. Vue d'ensemble du déroulé

| Créneau | Séquence | Interactions |
| :-- | :-- | :-- |
| 0:00–0:04 | Accueil & réinvestissement du devoir (votre cellule de crise) | Chat |
| 0:04–0:09 | Brise-glace : 2,66 M$ | 📊 Sondage n°1 |
| 0:09–0:19 | Théorie éclair : tabletop, cellule de crise, communication | — |
| 0:19–0:27 | Affaires réelles : Norsk Hydro & Maersk revisité | — |
| 0:27–0:32 | **🧪 Tabletop — mise en situation & inject 1 (7h55)** | — |
| 0:32–0:44 | Décisions 1 & 2 : confiner, alerter | 📊 Sondages n°2, 3 |
| 0:44–0:56 | Inject 2 (10h30) : la rançon — décision 3 | 📊 Sondage n°4 |
| 0:56–1:08 | Inject 3 (14h00) : le journaliste + le communiqué collectif | 🤔 Chat A/B/C + 💬 chat |
| 1:08–1:12 | La vraie question : paieriez-vous ? (opinion) | 📊 Sondage n°5 |
| 1:12–1:16 | RETEX à chaud | 💬 Chat |
| 1:16–1:21 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:21–1:25 | Exercice bonus : préserver les traces (tampon) | 📊 Sondage n°9 |
| 1:25–1:30 | Synthèse, devoirs & teaser B20 | Chat : « un mot retenu » |

## 4. Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & réinvestissement du devoir

**🎙️ Verbatim d'ouverture :**
> « Bonsoir à toutes et à tous ! Ce soir, pas de cours — un exercice. Dans vingt minutes, vous serez la cellule de crise d'une PME attaquée, et chaque décision passera par vos votes. Vous aviez une liste à préparer : les 4-5 fonctions de votre cellule de crise. **Dans le chat : votre liste !** »

**Points de contenu :**
- Récolter, regrouper au tableau : Direction, IT/Sécurité, Juridique/DPO, Communication (+ variantes : RH, métier, assureur).
- 🎙️ « Retenez surtout ce que votre liste dit en creux : l'informatique n'y est PAS seule. Une crise cyber est un problème d'entreprise à déclencheur informatique. »

**Transition :** « Avant l'exercice, une question d'argent. »

### 0:04–0:09 — 📊 Sondage n°1 (brise-glace) : le prix de la préparation

Lancer le sondage n°1 (IBM 2022 : économie avec équipe + plan testé). Laisser voter ~60 secondes.

**🎙️ Débrief scripté :**
> « Réponse C : 2,66 millions de dollars d'écart moyen (IBM, *Cost of a Data Breach* 2022) entre ceux qui ont une équipe ET un plan testé, et ceux qui n'ont rien. Le mot-clé, c'est TESTÉ : un plan jamais exercé est une hypothèse. Sous stress, on ne s'élève pas au niveau de ses ambitions — on retombe au niveau de son entraînement. Alors entraînons-nous. »

**Transition :** « Trois notions éclair, et on entre en crise. »

### 0:09–0:19 — Théorie éclair : tabletop, cellule, communication

**Points de contenu (support §1-3) :**
- **Le tabletop** : simulation théorique, zéro impact production ; le maître du jeu introduit des **injects** ; un bon exercice DOIT révéler des failles.
- **La cellule de crise** — qui décide de quoi : la Direction décide et assume (B13), l'IT éclaire (diagnostic, délais), le juridique/DPO qualifie (CNIL 72 h — B15, plainte LOPMI 72 h — B02, assureur — B14), la communication cadre (interne et externe).
- **Les 4 règles d'or de la communication** : les faits, une voix (porte-parole unique), l'empathie, la transparence contrôlée.
- 🎙️ « Gardez ces quatre règles en tête : dans une heure, un journaliste va vous appeler. »

**Transition :** « Deux entreprises réelles ont vécu ce que vous allez vivre. L'une est devenue un cas d'école. »

### 0:19–0:27 — Affaires réelles : Norsk Hydro & Maersk revisité

**Points de contenu (support §5) :**
- **Norsk Hydro (2019)** : LockerGoga à 4h du matin ; trois décisions en heures — isoler massivement (22 000 postes hors ligne), refuser de payer sans négocier, transparence totale (points presse quotidiens, dirigeants face caméra) ; usines en mode manuel (les classeurs papier ressortent) ; ~70 M$ (chiffres de l'entreprise, 2019) — et une réputation SORTIE RENFORCÉE de la crise.
- **Maersk (2017, revisité — l'attaque NotPetya elle-même a été vue en B03)** : côté cellule de crise — 10 jours de reconstruction (~4 000 serveurs, 45 000 postes), ~300 M$ déclarés, sauvé par une copie d'annuaire survivante au Ghana ; ~80 % d'activité maintenue en mode dégradé improvisé. Leçon : l'improvisation héroïque a marché UNE fois — la préparation coûte moins cher que la chance.
- 🎙️ « Hydro a pu déconnecter, refuser, parler — parce que rien ne s'improvisait ce matin-là. Voyons ce que VOUS improviserez. »

**Transition :** « Fermez vos notes. Lundi matin, 7h55. Votre téléphone sonne. »

### 0:27–0:32 — 🧪 Tabletop : mise en situation & inject 1

**🎙️ Verbatim maître du jeu (ton de jeu assumé) :**
> « Vous êtes la cellule de crise de GigaVolt : PME française, 120 salariés, distribution de matériel électrique. Lundi, 7h55. L'astreinte appelle : *"l'Active Directory ne répond plus. Des fichiers changent d'extension en `.lokd`. Il y a un écran de rançon sur les serveurs."* Il est 8h00. La logistique démarre à 8h30. Vos entrepôts ne peuvent plus imprimer un seul bon de livraison. À vous. »

**Points d'animation :**
- Laisser 20 secondes de silence — le stress fait partie de l'exercice.
- Rappeler le fonctionnement : « chaque décision = un vote ; vos arguments = le chat. »

### 0:32–0:44 — 📊 Décisions 1 & 2 (sondages n°2 et n°3)

1. **📊 n°2 — Décision 1 (0:32–0:38)** : première action ? → **B — confiner sans éteindre + activer la cellule**. Débrief : redémarrer (A) détruit la RAM et peut aggraver (B18) ; « contacter les attaquants » (C) n'est pas une première heure. Le confinement d'abord : segments isolés, accès distants coupés, machines allumées. Et l'activation de la cellule est une ACTION, pas une formalité : sans elle, chaque décision suivante prendra une heure de plus.
2. **📊 n°3 — Décision 2 (0:38–0:44)** : qui prévenir dans l'heure ? → **B — cellule complète + assureur + prestataire de réponse**. Débrief : l'IT seule (A) = les décisions juridiques et de communication ne seront pas prises à temps ; tous les clients immédiatement (C) = communiquer avant de savoir, la panique organisée. Question piège à poser au chat : « la messagerie est chiffrée — vous les prévenez COMMENT ? » → la communication **hors bande** (annuaire de crise imprimé, téléphones personnels, messagerie externe convenue) — qui se prépare AVANT.

### 0:44–0:56 — 🕙 Inject 2 : la rançon (sondage n°4)

**🎙️ Verbatim maître du jeu :**
> « 10h30. Un e-mail arrive sur la boîte PERSONNELLE de votre dirigeant : *"500 000 €, ou nous publions vos fichiers clients. Vous avez 48 heures."* Double extorsion — ils ont volé avant de chiffrer (souvenez-vous de B02). Précision de votre RSSI : les sauvegardes de la veille sont saines et hors ligne. Décision. »

**📊 n°4 + débrief (10 min) :** → **B — ne pas payer : plainte (LOPMI 72 h), notification CNIL préparée (72 h), restauration après éradication.**
- A (« payer discrètement ») : payer ne garantit ni le déchiffrement ni la non-publication, finance l'écosystème, signale un payeur — et Colonial Pipeline (B08) a payé pour un déchiffreur si lent qu'il a restauré sur sauvegardes quand même. « Discrètement », en plus : la fuite est déjà réelle, la CNIL devra être notifiée.
- C (« ignorer sans plainte ni notification ») : la pire — sans plainte sous 72 h, l'indemnisation assurantielle saute (LOPMI 2023) ; sans notification CNIL sous 72 h, l'amende s'ajoute à l'attaque (B15).
- Point mentor si le débat s'installe : négocier pour gagner du temps d'investigation n'est pas payer ; la position rançon se décide À FROID, avec juridique et assureur — pas à 10h30 un lundi de crise.

### 0:56–1:08 — 🕑 Inject 3 : le journaliste & le communiqué collectif

**🎙️ Verbatim maître du jeu :**
> « 14h00. Le standard transfère un appel : un journaliste. Il a trouvé des données GigaVolt sur un forum. Pendant qu'il parle, votre responsable comm vous tend son téléphone : un salarié vient de tweeter *"grosse panique au boulot, on est piratés !"*. Le journaliste attend. Que lui répondez-vous ? »

1. **🤔 Mini-scénario (chat A/B/C, 0:56–1:00)** : → **B — reconnaître factuellement, annoncer un communiqué, renvoyer au porte-parole unique**. Débrief : nier (A) alors qu'il A les données = le mensonge devient l'histoire ; tout détailler (C) = spéculation + informations exploitables. Et le tweet : la consigne interne de silence externe se donne à la première heure, pas après le premier tweet.
2. **💬 Le communiqué collectif (1:00–1:08)** : « construisons le squelette ensemble — proposez dans le chat : que met-on en premier ? » Assembler en direct les 6 blocs : reconnaissance factuelle → mesures engagées → ce qui est touché ET ce qui ne l'est pas → CNIL + information des clients → regrets et engagement → contact presse unique. Afficher ensuite le communiqué modèle du support et comparer. 🎙️ « Remarquez le bloc 3 : dire ce qui n'a PAS été volé est aussi important que d'admettre ce qui l'a été. »

### 1:08–1:12 — 📊 Sondage n°5 (opinion) : la vraie question

Lancer le sondage n°5 (votre organisation paierait-elle ?). Annoncer qu'il n'y a pas de bonne réponse.

**🎙️ Débrief scripté :**
> « Ceux qui ont répondu C — "aucune idée" — ont peut-être donné la réponse la plus utile : si vous ne savez pas ce que votre organisation déciderait, c'est que la décision n'a jamais été préparée, et elle se prendra donc dans la panique. Dans la réalité, beaucoup d'organisations paient — les rapports du secteur le confirment année après année. C'est exactement pourquoi la position se fixe à froid, en exercice, avec le juridique et l'assureur. Comme vous venez de le faire. »

### 1:12–1:16 — 💬 RETEX à chaud

**🎙️ Verbatim :**
> « L'exercice est terminé — place au retour d'expérience, comme après une vraie crise. Dans le chat, deux choses : la décision qui vous a semblé la plus DIFFICILE, et une chose que GigaVolt aurait dû préparer À L'AVANCE. »

**Points d'animation :** récolter et regrouper (annuaire de crise, canaux hors bande, position rançon écrite, sauvegardes testées, porte-parole désigné, numéros de l'assureur et du prestataire). Conclure : « cette liste EST un plan d'action RETEX — c'est le livrable d'un vrai exercice, et vous venez de le produire. »

### 1:16–1:21 — 📊 Quiz de validation (sondages n°6, 7, 8)

Enchaîner les trois sondages, débrief de 30 secondes chacun (éléments dans le support) :
- N°6 → B : l'inject, l'outil du maître du jeu — chaque inject teste UNE capacité.
- N°7 → B : éradiquer puis restaurer — sinon on restaure dans un environnement piégé (B18).
- N°8 → C : une voix, des faits — le silence total nourrit les rumeurs, la cacophonie fabrique des contradictions.

### 1:21–1:25 — 📊 Sondage n°9 (bonus tampon) : préserver les traces

Lancer si le temps le permet (sinon : « à faire en autonomie, il est dans le support »).

**🎙️ Débrief scripté :**
> « B : réinstaller, c'est effacer la scène de crime — sans investigation, vous ignorez comment il est entré, ce qu'il a pris, et s'il a laissé une porte dérobée. L'attaque recommence le lendemain de la réinstallation. D'abord isoler, préserver, investiguer — réinstaller vient après. »

### 1:25–1:30 — Synthèse, devoirs & teaser B20

**Points de clôture :**
- 🎙️ « Ce que vous avez fait ce soir : confiner sans détruire, alerter les bonnes personnes par les bons canaux, refuser sous pression, parler d'une seule voix, et transformer l'exercice en plan d'action. C'est exactement ce qu'un RETEX doit produire. »
- Chat : « un mot que vous retenez de la session ».
- Self-paced : terminer le cursus IBM SkillsBuild du parcours et récupérer ses badges ; **réviser pour B20** : relire ses notes des cinq modules (A à E) et les quatre Ateliers de Synthèse — l'audit final mobilisera TOUT.
- Teaser B20 : « la semaine prochaine, dernière session : le **Grand Atelier d'Audit MedDistri**. Vous auditerez une PME complète — architecture, comptes, sauvegardes, gouvernance —, vous voterez les constats et vous construirez le plan de remédiation. Tout ce que vous avez appris depuis B01 servira. La boucle sera bouclée. »
- Terminer à l'heure exacte.

## 5. Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**exercice bonus n°9** (1:21–1:25) — il est dans le support.
2. Compresser la théorie éclair (0:09–0:19) : les règles de communication seront de toute façon rejouées à l'inject 3.
3. Raccourcir le communiqué collectif : construire 3 blocs au lieu de 6, renvoyer au modèle du support.

**Ne JAMAIS couper :** les trois décisions votées (n°2-4), l'inject 3 avec le mini-scénario, le RETEX à chaud, le quiz n°6-8, la clôture avec devoirs et teaser.

**Si vous êtes en avance :**
- Poser les questions de réflexion du support (annoncer le montant d'une rançon ; les canaux hors bande ; Hydro vs Colonial, les arguments économiques).
- Inject bonus improvisé : « 17h00 — l'assureur demande la chronologie horodatée des décisions. L'avez-vous tenue ? » (le journal de bord de crise — pont vers la chaîne de contrôle).

## 6. Travail en autonomie (Self-paced)
* **Avant la session suivante (B20)** :
  * **Sur IBM SkillsBuild** : Terminer le cursus du parcours et récupérer les badges de complétion (valorisables sur un CV ou un profil professionnel).
  * **Révision générale** : Relire ses notes des cinq modules (A à E) et les quatre Ateliers de Synthèse (B08 architecture, B12 durcissement, B15 risques, B17 logs) — le Grand Atelier d'Audit de B20 mobilisera l'ensemble du parcours.
