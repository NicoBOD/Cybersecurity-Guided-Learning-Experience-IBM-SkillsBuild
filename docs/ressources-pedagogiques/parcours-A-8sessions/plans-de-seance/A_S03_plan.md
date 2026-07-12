# Parcours A — Session 03 : Sécurité des systèmes & réseaux
Module : Réseaux & Systèmes  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (4, verbes d'action)
- **Expliquer** le rôle de filtrage d'un pare-feu (*firewall*) et son utilité pour bloquer les connexions non autorisées.
- **Identifier** les cas d'usage d'un réseau privé virtuel (VPN) pour sécuriser la confidentialité des communications sur Internet.
- **Distinguer** le trafic chiffré (HTTPS, SSH) du trafic non chiffré (HTTP, Telnet) et expliquer le risque d'interception (*sniffing*).
- **Proposer** un plan de segmentation réseau simple (LAN, Wi-Fi Invités, Zone Démilitarisée - DMZ) pour isoler les composants critiques d'une entreprise.

## Prérequis
- Sessions précédentes : A1, A2.
- Self-paced AVANT la séance (~90 min) : Module SkillsBuild sur les bases du fonctionnement d'Internet (adresses IP, ports, notion de routeur et de commutateur/switch).

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama S03 ([spécifications](../slides/A_S03_slides_spec.md)) — y compris le schéma du réseau plat de l'activité et l'architecture cible.
- [ ] Le [script de la Démo 3 — Audit de règles de pare-feu](../outils/A_scripts_demo.md#demo-3-firewall) est relu ; la table de règles est prête à projeter.
- [ ] Le chat est ouvert ; un modérateur remonte les questions si possible.
- [ ] Un minuteur est visible du mentor.

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Délai avant les premières attaques sur un serveur exposé ? | A) Quelques minutes |
| 2 | 0:32 | Sondage | Wi-Fi d'hôtel + HTTPS : le gérant lit-il votre mot de passe ? | B) Non (contenu chiffré) |
| 3 | 0:45 | Sondage | Téléphone infecté sur réseau plat : risque principal ? | B) Déplacement latéral |
| 4 | 0:49 | Sondage | Où placer le serveur web public ? | B) En DMZ |
| 5 | 0:53 | Sondage | Quelle règle pour le Wi-Fi invités ? | A) Internet seul, zéro accès interne |
| 6 | 1:17 | Sondage | Règle de base du moindre privilège sur un pare-feu ? | B) Default Deny |
| 7 | 1:19 | Sondage | Le VPN empêche-t-il de télécharger un virus ? | B) Non |
| 8 | 1:21 | Sondage | Cadenas HTTPS = site de confiance ? | B) Faux |
| 9 | Tampon | Sondage | Serveur DMZ compromis : qu'est-ce qui protège le LAN ? | B) La règle DMZ→LAN bloquée |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil & retour sur les devoirs d'A2 | Chat : indices de phishing trouvés |
| 0:04–0:10 | Brise-glace : le serveur-appât | 📊 Sondage n°1 |
| 0:10–0:15 | La carte postale : comment circule l'info | 💬 Chat : « qui peut la lire ? » |
| 0:15–0:26 | Séquence 1 : Le pare-feu & la table de filtrage | Question rhétorique |
| 0:26–0:37 | Séquence 2 : VPN & HTTPS/TLS | 📊 Sondage n°2 |
| 0:37–0:45 | Séquence 3 : Segmentation, VLAN & DMZ | Question rhétorique |
| 0:45–0:59 | Activité : L'Architecte Réseau | 📊 Sondages n°3, 4, 5 |
| 0:59–1:07 | Démo 3 : Audit de règles de pare-feu | Chat : prédictions |
| 1:07–1:17 | Séquence 4 : Chiffres & cas réels (Target, Mirai/Dyn) | 💬 Chat : « qui aurait dû bloquer ? » |
| 1:17–1:23 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:23–1:27 | Bonus : Confinement DMZ (tampon) | 📊 Sondage n°9 |
| 1:27–1:30 | Synthèse, règle d'or & devoirs | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & retour sur les devoirs

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous ! Avant d'attaquer : la semaine dernière je vous avais demandé de traquer 3 indices de phishing dans vos propres boîtes mail. Qui a trouvé un spécimen intéressant ? Décrivez-le en une phrase dans le chat. »

