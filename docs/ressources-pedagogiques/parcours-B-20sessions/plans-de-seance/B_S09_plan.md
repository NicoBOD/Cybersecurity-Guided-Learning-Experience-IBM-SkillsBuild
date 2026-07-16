# Plan de séance — Session B09 : Gestion des identités et des accès (IAM)
Parcours : B 20 sessions  |  Module : C — Identités, cloud & données  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (verbes d'action)
- **Distinguer** les quatre étapes clés de l'IAM : Identification, Authentification, Autorisation, Audit.
- **Comparer** les modèles de contrôle d'accès RBAC (rôles métier) et ABAC (attributs dynamiques).
- **Concevoir** une politique MFA et SSO adaptée aux besoins de sécurité et d'ergonomie d'une entreprise, intégrant le cycle de vie des identités (JML).

## Prérequis & progression
- **Prérequis** : Module B (Systèmes & réseaux).
- **Lien de progression** : Ouverture du module C — les murailles sont construites, reste à gérer QUI a les clés. B10 apportera les mécanismes cryptographiques qui sous-tendent ces identités (hachage des mots de passe, signatures).

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama B09 ([spécifications](../slides/B_S09_slides_spec.md)) — la matrice RBAC vide doit pouvoir être remplie à l'écran pendant l'activité.
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Premier vecteur d'accès initial des attaquants (DBIR) ? | A) Les identifiants volés ou réutilisés |
| 2 | 0:46 | Sondage | Matrice : les droits du Stagiaire_Marketing ? | B) N/N/N + lecture du portail |
| 3 | 0:50 | Sondage | Matrice : le Comptable et le dossier RH ? | B) Aucun accès |
| 4 | 0:54 | Sondage | Matrice : l'Admin_IT et la base factures ? | C) Aucun accès aux données métier |
| 5 | 1:08 | Sondage | Votre pratique des mots de passe ? | Opinion (pas de bonne réponse) |
| 6 | 1:16 | Sondage | Mot de passe + question secrète = MFA ? | B) Non : même catégorie |
| 7 | 1:18 | Sondage | Quelle règle relève de l'ABAC ? | C) Celle qui dépend de l'heure et du réseau |
| 8 | 1:20 | Sondage | L'avantage du SSO au départ d'un salarié ? | B) Révocation instantanée de tous les accès |
| 9 | Tampon | Sondage | Contrer la fatigue MFA ? | B) Activer le number matching |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil, ouverture du module C & retour self-paced | 💬 Chat : le SSO au quotidien |
| 0:04–0:10 | Brise-glace : comment entrent-ils vraiment ? | 📊 Sondage n°1 |
| 0:10–0:24 | Séquence 1 : Les 4 piliers de l'IAM & les facteurs | 💬 Chat : l'immeuble sécurisé |
| 0:24–0:34 | Séquence 2 : RBAC vs ABAC | Question rhétorique |
| 0:34–0:44 | Séquence 3 : SSO & cycle de vie des identités (JML) | Question rhétorique |
| 0:44–0:58 | Activité : La matrice RBAC de MedDistri | 📊 Sondages n°2, 3, 4 |
| 0:58–1:08 | Chiffres clés & affaires Uber + 23andMe | 💬 Chat : réactions |
| 1:08–1:12 | Et vous ? Les mots de passe | 📊 Sondage n°5 |
| 1:12–1:16 | Mini-scénario : la mutation interne | 🤔 Chat : A, B ou C |
| 1:16–1:22 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:22–1:26 | Exercice bonus : la fatigue MFA (tampon) | 📊 Sondage n°9 |
| 1:26–1:30 | Synthèse, devoirs & teaser B10 | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & ouverture du module C

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous, et bienvenue dans le module Identités, cloud et données ! Vos murailles sont construites — mais une question est restée ouverte la semaine dernière : qui a les clés ? Votre mission de la semaine : le SSO. Tapez dans le chat un service que vous utilisez avec un bouton "Se connecter avec Google" ou "avec Microsoft". »

