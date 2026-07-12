# Support de cours — Session 06 : Opérations de sécurité & gestion des vulnérabilités
Parcours : A 8 sessions  |  Module : SecOps & Vulnérabilités  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - La surveillance active : Le couple SOC et SIEM
    - Identifier les failles : Scans de vulnérabilités vs Test d'intrusion
    - Prioriser la remédiation : Comprendre le score CVSS
    - La vulnérabilité en chiffres et deux cas réels : Equifax (2017) et Log4Shell (2021)
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

Une politique de sécurité robuste ne se limite pas à installer des protections statiques : elle exige une surveillance active et continue. Ce support de cours détaille le fonctionnement des centres d'opérations de sécurité (*SOC*) et des outils de corrélation de journaux d'événements (*SIEM*), qui constituent les yeux et les oreilles de la cybersécurité moderne. Vous étudierez la notion essentielle de journalisation (*logs*), trace numérique indispensable pour détecter et comprendre les attaques. Nous aborderons ensuite la gestion des vulnérabilités logicielles, en apprenant à faire la différence entre un scan automatisé et un test d'intrusion. Enfin, vous apprendrez à déchiffrer et à interpréter les scores du système de notation internationale *CVSS* afin de planifier et prioriser de manière pragmatique l'application des correctifs de sécurité (*patchs*) sans impacter l'activité opérationnelle de votre entreprise. Deux affaires réelles — dont un correctif ignoré qui a coûté 700 millions de dollars — démontreront que ces sujets d'apparence technique sont en réalité des enjeux de survie d'entreprise.

### Objectifs de la session

À l'issue de cette session, vous serez capable de :

- **Expliquer** le rôle du couple SOC/SIEM et le travail de qualification des alertes (vrai positif / faux positif).
- **Distinguer** un scan de vulnérabilités automatisé d'un test d'intrusion mené par un expert, et leurs usages respectifs.
- **Interpréter** un score CVSS et le pondérer par le contexte d'exposition pour prioriser les correctifs.
- **Structurer** une démarche de gestion des correctifs qui concilie sécurité et continuité d'activité.

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** À votre avis, combien de nouvelles vulnérabilités (CVE) ont été publiées dans le monde en 2024 ?

    - A) Environ 4 000
    - B) Environ 15 000
    - C) Environ 40 000 ✅
    - D) Environ 500

    **Débrief mentor :** Environ 40 000 — un record historique, soit plus de **100 nouvelles failles référencées par jour**. Message clé de la session : personne ne peut tout corriger tout de suite. La gestion des vulnérabilités n'est donc pas une affaire de perfection mais de **priorisation** — et c'est exactement ce que vous saurez faire dans 90 minutes.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Le fonctionnement d'un SOC (Security Operations Center)**
Détaillez l'organisation d'un SOC en Niveaux (Tier 1, Tier 2, Tier 3).
- Le T1 trie les événements bruts du SIEM (Security Information and Event Management) et gère les faux positifs.
- Le T2 investigue les incidents confirmés.
- Le T3 fait du *Threat Hunting* proactif pour trouver des menaces invisibles.

**2. Gestion des vulnérabilités et scoring CVSS**
Expliquez comment fonctionne le système CVSS (Common Vulnerability Scoring System). Précision de version : le standard actuel est **CVSS v4.0** (publié fin 2023 par le FIRST), mais la v3.1 reste très répandue dans les outils et les bulletins ; l'échelle qualitative (Faible/Moyenne/Élevée/Critique) est commune aux deux. Montrez qu'une faille notée 9.8 (Critique) signifie souvent qu'elle est exploitable à distance, sans authentification, et avec un impact total sur le système. Discutez de la priorisation des patchs (*Patch Management*) : le score brut ne suffit pas, l'exposition réelle de l'actif compte autant.

