# Session B13 — Gouvernance & cadres de sécurité
Parcours : B 20 sessions  |  Module : D — Gouvernance, risques & conformité  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - La Politique de Sécurité des Systèmes d'Information (PSSI)
    - Les référentiels mondiaux : ISO 27001 vs NIST CSF 2.0
    - Rôles et responsabilités : Direction vs RSSI
    - Deux affaires réelles : le RSSI d'Uber condamné pour dissimulation (2022) et Yahoo, la fuite cachée à 350 millions de dollars
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   La **PSSI** définit le cadre légal et technique de la sécurité. Elle doit être validée et portée politiquement par la **Direction Générale** pour être contraignante.
*   L'**ISO 27001** structure le management de la sécurité (SMSI) autour de l'amélioration continue (**PDCA**), tandis que le **NIST CSF 2.0** fournit un cadre d'action opérationnel basé sur **6 fonctions** — la sixième, *Govern* (Gouverner), ajoutée en 2024, est précisément le sujet de cette session.
*   Le **RSSI** propose et orchestre les mesures de sécurité, mais c'est la **Direction Générale** qui prend les décisions stratégiques et financières de couverture des risques — et qui en assume la responsabilité.

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer la structure, l'utilité et le processus d'élaboration d'une Politique de Sécurité des Systèmes d'Information (PSSI).
* Comparer les référentiels de sécurité mondiaux ISO 27001 (management organisationnel certifiable) et NIST CSF 2.0 (cadre opérationnel en 6 fonctions).
* Identifier la répartition des rôles et responsabilités entre la Direction Générale et le RSSI au sein de la gouvernance de sécurité d'une entreprise.

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** En 2024, le NIST a publié la version 2.0 de son célèbre référentiel de cybersécurité, en ajoutant une sixième fonction aux cinq historiques (Identifier, Protéger, Détecter, Répondre, Restaurer). Laquelle ?

    - A) *Govern* — Gouverner ✅
    - B) *Attack* — Attaquer pour mieux se défendre
    - C) *Insure* — Assurer

    **Débrief mentor :** Réponse A : **Gouverner** (NIST CSF 2.0, février 2024). Après dix ans d'existence, le référentiel technique le plus utilisé au monde a reconnu officiellement ce que le terrain criait : sans pilotage — sans stratégie, sans rôles clairs, sans arbitrages assumés par la direction — les cinq fonctions techniques finissent par échouer. C'est exactement le programme du module qui s'ouvre ce soir : qui décide, qui est responsable, selon quelles règles. Et deux affaires spectaculaires montreront ce qui arrive quand la gouvernance ment.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Gouvernance vs sécurité opérationnelle**
Le basculement conceptuel de la session : depuis B05, on configure (pare-feux, MFA, sauvegardes) ; ce soir, on pilote. L'ISO 27001 ne prescrit AUCUNE solution technique — elle impose un **système de management** : des politiques écrites, des processus, des audits, des preuves, et l'implication formelle de la direction. Formule utile : « l'opérationnel ferme les portes, la gouvernance décide quelles portes existent, qui en a la clé, et vérifie qu'elles sont bien fermées. »

