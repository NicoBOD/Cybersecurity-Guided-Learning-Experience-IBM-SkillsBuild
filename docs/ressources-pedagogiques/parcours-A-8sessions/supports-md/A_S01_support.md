# Support de cours — Session 01 : Découverte de la cybersécurité & paysage des menaces
Parcours : A 8 sessions  |  Module : Fondements Cyber  |  Niveau : Débutant

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - La Triade CIA : La boussole de la cybersécurité
    - Le triptyque : Vulnérabilité, Menace, Risque
    - Offense vs Défense : Deux facettes d'une même pièce
    - Qui sont les attaquants modernes ?
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

Bienvenue dans le monde de la cybersécurité. À l'ère numérique, la protection des informations est devenue une priorité absolue pour les individus, les entreprises et les gouvernements. Ce support pose les bases indispensables de la discipline. Vous y découvrirez la triade "CIA" (Confidentialité, Intégrité, Disponibilité), le modèle conceptuel de base pour évaluer la sécurité de tout système d'information. Nous étudierons également les différences fondamentales entre l'approche offensive (comprendre comment attaquent les pirates) et défensive (sécuriser les infrastructures), avant de cartographier les profils d'attaquants modernes et leurs motivations réelles, souvent bien éloignées des clichés du cinéma. Ce module constitue votre porte d'entrée vers une posture de vigilance active.

---

## 2. Développement

### Glossaire
* **Triade CIA (Confidentialité, Intégrité, Disponibilité)** : Le modèle de référence de la sécurité de l'information. Chaque action de sécurité vise à garantir l'un ou plusieurs de ces piliers.
* **Confidentialité** : Garantie que seules les personnes autorisées ont accès aux données.
* **Intégrité** : Garantie que les données ne sont pas modifiées, altérées ou supprimées de manière accidentelle ou malveillante.
* **Disponibilité** : Garantie que les données et les systèmes sont accessibles par les utilisateurs autorisés au moment où ils en ont besoin.
* **Vulnérabilité** : Une faiblesse ou une faille présente dans un système, un logiciel, une procédure ou un comportement humain, susceptible d'être exploitée.
* **Menace** : Un événement ou une entité externe ayant le potentiel d'exploiter une vulnérabilité et de causer des dommages.
* **Risque** : La probabilité qu'une menace exploite une vulnérabilité et provoque un impact négatif (Risque = Menace × Vulnérabilité × Impact).
* **Sécurité offensive** : Approche proactive consistant à tester les défenses en simulant des attaques réelles (ex. pentesting, red teaming).
* **Sécurité défensive** : Ensemble des mesures de protection, de surveillance et de réaction déployées pour sécuriser un système (ex. gestion des pare-feux, surveillance SOC, réponse sur incident).

---

### 1. La Triade CIA : La boussole de la cybersécurité

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.


Toute stratégie de cybersécurité s'appuie sur trois piliers fondamentaux. Comprendre ces concepts permet de classifier les incidents et de concevoir des mesures de protection appropriées.

#### A. Confidentialité (*Confidentiality*)
La confidentialité consiste à s'assurer que l'information n'est divulguée qu'aux personnes ou processus autorisés. Si un pirate accède à votre boîte de messagerie ou si un employé consulte le dossier médical d'un patient sans autorisation, la confidentialité est compromise.

* *Mécanismes de protection* : Le chiffrement des données (rendre la lecture impossible sans clé de déchiffrement), les contrôles d'accès logiques (mots de passe, biométrie) et la classification des informations.

#### B. Intégrité (*Integrity*)
L'intégrité garantit que l'information reste fiable, exacte et complète. Si un pirate intercepte un virement bancaire et remplace le RIB du destinataire par le sien, ou si un virus altère le code d'un logiciel médical pour fausser les doses administrées, c'est l'intégrité qui est impactée.

* *Mécanismes de protection* : Les signatures numériques, les fonctions de hachage (empreintes numériques uniques permettant de vérifier qu'un fichier n'a pas été modifié) et les historiques d'audit non modifiables.

