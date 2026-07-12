# Support de cours — Session 08 : Grand Atelier d'Audit & Synthèse du Parcours
Parcours : A 8 sessions  |  Module : Consolidation & Clôture  |  Niveau : Débutant / Intermédiaire  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session de clôture. Vous y découvrirez :
    - La méthodologie de l'Atelier d'Audit Interactif MedDistri (et son Score de Résilience)
    - La feuille de route de remédiation d'une PME, priorisée et budgétée
    - La carte de synthèse du parcours : 8 sessions, 7 réflexes, 10 cas réels
    - La valorisation de vos compétences et la suite de votre apprentissage

---

## 1. Introduction

Cette huitième session constitue la clôture du parcours A. Elle remplace l'évaluation académique traditionnelle par un **Grand Atelier d'Audit Interactif** mené en direct sur Livestorm. L'objectif est de mobiliser l'ensemble des connaissances acquises (fondations, ingénierie sociale, sécurité réseau, protection des identités, gouvernance, opérations et réponse aux incidents) pour auditer collectivement une PME vulnérable, **MedDistri**, décider des remédiations par vos votes, et formaliser sa feuille de route cyber. Aucun rendu écrit, aucune évaluation individuelle : c'est la communauté qui audite — et le Score de Résilience de MedDistri qui mesure votre réussite collective.

### Objectifs de la session

À l'issue de cette session, vous serez capable de :

- **Auditer** une infrastructure de PME en identifiant ses failles critiques et en les reliant aux fondamentaux du parcours.
- **Prioriser** des remédiations sous contrainte de budget (l'hygiène d'abord, les outils ensuite).
- **Vulgariser** un risque cyber en argument de direction (impact financier, juridique, réputationnel).
- **Poursuivre** votre montée en compétence en autonomie (veille, certifications, pratique).

!!! info "La mécanique de l'atelier"
    Le [dossier MedDistri](../projet/A_capstone.md) décrit l'entreprise et les quatre **sondages d'audit (n°4 à 7)**. Le **Score de Résilience Cyber** de la PME démarre à **10 %** ; chaque décision majoritairement correcte ajoute son gain (+25/+20/+25/+20). Objectif collectif : **≥ 80 %**. Les sondages n°1 à 3 (échauffement) et n°8-9 (objection métier et bilan) sont définis ci-dessous.

### Échauffement de l'auditeur (Sondages Livestorm n°1 à 3)

**Consignes pour le mentor :** Trois questions express pour réactiver les réflexes du parcours avant l'audit — une minute par vote, débrief éclair.

