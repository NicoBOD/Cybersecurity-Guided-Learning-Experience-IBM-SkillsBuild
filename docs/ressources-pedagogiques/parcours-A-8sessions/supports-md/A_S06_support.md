# Support de cours — Session 06 : Opérations de sécurité & gestion des vulnérabilités
Parcours : A 8 sessions  |  Module : SecOps & Vulnérabilités  |  Niveau : Débutant

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - La surveillance active : Le couple SOC et SIEM
    - Identifier les failles : Scans de vulnérabilités vs Test d'intrusion
    - Prioriser la remédiation : Comprendre le score CVSS
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

Une politique de sécurité robuste ne se limite pas à installer des protections statiques : elle exige une surveillance active et continue. Ce support de cours détaille le fonctionnement des centres d'opérations de sécurité (*SOC*) et des outils de corrélation de journaux d'événements (*SIEM*), qui constituent les yeux et les oreilles de la cybersécurité moderne. Vous étudierez la notion essentielle de journalisation (*logs*), trace numérique indispensable pour détecter et comprendre les attaques. Nous aborderons ensuite la gestion des vulnérabilités logicielles, en apprenant à faire la différence entre un scan automatisé et un test d'intrusion. Enfin, vous apprendrez à déchiffrer et à interpréter les scores du système de notation internationale *CVSS* afin de planifier et prioriser de manière pragmatique l'application des correctifs de sécurité (*patchs*) sans impacter l'activité opérationnelle de votre entreprise.

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


---

### Glossaire