**3. L'automatisation : du SIEM au SOAR**
Expliquez la "fatigue des alertes" subie par les analystes. Introduisez la technologie SOAR (Security Orchestration, Automation, and Response) qui permet de créer des *Playbooks* automatisés (ex : isoler automatiquement un poste de travail du réseau s'il communique avec une adresse IP malveillante connue).

**4. Le tempo de l'attaquant s'accélère (point d'actualité)**
Les observations des CERT et des éditeurs convergent : les vulnérabilités critiques sont désormais exploitées massivement **quelques jours — parfois quelques heures — après leur publication**, les attaquants automatisant la recherche de systèmes non corrigés (souvenez-vous du brise-glace d'A3 : Internet est scanné en permanence). Conséquence pédagogique : la fenêtre « publication du correctif → application du correctif » est devenue la métrique de survie n°1, et c'est elle que les deux cas réels de cette session illustrent.

---

### Glossaire

*   **CVE (Common Vulnerabilities and Exposures)** — Dictionnaire public recensant et identifiant de manière unique les failles de sécurité logicielles et matérielles connues (ex. CVE-2021-44228).
*   **CVSS (Common Vulnerability Scoring System)** — Système de notation standardisé (version actuelle : 4.0) évaluant la gravité d'une vulnérabilité sur une échelle de 0.0 (inoffensive) à 10.0 (critique).
*   **Faux Positif** — Une alerte de sécurité déclenchée à tort par un outil de surveillance face à une activité légitime (ex. un employé légitime qui se trompe de mot de passe trois fois).
*   **Log (Journal d'événements)** — Fichier texte généré automatiquement par un système, une application ou un équipement, enregistrant les actions, connexions et erreurs survenues chronologiquement.
*   **Patch (Correctif)** — Mise à jour logicielle publiée par un éditeur pour corriger des erreurs de programmation ou combler des failles de sécurité.
*   **Pentest (Test d'intrusion)** — Audit offensif mené par un expert humain qui tente de s'introduire dans le système en conditions réelles, avec une autorisation écrite préalable (cadre vu en A1 et approfondi en A7).
*   **SIEM (Security Information and Event Management)** — Logiciel centralisant les journaux d'événements (logs) de divers équipements réseau et serveurs pour y appliquer des règles de corrélation et lever des alertes en cas de comportement suspect.
*   **SOAR (Security Orchestration, Automation and Response)** — Couche d'automatisation qui exécute des réponses prédéfinies (playbooks) aux alertes du SIEM, pour soulager les analystes de la volumétrie.
*   **SOC (Security Operations Center)** — Centre opérationnel où des analystes surveillent et analysent en continu la sécurité du système d'information pour détecter les incidents.
*   **Threat Hunting (Chasse aux menaces)** — Démarche proactive consistant à rechercher dans le système des traces de compromission qui n'ont déclenché aucune alerte.

---

### 1. La surveillance active : Le couple SOC et SIEM

!!! info "À retenir"
    Une caméra que personne ne regarde n'a jamais arrêté un cambrioleur. Les logs sans SIEM, et le SIEM sans analystes, ne protègent rien : **la détection est une chaîne — outil, corrélation, humain.**

Pour sécuriser une grande infrastructure, il est impossible de regarder manuellement les écrans de chaque ordinateur. On centralise les informations.

#### A. Les Journaux d'événements (Logs) : La trace numérique
Chaque fois qu'un utilisateur se connecte, qu'un fichier est modifié ou qu'un pare-feu bloque un flux, une ligne de log est générée.
*Exemple de log d'accès simplifié* :
```text
2026-06-29 16:30:12 | IP: 192.168.1.100 | User: j.dupont | Action: LOGIN_SUCCESS | App: Intranet
```
Ces logs sont indispensables pour comprendre le scénario d'une attaque passée ou détecter une intrusion en cours. Ils sont aussi une obligation implicite : souvenez-vous du chrono des 72 heures de la session A5 — sans journalisation, impossible de savoir quoi notifier à la CNIL, ni même de savoir qu'il y a quelque chose à notifier.

#### B. Le SIEM : Le moteur de corrélation
Le SIEM reçoit des millions de lignes de logs par jour provenant de toutes les machines. Grâce à des règles prédéfinies, il détecte des corrélations suspectes :

* *Règle de corrélation* : Si la machine A subit 50 échecs de connexion en 1 minute (log de sécurité Windows) ET qu'immédiatement après, elle envoie 10 Go de données vers Internet (log pare-feu), ALORS générer une alerte critique pour "Suspicion d'attaque par force brute réussie".

Chaque événement isolé est anodin (qui n'a jamais raté son mot de passe ?) ; c'est la **combinaison** qui fait l'attaque. Le SIEM est payé pour voir les combinaisons.

#### C. Le SOC : Les analystes humains
L'alerte générée par le SIEM est prise en charge par un analyste SOC. L'analyste doit rapidement qualifier l'alerte : s'agit-il d'un **vrai incident** exigeant une réaction immédiate, ou d'un **faux positif** (une alerte déclenchée à tort par une activité bénigne) ? C'est un métier de tri sous pression : trop de faux positifs non maîtrisés, et c'est la « fatigue des alertes » — le loup finit par passer parce qu'on a crié au loup mille fois.

### Activité — L'Analyste SOC (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Annoncez : « vous prenez votre poste au SOC pour la garde du matin. Trois éléments attendent dans la file — à vous de trier. » Projetez chaque situation, lancez le sondage, débriefez avant la suivante.

*   **📊 Sondage n°2 — L'alerte "voyage impossible" :** Le SIEM signale : compte de M. Diallo connecté depuis Lyon à 8h02, puis depuis Singapour à 8h31. Votre qualification ?
    *   A) Faux positif : M. Diallo voyage beaucoup
    *   B) Vrai positif probable : vitesse de déplacement physiquement impossible → escalade immédiate au niveau 2 et blocage préventif de la session ✅
    *   C) J'attends de voir s'il se reconnecte
*   **📊 Sondage n°3 — L'alerte antivirus du poste 42 :** L'antivirus détecte un « logiciel malveillant » sur le poste d'un technicien... qui vous prévient : c'est le fichier de test standard (EICAR) qu'il utilise pour vérifier que l'antivirus fonctionne. Votre qualification ?
    *   A) Vrai positif : on isole le poste et on lance l'investigation
    *   B) Faux positif documenté : je le consigne, je vérifie l'usage déclaré et j'ajuste la règle pour ce cas d'usage encadré ✅
    *   C) J'ignore l'alerte sans rien consigner : je connais le technicien
