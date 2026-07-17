# Spécifications des slides — Session B17 : Outils SIEM & Analyse de logs
Parcours : B 20 sessions  |  Module : E — Opérations, détection & réponse  |  Format : Spécifications Markdown

> **Principe** : texte affiché minimal (mots-clés, chiffres, extraits de logs) ; le discours complet est dans le [plan de séance minuté](../plans-de-seance/B_S17_plan.md). Chaque interaction Livestorm est signalée sur la slide concernée.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Outils SIEM & Analyse de logs
  - Lire les traces, corréler les indices — et l'**Atelier de Synthèse 4**
  - Parcours B — Session B17
- **Notes orateur** : Accueil. B16 a présenté l'équipe (le SOC) ; ce soir, son instrument : le SIEM, et sa matière première : les journaux. Annoncer l'enquête collective de l'Atelier de Synthèse 4.
- **Visuel suggéré** : Flux de lignes de logs convergeant depuis plusieurs serveurs vers une console centrale d'analyse.
  - **alt-text** : Centralisation de journaux d'événements vers un concentrateur SIEM.

---

### Slide 2 — Le devoir de la semaine & objectifs
- **Type** : contenu
- **Points clés (bullets)** :
  - 💬 Chat : les **3 éléments obligatoires** d'une ligne de log ?
  - Objectifs : expliquer le SIEM (collecte, normalisation, corrélation, stockage) · lire un log brut · évaluer la réussite d'une attaque (codes HTTP, tailles) · mener l'enquête de l'Atelier 4.
  - Parcours : SIEM → anatomie d'un log → règles de corrélation → Marriott & Desjardins → **Atelier 4** → quiz.
- **Notes orateur** : Récolter dans le chat : horodatage, source, événement. Valider, compléter, puis dérouler le programme. Le fil rouge : les traces existent toujours — encore faut-il les lire.
- **Visuel suggéré** : Trois étiquettes (Quand ? Qui ? Quoi ?) posées sur une ligne de log agrandie.
  - **alt-text** : Les trois composantes obligatoires d'une ligne de journal.
- **Élément interactif** : Question chat (réinvestissement du devoir de B16).

---

### Slide 3 — 📊 Sondage n°1 : le chiffre qui fait mal
- **Type** : sondage
- **Points clés (bullets)** :
  - Délai moyen pour **identifier puis contenir** une violation de données ?
  - A) ~25 jours — B) ~90 jours — C) ~258 jours
  - Source : IBM, *Cost of a Data Breach*, 2024
- **Notes orateur** : Réponse C : 258 jours — presque neuf mois. Pendant ce temps, l'attaquant écrit son journal intime chez vous : chaque action laisse une ligne. Le drame n'est pas l'absence de traces, c'est l'absence de lecteur. Enchaîner : la machine qui lit pour nous.
- **Visuel suggéré** : Frise chronologique de 9 mois avec une silhouette d'intrus présente sur toute la longueur.
  - **alt-text** : Durée moyenne d'une violation de données avant identification et confinement.
- **Élément interactif** : Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — Le SIEM : 4 étapes
- **Type** : schéma
- **Points clés (bullets)** :
  - **1. Collecte** : agents + Syslog → base centrale
  - **2. Normalisation (parsing)** : formats hétérogènes → schéma commun
  - **3. Corrélation** : croiser les événements de machines différentes
  - **4. Stockage & visualisation** : archives probantes + tableaux de bord
- **Notes orateur** : Un pirate laisse une trace sur le pare-feu, une sur le serveur de fichiers, une sur l'annuaire. Séparées : anodines. Croisées : une intrusion qui se raconte. Personne ne lit des millions de lignes par jour — le SIEM, si. Insister : sans normalisation, pas de corrélation possible.
- **Visuel suggéré** : Entonnoir : logs disparates (XML, Syslog, pare-feu) entrant, alertes qualifiées sortant.
  - **alt-text** : Les quatre étapes de traitement d'un SIEM, de la collecte à l'alerte.

---

### Slide 5 — Panorama des outils
- **Type** : contenu
- **Points clés (bullets)** :
  - Payants : **Splunk** · **Microsoft Sentinel** · **Elastic Security**
  - Open-source (idéal PME) : **Wazuh** · **ELK** (Elasticsearch, Logstash, Kibana) · **Graylog Open**
  - Le coût réel : volume ingéré (Go/jour) + durée de rétention → d'où le **ciblage** des sources
- **Notes orateur** : Trente secondes, pas un catalogue : retenir qu'une PME a des options gratuites crédibles. Le vrai arbitrage est économique : on ne collecte pas tout, on cible — authentification, réseau, processus critiques. Détails dans le support.
- **Visuel suggéré** : Deux colonnes de logos (payant / open-source) avec un curseur budget en dessous.
  - **alt-text** : Panorama des solutions SIEM commerciales et open-source.

---

