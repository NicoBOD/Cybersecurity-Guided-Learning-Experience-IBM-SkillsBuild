# Session B17 — Outils SIEM & Analyse de logs
Parcours : B 20 sessions  |  Module : E — Opérations, détection & réponse  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30) — inclut l'**Atelier de Synthèse 4**

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Qu'est-ce qu'un SIEM ? (collecte, normalisation, corrélation, stockage)
    - Anatomie d'une ligne de log : lire « Qui, Quand, Quoi » (et Où)
    - Les règles de corrélation : transformer des millions de lignes en quelques alertes
    - Deux affaires réelles : Marriott (4 ans de présence non détectée) et Desjardins (26 mois d'exfiltration interne)
    - L'**Atelier de Synthèse 4** : l'enquête collective dans les journaux web de MedDistri
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Le **SIEM** centralise, normalise, corrèle et stocke les journaux d'événements (logs) de sécurité de l'ensemble de l'entreprise.
*   Une ligne de log exploitable contient trois informations obligatoires : un **horodatage**, une **source** (IP, machine ou compte) et un **événement** — c'était votre recherche de la semaine.
*   L'analyse des codes d'état HTTP (200 vs 400/403/404) et de la **taille des réponses** permet d'évaluer si une tentative d'attaque web a réussi.
*   Les **règles de corrélation** du SIEM détectent automatiquement des enchaînements d'événements suspects pour lever des alertes en temps réel — c'est la matière première du SOC vu en B16.

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer le rôle d'un outil SIEM dans la centralisation, la normalisation, la corrélation et le stockage des événements de sécurité.
* Analyser et décoder des lignes de logs brutes (serveur web, authentification système) pour identifier une anomalie ou une cyberattaque et évaluer sa réussite.
* Décrire le principe d'une règle de corrélation logique et proposer les contre-mesures immédiates face à une attaque détectée dans les journaux (**Atelier de Synthèse 4**).

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** Selon le rapport IBM *Cost of a Data Breach* 2024, combien de temps s'écoule en moyenne entre le début d'une violation de données et le moment où elle est identifiée puis contenue ?

    - A) Environ 25 jours
    - B) Environ 90 jours
    - C) Environ 258 jours ✅

    **Débrief mentor :** Réponse C : **258 jours en moyenne** (IBM, 2024) — presque neuf mois. Pendant tout ce temps, l'attaquant laisse pourtant des traces : chaque connexion, chaque requête, chaque fichier copié écrit une ligne quelque part. Le problème n'est presque jamais l'absence de traces — c'est que personne ne les collecte, ne les croise, ne les lit. La session de ce soir vous apprend exactement cela : où sont les traces, comment les lire, et comment une machine — le SIEM — les lit pour vous.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. De la logique à la règle : écrire une détection**
