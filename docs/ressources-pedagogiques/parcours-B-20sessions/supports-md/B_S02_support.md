# Session B02 — Paysage des menaces & acteurs
Parcours : B 20 sessions  |  Module : A — Fondations  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Typologie des attaquants et motivations
    - La Cybercriminalité organisée : Une économie de services
    - La Cyber Threat Intelligence (CTI) : Connaître son ennemi
    - Deux affaires réelles : le braquage de la Banque du Bangladesh (Lazarus, 2016) et le démantèlement de LockBit (2024)
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Les attaquants se divisent en 4 familles majeures : cybercriminels (argent), États (géopolitique/espionnage), hacktivistes (causes politiques) et internes (employés).
*   La cybercriminalité moderne est professionnalisée et fonctionne en réseau (modèle de type RaaS - Ransomware-as-a-Service) — et la riposte s'organise, comme l'a montré le démantèlement partiel de LockBit en 2024.
*   La Cyber Threat Intelligence (CTI) permet de collecter les indices techniques (IoC) laissés par les pirates pour renforcer proactivement nos défenses.
*   Le CERT-FR et la base MITRE ATT&CK sont des ressources essentielles de veille cyber opérationnelle.

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Catégoriser les quatre principaux profils de cyberattaquants (cybercriminels, États-nations, hacktivistes, menaces internes) et expliquer leurs motivations respectives.
* Expliquer le fonctionnement structurel de la cybercriminalité moderne sous forme d'économie de services (*Ransomware-as-a-Service*).
* Identifier et exploiter les sources de renseignement sur les menaces (*Cyber Threat Intelligence*) pour réaliser une veille efficace.

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** Selon l'ANSSI, quel type de structure constitue les premières victimes des attaques par rançongiciel en France ?

    - A) Les multinationales du CAC 40
    - B) Les ministères et grandes administrations
    - C) Les TPE/PME/ETI et les collectivités territoriales ✅

    **Débrief mentor :** Réponse C (ANSSI, *Panorama de la cybermenace 2024*) : les structures qui se croient « trop petites pour intéresser les pirates » sont précisément les plus touchées. Pourquoi ? Parce que la majorité des attaquants sont des **opportunistes** : ils n'attaquent pas ce qui est prestigieux, ils attaquent ce qui est mal fermé. Comprendre QUI attaque — l'objet de cette session — c'est comprendre comment calibrer sa défense.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. La classification fine des acteurs**
Au-delà des 4 familles, présentez la gradation des compétences : **Script Kiddies** (faible compétence, outils clés en main téléchargés — dangereux par leur nombre, pas par leur talent), **Cybercriminels organisés** (financier, ransomwares, division du travail), **Hacktivistes** (Anonymous, idéologie, DDoS et défigurations), et **APT / États-Nations** (ressources quasi illimitées, furtivité extrême, mois de préparation). Expliquez la notion de surface d'attaque en constante expansion (IoT, télétravail) qui profite à tous ces profils à la fois.

