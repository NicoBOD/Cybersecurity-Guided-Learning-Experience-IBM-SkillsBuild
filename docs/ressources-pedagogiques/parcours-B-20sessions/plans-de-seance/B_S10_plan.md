# Plan de séance — Session B10 : Cryptographie essentielle
Parcours : B 20 sessions  |  Module : C — Identités, cloud & données  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (verbes d'action)
- **Expliquer** la différence de fonctionnement et d'usage entre chiffrement symétrique (clé unique) et asymétrique (couple de clés).
- **Analyser** une fonction de hachage (SHA-256) : intégrité, effet d'avalanche — et le stockage correct des mots de passe (sel, fonctions lentes).
- **Décrire** le rôle d'une PKI, des autorités de certification et le contenu d'un certificat X.509.

## Prérequis & progression
- **Prérequis** : B09 (l'identité — dont la recherche sur le « sel ») et B07 (le handshake TLS, admis sans démonstration).
- **Lien de progression** : Cette session donne les fondations mathématiques de tout ce qui précède (TLS, BitLocker, signatures) et prépare la sécurisation du cloud (B11) et la protection des données (B12).

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama B10 ([spécifications](../slides/B_S10_slides_spec.md)) — les empreintes SHA-256 de l'activité doivent être lisibles (police à chasse fixe).
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Comment un site doit-il conserver votre mot de passe ? | B) Haché avec un sel unique |
| 2 | 0:46 | Sondage | Effet d'avalanche : caractères communs entre les deux empreintes ? | C) Pratiquement aucun |
| 3 | 0:50 | Sondage | Pourquoi publier le SHA-256 d'un fichier .ISO ? | A) Vérifier l'intégrité du téléchargement |
| 4 | 0:54 | Sondage | Peut-on retrouver le document depuis son empreinte ? | B) Non — mais on peut tester des candidats |
| 5 | 1:08 | Sondage | Vérifiez-vous les empreintes de vos téléchargements ? | Opinion (pas de bonne réponse) |
| 6 | 1:16 | Sondage | Pourquoi la cryptographie hybride (TLS) ? | A) L'asymétrique livre la clé, la symétrique chiffre vite |
| 7 | 1:18 | Sondage | À quoi sert le sel ? | B) Empreintes uniques, rainbow tables inopérantes |
| 8 | 1:20 | Sondage | Que contient un certificat X.509 ? | C) Clé publique + identité + signature de l'AC |
| 9 | Tampon | Sondage | Cause la plus courante d'une alerte « Connexion non sécurisée » ? | B) Certificat expiré ou AC non reconnue |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil & retour sur la recherche « sel » | 💬 Chat : définitions trouvées |
| 0:04–0:10 | Brise-glace : où va votre mot de passe ? | 📊 Sondage n°1 |
| 0:10–0:24 | Séquence 1 : Symétrique vs asymétrique | 💬 Chat : le code de César |
| 0:24–0:36 | Séquence 2 : Le hachage — intégrité & mots de passe | Question rhétorique |
| 0:36–0:44 | Séquence 3 : PKI, certificats & signature numérique | Question rhétorique |
| 0:44–0:58 | Activité : Le laboratoire du hachage | 📊 Sondages n°2, 3, 4 |
| 0:58–1:08 | Chiffres clés & affaires Adobe + LinkedIn | 💬 Chat : réactions |
| 1:08–1:12 | Et vous ? Les checksums | 📊 Sondage n°5 |
| 1:12–1:16 | Mini-scénario : le « mot de passe oublié » qui répond | 🤔 Chat : A, B ou C |
| 1:16–1:22 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:22–1:26 | Exercice bonus : l'alerte du navigateur (tampon) | 📊 Sondage n°9 |
| 1:26–1:30 | Synthèse, devoirs & teaser B11 | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & retour sur le self-paced

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous ! Ce soir, on ouvre le coffre à outils mathématique de tout ce qu'on a vu jusqu'ici : le cadenas TLS, BitLocker, les certificats... Mais d'abord, votre recherche de la semaine : le sel cryptographique. En une phrase dans le chat : à quoi sert-il ? »

