# Plan de séance — Session B17
Parcours : B 20 sessions  |  Module : E — Opérations, détection & réponse  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## 1. Métadonnées de la session
* **Titre** : Outils SIEM & Analyse de logs — avec l'**Atelier de Synthèse 4**
* **Objectifs pédagogiques opérationnels** :
  * Expliquer le rôle d'un SIEM dans la centralisation, la normalisation, la corrélation et le stockage des événements de sécurité.
  * Analyser des lignes de logs brutes (web Apache, authentification Linux) pour identifier une attaque et évaluer sa réussite (codes HTTP, tailles de réponses).
  * Décrire une règle de corrélation logique et proposer des contre-mesures immédiates face à une attaque détectée (Atelier de Synthèse 4).
* **Prérequis** : B05 (réseau), B16 (SOC). L'Atelier 4 réutilise la DMZ de l'Atelier 1 (B08) et la SQLi vue en B03.
* **Lien de progression** : B16 a présenté l'équipe (le SOC) ; B17 présente son instrument (le SIEM) et sa matière première (les journaux). La valeur probante des journaux prépare directement l'investigation de B18 (réponse aux incidents).

## 2. Checklist technique Livestorm (avant la session)

- [ ] Les **9 sondages** sont pré-créés dans Livestorm, dans l'ordre du tableau ci-dessous.
- [ ] Le partage d'écran est testé avec le diaporama B17 ([spécifications](../slides/B_S17_slides_spec.md)) — l'extrait de logs de l'Atelier 4 (5 lignes) doit être parfaitement lisible à l'écran.
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
| :-- | :-- | :-- | :-- | :-- |
| 1 | 0:04 | Brise-glace | IBM 2024 : délai moyen pour identifier puis contenir une violation ? | C — 258 jours |
| 2 | ~0:52 | Atelier 4 | Quelle attaque aux lignes 3-4 du log ? | B — Injection SQL |
| 3 | ~0:58 | Atelier 4 | Code 200 + tailles croissantes : réussite potentielle ? | A — Oui |
| 4 | ~1:04 | Atelier 4 | Contre-mesures immédiates pour MedDistri ? | B — WAF + requêtes paramétrées |
| 5 | 1:10 | Opinion | Le curseur de la journalisation des salariés ? | — (pas de bonne réponse) |
| 6 | 1:18 | Quiz | À quoi sert la normalisation (parsing) ? | B |
| 7 | 1:19 | Quiz | Pourquoi centraliser les journaux à part ? | C |
| 8 | 1:21 | Quiz | 10 échecs puis 1 succès, même IP : que faire ? | B |
| 9 | 1:23 | Bonus | 500 connexions/10 s vers 5 ports différents ? | B — Balayage de ports |

## 3. Vue d'ensemble du déroulé

