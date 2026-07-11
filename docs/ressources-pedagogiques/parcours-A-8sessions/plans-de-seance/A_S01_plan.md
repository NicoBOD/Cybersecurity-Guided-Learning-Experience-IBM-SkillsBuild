# Parcours A — Session 01 : Découverte de la cybersécurité & paysage des menaces
Module : Fondamentaux  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (4, verbes d'action)
- **Définir** les trois piliers de la triade CIA (Confidentialité, Intégrité, Disponibilité) à l'aide d'exemples d'incidents réels.
- **Distinguer** la posture et les objectifs de la cybersécurité offensive (comprendre l'adversaire) par rapport à la cybersécurité défensive (protéger les actifs).
- **Identifier** les quatre profils d'attaquants majeurs (cybercriminels, États, hacktivistes, menaces internes) et analyser leurs motivations.
- **Expliquer** les conséquences d'un manque de sécurité informatique pour une entreprise (financières, légales, réputationnelles) et pour un individu, chiffres et cas réels à l'appui.

## Prérequis
- Sessions précédentes : Aucun (première session d'introduction).
- Self-paced AVANT la séance (~45 min) : Lecture de ressources introductives sur la transformation numérique et la dépendance croissante aux technologies d'information, suivie d'un court questionnaire d'auto-évaluation sur les usages numériques personnels.

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama S01 ([spécifications](../slides/A_S01_slides_spec.md)).
- [ ] Le chat est ouvert à tous ; si possible, un co-animateur ou modérateur surveille le chat et remonte les meilleures questions.
- [ ] Le [script de la Démo 1 (cartographie OSINT)](../outils/A_scripts_demo.md) est relu et les captures d'écran de secours sont prêtes (en cas de problème technique, la démo se raconte avec les captures).
- [ ] Un minuteur est visible du mentor (le déroulé ci-dessous est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:05 | Sondage | Part du facteur humain dans les violations ? | C) ~60 % |
| 2 | 0:23 | Sondage | Rançongiciel sur base comptable → pilier ? | C) Disponibilité |
| 3 | 0:26 | Sondage | Interception d'e-mails RH → pilier ? | A) Confidentialité |
| 4 | 0:29 | Sondage | Erreur de droits d'accès sur ventes → pilier ? | B) Intégrité |
| 5 | 0:46 | Sondage | Menace n°1 pour VOTRE organisation ? | Opinion (pas de bonne réponse) |
| 6 | 1:15 | Sondage | Serveur non mis à jour depuis 2 ans = ? | B) Vulnérabilité |
| 7 | 1:17 | Sondage | Blocage d'un site ministériel par un collectif = ? | C) Idéologique |
| 8 | 1:19 | Sondage | Le pentest relève de... ? | A) Sécurité offensive |
| 9 | 1:21 | Sondage | Rançongiciel sur hôpital : 1re action ? | B) Isoler le réseau |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:05 | Accueil, logistique & règles du jeu | Chat : « d'où nous suivez-vous ? » |
| 0:05–0:11 | Brise-glace : le facteur humain | 📊 Sondage n°1 |
| 0:11–0:23 | Séquence 1 : La triade CIA | 💬 Chat : « C, I ou D ? » |
| 0:23–0:33 | Activité : Le Détective CIA | 📊 Sondages n°2, 3, 4 |
| 0:33–0:41 | Séquence 2 : Vulnérabilité, menace, risque & Offense/Défense | Question rhétorique |
| 0:41–0:50 | Séquence 3 : Qui sont les attaquants ? | 📊 Sondage n°5 |
| 0:50–0:57 | Séquence 4 : Le paysage de la menace en chiffres | Question rhétorique |
| 0:57–1:07 | Séquence 5 : Études de cas CHSF & France Travail | 💬 Chat : indices de phishing |
| 1:07–1:15 | Séquence 6 : Surface d'exposition + Démo OSINT | 🤔 Scénario RDP dans le chat |
| 1:15–1:21 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:21–1:26 | Dilemme décisionnel (tampon) | 📊 Sondage n°9 |
| 1:26–1:30 | Synthèse, devoirs & teaser A2 | Chat : « un mot appris aujourd'hui » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:05 — Accueil & cadrage

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous, et bienvenue dans cette première session de votre parcours cybersécurité ! Je suis [Prénom], votre mentor pour les 8 sessions à venir. Avant de commencer : cette session est interactive, mais pas comme d'habitude — vous êtes nombreux, donc tout se passera dans le **chat** et via les **sondages** qui apparaîtront à l'écran. Pour vérifier que tout fonctionne, écrivez dans le chat la ville ou la région d'où vous nous suivez. »