### Slide 6 — Anatomie d'un log web Apache
- **Type** : contenu
- **Points clés (bullets)** :
  - `203.0.113.88 - - [29/Jun/2026:16:42:57 +0200] "GET /admin/login.php HTTP/1.1" 200 4502`
  - **Qui** : IP source · **Quand** : horodatage + fuseau · **Quoi** : méthode + ressource
  - **Code d'état** : 200 traité · 400 requête invalide · 403 accès refusé · 404 introuvable · 500 erreur serveur
  - **Taille de la réponse** : l'indice oublié — une réponse anormalement grosse trahit une fuite
- **Notes orateur** : Décortiquer champ par champ en couleur. Marteler : « la taille, retenez-la — elle servira dans l'atelier ». 💬 Question chat : une requête isolée sur /admin/login.php, grave ? → signal faible ; la fréquence et la série font le diagnostic.
- **Visuel suggéré** : La ligne de log agrandie, chaque champ surligné d'une couleur avec sa bulle d'explication.
  - **alt-text** : Découpage commenté d'une ligne de journal Apache au format Common Log Format.
- **Élément interactif** : Question chat « le réflexe du lecteur de logs ».

---

### Slide 7 — Du log à la règle de corrélation
- **Type** : schéma
- **Points clés (bullets)** :
  - `Jun 29 22:15:30 srv-paye sshd[4012]: Failed password for invalid user admin from 198.51.100.42`
  - Une règle = **motif + seuil + fenêtre de temps → action**
  - Force brute : 10 × `Failed password` + 1 × `Accepted password`, même IP, < 60 s → **alerte critique** (+ isolement SOAR)
  - Autres motifs : voyage impossible · exfiltration (volume anormal) · scan de ports
- **Notes orateur** : Un échec de connexion, c'est la vie. Dix échecs puis un succès en une minute, c'est une histoire — et les histoires se détectent. Relier au SOAR de B16 pour l'action automatique. Annoncer que le voyage impossible revient en mini-scénario.
- **Visuel suggéré** : Équation visuelle : série de cadenas rouges + un cadenas vert → sirène d'alerte.
  - **alt-text** : Logique d'une règle de corrélation détectant une force brute réussie.

---

### Slide 8 — Affaire réelle : Marriott/Starwood (2018)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Intrusion : **2014** (chez Starwood) — rachat par Marriott : 2016 — découverte : **2018**
  - **4 ans** de présence · ~**339 millions** de dossiers clients (régulateur britannique) · passeports inclus
  - Détection : **une alerte** d'un outil de supervision de base de données
  - Amende ICO : **18,4 M£** (2020)
- **Notes orateur** : Dérouler la chronologie. Deux morales : on achète aussi les intrusions en cours (due diligence cyber, B13) ; une seule alerte bien placée sur l'actif critique a fait ce que quatre ans de silence n'avaient pas fait. 💬 Chat « l'énigme » : comment reste-t-on 4 ans invisible ? → comptes volés légitimes, petits volumes, périmètre hérité non supervisé.
- **Visuel suggéré** : Frise 2014→2018 avec le logo hôtel, le rachat au milieu, et l'unique alerte en fin de course.
  - **alt-text** : Chronologie de l'intrusion Starwood-Marriott, de 2014 à sa découverte en 2018.
- **Élément interactif** : Question chat « l'énigme Marriott ».

---

### Slide 9 — Le cas miroir : Desjardins (2019)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Un **employé** exfiltre des données pendant **26 mois** — **9,7 millions** de personnes
  - Découvert par… la **police** — aucune alerte interne
  - Rapport du Commissariat à la protection de la vie privée du Canada (2020) : copies massives non surveillées
  - Coût annoncé : **> 100 M$ CA** dès la première année (2019)
- **Notes orateur** : Le miroir de Marriott : la menace était à l'intérieur, et les traces aussi. Une règle sur les copies massives récurrentes, ou un outil DLP, aurait vu le motif. La journalisation ne vise pas que l'attaquant externe — elle est le seul témoin des abus internes.
- **Visuel suggéré** : Silhouette d'employé devant un écran, flux de données sortant discrètement vers un disque externe, compteur de mois qui défile.
  - **alt-text** : Exfiltration interne de données étalée sur vingt-six mois.

---

### Slide 10 — 🧪 Atelier de Synthèse 4 : l'enquête MedDistri
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Depuis l'Atelier 1 : DMZ en place + concentrateur de journaux
  - Cette nuit : le **WAF** (mode détection) signale des requêtes suspectes sur la boutique
  - À l'écran : l'extrait `access.log` — **5 lignes, une enquête**
  - Vos outils : les codes HTTP, les tailles de réponses, la chronologie
