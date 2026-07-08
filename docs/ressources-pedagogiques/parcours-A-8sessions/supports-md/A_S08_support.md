# Support de cours — Session 08 : Grand Atelier d'Audit & Synthèse du Parcours
Parcours : A 8 sessions  |  Module : Consolidation & Clôture  |  Niveau : Débutant / Intermédiaire

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session de clôture. Vous y découvrirez :
    - La méthodologie de l'Atelier d'Audit Interactif MedDistri
    - Les clés d'une synthèse managériale efficace pour un dirigeant
    - La valorisation de vos compétences et la suite de votre apprentissage

---

## 1. Introduction

Cette huitième session constitue la clôture du parcours A. Elle remplace l'évaluation académique traditionnelle par un **Grand Atelier d'Audit Interactif** mené en direct en visioconférence. L'objectif est de mobiliser l'ensemble des connaissances acquises (fondations, sécurité réseau, protection des identités, gouvernance, RGPD et réponse aux incidents) pour résoudre collectivement l'étude de cas d'une PME vulnérable, **MedDistri**, et formaliser sa feuille de route de remédiation cyber.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Restitution et Synthèse Managériale**
Expliquez aux apprenants comment vulgariser un concept cyber complexe pour convaincre un Comité de Direction. Le Comex ne comprend pas le jargon technique, il comprend le risque financier, juridique et réputationnel. Montrez comment transformer "Vulnérabilité SQLi sur le serveur" en "Risque de vol de l'intégralité du fichier client entraînant une sanction CNIL de 500k€".

**2. Audit Interactif**
Utilisez les sondages Livestorm pour engager l'auditoire. Laissez 1 minute par vote, puis débriefez en direct les choix faits par le public. Expliquez les forces et faiblesses de chaque option.

**3. Plan de développement des compétences**
Terminez la session (30 minutes) en orientant les apprenants vers l'avenir : quelles certifications viser (Sec+, CEH) ? Comment configurer un laboratoire virtuel (TryHackMe, HackTheBox) pour continuer la pratique ? Comment suivre l'actualité cyber (veille technologique).

---

### Glossaire

*   **Audit de sécurité** — Évaluation méthodique de l'état de sécurité d'une organisation par rapport à des normes ou des règles de l'art.
*   **Feuille de route de remédiation (Remediation Roadmap)** — Plan d'action chronologique et priorisé décrivant les étapes techniques et organisationnelles à accomplir pour corriger les vulnérabilités identifiées lors d'un audit.
*   **Hygiène informatique (Cyber Hygiene)** — Ensemble des règles élémentaires de sécurité à appliquer de manière systématique pour minimiser la majorité des cybermenaces courantes (ex. mises à jour, mots de passe complexes, sauvegardes).
*   **Plan de remédiation** — Document de synthèse ordonnant les mesures correctives techniques, physiques et organisationnelles pour corriger les failles.
*   **Synthèse managériale (Executive Summary)** — Courte introduction synthétique (1 page max) rédigée à l'intention des dirigeants de l'entreprise, résumant les menaces majeures découvertes et le budget requis, exempte de jargon technique trop complexe.
*   **Vulgarisation** — Traduction de concepts techniques complexes en termes simples et compréhensibles par des non-experts (ex. dirigeants business).

---

### Concepts clés de l'Atelier MedDistri

#### 1. L'évaluation de l'existant
L'analyse de l'infrastructure de MedDistri révèle des failles communes à de nombreuses PME :
*   **L'exposition directe d'outils d'administration (ports 22, 3389)** sur Internet sans filtrage IP est une invitation ouverte au piratage par force brute.
*   **L'absence de MFA** sur les messageries cloud Microsoft 365 expose l'entreprise au vol d'identité et à la compromission de factures clients.
*   **La sauvegarde permanente USB** rend la sauvegarde sensible au chiffrement immédiat par un ransomware.

