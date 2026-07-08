# Session B20 — Soutenance finale & Clôture (Validation Capstone B)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Le Capstone Project B : Une synthèse transverse
    - Réussir une soutenance de projet cyber
    - Capitalisation professionnelle et veille continue
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Le **Capstone Project B** valide la capacité à analyser globalement la sécurité d'une PME (MedDistri) sous les angles technique et organisationnel.
*   Présenter un audit cyber exige de **traduire les failles techniques en risques métiers** compréhensibles par la Direction Générale.
*   Une soutenance orale réussie repose sur un pitch de **7 minutes structuré**, suivi d'un échange argumenté avec le jury pour justifier ses choix.
*   La cybersécurité exige un engagement de **formation continue et de veille active** (bulletins du CERT-FR) tout au long de sa carrière professionnelle.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Restitution et Synthèse Managériale**
Expliquez aux apprenants comment vulgariser un concept cyber complexe pour convaincre un Comité de Direction. Le Comex ne comprend pas les adresses IP ou les CVSS, il comprend le risque financier, juridique et réputationnel. Montrez comment transformer "Vulnérabilité SQLi sur le serveur" en "Risque de vol de l'intégralité du fichier client entraînant une sanction CNIL de 500k€".

**2. Audit des livrables (Capstone)**
Prenez le temps d'auditer publiquement 2 ou 3 livrables de la salle. Félicitez la structure, pointez du doigt les oublis courants (absence de l'évaluation financière du risque, recommandations trop vagues comme "améliorer la sécurité").

**3. Plan de développement des compétences**
Terminez la session (30 minutes) en orientant les apprenants vers l'avenir : quelles certifications viser (Sec+, CEH, CISSP) ? Comment configurer un laboratoire virtuel (TryHackMe, HackTheBox) pour continuer la pratique ? Comment suivre l'actualité cyber (veille technologique).


*(Même que A_S08 étendu)*. Concluez le parcours. Insistez sur le 'Savoir-Être' du consultant cybersécurité : l'empathie, la pédagogie, et la diplomatie. Expliquez qu'un rapport d'audit agressif qui humilie les développeurs ne sera jamais corrigé. La sécurité nécessite l'adhésion de toutes les équipes (Dev, Ops, RH, Direction).

---

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Présenter et soutenir oralement en équipe les conclusions de votre audit et votre plan d'action pour la PME MedDistri.
* Argumenter et défendre vos choix d'architectures réseau, de gouvernance et de traitement des risques devant un jury d'évaluation.
* Formuler un bilan réflexif sur les compétences professionnelles acquises et planifier votre stratégie de veille technologique post-formation.

---

### Glossaire

*   **Audit de sécurité** — Évaluation formelle et technique de la conformité et de la vulnérabilité d'un système d'information.
*   **Capstone Project** — Projet intégrateur de fin de formation évaluant la capacité à structurer une politique de sécurité complète sur un cas pratique d'entreprise.
*   **CERT-FR** — Centre de veille, d'alerte et de réponse aux attaques informatiques de l'État français, rattaché à l'ANSSI.
*   **CVE (Common Vulnerabilities and Exposures)** — Système d'identification et de référencement public des vulnérabilités logicielles connues.
*   **Plan de remédiation** — Document de synthèse ordonnant les mesures correctives techniques, physiques et organisationnelles pour corriger les failles.
*   **Restitution** — Action de présenter ses travaux et ses conclusions techniques devant un public de décideurs non techniques.
*   **Soutenance de Projet** — Présentation orale synthétique devant un jury visant à démontrer la pertinence et la faisabilité des solutions proposées.

---

### Concepts clés

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

### 1. Le Capstone Project B : Une synthèse transverse
Le **Capstone Project B** marque l'aboutissement de votre parcours de formation de 30 heures. Il simule une mission de conseil cyber réelle pour la PME fictive **MedDistri** (distributeur de matériel médical critique).

Ce projet a requis l'application pratique de l'ensemble des modules étudiés :

