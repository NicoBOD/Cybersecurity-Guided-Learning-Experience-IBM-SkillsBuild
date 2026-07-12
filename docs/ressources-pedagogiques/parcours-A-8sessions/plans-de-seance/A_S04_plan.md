# Parcours A — Session 04 : Sécurité du cloud, des données & des identités
Module : Cloud, Données & Identités  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (4, verbes d'action)
- **Appliquer** le principe du moindre privilège lors de la définition de rôles et d'accès utilisateurs au sein d'une organisation.
- **Distinguer** la répartition des rôles de sécurité entre le client et le fournisseur dans le modèle de responsabilité partagée du *cloud*.
- **Expliquer** la différence entre le chiffrement des données au repos (*at rest*) et le chiffrement en transit (*in transit*), et l'apport du MFA (avec ses limites).
- **Concevoir** une politique de sauvegarde de données résiliente en appliquant de manière stricte la règle 3-2-1.

## Prérequis
- Sessions précédentes : A1, A2, A3.
- Self-paced AVANT la séance (~60 min) : Module SkillsBuild sur les bases du Cloud Computing (modèles IaaS, PaaS, SaaS) et les bases de la gestion des identités.

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **10 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama S04 ([spécifications](../slides/A_S04_slides_spec.md)) — y compris la matrice RBAC.
- [ ] Le [script de la Démo 4 — Identités : MFA & gestionnaire de mots de passe](../outils/A_scripts_demo.md#demo-4-identites) est relu ; les captures de secours sont prêtes.
- [ ] Le chat est ouvert ; un modérateur remonte les questions si possible.
- [ ] Un minuteur est visible du mentor.

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Part des attaques automatisées bloquées par le MFA ? | C) > 99,9 % |
| 2 | 0:27 | Sondage | Le commercial veut l'accès au dossier Salaires ? | B) Refuser, extraction RH |
| 3 | 0:31 | Sondage | Quel accès pour le stagiaire d'une semaine ? | B) Lecture ciblée, à expiration |
| 4 | 0:35 | Sondage | Le DG exige l'écriture partout ? | B) Strict besoin + pédagogie |
| 5 | 1:05 | Sondage | NAS connecté en permanence + ransomware : risque ? | B) Sauvegardes chiffrées aussi |
| 6 | 1:08 | Sondage | Parade dans la règle 3-2-1 ? | B) Copie immuable/déconnectée |
| 7 | 1:22 | Sondage | Principe des accès strictement nécessaires ? | A) Moindre privilège |
| 8 | 1:24 | Sondage | Pourquoi l'application d'authentification > SMS ? | B) SIM swapping |
| 9 | 1:26 | Sondage | Stockage cloud mal configuré : qui est responsable ? | B) Le client |
| 10 | Tampon | Sondage | Incendie + sauvegardes sur site : conséquence ? | B) Perte définitive |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil & retour sur Have I Been Pwned | Chat : réactions |
| 0:04–0:10 | Brise-glace : le chiffre du MFA | 📊 Sondage n°1 |
| 0:10–0:15 | La clé unique de l'immeuble | 💬 Chat : débat |
| 0:15–0:27 | Séquence 1 : IAM & moindre privilège | Question rhétorique |
| 0:27–0:39 | Activité : Le Gardien des Accès | 📊 Sondages n°2, 3, 4 |
| 0:39–0:49 | Séquence 2 : Le MFA en profondeur | Question rhétorique |
| 0:49–0:57 | Démo 4 : MFA & gestionnaire de mots de passe | Chat : réactions |
| 0:57–1:05 | Séquence 3 : Chiffrement & responsabilité partagée | 💬 Chat : locataire/propriétaire |
| 1:05–1:13 | Séquence 4 : Règle 3-2-1 & le NAS piégé | 📊 Sondages n°5, 6 |
| 1:13–1:22 | Chiffres & cas réels (OVHcloud, Capital One) | 🤔 Scénario « c'est dans le cloud » |
| 1:22–1:27 | Quiz de validation | 📊 Sondages n°7, 8, 9 |
| 1:27–1:30 | Synthèse, règle d'or & devoirs | Chat : « un réflexe retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & retour sur les devoirs

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous ! La semaine dernière, je vous avais demandé de vérifier vos adresses e-mail sur Have I Been Pwned. Sans donner de détails personnels : tapez simplement dans le chat "trouvé" si votre adresse apparaissait dans au moins une fuite, ou "rien" sinon. »