| Créneau | Séquence | Interactions |
| :-- | :-- | :-- |
| 0:00–0:04 | Accueil & réinvestissement du devoir (les 3 éléments d'un log) | Chat |
| 0:04–0:09 | Brise-glace : 258 jours | 📊 Sondage n°1 |
| 0:09–0:20 | Le SIEM : 4 étapes + panorama des outils | — |
| 0:20–0:30 | Anatomie d'une ligne de log (Apache, SSH) | 💬 Question chat |
| 0:30–0:38 | Les règles de corrélation (force brute, voyage impossible) | — |
| 0:38–0:46 | Affaires réelles : Marriott & Desjardins | 💬 Chat « l'énigme Marriott » |
| 0:46–1:10 | **Atelier de Synthèse 4 : l'enquête MedDistri** | 📊 Sondages n°2, 3, 4 + chat |
| 1:10–1:14 | Le curseur de la journalisation (opinion) | 📊 Sondage n°5 |
| 1:14–1:18 | Mini-scénario : le voyage impossible | 🤔 Chat A/B/C |
| 1:18–1:23 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:23–1:27 | Exercice bonus : le scan de ports (tampon) | 📊 Sondage n°9 |
| 1:27–1:30 | Synthèse, devoirs & teaser B18 | Chat : « un mot retenu » |

## 4. Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & réinvestissement du devoir

**🎙️ Verbatim d'ouverture :**
> « Bonsoir à toutes et à tous ! La semaine dernière, nous avons rencontré l'équipe — le SOC, ses analystes L1, L2, L3. Ce soir, nous ouvrons leur instrument de travail : le SIEM, et sa matière première, les journaux. Vous aviez une recherche à faire : la définition d'un log et ses trois éléments obligatoires. **Dans le chat, citez-en au moins un !** »

**Points de contenu :**
- Récolter dans le chat : horodatage, source (IP/machine/compte), événement — valider et compléter.
- Annoncer le programme : comprendre le SIEM, apprendre à LIRE un log, puis mener une vraie enquête collective (Atelier de Synthèse 4).

**Transition :** « Avant de lire notre première ligne de log, une question qui fait mal. »

### 0:04–0:09 — 📊 Sondage n°1 (brise-glace) : 258 jours

Lancer le sondage n°1 (IBM 2024 : délai moyen identification + confinement). Laisser voter ~60 secondes.

**🎙️ Débrief scripté :**
> « Réponse C : 258 jours en moyenne — presque neuf mois, selon le rapport IBM *Cost of a Data Breach* 2024. Neuf mois pendant lesquels l'attaquant écrit pourtant son journal intime chez vous : chaque connexion, chaque requête laisse une ligne quelque part. Le drame n'est presque jamais l'absence de traces — c'est que personne ne les lit. Ce soir, on apprend à les lire. »

**Transition :** « Et comme personne ne peut lire des millions de lignes par jour, on commence par la machine qui le fait pour nous. »

### 0:09–0:20 — Le SIEM : 4 étapes + panorama

**Points de contenu (support §1) :**
- **Collecte** : agents + Syslog → tout converge vers la base centrale.
- **Normalisation (parsing)** : traduire les formats hétérogènes (XML Windows, Syslog Linux, pare-feu) vers un schéma commun — la condition de tout le reste.
- **Corrélation** : croiser des événements de machines différentes pour reconstituer une attaque.
- **Stockage & visualisation** : archivage sécurisé (conformité, enquêtes futures) + tableaux de bord.
- 🎙️ « Un pirate laisse une trace sur le pare-feu, une sur le serveur de fichiers, une sur l'annuaire. Séparées : anodines. Croisées : une intrusion qui se raconte toute seule. »
- Panorama outils (30 secondes, sans catalogue) : Splunk, Microsoft Sentinel, Elastic côté payant ; Wazuh, ELK, Graylog côté open-source — retenir : la PME a des options gratuites crédibles.

**Transition :** « Descendons maintenant à l'échelle de la ligne — car tout le SIEM repose sur elle. »

### 0:20–0:30 — Anatomie d'une ligne de log

**Points de contenu (support §2) :**
- Afficher le log Apache et le décortiquer champ par champ : Qui (IP), Quand (horodatage + fuseau), Quoi (méthode + ressource), le **code d'état** (200/400/404/500), la **taille de réponse** — insister : « la taille, retenez-la, elle servira dans l'atelier ».
- Afficher le log SSH `Failed password` et refaire l'exercice en 60 secondes : la grille Qui/Quand/Où/Quoi est universelle.
- 💬 **Question chat — le réflexe du lecteur de logs** : « une requête sur `/admin/login.php` depuis Internet : grave ? Qu'allez-vous vérifier juste après ? » Débrief : une ligne isolée = signal faible ; la fréquence et la série font le diagnostic — c'est le travail de la corrélation.

**Transition :** « Justement : comment transformer cette lecture manuelle en détection automatique ? »

### 0:30–0:38 — Les règles de corrélation

**Points de contenu (support §3) :**
- La structure : **motif + seuil + fenêtre de temps → action**.
- Dérouler la règle force brute SSH : 10 `Failed password` + 1 `Accepted` même IP en 60 s → alerte critique (+ isolement SOAR, rappel B16).
- 🎙️ « Un échec de connexion, c'est la vie. Dix échecs puis un succès en une minute, c'est une histoire — et les histoires, ça se détecte. »
- Autres motifs en une phrase chacun : voyage impossible (le mini-scénario de tout à l'heure), exfiltration (volume sortant anormal), scan de ports (le bonus de fin).

**Transition :** « Voyons maintenant ce qui arrive quand ces règles n'existent pas. Deux affaires, deux continents, une même morale. »

### 0:38–0:46 — Affaires réelles : Marriott & Desjardins

**Points de contenu (support §5) :**
- **Marriott/Starwood** : intrusion démarrée en 2014 chez Starwood, rachat par Marriott en 2016, découverte en **2018** par une alerte d'un outil de supervision de base de données — **4 ans** de présence ; ~339 millions de dossiers clients (chiffre du régulateur britannique), passeports inclus ; amende ICO de 18,4 M£ (2020). Morale : on achète aussi les intrusions en cours (due diligence cyber, B13) ; une seule alerte bien placée sur l'actif critique a suffi.
- 💬 **Chat — l'énigme Marriott** : « comment reste-t-on 4 ans invisible ? » Récolter : comptes légitimes volés, petits volumes, horaires normaux, périmètre hérité non supervisé.
- **Desjardins** (cas miroir, plus bref) : un employé exfiltre pendant **26 mois** les données de **9,7 millions de personnes** ; découvert par la **police**, pas par l'interne (rapport du Commissariat à la protection de la vie privée du Canada, 2020) ; plus de 100 M$ CA de coûts annoncés dès 2019. Morale : la journalisation surveille aussi l'intérieur — copies massives, récurrence, DLP.

**Transition :** « Assez regardé les autres. À votre tour de mener l'enquête : Atelier de Synthèse 4. »

### 0:46–1:10 — 🧪 Atelier de Synthèse 4 : l'enquête dans les journaux de MedDistri

**Séquençage (24 min) :**

1. **Mise en situation (0:46–0:52)** : depuis l'Atelier 1 (B08), MedDistri a sa DMZ et un concentrateur de journaux. Cette nuit, le WAF en mode détection a signalé des requêtes suspectes sur la boutique. Afficher l'extrait `access.log` (5 lignes) et le lire ligne par ligne à voix haute, sans encore l'interpréter. 🎙️ « Cinq lignes. Toute l'attaque est là. À vous de la reconstituer. »
2. **📊 Sondage n°2 + débrief (0:52–0:58)** : quelle attaque aux lignes 3-4 ? → B, injection SQL : l'apostrophe qui casse la syntaxe, `OR 1=1` (condition toujours vraie), puis `UNION SELECT` qui greffe une requête sur la table `clients` (revue de B03). Faire remarquer la ligne 2 : `198.51.100.23` est un simple visiteur — première étape de toute enquête : isoler QUI fait QUOI.
3. **📊 Sondage n°3 + débrief (0:58–1:04)** : le code 200 signe-t-il la réussite ? → A, oui potentiellement — mais la nuance fait les bons analystes : 200 = « requête traitée », c'est la **taille** qui accable (851 → 4522 → 6817 octets quand la table `clients` sort). Pendant le vote, **chat** : « que révèle la ligne 5, et pourquoi est-elle plutôt rassurante ? » → traversée de répertoires vers `/etc/passwd`, **vraisemblablement sans succès** : 400 « requête invalide » + réponse de 118 octets — ni 200, ni volume ; le même raisonnement code+taille s'applique.
4. **📊 Sondage n°4 + débrief (1:04–1:08)** : la riposte ? → B : bloquer l'IP au WAF + passer en mode blocage + **requêtes paramétrées** (le correctif définitif), puis évaluer la fuite — si données personnelles : CNIL, 72 h (B15). A sacrifie la disponibilité sans traiter la cause ; C détruit **les preuves**.
5. **Synthèse de l'atelier (1:08–1:10)** : 🎙️ « Chronologie complète : reconnaissance à 21:00:15, extraction à 21:00:38, tentative d'élargissement à 21:01:02 — moins de trois minutes. Vous venez de faire, à la main, ce qu'une règle de corrélation fait en continu. Et vous comprenez pourquoi on n'efface JAMAIS les journaux : ce sont désormais des pièces à conviction. »

### 1:10–1:14 — 📊 Sondage n°5 (opinion) : le curseur de la journalisation

Lancer le sondage n°5 (tout journaliser / ciblé et proportionné / le minimum). Annoncer qu'il n'y a pas de bonne réponse.

**🎙️ Débrief scripté :**
> « Le cadre légal tranche une partie du débat : la journalisation des salariés doit être proportionnée, connue d'eux, limitée dans le temps — la CNIL recommande couramment de l'ordre de six mois pour les journaux de connexion. Vous reconnaissez B15 : minimisation et limitation de conservation s'appliquent aussi aux logs. En pratique, le point d'équilibre est proche de B : cibler l'authentification, le réseau, les processus critiques. Et souvenez-vous de Desjardins : zéro surveillance interne, ça se paie aussi. »

### 1:14–1:18 — 🤔 Mini-scénario : le voyage impossible

Afficher le scénario (Paris 9h02, Singapour 9h37) — réponses A/B/C dans le chat.

**🎙️ Débrief scripté :**
> « B, évidemment — mais regardez pourquoi : le VPN d'entreprise fabrique de faux voyages impossibles, donc on vérifie le contexte d'abord ; puis le canal indépendant — l'appel, toujours l'appel, le contre-appel de B04 ; puis la mesure conservatoire proportionnée. Une alerte de corrélation n'est jamais un verdict : c'est une priorité d'enquête. A parie sans vérifier, C punit deux cents salariés pour un doute. »

### 1:18–1:23 — 📊 Quiz de validation (sondages n°6, 7, 8)

Enchaîner les trois sondages, débrief de 30 secondes chacun (éléments dans le support) :
- N°6 → B : la normalisation est la langue commune — ingrate, chronophage, fondatrice.
- N°7 → C : le déport temps réel met les traces hors de portée de l'attaquant — et fonde leur valeur probante.
- N°8 → B : l'enchaînement échecs→succès est le motif ; réponse graduée, pas de coupure générale.

### 1:23–1:27 — 📊 Sondage n°9 (bonus tampon) : le scan de ports

Lancer si le temps le permet (sinon : « à faire en autonomie, il est dans le support »).

**🎙️ Débrief scripté :**
> « B : 500 tentatives en 10 secondes sur 5 ports, même source — quelqu'un sonne à toutes vos portes pour trouver celle qui s'ouvre. C'est la reconnaissance de B02-B03, et l'une des règles les plus simples à écrire dans un SIEM. »

### 1:27–1:30 — Synthèse, devoirs & teaser B18

**Points de clôture :**
- 🎙️ « Trois choses à retenir : un log = horodatage + source + événement ; la corrélation transforme des millions de lignes en quelques alertes ; et les journaux déportés sont vos pièces à conviction. »
- Chat : « un mot que vous retenez de la session ».
- Self-paced : cours IBM SkillsBuild *"Log Analysis and SIEM Concepts"* (~1h30) + recherche : qu'est-ce que le **confinement** d'une machine compromise, et citez une action technique pour l'isoler (câble débranché, VLAN d'isolement, règle de pare-feu locale) — préparation directe de B18.
- Teaser B18 : « la semaine prochaine : l'alerte a sonné, l'attaque est confirmée — que fait-on dans les dix premières minutes ? Confiner, éradiquer, reconstruire… et je vous expliquerai pourquoi il ne faut JAMAIS débrancher la prise d'une machine piratée. »
- Terminer à l'heure exacte.

## 5. Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**exercice bonus n°9** (1:23–1:27) — il est dans le support.
2. Raccourcir le débrief du sondage n°5 (opinion) à 90 secondes.
3. Compresser le panorama des outils (0:09–0:20) : citer trois noms, renvoyer au support.

**Ne JAMAIS couper :** l'Atelier de Synthèse 4 (sondages n°2-4), le quiz n°6-8, le cas Marriott, la clôture avec devoirs et teaser.

**Si vous êtes en avance :**
- Poser les questions de réflexion du support (l'effacement des traces, la normalisation chronophage, les règles qui auraient sauvé Marriott et Desjardins).
- Étendre l'atelier : « quelle règle de corrélation écririez-vous pour détecter cette attaque automatiquement ? » (motif : apostrophes en série + codes 200 + tailles croissantes).

## 6. Travail en autonomie (Self-paced)
* **Avant la session suivante (B18)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Log Analysis and SIEM Concepts"* (durée estimée : 1h30).
  * **Recherche autonome** : Chercher ce qu'est le **confinement** d'une machine compromise et citer une action technique permettant de l'isoler (déconnexion du câble réseau, VLAN d'isolement, règle de pare-feu locale).
