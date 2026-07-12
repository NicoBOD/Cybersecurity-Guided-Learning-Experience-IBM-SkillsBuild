# Parcours A — Session 02 : Menaces, attaques & ingénierie sociale
Module : Menaces  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (4, verbes d'action)
- **Classifier** les principales familles de codes malveillants (*malware* : rançongiciels, chevaux de Troie, logiciels espions, vers) selon leurs modes de fonctionnement.
- **Reconnaître** les indices de suspicion d'une tentative d'hameçonnage (*phishing*) par e-mail, SMS (*smishing*) ou téléphone (*vishing*).
- **Décrire** les grandes étapes d'une intrusion informatique en s'appuyant sur la chaîne d'attaque (*cyber kill chain*).
- **Appliquer** le réflexe de la double validation par canal alternatif face à toute demande sensible (virement, RIB, code).

## Prérequis
- Sessions précédentes : A1 (paysage cyber, triade CIA, surface d'exposition OSINT).
- Self-paced AVANT la séance (~60 min) : Module d'auto-formation en ligne sur les types de logiciels malveillants courants et visionnage d'une courte vidéo explicative sur l'ingénierie sociale.

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **11 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama S02 ([spécifications](../slides/A_S02_slides_spec.md)) — y compris les 4 visuels de la Chasse au phishing.
- [ ] Le [script de la Démo 2 — Simulation de vishing](../outils/A_scripts_demo.md#demo-2-vishing) est relu (jeu vocal théâtralisé, aucun outil requis).
- [ ] Le chat est ouvert ; un modérateur remonte les meilleures anecdotes du brise-glace si possible.
- [ ] Un minuteur est visible du mentor.

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Temps médian ouverture → saisie des données (phishing) ? | A) < 1 minute |
| 2 | 0:36 | Sondage | SMS colis Chronopost 1,95 € : phishing ou légitime ? | Phishing (smishing) |
| 3 | 0:40 | Sondage | E-mail Netflix `netf1ix-securite.com` ? | Phishing |
| 4 | 0:43 | Sondage | Message interne maladroit sans lien ? | Légitime |
| 5 | 0:46 | Sondage | E-mail du DAF avec changement de RIB ? | Phishing (BEC) |
| 6 | 1:14 | Sondage | Cartes cadeaux « de la direction » : type d'attaque ? | B) Spear-phishing / BEC |
| 7 | 1:16 | Sondage | Action la plus sûre ? | C) Canal alternatif |
| 8 | 1:20 | Sondage | Malware qui se propage seul ? | B) Le ver |
| 9 | 1:22 | Sondage | Envoi de l'e-mail piégé = étape Kill Chain ? | C) Livraison |
| 10 | 1:24 | Sondage | Levier qui court-circuite la réflexion ? | B) L'urgence |
| 11 | Tampon | Sondage | Anomalie prioritaire sur facture fournisseur ? | B) Domaine modifié |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil & fil rouge depuis A1 | Chat : présence |
| 0:04–0:10 | Brise-glace : la minute fatale | 📊 Sondage n°1 |
| 0:10–0:14 | Vos histoires de messages suspects | 💬 Chat : anecdotes |
| 0:14–0:26 | Séquence 1 : Typologie des malwares | 💬 Chat : « combien de familles ? » |
| 0:26–0:36 | Séquence 2 : Les leviers de l'ingénierie sociale | Question rhétorique |
| 0:36–0:50 | Activité : La Chasse au Phishing | 📊 Sondages n°2, 3, 4, 5 |
| 0:50–0:57 | Séquence 3 : La Cyber Kill Chain | Question rhétorique |
| 0:57–1:04 | Démo 2 : Simulation de vishing | Chat : réactions |
| 1:04–1:14 | Séquence 4 : Chiffres & cas réels (Pathé, Arup) | 🤔 Scénario deepfake dans le chat |
| 1:14–1:20 | Mise en situation BEC | 📊 Sondages n°6, 7 |
| 1:20–1:25 | Quiz de validation | 📊 Sondages n°8, 9, 10 |
| 1:25–1:30 | Synthèse, règle d'or & devoirs | Chat : « un réflexe retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & fil rouge

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous, ravi de vous retrouver pour cette session 2 ! La semaine dernière, nous avons vu QUI nous attaque et POURQUOI. Aujourd'hui, on passe au COMMENT : les armes logicielles — les malwares — et l'arme psychologique — l'ingénierie sociale. Petit test de présence : tapez "OK" dans le chat si vous m'entendez bien. »