**2. NIST CSF 2.0 : pourquoi GOVERN change tout**
Détaillez la nouveauté 2024 : la fonction *Govern* est transversale — elle alimente les cinq autres (contexte organisationnel, stratégie de gestion des risques, rôles et responsabilités, politiques, supervision, et **risques de la chaîne d'approvisionnement**). Le message : la gouvernance n'est pas une 6ᵉ étape après les autres, c'est le socle sous les cinq. Autre évolution : le CSF 2.0 s'adresse désormais explicitement à TOUTES les organisations, pas seulement aux infrastructures critiques.

**3. NIS2 : la responsabilité des dirigeants devient légale**
Contexte réglementaire européen à donner (sans en faire un cours de droit — B15 approfondira) : la directive **NIS2** (adoptée fin 2022, en cours de transposition en France) élargit massivement le nombre d'entités régulées (secteurs « essentiels » et « importants », sous-traitants inclus) et — point clé pour cette session — rend les **organes de direction** explicitement responsables de l'approbation et de la supervision des mesures de gestion des risques cyber, avec des sanctions pouvant viser les dirigeants. Le temps où la cybersécurité était « le problème de l'informatique » est juridiquement terminé.

---

### Glossaire

*   **ISO 27001** — Norme internationale définissant les exigences de mise en place et de certification d'un SMSI.
*   **NIS2** — Directive européenne (2022) élargissant les obligations de cybersécurité à des milliers d'entités et rendant les organes de direction responsables de leur supervision.
*   **NIST CSF (Cybersecurity Framework)** — Cadre de référence américain de cybersécurité ; sa version 2.0 (2024) est structurée en **6 fonctions** : Gouverner, Identifier, Protéger, Détecter, Répondre, Restaurer.
*   **PDCA (Plan, Do, Check, Act)** — Cycle d'amélioration continue (ou roue de Deming) à la base du management de la qualité et des normes ISO.
*   **PSSI** — Politique de Sécurité des Systèmes d'Information. Document de référence traduisant la stratégie de sécurité de l'entreprise en règles opérationnelles.
*   **RSSI (CISO)** — Responsable de la Sécurité des Systèmes d'Information. Expert technique et organisationnel chargé de piloter la sécurité informatique de l'organisation.
*   **SMSI** — Système de Management de la Sécurité de l'Information. Cadre organisationnel (processus, personnes, technologies) visant à protéger l'information d'une entreprise.

---

### Concepts clés

!!! info "À retenir"
    La technique ferme les portes ; la **gouvernance** décide quelles portes existent, qui en a la clé, et vérifie qu'elles sont fermées. Une règle non portée par la Direction n'est qu'un conseil ; un risque non arbitré est un risque accepté par accident ; et une fuite dissimulée se paie toujours plus cher que la fuite elle-même.

### 1. La Politique de Sécurité des Systèmes d'Information (PSSI)
La **PSSI** est le document de référence stratégique et juridique d'une entreprise. Elle traduit les objectifs de sécurité en règles d'usage précises et en exigences techniques obligatoires pour l'ensemble des collaborateurs et prestataires.

*   **Portage par la direction** : Une PSSI ne doit pas être un simple document technique rédigé dans son coin par le service informatique. Pour être légitime, applicable et juridiquement contraignante, elle doit être **validée et signée par la Direction Générale** (souvent annexée au règlement intérieur de l'entreprise).
*   **Structure classique d'une PSSI** :
    *   *Champ d'application* : Qui et quels équipements sont concernés.
    *   *Rôles et responsabilités* : Qui gère la sécurité, qui valide les accès.
    *   *Règles d'usage informatique* : Complexité des mots de passe, règles d'usage de la messagerie, charte de télétravail, gestion du matériel d'entreprise.
    *   *Sanctions* : Conséquences prévues en cas de violation volontaire des règles.
*   **Le test d'une bonne règle PSSI** : elle est **claire** (compréhensible sans jargon), **mesurable** (on peut vérifier son application) et **réaliste** (applicable sans bloquer le travail — sinon elle sera contournée, rappel B08).

### Activité — Le comité de rédaction PSSI (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** EcoLog rédige la section « Accès logiques & télétravail » de sa PSSI. Pour chaque sujet, trois formulations sont proposées : les participants votent la meilleure règle. Débriefez après chaque vote sur les critères (claire, mesurable, réaliste).

*   **📊 Sondage n°2 — La règle « mots de passe » :** Quelle formulation retenez-vous pour la PSSI ?
    *   A) « Les collaborateurs sont invités à choisir des mots de passe robustes. »
    *   B) « Chaque collaborateur utilise un mot de passe unique d'au moins 12 caractères, stocké dans le gestionnaire de mots de passe d'entreprise, obligatoire. » ✅
    *   C) « Les mots de passe sont changés tous les 5 jours et jamais notés nulle part. »