**Points à dérouler :**
- Commenter la proportion (généralement une majorité de « trouvé ») : « c'est normal, et c'est exactement le sujet du jour : vos identifiants circulent — comment faire en sorte que ça ne suffise plus à entrer ? »
- Pivot depuis A3 : « nous avons sécurisé les tuyaux ; aujourd'hui, on sécurise les clés, les coffres et les copies : identités, chiffrement, cloud, sauvegardes. »

**Transition scriptée :** « On commence par LE chiffre de la session. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (le chiffre du MFA)

**Consigne :** Lancer le **📊 Sondage n°1** — *« Selon Microsoft, quelle proportion des attaques automatisées de compromission de comptes le MFA bloque-t-il ? »* Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse C : plus de 99,9 %, selon l'étude de Microsoft publiée en 2019 et confirmée depuis. Deux précisions d'honnêteté intellectuelle : ce chiffre concerne les attaques AUTOMATISÉES — les robots qui testent des millions de mots de passe volés — et ce n'est pas 100 % : les attaques ciblées savent parfois contourner le MFA, on verra comment. Mais retenez l'essentiel : aucune autre mesure de sécurité n'offre un tel rapport protection/effort. Ceux qui ont tapé "trouvé" au chat tout à l'heure : avec le MFA activé, ces fuites ne suffisent plus à ouvrir vos comptes. »

**Transition scriptée :** « Avant les serrures, parlons des clés. Petite expérience de pensée immobilière. »

### 0:10–0:15 — 💬 La clé unique de l'immeuble

**Consigne :** Question chat — *« Vous gérez un immeuble de bureaux. Donneriez-vous le passe-partout — coffre-fort et locaux techniques compris — à tous les employés, y compris au stagiaire d'une semaine ? Pourquoi personne ne fait ça dans le monde physique... et pourquoi le fait-on si souvent en informatique ? Vos hypothèses dans le chat. »* Lire 3-4 réponses.

**🎙️ Formulation de synthèse :**
> « Vous avez trouvé : en informatique, donner tous les droits est INVISIBLE et IMMÉDIAT — pas de trousseau qui pèse, pas de serrurier à appeler. La facilité gagne, et chaque droit de trop est une porte de plus pour l'attaquant. La discipline qui corrige ça s'appelle l'IAM. »

### 0:15–0:27 — Séquence 1 : IAM & moindre privilège

**Points de contenu à dérouler (support §1) :**
- L'identité est le nouveau périmètre : la question n'est plus « êtes-vous dans le réseau ? » mais « qui êtes-vous et qu'avez-vous le droit de faire ? ».
- Authentification (qui suis-je ?) vs Autorisation (que puis-je faire ?) — deux étages distincts.
- Le **moindre privilège** : strict nécessaire, rien de plus. Double bénéfice : confinement de la compromission (rappel A3 : le déplacement latéral commence par un compte trop doté) et protection contre la maladresse.
- Le réflexe de l'attaquant : compte ordinaire (phishing d'A2) puis **escalade de privilèges** ; le moindre privilège transforme l'escalade en parcours du combattant.
- Le cycle de vie JML (Joiner-Mover-Leaver) : le « Leaver » oublié — le compte de l'ex-salarié encore actif — est le grand classique des audits.
- Présenter la **matrice RBAC** du support (Focus pratique) ligne par ligne, en insistant sur la ligne du DG : lecture large, écriture nulle part où ce n'est pas nécessaire.