**Points à dérouler :**
- Se présenter en 30 secondes (parcours professionnel, lien avec la cybersécurité).
- Annoncer le cadre : 8 sessions de 1h30, un fil rouge (la PME fictive MedDistri, auditée ensemble en session 8), un format 100 % à distance.
- Lire 3-4 villes dans le chat à voix haute (créer la connivence, valider que le chat fonctionne).
- Règle d'or annoncée : « il n'y a pas de question bête ; le chat est ouvert en permanence, je fais des pauses questions régulières. »

**Transition scriptée :** « Commençons par un petit test... qui va peut-être vous surprendre. »

### 0:05–0:11 — Brise-glace : Sondage n°1 (le facteur humain)

**Consigne :** Lancer le **📊 Sondage n°1** — *« À votre avis, dans quelle proportion des violations de données le facteur humain est-il impliqué ? A) ~10 % B) ~30 % C) ~60 % D) ~90 % »*. Laisser 60 à 90 secondes de vote, commenter la courbe de participation en direct (« je vois que les votes arrivent, encore 20 secondes... »).

**🎙️ Débrief scripté :**
> « La réponse est C : environ 60 %. Selon le rapport annuel de Verizon sur les violations de données — l'un des plus consultés au monde, édition 2025 — le facteur humain est impliqué dans environ six violations sur dix : une erreur, un clic sur un lien piégé, un mot de passe volé. Retenez bien ce chiffre : la cybersécurité n'est pas d'abord une histoire de machines, c'est une histoire de personnes. Et c'est une excellente nouvelle : cela veut dire que vous, en suivant cette formation, vous devenez une ligne de défense. »

**Si beaucoup ont voté D (~90 %) :** valider l'intuition (« vous surestimez à peine — certaines études incluant toutes les formes d'erreur montent plus haut ; l'ordre de grandeur qui fait consensus est 60 % »).

**Transition scriptée :** « Pour analyser tous ces incidents, les professionnels utilisent une boussole à trois directions. On l'appelle la triade CIA — et non, rien à voir avec l'agence américaine. »

### 0:11–0:23 — Séquence 1 : La triade CIA

**Points de contenu à dérouler (support §1) :**
- **Confidentialité** : seules les personnes autorisées accèdent à l'information. Analogie : la carte postale (lisible par tous en chemin) contre la lettre cachetée (le chiffrement). Exemples : boîte mail piratée, dossier médical consulté sans autorisation.
- **Intégrité** : l'information reste exacte et complète. Analogie : le cachet de cire — il ne cache pas le contenu, il prouve qu'il n'a pas été altéré (c'est le rôle du hachage SHA-256). Exemples : RIB remplacé dans un virement, doses faussées dans un logiciel médical.
- **Disponibilité** : l'information est accessible quand on en a besoin. Analogie : la bibliothèque aux portes fermées — livres intacts, mais inutiles. Exemples : site e-commerce saturé pendant les soldes (DoS), clinique bloquée par un rançongiciel.
- Question rhétorique à poser en passant : *« Si un pirate bloque vos fichiers sans les voler, quel pilier tombe ? »* (laisser 3 secondes, répondre : la Disponibilité).

**Interaction (vers 0:20) — 💬 Question chat :**
> « À vous : pensez à votre métier ou votre quotidien. Laquelle des trois lettres — C, I ou D — serait la plus grave à perdre pour vous ? Tapez la lettre dans le chat, avec votre secteur si vous voulez. »