Si des participants avancés demandent « concrètement, on écrit ça comment ? » : une règle de corrélation est un filtre + un seuil + une fenêtre temporelle + une action. Exemples canoniques à dérouler : la force brute (N échecs puis un succès, même source, fenêtre courte), le **voyage impossible** (deux connexions du même compte depuis deux pays incompatibles avec la vitesse d'un avion — le mini-scénario de ce soir), l'exfiltration (volume sortant anormal vers une destination inhabituelle, la ligne 4 de l'atelier en version réseau). Mentionnez **Sigma**, le format ouvert qui décrit une règle de détection une seule fois pour la convertir ensuite vers chaque SIEM (Splunk, Sentinel, Elastic…) — l'équivalent détection de ce que Syslog est au transport. Et le revers : chaque règle mal calibrée fabrique des faux positifs — le réglage des seuils est un travail continu du SOC (la fatigue des alertes de B16 naît ici).

**2. L'économie de la journalisation : pourquoi on ne collecte pas tout**
La question arrive toujours : « pourquoi ne pas tout journaliser ? ». Parce que la facture d'un SIEM se calcule en volume ingéré (par Go et par jour) et en durée de rétention : tout collecter coûte vite plus cher que le reste de la sécurité. D'où le **ciblage** : d'abord l'authentification (connexions, échecs, élévations de privilèges), le réseau (flux bloqués, requêtes DNS), l'exécution (processus inhabituels — le PowerShell de B16). Côté durées : les exigences varient selon les référentiels et les secteurs (certains standards de paiement imposent un an de rétention) ; pour les journaux de connexion des salariés, la CNIL recommande couramment une conservation de l'ordre de **six mois**, proportionnalité oblige — la journalisation trace aussi des humains, et le sondage n°5 ouvrira ce débat.

**3. Le déport des journaux : la mesure anti-attaquant par excellence**
L'effacement des traces locales est un geste standard de l'attaquant une fois les privilèges obtenus (les référentiels d'attaque le cataloguent sous « suppression d'indicateurs »). La parade architecturale : envoyer les journaux **en temps réel** vers un puits de logs distinct (Syslog, agents), idéalement en écriture seule depuis les sources, avec un horodatage fiable (serveurs de temps synchronisés — sans NTP cohérent, impossible de reconstituer une chronologie multi-machines). C'est aussi la condition de la valeur **probante** : des journaux centralisés, horodatés et non modifiables sont la base de l'investigation qui suivra un incident — le sujet exact de B18.

---

### Glossaire

*   **DLP (Data Loss Prevention)** — Famille d'outils détectant ou bloquant les fuites de données (copies massives, envois externes, périphériques USB) à partir de règles sur le contenu et le volume.
*   **Log (Journal d'événements)** — Fichier texte généré automatiquement par un système ou une application, décrivant chaque événement survenu : horodatage, source, action.
*   **Normalisation (Parsing)** — Transformation des journaux bruts de formats hétérogènes vers un schéma de données unique et comparable, condition préalable à la corrélation.
*   **Règle de corrélation** — Instruction logique croisant plusieurs événements (éventuellement issus de machines différentes) pour identifier un comportement d'attaque et lever une alerte.
*   **SIEM (Security Information and Event Management)** — Système logiciel centralisant, normalisant, corrélant et archivant les journaux de sécurité pour détecter des incidents en temps réel.
*   **Syslog** — Protocole réseau standard de transfert des messages de journaux d'une machine vers un serveur de collecte central.
*   **Temps de présence (Dwell time)** — Durée pendant laquelle un attaquant reste dans un système d'information avant d'être détecté.
*   **WAF (Web Application Firewall)** — Pare-feu applicatif placé devant un site web, qui inspecte les requêtes HTTP pour bloquer les attaques applicatives (injection SQL, traversée de répertoires…).

---

### Concepts clés

!!! info "À retenir"
    Le SOC (B16) est l'équipe ; le SIEM est son instrument principal. Tout repose sur une matière première humble : la ligne de log. Qui sait la lire sait reconstituer une attaque ; qui sait la corréler sait la détecter pendant qu'elle a lieu. Et la leçon des grandes affaires : les traces existaient — personne ne les regardait.

### 1. Qu'est-ce qu'un SIEM ?
Un **SIEM** (*Security Information and Event Management*) est le moteur logiciel centralisé d'un SOC. Son but : rassembler en temps réel tous les journaux d'événements générés par les équipements du système d'information (pare-feu, serveurs, postes, applications) pour y détecter des activités suspectes. Son traitement suit **4 étapes** :

1.  **La Collecte** : des agents logiciels installés sur les machines, ou des protocoles d'envoi standardisés (comme **Syslog**), transmettent les journaux vers la base centrale du SIEM.
2.  **La Normalisation (Parsing)** : les logs bruts arrivent dans des formats hétérogènes (XML Windows, Syslog Linux, format propriétaire du pare-feu). La normalisation les traduit dans un schéma unique : IP source, compte, action, résultat — dans des colonnes comparables.
3.  **La Corrélation** : le croisement logique des données normalisées. Le SIEM cherche des relations temporelles ou logiques entre des événements apparemment indépendants, survenus sur des machines différentes, pour reconstituer une attaque en cours.
4.  **Le Stockage & la Visualisation** : les journaux sont archivés de façon sécurisée (investigations futures, conformité) et présentés aux analystes via des tableaux de bord.

*Pourquoi c'est indispensable* : un pirate qui s'introduit laisse une trace sur le pare-feu, une autre sur le serveur de fichiers, une troisième sur le contrôleur de domaine. Regardées séparément, chacune est anodine ; croisées, elles racontent l'intrusion. Aucun humain ne peut lire des millions de lignes par jour — le SIEM, si.

### 2. Anatomie d'une ligne de log
Pour être exploitable, une ligne de log doit répondre à trois questions : **Qui, Quand, Quoi**. Vos recherches de la semaine l'ont montré : trois éléments sont obligatoires — l'**horodatage** (normalisé, idéalement en temps universel UTC), la **source** (IP, machine, compte) et l'**événement** (l'action et son résultat). Une quatrième question — **Où** (la machine ou le service visé) — est idéalement présente dans la ligne elle-même (comme `srv-paye` dans l'exemple SSH ci-dessous) ; à défaut, c'est le journal d'origine qui la fournit.

#### Un log web Apache (Common Log Format) :
`203.0.113.88 - - [29/Jun/2026:16:42:57 +0200] "GET /admin/login.php HTTP/1.1" 200 4502`

*   `203.0.113.88` : l'adresse IP du client (**qui**).
*   `[29/Jun/2026:16:42:57 +0200]` : date, heure, fuseau (**quand**).
*   `"GET /admin/login.php HTTP/1.1"` : la méthode HTTP, la ressource demandée (**quoi**), le protocole.
*   `200` : le **code d'état HTTP** — 200 signifie que le serveur a traité la requête avec succès (404 : ressource introuvable ; 400 : requête invalide, mal formée ; 403 : accès refusé ; 500 : erreur serveur).
*   `4502` : la **taille de la réponse** en octets — un indice souvent décisif : une réponse anormalement volumineuse peut trahir une fuite de données.

#### Un log d'authentification Linux (auth.log) :
`Jun 29 22:15:30 srv-paye sshd[4012]: Failed password for invalid user admin from 198.51.100.42 port 52345 ssh2`

On y lit : l'heure (quand), la machine cible `srv-paye` (où), le service `sshd` , l'événement `Failed password` (quoi — un échec de connexion) et l'IP d'origine (qui).

!!! question "💬 Question chat — Le réflexe du lecteur de logs"
    Dans la ligne Apache ci-dessus, quelqu'un demande la page de connexion de l'espace d'administration depuis Internet. **Dans le chat :** est-ce grave ? Qu'iriez-vous vérifier juste après ?

    **Éléments de débriefing :** une requête isolée sur `/admin/login.php` n'est pas une attaque — mais c'est un signal de reconnaissance classique. À vérifier : cette IP a-t-elle fait d'AUTRES requêtes (fréquence, pages sensibles, codes d'erreur en série) ? C'est exactement le travail que la corrélation automatise.

### 3. Les règles de corrélation logique
Une règle de corrélation transforme le bruit de fond de millions de lignes en quelques alertes ciblées. Sa structure : **une condition** (motif + seuil + fenêtre de temps) et **une action**.

!!! tip "Exemple de règle : détection de force brute SSH"
    *   **Condition** : *SI* plus de 10 échecs d'authentification (`Failed password` sous Linux, événement 4625 sous Windows) surviennent depuis la même IP source vers la même machine en moins de 60 secondes, *ET* qu'une connexion réussie (`Accepted password` / 4624) suit depuis cette même IP…
    *   **Action** : *ALORS* générer une alerte de priorité critique « Force brute probablement réussie » — et, si un SOAR est branché (B16), isoler préventivement la session.

Sans corrélation, un échec de connexion est un non-événement (tout le monde se trompe de mot de passe). C'est l'enchaînement — beaucoup d'échecs, puis un succès, même source, fenêtre courte — qui fait le diagnostic. Même logique pour le **voyage impossible** (deux connexions du même compte depuis deux pays en 30 minutes) ou l'**exfiltration** (volume sortant anormal vers une destination inconnue).

### 4. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **258 jours en moyenne** pour identifier puis contenir une violation de données (IBM, *Cost of a Data Breach*, 2024).
    - **10 jours** : temps de présence médian mondial d'un attaquant avant détection (Mandiant, *M-Trends*, 2024) — une médiane en forte baisse, en partie parce que les rançongiciels… s'annoncent eux-mêmes.
    - **~4 ans** : durée de présence des attaquants dans les systèmes de Starwood/Marriott avant détection (intrusion débutée en 2014, découverte en 2018 — procédure de l'ICO conclue en 2020).
    - **26 mois** : durée de l'exfiltration interne chez Desjardins avant sa découverte (rapport du Commissariat à la protection de la vie privée du Canada, 2020).

**Comment lire ces chiffres ?** (1) Médiane de 10 jours et moyenne de 258 jours ne se contredisent pas : la première mesure le temps avant détection (tiré vers le bas par les rançongiciels bruyants), la seconde ajoute le temps de reprise de contrôle — les intrusions discrètes, elles, durent des mois ou des années. (2) Marriott et Desjardins le montrent : les traces existaient dans les journaux ; c'est la collecte, la corrélation et la lecture qui manquaient. (3) La journalisation est votre machine à remonter le temps : sans elle, pas d'enquête possible — et pas de session B18.

### 5. Une affaire réelle : Marriott/Starwood (2018) — quatre ans d'intrusion, une requête pour tout révéler

Septembre 2018. Un outil de supervision des bases de données de la chaîne hôtelière **Marriott** signale une requête anormale sur la base de réservations héritée de **Starwood**, rachetée deux ans plus tôt. L'investigation qui suit remonte le fil : les attaquants étaient présents dans les systèmes de Starwood **depuis 2014** — quatre ans, dont deux APRÈS le rachat. Outils d'accès à distance, vol d'identifiants, extraction progressive : environ **339 millions de dossiers clients** concernés dans le monde selon le régulateur britannique, incluant des numéros de passeport. L'ICO infligera à Marriott une amende de **18,4 millions de livres** (2020), en soulignant un point clé : lors du rachat, Marriott a hérité d'un système déjà compromis — et quatre années de journaux n'ont jamais fait l'objet d'une surveillance capable de révéler l'intrusion.

**Ce que ce cas illustre :** le temps de présence n'est pas une abstraction — quatre ans de traces (connexions, requêtes, exports) attendaient dans les journaux qu'une corrélation les lise ; une **seule alerte bien placée** (sur la base de données, l'actif critique) a fait ce que quatre ans de silence n'avaient pas fait ; et la sécurité s'audite AVANT un rachat (la *due diligence* cyber de B13) — on n'achète pas seulement une entreprise, on achète aussi ses intrusions en cours.

**Le cas miroir — Desjardins (2019) : la menace était à l'intérieur.** Premier groupe financier coopératif canadien, Desjardins révèle en juin 2019 qu'un **employé** du service marketing a exfiltré pendant environ **26 mois** les données personnelles de ce qui sera finalement évalué à **9,7 millions de personnes**. Aucune alerte interne : c'est une enquête de **police** qui met l'entreprise sur la piste. Le rapport du Commissariat à la protection de la vie privée du Canada (2020) pointe l'absence de surveillance des copies massives de données par les employés — précisément ce qu'une règle de corrélation (volume anormal, support amovible, récurrence) ou un outil **DLP** aurait pu détecter. Coût annoncé par l'entreprise : plus de 100 millions de dollars canadiens dès la première année (2019). La journalisation ne vise pas que l'attaquant externe : elle est aussi le seul témoin des abus internes.

!!! question "💬 Question chat — L'énigme Marriott"
    **Dans le chat :** à votre avis, comment des attaquants peuvent-ils rester 4 ans dans un système d'information sans être vus ? Citez au moins une raison.

    **Éléments de débriefing :** attendez (et complétez) : pas de SIEM sur le périmètre hérité, alertes non branchées sur les bons actifs, attaquants discrets (petits volumes, horaires normaux, comptes légitimes volés), équipes absorbées par la fusion. Le fil conducteur : la discrétion de l'attaquant ne laisse AUCUNE chance à une détection non outillée — et toutes ses traces à une détection outillée.

### Atelier de Synthèse 4 — L'enquête dans les journaux de MedDistri (Sondages Livestorm n°2 à 4 + chat)

**Contexte (à présenter à l'écran) :** depuis l'Atelier 1 (B08), MedDistri a déployé sa DMZ et un concentrateur de journaux. Cette nuit, le pare-feu applicatif (WAF) en mode détection a signalé des requêtes suspectes sur la boutique en ligne. Voici l'extrait du `access.log` Apache — cinq lignes, une enquête :

```text
Ligne 1 : 203.0.113.66 - - [08/Jul/2026:20:58:47 +0200] "GET /product.php?id=1 HTTP/1.1" 200 851
Ligne 2 : 198.51.100.23 - - [08/Jul/2026:20:59:10 +0200] "GET /index.php HTTP/1.1" 200 1204
Ligne 3 : 203.0.113.66 - - [08/Jul/2026:21:00:15 +0200] "GET /product.php?id=1' OR 1=1-- HTTP/1.1" 200 4522
Ligne 4 : 203.0.113.66 - - [08/Jul/2026:21:00:38 +0200] "GET /product.php?id=1' UNION SELECT login, motdepasse FROM clients-- HTTP/1.1" 200 6817
Ligne 5 : 203.0.113.66 - - [08/Jul/2026:21:01:02 +0200] "GET /admin/../../etc/passwd HTTP/1.1" 400 118
```

*   **📊 Sondage n°2 — Le diagnostic :** Quelle attaque est tentée aux lignes 3 et 4 ?
    *   A) Une traversée de répertoires (Path Traversal)
    *   B) Une injection SQL (SQLi) ✅
    *   C) Un déni de service (DDoS)
*   **📊 Sondage n°3 — Le verdict :** D'après le code d'état HTTP `200` et l'évolution de la taille des réponses (851 → 4522 → 6817 octets), la tentative a-t-elle potentiellement réussi ?
    *   A) Oui : le serveur a répondu favorablement, et le volume anormal suggère que des données ont été renvoyées ✅
    *   B) Non : la requête a été bloquée par le serveur