**2. Les frontières poreuses entre catégories**
Le cas Lazarus (étudié en activité) illustre une réalité importante : les catégories fuient. Un groupe étatique peut mener des braquages financiers (financement d'un État sous sanctions) ; des cybercriminels peuvent être tolérés ou instrumentalisés par des États ; des hacktivistes peuvent servir de paravent. La classification sert à raisonner, pas à enfermer.

**3. La riposte internationale (point d'actualité)**
L'opération **Cronos** (février 2024) contre LockBit — coalition d'agences dont la Gendarmerie nationale, le FBI et la NCA britannique — a montré que le modèle RaaS a un talon d'Achille : son infrastructure et sa réputation. Sites saisis, clés de déchiffrement récupérées, affiliés identifiés, opérateur principal démasqué et sanctionné quelques mois plus tard. Le groupe a tenté de renaître, très affaibli. Message : le cybercrime n'est pas invincible — mais la traque est longue et internationale.

---

### Glossaire

*   **APT (Advanced Persistent Threat)** — Groupe d'attaquants hautement qualifié (généralement soutenu par un État) menant des cyberattaques ciblées et furtives sur le long terme.
*   **Dark Web** — Partie d'Internet accessible uniquement via des réseaux spécifiques (ex. Tor) où se déroulent des activités cybercriminelles comme la vente d'exploits ou d'accès volés.
*   **Defacement (Défiguration)** — Remplacement de la page d'accueil d'un site web par un message revendicatif ; l'attaque signature des hacktivistes.
*   **Insider Threat (Menace interne)** — Risque cyber provenant d'un employé, prestataire ou partenaire ayant des droits d'accès légitimes sur le réseau de l'entreprise.
*   **IoC (Indicator of Compromise)** — Indicateur de compromission technique (adresse IP, empreinte de fichier, nom de domaine) signalant une activité potentiellement malveillante sur un système.
*   **RaaS (Ransomware-as-a-Service)** — Modèle de location logicielle où des criminels louent un ransomware clé en main en échange d'un pourcentage sur la rançon extorquée.
*   **Script Kiddie** — Attaquant peu qualifié utilisant des outils d'attaque tout faits, sans en comprendre le fonctionnement ; dangereux par le nombre plus que par le talent.
*   **Threat Intelligence (CTI)** — Renseignement sur les cybermenaces : collecter, analyser et organiser des informations sur les attaquants et leurs techniques.
*   **TTP (Tactiques, Techniques et Procédures)** — Le « mode opératoire » caractéristique d'un groupe d'attaquants, référencé notamment dans la base MITRE ATT&CK.

---

### Concepts clés

!!! info "À retenir"
    Identifier QUI attaque n'est pas de la curiosité : c'est du calibrage de défense. On ne se protège pas d'un voleur opportuniste comme on se protège d'un service de renseignement.

!!! question "💬 Question chat — Le portrait-robot du pirate"
    « Décrivez en **un seul mot** le cyberattaquant tel que vous l'imaginez (par exemple : capuche, génie, adolescent, solitaire...). Tapez votre mot dans le chat ! »

    **Débrief mentor :** relevez les clichés qui reviennent — le solitaire à capuche, le surdoué de l'informatique. La réalité de cette session est bien différente : la majorité des attaques sont l'œuvre d'organisations structurées, avec des horaires de bureau, une division du travail et même un « service client ». Le cliché le plus dangereux est celui du « génie » : la plupart des attaques réussissent par des moyens banals contre des cibles mal protégées.

### 1. Typologie des attaquants et motivations
Le monde des cyberattaquants est hétérogène. Identifier qui attaque permet de mieux anticiper les techniques employées et de calibrer la défense de l'entreprise. On distingue quatre grands profils d'acteurs de menace :

*   **Les Cybercriminels (Motivation lucrative)** : C'est le groupe le plus représenté. Leur seul but est de faire de l'argent. Ils utilisent des logiciels de rançon pour chiffrer les données d'entreprises de toutes tailles (hôpitaux, PME, multinationales) et exiger des rançons, ou volent des données de cartes bancaires pour les revendre. La plupart sont des **opportunistes** : ils scannent Internet en masse et frappent ce qui est vulnérable.
*   **Les États-nations (Motivation géopolitique, espionnage, sabotage)** : Ces groupes d'attaquants, souvent appelés **APT** (*Advanced Persistent Threat* — Menace persistante avancée), disposent de ressources financières et techniques quasi illimitées. Leurs objectifs sont l'espionnage industriel ou politique, le vol de propriété intellectuelle ou la déstabilisation d'infrastructures critiques (ex. coupure d'un réseau électrique).
*   **Les Hacktivistes (Motivation politique ou idéologique)** : Groupes de pirates militant pour une cause. Leurs attaques consistent le plus souvent à saturer un site web (DDoS) ou à le défigurer (*defacement*) en remplaçant la page d'accueil par un message militant. Ils visent des entreprises ou gouvernements qu'ils considèrent comme contraires à leurs valeurs.
*   **La Menace Interne (*Insider Threat* — Motivation variée)** : Un collaborateur, un prestataire ou un administrateur qui abuse de ses accès légitimes. Il peut agir par malveillance (vengeance, sabotage), par appât du gain (revente de secrets) ou — cas le plus fréquent — par simple **négligence** : le clic malheureux, le fichier envoyé au mauvais destinataire.

Ajoutez à ce paysage les **script kiddies** : des attaquants peu qualifiés armés d'outils tout faits téléchargés en quelques clics. Individuellement inoffensifs pour une organisation bien tenue, ils sont dangereux par leur volume — et rappellent qu'aujourd'hui, le niveau d'entrée dans l'attaque est historiquement bas.

### 2. La Cybercriminalité organisée : Une économie de services
Oubliez l'image du pirate solitaire en capuche dans son garage. La cybercriminalité actuelle est structurée comme une industrie légitime, avec une division du travail poussée :

*   **Le Ransomware-as-a-Service (RaaS)** : C'est un modèle d'affaires où des créateurs de malwares de pointe (les "opérateurs") louent leur code à des "affiliés" (les attaquants qui s'introduisent dans le réseau cible). Si l'attaque réussit et que la victime paye, la rançon est partagée (souvent 70-80 % pour l'affilié, 20-30 % pour l'opérateur).
*   **La spécialisation des rôles** : Cette économie s'accompagne d'intermédiaires spécialisés :
    *   Les *Initial Access Brokers* (courtiers d'accès initiaux) qui cherchent des failles, s'introduisent dans les réseaux, puis revendent ces accès aux groupes de ransomware.
    *   Des négociateurs de rançons spécialisés.
    *   Des réseaux de blanchiment d'argent par cryptomonnaies.

C'est une économie avec ses places de marché (le Dark Web), ses programmes d'affiliation, son « support client » pour guider les victimes dans le paiement — et même sa gestion de réputation : un groupe qui ne fournit pas la clé après paiement perd ses « clients ». Cette industrialisation explique le volume : on n'affronte pas des individus, on affronte un secteur économique.

### 3. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **Plus d'un milliard de dollars** de paiements de rançons dans le monde sur la seule année 2023 — un record historique (analyses Chainalysis des flux de cryptomonnaies).
    - **De l'ordre de 70-80 % / 20-30 %** : le partage type d'une rançon entre l'affilié qui mène l'attaque et l'opérateur qui loue le rançongiciel (modèle RaaS).
    - **Plus d'un milliard et demi de dollars** en cryptomonnaies dérobés en une seule année par les groupes liés à la Corée du Nord, au plus fort de leur activité (estimations Chainalysis) — le « braquage d'État » à l'échelle industrielle.
    - **Février 2024** : l'opération internationale Cronos frappe LockBit, alors le groupe de rançongiciel le plus prolifique au monde (cas détaillé ci-dessous).

**Comment lire ces chiffres ?** (1) Le cybercrime est une économie qui se mesure en milliards — d'où son professionnalisme. (2) La frontière États/criminels est poreuse : certains États se financent par le braquage numérique. (3) La riposte existe et gagne des batailles — mais la meilleure défense reste de ne pas être une cible facile.

### Activité — La Fiche d'identité d'un attaquant (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Présentez la description ci-dessous du **Lazarus Group**, puis faites remplir la « fiche d'identité » collectivement, un sondage par rubrique. Après chaque vote, débriefez avant la rubrique suivante.

> **Description de la menace** : Le groupe connu sous le nom de *Lazarus Group* (ou *APT38* pour sa branche financière) est actif depuis au moins 2009. Il est soupçonné d'être lié à un État d'Asie de l'Est. Ce groupe s'est fait connaître par le piratage massif de Sony Pictures en 2014, le vol de 81 millions de dollars à la Banque centrale du Bangladesh en 2016 (via le réseau interbancaire SWIFT), et la propagation mondiale du ransomware *WannaCry* en 2017. Il cible principalement les institutions financières, les plateformes d'échange de cryptomonnaies et les organisations gouvernementales.

*   **📊 Sondage n°2 — Catégorie :** Dans quelle famille d'attaquants classez-vous le Lazarus Group ?
    *   A) Cybercriminels : ils volent des banques, c'est financier
    *   B) État-nation : un groupe lié à un État, malgré ses braquages financiers ✅
    *   C) Hacktivistes : Sony Pictures a été visé pour un film