**Points à dérouler :**
- Rappel express d'A1 en 30 secondes : triade C-I-D, profils d'attaquants, surface d'exposition OSINT — « cette surface d'exposition, les attaquants s'en servent aujourd'hui pour préparer leurs pièges ».
- Annoncer le programme et la promesse : « à la fin de la session, vous aurez UN réflexe qui neutralise 90 % de ce qu'on va voir. »

**Transition scriptée :** « On commence par un chiffre qui fait mal. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (la minute fatale)

**Consigne :** Lancer le **📊 Sondage n°1** — *« Combien de temps s'écoule, en médiane, entre l'ouverture d'un e-mail de phishing et la saisie des données par la victime ? »* Laisser 60-90 s de vote.

**🎙️ Débrief scripté :**
> « La réponse est A : moins d'une minute. Selon le rapport Verizon DBIR 2024 : environ 21 secondes pour cliquer, 28 secondes de plus pour taper ses identifiants. Moins d'une minute entre "tiens, un e-mail" et "catastrophe". Qu'est-ce que ça veut dire ? Que la réflexion après coup ne vous sauvera pas — c'est le réflexe AVANT le clic qu'on va installer aujourd'hui. »

**Transition scriptée :** « Et je suis sûr que beaucoup d'entre vous ont déjà croisé ces pièges. Racontez-moi. »

### 0:10–0:14 — 💬 Vos histoires de messages suspects

**Consigne :** Question chat — *« Avez-vous déjà reçu un message suspect ? SMS de colis, fausse contravention, e-mail alarmiste ? Racontez en une phrase : le message, et l'indice qui vous a mis la puce à l'oreille. »* Lire 4-5 anecdotes à voix haute, nommer à chaque fois l'indice (URL suspecte, urgence, faute) et le levier psychologique.

**🎙️ Formulation de synthèse :**
> « Vous voyez : vous avez déjà tous un début d'instinct. Notre travail aujourd'hui, c'est de le transformer en méthode. Et pour ça, commençons par connaître les armes de l'adversaire. »

### 0:14–0:26 — Séquence 1 : Typologie des malwares

**Points de contenu à dérouler (support §1) :**
- La question qui classe tout : **que cherche le malware ?** Extorquer / ouvrir une porte / observer / se propager.
- **Rançongiciel** : chiffrement + rançon + double extorsion — rappel express du CHSF (A1) sans re-raconter : « vous savez déjà à quoi ça ressemble en vrai ».
- **Cheval de Troie** : c'est la victime qui le fait entrer (mythe grec) ; ouvre des backdoors.
- **Spyware/Keylogger** : ne casse rien, n'affiche rien — il observe ; chaque frappe clavier capturée.
- **Ver** : l'auto-propagation par les failles, sans clic — ce qui a permis à WannaCry de faire le tour du monde (rappel A1) ; différence avec le virus (fichier hôte).

**Interaction (0:23) — 💬 Question chat :**
> « Un "antivirus gratuit" téléchargé sur un site douteux installe en réalité un programme qui enregistre vos frappes clavier. Combien de familles de malwares dans cette phrase ? Tapez un chiffre. »

**Débrief scripté :** deux — un cheval de Troie (déguisement) qui livre un spyware (keylogger). « Les familles se combinent : le trojan est le véhicule, le spyware est le passager. »

**Transition scriptée :** « Mais le meilleur malware du monde a un problème : il faut que quelqu'un le fasse entrer. Et pour ça, l'attaquant n'attaque pas votre ordinateur. Il VOUS attaque. »

### 0:26–0:36 — Séquence 2 : Les leviers de l'ingénierie sociale

**Points de contenu à dérouler (support §2) :**
- L'analogie du **faux agent du gaz** : pas d'effraction, un faux badge et une "fuite urgente" — vous ouvrez la porte vous-même.
- Les **4 leviers** avec un exemple chacun : Urgence (compte suspendu dans 2h), Autorité (le DG, la police, les impôts), Confiance (EDF, Netflix, un collègue), Curiosité/Appât (fichier "salaires.xlsx").
- Les **4 canaux** : phishing (masse), spear-phishing (personnalisé grâce à l'OSINT d'A1), smishing (SMS), vishing (téléphone).
- La logique économique : 0,1 % de réussite sur un million d'e-mails = 1 000 victimes ; le spear-phishing inverse l'équation — peu de cibles, beaucoup de préparation, gains démultipliés.
- Annoncer la mutation IA : « les fautes d'orthographe, c'est fini — l'IA écrit des pièges parfaits. On y revient avec un cas à 25 millions de dollars. »

