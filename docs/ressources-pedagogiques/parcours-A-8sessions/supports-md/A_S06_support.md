# Support de cours — Session 06 : Opérations de sécurité & gestion des vulnérabilités
Parcours : A 8 sessions  |  Module : SecOps & Vulnérabilités  |  Niveau : Débutant

---

!!! abstract "Résumé"
    Une politique de sécurité robuste ne se limite pas à installer des protections statiques : elle exige une surveillance active et continue. Ce support de cours détaille le fonctionnement des centres d'opérations de sécurité (*SOC*) et des outils de corrélation de journaux d'événements (*SIEM*), qui constituent les yeux et les oreilles de la cybersécurité moderne. Vous étudierez la notion essentielle de journalisation (*logs*), trace numérique indispensable pour détecter et comprendre les attaques. Nous aborderons ensuite la gestion des vulnérabilités logicielles, en apprenant à faire la différence entre un scan automatisé et un test d'intrusion. Enfin, vous apprendrez à déchiffrer et à interpréter les scores du système de notation internationale *CVSS* afin de planifier et prioriser de manière pragmatique l'application des correctifs de sécurité (*patchs*) sans impacter l'activité opérationnelle de votre entreprise.

---

## Glossaire de la session
* **SOC (Security Operations Center)** : Centre opérationnel où des analystes surveillent et analysent en continu la sécurité du système d'information pour détecter les incidents.
* **SIEM (Security Information and Event Management)** : Logiciel centralisant les journaux d'événements (logs) de divers équipements réseau et serveurs pour y appliquer des règles de corrélation et lever des alertes en cas de comportement suspect.
* **Log (Journal d'événements)** : Fichier texte généré automatiquement par un système, une application ou un équipement, enregistrant les actions, connexions et erreurs survenues chronologiquement.
* **Faux Positif** : Une alerte de sécurité déclenchée à tort par un outil de surveillance face à une activité légitime (ex. un employé légitime qui se trompe de mot de passe trois fois).
* **CVE (Common Vulnerabilities and Exposures)** : Dictionnaire public recensant et identifiant de manière unique les failles de sécurité logicielles et matérielles connues (ex. CVE-2021-44228).
* **CVSS (Common Vulnerability Scoring System)** : Système de notation standardisé évaluant la gravité d'une vulnérabilité informatique sur une échelle de 0.0 (inoffensive) à 10.0 (critique).
* **Patch (Correctif)** : Mise à jour logicielle publiée par un éditeur pour corriger des erreurs de programmation ou combler des failles de sécurité.

---

## Contenu théorique

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

---

### 2. Identifier les failles : Scans de vulnérabilités vs Test d'intrusion

Maintenir un bon niveau de sécurité nécessite de tester activement ses défenses. On utilise pour cela deux approches complémentaires :

* **Le scan de vulnérabilités** : Outil logiciel automatisé (ex. Nessus, OpenVAS) qui scanne le réseau et compare les versions des programmes installés avec une base de données de failles connues (la base des **CVE**). Il est rapide, peu coûteux et peut être exécuté fréquemment, mais il génère des faux positifs et ne détecte pas les failles logiques complexes.
* **Le test d'intrusion (*Pentest*)** : Audit mené par un expert humain (un *pentester* ou hacker éthique) qui cherche manuellement à s'introduire dans le réseau en exploitant et en combinant plusieurs vulnérabilités, y compris des faiblesses logiques ou humaines. Il est plus coûteux mais reflète fidèlement la réalité d'une attaque ciblée.

---

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

## Focus pratique : Utilisation des CVE & CVSS pour la priorisation

Voici une simulation de feuille de route de remédiation basée sur un scan de sécurité :

| Identifiant CVE | Description simplifiée | Score CVSS | Expositions / Contexte | Priorité de traitement | Action proposée |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **CVE-2024-XXXX** | Exécution de code à distance sur serveur web public. | **9.8 (Critique)** | Serveur hébergeant le site e-commerce de l'entreprise. | **1 (Immédiate)** | Appliquer le correctif de l'éditeur sous 24h. |
| **CVE-2023-YYYY** | Fuite d'informations mémoire locale sur postes de travail. | **4.3 (Moyen)** | Postes des collaborateurs situés derrière le pare-feu. | **3 (Basse)** | Intégrer la mise à jour dans le cycle mensuel de patching. |
| **CVE-2024-ZZZZ** | Élévation de privilèges sur le serveur de bases de données. | **7.8 (Élevé)** | Serveur interne contenant les données financières. | **2 (Sous 7 jours)** | Isoler le serveur et planifier le patch lors de la maintenance hebdo. |

---

## Exercice d'application (self-paced)
**Titre** : Décryptage d'une alerte SOC à partir d'un journal d'événements

### Énoncé
Vous êtes analyste de sécurité junior dans un SOC. Le SIEM vient de lever une alerte de niveau élevé concernant le serveur de fichiers de l'entreprise. Vous disposez de l'extrait de logs suivant pour analyser la situation :

```text
[16:45:01] LOGIN_FAILED | IP: 198.51.100.12 (Russie) | User: admin
[16:45:03] LOGIN_FAILED | IP: 198.51.100.12 (Russie) | User: administrator
[16:45:05] LOGIN_FAILED | IP: 198.51.100.12 (Russie) | User: root
[16:45:08] LOGIN_SUCCESS | IP: 198.51.100.12 (Russie) | User: admin
[16:45:15] FILE_DOWNLOAD | IP: 198.51.100.12 (Russie) | User: admin | File: /Shared/R&D/brevets-2026.zip
```

1. Décrivez l'attaque qui s'est déroulée en précisant sa chronologie.
2. Quel pilier de la triade CIA a été compromis en fin de séquence ?
3. Quelle action de confinement d'urgence devez-vous ordonner immédiatement au niveau du pare-feu ?

---

### Corrigé de l'exercice
1. **Description de l'attaque** :
   * Une adresse IP externe localisée en Russie a tenté de se connecter au serveur de fichiers en testant plusieurs identifiants d'administration courants (*admin*, *administrator*, *root*). Il s'agit d'une attaque par force brute ou par dictionnaire d'identifiants.
   * À 16:45:08, une tentative de connexion réussit sur le compte *admin* (mot de passe probablement trop simple ou par défaut).
   * À 16:45:15, l'attaquant télécharge un fichier de propriété intellectuelle très sensible (`brevets-2026.zip`).
2. **Pilier compromis : La Confidentialité**. Des données secrètes et stratégiques (brevets de l'entreprise) ont été divulguées à un tiers non autorisé.
3. **Action d'urgence** : Bloquer immédiatement tout trafic provenant de l'adresse IP `198.51.100.12` sur le pare-feu périphérique, réinitialiser immédiatement le mot de passe du compte *admin* sur le serveur de fichiers et suspendre temporairement sa session active pour stopper le vol de données en cours.

---


## Exercice Bonus (Temps additionnel)
**Si vous avez terminé en avance (avant les 1h30 de session) :**
- **Objectif :** Mise en pratique autonome.
- **Consignes :** Réfléchissez à un exemple réel ou une actualité récente liée au sujet de cette session. Discutez en groupe de la manière dont les concepts vus s'appliquent à cet exemple.
- **Correction :** Le mentor validera les réflexions et apportera son expertise.

## Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **SOC (Security Operations Center)** | Centre opérationnel où des analystes surveillent et analysent en continu la sécurité du système d'information pour détecter les incidents. |
| **SIEM (Security Information and Event Management)** | Logiciel centralisant les journaux d'événements (logs) de divers équipements réseau et serveurs pour y appliquer des règles de corrélation et lever des alertes en cas de comportement suspect. |
| **Log (Journal d'événements)** | Fichier texte généré automatiquement par un système, une application ou un équipement, enregistrant les actions, connexions et erreurs survenues chronologiquement. |
| **Faux Positif** | Une alerte de sécurité déclenchée à tort par un outil de surveillance face à une activité légitime (ex. un employé légitime qui se trompe de mot de passe trois fois). |
| **CVE (Common Vulnerabilities and Exposures)** | Dictionnaire public recensant et identifiant de manière unique les failles de sécurité logicielles et matérielles connues (ex. CVE-2021-44228). |
| **CVSS (Common Vulnerability Scoring System)** | Système de notation standardisé évaluant la gravité d'une vulnérabilité informatique sur une échelle de 0.0 (inoffensive) à 10.0 (critique). |
| **Patch (Correctif)** | Mise à jour logicielle publiée par un éditeur pour corriger des erreurs de programmation ou combler des failles de sécurité. |

## Ressources pour aller plus loin
* **IBM SkillsBuild** : Cours sur le fonctionnement d'un SIEM et le métier d'analyste SOC.
* **NIST** : Base de données nationale des vulnérabilités (NVD - National Vulnerability Database) pour rechercher des identifiants CVE.
* **FIRST.org** : Calculateur officiel des scores CVSS (pour comprendre l'impact des différentes variables de cotation).

* [ANSSI - Agence Nationale de la Sécurité des Systèmes d'Information](https://www.ssi.gouv.fr/)
* [Cybermalveillance.gouv.fr](https://www.cybermalveillance.gouv.fr/)
* [OWASP - Open Worldwide Application Security Project](https://owasp.org/)