*   **📊 Sondage n°3 — Motivation :** Pourquoi un groupe ÉTATIQUE braque-t-il des banques et des plateformes de cryptomonnaies ?
    *   A) Pour enrichir personnellement ses membres
    *   B) Pour financer un État sous sanctions internationales ✅
    *   C) Par défi technique, pour prouver sa supériorité
*   **📊 Sondage n°4 — La leçon :** Que nous apprend le cas Lazarus sur la classification des attaquants ?
    *   A) Les catégories sont étanches : un État ne fait jamais de financier
    *   B) Les frontières sont poreuses : un même groupe peut espionner, saboter ET braquer — la classification sert à raisonner, pas à enfermer ✅
    *   C) Seuls les États savent mener des cyberattaques

**Éléments de débriefing (pour le mentor) :**

- N°2 : le piège est A — la motivation financière ne suffit pas à classer : c'est le **commanditaire** qui compte. Lazarus est l'exemple unique d'un APT étatique qui braque pour financer son État.
- N°3 : un État sous sanctions ne peut plus se financer par les circuits classiques — le braquage numérique devient une politique publique. C'est aussi pour cela que ces groupes visent les cryptomonnaies (difficiles à geler).
- N°4 : conclure sur la fiche complète (origine présumée : Corée du Nord ; attaques majeures : Sony 2014, Bangladesh 2016, WannaCry 2017 ; cibles : banques, crypto, gouvernements). Teaser : « le braquage du Bangladesh mérite qu'on s'y arrête — c'est l'histoire d'un milliard de dollars sauvé par une faute d'orthographe. »

