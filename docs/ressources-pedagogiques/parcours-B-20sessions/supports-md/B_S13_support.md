# Session B13 — Gouvernance & cadres de sécurité

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - La Politique de Sécurité des Systèmes d'Information (PSSI)
    - Les référentiels mondiaux : ISO 27001 vs NIST CSF
    - Rôles et responsabilités : Direction vs RSSI
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   La **PSSI** définit le cadre légal et technique de la sécurité. Elle doit être validée et portée politiquement par la **Direction Générale** pour être contraignante.
*   L'**ISO 27001** structure le management de la sécurité (SMSI) autour de l'amélioration continue (**PDCA**), tandis que le **NIST CSF** fournit un cadre d'action opérationnel basé sur 5 fonctions techniques.
*   Le **RSSI** propose et orchestre les mesures de sécurité, mais c'est la **Direction Générale** qui prend les décisions stratégiques et financières de couverture des risques.

---

## 2. Développement
Détaillez la différence entre la Sécurité Opérationnelle (Pare-feu) et la Gouvernance. L'ISO 27001 ne prescrit aucune solution technique, elle impose la création d'un Système de Management (SMSI) avec des processus, des politiques écrites (PSSI), des audits réguliers et l'implication formelle de la direction générale.

---

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer la structure, l'utilité et le processus d'élaboration d'une Politique de Sécurité des Systèmes d'Information (PSSI).
* Comparer les référentiels de sécurité mondiaux ISO 27001 (management organisationnel) et NIST CSF (cadre opérationnel technique).
* Identifier la répartition des rôles et responsabilités entre la Direction Générale et le RSSI au sein de la gouvernance de sécurité d'une entreprise.

---

### Glossaire

*   **ISO 27001** — Norme internationale définissant les exigences de mise en place et de certification d'un SMSI.
*   **NIST CSF (Cybersecurity Framework)** — Cadre de référence américain de cybersécurité structuré en 5 fonctions clés (Identifier, Protéger, Détecter, Répondre, Restaurer).
*   **PDCA (Plan, Do, Check, Act)** — Cycle d'amélioration continue (ou roue de Deming) à la base du management de la qualité et des normes ISO.
*   **PSSI** — Politique de Sécurité des Systèmes d'Information. Document de référence traduisant la stratégie de sécurité de l'entreprise en règles opérationnelles.
*   **RSSI (CISO)** — Responsable de la Sécurité des Systèmes d'Information. Expert technique et organisationnel chargé de piloter la sécurité informatique de l'organisation.
*   **SMSI** — Système de Management de la Sécurité de l'Information. Cadre organisationnel (processus, personnes, technologies) visant à protéger l'information d'une entreprise.

---

### Concepts clés

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

### 1. La Politique de Sécurité des Systèmes d'Information (PSSI)
La **PSSI** est le document de référence stratégique et juridique d'une entreprise. Elle traduit les objectifs de sécurité en règles d'usage précises et en exigences techniques obligatoires pour l'ensemble des collaborateurs et prestataires.