*   **📊 Sondage n°4 — Le dilemme du patch :** Deux failles « Élevées » attendent : score **8.5** sur un serveur interne non exposé, score **7.5** sur le serveur web de production exposé à Internet. Laquelle corrigez-vous en premier ?
    *   A) La 8.5 : son score brut est plus élevé
    *   B) La 7.5 : l'exposition Internet augmente drastiquement la probabilité d'exploitation réelle ✅
    *   C) Aucune : j'attends le prochain audit externe

**Éléments de débriefing (pour le mentor) :**

- N°2 : le « voyage impossible » est LA règle de corrélation classique ; on bloque d'abord, on s'excuse ensuite — un blocage à tort coûte un appel au support, un vol de compte coûte une crise. Nuance à mentionner : un VPN personnel peut simuler ce voyage (d'où l'investigation du niveau 2, pas une sanction automatique).
- N°3 : le piège est C — un faux positif se **documente** toujours : c'est ainsi qu'on affine les règles (tuning) et qu'on combat la fatigue des alertes. Ignorer sans consigner, c'est dégrader le système de détection.
- N°4 : le score CVSS est le point de départ, **le contexte d'exposition est le juge de paix**. Rappel d'A1 : la formule du risque contient l'exposition. Cette question annonce la section CVSS qui suit.

### 2. Identifier les failles : Scans de vulnérabilités vs Test d'intrusion

Maintenir un bon niveau de sécurité nécessite de tester activement ses défenses. On utilise pour cela deux approches complémentaires :

* **Le scan de vulnérabilités** : Outil logiciel automatisé (ex. Nessus, OpenVAS) qui scanne le réseau et compare les versions des programmes installés avec une base de données de failles connues (la base des **CVE**). Il est rapide, peu coûteux et peut être exécuté fréquemment, mais il génère des faux positifs et ne détecte pas les failles logiques complexes.
* **Le test d'intrusion (*Pentest*)** : Audit mené par un expert humain (un *pentester* ou hacker éthique) qui cherche manuellement à s'introduire dans le réseau en exploitant et en combinant plusieurs vulnérabilités, y compris des faiblesses logiques ou humaines. Il est plus coûteux mais reflète fidèlement la réalité d'une attaque ciblée — et il exige toujours une autorisation écrite (cadre légal approfondi en session A7).

