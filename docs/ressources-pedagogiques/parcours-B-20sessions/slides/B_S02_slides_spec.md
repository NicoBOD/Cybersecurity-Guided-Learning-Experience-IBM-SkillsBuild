# Spécifications des slides — Session B02 : Paysage des menaces & acteurs
Parcours : B 20 sessions  |  Module : A — Fondations  |  Format : Spécifications Markdown

> **Principe** : le texte affiché reste minimal (mots-clés, chiffres, schémas) ; le contenu riche est dans les notes orateur et le [plan de séance minuté](../plans-de-seance/B_S02_plan.md). Toutes les interactions passent par les sondages et le chat Livestorm.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Paysage des menaces & acteurs
  - Qui nous attaque, et pourquoi ?
  - Parcours B — Session B02
- **Notes orateur** : Accueillir, se présenter, faire écrire dans le chat le retour sur le module self-paced (fait / en cours / pas encore). Rappel express de B01 : la triade C-I-D et les deux cas français. Annonce : ce soir on change de camp — on étudie l'adversaire, jusqu'à un braquage de banque à 81 millions de dollars.
- **Visuel suggéré** : Fond sombre avec une illustration stylisée montrant des silhouettes floues devant des écrans de contrôle.
  - **alt-text** : Silhouettes floutées d'acteurs de menace devant des écrans rétroéclairés de serveurs informatiques.
- **Élément interactif** : Chat d'accueil — retour sur le travail en autonomie.

---

### Slide 2 — Objectifs & agenda
- **Type** : contenu
- **Points clés (bullets)** :
  - Catégoriser les 4 profils d'attaquants et leurs motivations.
  - Expliquer l'économie du cybercrime (Ransomware-as-a-Service).
  - Découvrir la veille sur les menaces (CTI, CERT-FR, MITRE ATT&CK).
  - Agenda : typologie → économie RaaS → activité « Fiche d'identité » → 2 affaires réelles → CTI → quiz.
- **Notes orateur** : Nous allons casser certains clichés sur le « hacker », analyser le modèle économique de la cybercriminalité moderne, puis remplir ensemble — par sondages — la fiche d'identité d'un groupe d'attaquants bien réel.
- **Visuel suggéré** : Deux colonnes claires séparant les objectifs opérationnels et l'agenda de la séance.
  - **alt-text** : Tableau présentant les objectifs d'apprentissage à gauche et les étapes de la séance à droite.

---

### Slide 3 — Brise-glace : qui sont les premières victimes ?
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **Sondage n°1** : Selon l'ANSSI, qui sont les premières victimes des rançongiciels en France ?
  - A) Les multinationales du CAC 40 — B) Les ministères — C) Les TPE/PME/ETI et collectivités
- **Notes orateur** : Lancer le sondage n°1 (60-90 s). Réponse C (ANSSI, Panorama de la cybermenace 2024) : les structures qui se croient « trop petites pour intéresser les pirates » sont précisément les plus touchées, car la majorité des attaquants sont des opportunistes — ils attaquent ce qui est mal fermé, pas ce qui est prestigieux.
- **Visuel suggéré** : Pictogrammes contrastés : un gratte-ciel barré face à une rangée de petites boutiques et une mairie mises en évidence.
  - **alt-text** : Illustration opposant un grand siège social barré à des petites entreprises et une mairie ciblées par des flèches.
- **Élément interactif** : 📊 Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — Le portrait-robot du pirate
- **Type** : question chat
- **Points clés (bullets)** :
  - 💬 « Décrivez en UN mot le cyberattaquant tel que vous l'imaginez. »
  - Capuche ? Génie ? Adolescent ? Solitaire ?
- **Notes orateur** : Lire 5-6 mots du chat et regrouper les clichés. Synthèse : l'image du cinéma (capuche, génie solitaire) est fausse — la réalité est une industrie organisée, avec horaires de bureau et « service client ». Le cliché le plus dangereux est « génie » : la plupart des attaques réussissent par des moyens banals contre des cibles mal protégées.
- **Visuel suggéré** : Silhouette à capuche dessinée à la craie, entourée de points d'interrogation, qui se fissure pour laisser apparaître un open space de bureau ordinaire.
  - **alt-text** : Silhouette stéréotypée de pirate à capuche se fissurant et révélant un bureau d'entreprise banal derrière elle.
- **Élément interactif** : 💬 Question chat — un mot pour décrire l'attaquant.

---