**Points à dérouler :**
- Lire 2-3 définitions du chat, valider sans tout dévoiler : « gardez ça en tête — dans une heure, vous saurez exactement pourquoi son absence a coûté 117 millions de comptes à LinkedIn. »
- Rappel express de B09 : l'identité comme périmètre, Uber, 23andMe.
- Annonce du programme : chiffrer, hacher, certifier — trois outils, trois usages, et deux catastrophes d'école.

**Transition scriptée :** « Première décision d'architecte — celle que 153 millions de personnes auraient aimé qu'Adobe prenne correctement. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (où va votre mot de passe ?)

**Consigne :** Lancer le **📊 Sondage n°1** — comment un site doit-il conserver votre mot de passe ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse B : haché, salé, avec une fonction dédiée. Le piège, c'est A — "chiffré avec une clé bien protégée" SEMBLE sûr. Mais le chiffrement est réversible : qui détient la clé peut tout relire... et les clés finissent par fuiter. Le hachage, lui, est à sens unique : le site peut VÉRIFIER votre mot de passe sans jamais pouvoir le RELIRE. Cette distinction — chiffrer versus hacher — est LE fil rouge de la soirée. Et une grande entreprise a choisi A pour 153 millions de comptes... j'y reviens tout à l'heure. »

**Transition scriptée :** « Commençons par le chiffrement — avec un détour de deux mille ans. »

### 0:10–0:24 — Séquence 1 : Symétrique vs asymétrique