*   **CVE (Common Vulnerabilities and Exposures)** — Dictionnaire public recensant et identifiant de manière unique les failles de sécurité logicielles et matérielles connues (ex. CVE-2021-44228).
*   **CVE (Common Vulnerabilities and Exposures)** — Base de données publique répertoriant les vulnérabilités de sécurité logicielle connues de façon unique.
*   **CVSS (Common Vulnerability Scoring System)** — Système de notation standardisé évaluant la gravité d'une vulnérabilité informatique sur une échelle de 0.0 (inoffensive) à 10.0 (critique).
*   **CVSS (Common Vulnerability Scoring System)** — Système de notation standardisé évaluant la gravité d'une vulnérabilité informatique sur une échelle de 0 à 10.
*   **Faux Positif** — Une alerte de sécurité déclenchée à tort par un outil de surveillance face à une activité légitime (ex. un employé légitime qui se trompe de mot de passe trois fois).
*   **Log (Journal d'événements)** — Fichier texte généré automatiquement par un système, une application ou un équipement, enregistrant les actions, connexions et erreurs survenues chronologiquement.
*   **Patch (Correctif)** — Mise à jour logicielle publiée par un éditeur pour corriger des erreurs de programmation ou combler des failles de sécurité.
*   **SIEM (Security Information and Event Management)** — Logiciel centralisant les journaux d'événements (logs) de divers équipements réseau et serveurs pour y appliquer des règles de corrélation et lever des alertes en cas de comportement suspect.
*   **SIEM (Security Information and Event Management)** — Solution logicielle qui centralise, normalise et corrèle les logs de sécurité pour identifier des menaces.
*   **SOC (Security Operations Center)** — Centre opérationnel où des analystes surveillent et analysent en continu la sécurité du système d'information pour détecter les incidents.
*   **SOC (Security Operations Center)** — Centre opérationnel composé d'experts chargé de surveiller, détecter et répondre aux alertes de sécurité en temps réel.

---

### 1. La surveillance active : Le couple SOC et SIEM

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.


Pour sécuriser une grande infrastructure, il est impossible de regarder manuellement les écrans de chaque ordinateur. On centralise les informations.

#### A. Les Journaux d'événements (Logs) : La trace numérique
Chaque fois qu'un utilisateur se connecte, qu'un fichier est modifié ou qu'un pare-feu bloque un flux, une ligne de log est générée.
*Exemple de log d'accès simplifié* :
```text
2026-06-29 16:30:12 | IP: 192.168.1.100 | User: j.dupont | Action: LOGIN_SUCCESS | App: Intranet
```
Ces logs sont indispensables pour comprendre le scénario d'une attaque passée ou détecter une intrusion en cours.

#### B. Le SIEM : Le moteur de corrélation
Le SIEM reçoit des millions de lignes de logs par jour provenant de toutes les machines. Grâce à des règles prédéfinies, il détecte des corrélations suspectes :

* *Règle de corrélation* : Si la machine A subit 50 échecs de connexion en 1 minute (log de sécurité Windows) ET qu'immédiatement après, elle envoie 10 Go de données vers Internet (log pare-feu), ALORS générer une alerte critique pour "Suspicion d'attaque par force brute réussie".

#### C. Le SOC : Les analystes humains
L'alerte générée par le SIEM est prise en charge par un analyste SOC. L'analyste doit rapidement qualifier l'alerte : s'agit-il d'un **vrai incident** exigeant une réaction immédiate, ou d'un **faux positif** (une alerte déclenchée à tort par une activité bénigne) ?



### 2. Identifier les failles : Scans de vulnérabilités vs Test d'intrusion

Maintenir un bon niveau de sécurité nécessite de tester activement ses défenses. On utilise pour cela deux approches complémentaires :

* **Le scan de vulnérabilités** : Outil logiciel automatisé (ex. Nessus, OpenVAS) qui scanne le réseau et compare les versions des programmes installés avec une base de données de failles connues (la base des **CVE**). Il est rapide, peu coûteux et peut être exécuté fréquemment, mais il génère des faux positifs et ne détecte pas les failles logiques complexes.
* **Le test d'intrusion (*Pentest*)** : Audit mené par un expert humain (un *pentester* ou hacker éthique) qui cherche manuellement à s'introduire dans le réseau en exploitant et en combinant plusieurs vulnérabilités, y compris des faiblesses logiques ou humaines. Il est plus coûteux mais reflète fidèlement la réalité d'une attaque ciblée.



### 3. Prioriser la remédiation : Comprendre le score CVSS

Un scan de sécurité sur une entreprise moyenne peut remonter des centaines de vulnérabilités. On utilise le score CVSS pour savoir lesquelles corriger en premier.

Le score CVSS varie de **0.0 à 10.0** et s'appuie sur plusieurs critères d'évaluation :

* **Le vecteur d'accès** : La faille est-elle exploitable à distance via Internet (gravité max) ou nécessite-t-elle un accès physique à la machine ?
* **La complexité d'exploitation** : Est-elle facile à exploiter (ex. via un script public disponible) ou très complexe ?
* **Les privilèges requis** : Faut-il être déjà authentifié comme administrateur pour l'exploiter ?
* **L'impact sur la triade CIA** : La faille permet-elle de lire des données secrètes, de modifier des fichiers ou de bloquer le serveur ?

```text
[ 0.0 - 3.9 ] ➔ Faible  |  [ 4.0 - 6.9 ] ➔ Moyenne  |  [ 7.0 - 8.9 ] ➔ Élevée  |  [ 9.0 - 10.0 ] ➔ Critique
```

*Règle opérationnelle* : Une faille avec un score de 9.8 exploitable à distance sans authentification sur un serveur web de production doit être patchée immédiatement (dans les 24h). Une faille de score 3.2 nécessitant un accès physique local peut être traitée lors d'une maintenance ultérieure.

---

### Focus pratique
Voici une simulation de feuille de route de remédiation basée sur un scan de sécurité :

| Identifiant CVE | Description simplifiée | Score CVSS | Expositions / Contexte | Priorité de traitement | Action proposée |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **CVE-2024-XXXX** | Exécution de code à distance sur serveur web public. | **9.8 (Critique)** | Serveur hébergeant le site e-commerce de l'entreprise. | **1 (Immédiate)** | Appliquer le correctif de l'éditeur sous 24h. |
| **CVE-2023-YYYY** | Fuite d'informations mémoire locale sur postes de travail. | **4.3 (Moyen)** | Postes des collaborateurs situés derrière le pare-feu. | **3 (Basse)** | Intégrer la mise à jour dans le cycle mensuel de patching. |
| **CVE-2024-ZZZZ** | Élévation de privilèges sur le serveur de bases de données. | **7.8 (Élevé)** | Serveur interne contenant les données financières. | **2 (Sous 7 jours)** | Isoler le serveur et planifier le patch lors de la maintenance hebdo. |

---

### Exercice d'application (Analyse de Gravité de Vulnérabilités - Livestorm)

**Consignes pour le mentor :** Lancez le sondage pour tester la compréhension de la priorisation des vulnérabilités.

*   **Sondage 1 :** Un scan de vulnérabilités révèle une faille avec un score CVSS de 9.8. Comment qualifiez-vous cette faille et quelle doit être votre réaction ?
    *   A) Faible — À corriger lors de la prochaine maintenance annuelle.
    *   B) Critique — Nécessite une remédiation urgente ou l'application immédiate du patch constructeur *(Bonne réponse)*.
    *   C) Moyenne — À corriger d'ici la fin du mois.