*   **📊 Sondage n°4 — La riposte :** Quelles contre-mesures immédiates recommandez-vous à MedDistri ?
    *   A) Éteindre définitivement le serveur web et attendre
    *   B) Bloquer l'IP `203.0.113.66` sur le WAF, passer le WAF en mode blocage, et corriger l'application (requêtes paramétrées) — puis évaluer l'ampleur de la fuite ✅
    *   C) Effacer les journaux compromis et réinstaller le serveur au plus vite

**Éléments de débriefing (pour le mentor) :**

- **N°2 :** l'apostrophe `'` qui casse la syntaxe SQL, le `OR 1=1` (condition toujours vraie) puis le `UNION SELECT` qui greffe une seconde requête : la signature SQLi au complet (revue de B03). La ligne 2 (`198.51.100.23`) est un visiteur légitime — l'enquête commence toujours par isoler QUI fait QUOI.
- **N°3 :** nuance importante : le code 200 dit « le serveur a traité la requête », pas « des données ont fui » — c'est la **taille de la réponse** qui accable : 851 octets pour une fiche produit normale, 6817 quand la requête greffée demande la table `clients`. Chronologie complète en moins de 3 minutes : reconnaissance (ligne 3), extraction (ligne 4), tentative d'élargissement (ligne 5 — une traversée de répertoires, **vraisemblablement sans succès** : code 400 « requête invalide » et réponse minuscule de 118 octets, un simple message d'erreur — ni 200, ni volume).
- **N°4 :** B enchaîne le confinement (bloquer l'IP, activer le blocage WAF), la correction de la cause (requêtes paramétrées — le correctif définitif contre la SQLi) et la qualification de l'impact (quelles données la table `clients` expose-t-elle ? → si données personnelles : notification CNIL sous 72 h, réflexe de B15). A détruit la disponibilité sans traiter la cause ; C détruit **les preuves** — les journaux sont désormais des pièces à conviction (teaser B18).
- **Chat (pendant le vote n°3)** : « que révèle la ligne 5, et pourquoi est-elle plutôt rassurante ? » — l'attaquant a aussi tenté de lire `/etc/passwd` ; le code 400 (« requête invalide ») ne prouve pas à lui seul un blocage, mais l'absence de 200 ET la réponse minuscule (118 octets) indiquent que rien de volumineux n'est sorti — appliquer à la ligne 5 le même raisonnement code+taille que pour le vote n°3.

!!! tip "📊 Sondage Livestorm n°5 — Le curseur de la journalisation (sondage d'opinion, pas de bonne réponse)"
    **Question :** Un SIEM trace tout — y compris l'activité quotidienne des salariés. Où placeriez-vous le curseur dans votre organisation ?

    - A) Tout journaliser : la sécurité d'abord, on trie ensuite
    - B) Journaliser de façon ciblée et proportionnée, avec information des salariés
    - C) Le minimum : la vie privée des salariés d'abord

    **Débrief mentor :** Pas de bonne réponse au sondage — mais un cadre légal : la journalisation des salariés doit être **proportionnée**, portée à leur connaissance, et limitée dans le temps (la CNIL recommande couramment une conservation de l'ordre de six mois pour les journaux de connexion — écho direct de B15 : minimisation et limitation de conservation s'appliquent AUSSI aux logs). Le point d'équilibre pratique est proche de B : cibler l'authentification, le réseau et les processus critiques — pas les frappes clavier. Et rappelez Desjardins : l'absence totale de surveillance interne se paie aussi.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Le SIEM lève une alerte « voyage impossible » : le compte d'une commerciale s'est connecté depuis Paris à 9h02, puis depuis Singapour à 9h37. **Tapez A, B ou C dans le chat :**

    - A) Ignorer : elle utilise probablement un VPN personnel, ça arrive.
    - B) Qualifier : vérifier si l'entreprise utilise un VPN sortant en Asie, appeler la commerciale, et suspendre les sessions du compte au moindre doute. ✅
    - C) Bloquer immédiatement tous les comptes du domaine par précaution.

    **Débrief mentor :** B — la démarche exacte du L1 de B16, appliquée à une alerte de corrélation : le **contexte** d'abord (le VPN d'entreprise peut créer de faux voyages impossibles — c'est le faux positif classique de cette règle), la vérification par un canal indépendant ensuite (l'appel — le contre-appel de B04, encore lui), la mesure conservatoire proportionnée si le doute persiste. A parie sur une hypothèse sans la vérifier ; C punit 200 salariés pour une alerte non qualifiée. Une règle de corrélation ne donne jamais une certitude : elle donne une **priorité d'enquête**.

---

### Questions de réflexion
1. Un attaquant qui vient de compromettre un serveur avec des droits d'administrateur cherche généralement à effacer les journaux locaux. Comment l'architecture de journalisation d'un SIEM rend-elle cette manœuvre inefficace ?
2. Pourquoi la normalisation (parsing) est-elle l'étape la plus chronophage lors de l'intégration d'un nouvel équipement dans un SIEM ?
3. Marriott a découvert quatre ans d'intrusion grâce à une alerte sur sa base de données ; Desjardins n'a rien détecté en 26 mois. Quelles règles de corrélation ou de surveillance auraient pu révéler chacune de ces deux affaires plus tôt ?

**Corrigé / Éléments de réponse :**

1. Les journaux sont expédiés **en temps réel** vers un serveur de collecte distinct (Syslog, agents), hors de portée de la machine compromise : l'attaquant peut effacer ses traces locales, la copie centralisée existe déjà. C'est aussi ce qui donne leur valeur probante aux journaux.
2. Chaque source (pare-feu, Windows, Linux, application métier) écrit dans un format différent : il faut construire et maintenir les règles de traduction champ par champ vers le schéma commun — sans normalisation correcte, la corrélation compare des choux et des carottes.
3. Marriott : une surveillance des requêtes anormales sur la base de réservations (volume, horaires, comptes utilisés) — c'est précisément l'alerte qui a fini par fonctionner en 2018, quatre ans trop tard. Desjardins : une règle sur les **copies massives récurrentes** de données clients par un même compte interne (volume cumulé, périodicité, exports vers supports personnels) ou un outil DLP — la menace interne se détecte par le comportement, pas par la signature.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez le travail d'un SIEM comme une **enquête policière** en continu :
    - **Les logs** sont les indices bruts éparpillés partout : enregistrements de la caméra du hall, historique des badges, registre des visiteurs.
    - **La normalisation (parsing)** traduit ces indices, écrits dans des formats différents, en fiches standardisées et comparables dans la base du détective.
    - **La corrélation** est le raisonnement du détective : « si la même personne a badgé à Paris à 14h00 ET à Lyon à 14h15, il y a usurpation. » Une ligne isolée n'a pas de sens ; c'est le croisement qui révèle l'attaque.
    - **Le stockage sécurisé** est la salle des scellés : les indices y sont conservés intacts pour le procès (l'investigation de B18).
    Autre image utile : le journal d'événements est la **boîte noire** de l'avion — on espère ne jamais en avoir besoin, mais quand l'accident survient, c'est elle qui raconte ce qui s'est réellement passé.

**Exemple d'application professionnelle :**
Le RSSI d'un site e-commerce configure son SIEM avec une règle : si une IP externe envoie plus de 20 requêtes contenant une apostrophe `'` dans les paramètres en moins de 10 secondes ET reçoit des codes HTTP 200, générer une alerte critique et demander au WAF de basculer cette IP en liste de blocage — la version automatisée, en somme, de l'enquête que vous venez de mener dans l'Atelier 4.

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour centraliser, normaliser et corréler les journaux d'événements :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Splunk Enterprise Security** : le leader historique des SIEM sur site et cloud, réputé pour sa puissance d'analyse et la flexibilité de ses requêtes de détection.
    *   **Microsoft Sentinel** : SIEM cloud-natif, intégration native des journaux Microsoft 365, Active Directory et Azure.
    *   **Elastic Security** : SIEM construit sur Elasticsearch, reconnu pour ses performances de recherche.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **Wazuh** : plateforme XDR/SIEM open-source, collecte par agents, règles de détection riches, réponses actives.
    *   **Elastic Stack (ELK : Elasticsearch, Logstash, Kibana)** : la pile classique pour collecter (Logstash), stocker (Elasticsearch) et visualiser (Kibana) les journaux.
    *   **Graylog Open** : gestion de logs open-source robuste, idéale pour de gros volumes Syslog.

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après le mini-scénario.