*   **📊 Sondage n°3 — La règle « télétravail » :** Quelle formulation retenez-vous ?
    *   A) « Le matériel personnel est à éviter dans la mesure du possible. »
    *   B) « Chacun est libre d'utiliser l'équipement de son choix s'il est prudent. »
    *   C) « Seuls les ordinateurs fournis et configurés par le service informatique sont autorisés pour accéder aux applications internes ; l'usage d'un ordinateur personnel est interdit. » ✅
*   **📊 Sondage n°4 — Le document est-il prêt ?** Ces règles, rédigées par la DSI, suffisent-elles à faire une PSSI applicable ?
    *   A) Oui : les règles sont claires et mesurables, c'est l'essentiel
    *   B) Non : il manque le portage par la Direction — validation formelle, sanctions prévues, annexion au règlement intérieur ✅
    *   C) Non : il manque le détail des configurations de pare-feu

**Éléments de débriefing (pour le mentor) :**

- N°2 : A est un vœu pieux (rien de mesurable) ; C est irréaliste — une règle inapplicable sera contournée (post-it !) et décrédibilise toute la PSSI. B coche les trois critères : claire, mesurable, réaliste.
- N°3 : les formulations « à éviter », « dans la mesure du possible » n'ont aucune valeur d'audit ni juridique. C interdit ET explique le périmètre — le durcissement de B08 (EDR, chiffrement) n'existe que sur le matériel maîtrisé.
- N°4 : LE point de gouvernance — sans validation de la Direction, sans sanctions et sans intégration au règlement intérieur, ce document n'est qu'une liste de conseils de la DSI. Une PSSI est un acte de direction, pas un document technique. (Et C confond PSSI et documentation d'exploitation : la politique fixe le « quoi », pas le « comment » technique.)

### 2. Les référentiels mondiaux : ISO 27001 vs NIST CSF 2.0
Pour concevoir leur stratégie cyber, les entreprises s'appuient sur des cadres de référence reconnus mondialement :

*   **ISO/IEC 27001 (Management de la sécurité)** : C'est la norme internationale décrivant la mise en place d'un **SMSI** (Système de Management de la Sécurité de l'Information). Elle repose sur le principe de l'amélioration continue (la roue de Deming ou **PDCA** : *Plan, Do, Check, Act*). C'est une démarche organisationnelle globale qui aboutit, après audit externe, à une **certification** officielle très valorisée auprès des clients. Point essentiel : elle ne prescrit aucune solution technique — elle certifie que le management de la sécurité fonctionne et s'améliore.
*   **NIST CSF 2.0 (Cybersecurity Framework, version 2024)** : Proposé par l'organisme public américain NIST, c'est un cadre pragmatique, axé sur la gestion opérationnelle des risques. Sa version 2.0 (février 2024) structure la défense autour de **6 fonctions clés** :
    1.  **Govern (Gouverner)** — *la nouveauté 2024* : Définir la stratégie, les rôles, les politiques et la supervision — la fonction transversale qui alimente les cinq autres.
    2.  **Identify (Identifier)** : Cartographier les actifs matériels, logiciels et les risques.
    3.  **Protect (Protéger)** : Mettre en œuvre des barrières de sécurité (pare-feu, IAM, formation).
    4.  **Detect (Détecter)** : Déployer des outils pour identifier les anomalies en continu (supervision — la session B16).
    5.  **Respond (Répondre)** : Définir des procédures de réaction rapide en cas d'attaque détectée (B19).
    6.  **Recover (Restaurer)** : Planifier la restauration des systèmes d'information (sauvegardes 3-2-1 de B12, PCA/PRA de votre recherche).

*   *L'analogie du bâtiment* :
    *   **ISO 27001** est le code de la construction et le manuel de gestion de l'immeuble. Il garantit que vous avez mis en place des comités de suivi, des processus de réévaluation et des audits pour veiller à la qualité continue du bâtiment.
    *   **NIST CSF** est le plan d'action opérationnel des pompiers et de la sécurité physique de l'immeuble. Il détaille comment verrouiller les portes (Protect), où installer les détecteurs de fumée (Detect), comment évacuer (Respond/Recover) — et, depuis la version 2.0, qui dirige le tout et rend des comptes (Govern).
    *   Les deux se complètent : beaucoup d'entreprises pilotent avec le CSF et se font certifier ISO 27001.

### 3. Rôles et responsabilités : Direction vs RSSI
La gouvernance cyber exige une distinction claire entre le pouvoir de décision et le rôle d'expertise :

*   **Le RSSI (Responsable de la Sécurité des Systèmes d'Information / *CISO*)** : C'est l'expert, le conseiller et le chef d'orchestre. Il analyse les menaces, rédige la PSSI, recommande des investissements techniques et sensibilise les équipes. **Le RSSI conseille, mais il ne prend pas les décisions stratégiques finales.**
*   **La Direction Générale** : C'est l'arbitre et le donneur d'ordres. C'est elle qui valide les budgets de sécurité, accepte formellement le niveau de risque restant, et assume la responsabilité civile — et désormais, avec la directive **NIS2**, une responsabilité personnelle accrue des organes de direction dans la supervision des risques cyber.
*   **Le rattachement du RSSI** compte : sous l'autorité directe de la DSI, le RSSI juge son propre patron (la production prime alors sur la sécurité) — les organisations matures le rattachent à la direction générale, au secrétariat général ou à la direction des risques.

### 4. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **Février 2024** : publication du NIST CSF 2.0 — la fonction *Govern* rejoint les cinq fonctions historiques, dix ans après la version 1.0.
    - **350 millions de dollars** : la baisse du prix de rachat de Yahoo par Verizon (2017) après la révélation tardive de fuites massives dissimulées — plus 35 M$ d'amende du gendarme boursier américain (2018).
    - **2022** : le responsable sécurité d'Uber est reconnu coupable par la justice fédérale américaine pour avoir dissimulé la fuite de 2016 — première condamnation pénale d'un CSO pour la gestion d'une violation de données.

**Comment lire ces chiffres ?** (1) Les référentiels mondiaux eux-mêmes ont conclu que la technique sans gouvernance échoue. (2) Cacher une fuite coûte plus cher que la fuite. (3) La responsabilité n'est plus théorique : elle se chiffre en millions... et désormais en casiers judiciaires.

### 5. Deux affaires réelles : le RSSI condamné et la fuite à 350 millions

#### Cas n°1 — Uber (2016-2022) : le « bug bounty » qui valait une condamnation

En 2016, Uber subit une fuite touchant des dizaines de millions d'utilisateurs et de chauffeurs. Plutôt que de notifier les autorités — l'entreprise était alors précisément sous le coup d'une enquête du régulateur américain pour une fuite précédente — le responsable sécurité (CSO) organise le silence : les attaquants reçoivent **100 000 $** maquillés en récompense de « bug bounty », contre la signature d'un accord de confidentialité et la promesse d'avoir détruit les données. La fuite ne sera révélée qu'un an plus tard par la nouvelle direction. En 2022, la justice fédérale américaine reconnaît le CSO **coupable** d'obstruction et de dissimulation — la première condamnation pénale d'un responsable sécurité pour sa gestion d'une violation de données.

**Ce que ce cas illustre :** la gestion d'un incident est un acte de **gouvernance**, pas une opération technique discrète — notification, transparence et traçabilité ne sont pas optionnelles ; le « bug bounty » est un outil légitime... qui ne doit jamais servir de déguisement à une extorsion ; et l'obéissance n'exonère pas : un professionnel de la sécurité peut avoir à dire non — par écrit — à sa propre hiérarchie. (Le mini-scénario de ce soir vous mettra exactement dans cette position.)

#### Cas n°2 — Yahoo (2013-2017) : la fuite cachée à 350 millions de dollars

Entre 2013 et 2014, Yahoo subit deux fuites gigantesques — l'une touchera, révélation après révélation, la totalité de ses **3 milliards de comptes**. L'entreprise le sait en interne... et ne dit rien : ni aux utilisateurs, ni aux investisseurs. La vérité éclate en 2016, en pleine négociation du rachat par Verizon : l'acquéreur réduit son offre de **350 millions de dollars**, et le gendarme boursier américain (SEC) inflige en 2018 une amende de **35 M$** pour défaut d'information des investisseurs — la première du genre.

**Ce que ce cas illustre :** une violation de données est une information **financière** majeure — la cacher trompe les investisseurs, les clients et les partenaires ; la dissimulation a transformé un incident de sécurité en scandale de gouvernance (démissions, décote, procès en cascade) ; et la valeur d'une entreprise intègre désormais sa posture cyber — la sécurité est devenue un sujet de conseil d'administration, exactement ce que NIST CSF 2.0 et NIS2 actent aujourd'hui.

!!! tip "📊 Sondage Livestorm n°5 — Et chez vous ? (sondage d'opinion, pas de bonne réponse)"
    **Question :** Dans votre organisation, existe-t-il une charte informatique (ou PSSI) que les collaborateurs ont formellement signée ?

    - A) Oui — signée à l'embauche ou validée électroniquement, preuve à l'appui
    - B) Elle existe « quelque part », mais personne ne se souvient l'avoir signée
    - C) Je ne sais pas / Je ne crois pas

    **Débrief mentor :** Sondage d'opinion — B est extrêmement répandu : le document existe, le portage n'existe pas. Or une charte non signée n'est ni opposable juridiquement, ni auditable (l'exercice bonus y revient). La question de lundi matin : où est notre charte, qui l'a signée, et la Direction l'a-t-elle validée ? Trois questions, trois minutes — et souvent trois surprises.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Vous êtes RSSI. Une fuite de données clients vient d'être confirmée. Un prestataire « spécialisé » vous propose : « On contacte les pirates, on leur paie 50 000 € déguisés en récompense de bug bounty avec accord de confidentialité — et il n'y a rien à notifier, votre réputation est sauve. » **Tapez A, B ou C dans le chat :**

    - A) Accepter : la réputation de l'entreprise passe d'abord, et l'affaire reste discrète.
    - B) Refuser : informer la Direction, notifier la CNIL dans les 72 heures, traiter l'incident de façon documentée — et le mettre par écrit. ✅
    - C) Payer, mais sans accord écrit, pour ne laisser aucune trace.

    **Débrief mentor :** B — c'est mot pour mot le scénario Uber, et il a valu au CSO une condamnation pénale. La notification à la CNIL sous **72 heures** est une obligation légale (RGPD — approfondi en B15), la dissimulation transforme la victime en fautif, et l'écrit protège le professionnel qui a alerté (si la direction passe outre, la responsabilité est la sienne). C cumule toutes les fautes en supprimant même la traçabilité. Retenez la formule : on ne négocie pas sa transparence.