### 4. Deux affaires réelles : le braquage d'État et la chute d'un empire criminel

#### Cas n°1 — La Banque du Bangladesh (2016) : le casse du siècle... freiné par une coquille

En février 2016, des ordres de virement partent du compte de la **Banque centrale du Bangladesh** auprès de la Réserve fédérale de New York, via le réseau interbancaire mondial **SWIFT**. Les attaquants — attribués au groupe **Lazarus** — ont passé des mois dans le réseau de la banque, étudié les procédures, neutralisé les impressions de confirmation, et programmé leurs ordres un jeudi soir : week-end au Bangladesh, puis week-end à New York — près de quatre jours de battement. Objectif : près d'**un milliard de dollars**. Ils en obtiennent **81 millions**, évaporés vers des casinos asiatiques. Le reste est bloqué grâce à une série de hasards — dont une **faute d'orthographe** dans un ordre de virement (« fandation » au lieu de « foundation ») qui éveille les soupçons d'une banque intermédiaire.

**Ce que ce cas illustre :** le niveau de préparation d'un APT (des mois d'infiltration, l'étude des procédures humaines, le choix du calendrier) ; la porosité des catégories (un État qui braque) ; et une leçon d'humilité : les défenses ont échoué — c'est la chance qui a limité les dégâts. Face à un APT, la question n'est pas « comment l'empêcher d'entrer » mais « comment le détecter avant qu'il n'agisse » (le threat hunting, revu en B16).

#### Cas n°2 — LockBit et l'opération Cronos (2024) : la riposte internationale

En février 2024, les visiteurs du site de fuite de **LockBit** — alors le groupe de rançongiciel le plus prolifique au monde, responsable notamment de l'attaque de l'hôpital de Corbeil-Essonnes (vue en B01) — découvrent... une bannière des forces de l'ordre. L'opération **Cronos**, coalition internationale (NCA britannique, FBI, Europol, Gendarmerie nationale française entre autres), a saisi l'infrastructure du groupe : serveurs, code source, portefeuilles de cryptomonnaies, et surtout des **clés de déchiffrement** remises aux victimes. Des affiliés sont arrêtés, et quelques mois plus tard l'opérateur principal est publiquement identifié et sanctionné. Le groupe tentera de renaître, durablement affaibli et discrédité auprès de ses « affiliés ».

**Ce que ce cas illustre :** le modèle RaaS a un talon d'Achille — son infrastructure et sa **réputation** (un RaaS dont les clés sont chez la police ne recrute plus d'affiliés) ; la coopération internationale fonctionne, y compris avec la France en première ligne ; et pour les victimes, le dépôt de plainte n'est jamais inutile : des clés de déchiffrement récupérées en 2024 ont servi des victimes de 2022.

