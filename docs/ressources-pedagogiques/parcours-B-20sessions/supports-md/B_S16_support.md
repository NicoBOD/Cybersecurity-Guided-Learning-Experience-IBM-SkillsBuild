# Session B16 — Centre des opérations de sécurité (SOC) & supervision
Parcours : B 20 sessions  |  Module : E — Opérations de sécurité  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Qu'est-ce qu'un SOC ? (Security Operations Center)
    - Le cycle de vie d'une alerte : Vrai vs Faux Positif
    - Les indicateurs de performance (KPIs) du SOC : MTTD, MTTR
    - Une affaire réelle : SolarWinds (2020), l'attaque de la décennie révélée par... une alerte MFA vérifiée
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Le **SOC** surveille le système d'information 24h/24 pour détecter et répondre aux cyberattaques.
*   Les analystes sont organisés en niveaux : le **L1** qualifie et trie, le **L2** mène l'enquête technique, le **L3** résout la crise et chasse les menaces avancées.
*   Distinguer les **vrais positifs** (attaques réelles) des **faux positifs** (comportements légitimes inhabituels) est la mission quotidienne du L1.
*   Les performances du SOC se mesurent par le **MTTD** (rapidité de détection) et le **MTTR** (rapidité de réaction et de confinement).

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Décrire l'organisation humaine, les différents niveaux d'analystes (L1, L2, L3) et les missions d'un Centre d'Opérations de Sécurité (SOC) moderne.
* Modéliser le cycle de vie d'une alerte et qualifier des événements de sécurité pour identifier et écarter les faux positifs.
* Interpréter les indicateurs clés de performance (KPIs) opérationnels d'un SOC : le MTTD et le MTTR.

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** Selon le rapport CrowdStrike 2024, combien de temps s'écoule en moyenne entre l'intrusion initiale d'un attaquant et le début de son mouvement latéral (la propagation vers d'autres machines) ?

    - A) Environ une heure ✅
    - B) Environ une journée
    - C) Environ une semaine

    **Débrief mentor :** Réponse A : **62 minutes en moyenne** (CrowdStrike, rapport 2024) — et le record observé est d'à peine plus de **2 minutes**. Une heure : c'est le temps dont dispose le défenseur entre « l'attaquant est entré » et « l'attaquant se propage » (le mouvement latéral de B06). Toute la session de ce soir tient dans cette course contre la montre : qui regarde, comment on trie, et à quelle vitesse on réagit. Bienvenue dans la tour de contrôle — le SOC.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Les trois niveaux, en pratique**
Détaillez la vie réelle des paliers : le **L1** vit dans la console du SIEM (B17) — il applique les *playbooks* de qualification, clôt les faux positifs, escalade avec un dossier propre (horodatage, machines, comptes, premières vérifications) ; le **L2** investigue (processus, journaux, historique réseau — l'EDR de B08 est son microscope) et prescrit la neutralisation ; le **L3** gère les crises majeures et pratique le ***threat hunting*** : chercher les menaces qui n'ont déclenché AUCUNE alerte, en partant d'hypothèses (les TTP de B02-B03 : « si un attaquant utilisait cette technique chez nous, où verrait-on des traces ? »).

**2. La fatigue des alertes et la réponse SOAR**
Le problème central du SOC moderne : le volume. Des milliers d'alertes par jour, largement des faux positifs — d'où la **fatigue des alertes** (traiter superficiellement, finir par rater la vraie attaque : Target en contre-exemple ce soir). Deux réponses complémentaires : améliorer la qualité des règles de détection (moins mais mieux), et **automatiser** avec le SOAR (*Security Orchestration, Automation and Response*) : des *playbooks* automatisés — exemple canonique : un poste communique avec une IP malveillante connue (IoC de B02) → isolement réseau automatique par l'EDR, en secondes, même à 3 h du matin (l'exercice bonus).