### Slide 5 — Les quatre familles d'attaquants
- **Type** : schéma
- **Points clés (bullets)** :
  - **Cybercriminels** : le gain financier — les opportunistes du volume.
  - **États-nations (APT)** : espionnage, sabotage — ressources quasi illimitées.
  - **Hacktivistes** : idéologie — DDoS et défiguration pour la visibilité.
  - **Menaces internes** : malveillance ou négligence — déjà à l'intérieur.
  - (+ les *script kiddies* : peu doués, mais nombreux.)
- **Notes orateur** : Dérouler les quatre profils avec les analogies du support : le voleur de rue, l'espion/commando, le manifestant, le garde corrompu — et le gamin qui teste les poignées de portes. Expliquer chaque mot d'APT : Advanced (moyens), Persistent (installé des mois), Threat. Insister : identifier QUI attaque, c'est du calibrage de défense.
- **Visuel suggéré** : Matrice en 4 quadrants avec icônes distinctives : sac de pièces, radar géopolitique, poing levé, badge d'employé — et un petit personnage « script kiddie » en marge.
  - **alt-text** : Grille à quatre quadrants présentant cybercriminels, États-nations, hacktivistes et menaces internes avec leurs icônes de motivation.

---

### Slide 6 — Quatre profils, quatre défenses
- **Type** : tableau
- **Points clés (bullets)** :
  - Cybercriminel opportuniste → hygiène de base : il ira voir ailleurs.
  - APT étatique → détection avancée : il finira par entrer.
  - Hacktiviste → protéger la vitrine (site web, DDoS).
  - Menace interne → moindre privilège + journaux d'audit.
- **Notes orateur** : Question rhétorique : se protège-t-on d'un voleur opportuniste comme d'un service de renseignement ? Non — et c'est le fil rouge de la session : la défense se calibre sur l'adversaire. L'hygiène décourage l'opportuniste ; contre le persistant, il faut le détecter avant qu'il n'agisse.
- **Visuel suggéré** : Tableau à deux colonnes « Profil → Parade » avec un code couleur par famille d'attaquants.
  - **alt-text** : Tableau associant chaque profil d'attaquant à la stratégie de défense adaptée, avec un code couleur par profil.

---

### Slide 7 — L'économie du cybercrime : le RaaS
- **Type** : schéma
- **Points clés (bullets)** :
  - **Ransomware-as-a-Service** : l'opérateur développe, l'affilié attaque.
  - Partage type de la rançon : 70-80 % affilié / 20-30 % opérateur.
  - Spécialistes : courtiers d'accès (*Initial Access Brokers*), négociateurs, blanchisseurs.
  - Places de marché, programmes d'affiliation... et « service client ».
- **Notes orateur** : Oubliez le pirate solitaire : c'est une industrie avec division du travail. Détailler la chaîne : l'opérateur loue son code, l'affilié s'introduit (souvent via un accès acheté à un courtier), la rançon est partagée. Même la réputation compte : un groupe qui ne livre pas la clé après paiement perd ses « clients ». On n'affronte pas des individus, on affronte un secteur économique.
- **Visuel suggéré** : Schéma de flux : Opérateur (code) → plateforme d'affiliation → Affilié (intrusion) → Victime (rançon) → partage des cryptomonnaies.
  - **alt-text** : Diagramme du cycle d'affaires du Ransomware-as-a-Service décrivant opérateur, affilié, victime et flux de partage de la rançon.

---

### Slide 8 — Le paysage en chiffres
- **Type** : chiffres clés
- **Points clés (bullets)** :
  - **+ de 1 milliard $** de rançons payées dans le monde en 2023 — record (Chainalysis).
  - **~1,5 milliard $** de cryptomonnaies volées en un an par les groupes liés à la Corée du Nord, au plus fort de leur activité (Chainalysis).
  - **Février 2024** : l'opération Cronos frappe LockBit.
- **Notes orateur** : Trois lectures : (1) le cybercrime est une économie qui se mesure en milliards — d'où son professionnalisme ; (2) la frontière États/criminels est poreuse — certains États se financent par le braquage numérique (teaser de l'activité qui suit) ; (3) la riposte existe et gagne des batailles — on verra Cronos en détail. Relance chat : « un service client chez les rançonneurs, ça vous étonne ? »
- **Visuel suggéré** : Trois grands chiffres en typographie XXL sur fond sombre, chacun avec sa source et son année en petit.
  - **alt-text** : Trois statistiques géantes sur la cybercriminalité avec leurs sources : montants des rançons, vols de cryptomonnaies et opération Cronos.

---

### Slide 9 — Activité : la Fiche d'identité d'un attaquant
- **Type** : activité (sondages)
- **Points clés (bullets)** :
  - Le dossier : **Lazarus Group** (APT38) — actif depuis 2009.
  - Sony Pictures 2014 · Banque du Bangladesh 2016 · WannaCry 2017.
  - 📊 **Sondages n°2, 3, 4** : Catégorie ? Motivation ? La leçon ?