#### 2. Priorisation et réalisme budgétaire
Une PME ne dispose pas de ressources infinies. La feuille de route proposée doit diviser les chantiers dans le temps :
*   **Court terme (Mois 1 — Budget quasi-nul)** : Fermeture des accès ouverts sur le WAN, mise en place du MFA, modification des mots de passe par défaut.
*   **Moyen terme (Mois 2-3 — Investissements de base)** : Tunnelisation des flux via VPN, règle de sauvegarde 3-2-1 isolée, conformité RGPD.
*   **Long terme (Mois 6+ — Consolidation)** : Sensibilisation des employés, scans de vulnérabilités planifiés.

---

### Exercice d'application (Débat Décisionnel : Objections Métier - Livestorm)

**Consignes pour le mentor :** Lancez le sondage pour confronter le public aux réalités du terrain.

*   **Sondage :** La directrice refuse d'imposer l'authentification multifacteur (MFA) car elle craint que les commerciaux ne perdent du temps lors de leurs connexions quotidiennes. Quel argument de sensibilisation est le plus percutant ?
    *   A) Le MFA protège de 99% des attaques par vol d'identifiants, et l'arrêt d'activité en cas de piratage coûtera bien plus cher que 3 secondes par connexion *(Bonne réponse)*.
    *   B) Le MFA est obligatoire par la loi sur la protection des données personnelles.
    *   C) Les commerciaux n'ont pas leur mot à dire sur les choix de sécurité.

**Éléments de débriefing (pour le mentor) :**
- La sécurité doit être présentée sous l'angle du risque financier et opérationnel. Le MFA moderne (notifications push) est aujourd'hui très fluide.

---

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour piloter le plan de remédiation, suivre les vulnérabilités et formaliser la gouvernance :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Tugboat Logic (OneTrust)** : Solution automatisée d'aide à la préparation d'audits (ISO 27001, SOC 2), très prisée pour générer des politiques adaptées aux PME.
    *   **AuditBoard** : Plateforme collaborative pour piloter l'évaluation des contrôles de sécurité et le reporting d'audit auprès de la direction.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **OpenEx** : Plateforme open-source pour simuler des scénarios de crise cyber développée à l'origine en France (ANSSI/communauté).
    *   **Gitea / GitLab Community Edition** : Utilisés en sécurité pour suivre l'avancement des tickets de remédiation technique sous forme de kanbans collaboratifs.

---

## 3. Ressources complémentaires

* **IBM SkillsBuild** : Explorez les cours pour continuer votre parcours d'apprentissage en cybersécurité.
* **ANSSI** : Guide "La cybersécurité pour les TPE/PME en 12 questions".
* **Cybermalveillance.gouv.fr** : Fiches pratiques de sensibilisation pour les entreprises.

---

## 4. Exercice bonus (Sondage Bilan - Livestorm)

*   **Objectif :** Évaluation globale de la posture d'hygiène.
*   **Sondage Livestorm :** Quelle mesure de sécurité simple et gratuite présente le meilleur retour sur investissement immédiat pour une TPE/PME ?
    *   A) Acheter un pare-feu à 5 000 €.
    *   B) Mettre en œuvre une politique de mots de passe robustes associée au MFA gratuit et sensibiliser les collaborateurs *(Bonne réponse)*.
    *   C) Rédiger une charte informatique de 80 pages.
*   **Guide d'animation (pour le mentor) :** Rappelez que l'hygiène cyber de base bloque la majorité des attaques opportunistes sans nécessiter de budgets importants.

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Audit de sécurité** | Évaluation méthodique de l'état de sécurité d'une organisation par rapport à des normes ou des règles de l'art. |
| **Feuille de route de remédiation (Remediation Roadmap)** | Plan d'action chronologique et priorisé décrivant les étapes techniques et organisationnelles à accomplir pour corriger les vulnérabilités identifiées lors d'un audit. |
| **Hygiène informatique (Cyber Hygiene)** | Ensemble des règles de base à appliquer systématiquement (mises à jour, mots de passe complexes, sauvegardes). |
| **Plan de remédiation** | Document structuré détaillant la liste ordonnée des actions correctives à mener pour corriger les failles. |
| **Synthèse managériale (Executive Summary)** | Résumé d'une page vulgarisé résumant les menaces majeures découvertes et le budget requis pour la direction générale. |
| **Vulgarisation** | Traduction de concepts techniques complexes en termes simples et compréhensibles par des non-experts. |