**3. Le SOC externalisé (MSSP) : l'option réaliste des PME**
Expliquez l'économie du 24/7 : trois équipes en rotation (3×8), les week-ends, les congés — une surveillance continue exige au minimum 8 à 10 analystes, hors outillage. C'est pourquoi les PME passent par un **MSSP** (*Managed Security Service Provider*) : un SOC mutualisé, enrichi par la **CTI** (B02) — les IoC observés chez un client protègent tous les autres. Points de vigilance à l'externalisation : la connaissance du contexte métier (qu'est-ce qui est « normal » chez NOUS ?), les délais contractuels de réaction (le MTTR s'écrit dans le contrat), et la réversibilité.

---

### Glossaire

*   **Fatigue des alertes (Alert fatigue)** — Saturation des analystes par un volume excessif d'alertes (majoritairement des faux positifs), conduisant à des traitements superficiels et au risque de rater une attaque réelle.
*   **Faux Positif (FP)** — Alerte de sécurité déclenchée par un événement informatique légitime et sans danger pour le système.
*   **MSSP (Managed Security Service Provider)** — Prestataire opérant un SOC externalisé et mutualisé pour le compte de plusieurs clients.
*   **MTTD (Mean Time To Detect)** — Temps moyen écoulé entre le début d'une intrusion et sa détection par l'équipe de sécurité.
*   **MTTR (Mean Time To Respond)** — Temps moyen écoulé entre la détection d'une alerte et la neutralisation complète de l'incident.
*   **Playbook de sécurité** — Procédure documentée décrivant pas à pas les actions obligatoires à mener par l'analyste face à un type d'alerte spécifique.
*   **SOAR (Security Orchestration, Automation and Response)** — Plateforme d'automatisation exécutant des playbooks de réponse (ex. isolement automatique d'un poste) sans intervention humaine.
*   **SOC (Security Operations Center)** — Centre d'Opérations de Sécurité. Équipe centralisée chargée de la supervision cyber et de la réponse aux alertes, en continu (24/7).
*   **Threat hunting (Chasse aux menaces)** — Recherche proactive, par hypothèses, des menaces présentes dans le réseau qui n'ont déclenché aucune alerte automatique.

---

### Concepts clés

!!! info "À retenir"
    Les modules précédents ont posé les défenses ; le SOC les fait **vivre** : des humains organisés en paliers (trier, investiguer, résoudre), un cycle de qualification (vrai ou faux positif ?) et deux chronomètres (MTTD, MTTR). La leçon des grandes affaires : une alerte ne vaut que par l'humain qui la **vérifie** — et une minute de vérification peut révéler l'attaque de la décennie.

### 1. Qu'est-ce qu'un SOC ? (Security Operations Center)
Le **SOC** est la tour de contrôle de la sécurité d'une entreprise. C'est une entité centralisée (composée d'une équipe humaine et d'outils techniques) chargée de surveiller, détecter, analyser et répondre aux cybermenaces pesant sur le système d'information, 24 heures sur 24 et 7 jours sur 7.