*   **📊 Sondage n°1 :** Un rançongiciel chiffre les fichiers ET les attaquants menacent de publier les données volées. Comment s'appelle cette tactique ?
    *   A) La double extorsion ✅
    *   B) Le spear-phishing
    *   C) Le déni de service
    *(Débrief éclair : vue en A1 avec l'hôpital de Corbeil-Essonnes — et MedDistri est justement du secteur santé...)*
*   **📊 Sondage n°2 :** Un e-mail du DAF : « le RIB du fournisseur a changé, payez avant midi ». Votre réflexe ?
    *   A) Payer : c'est le DAF
    *   B) Vérifier par un canal alternatif que J'INITIE (téléphone interne) ✅
    *   C) Répondre à l'e-mail pour confirmer
    *(Débrief éclair : la règle d'or d'A2 — Pathé, 19,2 M€ faute de l'avoir appliquée.)*
*   **📊 Sondage n°3 :** Un poste montre une infection active. Votre TOUT premier geste ?
    *   A) Éteindre la machine
    *   B) La débrancher du réseau sans l'éteindre ✅
    *   C) Lancer un scan antivirus
    *(Débrief éclair : le vote avant/après d'A7 — isoler, jamais éteindre.)*

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Restitution et Synthèse Managériale**
Expliquez aux apprenants comment vulgariser un concept cyber complexe pour convaincre un Comité de Direction. Le Comex ne comprend pas le jargon technique, il comprend le risque financier, juridique et réputationnel. Montrez comment transformer "Vulnérabilité d'injection SQL sur le serveur" en "Risque de vol de l'intégralité du fichier client entraînant une sanction CNIL et la une de la presse locale". Tout le parcours fournit les munitions chiffrées : les amendes RGPD réelles (A5), les coûts moyens (A1), les cas Pathé/Equifax/Target (A2, A6, A3).

**2. Audit Interactif — la posture d'animation**
Utilisez les sondages Livestorm pour engager l'auditoire. Laissez 1 à 2 minutes par vote, faites argumenter le chat AVANT de révéler la réponse, puis débriefez en expliquant forces et faiblesses de chaque option. Mettez à jour le Score de Résilience à l'écran après chaque sondage d'audit — la jauge qui monte est le moteur ludique de la session. Si une réponse majoritaire est incorrecte : ne pas donner le point, ouvrir un débat contradictoire dans le chat, puis re-voter en « seconde délibération » (le point est alors acquis si le vote bascule).

**3. Plan de développement des compétences**
Terminez la session (~10 minutes, voir plan minuté) en orientant les apprenants vers l'avenir : quelles certifications viser (CompTIA Security+, puis des certifications plus offensives type CEH pour les intéressés) ? Comment pratiquer en toute légalité sur des laboratoires en ligne dédiés (TryHackMe, Hack The Box, Root-Me — plateformes d'entraînement autorisées, à opposer au « test » sauvage de systèmes réels, cf. cadre légal d'A7) ? Comment organiser sa veille (alertes CERT-FR déjà adoptées en A6, Panorama annuel de l'ANSSI, rapports d'activité Cybermalveillance) ?

---

### Glossaire

*   **Audit de sécurité** — Évaluation méthodique de l'état de sécurité d'une organisation par rapport à des normes ou des règles de l'art.
*   **Feuille de route de remédiation (Remediation Roadmap)** — Plan d'action chronologique et priorisé décrivant les étapes techniques et organisationnelles à accomplir pour corriger les vulnérabilités identifiées lors d'un audit.
*   **Hygiène informatique (Cyber Hygiene)** — Ensemble des règles élémentaires de sécurité à appliquer de manière systématique pour minimiser la majorité des cybermenaces courantes (ex. mises à jour, mots de passe robustes, MFA, sauvegardes).
*   **Score de Résilience** — Indicateur pédagogique et ludique de l'atelier : la capacité estimée de la PME à résister à une attaque et à s'en relever, mise à jour à chaque décision d'audit.
*   **Synthèse managériale (Executive Summary)** — Courte introduction synthétique (1 page max) rédigée à l'intention des dirigeants de l'entreprise, résumant les menaces majeures découvertes et le budget requis, exempte de jargon technique complexe.
*   **Vulgarisation** — Traduction de concepts techniques complexes en termes simples et compréhensibles par des non-experts (ex. dirigeants business).

---

### Concepts clés de l'Atelier MedDistri

#### 1. L'évaluation de l'existant — chaque faille est une leçon du parcours
L'analyse de l'infrastructure de MedDistri révèle des failles communes à de nombreuses PME — et chacune renvoie à une session :

*   **L'exposition directe d'outils d'administration (ports 22, 3389)** sur Internet sans filtrage est une invitation ouverte à la force brute — le « serveur-appât » d'A3, attaqué en quelques minutes, et le vecteur d'intrusion n°1 relevé par l'ANSSI.
*   **L'absence de MFA** sur Microsoft 365 expose au vol d'identité et à la fraude aux fausses factures — la mécanique Pathé d'A2, que le chiffre Microsoft d'A4 (99,9 % des attaques automatisées bloquées) suffit à désamorcer.
*   **La sauvegarde USB branchée en permanence** sera chiffrée avec le serveur — le « NAS piégé » d'A4, version PME.
*   **L'absence de PSSI et de registre RGPD** malgré des données nominatives de clients : la gouvernance d'A5 — et le rappel que l'on peut être sanctionné sans avoir été piraté (Google, 2019).
*   **Le secteur santé** : le parallèle avec l'hôpital de Corbeil-Essonnes (A1) donne à Mme Legrand la meilleure raison du monde d'agir — ses clients hospitaliers exigeront bientôt des garanties.

#### 2. Priorisation et réalisme budgétaire
Une PME ne dispose pas de ressources infinies. La feuille de route proposée doit diviser les chantiers dans le temps :

*   **Court terme (Mois 1 — Budget quasi nul)** : Fermeture des accès exposés sur Internet, activation du MFA, changement des mots de passe prévisibles. *C'est l'application directe des sondages d'audit n°4 et 5.*
*   **Moyen terme (Mois 2-3 — Investissements de base)** : Accès distant par VPN, règle de sauvegarde 3-2-1 avec copie déconnectée ou immuable, amorce de conformité RGPD (registre des traitements). *Sondages n°6 et 7.*
*   **Long terme (Mois 6+ — Consolidation)** : Sensibilisation régulière des employés, scans de vulnérabilités planifiés (A6), PSSI signée par la direction (A5), exercice de crise annuel (A7).

La logique est celle du Comité des Risques d'A5 : la criticité multipliée par l'exposition dicte l'ordre, et le budget se justifie par le passage du rouge à l'orange — pas par la peur.

---

### Le dilemme des objections métier (Sondage Livestorm n°8)

**Consignes pour le mentor :** Lancez le sondage pour confronter le public aux réalités du terrain — l'audit technique est terminé, reste à convaincre les humains.

*   **📊 Sondage n°8 :** La directrice refuse d'imposer l'authentification multifacteur (MFA) car elle craint que les commerciaux ne perdent du temps lors de leurs connexions quotidiennes. Quel argument de sensibilisation est le plus percutant ?
    *   A) Selon Microsoft, le MFA bloque plus de 99,9 % des attaques automatisées de compromission de comptes — et l'arrêt d'activité en cas de piratage coûtera bien plus cher que 3 secondes par connexion ✅
    *   B) Le MFA est obligatoire par la loi sur la protection des données personnelles.
    *   C) Les commerciaux n'ont pas leur mot à dire sur les choix de sécurité.