*   **Sondage 2 :** Une faille de score 8.5 (Haute) touche un serveur web interne non exposé sur Internet. Une faille de score 7.5 (Haute) touche un serveur web de production exposé publiquement. Laquelle patchez-vous en premier ?
    *   A) La faille de score 8.5 car son score brut est plus élevé.
    *   B) La faille de score 7.5 car l'exposition sur Internet augmente drastiquement la probabilité d'exploitation réelle *(Bonne réponse)*.
    *   C) Aucune, j'attends le prochain audit externe.

**Éléments de débriefing (pour le mentor) :**
- La criticité réelle dépend du score CVSS brut ET du contexte d'exposition de la machine (surface d'attaque).

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez la surveillance de la sécurité de votre entreprise comme la protection d'un **centre commercial** :
    - **Le SOC (Security Operations Center)** est le PC de sécurité central où les agents surveillent en temps réel les caméras de surveillance (logs d'événements).
    - **Le SIEM** est le système d'alarme intelligent qui analyse toutes les caméras en même temps : si un détecteur s'active à la porte A et qu'une personne court vers la sortie B 5 secondes après, il génère une alerte d'intrusion automatique.
    - **Le Scan de vulnérabilités** est le garde qui fait sa ronde la nuit pour vérifier physiquement si des fenêtres sont restées ouvertes ou si des serrures sont endommagées.
    - **Le Score CVSS** est la note d'urgence attribuée à une vitre brisée : une vitre brisée au rez-de-chaussée (CVSS 9.8) est bien plus urgente à réparer qu'une poignée de porte lâche au 3ème étage (CVSS 3.0).

**Exemple d'application professionnelle :**
Dans une banque, le SIEM détecte qu'un compte utilisateur s'est connecté depuis la France puis depuis la Chine 10 minutes plus tard. Le SOC qualifie cette alerte de "Vrai Positif" (vitesse de déplacement impossible) et bloque immédiatement la session de l'utilisateur, évitant ainsi le vol de données bancaires.


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

## 3. Ressources complémentaires

* **IBM SkillsBuild** : Cours sur le fonctionnement d'un SIEM et le métier d'analyste SOC.
* **NIST** : Base de données nationale des vulnérabilités (NVD - National Vulnerability Database) pour rechercher des identifiants CVE.
* **FIRST.org** : Calculateur officiel des scores CVSS (pour comprendre l'impact des différentes variables de cotation).


---

* [CERT-FR - Alertes de sécurité](https://www.cert.ssi.gouv.fr/)
* [OWASP - Top 10 Web](https://owasp.org/www-project-top-ten/)

## 4. Exercice bonus (Sondage Mises à Jour - Livestorm)

*   **Objectif :** Évaluation des risques liés aux correctifs.
*   **Sondage Livestorm :** L'éditeur d'un logiciel métier publie un correctif de sécurité urgent. Le technicien refuse de l'installer immédiatement par crainte de bloquer la production. Quelle est la meilleure approche ?
    *   A) Ne jamais installer la mise à jour pour préserver la stabilité.
    *   B) Tester le correctif sur un poste de test pendant 24h avant de le déployer à grande échelle *(Bonne réponse)*.
    *   C) Forcer le déploiement sur tous les serveurs à 14h sans prévenir les équipes.
*   **Guide d'animation (pour le mentor) :** Débattez du compromis permanent en cybersécurité entre la sécurité (appliquer les patchs) et la disponibilité opérationnelle (tester pour ne pas casser la production).

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **CVE (Common Vulnerabilities and Exposures)** | Dictionnaire public recensant et identifiant de manière unique les failles de sécurité logicielles et matérielles connues (ex. CVE-2021-44228). |
| **CVSS (Common Vulnerability Scoring System)** | Système de notation standardisé évaluant la gravité d'une vulnérabilité informatique sur une échelle de 0.0 (inoffensive) à 10.0 (critique). |
| **Faux Positif** | Une alerte de sécurité déclenchée à tort par un outil de surveillance face à une activité légitime (ex. un employé légitime qui se trompe de mot de passe trois fois). |
| **Log (Journal d'événements)** | Fichier texte généré automatiquement par un système, une application ou un équipement, enregistrant les actions, connexions et erreurs survenues chronologiquement. |
| **Patch (Correctif)** | Mise à jour logicielle publiée par un éditeur pour corriger des erreurs de programmation ou combler des failles de sécurité. |
| **SIEM (Security Information and Event Management)** | Logiciel centralisant les journaux d'événements (logs) de divers équipements réseau et serveurs pour y appliquer des règles de corrélation et lever des alertes en cas de comportement suspect. |
| **SOC (Security Operations Center)** | Centre opérationnel où des analystes surveillent et analysent en continu la sécurité du système d'information pour détecter les incidents. |