Analogie : le scan est le **radar automatique** — systématique, infatigable, mais il ne voit que ce qu'on lui a appris à voir ; le pentester est le **pilote d'essai** — il improvise, combine, contourne. Une bonne stratégie utilise les deux : scans fréquents (mensuels, voire continus), pentest périodique (annuel ou à chaque évolution majeure).

### 3. Prioriser la remédiation : Comprendre le score CVSS

Un scan de sécurité sur une entreprise moyenne peut remonter des centaines de vulnérabilités. On utilise le score CVSS pour savoir lesquelles corriger en premier. Le standard actuel est la **version 4.0** (l'échelle et la logique décrites ici valent aussi pour la v3.1, encore très répandue dans les outils).

Le score CVSS varie de **0.0 à 10.0** et s'appuie sur plusieurs critères d'évaluation :

* **Le vecteur d'accès** : La faille est-elle exploitable à distance via Internet (gravité max) ou nécessite-t-elle un accès physique à la machine ?
* **La complexité d'exploitation** : Est-elle facile à exploiter (ex. via un script public disponible) ou très complexe ?
* **Les privilèges requis** : Faut-il être déjà authentifié comme administrateur pour l'exploiter ?
* **L'impact sur la triade C-I-D** : La faille permet-elle de lire des données secrètes, de modifier des fichiers ou de bloquer le serveur ?

```text
[ 0.0 - 3.9 ] ➔ Faible  |  [ 4.0 - 6.9 ] ➔ Moyenne  |  [ 7.0 - 8.9 ] ➔ Élevée  |  [ 9.0 - 10.0 ] ➔ Critique
```

*Règle opérationnelle* : Une faille avec un score de 9.8 exploitable à distance sans authentification sur un serveur web de production doit être patchée immédiatement (dans les 24h). Une faille de score 3.2 nécessitant un accès physique local peut être traitée lors d'une maintenance ultérieure. Et retenez la leçon du sondage n°4 : **le score dit la gravité intrinsèque, le contexte d'exposition dit l'urgence réelle.**

---

### Focus pratique
Voici une feuille de route de remédiation type, construite sur deux failles réelles célèbres et un cas générique :

| Identifiant CVE | Description simplifiée | Score CVSS | Exposition / Contexte | Priorité de traitement | Action proposée |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **CVE-2021-44228** (« Log4Shell ») | Exécution de code à distance via la bibliothèque de journalisation Java Log4j. | **10.0 (Critique)** | Serveur hébergeant le site e-commerce de l'entreprise, exposé à Internet. | **1 (Immédiate)** | Appliquer le correctif de l'éditeur sous 24h ; à défaut, mesure de contournement et surveillance renforcée. |
| **CVE-2021-4034** (« PwnKit ») | Élévation de privilèges locale vers administrateur sur systèmes Linux. | **7.8 (Élevée)** | Serveur interne contenant les données financières, non exposé. | **2 (Sous 7 jours)** | Planifier le correctif lors de la maintenance hebdomadaire ; surveiller les connexions locales d'ici là. |
| *(exemple générique)* | Divulgation d'informations en mémoire locale sur postes de travail. | **4.3 (Moyenne)** | Postes des collaborateurs situés derrière le pare-feu. | **3 (Basse)** | Intégrer la mise à jour dans le cycle mensuel de patching. |

### 4. La vulnérabilité en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **Environ 40 000 CVE publiées en 2024** — un record historique, soit plus de 100 nouvelles failles référencées par jour (base CVE/NVD).
    - **Quelques jours, parfois quelques heures** : le délai désormais observé entre la publication d'une vulnérabilité critique et son exploitation massive par les attaquants (observations des CERT et rapports d'éditeurs récents).
    - **Environ 147 millions de personnes** touchées par la violation Equifax (2017), causée par un correctif disponible mais non appliqué pendant deux mois (cas détaillé ci-dessous).
    - Rappel de la session A1 : **plusieurs mois s'écoulent en moyenne entre une intrusion et son confinement** (IBM, 2025) — c'est précisément ce que le couple SOC/SIEM cherche à réduire.