!!! tip "📊 Sondage Livestorm n°5 — Le grand débat (sondage d'opinion, pas de bonne réponse)"
    **Question :** Votre organisation est paralysée par un rançongiciel et l'attaquant réclame une rançon. Faut-il payer ?

    - A) Oui, si c'est la seule façon de sauver l'activité et les emplois
    - B) Non, jamais : payer finance le crime et rien ne garantit la clé
    - C) Cela dépend : décision au cas par cas, avec juristes et assureur

    **Débrief mentor :** Sondage d'opinion — pas de « bonne » réponse, mais des repères solides. L'ANSSI et les forces de l'ordre recommandent de **ne pas payer** : aucune garantie de récupérer une clé fonctionnelle, la victime se signale comme « bonne payeuse », et chaque paiement alimente l'industrie (rappel : plus d'un milliard de dollars versés en 2023). En France, depuis la loi LOPMI (2023), une entreprise ne peut être indemnisée d'une cyber-rançon par son assurance que si elle **dépose plainte sous 72 heures**. Et l'opération Cronos ajoute un argument inattendu : des victimes qui n'avaient PAS payé ont récupéré leurs données grâce aux clés saisies... deux ans plus tard.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Vous êtes RSSI d'une PME industrielle. Votre veille CTI signale que votre **secteur** est activement ciblé par un groupe de rançongiciel exploitant une faille sur les passerelles VPN. Rien d'anormal détecté chez vous pour l'instant. **Tapez A, B ou C dans le chat :**

    - A) Rien à faire : nous ne sommes pas attaqués.
    - B) Appliquer immédiatement le correctif VPN, vérifier les journaux de connexion des dernières semaines, alerter les équipes. ✅
    - C) Débrancher Internet par précaution jusqu'à nouvel ordre.

    **Débrief mentor :** B — c'est exactement l'usage de la CTI : transformer le renseignement en action AVANT l'attaque (correctif) et VÉRIFIER qu'on n'est pas déjà compromis (les journaux). A confond « pas détecté » et « pas attaqué » ; C est disproportionné (on tue l'activité). Transition parfaite vers la section CTI.

### 5. La Cyber Threat Intelligence (CTI) : Connaître son ennemi
La **CTI** (Renseignement sur les cybermenaces) consiste à collecter, analyser et organiser des informations sur les attaquants actifs et leurs méthodes.