#### L'organisation humaine en 3 niveaux d'expertise :
*   **Analyste L1 (Triage et Filtrage)** : C'est la première ligne de défense. L'analyste L1 surveille en permanence la console d'alertes. Son but est de trier le flux continu d'alertes pour éliminer les événements bénins (faux positifs) et escalader les menaces réelles (vrais positifs) vers le niveau supérieur.
*   **Analyste L2 (Investigation)** : Reçoit les alertes qualifiées et jugées suspectes par le L1. Il effectue une investigation approfondie (analyse des processus de la machine, examen de l'historique réseau) pour comprendre la méthode d'attaque de l'intrus et rédiger les consignes de neutralisation de la menace.
*   **Analyste L3 (Threat Hunter & Incident Response)** : Expert senior. Il intervient lors des crises majeures pour diriger les opérations de nettoyage et de reconstruction des serveurs. De plus, il cherche activement des menaces complexes tapies et cachées dans le réseau qui auraient échappé aux outils de détection automatiques (*threat hunting* — le rendez-vous promis depuis le cas de la Banque du Bangladesh en B02).

*   *L'analogie des urgences d'un hôpital* :
    *   **L'analyste L1** est l'infirmier d'accueil et de tri. Il prend le pouls des patients arrivant, écarte les petits bobos sans danger, et oriente les cas graves vers les lits de consultation.
    *   **L'analyste L2** est le médecin généraliste de garde. Il examine le patient, l'ausculte, demande des analyses de sang et pose le diagnostic de la maladie.
    *   **L'analyste L3** est le chirurgien spécialiste. Il intervient d'urgence au bloc opératoire pour traiter une crise cardiaque ou opérer un polytraumatisé.

Pour les PME, la surveillance 24/7 exige au minimum 8 à 10 analystes (rotations 3×8, week-ends, congés) : c'est pourquoi beaucoup externalisent auprès d'un **MSSP** — un SOC mutualisé, enrichi par le renseignement sur les menaces (CTI, B02).

### 2. Le cycle de vie d'une alerte : Vrai vs Faux Positif
Une alerte de sécurité commence par un événement technique brut (ex. une connexion réseau). Cet événement est analysé par les règles du SOC pour générer une alerte. L'analyste L1 doit qualifier cette alerte :

*   **Faux Positif (FP)** : Une activité légitime et inoffensive mais qui a déclenché une alerte car elle ressemble à un comportement suspect.
    *   *Exemple* : Un outil d'inventaire informatique interne qui scanne le réseau de l'entreprise à la recherche de serveurs. Le pare-feu le signale comme une tentative d'intrusion. L'analyste L1 doit identifier la machine d'inventaire et clore l'alerte comme Faux Positif.
*   **Vrai Positif (VP)** : Une menace réelle ou une activité malveillante avérée qui nécessite une intervention corrective immédiate.
*   **Le danger silencieux : la fatigue des alertes** — noyé sous les faux positifs, l'analyste finit par traiter superficiellement... et rater la vraie attaque. La qualité des règles de détection compte autant que leur quantité, et le **contexte** est l'arme du L1 : qui est l'utilisateur, où, quand, est-ce habituel ?

### 3. Les indicateurs de performance (KPIs) du SOC
Pour mesurer l'efficacité d'un SOC, les directeurs s'appuient sur deux métriques de temps fondamentales :

*   **MTTD (*Mean Time To Detect* / Temps Moyen de Détection)** : Le délai moyen s'écoulant entre le moment où un attaquant pénètre dans le système d'information et le moment où le SOC détecte son activité. Plus le MTTD est bas, plus vite l'alerte est donnée.
*   **MTTR (*Mean Time To Respond* / Temps Moyen de Réponse)** : Le délai moyen s'écoulant entre le moment où l'alerte est détectée par le SOC et le moment où la menace est complètement neutralisée (ex. machine isolée du réseau, compte piraté désactivé).
*   **Les deux vont ensemble** : détecter en 30 secondes ne sert à rien si l'on réagit en 24 heures — le rançongiciel aura chiffré le réseau (souvenez-vous : 62 minutes avant le mouvement latéral). D'où les **playbooks** (la réaction écrite à l'avance) et le **SOAR** (la réaction automatisée : isoler un poste en secondes, même à 3 h du matin).

### Activité — La garde de nuit du L1 (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Vous êtes analyste SOC L1 de garde pour EcoLog. Affichez chaque alerte avec son élément de contexte, laissez 30 secondes de lecture, puis lancez le sondage : Faux Positif ou Vrai Positif — et quelle action ? Débriefez après chaque vote.

*   **📊 Sondage n°2 — Alerte A :** Connexion administrative SSH réussie sur le serveur de paie RH à **3h15 du matin**, depuis une adresse IP publique localisée en Asie. *Contexte : l'administrateur officiel habite en France ; aucune intervention nocturne planifiée.* Votre qualification ?
    *   A) Faux positif : les admins travaillent parfois la nuit
    *   B) Vrai positif critique : escalade immédiate au L2, isoler la session, réinitialiser les identifiants ✅
    *   C) À revoir lundi matin avec l'administrateur