---

### Questions de réflexion
1. Pourquoi est-il risqué qu'un RSSI soit directement rattaché à la Direction Informatique (DSI) plutôt qu'au Secrétariat Général ou à la Direction des Risques ? (Pensez aux conflits d'intérêts entre la production informatique et le contrôle de sécurité.)
2. Si une entreprise est certifiée ISO 27001, cela signifie-t-il qu'elle est techniquement impossible à pirater ? Expliquez la différence entre un système de management de la sécurité et une garantie de sécurité absolue.
3. Dans l'affaire Yahoo, la dissimulation a coûté 350 M$ de décote — bien plus que la remédiation de la fuite elle-même. Qu'est-ce que cela révèle sur la valeur économique de la transparence en cybersécurité ?

**Corrigé / Éléments de réponse :**

1. La DSI priorise souvent la disponibilité et les délais, tandis que le RSSI priorise la sécurité. Ce conflit d'intérêts rend le RSSI impuissant s'il est sous les ordres du DSI — il juge alors son propre patron.
2. L'ISO 27001 atteste que l'entreprise a mis en place de bons processus d'amélioration continue de la sécurité, mais le risque zéro n'existe pas. La certification garantit le management, pas l'imperméabilité.
3. Le marché sanctionne moins l'incident que le mensonge : une fuite gérée avec transparence entame la confiance temporairement ; une fuite cachée détruit la crédibilité de toute la gouvernance (que cache-t-elle d'autre ?). La transparence est un actif financier — c'est pourquoi les régulateurs (SEC, RGPD, NIS2) l'imposent.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez la gouvernance de la sécurité et la PSSI comme la **gestion de la sécurité routière d'un pays** :
    - **La PSSI (Politique de Sécurité)** est comparable au Code de la Route : elle définit les règles, les comportements obligatoires (porter la ceinture, respecter la vitesse) et les sanctions en cas de manquement.
    - **La Direction Générale (le Gouvernement)** valide le budget, vote les lois de sécurité et fixe les objectifs globaux de réduction des accidents.
    - **Le RSSI (le Ministère de la Sécurité Routière)** propose les règles techniques, surveille l'état des routes, sensibilise les conducteurs et analyse les causes des accidents.
    - **Les cadres comme ISO 27001 ou le NIST CSF** sont les normes internationales de construction des autoroutes et des voitures que le pays applique pour rester performant.