- **Notes orateur** : Lire les 5 lignes à voix haute SANS les interpréter (l'extrait complet est dans le support et affiché en grand). « Toute l'attaque est là. À vous de la reconstituer. » Rappeler la ligne 2 : tous les visiteurs ne sont pas des suspects.
- **Visuel suggéré** : Terminal affichant les cinq lignes de logs, loupe de détective posée sur la ligne 3.
  - **alt-text** : Extrait de cinq lignes de journal Apache à analyser collectivement.

---

### Slide 11 — Atelier 4 : votes & verdicts
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **n°2** : quelle attaque aux lignes 3-4 ? (Path Traversal / **SQLi** ✅ / DDoS)
  - 📊 **n°3** : code 200 + tailles 851 → 4522 → 6817 octets : réussite potentielle ? (**Oui** ✅ / Non)
  - 💬 Chat : que révèle la ligne 5 — et pourquoi est-elle plutôt **rassurante** (400 + 118 octets) ?
  - 📊 **n°4** : la riposte ? (**WAF en blocage + requêtes paramétrées + évaluation de la fuite** ✅)
- **Notes orateur** : Un vote → un débrief, dans l'ordre. N°2 : apostrophe, OR 1=1, UNION SELECT — la signature complète (B03). N°3 : la nuance qui fait les bons analystes : 200 = requête traitée ; c'est la TAILLE qui accable. Ligne 5 : traversée de répertoires vraisemblablement sans succès — 400 « requête invalide » + 118 octets, ni 200 ni volume (même raisonnement code+taille). N°4 : confinement + correction de la cause + qualification de la fuite (CNIL 72 h, B15) ; effacer les logs = détruire les pièces à conviction. Conclure : reconnaissance → extraction → élargissement en moins de 3 minutes.
- **Visuel suggéré** : Les trois questions empilées avec cases à cocher, extrait de logs en fond grisé.
  - **alt-text** : Les trois votes de l'Atelier de Synthèse 4 sur l'analyse de l'extrait de journal.
- **Élément interactif** : Sondages Livestorm n°2, 3, 4 + question chat.

---

### Slide 12 — Deux débats : le curseur & le voyage impossible
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **n°5 (opinion)** : un SIEM trace aussi les salariés — où placez-vous le curseur ? (Tout / **Ciblé et proportionné** / Minimum)
  - Cadre : proportionnalité, information des salariés, conservation ~6 mois (recommandation CNIL) — B15 s'applique aussi aux logs
  - 🤔 Mini-scénario : Paris 9h02 → Singapour 9h37. A) Ignorer (VPN ?) B) **Qualifier : contexte, appel, mesure conservatoire** ✅ C) Tout bloquer
- **Notes orateur** : N°5 sans bonne réponse, mais un cadre légal — et Desjardins en contrepoint : zéro surveillance interne se paie aussi. Mini-scénario : le VPN d'entreprise fabrique de faux voyages impossibles → contexte d'abord, puis canal indépendant (le contre-appel de B04), puis mesure proportionnée. Une alerte est une priorité d'enquête, pas un verdict.
- **Visuel suggéré** : Curseur à trois positions au-dessus ; planisphère Paris-Singapour avec deux horodatages en dessous.
  - **alt-text** : Sondage d'opinion sur la journalisation et scénario d'alerte de voyage impossible.
- **Élément interactif** : Sondage Livestorm n°5 + scénario A/B/C dans le chat.

---

### Slide 13 — Quiz de validation & bonus
- **Type** : quiz
- **Points clés (bullets)** :
  - 📊 **n°6** : à quoi sert la normalisation (parsing) ? → langue commune, condition de la corrélation
  - 📊 **n°7** : pourquoi centraliser les journaux à part ? → hors de portée de l'effacement par l'attaquant
  - 📊 **n°8** : 10 échecs + 1 succès, même IP, 60 s ? → alerte critique « force brute probablement réussie »
  - 📊 **n°9 (bonus)** : 500 connexions/10 s sur 5 ports ? → balayage de ports (reconnaissance)
- **Notes orateur** : Trois sondages, débrief 30 secondes chacun (éléments dans le support). Le bonus n°9 est le tampon : le couper si retard, il est dans le support. Fil conducteur des débriefs : réponse graduée, valeur probante, motifs d'attaque.
- **Visuel suggéré** : Quatre cartes de quiz numérotées, la dernière marquée « bonus ».
  - **alt-text** : Les quatre sondages de validation de fin de session.
- **Élément interactif** : Sondages Livestorm n°6, 7, 8 (+ n°9 bonus).

---

### Slide 14 — Synthèse, devoirs & prochaine session
- **Type** : récap
- **Points clés (bullets)** :
  - Un log = **horodatage + source + événement** · la corrélation transforme le bruit en alertes · les journaux déportés = pièces à conviction
  - 💬 Chat : « un mot que vous retenez »
  - Self-paced : IBM SkillsBuild *"Log Analysis and SIEM Concepts"* (~1h30) + recherche : le **confinement** d'une machine compromise (+ une action technique d'isolement)
  - Prochaine session (B18) : l'alerte a sonné — confiner, éradiquer, reconstruire
- **Notes orateur** : Boucler : vous savez désormais lire ce que le SOC de B16 regarde. Donner les devoirs (le confinement prépare directement B18). Teaser : « pourquoi ne faut-il JAMAIS débrancher la prise d'une machine piratée ? Réponse la semaine prochaine. » Terminer à l'heure.
- **Visuel suggéré** : Trois pictogrammes de synthèse (ligne de log, entonnoir, coffre-fort à preuves) + badge SkillsBuild.
  - **alt-text** : Slide de synthèse avec les devoirs et l'annonce de la session B18.
- **Élément interactif** : Question chat de clôture.