**Question rhétorique (0:25) :** *« À votre avis, dans une PME de 50 personnes, combien ont des droits d'administrateur ? Et combien devraient en avoir ? »* — laisser 5 secondes : « souvent dix fois trop. Vous allez corriger ça vous-mêmes. »

### 0:27–0:39 — Activité : Le Gardien des Accès (Sondages n°2 à 4)

**Consigne :** Projeter la matrice RBAC (slide). Lancer les **📊 Sondages n°2, 3, 4** l'un après l'autre (~4 min par décision : 1 min de vote, 3 min de débrief). Scénarios, options et débriefs complets : voir le [support, section « Le Gardien des Accès »](../supports-md/A_S04_support.md).

**🎙️ Verbatim de lancement :**
> « Vous êtes l'administrateur des accès de cette PME. Trois demandes viennent d'arriver dans votre boîte, et les trois demandeurs ont d'excellents arguments. À vous de trancher — dans le respect du moindre privilège. Première demande : le commercial... »

**Débriefs scriptés (points obligatoires) :**
- N°2 : on répond au **besoin** (sa commission), pas à la **demande** (le dossier Salaires entier).
- N°3 : les trois mots magiques — **minimal, nominatif, temporaire** ; l'héritage des droits du tuteur est le péché originel des dérives d'accès.
- N°4 : le moindre privilège n'est pas une question de hiérarchie mais d'**exposition** — rappel A2 : c'est le DG qu'on usurpe (arnaque au président) ET son compte qu'on cible. Un bon DG comprend l'argument en 30 secondes.

**Transition scriptée :** « Les droits sont bien découpés. Reste à s'assurer que celui qui se connecte est bien celui qu'il prétend être. Place à la meilleure serrure du siècle. »

### 0:39–0:49 — Séquence 2 : Le MFA en profondeur

**Points de contenu à dérouler (support §1.B) :**
- Les 3 familles de facteurs : ce que je **sais** / ce que je **possède** / ce que je **suis** — le MFA combine deux natures différentes (deux mots de passe = toujours un seul facteur !).
- Pourquoi le mot de passe seul est mort : deviné, hameçonné, acheté en gros sur le dark web (reboucler avec Have I Been Pwned).
- Les limites, pour ne pas s'endormir : **SIM swapping** (le SMS détourné), **MFA fatigue** (le bombardement de notifications), hameçonnage du code en temps réel (rappel : la démo vishing d'A2 demandait exactement ce code).
- L'état de l'art : **passkeys / FIDO2** — la clé cryptographique est liée au site légitime ; un faux site n'obtient rien, même si l'utilisateur s'y laisse prendre. Hiérarchie à projeter : passkey/clé physique > application d'authentification > SMS > mot de passe seul.
- Nuancer sans décourager : **même le MFA par SMS vaut mille fois mieux que rien.** Priorités d'activation : messagerie, banque, comptes d'administration cloud.

**Question rhétorique (0:47) :** *« Pourquoi la messagerie d'abord ? »* — réponse : c'est la clé de toutes les autres serrures (réinitialisation de mots de passe).

### 0:49–0:57 — Démo 4 : MFA & gestionnaire de mots de passe