**🎙️ Débrief scripté (lire 4-5 réponses) :**
> « Je vois des D en logistique, des C en RH, des I en comptabilité... C'est exactement la leçon : il n'y a pas de bonne réponse universelle. Un hôpital meurt si la Disponibilité tombe, une banque si l'Intégrité tombe, un cabinet d'avocats si la Confidentialité tombe. Toute stratégie de sécurité commence par cette question : qu'est-ce qui est vital pour MOI ? »

**Transition scriptée :** « Vérifions que la boussole est bien en main. Je vous propose de jouer au détective. »

### 0:23–0:33 — Activité : Le Détective CIA (Sondages n°2 à 4)

**Consigne :** Annoncer la règle du jeu — trois mini-enquêtes, un vote par enquête, débrief immédiat. Lancer successivement les **📊 Sondages n°2, 3 et 4** (scénarios et options : voir le [support de cours, section « Le Détective CIA »](../supports-md/A_S01_support.md)). Rythme : ~1 min de vote + ~2 min de débrief par scénario.

**🎙️ Verbatim de lancement :**
> « Vous êtes désormais détectives en cybersécurité. Je vais vous présenter trois incidents réalistes. À chaque fois, votre mission : identifier quel pilier de la triade a été touché. Attention, il y a des pièges dans les réponses proposées ! Premier cas... »

**Débriefs scriptés (points obligatoires) :**
- **N°2 (rançongiciel → Disponibilité)** : « Le chiffrement bloque l'accès : la Disponibilité tombe en premier. Gardez ce cas en tête, on le retrouvera en chair et en os dans quelques minutes avec un vrai hôpital français. Et notez le mot "double extorsion" : souvent, les données sont AUSSI volées — la Confidentialité tombe ensuite. »
- **N°3 (interception e-mails → Confidentialité)** : « Rien n'a été modifié, rien n'a été bloqué — et pourtant l'incident est grave. La Confidentialité peut être violée en silence total ; c'est ce qui la rend sournoise. »
- **N°4 (erreur de droits → Intégrité)** : « Piège : il n'y a AUCUN pirate dans ce scénario ! Une simple erreur d'administration suffit à compromettre l'Intégrité. La sécurité protège aussi contre la maladresse, pas seulement contre la malveillance. »
- Signaler le piège transversal : « Non-répudiation, Authenticité, Résilience sont de vrais concepts — mais pas des piliers de la triade. »

**Transition scriptée :** « Vous savez maintenant diagnostiquer un incident. Question suivante : comment évalue-t-on un danger AVANT qu'il ne se produise ? Trois mots à ne plus jamais confondre. »

### 0:33–0:41 — Séquence 2 : Vulnérabilité, menace, risque & Offense/Défense

**Points de contenu à dérouler (support §2 et §3) :**
- L'analogie du cambriolage : la **vulnérabilité** est la porte ouverte, la **menace** est le cambrioleur, le **risque** est la probabilité qu'il entre, multipliée par ce qu'il peut voler. Formule : *Risque = Menace × Vulnérabilité × Impact*.
- Dérouler l'exemple chiffré du support (serveur de paie exposé vs vieil ordinateur de salle de pause) : même menace, même type de faille, risque radicalement différent — tout dépend de l'impact. Parallèle avec l'assurance habitation : on évalue d'abord la valeur de ce qu'on protège.
- Message clé : *« On ne supprime pas les menaces — les cambrioleurs existeront toujours. On ferme les portes. »*
- **Offense vs Défense** : la Red Team attaque de façon contrôlée, la Blue Team défend au quotidien, la Purple Team les fait collaborer. Point juridique à marteler : un test d'intrusion sans autorisation écrite est un délit (Code pénal, art. 323-1 et suivants) — même avec de bonnes intentions.

**Question rhétorique (0:39) :** *« À votre avis, de quoi une entreprise a-t-elle besoin en premier : d'attaquants éthiques ou de défenseurs ? »* — laisser le chat réagir 20 secondes, puis trancher : « Les deux, mais dans cet ordre : on défend d'abord, on teste ensuite. L'offense sans défense, c'est un crash-test sans voiture. »