**Exemple d'application professionnelle :**
Une entreprise industrielle de 500 salariés souhaite travailler pour des clients étatiques. Elle doit prouver son niveau de sécurité. Le RSSI pilote la rédaction de la PSSI, définit les politiques de mots de passe et met en place un SMSI (Système de Management de la Sécurité). En s'appuyant sur le référentiel ISO 27001, l'entreprise obtient une certification officielle qui rassure ses clients et lui permet de signer ses contrats.

### Panorama des solutions du marché (Commerciales & Open-Source)

Le pilotage de la gouvernance de sécurité et l'établissement d'une PSSI s'appuient sur les outils GRC suivants :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **OneTrust (Tugboat Logic)** : Outil de conformité automatisé guidant pas à pas les PME et start-ups dans la rédaction de leurs politiques de sécurité et la préparation à la certification ISO 27001.
    *   **AuditBoard** : Plateforme de premier plan pour gérer les programmes de conformité, l'audit interne et le suivi des exigences de sécurité auprès des collaborateurs.
    *   **ServiceNow Policy and Compliance** : Solution d'entreprise haut de gamme pour centraliser et valider le respect des processus internes par rapport aux réglementations.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **EBIOS RM (ANSSI)** : Méthode française d'analyse de risques avec modèles et documents en accès libre pour structurer sa gouvernance conformément aux références de l'ANSSI (au programme de B14).
    *   **PIA Tool (CNIL)** : Solution open-source gratuite pour cartographier et analyser la conformité des traitements de données personnelles.
    *   **Monarc** : Outil open-source de gestion de la conformité et des risques de sécurité de l'information développé au Luxembourg, idéal pour aligner sa PSSI sur l'ISO 27001.

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après le mini-scénario.