**Éléments de débriefing (pour le mentor) :**
- La sécurité doit être présentée sous l'angle du risque financier et opérationnel — jamais du jargon, jamais de l'autorité brute (option C : la sécurité imposée sans adhésion est contournée). L'option B est fausse en l'état : le RGPD exige des « mesures appropriées », pas nommément le MFA — un auditeur ne gagne jamais en inventant une obligation légale.
- Le MFA moderne (notifications, passkeys — cf. A4) est aujourd'hui très fluide : la friction réelle est de quelques secondes.
- C'est l'exercice de **vulgarisation managériale** : transformer « authentification multifacteur » en « 3 secondes par jour contre 3 semaines d'arrêt ».

---

### La carte du parcours : 8 sessions, 7 réflexes, 10 cas réels

En clôture de l'audit, le mentor déroule la synthèse du parcours — chaque session, son réflexe, son cas marquant :

| Session | Le réflexe à vie | Le cas qui le prouve |
| :--- | :--- | :--- |
| **A1 — Fondations** | Penser C-I-D et Risque = Menace × Vulnérabilité × Impact | CHU de Corbeil-Essonnes (2022), France Travail (2024) |
| **A2 — Ingénierie sociale** | Toute demande sensible se vérifie par un canal que J'INITIE | Pathé (2018), deepfake Arup (2024) |
| **A3 — Réseau** | Filtrer (Default Deny), chiffrer, cloisonner | Target (2013), Mirai/Dyn (2016) |
| **A4 — Identités & données** | MFA partout ; 3-2-1 dont une copie VRAIMENT hors ligne | Capital One (2019), incendie OVHcloud (2021) |
| **A5 — GRC** | On ne supprime pas un risque, on le cote et on le traite | Google vs CNIL (2019), Meta (2023) |
| **A6 — Opérations** | Le score dit la gravité, l'exposition dit l'urgence | Equifax (2017), Log4Shell (2021) |
| **A7 — Incidents** | Isoler, jamais éteindre — et tout se gagne avant l'incident | Maersk/NotPetya (2017) |
| **A8 — Audit** | L'hygiène de base d'abord, les outils ensuite | MedDistri (vous venez de le vivre) |