**Consigne :** Dérouler la [Démo 4 — Sécuriser une identité de A à Z](../outils/A_scripts_demo.md#demo-4-identites) en partage d'écran : vérification d'une adresse dans les fuites publiques, enrôlement d'une application TOTP (le QR code, le code qui tourne toutes les 30 secondes), et génération/remplissage d'un mot de passe fort par un gestionnaire. Tout est réalisé sur des comptes de démonstration.

**Points de débrief obligatoires :**
- Le code TOTP est généré localement — rien ne transite par SMS, rien à détourner.
- Le gestionnaire de mots de passe résout l'équation impossible « unique + long + mémorisable » : l'humain retient UN mot de passe maître, la machine retient le reste.
- Faire réagir le chat : *« qui utilise déjà un gestionnaire de mots de passe ? »* — valoriser, et renvoyer au self-paced (l'installer soi-même).
- En cas de pépin technique : dérouler avec les captures d'écran de secours du script.

**Transition scriptée :** « Identités verrouillées. Maintenant, protégeons la donnée elle-même — pendant qu'elle voyage, et pendant qu'elle dort. »

### 0:57–1:05 — Séquence 3 : Chiffrement & responsabilité partagée

**Points de contenu à dérouler (support §2 et §3) :**
- **En transit** vs **au repos** : l'enveloppe pendant le voyage (TLS, vu en A3) vs le coffre-fort à l'arrivée (BitLocker/FileVault). Il faut les deux : une lettre blindée dans une boîte ouverte ne protège rien. Rappel du consultant d'A1 : son portable volé était illisible.
- Le modèle de **responsabilité partagée** : le fournisseur sécurise LE cloud (bâtiments, serveurs, hyperviseurs), le client sécurise DANS le cloud (identités, accès, configurations, données). La frontière glisse selon IaaS/PaaS/SaaS — mais identités, accès et données restent TOUJOURS au client.
- Les deux idées reçues à enterrer : « c'est dans le cloud donc c'est sécurisé » et « c'est dans le cloud donc c'est sauvegardé ».

**Interaction (1:03) — 💬 Question chat :**
> « L'analogie du locataire : le propriétaire assure les murs et la porte de l'immeuble. Citez dans le chat UNE chose qui reste à la charge du locataire. » — lire 3-4 réponses (serrure, fenêtres, qui entre, assurance...) et conclure : « l'assurance habitation, on y revient dans deux minutes : c'est la sauvegarde. »

### 1:05–1:13 — Séquence 4 : La règle 3-2-1 & le NAS piégé (Sondages n°5 et 6)

**Points de contenu à dérouler (support §4) :**
- La règle : **3** copies, **2** supports, **1** hors site — dérouler chaque chiffre avec son scénario de panne.
- Les compléments modernes : copie **immuable** ou **déconnectée** (les ransomwares chiffrent les sauvegardes joignables EN PRIORITÉ) ; et la règle « 0 » : une sauvegarde jamais testée en restauration n'est pas une sauvegarde, c'est un espoir.

**Interaction :** Lancer les **📊 Sondages n°5 puis 6** (le NAS connecté en permanence + ransomware du week-end ; puis la parade). Débriefs dans le [support, « Le NAS piégé »](../supports-md/A_S04_support.md) — relier au déplacement latéral d'A3 : un NAS joignable depuis le réseau compromis fait partie du réseau compromis.

**Transition scriptée :** « Tout cela peut sembler théorique. Deux histoires vraies — un incendie et une banque — vont le rendre très concret. »

### 1:13–1:22 — Chiffres & cas réels

**Chiffres (2 min, support §5) :** re-projeter le 99,9 % (Microsoft) ; les identifiants volés = l'un des tout premiers vecteurs d'accès initial (Verizon DBIR 2025) — « l'attaquant moderne ne pirate pas, il se connecte » ; annoncer les deux cas.

**Cas n°1 — OVHcloud, 2021 (3 min, support §6) :** raconter : nuit du 9 au 10 mars 2021, incendie à Strasbourg, le bâtiment SBG2 intégralement détruit, des centaines de milliers de sites hors ligne. Pour la plupart : quelques heures ou jours d'interruption. Pour certains : perte DÉFINITIVE — leurs « sauvegardes » étaient dans le même bâtiment. Punchline : « ni piratage, ni fraude : un incendie. Le "1 hors site" de la règle 3-2-1 signifie VRAIMENT hors site. » Et la leçon responsabilité partagée : la sauvegarde des données reste au client, sauf service explicitement souscrit.

**Cas n°2 — Capital One, 2019 (3 min, support §6) :** raconter : une banque réputée mature en cloud ; une mauvaise configuration du pare-feu applicatif exploitée (requêtes internes SSRF), des identifiants temporaires TROP privilégiés récupérés, ~106 millions de clients touchés ; 80 M$ d'amende + 190 M$ d'indemnisation. Punchline : « ce n'est pas le cloud qui a failli, c'est la configuration du client — et un défaut de moindre privilège : le rôle compromis ouvrait la salle des coffres au lieu d'un placard. » Relier à l'activité Gardien des Accès.

**Interaction (1:20) — 🤔 Scénario (chat) :** dérouler le mini-scénario du support (« pas besoin de sauvegarde, c'est dans le cloud, c'est répliqué ») — voter A/B/C dans le chat ; débrief : B — la réplication synchronise tout, y compris les suppressions et les fichiers chiffrés par ransomware.

### 1:22–1:27 — Quiz de validation (Sondages n°7 à 9)

**Consigne :** Lancer les **📊 Sondages n°7, 8, 9** à la suite (~90 s chacun). Réponses : moindre privilège ; SIM swapping ; le client. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/A_S04_support.md).

### 1:27–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Quatre réflexes à emporter : le MOINDRE PRIVILÈGE — minimal, nominatif, temporaire ; le MFA PARTOUT — la meilleure serrure du siècle, 99,9 % des attaques automatisées bloquées ; la RESPONSABILITÉ PARTAGÉE — la serrure de votre porte, c'est vous ; et le 3-2-1 — dont une copie vraiment hors site, immuable, et TESTÉE. L'incendie de Strasbourg et Capital One : deux rappels que tout ceci est très concret. Tapez dans le chat le réflexe que vous retenez. »

**Points de clôture :**
- Lire 4-5 réflexes dans le chat ; féliciter : mi-parcours atteint !
- Devoirs : module IBM SkillsBuild *Introduction à la GRC et à la conformité réglementaire* (~60 min) + exercice personnel : installer un gestionnaire de mots de passe et activer le MFA sur sa messagerie personnelle.
- Teaser A5 : « la semaine prochaine, on prend de la hauteur : gouvernance, gestion des risques, RGPD — qui décide, qui paie, et que dit la loi. Indice : une amende record à 9 chiffres sera au programme. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Compresser la séquence 3 (0:57–1:05) : l'analogie du locataire en 3 min, sans la question chat.
2. Compresser Capital One à 90 secondes (chiffre + punchline moindre privilège).
3. Ne JAMAIS couper : le Gardien des Accès, la démo 4, le NAS piégé (n°5-6), OVHcloud.
4. Le **📊 Sondage n°10** (bonus incendie) est le tampon officiel : en autonomie si besoin.

**Si vous êtes en avance :**
1. Lancer le **📊 Sondage n°10** (bonus : l'incendie et les deux disques sur site) — écho direct au cas OVHcloud.
2. Dérouler les **Questions de réflexion** du support (notamment la n°3 : convaincre des équipes réticentes au MFA — excellent débat de chat).
3. Ouvrir une séquence questions/réponses libre.

## Articulation avec l'atelier de fin de parcours
- Cette session apporte la dimension "Identité & Données" de l'Atelier d'Audit Interactif MedDistri. Les notions de MFA, de moindre privilège et de règle de sauvegarde 3-2-1 y sont testées lors des choix décisionnels.

## Self-paced APRÈS la séance (~90 min) & évaluation formative
- Suivre le module sur la gestion des identités, le contrôle des accès dans les infrastructures cloud et la protection des données.
- Configurer à titre d'exercice d'application personnelle un gestionnaire de mots de passe gratuit et activer la MFA sur l'un de ses comptes personnels (messagerie en priorité).
- Quiz d'auto-évaluation en ligne (10 questions de type scénarios sur la cryptographie de base, le cloud et la sauvegarde).