*   **📊 Sondage n°6 :** Qui accepte formellement le niveau de risque résiduel et assume la responsabilité en cas de sinistre majeur ?
    *   A) Le RSSI : c'est l'expert de la sécurité
    *   B) La Direction Générale : le RSSI conseille, elle décide et assume ✅
    *   C) Le prestataire informatique qui gère le parc
*   **📊 Sondage n°7 :** Quelle est la différence essentielle entre l'ISO 27001 et le NIST CSF ?
    *   A) L'ISO 27001 certifie un système de management (SMSI, audits, PDCA) ; le NIST CSF est un cadre d'action opérationnel non certifiant ✅
    *   B) L'ISO 27001 est gratuite, le NIST CSF est payant
    *   C) L'ISO 27001 est réservée aux banques, le NIST CSF aux hôpitaux
*   **📊 Sondage n°8 :** Dans le cycle PDCA, à quoi correspond le « C » (*Check*) ?
    *   A) Chiffrer les données sensibles
    *   B) Vérifier l'efficacité des mesures mises en place (audits, indicateurs) avant d'ajuster ✅
    *   C) Choisir les meilleurs outils du marché

**Éléments de débriefing (pour le mentor) :**

- N°6 : la répartition canonique — l'expertise ne se confond pas avec la décision ; et NIS2 grave désormais cette responsabilité des dirigeants dans le droit européen.
- N°7 : les deux se complètent (piloter avec le CSF, se certifier ISO) — mais seule l'ISO 27001 délivre un certificat opposable aux clients.
- N°8 : le « Check » est ce qui distingue un système de management d'une liste de bonnes intentions — on mesure, on audite, puis on corrige (Act). Sans vérification, pas d'amélioration continue.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Cybersecurity Governance and Risk Management - Part 1"* (durée estimée : 1h30).
*   **Ressource complémentaire** : Visiter le site de l'ANSSI (cyber.gouv.fr) et consulter le guide *"La PSSI"* pour observer comment un État structure ses exigences nationales.
*   [ANSSI — La méthode EBIOS Risk Manager](https://cyber.gouv.fr/la-methode-ebios-risk-manager)
*   [CNIL — PIA / Analyse d'impact](https://www.cnil.fr)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Approche de la conformité d'audit.
*   **📊 Sondage Livestorm n°9 :** Un auditeur de sécurité vous demande de prouver que vos collaborateurs ont pris connaissance de la charte informatique. Quelle preuve présentez-vous ?
    *   A) Une affirmation orale du technicien informatique.
    *   B) La charte informatique signée individuellement par chaque collaborateur ou validée électroniquement avec preuve de réception ✅
    *   C) Le code source de votre outil d'IAM.