**Transition scriptée :** « Nous avons parlé du cambrioleur en théorie. Passons aux vrais visages : qui nous attaque, réellement, en 2025 ? »

### 0:41–0:50 — Séquence 3 : Qui sont les attaquants ?

**Points de contenu à dérouler (support §4) :**
- Casser le cliché de l'adolescent à capuche : la cybercriminalité est une **industrie**, avec filiales, franchises (le modèle RaaS) et support client. Citer LockBit — le groupe derrière l'attaque de l'hôpital de Corbeil-Essonnes — partiellement démantelé en février 2024 par l'opération internationale « Cronos ».
- Les 4 profils, avec pour chacun motivation + méthode type :
    1. **Cybercriminels** — l'argent ; rançongiciels, hameçonnage de masse. La menace la plus probable pour 99 % des organisations.
    2. **États-nations** — espionnage, sabotage, influence ; attaques longues et discrètes (APT : ils s'installent et attendent, parfois des mois).
    3. **Hacktivistes** — idéologie ; défiguration de sites, DDoS de protestation (type Anonymous). Impact souvent plus médiatique que technique.
    4. **Menaces internes** — vengeance OU simple négligence ; déjà à l'intérieur, donc les plus durs à détecter. Rappeler le sondage n°1 : l'erreur humaine EST une menace interne involontaire.

**Interaction (0:46) :** Lancer le **📊 Sondage n°5** — *« Quel profil représente la menace n°1 pour VOTRE organisation ? »* (sondage d'opinion, pas de bonne réponse).

**🎙️ Débrief scripté :**
> « Résultat typique : les cybercriminels arrivent en tête — et statistiquement, c'est juste. Mais regardez le score de la menace interne... [commenter le résultat réel]. Dans la plupart des groupes, elle est sous-estimée. Or elle a un accès que personne d'autre n'a : les clés de la maison. Les meilleurs programmes de sécurité traitent les deux. »

**Transition scriptée :** « Vos perceptions sont posées. Confrontons-les maintenant aux chiffres officiels. »

### 0:50–0:57 — Séquence 4 : Le paysage de la menace en chiffres

**Points de contenu à dérouler (support §5 — les 5 chiffres clés, chacun avec sa source et son année) :**
- ~60 % des violations impliquent le facteur humain (Verizon DBIR 2025) — rappel du sondage n°1, boucle bouclée.
- Près de 4 400 événements de sécurité traités par l'ANSSI en 2024 (+~15 % sur un an) ; TPE/PME/ETI et collectivités = premières victimes des rançongiciels (Panorama de la cybermenace 2024).
- L'hameçonnage = menace n°1 en volume (Cybermalveillance.gouv.fr, rapport 2024).
- Record de violations notifiées à la CNIL en 2024 (plus de 5 000, en forte hausse).
- ~4,4 M$ de coût moyen d'une violation dans le monde ; plusieurs mois entre l'intrusion et son confinement (IBM Cost of a Data Breach 2025).

**🎙️ Formulation prête à dire (le message derrière les chiffres) :**
> « Trois choses à retenir de ces chiffres. Un : l'attaque n'est pas un événement rare, c'est un flux industriel et permanent. Deux : les petites structures sont des cibles PRIVILÉGIÉES — précisément parce qu'elles se croient trop petites pour intéresser qui que ce soit. Trois : l'humain est à la fois la première porte d'entrée et le meilleur pare-feu. Vous êtes ici pour devenir la deuxième option. »

**Question rhétorique (0:56) :** *« Plusieurs mois pour découvrir et contenir une intrusion... Que peut faire un attaquant chez vous pendant six mois ? »* — laisser planer 3 secondes, ne pas répondre : « Gardez cette question en tête, on y répondra en session 7 sur la réponse aux incidents. »

**Transition scriptée :** « Assez de statistiques. Voici deux histoires vraies, françaises, récentes — et tout ce qu'on vient de voir va s'y retrouver. »

### 0:57–1:07 — Séquence 5 : Études de cas (CHSF & France Travail)

**Cas n°1 — Hôpital de Corbeil-Essonnes (5 min, support §6) :**
- Raconter chronologiquement : nuit du 20 au 21 août 2022, rançongiciel LockBit, systèmes chiffrés, retour au papier, transferts de patients, 10 M$ de rançon exigés.
- Points d'analyse à expliciter : refus de payer (doctrine française : un établissement public ne paie pas), publication d'environ 11 Go de données en représailles → la violation de **Disponibilité** devient AUSSI une violation de **Confidentialité** (la « double extorsion » annoncée au sondage n°2), des mois de reconstruction, un coût de plusieurs millions d'euros — sans commune mesure avec le budget sécurité de l'époque.
- 🎙️ Punchline : « Première idée reçue qui tombe : "les pirates ne s'attaquent pas aux hôpitaux". Si. Pour un cybercriminel, plus la cible est critique, plus elle est censée payer vite. »

**Cas n°2 — France Travail (4 min, support §6) :**
- Raconter : mars 2024, comptes de partenaires usurpés, données de potentiellement 43 millions de personnes exfiltrées (identité, NIR, coordonnées) — l'une des plus grandes fuites françaises. Ni mot de passe ni données bancaires volés... et pourtant.
- Point d'analyse : une violation de **Confidentialité** pure — aucun système bloqué, rien de modifié — dont l'effet réel est différé : ces données alimentent des campagnes d'hameçonnage crédibles pendant des années. Mentionner Viamedis/Almerys (~33 millions d'assurés, février 2024) : 2024, année charnière de la prise de conscience française.

**Interaction (1:05) — 💬 Question chat :**
> « Vous recevez demain un e-mail de "France Travail" vous demandant de confirmer vos coordonnées bancaires. Donnez-moi dans le chat UN indice que vous vérifieriez avant de cliquer. »

**🎙️ Débrief scripté (lire 4-5 réponses) :**
> « Excellent : l'adresse de l'expéditeur, survoler le lien sans cliquer, le ton d'urgence, la demande inhabituelle — France Travail ne demande JAMAIS vos coordonnées bancaires par e-mail. Vous venez de faire, sans le savoir, l'introduction de la session A2 : l'ingénierie sociale. »

**Si le temps manque :** compresser France Travail à 2 min (chiffre + leçon), conserver impérativement la question chat.

### 1:07–1:15 — Séquence 6 : Surface d'exposition & Démo OSINT

**Points de contenu (support « Focus pratique ») :**
- Définir la surface d'exposition : tout ce qu'un attaquant voit de l'extérieur. Analogie : le cambrioleur qui fait le tour du pâté de maisons avant d'agir.
- Parcourir rapidement le tableau des 4 éléments (DNS, serveurs web, ports ouverts type RDP/SSH, employés sur les réseaux sociaux) avec la mesure d'hygiène associée.

**Démonstration (1:09, ~4 min) :** Dérouler la [Démo 1 — Cartographie passive OSINT](../outils/A_scripts_demo.md) en partage d'écran : montrer ce qu'un attaquant collecte légalement et passivement sur une entreprise fictive (domaine, serveurs de messagerie, e-mails divulgués). Insister deux fois : **tout est légal et passif ici — aucune intrusion**. En cas de pépin technique : basculer sur les captures d'écran préparées et raconter la démo.

**Interaction (1:13) — 🤔 Scénario « Que feriez-vous si... ? » (dans le chat) :**
> « Vous découvrez que le serveur de votre PME expose un accès RDP ouvert sur Internet, mot de passe : Admin2024. Trois options : A) ce n'est pas mon rôle, je ne dis rien ; B) je préviens immédiatement le responsable informatique ; C) je teste moi-même le mot de passe "pour vérifier". Tapez A, B ou C. »

