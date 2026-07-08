# Session B16 — Centre des opérations de sécurité (SOC) & supervision

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Qu'est-ce qu'un SOC ? (Security Operations Center)
    - Le cycle de vie d'une alerte : Vrai vs Faux Positif
    - Les indicateurs de performance (KPIs) du SOC
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Le **SOC** surveille le système d'information 24h/24 pour détecter et répondre aux cyberattaques.
*   Les analystes sont organisés en niveaux : le **L1** qualifie et trie, le **L2** mène l'enquête technique, le **L3** résout la crise et cherche les menaces avancées.
*   Distinguer les **vrais positifs** (attaques réelles) des **faux positifs** (comportements légitimes inhabituels) est la mission quotidienne du L1.
*   Les performances du SOC se mesurent par le **MTTD** (rapidité de détection) et le **MTTR** (rapidité de réaction et de confinement).

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Le fonctionnement d'un SOC (Security Operations Center)**
Détaillez l'organisation d'un SOC en Niveaux (Tier 1, Tier 2, Tier 3). 
- Le T1 trie les événements bruts du SIEM (Security Information and Event Management) et gère les faux positifs.
- Le T2 investigue les incidents confirmés.
- Le T3 fait du *Threat Hunting* proactif pour trouver des menaces invisibles.

**2. Gestion des vulnérabilités et scoring CVSS**
Expliquez comment fonctionne le système CVSS (Common Vulnerability Scoring System). Montrez qu'une faille notée 9.8 (Critique) signifie souvent qu'elle est exploitable à distance, sans authentification, et avec un impact total sur le système. Discutez de la priorisation des patchs (*Patch Management*).