*   **Technique** : Conception d'une architecture réseau sécurisée avec segmentation (DMZ, VLANs), durcissement des postes, mise en œuvre d'outils défensifs (pare-feu, IDS) et gestion des accès (MFA, IAM).
*   **Organisationnel** : Élaboration des règles de la PSSI, calcul et priorisation des risques cyber (matrice 4x4), planification de la résilience (sauvegardes 3-2-1, PCA/PRA) et respect des lois sur la protection des données (RGPD).

### 2. Réussir une soutenance de projet cyber
Soutenir un audit de sécurité exige d'adapter sa communication à son auditoire. Les décideurs d'une entreprise (comme la direction de MedDistri) ne sont pas tous des techniciens système. Votre présentation doit donc traduire les vulnérabilités techniques en **enjeux et impacts business**.

#### Structure recommandée pour le diaporama (Pitch de 7 minutes) :
*   **Diapositive 1 — Enjeux et contexte (1 min)** : Rappel de l'activité de MedDistri, ses actifs les plus précieux (données médicales, serveurs de commandes) et ses menaces prioritaires.
*   **Diapositive 2 — Résultats de l'Audit (2 min)** : Cartographie claire et visuelle des vulnérabilités critiques identifiées (ex. absence de sauvegardes externalisées, ports d'administration ouverts sur Internet).
*   **Diapositive 3 — Plan de remédiation (3 min)** : Présentation de votre feuille de route organisée de manière réaliste et planifiée dans le temps (court terme à coût zéro, moyen terme tactique, long terme structurant).
*   **Diapositive 4 — Retours sur investissement (1 min)** : Conclusion sur la valeur ajoutée pour MedDistri (amélioration de la résilience, réduction des risques de sanctions CNIL, préservation de l'image de marque).

#### Gérer les questions du jury :
Le jury cherchera à tester la solidité de votre plan en vous demandant de justifier vos priorités budgétaires (ex. *« Pourquoi dépenser de l'argent dans la formation des salariés avant de déployer un outil de supervision SIEM coûteux ? »*). Vous devez répondre en faisant le lien avec votre analyse de risques : le facteur humain étant la faille la plus exploitée, le former à moindre coût est la mesure au ratio bénéfice/risque le plus élevé.

### 3. Capitalisation professionnelle et veille continue
La fin de la formation n'est pas la fin de votre apprentissage. Le paysage de la cybersécurité évolue quotidiennement avec l'apparition de nouvelles failles de sécurité (**CVE**) et de nouvelles techniques d'attaque.

*   **Valorisation** : Téléchargez vos badges de cours et votre certificat final **IBM SkillsBuild** et intégrez-les à vos profils professionnels (LinkedIn, CV) pour valoriser vos compétences de gestion cyber opérationnelle.
*   **Veille cyber active** : Prenez l'habitude de suivre les bulletins de sécurité officiels (ex. les alertes du **CERT-FR** de l'ANSSI, les articles de cyber.gouv.fr) pour rester informé des vulnérabilités critiques à corriger d'urgence dans vos futurs environnements professionnels.

---

### Activités / exercices
### Exercice 1 — Grille d'évaluation et de notation pour l'auto-évaluation du projet Capstone
**Objectif :** Réaliser une auto-évaluation rigoureuse de la prestation écrite et orale de son équipe avant de soumettre le livrable au jury, afin d'identifier les zones de faiblesse à corriger.

**Consignes :**
Utilisez la grille critériée ci-dessous pour évaluer votre livrable *« Audit & Plan de Remédiation MedDistri »*. Pour chaque critère, attribuez-vous une note de 1 à 4 et identifiez 2 points forts ainsi que 2 axes d'amélioration.

#### Grille d'évaluation type d'un audit de sécurité :

| Critère d'évaluation | Niveau 1 (Insuffisant) | Niveau 2 (Moyen) | Niveau 3 (Bien) | Niveau 4 (Excellent) |
|---|---|---|---|---|
| **1. Analyse des risques** | Risques non identifiés ou vagues. | Risques listés mais sans calcul de criticité. | Risques documentés avec matrice de cotation 4x4. | Analyse approfondie reliant menaces, failles et impacts métiers. |
| **2. Architecture réseau** | Aucune segmentation réseau proposée. | Segmentation proposée mais incohérente. | Segmentation claire (LAN, DMZ, WAN) avec pare-feu. | Schéma réseau complet intégrant VLANs, VPN et règles de filtrage. |
| **3. Gouvernance & PSSI** | Pas de règles organisationnelles définies. | Règles rédigées mais informelles ou trop courtes. | Règles PSSI rédigées et charte utilisateurs esquissée. | Règles PSSI exhaustives, plan de sauvegarde 3-2-1 et PCA/PRA. |
| **4. Clarté du plan de remédiation** | Aucune planification chronologique. | Actions listées en vrac sans priorité claire. | Actions priorisées à court, moyen et long terme. | Feuille de route budgétée, planifiée et adaptée aux ressources de la PME. |

**Exemple de rapport d'auto-évaluation rédigé par un groupe d'apprenants :**

*   **Points forts de notre projet** :
    1.  *Architecture réseau robuste* : Notre proposition de segmentation sépare parfaitement le réseau administratif des serveurs sensibles de commandes médicales via une DMZ stricte.
    2.  *Plan de remédiation réaliste* : Nous avons séparé les actions en 3 phases pour ne pas saturer le budget limité de la PME MedDistri, en commençant par des mesures simples comme le MFA et la sensibilisation.
*   **Axes d'amélioration identifiés** :
    1.  *Détail du PCA/PRA* : Notre plan de continuité d'activité manque de détails sur le temps de rétablissement cible des serveurs en cas d'attaque par ransomware (RTO/RPO).
    2.  *Vulgarisation de l'oral* : Lors de notre répétition, nous avons utilisé des termes trop techniques (comme EDR, SIEM, DMZ) sans en expliquer le sens à des décideurs non techniques. Nous devrons vulgariser ces notions lors du pitch final.

---

### Questions de réflexion
1. Pourquoi est-il indispensable qu'un auditeur en cybersécurité conserve une posture de neutralité absolue et de bienveillance lorsqu'il présente des vulnérabilités critiques aux équipes techniques d'une entreprise auditée ? (Pensez à la gestion de la susceptibilité professionnelle).
2. Si vous deviez choisir une seule mesure de sécurité à mettre en œuvre d'urgence dans une entreprise manquant totalement de budget, laquelle choisiriez-vous et pourquoi ?

**Corrigé / Éléments de réponse :**
1. Critiquer agressivement le travail des équipes pousse ces dernières à se braquer et à refuser de collaborer. La sécurité nécessite l'adhésion de tous.
2. Les mises à jour de sécurité (patchs) et l'utilisation de mots de passe longs (ou MFA). C'est gratuit et cela élimine 80% des attaques basiques.

---


### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Pour bien comprendre la restitution d'un projet de fin d'études en sécurité (Capstone), imaginez le rôle d'un **architecte en bâtiment menant l'audit d'une maison ancienne** :
    - Vous visitez la maison de la cave au grenier, testez la solidité des murs, vérifiez si l'électricité respecte les normes et si les serrures des portes fonctionnent (audit de sécurité).
    - Vous ne vous contentez pas de dire "tout est dangereux". Vous rédigez un rapport clair pour le propriétaire.
    - Vous listez les travaux à réaliser du plus urgent (réparer le toit qui fuit - CVSS critique) au moins urgent (repeindre le portail - hygiène de base).
    - Vous expliquez le projet avec des mots simples pour que le propriétaire comprenne pourquoi ces dépenses sont nécessaires pour sa sécurité quotidienne.

**Exemple d'application professionnelle :**
À la suite d'un audit de sécurité d'un mois, un prestataire présente ses conclusions au comité de direction d'un fabricant industriel. Au lieu de noyer les dirigeants sous le jargon technique, il utilise une échelle de risques claire : la mise en place du MFA sur la messagerie et la segmentation réseau entre l'usine et les bureaux sont présentées comme les deux chantiers prioritaires pour éviter un arrêt total de la production.


### Panorama des solutions du marché (Commerciales & Open-Source)

Pour tester la solidité d'une infrastructure cyber, mener des exercices de crise ou réaliser un audit technique final :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Immersive Labs / Mandiant Crisis Simulations** : Plateformes interactives de pointe permettant de tester la prise de décision des comités de direction lors de simulations de crises cyber (tabletop interactives).
    *   **XM Cyber** : Solution commerciale de simulation d'attaque continue (BAS - Breach and Attack Simulation), révélant en continu les chemins d'attaque menant aux actifs critiques.
    *   **AuditBoard** : Plateforme collaborative pour gérer l'évaluation des contrôles de sécurité et le reporting d'audit auprès de la direction.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **OpenEx** : Plateforme open-source de planification et d'exécution d'exercices de crise cyber développée à l'origine en France (ANSSI/communauté). Elle permet de simuler des e-mails frauduleux, des appels téléphoniques et des posts sur de faux réseaux sociaux pour entraîner les équipes.
    *   **CISA Cyber Security Tabletop Exercises** : Banques gratuites de scénarios et de guides d'animation d'exercices de crise à destination des organisations privées et publiques.
    *   **OpenCTI** : Outil open-source permettant de consigner et de visualiser la cartographie des menaces modélisées lors de l'audit initial.

## 3. Ressources complémentaires

*   **Après la formation** : Ajoutez vos certifications et badges de réussite **IBM SkillsBuild** sur votre profil LinkedIn pour valoriser vos nouvelles compétences auprès des recruteurs.
*   **Veille continue** : Créez un compte sur le portail de veille cyber de l'ANSSI ou abonnez-vous au flux RSS du site de référence *cyber.gouv.fr* pour suivre en direct l'actualité des menaces nationales et internationales.


---

* [ANSSI - Métiers de la cybersécurité](https://cyber.gouv.fr/formations)
* [IBM SkillsBuild](https://skillsbuild.org/)

## 4. Exercice bonus (Sondage Bilan - Livestorm)

*   **Objectif :** Évaluation globale de la posture d'hygiène.
*   **Sondage Livestorm :** Quelle mesure de sécurité simple et gratuite présente le meilleur retour sur investissement immédiat pour une TPE/PME ?
    *   A) Acheter un pare-feu à 5 000 €.
    *   B) Mettre en œuvre une politique de mots de passe robustes associée au MFA gratuit et sensibiliser les collaborateurs *(Bonne réponse)*.
    *   C) Rédiger une charte informatique de 80 pages.
*   **Guide d'animation (pour le mentor) :** Rappelez que l'hygiène cyber de base bloque la majorité des attaques opportunistes sans nécessiter de budgets importants.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Audit de sécurité** | Évaluation formelle et technique de la conformité et de la vulnérabilité d'un système d'information. |
| **Capstone Project** | Projet intégrateur de fin de formation évaluant la capacité à structurer une politique de sécurité complète sur un cas pratique d'entreprise. |
| **CERT-FR** | Centre de veille, d'alerte et de réponse aux attaques informatiques de l'État français, rattaché à l'ANSSI. |
| **CVE (Common Vulnerabilities and Exposures)** | Système d'identification et de référencement public des vulnérabilités logicielles connues. |
| **Plan de remédiation** | Document de synthèse ordonnant les mesures correctives techniques, physiques et organisationnelles pour corriger les failles. |
| **Restitution** | Action de présenter ses travaux et ses conclusions techniques devant un public de décideurs non techniques. |
| **Soutenance de Projet** | Présentation orale synthétique devant un jury visant à démontrer la pertinence et la faisabilité des solutions proposées. |