*   **Guide d'animation (pour le mentor) :** La gouvernance et l'audit exigent des preuves documentaires tangibles (*accountability*) : en audit, ce qui n'est pas prouvé n'existe pas. C'est le prolongement direct du sondage d'opinion n°5 — la charte « qui existe quelque part » ne vaut rien face à un auditeur. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **PSSI** | Le Code de la Route de l'entreprise : règles claires, mesurables, réalistes — et signées par la Direction. |
| **ISO 27001** | La norme certifiable du management de la sécurité (SMSI) — elle garantit le pilotage, pas l'imperméabilité. |
| **NIST CSF 2.0 (2024)** | 6 fonctions : **Gouverner**, Identifier, Protéger, Détecter, Répondre, Restaurer — la gouvernance est le socle des cinq autres. |
| **PDCA** | Planifier, Déployer, **Vérifier**, Ajuster — l'amélioration continue, cœur de l'ISO. |
| **RSSI vs Direction** | Le RSSI conseille et orchestre ; la Direction décide, finance et **assume**. |
| **NIS2** | La directive européenne qui rend les dirigeants légalement responsables de la supervision des risques cyber. |
| **Accountability** | En audit, ce qui n'est pas prouvé (signé, tracé, documenté) n'existe pas. |

**La règle d'or de la session :** la gouvernance décide, documente et prouve — une règle non portée par la Direction n'est qu'un conseil, un incident dissimulé est une faute qui se paie au centuple (Uber, Yahoo), et depuis NIS2, la responsabilité cyber des dirigeants n'est plus une métaphore.