#### C. Disponibilité (*Availability*)
La disponibilité assure que les systèmes informatiques, les réseaux et les données sont accessibles en temps voulu par les utilisateurs autorisés. Si une attaque par déni de service (DoS) sature le site e-commerce d'une enseigne commerciale durant les soldes, ou si un rançongiciel (ransomware) bloque l'accès aux ordinateurs d'une clinique, la disponibilité est rompue.

* *Mécanismes de protection* : La redondance des infrastructures (serveurs de secours), les sauvegardes régulières, et la maintenance préventive du matériel.



### 2. Le triptyque : Vulnérabilité, Menace, Risque

En sécurité, ces trois termes ont des sens bien distincts qu'il convient de ne pas confondre :

* La **vulnérabilité** est la porte ouverte (ex. un logiciel non mis à jour ou un mot de passe trop simple).
* La **menace** est le cambrioleur (ex. un groupe de cybercriminels qui cherche à voler des données).
* Le **risque** est la probabilité que le cambrioleur trouve la porte ouverte et s'introduise dans la maison pour dérober des biens (l'impact).

Sécuriser un système consiste à réduire les vulnérabilités pour minimiser la probabilité de réalisation du risque.



### 3. Offense vs Défense : Deux facettes d'une même pièce

* **La Sécurité Offensive (Offense)** cherche à penser comme l'attaquant. Elle utilise des méthodes de tests d'intrusion pour découvrir les failles avant qu'elles ne soient exploitées par des cybercriminels. Elle est indispensable pour valider la robustesse réelle des systèmes.
* **La Sécurité Défensive (Défense)** englobe toutes les mesures passives et actives de protection. Elle installe les barrières (antivirus, pare-feux), surveille les accès en continu et met en œuvre les processus de réaction et de reconstruction. Elle représente le travail quotidien de sécurisation.



### 4. Qui sont les attaquants modernes ?

Le cliché de l'adolescent isolé piratant la NASA depuis sa chambre est obsolète. Aujourd'hui, les acteurs de menaces sont structurés :

1. **Les Cybercriminels** : Motivés par l'appât du gain financier (ransomware, vol de données bancaires, revente d'informations). Ils opèrent souvent en bandes organisées.
2. **Les États-Nations** : Motivés par l'espionnage industriel, l'influence géopolitique, la sabotage d'infrastructures critiques ou le vol d'informations stratégiques. Ils disposent de ressources financières et techniques quasi illimitées.
3. **Les Hacktivistes** : Motivés par des revendications idéologiques, politiques ou écologiques. Ils cherchent à défigurer des sites web (*defacement*) ou à bloquer l'accès à des services pour faire entendre leur voix.
4. **Les Menaces Internes** : Employés mécontents, collaborateurs négligents ou prestataires indélicats. Ils possèdent déjà des accès légitimes au réseau, ce qui les rend particulièrement difficiles à détecter.

---

### Focus pratique
Pour comprendre comment un attaquant initie ses recherches, on étudie la **surface d'exposition numérique**. Il s'agit de l'ensemble des points d'entrée d'une organisation qui sont visibles et accessibles depuis Internet.

| Élément de la surface d'exposition | Risque associé | Mesure d'hygiène de base |
| :--- | :--- | :--- |
| **Noms de domaine et serveurs DNS** | Usurpation de nom de domaine, redirection frauduleuse. | Verrouillage des registres, protocoles DNSSEC. |
| **Serveurs web & applications cloud** | Exploitation de failles logicielles non patchées. | Scans réguliers, application stricte des mises à jour. |
| **Ports de connexion ouverts (ex. RDP, SSH)** | Attaques par force brute sur les identifiants d'accès. | Limitation des accès par VPN, filtrage IP, MFA obligatoire. |
| **Employés sur les réseaux sociaux** | Collecte d'informations d'ingénierie sociale (phishing ciblé). | Sensibilisation aux données partagées publiquement. |

---

### Exercice d'application
**Titre** : Classification d'incidents cyber selon la triade CIA