*   **📊 Sondage n°3 — Alerte B :** 80 tentatives de connexion échouées en 2 minutes sur l'intranet RH, puis une connexion réussie à 9h02. *Contexte : le compte appartient à une secrétaire présente au bureau, qui confirme par téléphone une touche « Verr Maj » activée par erreur.* Votre qualification ?
    *   A) Vrai positif : 80 échecs = force brute, on bloque le compte
    *   B) Faux positif : erreur de saisie confirmée par la vérification contextuelle — clore l'alerte en la documentant ✅
    *   C) Ni l'un ni l'autre : on ignore l'alerte sans la documenter
*   **📊 Sondage n°4 — Alerte C :** Un poste de la comptabilité exécute un script PowerShell copiant la base locale des utilisateurs vers un serveur externe. *Contexte : l'employé n'a rien lancé, sa machine ralentit fortement.* Votre qualification ?
    *   A) Faux positif : PowerShell est un outil d'administration légitime
    *   B) Vrai positif mineur : on planifie un antivirus pour demain
    *   C) Vrai positif majeur : isoler immédiatement le poste via l'EDR, puis escalader au L2 ✅

**Éléments de débriefing (pour le mentor) :**

- N°2 : le faisceau d'indices — serveur sensible + heure + géolocalisation + aucun ticket : tout crie « identifiants volés ». Le L1 n'attend pas d'être sûr à 100 % : il escalade avec un dossier propre. (Et rappelez B06 : l'alerte de 2h du matin non traitée, c'était Target.)
- N°3 : le réflexe d'or du L1 — **vérifier le contexte** avant de trancher : l'annuaire, puis l'appel. L'activité RESSEMBLAIT à une force brute ; le contexte dit erreur humaine. Et on documente la clôture : un faux positif non documenté reviendra demain.
- N°4 : Word→PowerShell→exfiltration : la chaîne comportementale type (l'EDR de B08 est fait pour ça). Isoler UN poste coûte peu, la propagation coûte tout — on isole D'ABORD, on investigue ensuite. « PowerShell est légitime » : oui, et c'est précisément pourquoi les attaquants l'adorent (B03 : *fileless*).

### 4. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **62 minutes en moyenne** entre l'intrusion initiale et le début du mouvement latéral — record observé : à peine plus de 2 minutes (CrowdStrike, rapport 2024).
    - **~18 000 organisations** ont téléchargé la mise à jour piégée de SolarWinds Orion (chiffres communiqués par l'éditeur, décembre 2020) — l'attaque révélée par une simple alerte MFA vérifiée.
    - **44 % des alertes de sécurité** n'étaient jamais investiguées dans les entreprises sondées (étude Cisco, 2017) — la fatigue des alertes, mesurée.

**Comment lire ces chiffres ?** (1) La fenêtre de réaction se compte en minutes : le SOC est une course. (2) La plus grande attaque de la décennie a été découverte par un analyste qui a pris la peine de vérifier UNE alerte. (3) Une alerte sur deux ignorée : le vrai risque du SOC n'est pas de manquer d'outils, mais de se noyer.

### 5. Une affaire réelle : SolarWinds (2020) — l'alerte qui valait dix mille intrusions

Décembre 2020. Chez **Mandiant** (alors FireEye), l'un des plus grands cabinets de cybersécurité au monde, une alerte de routine s'affiche : un **deuxième téléphone** vient d'être enrôlé pour la MFA sur le compte VPN d'un employé. Banal — les salariés changent de téléphone tous les jours. Mais l'analyste applique le playbook : il **appelle l'employé**. Réponse : « ce n'est pas moi. » Ce simple contre-appel (le réflexe de B04, version SOC) déclenche une investigation qui révèle l'impensable : Mandiant est compromis... par la mise à jour d'un logiciel légitime — **SolarWinds Orion**, un outil de supervision utilisé par des dizaines de milliers d'organisations. Des attaquants étatiques avaient piégé la chaîne de fabrication du logiciel (une attaque par la **chaîne d'approvisionnement**, comme NotPetya en B03) : environ **18 000 organisations** avaient téléchargé la mise à jour infectée, dont des agences fédérales américaines et des géants technologiques — une centaine ont été activement ciblées, pendant des **mois**, sans qu'aucune alerte ne sorte nulle part.

**Ce que ce cas illustre :** la plus grande campagne d'espionnage de la décennie n'a pas été détectée par une intelligence artificielle, mais par **un analyste qui a vérifié une alerte banale** — le contre-exemple exact de Target (B06), où les alertes généraient... et personne n'agissait ; la qualification contextuelle (appeler, vérifier) est LE geste professionnel du SOC ; et la victime qui détecte et **publie** (Mandiant a révélé l'affaire et partagé les IoC — la CTI de B02 en action) protège toute la communauté.

**Le contre-exemple, revisité — Target (2013, vu en B06) :** les outils avaient détecté le malware, le SOC de Bangalore avait remonté l'alerte... et la chaîne de traitement s'est arrêtée là : personne n'a agi à Minneapolis. Mêmes ingrédients (une alerte, un humain), issue inverse : 40 millions de cartes. La différence entre les deux affaires ne tient ni au budget ni aux outils — elle tient au **processus de qualification et d'escalade**. C'est tout l'objet des playbooks.

!!! tip "📊 Sondage Livestorm n°5 — Et chez vous ? (sondage d'opinion, pas de bonne réponse)"
    **Question :** Votre organisation dispose-t-elle d'une supervision de sécurité ?

    - A) Oui : un SOC interne (ou une équipe dédiée)
    - B) Oui : externalisée auprès d'un prestataire (MSSP)
    - C) Aucune supervision à ma connaissance / Je ne sais pas

    **Débrief mentor :** Sondage d'opinion — C est majoritaire dans les PME, et c'est le point aveugle français : des défenses (pare-feu, antivirus) mais **personne qui regarde**. Rappelez l'économie du 24/7 (8 à 10 analystes minimum) : pour une PME, la voie réaliste est le MSSP — en vérifiant trois choses au contrat : la connaissance du contexte métier, les délais de réaction garantis (le MTTR s'écrit dans le contrat), la réversibilité. Une supervision même partielle (alertes EDR + astreinte) vaut infiniment mieux que rien.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Vendredi, 17h50. Une alerte s'affiche : « nouvel appareil MFA enrôlé » sur le compte d'un administrateur. Vous l'appelez : pas de réponse — il est peut-être déjà parti en week-end. **Tapez A, B ou C dans le chat :**

    - A) Clore l'alerte : c'est sûrement lui, les gens changent de téléphone.
    - B) Traiter comme suspect : désactiver le nouvel appareil, suspendre les sessions du compte, poursuivre la vérification par un autre canal — et documenter. ✅
    - C) Laisser l'alerte ouverte et vérifier lundi matin.

    **Débrief mentor :** B — c'est mot pour mot l'alerte qui a révélé SolarWinds, et le week-end est précisément la fenêtre préférée des attaquants (rappel BEC B04 : le vendredi soir). Le calcul coût/risque est sans appel : désactiver un appareil MFA coûte cinq minutes et un léger désagrément lundi ; laisser un attaquant équipé d'un MFA valide tout un week-end coûte potentiellement l'entreprise. A parie l'entreprise sur une probabilité ; C offre 60 heures d'avance à l'adversaire (62 minutes suffisent, souvenez-vous).