*   **Les indicateurs de compromission (IoC — *Indicators of Compromise*)** : Ce sont les indices techniques laissés par les pirates (adresses IP de commande, signatures de fichiers malveillants, noms de domaine suspects). Les partager entre organisations, c'est vacciner la communauté avec l'expérience des victimes.
*   **Les TTP (Tactiques, Techniques et Procédures)** : au-delà des indices ponctuels, le « mode opératoire » d'un groupe — sa signature comportementale. C'est ce que documente la base **MITRE ATT&CK**, l'encyclopédie mondiale des techniques observées, groupe par groupe.
*   **Les sources de confiance pour la veille** :
    *   Le **CERT-FR** (centre gouvernemental français d'alerte) publie régulièrement des alertes et des fiches sur les vulnérabilités activement exploitées — l'abonnement est gratuit et constitue le premier réflexe de veille professionnel.
    *   La base **MITRE ATT&CK** pour comprendre les modes opératoires.
    *   Les plateformes d'échange d'IoC (MISP, OpenCTI — voir panorama).

> 💡 **Bon à savoir : APT (Advanced Persistent Threat)**
> Le terme "persistant" signifie que ces groupes ne font pas une intrusion rapide pour voler et repartir. Ils s'installent discrètement dans le réseau de la victime pendant des mois, voire des années, pour espionner et collecter des données à long terme sans se faire détecter — Lazarus a préparé le braquage du Bangladesh pendant des mois, de l'intérieur.

---

### Questions de réflexion
1. Quelle différence majeure de défense appliquez-vous face à un cybercriminel opportuniste (qui attaque au hasard une PME vulnérable) vs un groupe APT étatique (qui cible précisément votre entreprise avec des ressources illimitées) ?
2. Pourquoi la menace interne (un collaborateur malveillant ou négligent) est-elle parfois considérée comme le risque le plus difficile à détecter pour une équipe de sécurité ?
3. Après l'opération Cronos, LockBit a perdu la confiance de ses affiliés. En quoi la « réputation » est-elle un point faible exploitable de l'économie RaaS ?

**Corrigé / Éléments de réponse :**
1. Contre un cybercriminel opportuniste, on bloque les failles connues (hygiène de base) — il ira voir ailleurs. Contre un APT, on ajoute la détection avancée (EDR/SOC, threat hunting) car il utilisera des moyens inconnus et persistera.
2. L'interne a déjà des droits d'accès légitimes : ses actions se fondent dans le trafic normal. Les outils classiques (pare-feu) sont conçus pour bloquer les menaces externes.
3. Le RaaS repose sur la confiance des affiliés (partage des rançons, fourniture des clés). Une infrastructure saisie et des clés récupérées par la police détruisent cette confiance — l'arme économique complète l'arme judiciaire.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez le paysage des menaces cyber comme la **criminalité dans le monde physique** :
    - **Le voleur de rue** correspond au cybercriminel opportuniste : il cherche des portes déverrouillées (logiciels non mis à jour) pour voler ce qu'il peut (argent, données à revendre).
    - **L'espion industriel ou le commando militaire** représente l'APT (État-Nation) : il dispose de budgets colossaux, d'équipements de pointe et peut planifier son intrusion pendant des mois pour voler des plans secrets.
    - **Le manifestant devant un siège social** est le hacktiviste : il veut dégrader votre vitrine (défigurer votre site web) pour diffuser ses revendications politiques.
    - **Le garde corrompu ou l'employé négligent** est la menace interne.
    - Et **le gamin qui teste toutes les poignées de portes du parking** est le script kiddie : peu doué, mais il y en a beaucoup.

**Exemple d'application professionnelle :**
Une entreprise technologique subit une intrusion discrète. Les outils de Threat Intelligence permettent de corréler les signatures techniques (IoC) laissées par l'attaquant avec le mode opératoire (TTP) documenté d'un groupe APT étatique dans MITRE ATT&CK. Grâce à ces données, l'équipe de sécurité comprend que l'attaquant cible spécifiquement les fichiers de R&D et applique immédiatement des mesures de confinement adaptées — au lieu de traiter l'incident comme un vulgaire ransomware.

### Panorama des solutions du marché (Commerciales & Open-Source)

L'analyse de Threat Intelligence et la veille sur les cybermenaces requièrent des outils capables de consolider des indicateurs de compromission :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Recorded Future** : Leader mondial de la Threat Intelligence, intégrant l'analyse automatisée du Dark Web et la notation en temps réel du risque IP/Domaine.
    *   **CrowdStrike Falcon Intelligence** : Service de Threat Intelligence corrélant les données de millions d'agents de sécurité dans le monde pour cartographier les TTPs des groupes d'attaquants.
    *   **Mandiant Threat Intelligence (Google Cloud)** : Base de connaissances hautement qualifiée sur les menaces étatiques et les attaques ciblées avancées.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **MISP (Malware Information Sharing Platform)** : Plateforme open-source leader mondiale pour le partage et le stockage d'indicateurs de compromission (IoC). Très utilisée par les CERTs et les entreprises pour synchroniser leurs listes de blocage.
    *   **OpenCTI** : Solution open-source développée en France pour structurer, modéliser et visualiser les connaissances sur les cybermenaces.
    *   **AlienVault OTX (Open Threat Exchange)** : Plus grande communauté gratuite d'échange d'IoC au monde, facilement intégrable dans les outils de détection.

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après la séquence CTI.

*   **📊 Sondage n°6 :** Dans le modèle RaaS, comment la rançon est-elle typiquement partagée ?
    *   A) L'opérateur qui a créé le rançongiciel garde tout
    *   B) L'affilié qui mène l'attaque garde la plus grande part (70-80 %), l'opérateur prélève sa commission ✅
    *   C) La rançon est reversée à parts égales à tous les membres du forum
*   **📊 Sondage n°7 :** Qu'est-ce qu'un IoC (indicateur de compromission) ?
    *   A) Un indice technique (adresse IP, empreinte de fichier, domaine) signalant une activité malveillante probable ✅
    *   B) Le montant de la rançon demandée
    *   C) Le niveau de compétence d'un attaquant