### Énoncé
Lisez attentivement les trois situations fictives ci-dessous et déterminez pour chacune quel(s) pilier(s) de la triade CIA a/ont été compromis, en justifiant votre choix en une ou deux phrases.

1. **Cas n°1** : Le serveur contenant le site web d'un cabinet comptable subit une attaque par déni de service. Les clients ne peuvent plus accéder à leur espace client pour téléverser leurs documents fiscaux pendant 12 heures.
2. **Cas n°2** : Un pirate s'infiltre dans la base de données d'un laboratoire d'analyses et modifie les valeurs de glycémie de plusieurs dizaines de dossiers de patients sans les supprimer.
3. **Cas n°3** : Un employé envoie par e-mail un fichier Excel non chiffré contenant la liste complète des salaires et des adresses personnelles des salariés de l'entreprise à un destinataire externe par erreur de saisie d'adresse.



### Corrigé de l'exercice
1. **Cas n°1 : Disponibilité compromise**. Le système est temporairement hors service et inaccessible pour les utilisateurs légitimes. La confidentialité et l'intégrité n'ont en revanche pas été altérées car aucune donnée n'a été volée ni modifiée.
2. **Cas n°2 : Intégrité compromise**. Les données de santé ont été altérées à l'insu du laboratoire, faussant la fiabilité des informations. Cela pose un danger vital immédiat en raison du risque de mauvais diagnostic médical.
3. **Cas n°3 : Confidentialité compromise**. Des données personnelles et sensibles (salaires, adresses) ont été divulguées à un tiers non autorisé qui n'avait pas le droit d'y accéder.

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

* **IBM SkillsBuild** : Cours "Introduction to Cybersecurity" pour approfondir l'histoire et les fondamentaux.
* **ANSSI (ou agence cyber locale)** : Guide d'hygiène informatique (consulter la section sur la sensibilisation et les notions de base).
* **NIST SP 800-12** : Guide d'introduction à la sécurité de l'information pour comprendre le cycle de protection.

* [ANSSI - Agence Nationale de la Sécurité des Systèmes d'Information](https://www.ssi.gouv.fr/)
* [Cybermalveillance.gouv.fr](https://www.cybermalveillance.gouv.fr/)
* [OWASP - Open Worldwide Application Security Project](https://owasp.org/)

---

## 4. Exercice bonus

- **Objectif :** Mise en pratique autonome.
- **Consignes :** Réfléchissez à un exemple réel ou une actualité récente liée au sujet de cette session. Discutez en groupe de la manière dont les concepts vus s'appliquent à cet exemple.
- **Correction :** Le mentor validera les réflexions et apportera son expertise.

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Triade CIA (Confidentialité, Intégrité, Disponibilité)** | Le modèle de référence de la sécurité de l'information. Chaque action de sécurité vise à garantir l'un ou plusieurs de ces piliers. |
| **Confidentialité** | Garantie que seules les personnes autorisées ont accès aux données. |
| **Intégrité** | Garantie que les données ne sont pas modifiées, altérées ou supprimées de manière accidentelle ou malveillante. |
| **Disponibilité** | Garantie que les données et les systèmes sont accessibles par les utilisateurs autorisés au moment où ils en ont besoin. |
| **Vulnérabilité** | Une faiblesse ou une faille présente dans un système, un logiciel, une procédure ou un comportement humain, susceptible d'être exploitée. |
| **Menace** | Un événement ou une entité externe ayant le potentiel d'exploiter une vulnérabilité et de causer des dommages. |
| **Risque** | La probabilité qu'une menace exploite une vulnérabilité et provoque un impact négatif (Risque = Menace × Vulnérabilité × Impact). |
| **Sécurité offensive** | Approche proactive consistant à tester les défenses en simulant des attaques réelles (ex. pentesting, red teaming). |
| **Sécurité défensive** | Ensemble des mesures de protection, de surveillance et de réaction déployées pour sécuriser un système (ex. gestion des pare-feux, surveillance SOC, réponse sur incident). |