**Question rhétorique (0:34) :** *« À votre avis, pourquoi les attaquants préfèrent-ils appeler la comptabilité un vendredi à 17h45 ? »* — laisser le chat réagir, répondre : urgence + fatigue + hiérarchie injoignable pour vérifier = triple levier.

**Transition scriptée :** « Assez de théorie. Place à la pratique : je vais vous envoyer à la chasse. »

### 0:36–0:50 — Activité : La Chasse au Phishing (Sondages n°2 à 5)

**Consigne :** Annoncer la règle : quatre messages vont s'afficher ; pour chacun, votez « Phishing / Légitime / Je ne sais pas » ; analyse collective après chaque vote. Projeter les visuels (slides 6) et lancer les **📊 Sondages n°2, 3, 4, 5** (~3 min par message : 1 min de vote, 2 min d'analyse). Messages et débriefs complets : voir le [support, section « La Chasse au Phishing »](../supports-md/A_S02_support.md).

**🎙️ Verbatim de lancement :**
> « Vous êtes l'analyste sécurité de l'entreprise. Quatre messages viennent d'arriver dans les boîtes de vos collègues. À vous de trier : phishing ou légitime ? Attention — il y a au moins un piège dans les deux sens. »

**Débriefs scriptés (points obligatoires) :**
- N°2 (SMS colis) : lien raccourci = destination masquée ; le micro-paiement de 1,95 € ne vise pas 1,95 € mais votre carte entière.
- N°3 (Netflix) : dérouler les 3 indices du Focus pratique (typosquatting, urgence, lien vers IP) en survolant sans cliquer à l'écran.
- N°4 (message interne) : LE piège inversé — des fautes mais domaine authentique, aucun lien, aucune demande sensible → légitime. « Des fautes ne condamnent pas un message ; une demande sensible, si. »
- N°5 (DAF/RIB) : le plus dur — personnalisation issue de l'OSINT. Règle absolue à marteler : **un changement de RIB se vérifie TOUJOURS par un canal alternatif initié par vous.**

**Transition scriptée :** « Vous venez d'intercepter des attaques à l'étape "Livraison". Voyons maintenant la carte complète du parcours d'un attaquant. »

### 0:50–0:57 — Séquence 3 : La Cyber Kill Chain

**Points de contenu à dérouler (support §3) :**
- Les 7 étapes dans l'ordre, avec l'exemple fil rouge d'un spear-phishing : reconnaissance (LinkedIn), armement (PDF piégé), livraison (l'e-mail), exploitation (lecteur PDF pas à jour), installation, C2, actions sur objectifs.
- Le message défensif : **brisez UN maillon, brisez l'attaque** — et à chaque maillon sa contre-mesure : sensibilisation (1, 3-4), filtrage mail (3), mises à jour (4), antivirus/EDR (5), surveillance réseau (6). C'est la défense en profondeur d'A1, version chronologique.
- Mentionner MITRE ATT&CK comme « la version encyclopédique moderne » (ressource pour les curieux).

