# Session B08 — Durcissement des systèmes & endpoints

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Le Principe du Moindre Privilège
    - Le Durcissement Système (Hardening)
    - Antivirus Traditionnel vs EDR
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Le **principe du moindre privilège** protège le système en limitant les droits des utilisateurs au strict nécessaire pour leurs tâches courantes.
*   Le **durcissement (hardening)** réduit la surface d'attaque en fermant les ports locaux, en désactivant les services superflus et en chiffrant les données au repos.
*   La gestion des correctifs de sécurité (*patching*) est l'arme la plus efficace contre l'exploitation des failles de sécurité publiques (CVE).
*   L'**EDR** surpasse l'antivirus classique en analysant en continu les comportements des processus pour contrer les attaques inconnues et automatiser la réaction.

---

## 2. Développement
Expliquez le principe de durcissement (Hardening). Prenez l'exemple du Center for Internet Security (CIS) Benchmarks : désactiver l'exécution automatique des clés USB, renommer le compte administrateur local, appliquer les principes du moindre privilège via les GPO (Group Policy Objects) sur Active Directory. Distinguez l'Antivirus classique de l'EDR (Endpoint Detection and Response) basé sur l'analyse comportementale.

---

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Appliquer le principe du moindre privilège sur un système d'exploitation Windows ou Linux pour restreindre la surface d'attaque.
* Établir et déployer une checklist méthodologique de durcissement (*hardening*) de serveur ou de poste de travail.
* Différencier les mécanismes de détection par signatures d'un antivirus traditionnel de la détection comportementale d'un EDR (*Endpoint Detection and Response*).
* Évaluer de manière critique une architecture réseau sécurisée à l'aide d'une grille d'évaluation par pairs (**Mini-projet 1**).

---

### Glossaire
*   **GPO (Group Policy Object)** — Outil de l'infrastructure Microsoft Active Directory permettant de configurer de manière centralisée les règles de sécurité d'un parc de machines Windows.
*   **Hardening (Durcissement)** — Processus de sécurisation d'un système d'exploitation par réduction de sa surface d'exposition et verrouillage de ses configurations.
*   **EDR (Endpoint Detection and Response)** — Solution de sécurité installée sur les terminaux surveillant les comportements pour détecter et bloquer les attaques sophistiquées en temps réel.
*   **UAC (User Account Control)** — Mécanisme de sécurité Windows demandant l'approbation de l'utilisateur pour accorder des privilèges d'administration temporaires à un programme.

---

### Concepts clés

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

### 1. Le Principe du Moindre Privilège
Le principe du moindre privilège (*Least Privilege*) stipule qu'un utilisateur, un programme ou un processus ne doit posséder que les droits d'accès strictement nécessaires à l'accomplissement de sa tâche, et rien de plus.

*   **En pratique** : Les utilisateurs ne doivent jamais travailler au quotidien avec un compte disposant de privilèges d'administration globaux (compte Administrateur sous Windows ou `root` sous Linux).
*   **Élévation de privilèges** : Pour les tâches d'administration ponctuelles, l'administrateur doit utiliser un mécanisme d'élévation temporaire des droits (comme le contrôle de compte d'utilisateur **UAC** sous Windows, ou la commande `sudo` sous Linux), nécessitant une re-saisie de mot de passe.
*   *Objectif de sécurité* : Limiter la portée d'une erreur de manipulation ou restreindre les droits qu'un pirate obtiendrait s'il parvenait à compromettre la session de l'utilisateur.

### 2. Le Durcissement Système (Hardening)
Par défaut, les systèmes d'exploitation (Windows, Linux, macOS) sont livrés configurés pour maximiser la compatibilité et la facilité d'utilisation, ce qui se fait souvent au détriment de la sécurité (nombreux services activés, ports ouverts, partages activés).
Le **durcissement** (*hardening*) désigne l'ensemble des configurations appliquées à un système pour réduire sa surface d'exposition aux attaques.

*   *L'analogie* : Une voiture neuve livrée par défaut avec toutes les vitres baissées, l'alarme désactivée et la boîte à gants déverrouillée. Le durcissement consiste à remonter les vitres, fermer les portes à clé, activer l'antidémarrage et fermer les coffres.