**Points à dérouler :**
- Lire 2-3 trouvailles, féliciter, rappeler la règle d'or d'A2 (canal alternatif initié par soi).
- Pivot : « A2 = l'attaquant vous manipule pour entrer. Aujourd'hui : les remparts techniques qui limitent les dégâts quand quelqu'un a quand même cliqué. Pare-feu, VPN, HTTPS, segmentation — le système immunitaire du réseau. »

**Transition scriptée :** « Première question, et elle va calmer ceux qui pensent qu'on est trop petits pour intéresser les pirates. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (le serveur-appât)

**Consigne :** Lancer le **📊 Sondage n°1** — *« Vous branchez un serveur tout neuf sur Internet, sans protection. Combien de temps avant les premières tentatives de connexion malveillantes ? »* Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse A : quelques minutes — parfois quelques secondes. On le sait grâce aux "pots de miel", des machines-appâts que les chercheurs branchent exprès pour observer. Internet est balayé en permanence par des robots. Souvenez-vous de la session A1 : l'attaquant ne vous choisit pas, il teste TOUT ce qui est branché. Celui qui a voté D — "seulement si on est ciblé" — vient de comprendre pourquoi cette session existe. »

**Transition scriptée :** « Avant de construire les remparts, il faut comprendre ce qui circule. Petite expérience de pensée postale. »

### 0:10–0:15 — 💬 La carte postale

**Consigne :** Question chat — *« Vous envoyez une carte postale sans enveloppe avec un secret écrit au dos. Qui peut la lire pendant le voyage ? Listez dans le chat. »* Lire les réponses (facteur, trieur, voisin, concierge...).

**🎙️ Formulation de synthèse :**
> « Tout le monde, donc. Eh bien le protocole HTTP, c'est exactement ça : vos mots de passe voyagent au dos d'une carte postale. HTTPS, c'est la même carte... dans une enveloppe blindée. Et le VPN, on va le voir, c'est carrément un convoyeur privé. Gardez cette image, toute la session tient dedans. »

### 0:15–0:26 — Séquence 1 : Le pare-feu

**Points de contenu à dérouler (support §1 + Focus pratique) :**
- Le douanier à la frontière : chaque paquet inspecté → Autoriser ou Bloquer.
- Les 3 critères : IP source/destination, protocole (TCP/UDP/ICMP), port. Métaphore des ports = portes numérotées de l'immeuble (443 = l'entrée visiteurs sécurisée, 22 = l'entrée technicien).
- **Dérouler la table de filtrage du support ligne par ligne** (règles 1 à 4) : lecture de haut en bas, première correspondance gagne, dernière ligne = tout bloquer.
- Marteler le principe : **Default Deny** — on autorise le nécessaire, on n'énumère jamais le mal (la liste serait infinie). Le portier de soirée : pas sur la liste, pas d'entrée.

**Question rhétorique (0:24) :** *« Pourquoi ne pas faire l'inverse : tout autoriser et bloquer les méchants connus ? »* — laisser 5 secondes : « parce que les méchants inconnus d'aujourd'hui sont plus nombreux que les méchants connus d'hier. »

**Transition scriptée :** « Le pare-feu filtre qui entre. Mais que fait-on quand nos données doivent SORTIR et traverser des réseaux qu'on ne contrôle pas — le Wi-Fi d'un hôtel, par exemple ? »

### 0:26–0:37 — Séquence 2 : VPN & HTTPS

**Points de contenu à dérouler (support §2 et §3) :**
- Le problème du Wi-Fi public : n'importe qui sur le même réseau peut écouter (*sniffing* = écoute passive ; à distinguer du *Man-in-the-Middle* = interposition active qui peut modifier les échanges).
- Le VPN : tunnel chiffré poste ↔ passerelle d'entreprise ; les intermédiaires ne voient qu'un flux illisible. Cas d'usage : télétravail, déplacement.
- Les 2 limites anti-faux-sentiment-de-sécurité : le tunnel protège le transport, pas le contenu (un malware voyage très bien chiffré) ; et la passerelle VPN elle-même doit être mise à jour (teaser de la séquence chiffres : c'est un vecteur d'intrusion majeur).
- HTTPS/TLS : le chiffrement de la navigation ; le certificat qui authentifie le site. Point de rigueur : on dit « SSL » par habitude, le protocole moderne est TLS (SSL est déprécié).

**Interaction (0:32) :** Lancer le **📊 Sondage n°2** — le Wi-Fi de l'hôtel (le gérant peut-il lire votre mot de passe bancaire en HTTPS ?).