**Comment lire ces chiffres ?** (1) Le flux de failles est industriel : sans méthode de priorisation, on se noie. (2) La course a changé de nature : ce n'est plus « corriger un jour », c'est « corriger avant l'attaquant » — en jours, pas en trimestres. (3) La détection est le multiplicateur de tout le reste : une intrusion vue en 1 heure est un incident, la même vue en 6 mois est une catastrophe.

### 5. Deux cas réels : le correctif ignoré et la faille du siècle

#### Cas n°1 — Equifax (2017) : le patch à 700 millions de dollars

En mars 2017, une faille critique est publiée dans Apache Struts (**CVE-2017-5638**), un composant très utilisé des applications web — correctif disponible le jour même. L'agence de crédit américaine Equifax, qui détient les données financières de la moitié des adultes américains, identifie le composant dans son parc... mais le correctif n'est pas appliqué sur un portail web critique : défaut d'inventaire, scan incomplet, responsabilités diluées. Deux mois plus tard, des attaquants exploitent la faille, s'installent dans le réseau — et y restent **76 jours sans être détectés** (un outil de surveillance était lui-même mal configuré, son certificat expiré depuis des mois). Bilan : les données personnelles et financières d'environ **147 millions de personnes** exfiltrées, un accord d'indemnisation d'environ **700 millions de dollars** avec les autorités américaines, le départ du PDG, du DSI et du RSSI.

**Ce que ce cas illustre :** toute la session en une histoire. La gestion des vulnérabilités a échoué (patch disponible, non appliqué — problème d'inventaire et de processus, pas de compétence) ; puis la détection a échoué (le SOC était aveugle par mauvaise configuration). Deux chaînes de défense, deux maillons rompus. La question à poser à toute organisation : « combien de temps entre la publication d'un correctif critique et son application chez vous ? » — chez Equifax, la réponse valait 700 millions de dollars.

#### Cas n°2 — Log4Shell (2021) : la faille du siècle et la course mondiale au correctif

Le 9 décembre 2021, une vulnérabilité est révélée dans **Log4j**, une bibliothèque de journalisation Java utilisée dans une part considérable des applications du monde : **CVE-2021-44228**, score CVSS **10.0** — le maximum absolu. Exploitables à distance, sans authentification, par une simple chaîne de caractères envoyée à l'application, des millions de serveurs deviennent attaquables du jour au lendemain. En quelques **heures**, les scanners malveillants ratissent Internet ; en quelques jours, les équipes de sécurité du monde entier vivent leur pire semaine de l'année : il faut d'abord savoir **où** Log4j se cache (souvent enfoui dans des produits tiers — l'inventaire, encore lui), puis corriger, souvent plusieurs fois (les premiers correctifs étaient incomplets). Le CERT-FR et toutes les agences nationales publient des alertes de niveau maximal. La remédiation complète prendra des mois.

**Ce que ce cas illustre :** l'ironie d'abord — l'outil compromis était celui-là même qui écrit les logs, la matière première de cette session. La leçon ensuite : face à une CVSS 10.0 ubiquitaire, la vitesse de réaction dépend de trois choses préparées AVANT la crise : un inventaire à jour (savoir où l'on est vulnérable), des scans capables de le confirmer, et un processus de patch d'urgence déjà rodé. La priorisation CVSS que vous avez pratiquée au sondage n°4 n'est pas un exercice d'école : en décembre 2021, elle a été la différence entre les organisations corrigées en 48 heures et celles compromises pour des mois.