---

### Questions de réflexion
1. Pourquoi une trop grande quantité d'alertes inoffensives (faux positifs) présente-t-elle un danger pour la sécurité réelle d'une entreprise ? (Recherchez le concept de « fatigue des alertes ».)
2. Si un SOC dispose d'outils de détection automatique ultra-performants qui alertent en 30 secondes (MTTD bas), mais que l'équipe met 24 heures à réagir et isoler les serveurs infectés (MTTR élevé), l'entreprise est-elle efficacement protégée contre un ransomware ? Expliquez le rôle des playbooks de sécurité pour réduire le MTTR.
3. Dans l'affaire SolarWinds, l'alerte décisive était banale (un appareil MFA ajouté). Qu'est-ce qui a fait la différence — et qu'est-ce que cela implique pour la conception des playbooks d'un SOC ?

**Corrigé / Éléments de réponse :**

1. La fatigue des alertes pousse les analystes à ignorer ou traiter superficiellement les notifications, augmentant le risque de rater une vraie attaque — 44 % d'alertes jamais investiguées (Cisco, 2017), et Target en démonstration.
2. Non : si le MTTR est de 24 h, le ransomware aura chiffré le réseau (le mouvement latéral commence en ~1 h). Les playbooks écrivent la réaction à l'avance, et le SOAR l'automatise (isoler un poste en secondes) — le MTTR passe d'heures à minutes.
3. La différence : un playbook qui imposait la **vérification humaine par un canal indépendant** (l'appel), et un analyste qui l'a appliqué sans se dire « c'est sûrement rien ». Implication : les playbooks doivent prévoir la vérification contextuelle des alertes « banales mais sensibles » (MFA, comptes à privilèges), pas seulement des alertes spectaculaires.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez l'organisation et le fonctionnement d'un SOC (Security Operations Center) comme le personnel des **urgences d'un grand hôpital** :
    - **L'analyste L1 (Triage)** est l'infirmier d'accueil. Il reçoit le flux continu de patients (alertes de sécurité), écarte les cas inoffensifs (un faux positif, comme une fausse alerte de toux), et escalade immédiatement les cas graves (un vrai positif, comme un arrêt cardiaque) vers le niveau supérieur.
    - **L'analyste L2 (Investigation)** est le médecin de garde. Il examine les antécédents médicaux du patient, demande des analyses de sang poussées (forensics de la machine) pour poser un diagnostic précis et rédiger la prescription (les étapes de nettoyage).
    - **L'analyste L3 (Incident Response & Threat Hunter)** est le chirurgien spécialiste. Il intervient d'urgence en salle d'opération pour traiter les cas critiques complexes et mène des recherches préventives de nouvelles maladies (chasse aux menaces cachées).

**Exemple d'application professionnelle :**
Dans le SOC d'une multinationale, l'analyste L1 reçoit une alerte d'un ordinateur exécutant un outil d'administration suspect à 2h du matin. Il vérifie le profil de l'employé (il s'agit d'un comptable non connecté à ces heures). Il escalade l'incident au L2 qui confirme une compromission par cheval de Troie et isole la machine du réseau local en moins de 30 minutes, contenant ainsi la propagation.

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour équiper un SOC (Security Operations Center) moderne et coordonner la réponse aux alertes via des playbooks :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Palo Alto Cortex XSOAR** : Leader du marché des SOAR, offrant l'automatisation complète de la réponse, la gestion intégrée des incidents et des playbooks interactifs.
    *   **Splunk SOAR (anciennement Phantom)** : Plateforme d'orchestration permettant d'automatiser les tâches de sécurité et d'accélérer les investigations lors d'alertes complexes.
    *   **Microsoft Sentinel / IBM QRadar SOAR** : Outils de corrélation SIEM/SOAR natifs cloud facilitant le travail d'escalade des analystes L1, L2 et L3.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **TheHive & Cortex** : Le duo open-source de référence pour la réponse à incident. TheHive sert de console de gestion des cas (tickets d'incident), tandis que Cortex exécute des analyses d'indicateurs (IoC) à l'aide de centaines de connecteurs gratuits.
    *   **Shuffle** : Solution SOAR open-source moderne permettant de lier et d'automatiser visuellement la réaction entre différents systèmes de sécurité (ex. isoler un hôte Wazuh lors d'une alerte).

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après le mini-scénario.