**Points de contenu à dérouler (support §1) :**
- **Échauffement (2 min) — 💬 le code de César :** afficher `FRPHEVGR` : *« message chiffré par décalage de 13 lettres — le premier qui tape le mot en clair dans le chat a gagné ! »* (réponse : SÉCURITÉ). Débrief : un algorithme (le décalage) + une clé (13) — toute la cryptographie tient dans ce couple ; seule la solidité mathématique a changé.
- **Symétrique (AES)** : une seule clé partagée — ultra-rapide, pour les gros volumes (le BitLocker de B08, c'est lui). L'analogie du coffre-fort à clé unique... et son problème : comment livrer la clé ?
- **Asymétrique (RSA, Diffie-Hellman)** : le couple publique/privée — l'analogie du cadenas ouvert : tout le monde peut fermer la boîte, seul le détenteur de la clé privée l'ouvre. Lent, mais il résout l'échange de clés et permet la signature.
- **L'hybride** : le handshake TLS de B07, désormais compris de l'intérieur — l'asymétrique livre la clé de session, la symétrique fait le travail.
- Question rhétorique : *« Laquelle des deux clés ne quitte JAMAIS son propriétaire ? »* — la privée, toujours. Tout l'édifice repose là-dessus.

**Transition scriptée :** « Deuxième outil — et attention : celui-ci ne chiffre RIEN. »

### 0:24–0:36 — Séquence 2 : Le hachage — intégrité & mots de passe

**Points de contenu à dérouler (support §2) :**
- Le hachage n'est **pas** du chiffrement : une empreinte de taille fixe, à sens unique — l'analogie de l'empreinte digitale.
- **Les 3 propriétés** : irréversible, résistant aux collisions, effet d'avalanche (une lettre change → tout change).
- *Usage n°1 — l'intégrité* : l'empreinte publiée par l'éditeur vs celle calculée localement.
- *Usage n°2 — les mots de passe* : jamais de clair, jamais de chiffrement — du hachage. Mais pas n'importe comment :
  - **Le sel** : une valeur aléatoire unique par utilisateur — sans lui, deux « linkedin123 » ont la même empreinte, et les **rainbow tables** cassent tout en masse.
  - **La lenteur volontaire** : SHA-256 est trop rapide face aux cartes graphiques (des milliards de tests/seconde) — d'où bcrypt, scrypt, **Argon2**.
  - **MD5 et SHA-1 sont cassés** — à bannir de tout nouvel usage.
- Question rhétorique : *« Pourquoi votre banque ne peut-elle pas vous renvoyer votre mot de passe "oublié" ? »* — parce qu'elle ne l'a jamais eu : elle n'en garde que l'empreinte. Si un site PEUT vous le renvoyer... méfiance (le mini-scénario y revient).

**Transition scriptée :** « Troisième outil : prouver QUI a écrit quoi — et qui garantit le cadenas de B07. »

### 0:36–0:44 — Séquence 3 : PKI, certificats & signature numérique

**Points de contenu à dérouler (support §3) :**
- Le problème de confiance : cette clé publique de `banque.com` est-elle bien celle de votre banque ?
- **L'AC** : le tiers de confiance qui vérifie l'identité puis signe le certificat.
- **Le certificat X.509** : la carte d'identité du serveur — clé publique, domaine, validité, identité de l'AC, signature (JAMAIS la clé privée).
- **La signature numérique**, mécanique dévoilée : hacher le document, chiffrer l'empreinte avec la clé PRIVÉE ; tout détenteur de la clé publique vérifie (déchiffre, recalcule, compare). Hachage + asymétrique = authenticité + intégrité.
- Boucler avec B07 : c'est ce que le navigateur vérifie à chaque cadenas — et DigiNotar a montré ce qui arrive quand le signataire ment.

**Transition scriptée :** « Passons au laboratoire : deux phrases, deux empreintes, trois votes. »

### 0:44–0:58 — Activité : Le laboratoire du hachage (Sondages n°2 à 4)

**Consigne :** Afficher les deux phrases et leurs empreintes SHA-256 (support, activité « Le laboratoire du hachage »), 30 secondes d'observation, puis lancer les **📊 Sondages n°2, 3, 4** (~4-5 min chacun : vote, débrief).

**🎙️ Verbatim de lancement :**
> « Deux phrases identiques au détail près : les accents. En dessous, leurs empreintes SHA-256. Observez-les trente secondes... Premier vote : combien de caractères ces empreintes ont-elles en commun ? »

**Débriefs scriptés (points obligatoires) :**
- N°2 (pratiquement aucun) : l'**effet d'avalanche** — aucune corrélation visible, impossible de deviner la nature de la modification. C'est ce qui rend l'empreinte fiable : tout changement, même d'un bit, se voit.
- N°3 (l'intégrité) : dérouler le scénario complet — le hash de référence publié en HTTPS, le fichier téléchargé (parfois via un miroir), `sha256sum` local, comparaison. Identique = ni corruption ni malware injecté.
- N°4 (le sens unique... nuancé) : inverser est impossible, mais **tester** est possible — hacher des millions de candidats (« azerty », « 123456 ») et comparer aux empreintes volées. C'est exactement le pont vers le sel et les fonctions lentes... et vers LinkedIn.

**Transition scriptée :** « Théorie validée. Voyons maintenant ce que coûte de la négliger — deux affaires, 270 millions de comptes à elles deux. »

### 0:58–1:08 — Chiffres clés & deux affaires réelles

**Chiffres (2 min, support §4) :** ~153 millions de comptes dans le fichier Adobe (2013) — chiffrés, pas hachés, indices en clair ; 117 millions d'identifiants LinkedIn en vente en 2016 (fuite 2012) — SHA-1 sans sel, majorité cassée en jours ; des milliards d'empreintes testées par seconde sur une seule carte graphique moderne.

**Cas n°1 — Adobe, 2013 (4 min, support §5) :** raconter : la base de ~153 millions de comptes diffusée ; les mots de passe **chiffrés** (même clé, mode produisant le même bloc pour la même entrée) au lieu d'être hachés ; conséquence : les mots de passe identiques se voient sans rien casser ; et les **indices** stockés en clair à côté (« prénom de ma fille », « pareil que gmail »)... La communauté l'a surnommée « la plus grande grille de mots croisés du monde » : l'indice de l'un révélait le mot de passe de millions d'autres. Leçon : chiffrer n'est pas hacher — et le sondage n°1 de ce soir était exactement ce choix.

**Cas n°2 — LinkedIn, 2012 (4 min, support §5) :** raconter : 6,5 millions d'empreintes sur un forum en 2012... puis la vérité en 2016 : **117 millions** d'identifiants en vente ; du SHA-1 **sans sel** — tous les « linkedin123 » partagent la même empreinte, les tables précalculées et les cartes graphiques font le reste en quelques jours ; et ces 117 millions de couples alimentent depuis le *credential stuffing* — « 23andMe, la semaine dernière : la boucle est bouclée. » Leçons : le sel rend chaque empreinte unique ; la lenteur de la fonction rend la force brute non rentable ; une fuite mal protégée nourrit les attaques pendant une décennie. Relance chat : *« Quel détail vous marque le plus ? »*

### 1:08–1:12 — Sondage n°5 : et vous, les checksums ?

**Consigne :** Lancer le **📊 Sondage n°5** (opinion) — vérifiez-vous les empreintes de vos téléchargements ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « C est la réponse la plus fréquente, et c'est normal — ce réflexe est surtout attendu des professionnels IT. Retenez deux choses : la vérification prend dix secondes — c'est votre travail en autonomie de la semaine — et c'est le SEUL moyen de détecter un installeur piégé en chemin. À défaut : toujours le site officiel, toujours en HTTPS. »

### 1:12–1:16 — 🤔 Mini-scénario : le « mot de passe oublié » qui répond

**Consigne :** Afficher le mini-scénario du support : le site livré par le prestataire renvoie votre mot de passe actuel en clair par e-mail. *« Tapez A, B ou C dans le chat. »*

**Débrief :** B — si le site peut vous RENVOYER votre mot de passe, il peut le RELIRE : stockage en clair ou chiffrement réversible, l'anti-modèle d'Adobe. Un site bien conçu ne connaît jamais votre mot de passe — d'où la seule procédure légitime : la **réinitialisation** par lien temporaire. C (chiffrer l'e-mail) déplace le problème sans le résoudre. Ce test à dix secondes révèle le sérieux d'un prestataire.

**Transition scriptée :** « Trois questions pour sceller les fondations. »

### 1:16–1:22 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : l'hybride = l'asymétrique livre la clé, la symétrique chiffre vite ; le sel = empreintes uniques, rainbow tables inopérantes ; le X.509 = clé publique + identité + signature de l'AC (jamais la clé privée). Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/B_S10_support.md).

### 1:22–1:26 — Exercice bonus (Sondage n°9) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°9** — la cause la plus courante d'une alerte « Connexion non sécurisée » ? Débrief : un certificat expiré ou signé par une AC non reconnue (B) — la chaîne de confiance PKI en action ; et la signature, vous savez désormais comment elle fonctionne (hachage + clé privée de l'AC). À couper en cas de retard.

### 1:26–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Trois outils, trois usages : on CHIFFRE ce qu'on devra relire, on HACHE — avec sel et fonction lente — ce qu'on doit seulement vérifier, on SIGNE ce dont il faut prouver l'origine. Adobe et LinkedIn ont confondu les outils : 270 millions de comptes. Vous, plus jamais. Un mot que vous retenez, dans le chat ! »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Self-paced : cours IBM SkillsBuild *"Cryptography Basics"* (~1h30) + l'expérience `sha256sum` dans un terminal + recherche IaaS/PaaS/SaaS avec un exemple de chaque — préparation directe de B11.
- Teaser B11 : « la semaine prochaine, vos données déménagent chez quelqu'un d'autre : le cloud. Qui est responsable de quoi ? Et l'histoire d'une seule configuration erronée qui a exposé 106 millions de dossiers bancaires. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**Exercice bonus n°9** (1:22–1:26) — il est dans le support en exercice bonus.
2. Compresser le code de César à 1 min (donner la réponse après 3 propositions).
3. Raccourcir le débrief du sondage n°5 à 1 min.
4. Ne JAMAIS couper : le laboratoire du hachage, les deux affaires, le quiz.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°3 : pourquoi un hachage salé aurait sauvé Adobe).
2. Démonstration en direct : `echo -n "Bonjour" | sha256sum` dans un terminal partagé, puis modifier une lettre — l'effet d'avalanche en temps réel.
3. Questions/réponses libres.

## Travail en autonomie (Self-paced)
* **Avant la session suivante (B11)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Cryptography Basics"* (durée estimée : 1h30).
  * **Activité pratique** : Dans un terminal, hacher un court texte (`echo -n "Bonjour" | sha256sum` sous Linux/macOS), modifier une lettre, recommencer — observer l'effet d'avalanche.
  * **Exercice de recherche** : Identifier la différence entre IaaS, PaaS et SaaS et donner un exemple de service connu pour chaque catégorie (ex. AWS EC2, Heroku, Google Workspace).