**3. L'automatisation : du SIEM au SOAR**
Prenez 15 minutes pour expliquer la "fatigue des alertes" subie par les analystes. Introduisez la technologie SOAR (Security Orchestration, Automation, and Response) qui permet de créer des *Playbooks* automatisés (ex: isoler automatiquement un poste de travail du réseau s'il communique avec une adresse IP malveillante connue).


*(Même que A_S06 étendu)*. Expliquez la notion de SOC externalisé (MSSP). Pourquoi les PME sous-traitent-elles le SOC ? Parce que la surveillance 24/7 (3x8) requiert au minimum 8 à 10 analystes, ce qui coûte très cher. Détaillez le rôle de la *Threat Intelligence* (CTI) pour enrichir le SOC avec des IOCs (Indicators of Compromise) provenant du monde entier.

---

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Décrire l'organisation humaine, les différents niveaux d'analystes (L1, L2, L3) et les missions d'un Centre d'Opérations de Sécurité (SOC) moderne.
* Modéliser le cycle de vie d'une alerte et qualifier des événements de sécurité pour identifier et écarter les faux positifs.
* Interpréter et calculer les indicateurs clés de performance (KPIs) opérationnels d'un SOC : le MTTD et le MTTR.

---

### Glossaire

*   **Faux Positif (FP)** — Alerte de sécurité déclenchée par un événement informatique légitime et sans danger pour le système.
*   **MTTD (Mean Time To Detect)** — Temps moyen nécessaire pour identifier la présence d'une intrusion ou d'un incident de sécurité.
*   **MTTD (Mean Time To Detect)** — Indicateur mesurant le temps moyen écoulé entre le début d'une intrusion et sa détection par l'équipe de sécurité.
*   **MTTR (Mean Time To Respond)** — Temps moyen nécessaire pour contenir, éradiquer et corriger un incident après sa détection.
*   **MTTR (Mean Time To Respond)** — Indicateur mesurant le temps moyen écoulé entre la détection d'une alerte et la neutralisation de l'incident.
*   **Playbook de sécurité** — Procédure documentée décrivant pas à pas les actions obligatoires à mener par l'analyste face à un type d'alerte spécifique.
*   **SOC (Security Operations Center)** — Centre d'Opérations de Sécurité. Équipe centralisée chargée de la supervision cyber et de la réponse aux alertes.
*   **SOC (Security Operations Center)** — Équipe et centre opérationnel chargés de surveiller et analyser la sécurité d'une organisation en continu (24/7).

---

### Concepts clés

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

### 1. Qu'est-ce qu'un SOC ? (Security Operations Center)
Le **SOC** est la tour de contrôle de la sécurité d'une entreprise. C'est une entité centralisée (composée d'une équipe humaine et d'outils techniques) chargée de surveiller, détecter, analyser et répondre aux cybermenaces pesant sur le système d'information, 24 heures sur 24 et 7 jours sur 7.

#### L'organisation humaine en 3 niveaux d'expertise :
*   **Analyste L1 (Triage et Filtrage)** : C'est la première ligne de défense. L'analyste L1 surveille en permanence la console d'alertes. Son but est de trier le flux continu d'alertes pour éliminer les événements bénins (faux positifs) et escalader les menaces réelles (vrais positifs) vers le niveau supérieur.
*   **Analyste L2 (Investigation)** : Reçoit les alertes qualifiées et jugées suspectes par le L1. Il effectue une investigation approfondie (analyse des processus de la machine, examen de l'historique réseau) pour comprendre la méthode d'attaque de l'intrus et rédiger les consignes de neutralisation de la menace.
*   **Analyste L3 (Threat Hunter & Incident Response)** : Expert senior. Il intervient lors des crises majeures pour diriger les opérations de nettoyage et de reconstruction des serveurs. De plus, il cherche activement des menaces complexes tapies et cachées dans le réseau qui auraient échappé aux outils de détection automatiques (*threat hunting*).

*   *L'analogie des urgences d'un hôpital* :
    *   **L'analyste L1** est l'infirmier d'accueil et de tri. Il prend le pouls des patients arrivant, écarte les petits bobos sans danger, et oriente les cas graves vers les lits de consultation.
    *   **L'analyste L2** est le médecin généraliste de garde. Il examine le patient, l'ausculte, demande des analyses de sang et pose le diagnostic de la maladie.
    *   **L'analyste L3** est le chirurgien spécialiste. Il intervient d'urgence au bloc opératoire pour traiter une crise cardiaque ou opérer un polytraumatisé.

### 2. Le cycle de vie d'une alerte : Vrai vs Faux Positif
Une alerte de sécurité commence par un événement technique brut (ex. une connexion réseau). Cet événement est analysé par les règles du SOC pour générer une alerte. L'analyste L1 doit qualifier cette alerte :

*   **Faux Positif (FP)** : Une activité légitime et inoffensive mais qui a déclenché une alerte car elle ressemble à un comportement suspect.
    *   *Exemple* : Un outil d'inventaire informatique interne qui scanne le réseau de l'entreprise à la recherche de serveurs. Le pare-feu le signale comme une tentative d'intrusion. L'analyste L1 doit identifier la machine d'inventaire et clore l'alerte comme Faux Positif pour éviter la fatigue des alertes (*alert fatigue*).
*   **Vrai Positif (VP)** : Une menace réelle ou une activité malveillante avérée qui nécessite une intervention corrective immédiate.

### 3. Les indicateurs de performance (KPIs) du SOC
Pour mesurer l'efficacité d'un SOC, les directeurs s'appuient sur deux métriques de temps fondamentales :

*   **MTTD (*Mean Time To Detect* / Temps Moyen de Détection)** : Le délai moyen s'écoulant entre le moment où un attaquant pénètre dans le système d'information et le moment où le SOC détecte son activité. Plus le MTTD est bas, plus vite l'alerte est donnée.
*   **MTTR (*Mean Time To Respond* / Temps Moyen de Réponse)** : Le délai moyen s'écoulant entre le moment où l'alerte est détectée par le SOC et le moment où la menace est complètement neutralisée (ex. machine isolée du réseau, compte piraté désactivé).

---

### Activités / exercices
### Exercice 1 — Qualification et triage d'alertes de supervision
**Objectif :** Analyser des alertes de sécurité brutes en tant qu'analyste L1, collecter des indices contextuels et prendre la décision opérationnelle appropriée.

**Consignes :**
Vous êtes analyste SOC L1 de garde pour l'entreprise EcoLog. Les 3 alertes suivantes apparaissent sur votre console de supervision. Pour chacune d'elles, déterminez s'il s'agit d'un **Faux Positif** ou d'un **Vrai Positif**, justifiez votre choix et indiquez l'action que vous menez.

*   **Alerte A** : Connexion administrative SSH réussie sur le serveur de paie RH à 3h15 du matin depuis une adresse IP publique localisée en Asie.
    *   *Élément de contexte* : L'administrateur système officiel d'EcoLog habite en France. Aucun ticket d'intervention technique nocturne n'a été planifié.
*   **Alerte B** : 80 tentatives de connexions échouées en 2 minutes sur le portail Intranet de la DRH, suivies d'une connexion réussie à 9h02.
    *   *Élément de contexte* : Après vérification de l'annuaire interne, le compte appartient à une secrétaire présente physiquement dans les bureaux. Elle confirme par téléphone s'être trompée de mot de passe car sa touche "Verr Maj" était activée par erreur, avant de réussir à se connecter.
*   **Alerte C** : Un poste de travail de l'équipe Comptabilité a exécuté un script PowerShell tentant de copier la base de données locale des utilisateurs vers un serveur externe sur Internet.
    *   *Élément de contexte* : L'employé de la comptabilité déclare n'avoir lancé aucun programme et sa machine présente d'importants ralentissements.

**Corrigé / Éléments de réponse :**

*   **Alerte A** :
    *   *Qualification* : **Vrai Positif (Critique)**.
    *   *Justification* : Connexion sur un serveur très sensible contenant les données de salaire, en pleine nuit, depuis l'étranger et sans changement de planning planifié. Tout indique un vol d'identifiants de connexion.
    *   *Action* : Escalade immédiate en L2 pour isoler la session et réinitialiser les identifiants de l'administrateur. Rédiger un ticket d'incident urgent.
*   **Alerte B** :
    *   *Qualification* : **Faux Positif**.
    *   *Justification* : L'activité ressemble à une attaque par force brute, mais la vérification contextuelle et l'appel de l'utilisatrice confirment une erreur humaine de saisie classique d'un mot de passe légitime.
    *   *Action* : Clôturer le ticket d'alerte en le marquant comme "Faux Positif dû à une erreur de saisie de l'utilisateur". Aucun traitement de sécurité supplémentaire requis.
*   **Alerte C** :
    *   *Qualification* : **Vrai Positif (Majeur)**.
    *   *Justification* : L'activité correspond à une exfiltration de données via script PowerShell, combinée à des ralentissements de la machine. C'est le comportement typique d'un malware ou d'un pirate installé sur le poste.
    *   *Action* : Utiliser l'outil d'administration centrale (EDR) pour isoler immédiatement l'ordinateur portable du réseau local afin d'éviter la propagation, puis escalader au L2 pour investigation de la machine.

---

### Questions de réflexion
1. Pourquoi une trop grande quantité d'alertes inoffensives (faux positifs) présente-t-elle un danger pour la sécurité réelle d'une entreprise ? (Recherchez le concept de "fatigue des alertes").
2. Si un SOC dispose d'outils de détection automatique ultra-performants qui alertent en 30 secondes (MTTD bas), mais que l'équipe met 24 heures à réagir et isoler les serveurs infectés (MTTR élevé), l'entreprise est-elle efficacement protégée contre un ransomware ? Expliquez le rôle des playbooks de sécurité pour réduire le MTTR.

**Corrigé / Éléments de réponse :**
1. La fatigue des alertes pousse les analystes à ignorer ou traiter superficiellement les notifications, augmentant le risque de rater une vraie attaque.
2. Non, si le MTTR (temps de réaction) est de 24h, le ransomware aura chiffré le réseau. Les playbooks permettent d'automatiser les actions (ex: isoler le poste en 5 minutes) pour réduire le MTTR.

---


### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez l'organisation et le fonctionnement d'un SOC (Security Operations Center) comme le personnel des **urgences d'un grand hôpital** :
    - **L'analyste L1 (Triage)** est l'infirmier d'accueil. Il reçoit le flux continu de patients (alertes de sécurité), écarte les cas inoffensifs (un faux positif, comme une fausse alerte de toux), et escalade immédiatement les cas graves (un vrai positif, comme un arrêt cardiaque) vers le niveau supérieur.
    - **L'analyste L2 (Investigation)** est le médecin de garde. Il examine les antécédents médicaux du patient, demande des analyses de sang poussées (forensics de la machine) pour poser un diagnostic précis et rédiger la prescription (les étapes de nettoyage).
    - **L'analyste L3 (Incident Response & Threat Hunter)** est le chirurgien spécialiste. Il intervient d'urgence en salle d'opération pour traiter les cas critiques complexes et mène des recherches préventives de nouvelles maladies (chasse aux menaces cachées).

**Exemple d'application professionnelle :**
Dans le SOC d'une multinationale, l'analyste L1 reçoit une alerte d'un ordinateur exécutant un outil d'administration suspect à 2h du matin. Il vérifie le profil de l'employé (il s'agit d'un comptable non connecté à ces heures). Il escalade l'incident au L2 qui confirme une compromission par cheval de Troie et isole la machine du réseau local en moins de 30 minutes, contenant ainsi la propagation.


## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Security Operations Center (SOC) Fundamentals"* (durée estimée : 1h30).
*   **Activité pratique** : Rechercher la définition d'un outil **SOAR** (*Security Orchestration, Automation, and Response*). Comprendre comment l'automatisation permet de bloquer automatiquement une machine compromise sans intervention humaine pour réduire le MTTR à quelques secondes.


---

* [CERT-FR - Signalement d'incidents](https://www.cert.ssi.gouv.fr/)
* [ANSSI - Externalisation SOC](https://cyber.gouv.fr)

## 4. Exercice bonus

- **Objectif :** Qualification opérationnelle d'alertes SOC et calcul de KPIs.
- **Consignes :**
    1. Calculez le MTTD (Temps Moyen de Détection) et le MTTR (Temps Moyen de Réponse) pour les 3 incidents suivants :
       - Incident A : intrusion à 10h00, détectée à 10h10, neutralisée à 10h40.
       - Incident B : intrusion à 14h00, détectée à 14h30, neutralisée à 15h30.
       - Incident C : intrusion à 22h00, détectée à 22h05, neutralisée à 23h05.
    2. Commentez les résultats obtenus et proposez une action pour réduire le MTTR d'une équipe.
- **Correction pour le mentor :** Calcul des temps :
  - Incident A : Détection = 10 min, Réponse = 30 min.
  - Incident B : Détection = 30 min, Réponse = 60 min.
  - Incident C : Détection = 5 min, Réponse = 60 min.
  - **MTTD Moyen** = (10 + 30 + 5) / 3 = 15 minutes.
  - **MTTR Moyen** = (30 + 60 + 60) / 3 = 50 minutes.
  Pour réduire le MTTR, les apprenants doivent proposer l'automatisation d'actions de confinement via des *playbooks* ou un outil SOAR (ex. isolation automatique d'une machine suspecte en quelques secondes).

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Faux Positif (FP)** | Alerte de sécurité déclenchée par un événement informatique légitime et sans danger pour le système. |
| **MTTD (Mean Time To Detect)** | Temps moyen nécessaire pour identifier la présence d'une intrusion ou d'un incident de sécurité. |
| **MTTR (Mean Time To Respond)** | Temps moyen nécessaire pour contenir, éradiquer et corriger un incident après sa détection. |
| **Playbook de sécurité** | Procédure documentée décrivant pas à pas les actions obligatoires à mener par l'analyste face à un type d'alerte spécifique. |
| **SOC (Security Operations Center)** | Centre d'Opérations de Sécurité. Équipe centralisée chargée de la supervision cyber et de la réponse aux alertes. |