!!! question "💬 Question chat — Transition"
    Chez Equifax, le correctif existait, la faille était connue, et l'attaque a quand même réussi. **Dans le chat : à votre avis, quel a été le VRAI maillon faible — la technique, le processus, ou l'organisation ?** Le mentor lit 3-4 réponses ; conclusion : le processus et l'organisation (inventaire incomplet, responsabilités diluées, surveillance mal configurée) — la technologie était disponible du premier au dernier jour. C'est la GRC de la session A5 qui rejoint la technique.

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez la surveillance de la sécurité de votre entreprise comme la protection d'un **centre commercial** :
    - **Le SOC (Security Operations Center)** est le PC de sécurité central où les agents surveillent en temps réel les caméras de surveillance (logs d'événements).
    - **Le SIEM** est le système d'alarme intelligent qui analyse toutes les caméras en même temps : si un détecteur s'active à la porte A et qu'une personne court vers la sortie B 5 secondes après, il génère une alerte d'intrusion automatique.
    - **Le SOAR** est le rideau métallique qui s'abaisse automatiquement dès que l'alarme confirmée retentit — sans attendre qu'un agent coure jusqu'à la porte.
    - **Le Scan de vulnérabilités** est le garde qui fait sa ronde la nuit pour vérifier physiquement si des fenêtres sont restées ouvertes ou si des serrures sont endommagées.
    - **Le Score CVSS** est la note d'urgence attribuée à une vitre brisée : une vitre brisée au rez-de-chaussée (CVSS 9.8) est bien plus urgente à réparer qu'une poignée de porte lâche au 3ème étage (CVSS 3.0).

**Exemple d'application professionnelle :**
Dans une banque, le SIEM détecte qu'un compte utilisateur s'est connecté depuis la France puis depuis la Chine 10 minutes plus tard. Le SOC qualifie cette alerte de "Vrai Positif" (vitesse de déplacement impossible) et bloque immédiatement la session de l'utilisateur, évitant ainsi le vol de données bancaires. C'est le sondage n°2 de votre activité, en conditions réelles — et c'est un scénario quotidien dans les SOC bancaires.

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour orchestrer les opérations de sécurité (SOC) et cartographier les vulnérabilités système, plusieurs outils se distinguent :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Tenable Nessus / Tenable.io** : Référence mondiale pour le scan et le management des vulnérabilités, offrant une détection précise des CVE et des configurations défectueuses.
    *   **Qualys VMDR** : Plateforme SaaS leader de détection des vulnérabilités et de priorisation des correctifs en temps réel.
    *   **Splunk Enterprise Security / Microsoft Sentinel** : Leaders du marché des SIEM et du SOAR pour centraliser les logs et corréler les menaces à l'échelle de l'entreprise.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **Greenbone Community Edition (OpenVAS)** : Scanner de vulnérabilités open-source très complet pour évaluer les vulnérabilités de réseau local et de serveurs.
    *   **Wazuh** : Outil open-source de centralisation de logs et de détection d'intrusions (HIDS/SIEM), idéal pour les PME souhaitant mettre en place une première brique de SOC.
    *   **TheHive & Cortex** : Plateforme open-source d'orchestration de réponse aux incidents (SOAR light) permettant de gérer les alertes cyber et d'automatiser les analyses d'indicateurs (IOC).

### Quiz de validation (Sondages Livestorm n°5 à 7)

**Consignes pour le mentor :** À lancer en fin de session, après les études de cas.

*   **📊 Sondage n°5 :** Quel est le rôle principal d'un SIEM ?
    *   A) Bloquer les virus sur les postes de travail
    *   B) Centraliser et corréler les journaux d'événements pour lever des alertes ✅
    *   C) Remplacer les analystes du SOC
    *   D) Scanner les vulnérabilités du réseau
*   **📊 Sondage n°6 :** Quelle est la différence fondamentale entre un scan de vulnérabilités et un test d'intrusion ?
    *   A) Aucune, ce sont deux noms pour la même chose
    *   B) Le scan est automatisé et compare aux failles connues ; le pentest est mené par un expert humain qui exploite et combine les failles ✅
    *   C) Le pentest est gratuit, le scan est payant
*   **📊 Sondage n°7 :** Un scan révèle une faille CVSS 9.8 sur votre serveur web de production. Votre réaction ?
    *   A) L'ajouter au cycle de maintenance annuel
    *   B) Critique : correctif ou mesure de contournement en urgence (sous 24h), avec surveillance renforcée ✅
    *   C) Attendre la confirmation d'un deuxième scan le mois prochain

**Éléments de débriefing (pour le mentor) :**

- N°5 : le SIEM voit les combinaisons, l'analyste qualifie — l'outil ne remplace pas l'humain, il le rend possible à cette échelle.
- N°6 : radar automatique vs pilote d'essai ; les deux se complètent, avec autorisation écrite pour le pentest.
- N°7 : re-projeter la règle opérationnelle et rappeler Log4Shell : en décembre 2021, la différence entre 48 heures et 6 mois s'est jouée exactement ici.

### Questions de réflexion