#### Les 5 étapes indispensables du durcissement :
1.  **Désactivation des services et protocoles inutiles** : Désactiver les services non requis pour le rôle du serveur (ex. désactiver le service d'impression sur un serveur de base de données). Supprimer les anciens protocoles réseau vulnérables comme SMBv1 ou Telnet.
2.  **Gestion rigoureuse des correctifs (*Patch Management*)** : Appliquer systématiquement les correctifs de sécurité du système d'exploitation et des applications tierces pour fermer les failles connues.
3.  **Configuration des politiques de sécurité locales** : Imposer une longueur minimale de mots de passe, limiter le nombre de tentatives de connexion échouées (verrouillage temporaire du compte) et désactiver les comptes par défaut (comme le compte "Invité").
4.  **Chiffrement des disques durs** : Activer le chiffrement au repos (BitLocker sur Windows, LUKS sur Linux) pour empêcher un attaquant ayant volé physiquement la machine d'accéder aux données en branchant le disque dur sur un autre ordinateur.
5.  **Pare-feu local actif** : Activer et configurer le pare-feu local de l'hôte (Windows Defender Firewall ou UFW/iptables sous Linux) pour bloquer les flux réseau entrants non autorisés directement au niveau du système d'exploitation.

### 3. Antivirus Traditionnel vs EDR
La protection des machines hôtes (*endpoints*) a fortement évolué pour faire face à la sophistication des malwares.

*   **L'Antivirus traditionnel** : Fonctionne principalement par **signatures**. Il calcule l'empreinte mathématique (hachage) d'un fichier suspect et la compare à une base de données mondiale de signatures de malwares connus.
    *   *Limite* : Il est inefficace face aux menaces inconnues (attaques Zero-Day) ou aux fichiers malveillants modifiés à la volée par les attaquants (malwares polymorphes).
*   **L'EDR (*Endpoint Detection and Response*)** : Il agit comme une boîte noire et un agent de surveillance intelligent sur la machine. Il surveille en continu les actions des processus, les modifications de fichiers et le comportement réseau.
    *   *Force* : Il détecte les anomalies comportementales. Si un fichier Word démarre discrètement un script PowerShell pour chiffrer des fichiers dans vos documents, l'EDR repère cette anomalie comportementale (inconnue en termes de signature), bloque le processus suspect et isole la machine du réseau local pour éviter la propagation.

---

### Activités / exercices
### Exercice 1 — Élaboration d'une checklist de durcissement système (Hardening)
**Objectif :** Rédiger des règles techniques concrètes d'application de sécurité pour durcir un poste de travail Windows 11 en entreprise.

**Consignes :**
L'entreprise "EcoLog" déploie 50 nouveaux ordinateurs portables Windows 11 pour ses salariés. Rédigez les 5 règles clés de configuration de sécurité que le service informatique doit intégrer dans sa politique de groupe (**GPO** — *Group Policy Object*) avant de remettre les postes aux employés. Complétez le tableau ci-dessous en justifiant le risque atténué pour chaque règle.

**Tableau à remplir :**

| N° | Règle de durcissement technique | Risque de sécurité mitigé (si non appliquée) |
|---|---|---|
| 1 | Désactiver les ports USB pour le stockage de masse externe | ... |
| 2 | Activer BitLocker avec authentification au démarrage | ... |
| 3 | Configurer le pare-feu Windows en mode restrictif | ... |
| 4 | Imposer le verrouillage automatique de session après 5 min d'inactivité | ... |
| 5 | Interdire le fonctionnement quotidien avec des privilèges administrateur | ... |

**Corrigé / Éléments de réponse :**

| N° | Règle de durcissement technique | Risque de sécurité mitigé (si non appliquée) |
|---|---|---|
| **1** | Désactiver les ports USB pour le stockage de masse externe | Atténue l'introduction accidentelle ou volontaire de malwares via des clés USB infectées, et évite la fuite de données confidentielles par copie physique non autorisée. |
| **2** | Activer BitLocker avec authentification au démarrage | Protège contre le vol physique de l'ordinateur portable. Sans BitLocker, un voleur pourrait démonter le disque dur et lire toutes les données en clair sur une autre machine sans connaître le mot de passe Windows. |
| **3** | Configurer le pare-feu Windows en mode restrictif | Bloque les connexions entrantes directes non sollicitées de pirates ou de vers se propageant sur le réseau local, notamment lorsque l'employé est connecté à un Wi-Fi public. |
| **4** | Imposer le verrouillage automatique de session après 5 min d'inactivité | Empêche une personne malveillante d'accéder aux données ou d'exécuter des commandes malveillantes sur le poste de l'employé si celui-ci s'éloigne de son bureau sans verrouiller manuellement sa session. |
| **5** | Interdire le fonctionnement quotidien avec des privilèges administrateur | Limite la portée d'une infection logicielle. Si l'utilisateur clique sur une pièce jointe piégée, le malware s'exécutera avec ses droits limités d'utilisateur standard, ce qui l'empêchera d'installer des programmes système persistants ou de modifier la configuration globale de l'OS. |

---

### Questions de réflexion
1. Si une entreprise déploie des EDR de dernière génération sur tous ses postes, peut-elle se dispenser d'appliquer les mises à jour de sécurité de son système d'exploitation ? Pourquoi la défense en profondeur reste-t-elle indispensable ?
2. Quelle est la différence fondamentale entre le rôle d'un administrateur système qui fait du "durcissement" et un analyste SOC qui surveille les alertes EDR ? Comment ces deux activités se complètent-elles ?

**Corrigé / Éléments de réponse :**
1. L'EDR détecte les comportements malveillants, mais si la faille n'est pas patchée, la vulnérabilité reste ouverte et l'attaquant pourrait désactiver l'EDR ou trouver un moyen de contournement.
2. L'administrateur prévient (réduction de la surface d'attaque), le SOC détecte et réagit aux menaces résiduelles.