*   **📊 Sondage n°6 :** Quelle est la mission première de l'analyste L1 ?
    *   A) Reconstruire les serveurs après une attaque majeure
    *   B) Trier et qualifier le flux d'alertes (vrai ou faux positif) et escalader les menaces réelles ✅
    *   C) Négocier avec les attaquants en cas de rançongiciel
*   **📊 Sondage n°7 :** Que mesurent respectivement le MTTD et le MTTR ?
    *   A) Le temps de détection d'une intrusion, puis le temps de neutralisation après détection ✅
    *   B) Le nombre d'alertes traitées par jour et par analyste
    *   C) Le coût moyen d'un incident et son remboursement par l'assurance
*   **📊 Sondage n°8 :** Qu'est-ce qui distingue le *threat hunting* (L3) du travail d'alerte classique ?
    *   A) Il se pratique uniquement la nuit
    *   B) Il utilise des outils plus chers
    *   C) Il cherche proactivement, par hypothèses, les menaces qui n'ont déclenché AUCUNE alerte ✅

**Éléments de débriefing (pour le mentor) :**

- N°6 : le L1 est l'infirmier de tri des urgences — sa valeur : la qualification contextuelle rapide et l'escalade documentée. Ni héros solitaire, ni presse-bouton.
- N°7 : les deux chronomètres — et ils vont ensemble : détecter en 30 s ne sert à rien si l'on réagit en 24 h (62 minutes avant le mouvement latéral !).
- N°8 : le hunting part du principe que les outils ont raté quelque chose — hypothèse (TTP de B02-B03), recherche de traces, confirmation. C'est la réponse au « comment détecter un APT » posée depuis la Banque du Bangladesh.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Security Operations Center (SOC) Fundamentals"* (durée estimée : 1h30).
*   **Activité pratique** : Rechercher la définition d'un outil **SOAR** (*Security Orchestration, Automation, and Response*). Comprendre comment l'automatisation permet de bloquer automatiquement une machine compromise sans intervention humaine pour réduire le MTTR à quelques secondes.
*   [CERT-FR — Signalement d'incidents](https://www.cert.ssi.gouv.fr/)
*   [ANSSI — Prestataires de détection d'incidents](https://cyber.gouv.fr)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Rôle de l'automatisation en réponse à incident.
*   **📊 Sondage Livestorm n°9 :** Un incident de sécurité survient à 3 heures du matin. L'analyste SOC est absent. Quelle solution permet de confiner automatiquement l'attaque ?
    *   A) Le pare-feu local de la machine.
    *   B) Un playbook d'isolation automatique configuré dans le SOAR et l'EDR ✅
    *   C) Un script de redémarrage des serveurs.