*   **📊 Sondage n°6 :** À quoi sert la normalisation (parsing) dans un SIEM ?
    *   A) À compresser les journaux pour économiser du stockage
    *   B) À traduire des formats de logs hétérogènes vers un schéma commun, condition de la corrélation ✅
    *   C) À chiffrer les journaux pour les rendre confidentiels
*   **📊 Sondage n°7 :** Pourquoi centralise-t-on les journaux sur un serveur de collecte distinct des machines qui les produisent ?
    *   A) Pour accélérer les machines de production
    *   B) Parce que le protocole Syslog l'impose
    *   C) Parce qu'un attaquant efface d'abord ses traces locales : le déport en temps réel les met hors de sa portée ✅
*   **📊 Sondage n°8 :** Le SIEM observe 10 « Failed password » puis un « Accepted password » depuis la même IP en 60 secondes. Que doit faire la règle de corrélation ?
    *   A) Rien : des échecs de connexion arrivent tous les jours
    *   B) Lever une alerte critique « force brute probablement réussie » (et isoler la session si un SOAR est branché) ✅
    *   C) Bloquer immédiatement tout le réseau de l'entreprise

**Éléments de débriefing (pour le mentor) :**

- N°6 : sans langue commune, pas de croisement possible — le parsing est ingrat mais fondateur (et chronophage : question de réflexion n°2).
- N°7 : le déport temps réel est LA parade à l'effacement de traces — et la condition de la valeur probante des journaux (B18 arrive).
- N°8 : l'enchaînement échecs→succès est le motif ; la réponse graduée (alerte critique, pas coupure générale) est la bonne échelle — revoyez le mini-scénario : une alerte est une priorité d'enquête, pas un verdict.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Log Analysis and SIEM Concepts"* (durée estimée : 1h30).
*   **Recherche de syntaxe** : Rechercher les formats standardisés **CEF** (*Common Event Format*) et **LEEF** (*Log Event Extended Format*) pour voir comment l'industrie structure les journaux échangés entre outils.
*   [ANSSI — Recommandations sur la journalisation](https://cyber.gouv.fr)
*   [CNIL — Tracer les accès et gérer les journaux](https://www.cnil.fr)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Détection de balayages réseau.
*   **📊 Sondage Livestorm n°9 :** Vous observez dans les journaux réseau 500 connexions échouées en 10 secondes vers des ports différents (21, 22, 80, 443, 3389), provenant de la même IP externe. Que détectez-vous ?
    *   A) Un test de connexion normal d'un utilisateur
    *   B) Un balayage de ports (port scanning) automatisé : un attaquant cartographie les services ouverts ✅
    *   C) Une mise à jour du pare-feu