- **Notes orateur** : Lire le dossier à voix haute, puis lancer les trois sondages l'un après l'autre avec débrief entre chaque (scripts dans le plan). Piège du n°2 : la motivation financière ne suffit pas à classer — c'est le commanditaire qui compte. N°3 : un État sous sanctions se finance par le braquage numérique. N°4 : les frontières entre catégories sont poreuses — la classification sert à raisonner, pas à enfermer.
- **Visuel suggéré** : Fiche d'identité de type dossier de renseignement avec champs à remplir (catégorie, origine, motivations, cibles) à côté d'une carte du monde.
  - **alt-text** : Gabarit de fiche de renseignement cyber avec des champs vides pour documenter le profil du Lazarus Group.
- **Élément interactif** : 📊 Sondages Livestorm n°2 à 4 — classification collective par votes.

---

### Slide 10 — Affaire n°1 : la Banque du Bangladesh (2016)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Des mois d'infiltration · le réseau interbancaire SWIFT.
  - Objectif : ~1 milliard $ — butin : **81 millions $**.
  - Le grain de sable : une faute d'orthographe (« fandation »).
- **Notes orateur** : Raconter chronologiquement : l'étude des procédures, la neutralisation des impressions de confirmation, le choix du jeudi soir (quatre jours de battement entre les week-ends du Bangladesh et de New York), les fonds évaporés vers des casinos asiatiques — et la coquille qui éveille les soupçons d'une banque intermédiaire. Leçon d'humilité : les défenses ont échoué, la chance a limité les dégâts. Face à un APT, la question est « comment le détecter avant qu'il n'agisse » (threat hunting, B16).
- **Visuel suggéré** : Frise chronologique du casse avec un zoom loupe sur le mot mal orthographié dans l'ordre de virement.
  - **alt-text** : Chronologie du braquage de la Banque du Bangladesh avec une loupe mettant en évidence la faute d'orthographe décisive.

---

### Slide 11 — Affaire n°2 : LockBit & l'opération Cronos (2024)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Février 2024 : le site du groupe affiche... une bannière de police.
  - Coalition NCA · FBI · Europol · Gendarmerie nationale.
  - Serveurs, code source, portefeuilles — et **clés de déchiffrement** saisis.
  - Le talon d'Achille du RaaS : l'infrastructure et la **réputation**.
- **Notes orateur** : LockBit — le groupe qui avait frappé l'hôpital de Corbeil-Essonnes vu en B01. Affiliés arrêtés, opérateur principal identifié et sanctionné ; le groupe tente de renaître, durablement discrédité. Punchline : des victimes de 2022 qui n'avaient pas payé ont récupéré leurs données en 2024 — déposer plainte n'est jamais inutile. Enchaîner immédiatement sur le débat de la slide suivante.
- **Visuel suggéré** : Capture stylisée d'un site sombre recouvert d'une bannière officielle multi-agences de forces de l'ordre.
  - **alt-text** : Page d'accueil d'un site de fuite de données recouverte par la bannière de saisie des forces de l'ordre internationales.

---

### Slide 12 — Le grand débat : faut-il payer la rançon ?
- **Type** : sondage (opinion)
- **Points clés (bullets)** :
  - 📊 **Sondage n°5** : votre organisation est paralysée — faut-il payer ?
  - A) Oui, pour sauver l'activité — B) Non, jamais — C) Au cas par cas.
  - Repères : recommandation ANSSI · loi LOPMI 2023 : plainte sous 72 h pour être indemnisé.
- **Notes orateur** : Sondage d'opinion, pas de bonne réponse — mais des repères solides : pas de garantie de clé fonctionnelle, la victime se signale comme « bonne payeuse », chaque paiement alimente le milliard annuel. Depuis la LOPMI (2023), l'indemnisation d'une cyber-rançon par l'assurance exige un dépôt de plainte sous 72 heures. Argument final de Cronos : des victimes qui n'avaient pas payé ont récupéré leurs données gratuitement.
- **Visuel suggéré** : Balance à deux plateaux : d'un côté une liasse de billets, de l'autre un marteau de justice et une clé de déchiffrement.
  - **alt-text** : Balance mettant en regard le paiement d'une rançon et l'alternative judiciaire symbolisée par un marteau et une clé.
- **Élément interactif** : 📊 Sondage Livestorm n°5 (opinion — débat).

---