*   **Portage par la direction** : Une PSSI ne doit pas être un simple document technique rédigé dans son coin par le service informatique. Pour être légitime, applicable et juridiquement contraignante, elle doit être **validée et signée par la Direction Générale** (souvent annexée au règlement intérieur de l'entreprise).
*   **Structure classique d'une PSSI** :
    *   *Champ d'application* : Qui et quels équipements sont concernés.
    *   *Rôles et responsabilités* : Qui gère la sécurité, qui valide les accès.
    *   *Règles d'usage informatique* : Complexité des mots de passe, règles d'usage de la messagerie, charte de télétravail, gestion du matériel d'entreprise.
    *   *Sanctions* : Conséquences prévues en cas de violation volontaire des règles.

### 2. Les référentiels mondiaux : ISO 27001 vs NIST CSF
Pour concevoir leur stratégie cyber, les entreprises s'appuient sur des cadres de référence reconnus mondialement :

*   **ISO/IEC 27001 (Management de la sécurité)** : C'est la norme internationale décrivant la mise en place d'un **SMSI** (Système de Management de la Sécurité de l'Information). Elle repose sur le principe de l'amélioration continue (la roue de Deming ou **PDCA** : *Plan, Do, Check, Act*). C'est une démarche organisationnelle globale qui aboutit, après audit externe, à une certification officielle très valorisée auprès des clients.
*   **NIST CSF (Cybersecurity Framework - Cadre d'action technique)** : Proposé par l'organisme public américain NIST, c'est un cadre pragmatique, axé sur la gestion opérationnelle et technique des risques. Il structure la défense autour de **5 fonctions clés** :
    1.  **Identify (Identifier)** : Cartographier les actifs matériels, logiciels et les risques.
    2.  **Protect (Protéger)** : Mettre en œuvre des barrières de sécurité (pare-feu, IAM, formation).
    3.  **Detect (Détecter)** : Déployer des outils pour identifier les anomalies en continu (supervision).
    4.  **Respond (Répondre)** : Définir des procédures de réaction rapide en cas d'attaque détectée.
    5.  **Recover (Restaurer)** : Planifier la restauration des systèmes d'information (sauvegardes, continuité).

*   *L'analogie du bâtiment* :
    *   **ISO 27001** est le code de la construction et le manuel de gestion de l'immeuble. Il garantit que vous avez mis en place des comités de suivi, des processus de réévaluation et des audits pour veiller à la qualité continue du bâtiment.
    *   **NIST CSF** est le plan d'action opérationnel des pompiers et de la sécurité physique de l'immeuble. Il détaille exactement comment verrouiller les portes (Protect), où installer les détecteurs de fumée (Detect), et comment évacuer les occupants en cas d'incendie (Respond/Recover).

### 3. Rôles et responsabilités : Direction vs RSSI
La gouvernance cyber exige une distinction claire entre le pouvoir de décision et le rôle d'expertise :

*   **Le RSSI (Responsable de la Sécurité des Systèmes d'Information / *CISO*)** : C'est l'expert, le conseiller et le chef d'orchestre. Il analyse les menaces, rédige la PSSI, recommande des investissements techniques et sensibilise les équipes. **Le RSSI conseille, mais il ne prend pas les décisions stratégiques finales**.
*   **La Direction Générale** : C'est l'arbitre et le donneur d'ordres. C'est elle qui valide les budgets de sécurité, accepte formellement le niveau de risque restant, et assume la responsabilité civile et pénale en cas de sinistre majeur ou de fuite de données.

---

### Activités / exercices
### Exercice 1 — Rédaction d'une charte PSSI simplifiée sur les accès logiques
**Objectif :** Formaliser des règles de sécurité claires, exploitables et compréhensibles par les utilisateurs finaux dans le cadre d'une PSSI.

**Consignes :**
L'entreprise de logistique "EcoLog" souhaite intégrer une section "Sécurité des accès logiques et télétravail" dans sa PSSI. Rédigez 4 règles impératives à destination des salariés, en évitant le jargon trop technique mais en fixant des obligations claires et mesurables. 

*Indication : Pensez aux mots de passe, au MFA, à l'usage des terminaux personnels, et au verrouillage d'écran.*

**Corrigé / Éléments de réponse :**

*   **Règle 1 (Mots de passe)** : *"Chaque collaborateur doit utiliser un mot de passe unique composé d'au moins 12 caractères, comprenant des majuscules, des minuscules, des chiffres et des caractères spéciaux. L'usage d'un gestionnaire de mots de passe d'entreprise est obligatoire pour stocker ces secrets."*
    *   *Justification* : Prévient les attaques par force brute ou dictionnaire et évite la réutilisation de mots de passe identiques.
*   **Règle 2 (Authentification forte)** : *"L'authentification multifacteur (MFA) doit obligatoirement être activée pour toute connexion à distance au réseau de l'entreprise (VPN) ou aux applications Cloud d'entreprise."*
    *   *Justification* : Protège les comptes en cas de vol de mot de passe à la suite d'un hameçonnage.
*   **Règle 3 (Télétravail & Équipements)** : *"Il est strictement interdit d'utiliser un ordinateur personnel pour accéder aux applications internes ou traiter des données de l'entreprise. Seuls les ordinateurs portables fournis et configurés par le service informatique d'EcoLog sont autorisés."*
    *   *Justification* : Garantit que les outils de sécurité (EDR, pare-feu local) sont actifs sur les machines traitant les données de l'entreprise.
*   **Règle 4 (Sécurité physique du poste)** : *"Tout collaborateur quittant son poste de travail, même temporairement, doit obligatoirement verrouiller sa session informatique (touche Raccourci Windows + L)."*
    *   *Justification* : Évite qu'une personne de passage (visiteur, personnel d'entretien) n'accède à des données sensibles à l'insu de l'employé.

---

### Questions de réflexion
1. Pourquoi est-il risqué qu'un RSSI soit directement rattaché à la Direction Informatique (DSI) plutôt qu'au Secrétariat Général ou à la Direction des Risques ? (Pensez aux conflits d'intérêts entre la production informatique et le contrôle de sécurité).
2. Si une entreprise est certifiée ISO 27001, cela signifie-t-il qu'elle est techniquement impossible à pirater ? Expliquez la différence entre un système de management de la sécurité et une garantie de sécurité absolue.

**Corrigé / Éléments de réponse :**
1. La DSI priorise souvent la disponibilité et les délais, tandis que le RSSI priorise la sécurité. Ce conflit d'intérêts rend le RSSI impuissant s'il est sous les ordres du DSI.
2. L'ISO 27001 atteste que l'entreprise a mis en place de bons processus d'amélioration de la sécurité, mais le risque zéro n'existe pas.

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
    *   **Tugboat Logic (OneTrust)** : Outil de conformité automatisé guidant pas à pas les PME et start-ups dans la rédaction de leurs politiques de sécurité et la préparation à la certification ISO 27001.
    *   **AuditBoard** : Plateforme de premier plan pour gérer les programmes de conformité, l'audit interne et le suivi des exigences de sécurité auprès des collaborateurs.
    *   **ServiceNow Policy and Compliance** : Solution d'entreprise haut de gamme pour centraliser et valider le respect des processus internes par rapport aux réglementations.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **EBIOS RM Manager** : Modèles d'analyse et de documents en accès libre pour structurer la rédaction d'une PSSI conformément aux normes françaises de l'ANSSI.
    *   **PIA Tool (CNIL)** : Solution open-source gratuite pour cartographier et analyser la conformité des traitements de données personnelles.
    *   **Monarc** : Outil open-source de gestion de la conformité et des risques de sécurité de l'information développé au Luxembourg, idéal pour aligner sa PSSI sur l'ISO 27001.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Cybersecurity Governance and Risk Management - Part 1"* (durée estimée : 1h30).
*   **Ressource complémentaire** : Visiter le site de l'ANSSI (cyber.gouv.fr) et télécharger le document *"La PSSI en 10 principes de base"* pour observer comment un État structure ses exigences nationales.


---

* [ANSSI - EBIOS RM](https://cyber.gouv.fr/la-methode-ebios-risk-manager)
* [CNIL - PIA / Analyse d'impact](https://www.cnil.fr)

## 4. Exercice bonus

- **Objectif :** Rédaction d'une clause de PSSI (BYOD).
- **Consignes :**
    1. Dans le cadre de la rédaction de la PSSI de votre entreprise, vous devez rédiger la clause encadrant l'usage des smartphones personnels des employés pour accéder aux e-mails professionnels (règle BYOD).
    2. Rédigez 3 règles d'usage simples mais contraignantes pour le collaborateur (ex. verrouillage d'écran obligatoire).
    3. Indiquez la mesure technique que le département informatique doit déployer sur le téléphone pour séparer les données privées des données pro.
- **Correction pour le mentor :** Les règles d'usage rédigées doivent imposer : 1. Un mot de passe ou schéma de déverrouillage fort obligatoire sur le smartphone. 2. L'interdiction de prêter le téléphone à des tiers (famille, amis) pour un usage professionnel. 3. L'obligation de signaler immédiatement la perte ou le vol du mobile. La mesure technique attendue est le déploiement d'un conteneur sécurisé ou d'une solution MDM/MAM (Mobile Device Management) pour isoler les applications professionnelles et permettre leur effacement à distance sans altérer les photos personnelles.

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **ISO 27001** | Norme internationale définissant les exigences de mise en place et de certification d'un SMSI. |
| **NIST CSF (Cybersecurity Framework)** | Cadre de référence américain de cybersécurité structuré en 5 fonctions clés (Identifier, Protéger, Détecter, Répondre, Restaurer). |
| **PDCA (Plan, Do, Check, Act)** | Cycle d'amélioration continue (ou roue de Deming) à la base du management de la qualité et des normes ISO. |
| **PSSI** | Politique de Sécurité des Systèmes d'Information. Document de référence traduisant la stratégie de sécurité de l'entreprise en règles opérationnelles. |
| **RSSI (CISO)** | Responsable de la Sécurité des Systèmes d'Information. Expert technique et organisationnel chargé de piloter la sécurité informatique de l'organisation. |
| **SMSI** | Système de Management de la Sécurité de l'Information. Cadre organisationnel (processus, personnes, technologies) visant à protéger l'information d'une entreprise. |