**🎙️ Débrief scripté :**
> « B, bien sûr. Mais le vrai piège, c'est C : tester un accès sans autorisation écrite est un délit — même pour "aider". La posture professionnelle : signaler, jamais exploiter. Et pour ceux qui ont répondu A... souvenez-vous du sondage n°1 : 60 % de facteur humain. La sécurité, c'est vous aussi. »

### 1:15–1:21 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7 et 8** à la suite (~2 min chacun, vote + débrief). Questions, options et éléments de débrief : voir le [support, section « Quiz de validation »](../supports-md/A_S01_support.md). Annoncer l'esprit : « pas une évaluation, un ancrage — les erreurs sont les bienvenues, c'est maintenant qu'il faut les faire. »

**Points de débrief obligatoires :**
- N°6 : re-projeter mentalement la formule Risque = Menace × Vulnérabilité × Impact (le serveur obsolète = la porte ouverte).
- N°7 : re-balayer les 4 profils en 20 secondes (argent / espionnage / idéologie / négligence).
- N°8 : offense = tester, défense = protéger ; l'autorisation écrite, toujours.

### 1:21–1:26 — Dilemme décisionnel (Sondage n°9) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°9** — le rançongiciel sur un hôpital (options et guide : voir le [support, « Exercice bonus »](../supports-md/A_S01_support.md)).