*   **Guide d'animation (pour le mentor) :** Le SOAR assure la protection quand l'humain dort : IP malveillante contactée (IoC) → poste isolé en secondes. Le pare-feu local (A) laisse passer ce qu'il ne connaît pas ; redémarrer (C) détruit des preuves sans confiner (teaser B19 : préserver la RAM). Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **SOC** | La tour de contrôle : surveiller, détecter, qualifier, répondre — 24/7 (ou via un MSSP). |
| **L1 / L2 / L3** | Trier et qualifier / investiguer et prescrire / résoudre les crises et chasser (*threat hunting*). |
| **Faux positif** | Une activité légitime qui ressemble à une attaque — se qualifie par le CONTEXTE, se clôt documentée. |
| **Fatigue des alertes** | Le danger silencieux : noyé sous les FP, on rate le VP (44 % d'alertes jamais investiguées — Cisco 2017). |
| **MTTD / MTTR** | Les deux chronomètres : détecter vite ET neutraliser vite (62 min avant le mouvement latéral). |
| **Playbook** | La réaction écrite à l'avance — y compris la vérification humaine des alertes « banales mais sensibles ». |
| **SOAR** | La réaction automatisée : isoler en secondes, même à 3 h du matin. |
| **Threat hunting** | Chercher, par hypothèses, ce qui n'a déclenché aucune alerte. |

**La règle d'or de la session :** une alerte ne vaut que par l'humain (ou le playbook) qui la traite — qualifiez par le contexte, escaladez documenté, automatisez la première réponse. SolarWinds et Target racontent la même histoire avec deux fins : la différence, c'est la vérification.