**Question rhétorique (0:56) :** *« À quelle étape la formation que vous suivez en ce moment agit-elle ? »* — réponse : surtout 3 et 4 (vous refusez la livraison, vous ne déclenchez pas l'exploitation) — « vous ÊTES une contre-mesure. »

### 0:57–1:04 — Démo 2 : Simulation de vishing

**Consigne :** Dérouler la [Démo 2 — Simulation de vishing](../outils/A_scripts_demo.md#demo-2-vishing) : jouer théâtralement le dialogue du faux support technique qui, sous pression (fausse attaque en cours), extorque un code MFA. En webinaire : jouer les deux voix soi-même en changeant de ton, ou lire le script à deux avec le modérateur.

**Points de débrief obligatoires :**
- Faire réagir le chat : *« À quel moment précis auriez-vous raccroché ? »* — lire 3-4 réponses.
- Nommer les leviers entendus : urgence (attaque en cours), autorité (support officiel), peur (vos comptes sont menacés).
- Règle absolue : **un code reçu par SMS ou application ne se communique JAMAIS à personne** — pas même au « support » ; le vrai support ne le demande jamais.

**Transition scriptée :** « Vous pensez peut-être : "ça ne marche que sur les gens crédules". Les deux histoires qui suivent vont vous faire changer d'avis. »

### 1:04–1:14 — Séquence 4 : Chiffres & cas réels

**Chiffres (2 min, support §4) :** re-projeter le sondage n°1 (< 1 minute), puis : hameçonnage = menace n°1 des particuliers et piratage de compte en tête côté entreprises (Cybermalveillance.gouv.fr 2024) ; ~2,8 milliards de dollars de pertes BEC déclarées au FBI par an (IC3 2024) — « la fraude au virement rapporte plus que les rançongiciels en montants déclarés ».

**Cas n°1 — Pathé, 2018 (3 min, support §5) :** raconter : faux e-mails du « siège parisien », acquisition « confidentielle » à Dubaï, ~19,2 M€ virés par les deux dirigeants de la filiale néerlandaise, licenciés ensuite. Nommer les leviers : autorité + urgence + secret (le secret neutralise la double validation !). Punchline : « le BEC ne cible pas les naïfs, il cible les processus. »

**Cas n°2 — Arup, 2024 (3 min, support §5) :** raconter : l'employé se méfie de l'e-mail (bon réflexe !), demande confirmation... et la reçoit en **visioconférence** — avec un directeur financier et des collègues 100 % deepfakes. ~25 M$ virés en quinze transactions. Punchline : « "je l'ai vu, je l'ai entendu" ne prouve plus rien. Seul compte : QUI a initié le contact, et sur QUEL canal. »

**Interaction (1:12) — 🤔 Scénario deepfake (chat) :** dérouler le mini-scénario du support (« votre DG vous appelle en visio... ») — voter A/B/C dans le chat, débriefer : B (rappeler soi-même sur le numéro interne connu) ; C est un piège (le compte e-mail peut être aux mains de l'attaquant).

### 1:14–1:20 — Mise en situation BEC (Sondages n°6 et 7)

**Consigne :** Lancer les **📊 Sondages n°6 puis 7** (cartes cadeaux « de la direction » : type d'attaque, puis action la plus sûre). Questions et débriefs : voir le [support, « Mise en situation BEC »](../supports-md/A_S02_support.md).

**Points de débrief obligatoires :** ne jamais confirmer via le canal d'origine ; le canal alternatif doit être initié par soi ; le bon circuit de signalement = service informatique/sécurité, pas un e-mail groupé aux collègues.

### 1:20–1:25 — Quiz de validation (Sondages n°8 à 10)

**Consigne :** Lancer les **📊 Sondages n°8, 9, 10** à la suite (~90 s chacun). Réponses : le ver ; Livraison ; l'urgence. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/A_S02_support.md). Esprit : ancrage, pas évaluation.

### 1:25–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Votre boîte à outils s'agrandit : quatre familles de malwares, quatre leviers de manipulation, sept maillons de la Kill Chain — et surtout UNE règle d'or : toute demande sensible se vérifie par un canal alternatif que VOUS initiez. Pathé, Arup : des professionnels sont tombés faute de cette règle. Pas vous. Avant de partir : tapez dans le chat le réflexe que vous retenez. »

**Points de clôture :**
- Lire 4-5 réflexes dans le chat.
- Devoirs : module IBM SkillsBuild *Introduction aux réseaux et à la sécurité réseau* (~90 min) + exercice d'observation : relever 3 indices de phishing dans sa propre boîte mail (sans cliquer !) et, pour les SMS frauduleux, les transférer au 33700.
- Teaser A3 : « la semaine prochaine, on passe côté infrastructure : pare-feux, VPN, HTTPS — les remparts techniques qui rattrapent les clics malheureux. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Compresser le brise-glace anecdotes (0:10–0:14) à 2 min (lire 2 anecdotes au lieu de 5).
2. Réduire la mise en situation BEC (1:14–1:20) au seul sondage n°7 (l'action à faire) — le n°6 est redondant avec la chasse au phishing.
3. Ne JAMAIS couper : la Chasse au phishing, la démo vishing, les cas réels.

**Si vous êtes en avance :**
1. Lancer le **📊 Sondage n°11** (bonus vigilance : la facture fournisseur `st0rmshield`).
2. Dérouler les **Questions de réflexion** du support (notamment la n°3 : le collègue qui avoue avoir cliqué — excellent débat sur la culture du blâme).
3. Ouvrir une séquence questions/réponses libre via le chat.

## Articulation avec l'atelier de fin de parcours
- Cette session fournit les briques sur le facteur humain pour l'Atelier d'Audit Interactif MedDistri. Les apprenants y mobilisent les contre-mesures face à l'ingénierie sociale (procédure de double validation, sensibilisation) pour conseiller la directrice.

## Self-paced APRÈS la séance (~120 min) & évaluation formative
- Suivre le module interactif sur la sensibilisation à la sécurité et à la détection de l'ingénierie sociale.
- Quiz d'auto-évaluation en ligne (10 questions de type scénarios d'attaque).
- Exercice pratique individuel : inspecter sa propre boîte de messagerie (personnelle ou académique) et signaler au mentor un exemple réel suspect reçu récemment (capture d'écran, sans cliquer sur les liens).