**🎙️ Verbatim de lancement :**
> « Dernière décision de la journée, et cette fois vous êtes aux commandes. Vous dirigez un hôpital, il est 3 heures du matin, un rançongiciel vient de bloquer les dossiers médicaux. Que faites-vous EN PREMIER ? »

**Débrief scripté :** isoler le réseau (B) coupe la propagation ; payer (A) ne garantit rien et finance le crime — c'est le choix qu'a écarté le CHSF, que vous connaissez maintenant ; restaurer sur un réseau infecté (C) revient à reconstruire la maison pendant l'incendie.

### 1:26–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Résumons votre première boîte à outils : une boussole — la triade CIA ; une équation — Risque égale Menace fois Vulnérabilité fois Impact ; quatre visages d'attaquants ; et deux histoires vraies qui prouvent que tout cela n'a rien de théorique. Avant de se quitter : tapez dans le chat UN mot que vous retenez de cette session. »

**Points de clôture :**
- Lire 4-5 mots du chat à voix haute (renforcement collectif).
- Devoirs : module IBM SkillsBuild *Introduction aux menaces cyber et logiciels malveillants* (~60 min, mini-quiz à 80 %).
- Teaser A2 : « La semaine prochaine, on entre dans la tête des attaquants : hameçonnage, manipulation, ingénierie sociale. D'ici là... méfiez-vous des e-mails de France Travail. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Le segment tampon est le **Dilemme (1:21–1:26)** : il peut être supprimé sans casser la progression (il est dans le support en exercice bonus, les apprenants le feront en autonomie).
2. Compresser la séquence chiffres (0:50–0:57) à 4 min : ne garder que facteur humain, ANSSI et coût moyen.
3. Ne JAMAIS couper : le Détective CIA, les études de cas, le quiz de validation.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°3 : faut-il payer une rançon ? — excellent débat de chat).
2. Approfondir la démo OSINT (montrer un deuxième exemple de recherche).
3. Ouvrir une séquence questions/réponses libre via le chat.

## Articulation avec l'atelier de fin de parcours
- Cette session pose les fondations de l'Atelier d'Audit Interactif MedDistri (session A8). Les notions de triade CIA et de profils d'attaquants y sont mobilisées pour évaluer la criticité des données et les menaces pesant sur la PME.

## Self-paced APRÈS la séance (~120 min) & évaluation formative
- Suivre le module en ligne d'introduction à la cybersécurité (concepts de base et vocabulaire).
- Quiz d'auto-évaluation en ligne (10 questions de type vrai/faux et QCM) sur la triade CIA et les motivations des attaquants.
- Lecture suggérée : Guide des bonnes pratiques de l'hygiène informatique (document ANSSI ou équivalent vulgarisé) et, pour les curieux, la synthèse du dernier Panorama de la cybermenace de l'ANSSI.