1. Chez Equifax, l'outil de détection était mal configuré depuis des mois. Qui, dans une organisation, devrait vérifier que les outils de surveillance... sont eux-mêmes surveillés ? (Pont vers la gouvernance d'A5.)
2. Votre PME n'a ni SOC ni SIEM. Quelles briques minimales pourriez-vous mettre en place dès demain avec un budget quasi nul ? (Pistes : journalisation activée et centralisée, alertes de connexion, Wazuh.)
3. Trop d'alertes tue l'alerte : comment un SOC peut-il lutter contre la fatigue des alertes sans devenir aveugle ? Quel rôle pour le SOAR — et quelles limites à l'automatisation d'une réponse ?
4. « Patcher immédiatement » et « ne rien casser en production » sont deux exigences légitimes et contradictoires. Comment votre organisation arbitre-t-elle ? Qui tranche en cas de désaccord ?

## 3. Ressources complémentaires

* **IBM SkillsBuild** : Cours sur le fonctionnement d'un SIEM et le métier d'analyste SOC.
* **[CERT-FR — Alertes de sécurité](https://www.cert.ssi.gouv.fr/)** : le fil d'alertes de référence en France — abonnez-vous, c'est gratuit et c'est le réflexe professionnel n°1.
* **NIST** : Base de données nationale des vulnérabilités (NVD - National Vulnerability Database) pour rechercher des identifiants CVE.
* **FIRST.org** : Calculateur officiel des scores CVSS (v3.1 et v4.0) pour comprendre l'impact des différentes variables de cotation.
* **[OWASP — Top 10 Web](https://owasp.org/www-project-top-ten/)** : le classement de référence des risques applicatifs web.

## 4. Exercice bonus (Sondage Mises à Jour - Livestorm)

*   **Objectif :** Évaluation des risques liés aux correctifs.
*   **📊 Sondage Livestorm n°8 :** L'éditeur d'un logiciel métier publie un correctif de sécurité urgent. Le technicien refuse de l'installer immédiatement par crainte de bloquer la production. Quelle est la meilleure approche ?
    *   A) Ne jamais installer la mise à jour pour préserver la stabilité.
    *   B) Tester le correctif sur un poste de test pendant 24h avant de le déployer à grande échelle ✅
    *   C) Forcer le déploiement sur tous les serveurs à 14h sans prévenir les équipes.
*   **Guide d'animation (pour le mentor) :** Débattez du compromis permanent en cybersécurité entre la sécurité (appliquer les patchs) et la disponibilité opérationnelle (tester pour ne pas casser la production). Rebouclez avec Equifax : ne pas patcher a un coût, lui aussi — et il se chiffre en centaines de millions. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **CVE (Common Vulnerabilities and Exposures)** | Dictionnaire public identifiant de manière unique les failles connues (ex. CVE-2021-44228 « Log4Shell »). |
| **CVSS (Common Vulnerability Scoring System)** | Notation standardisée de la gravité d'une faille de 0.0 à 10.0 (version actuelle : 4.0) ; le contexte d'exposition détermine l'urgence réelle. |
| **Faux Positif** | Alerte déclenchée à tort par une activité légitime — toujours à documenter pour affiner les règles. |
| **Log (Journal d'événements)** | Trace chronologique générée par systèmes et équipements ; matière première de la détection et de l'investigation. |
| **Patch (Correctif)** | Mise à jour comblant une faille ; la fenêtre publication → application est la métrique de survie n°1. |
| **Pentest (Test d'intrusion)** | Audit offensif humain, en conditions réelles, avec autorisation écrite préalable. |
| **SIEM (Security Information and Event Management)** | Centralise et corrèle les logs pour lever des alertes sur les combinaisons suspectes. |
| **SOAR** | Automatise les réponses aux alertes (playbooks) pour combattre la fatigue des alertes. |
| **SOC (Security Operations Center)** | Les analystes (T1 tri, T2 investigation, T3 chasse) qui qualifient et traitent les alertes en continu. |
| **Threat Hunting** | Recherche proactive de compromissions silencieuses, sans attendre d'alerte. |

**La règle d'or de la session :** on ne peut pas tout corriger — on corrige d'abord ce qui est **critique ET exposé** ; et une intrusion vue en 1 heure est un incident, la même vue en 6 mois est une catastrophe.