**Points à dérouler :**
- Lire 3-4 exemples du chat : « vous utilisez déjà du SSO tous les jours — ce soir, vous comprendrez la machinerie derrière le bouton. »
- Rappel express de B08 : le durcissement, Colonial Pipeline et son compte dormant — « gardez ce compte en tête, il va revenir. »
- Annonce du programme : les 4 piliers de l'IAM, les modèles de droits, le SSO — et deux affaires récentes où l'identité fut la seule porte.

**Transition scriptée :** « Première question — et la réponse justifie tout le module. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (comment entrent-ils vraiment ?)

**Consigne :** Lancer le **📊 Sondage n°1** — le premier vecteur d'accès initial selon le Verizon DBIR. Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse A : les identifiants volés ou réutilisés — de l'ordre d'une violation sur cinq, en tête année après année (Verizon DBIR 2025). Retenez la formule : les attaquants ne piratent pas, ils SE CONNECTENT — avec de vrais mots de passe achetés, hameçonnés ou rejoués depuis d'anciennes fuites. Le périmètre de sécurité n'est plus la muraille : c'est l'identité. Voyons comment on la gère. »

**Transition scriptée :** « Tout système de contrôle d'accès répond à quatre questions. Les voici. »

### 0:10–0:24 — Séquence 1 : Les 4 piliers de l'IAM & les facteurs