### Slide 13 — 🤔 Que feriez-vous ? La veille qui sauve
- **Type** : scénario
- **Points clés (bullets)** :
  - Votre veille signale : votre **secteur** est ciblé via une faille VPN.
  - Rien d'anormal détecté chez vous... pour l'instant.
  - A) Rien à faire — B) Corriger + vérifier les journaux — C) Tout débrancher.
- **Notes orateur** : Réponses par chat (A, B ou C). Débrief : B — appliquer le correctif AVANT l'attaque et vérifier qu'on n'est pas déjà compromis. A confond « pas détecté » et « pas attaqué » ; C est disproportionné. Ce réflexe a un nom : la Cyber Threat Intelligence — transition vers la slide suivante.
- **Visuel suggéré** : Écran de veille affichant une alerte sectorielle avec trois portes de sortie étiquetées A, B, C.
  - **alt-text** : Tableau de bord de veille cyber affichant une alerte sur une faille VPN et trois options de réaction.
- **Élément interactif** : 🤔 Mini-scénario — réponse A/B/C dans le chat.

---

### Slide 14 — La CTI : connaître son ennemi
- **Type** : contenu
- **Points clés (bullets)** :
  - **CTI** : le renseignement sur les menaces — jouer avec un coup d'avance.
  - **IoC** : les indices techniques (IP, empreintes, domaines) — à partager (MISP).
  - **TTP** : le mode opératoire signature — documenté dans **MITRE ATT&CK**.
  - Premier réflexe : s'abonner aux alertes du **CERT-FR** (gratuit).
- **Notes orateur** : L'IoC est l'empreinte digitale laissée sur la scène ; la partager, c'est vacciner la communauté avec l'expérience des victimes. MITRE ATT&CK documente les modes opératoires groupe par groupe — la fiche « Lazarus Group » y existe. Le devoir de la semaine : s'abonner au CERT-FR et repérer une alerte récente (elle servira en B03).
- **Visuel suggéré** : Pyramide ou entonnoir reliant IoC (indices bruts) → TTP (modes opératoires) → décisions de défense, avec les logos CERT-FR et MITRE ATT&CK.
  - **alt-text** : Schéma reliant les indicateurs de compromission aux modes opératoires puis aux décisions de défense, avec les sources CERT-FR et MITRE ATT&CK.

---

### Slide 15 — Quiz de validation
- **Type** : quiz (sondages)
- **Points clés (bullets)** :
  - 📊 **Sondage n°6** : comment la rançon est-elle partagée dans le RaaS ?
  - 📊 **Sondage n°7** : qu'est-ce qu'un IoC ?
  - 📊 **Sondage n°8** : pourquoi la menace interne est-elle si difficile à détecter ?
- **Notes orateur** : Lancer les trois sondages à la suite (~2 min chacun), débriefs scriptés dans le support : l'économie du RaaS explique le volume d'attaques ; l'IoC partagé vaccine les autres ; l'interne est déjà dedans — d'où les journaux d'audit et le moindre privilège (module C). Si le temps le permet, enchaîner sur le sondage bonus n°9 (départ conflictuel d'un administrateur).
- **Visuel suggéré** : Trois cartes de quiz numérotées 6, 7, 8 avec l'icône de sondage Livestorm.
  - **alt-text** : Trois cartes de questions de quiz numérotées, associées à des sondages en direct.
- **Élément interactif** : 📊 Sondages Livestorm n°6 à 8 (+ n°9 en tampon).

---

### Slide 16 — Synthèse & prochaine session
- **Type** : récap
- **Points clés (bullets)** :
  - 4 familles d'attaquants → 4 défenses calibrées.
  - Une économie en milliards (RaaS)... et une riposte qui gagne (Cronos).
  - La veille : CERT-FR, IoC, TTP, MITRE ATT&CK.
  - Self-paced : IBM SkillsBuild *« Cybersecurity Threat Landscape »* + abonnement CERT-FR.
  - Prochaine session — B03 : Types d'attaques & vecteurs.
- **Notes orateur** : Faire écrire dans le chat UN mot retenu de la session, en lire 4-5. Rappeler le double devoir : le module SkillsBuild et l'abonnement aux alertes du CERT-FR (repérer une alerte récente pour B03). Teaser B03 : « on ouvre l'arsenal — malwares, hameçonnage, déni de service, et l'histoire du ver qui a paralysé des hôpitaux entiers en un week-end. » Terminer à l'heure exacte.
- **Visuel suggéré** : Récapitulatif visuel en quatre vignettes (familles, économie, riposte, veille) et un panneau « B03 » fléché.
  - **alt-text** : Synthèse en quatre vignettes des thèmes de la session avec un panneau indiquant la prochaine session B03.
- **Élément interactif** : Chat de clôture — « un mot que vous retenez ».