*   **Guide d'animation (pour le mentor) :** le balayage de ports est l'étape de **reconnaissance** (B02-B03) : l'attaquant sonne à toutes les portes pour trouver celle qui s'ouvre. Dans un SIEM, c'est l'une des règles les plus simples à écrire (N ports distincts, même source, fenêtre courte) — et un excellent signal d'alerte précoce. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **SIEM** | Collecte, normalise, corrèle, archive : des millions de lignes → quelques alertes qui comptent. |
| **Log (journal)** | Horodatage + source + événement : la trace élémentaire — la boîte noire du SI. |
| **Normalisation** | La langue commune : traduire des formats hétérogènes pour pouvoir corréler. |
| **Règle de corrélation** | Motif + seuil + fenêtre de temps → alerte (force brute, voyage impossible, exfiltration…). |
| **Codes HTTP + taille** | 200 = requête traitée ; la taille de réponse anormale trahit la fuite (Atelier 4). |
| **Déport des journaux** | Envoi temps réel vers un puits central : l'attaquant ne peut plus effacer ses traces. |
| **Temps de présence** | Médiane 10 jours (Mandiant 2024) — mais Marriott : 4 ans, Desjardins : 26 mois. |
| **WAF** | Le pare-feu applicatif web : détecte puis bloque SQLi et traversées de répertoires. |

**La règle d'or de la session :** un journal qu'on ne collecte pas n'existe pas, et un journal que personne ne lit ne protège personne — collectez ciblé, centralisez hors de portée de l'attaquant, corrélez pour transformer le bruit en alertes. Marriott et Desjardins racontent la même histoire : les traces étaient là ; il manquait quelqu'un — ou quelque chose — pour les lire.