---


### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Pour bien comprendre ces concepts techniques, imaginez l'analogie suivante : la cybersécurité de votre entreprise est comme la sécurité d'une maison physique.
    - **Le Pare-feu (Firewall)** agit comme la porte d'entrée blindée : il filtre qui entre et qui sort.
    - **L'Antivirus / EDR** est comme le système d'alarme intérieur : s'il détecte un mouvement suspect, il bloque l'intrus.
    - **La Politique de mots de passe et le MFA** correspondent aux serrures multipoints et au digicode : posséder la clé ne suffit pas toujours, il faut aussi connaître le code secret.

**Exemple d'application professionnelle :**
Dans une PME, un attaquant tentera rarement de forcer les serveurs directement. Il enverra un e-mail frauduleux (Phishing) à un employé des ressources humaines. Si l'employé clique, le logiciel malveillant tente de s'installer. C'est ici que la *défense en profondeur* intervient : le filtre anti-spam aurait dû bloquer l'e-mail, l'antivirus aurait dû bloquer l'exécution, et l'absence de droits administrateurs de l'employé aurait empêché l'installation. Chaque couche est vitale.


## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"System Hardening and Patch Management"* (durée estimée : 1h30).
*   **Ressource complémentaire** : Visiter le site de l'ANSSI (cyber.gouv.fr) et consulter le "Guide de configuration d'un système Windows" ou les recommandations de durcissement Linux pour observer le niveau d'exigence technique requis en milieu professionnel.


---

* [ANSSI - Déploiement client Windows](https://cyber.gouv.fr)
* [Cybermalveillance - Mises à jour](https://www.cybermalveillance.gouv.fr/tous-nos-contenus/bonnes-pratiques/mises-a-jour)

## 4. Exercice bonus

- **Objectif :** Mise en pratique autonome.
- **Consignes :** Réfléchissez à un exemple réel ou une actualité récente liée au sujet de cette session. Discutez en groupe de la manière dont les concepts vus s'appliquent à cet exemple.
- **Correction :** Le mentor validera les réflexions et apportera son expertise.

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **GPO (Group Policy Object)** | Outil de l'infrastructure Microsoft Active Directory permettant de configurer de manière centralisée les règles de sécurité d'un parc de machines Windows. |
| **Hardening (Durcissement)** | Processus de sécurisation d'un système d'exploitation par réduction de sa surface d'exposition et verrouillage de ses configurations. |
| **EDR (Endpoint Detection and Response)** | Solution de sécurité installée sur les terminaux surveillant les comportements pour détecter et bloquer les attaques sophistiquées en temps réel. |
| **UAC (User Account Control)** | Mécanisme de sécurité Windows demandant l'approbation de l'utilisateur pour accorder des privilèges d'administration temporaires à un programme. |