**Points de contenu à dérouler (support §1) :**
- Dérouler l'**analogie de l'immeuble sécurisé** : *Identification* (« je suis Alice Martin ») → *Authentification* (le passeport) → *Autorisation* (le badge limité au 1er étage) → *Audit* (chaque passage enregistré).
- Vocabulaire pro : AuthN vs AuthZ — prouver qui l'on est ≠ décider ce que l'on peut faire.
- **Les 3 catégories de facteurs** : ce que l'on SAIT (mot de passe, PIN), ce que l'on POSSÈDE (téléphone, clé matérielle), ce que l'on EST (biométrie).
- **La règle du MFA** : au moins deux facteurs de catégories DIFFÉRENTES — deux mots de passe ne font pas un MFA.
- **Tous les MFA ne se valent pas** (bloc mentor) : SMS (fragile — SIM swapping) < application TOTP < push avec number matching < clé FIDO2/passkey (résistante à l'hameçonnage par conception). Rappel B04 : la MFA bloque plus de 99,9 % des attaques automatisées — encore faut-il bien la choisir.
- Relance chat (0:20) : *« Dans l'analogie de l'immeuble : le badge limité au 1er étage, c'est quel pilier ? »* — l'Autorisation.

**Transition scriptée :** « L'identité est prouvée. Reste à décider des droits — et il y a deux écoles. »

### 0:24–0:34 — Séquence 2 : RBAC vs ABAC

**Points de contenu à dérouler (support §2) :**
- **RBAC** : les droits suivent les **rôles métier** — on attribue aux rôles, on affecte les personnes aux rôles. Simple, auditable, idéal pour les structures stables.
- **ABAC** : la décision dépend d'**attributs** évalués à la volée — le sujet (rôle, habilitation), la ressource (sensibilité), l'environnement (heure, lieu, réseau).
- L'exemple canonique : *« le Comptable modifie les factures SEULEMENT aux heures de bureau ET depuis le réseau de l'entreprise »* — impossible à exprimer en RBAC pur.
- Question rhétorique : *« Pourquoi ne pas tout faire en ABAC, alors ? »* — complexité : chaque règle dynamique doit être écrite, testée, maintenue. En pratique : RBAC pour la structure, ABAC pour les ressources les plus sensibles.

**Transition scriptée :** « Troisième brique : un seul compte pour tout ouvrir — miracle ou catastrophe ? »

### 0:34–0:44 — Séquence 3 : SSO & cycle de vie des identités

**Points de contenu à dérouler (support §3) :**
- **Le SSO** : une authentification unique auprès d'un fournisseur d'identité (IdP), qui émet des preuves signées vers les applications — l'application ne voit jamais le mot de passe (protocoles SAML 2.0, OpenID Connect — le travail en autonomie).
- Les bénéfices : fin de la lassitude des mots de passe (la matière première du *credential stuffing*), et surtout la **révocation centralisée instantanée** au départ d'un salarié.
- **Le revers** : un point de défaillance unique — compte SSO compromis = tout compromis. Conséquence non négociable : MFA robuste + surveillance des connexions sur ce compte.
- **Le cycle JML** : *Joiner* (provisionner selon le rôle), *Mover* (LE maillon faible — retirer les anciens droits avant d'accorder les nouveaux, sinon « dérive des privilèges »), *Leaver* (tout révoquer, immédiatement — Colonial Pipeline, encore). La revue périodique des droits est le filet de sécurité.
- Question rhétorique : *« Qui, dans une entreprise, connaît TOUS les accès d'un salarié muté deux fois ? »* — sans IAM centralisé : personne. C'est le problème.

**Transition scriptée :** « À vous de jouer : MedDistri — dont vous avez sécurisé le réseau en B08 — vous confie ses droits d'accès. »

### 0:44–0:58 — Activité : La matrice RBAC de MedDistri (Sondages n°2 à 4)

**Consigne :** Afficher le contexte (support, activité « La matrice RBAC ») : 4 ressources (dossier candidats RH, base factures, console cloud, portail actualités) × 4 profils (RH_Manager, Comptable, Admin_IT, Stagiaire_Marketing), droits W/R/N. Lancer les **📊 Sondages n°2, 3, 4** (~4-5 min chacun : énoncé, vote, débrief), puis reconstituer la matrice complète à l'écran.

**🎙️ Verbatim de lancement :**
> « Vous êtes l'administrateur IAM de MedDistri. Chaque case de cette matrice est une décision de sécurité. Premier profil, le plus délicat : le stagiaire marketing. Quels droits ? »

**Débriefs scriptés (points obligatoires) :**
- N°2 (stagiaire → N/N/N + R actualités) : le réflexe « lecture partout pour apprendre » est la première cause de sur-attribution. Le besoin métier, rien que le besoin métier.
- N°3 (Comptable × dossier RH → N) : le piège est la justification plausible (« vérifier les salaires ») — presque tous les accès excessifs ont une bonne excuse. Le critère : le rôle l'exige-t-il ?
- N°4 (Admin_IT × factures → N) : LE piège de l'IAM — confondre administration technique et accès aux données. Gérer la console ≠ lire le contenu : c'est la **séparation des privilèges** ; un compte admin compromis ne doit pas livrer les données métier.
- **Reconstituer la matrice complète** (support) ligne par ligne, en verbalisant chaque justification.

**Transition scriptée :** « Cette rigueur a un coût ? Attendez de voir le coût de son absence — deux histoires, 2022 et 2023. »

### 0:58–1:08 — Chiffres clés & deux affaires réelles

**Chiffres (2 min, support §4) :** l'abus d'identifiants volés = premier vecteur d'accès initial, ~1 violation sur 5 (Verizon DBIR 2025) ; 23andMe : ~6,9 millions de personnes touchées à partir de ~14 000 comptes ; Uber 2022 : compromis en profondeur par un attaquant présenté comme mineur, sans le moindre exploit.

**Cas n°1 — Uber, 2022 (4 min, support §5) :** raconter la chaîne : les identifiants d'un prestataire achetés au marché noir → la MFA qui bloque → la **fatigue MFA** (notifications en rafale) → le message WhatsApp du faux support (« acceptez pour faire cesser les notifications ») → l'acceptation → le VPN → un script aux identifiants d'administration codés en dur → l'accès généralisé, jusqu'au Slack interne. Leçons : la faille du push est comportementale (parade : number matching — l'exercice bonus) ; l'ingénierie sociale (B04) et l'IAM se combinent ; les secrets codés en dur transforment un accès limité en compromission totale.

**Cas n°2 — 23andMe, 2023 (4 min, support §5) :** raconter : du *credential stuffing* — des couples e-mail/mot de passe issus d'anciennes fuites, rejoués en masse ; ~14 000 comptes cèdent (mots de passe recyclés)... et la fonction de mise en relation généalogique expose les données de ~6,9 millions de personnes ; la MFA rendue obligatoire après coup. Leçons : la fuite d'hier chez X est l'intrusion de demain chez Y ; dans un système interconnecté, votre négligence expose les autres. Relance chat : *« Quel détail vous marque le plus ? »*

### 1:08–1:12 — Sondage n°5 : et vous, les mots de passe ?

**Consigne :** Lancer le **📊 Sondage n°5** (opinion) — votre pratique actuelle des mots de passe ? Vote 60-90 s, rappeler que c'est anonyme.

**🎙️ Débrief scripté :**
> « Anonyme et sans jugement — B et C sont majoritaires partout. Le message n'est pas la culpabilité, c'est la mécanique : 23andMe vient de montrer qu'un mot de passe recyclé déjà fuité ailleurs suffit — personne n'a besoin de vous "pirater". La sortie par le haut tient en trois gestes : un gestionnaire de mots de passe, des mots de passe uniques, et la MFA partout — en commençant par votre messagerie, qui est la clé de récupération de tout le reste. »

### 1:12–1:16 — 🤔 Mini-scénario : la mutation interne

**Consigne :** Afficher le mini-scénario du support : la collaboratrice mutée de la comptabilité au marketing. *« Tapez A, B ou C dans le chat. »*

**Débrief :** B — le « M » du cycle JML, le moment le plus négligé : les droits s'ajoutent et ne se retirent jamais ; après trois mutations, un salarié cumule trois métiers de privilèges (la « dérive des privilèges »). Une passation, si nécessaire, se borne dans le temps et se trace. A crée le profil sur-privilégié dont rêvent les attaquants ; C punit l'activité. La revue périodique attrape ce que le quotidien laisse passer.

**Transition scriptée :** « Trois questions pour verrouiller le vocabulaire. »

### 1:16–1:22 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : mot de passe + question secrète = même catégorie, donc pas de MFA ; la règle dépendante de l'heure et du réseau = ABAC ; le SSO au départ = révocation instantanée centralisée. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/B_S09_support.md).

### 1:22–1:26 — Exercice bonus (Sondage n°9) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°9** — contrer la fatigue MFA ? Débrief : le **number matching** (B) — c'est exactement l'attaque qui a fait tomber Uber ; impossible d'accepter « par réflexe » quand il faut recopier un code que seul l'écran de connexion légitime affiche. La clé FIDO2 supprime même toute action à distance. Désactiver la MFA (A) est un contresens ; complexifier le mot de passe (C) ne change rien — l'attaquant l'a déjà. À couper en cas de retard.

### 1:26–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Ce soir : quatre piliers — s'identifier, le prouver, recevoir ses droits, être tracé ; une matrice — le besoin métier, rien que le besoin métier ; un compte unique — à protéger comme un coffre ; et deux affaires qui tiennent en une phrase : les attaquants ne piratent pas, ils se connectent. Un mot que vous retenez, dans le chat ! »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Self-paced : cours IBM SkillsBuild *"Identity and Access Management Fundamentals"* (~1h30) + recherche : le « sel cryptographique » (*salt*) et pourquoi il est indispensable au stockage des mots de passe — préparation directe de B10.
- Teaser B10 : « la semaine prochaine, la cryptographie : chiffrer, hacher, signer. Avec une histoire d'école : une grande entreprise a "chiffré" 153 millions de mots de passe au lieu de les hacher... et le monde entier a pu les lire comme une grille de mots croisés. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**Exercice bonus n°9** (1:22–1:26) — il est dans le support en exercice bonus.
2. Compresser la hiérarchie des MFA (séquence 1) au seul message « SMS < application < number matching < FIDO2 ».
3. Raccourcir le débrief du sondage n°5 à 1 min.
4. Ne JAMAIS couper : l'activité matrice RBAC, les deux affaires réelles, le quiz.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°3 : pourquoi Uber est tombé malgré la MFA).
2. Étendre la matrice MedDistri : ajouter un cinquième profil proposé par le chat (ex. prestataire de maintenance) et le faire voter.
3. Questions/réponses libres.

## Travail en autonomie (Self-paced)
* **Avant la session suivante (B10)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Identity and Access Management Fundamentals"* (durée estimée : 1h30).
  * **Recherche autonome** : Trouver la définition du terme « sel cryptographique » (*salt*) et comprendre pourquoi il est indispensable pour stocker des mots de passe en base de données.