---

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour piloter le plan de remédiation, suivre les vulnérabilités et formaliser la gouvernance :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Tugboat Logic (OneTrust)** : Solution automatisée d'aide à la préparation d'audits (ISO 27001, SOC 2), très prisée pour générer des politiques adaptées aux PME.
    *   **AuditBoard** : Plateforme collaborative pour piloter l'évaluation des contrôles de sécurité et le reporting d'audit auprès de la direction.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **OpenEx / OpenBAS (Filigran)** : Plateforme open-source française pour simuler des scénarios de crise cyber et entraîner les équipes.
    *   **Gitea / GitLab Community Edition** : Utilisés en sécurité pour suivre l'avancement des tickets de remédiation technique sous forme de kanbans collaboratifs.

---

### Questions de réflexion

1. MedDistri ressemble-t-elle à une organisation que vous connaissez ? Quelle serait la première mesure à y proposer lundi matin — et comment la présenteriez-vous à la direction ?
2. Le Score de Résilience est passé de 10 % à (idéalement) 90 %+ en quatre décisions à moins de 2 000 €. Que nous dit ce ratio sur la nature réelle du risque cyber des PME ?
3. Dans six mois, qu'est-ce qui aura survécu de cette formation dans vos pratiques quotidiennes ? Quel réflexe risque de s'éroder en premier, et comment l'entretenir ?
4. Si vous deviez résumer ce parcours en une phrase à un collègue qui n'y a pas assisté, laquelle choisiriez-vous ?

## 3. Ressources complémentaires

* **IBM SkillsBuild** : Explorez les cours pour continuer votre parcours d'apprentissage en cybersécurité (et récupérez votre badge de fin de parcours).
* **ANSSI** : Guide "La cybersécurité pour les TPE/PME en 12 questions" — le prolongement naturel de l'audit MedDistri, à offrir à toutes les Mme Legrand de votre entourage.
* **Cybermalveillance.gouv.fr** : Fiches pratiques de sensibilisation pour les entreprises.
* **CERT-FR** : le fil d'alertes adopté en A6 — votre veille est déjà en place.
* **TryHackMe / Root-Me / Hack The Box** : plateformes d'entraînement pratiques et légales pour continuer à progresser.

---

## 4. Exercice bonus (Sondage Bilan - Livestorm)

*   **Objectif :** Évaluation globale de la posture d'hygiène.
*   **📊 Sondage Livestorm n°9 :** Quelle mesure de sécurité simple et peu coûteuse présente le meilleur retour sur investissement immédiat pour une TPE/PME ?
    *   A) Acheter un pare-feu à 5 000 €.
    *   B) Mettre en œuvre une politique de mots de passe robustes associée au MFA et sensibiliser les collaborateurs ✅
    *   C) Rédiger une charte informatique de 80 pages.
*   **Guide d'animation (pour le mentor) :** Rappelez que l'hygiène cyber de base bloque la majorité des attaques opportunistes sans nécessiter de budgets importants — c'est le verdict du sondage d'audit n°7, généralisé. La charte de 80 pages (option C) que personne ne lit est l'anti-modèle de la PSSI utile vue en A5.

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Audit de sécurité** | Évaluation méthodique de l'état de sécurité d'une organisation par rapport à des normes ou des règles de l'art. |
| **Feuille de route de remédiation** | Plan d'action chronologique et priorisé : court terme (budget nul : fermer, activer, changer), moyen terme (VPN, 3-2-1, RGPD), long terme (sensibilisation, scans, PSSI, exercice). |
| **Hygiène informatique (Cyber Hygiene)** | Les règles de base appliquées systématiquement (mises à jour, MFA, sauvegardes, sensibilisation) — elles bloquent la majorité des attaques opportunistes. |
| **Score de Résilience** | Indicateur ludique de l'atelier : capacité estimée de la PME à résister et à se relever, mise à jour à chaque décision. |
| **Synthèse managériale (Executive Summary)** | Résumé d'une page vulgarisé : menaces majeures, impacts business, budget requis — zéro jargon. |
| **Vulgarisation** | Traduire « authentification multifacteur » en « 3 secondes par jour contre 3 semaines d'arrêt ». |

**La règle d'or du parcours :** la cybersécurité n'est pas une affaire d'outils coûteux mais de réflexes constants — et vous êtes désormais, chacune et chacun, une ligne de défense.