**🎙️ Débrief scripté :**
> « Réponse B — mais avec une subtilité qui vaut de l'or : le gérant ne peut pas lire CE que vous échangez, mais il voit QUE vous parlez à votre banque. Contenu chiffré, métadonnées visibles. C'est ce que le VPN ajoute : il masque aussi la destination. Et attention au piège inverse : le cadenas HTTPS signifie "conversation privée", pas "interlocuteur honnête" — un site de phishing obtient son cadenas gratuitement en cinq minutes. Souvenez-vous de la chasse au phishing d'A2. »

**Transition scriptée :** « Filtrer, chiffrer... il reste le troisième pilier : cloisonner. Et pour comprendre pourquoi, imaginez une maison sans aucune porte intérieure. »

### 0:37–0:45 — Séquence 3 : Segmentation, VLAN & DMZ

**Points de contenu à dérouler (support §4) :**
- Le réseau plat = maison sans portes intérieures : un poste infecté à l'accueil, et le malware se promène jusqu'à la comptabilité. Nommer le concept : **déplacement latéral**.
- Les 3 zones types : LAN interne / Wi-Fi invités / DMZ. L'analogie de l'immeuble : guichet d'accueil (pare-feu), salle d'attente aux portes blindées (DMZ), badges par étage (VLAN).
- La règle d'or DMZ : interrogeable depuis Internet, mais interdite d'initier des connexions vers le LAN (règle 3 de la table).
- Relier à A1 : la segmentation est la défense en profondeur version réseau — chaque zone peut tomber sans entraîner les autres, comme des portes coupe-feu.

**Question rhétorique (0:43) :** *« Dans votre entreprise, le Wi-Fi des visiteurs mène-t-il quelque part ? En êtes-vous sûr ? »* — laisser planer, ne pas répondre : « vous allez le décider vous-mêmes, tout de suite. »

### 0:45–0:59 — Activité : L'Architecte Réseau (Sondages n°3 à 5)