*   **📊 Sondage n°8 :** Pourquoi la menace interne est-elle si difficile à détecter ?
    *   A) Parce que les employés sont plus intelligents que les pirates
    *   B) Parce qu'elle utilise des accès légitimes : ses actions se fondent dans l'activité normale ✅
    *   C) Parce qu'elle n'existe presque jamais

**Éléments de débriefing (pour le mentor) :**

- N°6 : l'économie du RaaS explique le volume d'attaques — le talent (l'opérateur) est démultiplié par les bras (les affiliés). Et c'est cette économie que Cronos a frappée au portefeuille et à la réputation.
- N°7 : l'IoC est l'empreinte digitale laissée sur la scène ; la partager (MISP, CERT-FR), c'est vacciner les autres.
- N°8 : les pare-feux regardent vers l'extérieur ; l'interne est déjà dedans — d'où les journaux d'audit et le moindre privilège (module C du parcours).

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Cybersecurity Threat Landscape"* (~1h30).
*   **[CERT-FR — Centre gouvernemental de veille](https://www.cert.ssi.gouv.fr/)** : s'abonner aux alertes (gratuit) et lire la description d'une alerte « Active » pour voir comment les experts documentent une menace en temps réel.
*   **[Cybermalveillance — Rapport d'activité](https://www.cybermalveillance.gouv.fr)** : le baromètre annuel des menaces vues du terrain français.
*   **MITRE ATT&CK** : parcourir la fiche d'un groupe (ex. « Lazarus Group ») pour découvrir ses TTP documentées.

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Appliquer la notion de menace interne à une décision concrète.
*   **📊 Sondage Livestorm n°9 :** Votre administrateur systèmes quitte l'entreprise en mauvais termes ; son départ est effectif vendredi soir. Quelle est l'action prioritaire ?
    *   A) Aucune : il a signé une clause de confidentialité, la question est désormais juridique.
    *   B) Révoquer tous ses accès (comptes, VPN, badges) dès le départ effectif et passer en revue ses journaux d'activité récents ✅
    *   C) Attendre le prochain audit annuel pour désactiver ses comptes.
*   **Guide d'animation (pour le mentor) :** La menace interne se gère par des **processus** : la révocation immédiate des accès au départ d'un collaborateur (*offboarding*) est l'un des contrôles les plus rentables qui soient. La clause de confidentialité (A) n'empêche rien techniquement ; l'audit annuel (C) laisse des mois de fenêtre d'exposition. La revue des journaux répond à la question qui fâche : « a-t-il déjà emporté quelque chose ? ». À relier au principe de moindre privilège (module C du parcours). Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **APT (Advanced Persistent Threat)** | Groupe d'attaquants sophistiqué, souvent étatique, menant des campagnes ciblées, furtives et longues (des mois d'infiltration). |
| **Dark Web** | Partie d'Internet accessible via des réseaux spécifiques (Tor) où se vendent exploits, accès volés et données. |
| **Defacement (Défiguration)** | Remplacement de la page d'accueil d'un site par un message revendicatif — la signature hacktiviste. |
| **Insider Threat (Menace interne)** | Risque venant d'un employé/prestataire aux accès légitimes — malveillance ou simple négligence. |
| **IoC (Indicator of Compromise)** | Indice technique (IP, empreinte de fichier, domaine) signalant une compromission probable. |
| **RaaS (Ransomware-as-a-Service)** | Location de rançongiciel clé en main contre un pourcentage de la rançon (70-80 % affilié / 20-30 % opérateur). |
| **Script Kiddie** | Attaquant peu qualifié armé d'outils tout faits — dangereux par le nombre. |
| **Threat Intelligence (CTI)** | Renseignement sur les menaces : transformer les indices (IoC) et modes opératoires (TTP) en défense proactive. |
| **TTP** | Tactiques, Techniques et Procédures — le mode opératoire signature d'un groupe (base MITRE ATT&CK). |

**La règle d'or de la session :** connaître son ennemi pour calibrer sa défense — l'hygiène de base décourage l'opportuniste, la détection avancée traque le persistant, et la veille (CERT-FR) vous fait jouer avec un coup d'avance.