**Consigne :** Projeter le schéma du réseau plat de la PME fictive (slide 8). Lancer les **📊 Sondages n°3, 4, 5** l'un après l'autre (~4-5 min par décision : 1 min de vote, 3 min de débrief). Scénarios, options et débriefs complets : voir le [support, section « L'Architecte Réseau »](../supports-md/A_S03_support.md).

**🎙️ Verbatim de lancement :**
> « Voici le réseau d'une PME bien réelle dans son genre : tout le monde sur le même réseau — les postes de bureau, le serveur web public, la compta... et la borne Wi-Fi des clients. C'est une catastrophe annoncée, et vous êtes l'architecte appelé à la rescousse. Trois décisions, trois votes. Première décision... »

**Débriefs scriptés (points obligatoires) :**
- N°3 (téléphone infecté) : introduire le déplacement latéral en pratique ; teaser : « retenez ce mot — le cas réel de tout à l'heure, c'est ça, à 200 millions de dollars. »
- N°4 (serveur web) : la DMZ-sas ; rejouer la règle 3 de la table de filtrage à l'écran.
- N°5 (Wi-Fi invités) : « c'est pratique » = l'ennemi de la segmentation ; un réseau d'inconnus se traite comme Internet.
- Conclusion : afficher l'architecture cible (slide) — « trois votes, et vous venez de faire le travail d'un architecte sécurité. »

### 0:59–1:07 — Démo 3 : Audit de règles de pare-feu

**Consigne :** Dérouler la [Démo 3 — Audit et logique de filtrage](../outils/A_scripts_demo.md#demo-3-firewall) en partage d'écran : projeter la table de règles, la lire de haut en bas, puis poser la question piège.

**🎙️ Question centrale de la démo :**
> « Que se passe-t-il si j'inverse la règle "Internet → Serveur Web : AUTORISER" et la règle "Internet → LAN : TOUT BLOQUER" ? Vos prédictions dans le chat ! »

**Points de débrief obligatoires :**
- Révéler : le site web public devient inaccessible — la règle de blocage, placée avant, capte tout le trafic entrant : **l'ordre des règles est aussi important que les règles elles-mêmes**.
- Rappeler : première correspondance gagne, lecture de haut en bas, Default Deny en dernière ligne.
- En cas de pépin technique : la table est dans le support (Focus pratique), la démo se raconte.

**Transition scriptée :** « Vous savez maintenant lire une table de filtrage. Voyons ce qui arrive aux entreprises qui ont négligé tout ce qu'on vient de voir — deux histoires vraies. »

### 1:07–1:17 — Séquence 4 : Chiffres & cas réels

**Chiffres (2 min, support §5) :** rappeler le sondage n°1 (quelques minutes) ; l'ANSSI observe que l'exploitation des équipements de bordure exposés (passerelles VPN, pare-feux) figure parmi les premiers vecteurs d'intrusion (Panorama 2024) — « l'ironie : la porte blindée mal entretenue devient LA porte d'entrée » ; annoncer les deux cas.

**Cas n°1 — Target, 2013 (4-5 min, support §6) :** raconter : les fêtes de fin d'année, ~40 millions de cartes bancaires volées ; point d'entrée = les identifiants d'un prestataire de chauffage-climatisation ; déplacement latéral jusqu'aux caisses faute de segmentation ; plus de 200 M$ de coûts, PDG et DSI partis. Punchline : « le climatiseur a coûté 200 millions de dollars. » Relier explicitement aux 3 votes de l'activité.

**Cas n°2 — Mirai/Dyn, 2016 (3 min, support §6) :** raconter : un ver qui teste les mots de passe d'usine sur les objets connectés ; des centaines de milliers de caméras enrôlées ; DDoS ~1 Tbit/s contre OVH puis contre le fournisseur DNS Dyn → Twitter, Netflix, Spotify inaccessibles des heures durant. Punchline : « des caméras à 40 € ont mis à genoux une partie du web mondial. » Relier au brise-glace (le balayage permanent) et à la Disponibilité (triade d'A1).

**Interaction (1:15) — 💬 Question chat :** *« Chez Target, QUI ou QUOI aurait dû empêcher le déplacement latéral entre l'accès prestataire et les caisses ? »* — lire 3-4 réponses ; conclure : la règle 3 de notre table, un pare-feu interne entre zones — « la technologie existait ; c'est l'architecture qui a manqué. »

### 1:17–1:23 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : Default Deny ; Non (le VPN protège le transport, pas le contenu) ; Faux (le cadenas ≠ confiance). Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/A_S03_support.md).

### 1:23–1:27 — Bonus : Confinement DMZ (Sondage n°9) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°9** — le serveur DMZ compromis (qu'est-ce qui protège la comptabilité ?). Débrief : la règle DMZ→LAN bloquée ; même compromis, le serveur est en cage. À couper en cas de retard (l'exercice reste dans le support en bonus).

### 1:27–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Votre réseau a désormais trois réflexes : FILTRER — tout ce qui n'est pas autorisé est interdit ; CHIFFRER — HTTPS et VPN, la carte postale sous enveloppe blindée ; CLOISONNER — chaque zone peut tomber sans entraîner les autres. Target a ignoré le troisième : 200 millions de dollars. Tapez dans le chat le mot que vous retenez de la session. »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Devoirs : module IBM SkillsBuild *Principes de la sécurité des identités et du cloud* (~75 min) + vérifier si son adresse e-mail apparaît dans des fuites connues (site *Have I Been Pwned*) — « préparation directe de la session A4 sur les identités. »
- Teaser A4 : « la semaine prochaine : le cloud, vos données, vos identités — et pourquoi le MFA est la meilleure serrure du siècle. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper le **Bonus n°9** (1:23–1:27) — il est dans le support en exercice bonus.
2. Compresser la carte postale (0:10–0:15) à 3 min (2 réponses lues au lieu de 5).
3. Compresser Mirai/Dyn à 90 secondes (chiffre + punchline) — mais ne JAMAIS couper Target, l'activité Architecte ni la démo.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°3 : qui est responsable des mots de passe d'usine ? — excellent débat de chat).
2. Approfondir la démo 3 : écrire en direct une règle supplémentaire proposée par le chat (ex. autoriser SSH depuis une seule IP d'administration).
3. Ouvrir une séquence questions/réponses libre.

## Articulation avec l'atelier de fin de parcours
- Les concepts de cette session fournissent la base réseau de l'Atelier d'Audit Interactif MedDistri. Les apprenants y décident de la meilleure architecture de filtrage et de segmentation à adopter pour isoler les serveurs.

## Self-paced APRÈS la séance (~90 min) & évaluation formative
- Suivre le module d'auto-formation sur la sécurité des réseaux (pare-feux et VPN).
- Réaliser le lab pratique virtuel d'écriture de règles de pare-feu élémentaires (autoriser/bloquer un port).
- Auto-évaluation (10 questions sur les protocoles, les ports par défaut et les principes de filtrage).
