# Session B11 — Sécurité du cloud

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Le Modèle de Responsabilité Partagée
    - Les risques majeurs liés aux mauvaises configurations cloud
    - Règles d'or de la gouvernance des accès Cloud
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   La sécurité dans le cloud est une **responsabilité partagée** : le fournisseur sécurise l'infrastructure physique (*sécurité du cloud*), le client sécurise ses configurations et données (*sécurité dans le cloud*).
*   En **IaaS**, le client gère le système d'exploitation et le réseau virtuel. En **SaaS**, le client ne gère que ses données et les droits d'accès de ses utilisateurs.
*   Les **mauvaises configurations** (comme les buckets de stockage S3 laissés publics ou l'écriture de clés d'API en dur dans le code) sont les principales sources d'incidents cyber dans le cloud.
*   L'administration d'infrastructures cloud requiert une isolation stricte du compte **Root**, le déploiement généralisé du **MFA** et l'application du moindre privilège via l'**IAM**.

---

## 2. Développement
Détaillez le modèle de responsabilité partagée du Cloud. En IaaS, le client gère tout depuis l'OS jusqu'à l'application. En PaaS, le fournisseur gère l'OS. En SaaS, le fournisseur gère tout, sauf la donnée et l'identité des utilisateurs. Discutez des erreurs de configuration courantes : buckets AWS S3 laissés publics accidentellement.

---

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Analyser le modèle de responsabilité partagée et attribuer les devoirs de sécurité entre le client et le fournisseur pour les services IaaS, PaaS et SaaS.
* Identifier les menaces et erreurs de configuration majeures propres au cloud public (buckets de stockage exposés, secrets codés en dur).
* Définir les bonnes pratiques de sécurité d'accès (IAM, MFA) pour la gouvernance des consoles d'administration cloud.

---

### Glossaire

*   **Bucket de stockage** — Conteneur logique de stockage d'objets (fichiers, images, sauvegardes) dans le cloud public.
*   **IaaS (Infrastructure as a Service)** — Modèle de cloud où le client loue des ressources matérielles virtualisées (serveurs, stockage, réseaux).
*   **IaaS (Infrastructure as a Service)** — Modèle cloud offrant un accès à des ressources matérielles brutes (serveurs virtuels, disques), le client gérant l'OS et le reste.
*   **PaaS (Platform as a Service)** — Modèle fournissant une plateforme complète d'exécution pour développer et héberger des applications sans gérer les OS.
*   **PaaS (Platform as a Service)** — Modèle cloud où le fournisseur gère le système d'exploitation et l'infrastructure, laissant le client gérer ses applications et codes.
*   **Responsabilité Partagée** — Principe fondamental délimitant les rôles de sécurité entre le fournisseur cloud (sécurité du cloud) et l'entreprise cliente (sécurité dans le cloud).
*   **SaaS (Software as a Service)** — Logiciel applicatif complet clé en main hébergé et administré directement par le fournisseur cloud.
*   **SaaS (Software as a Service)** — Modèle cloud où l'application complète est hébergée et gérée à 100% par le fournisseur (ex. Salesforce, Microsoft 365).

---

### Concepts clés

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

### 1. Le Modèle de Responsabilité Partagée
Contrairement à une infrastructure classique hébergée en local (on-premise) où l'entreprise gère tout, du câblage au logiciel, le cloud repose sur un partage des responsabilités de sécurité entre le **fournisseur de services cloud** (CSP — *Cloud Service Provider*) et le **client**.

*   **Sécurité DU cloud (Responsabilité du fournisseur)** : Concerne les infrastructures physiques (bâtiments sécurisés, serveurs physiques, alimentation électrique, réseaux de communication physiques) et la couche de virtualisation (l'hyperviseur).
*   **Sécurité DANS le cloud (Responsabilité du client)** : Concerne les données, le système d'exploitation de la machine virtuelle (dans le cas du IaaS), la configuration logique des réseaux (pare-feux cloud) et la gestion des accès et des identités (IAM).

*   *L'analogie de la colocation immobilière* :
    *   Le **propriétaire** (le fournisseur cloud) est responsable de l'intégrité de la toiture, de la solidité des murs et de la tuyauterie de l'immeuble.
    *   Le **locataire** (le client) est responsable de fermer sa porte à clé (configuration IAM), de ne pas laisser entrer de personnes suspectes, et d'assurer ses propres meubles et objets de valeur (ses données).

#### Application selon les types de services :
*   **IaaS (*Infrastructure as a Service*)** : Le fournisseur fournit uniquement le matériel virtuel. Le client doit configurer, sécuriser et mettre à jour le système d'exploitation (OS), le réseau logique et les applications.
*   **PaaS (*Platform as a Service*)** : Le fournisseur gère le matériel et le système d'exploitation. Le client est uniquement responsable du code de ses applications et de ses données.
*   **SaaS (*Software as a Service*)** : Le fournisseur gère l'ensemble de l'application (infrastructure, OS, code). Le client est uniquement responsable de la configuration des comptes d'accès de ses utilisateurs et de la classification des données qu'il y injecte.

### 2. Les risques majeurs liés aux mauvaises configurations cloud
Dans le cloud, les infrastructures sont gérées par logiciel (*Infrastructure as Code*). Une seule erreur de clic ou de ligne de code peut exposer instantanément l'entreprise à l'échelle mondiale.

*   **Les espaces de stockage (buckets) ouverts** : Configuration par erreur d'un bucket cloud (ex. AWS S3 ou Google Cloud Storage) en accès "Public" sans authentification, exposant des milliers de fichiers internes (factures, scans de pièces d'identité) à n'importe quel internaute ou moteur de recherche.
*   **Le vol de clés d'API et secrets codés en dur (*hardcoded*)** : Intégrer des clés de connexion d'administration cloud directement au milieu du code source des applications et publier ce code par mégarde sur des plateformes publiques comme GitHub. Les attaquants scannent en permanence ces plateformes et utilisent ces clés pour louer des serveurs de cryptomonnaie sous la facture de la victime.
*   **L'absence de MFA sur le compte administrateur global (Root)** : La compromission du mot de passe du compte racine d'une console cloud permet à un attaquant de détruire ou de rançonner l'ensemble des serveurs et sauvegardes de l'entreprise en quelques minutes.

### 3. Règles d'or de la gouvernance des accès Cloud
Pour sécuriser les consoles d'administration cloud, appliquez la politique du moindre privilège :

*   **Ne jamais utiliser le compte Root** (le compte de création du compte cloud) au quotidien. Ce compte doit être verrouillé dans un coffre-fort numérique avec un MFA matériel fort.
*   **Créer des comptes d'accès nominatifs** via le service IAM du fournisseur cloud pour chaque administrateur et imposer le **MFA obligatoire**.
*   **Utiliser le principe du moindre privilège** en attribuant des rôles spécifiques (ex. *Billing Administrator* pour la comptabilité, *Network Administrator* pour les réseaux) au lieu du rôle *Owner/Administrator* global.

---

### Activités / exercices
### Exercice 1 — La Matrice de responsabilité Cloud
**Objectif :** Maîtriser le modèle de responsabilité partagée en attribuant correctement les tâches de sécurité à l'acteur concerné (Client ou Fournisseur Cloud) selon le type d'architecture.

**Consignes :**
Pour les 6 tâches de sécurité listées ci-dessous, écrivez dans la colonne correspondante si la responsabilité incombe au **Client** ou au **Fournisseur** pour chacun des modèles (IaaS, PaaS, SaaS).

**Tableau à remplir :**

| N° | Tâche de Sécurité | Modèle IaaS | Modèle PaaS | Modèle SaaS |
|---|---|---|---|---|
| 1 | Sécurité physique du datacenter (caméras, alarmes, électricité) | ... | ... | ... |
| 2 | Application des correctifs de sécurité de l'OS invité (ex. Linux) | ... | ... | ... |
| 3 | Classification et protection des données sensibles | ... | ... | ... |
| 4 | Configuration du pare-feu applicatif web (WAF) | ... | ... | ... |
| 5 | Application des correctifs de sécurité de l'application (ex. Salesforce) | ... | ... | ... |
| 6 | Gestion du cycle de vie des identités et obligation du MFA | ... | ... | ... |

**Corrigé / Éléments de réponse :**

| N° | Tâche de Sécurité | Modèle IaaS | Modèle PaaS | Modèle SaaS | Justification |
|---|---|---|---|---|---|
| **1** | Sécurité physique | **Fournisseur** | **Fournisseur** | **Fournisseur** | Le fournisseur gère toujours la sécurité physique de ses datacenters. |
| **2** | Correctifs OS invité | **Client** | **Fournisseur** | **Fournisseur** | En IaaS, le client a la main sur l'OS, il doit donc le patcher lui-même. En PaaS et SaaS, l'OS est masqué et géré par le fournisseur. |
| **3** | Protection des données | **Client** | **Client** | **Client** | **La donnée appartient toujours au client**, c'est à lui de la classer et de la protéger, quel que soit le modèle. |
| **4** | Configuration WAF | **Client** | **Client** | **Fournisseur** | En IaaS/PaaS, le client développe/configure son application et son filtrage. En SaaS, le fournisseur protège l'application qu'il édite. |
| **5** | Correctifs applicatifs | **Client** | **Client** | **Fournisseur** | En SaaS, le logiciel est mis à jour directement par le fournisseur de service. |
| **6** | Identités & MFA | **Client** | **Client** | **Client** | C'est au client de gérer qui a le droit d'accéder à son espace cloud et d'activer le MFA. |

---

### Questions de réflexion
1. Si un pirate vole les accès d'un développeur et modifie le code source d'un site web hébergé en PaaS pour y ajouter une porte dérobée, le fournisseur de cloud est-il responsable de cet incident ? Justifiez votre réponse à l'aide de la matrice de responsabilité.
2. Pourquoi le cloud public augmente-t-il les risques liés aux erreurs humaines de configuration par rapport à un centre de données classique interne ?

**Corrigé / Éléments de réponse :**
1. Non. En PaaS, le fournisseur gère l'infrastructure, mais le client reste responsable de la sécurité de son application et de la gestion de ses accès (code source).
2. Le cloud permet de déployer des ressources en un clic à l'échelle mondiale ; une erreur de configuration (ex: un bucket S3 public) expose immédiatement les données à tout Internet.

---


### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez le modèle de responsabilité partagée dans le cloud comme la **location d'un appartement** :
    - **Le Propriétaire (Fournisseur Cloud - AWS/Azure/GCP)** est responsable des murs, de la solidité du toit, de la porte d'entrée de l'immeuble et des canalisations (sécurité physique et de l'infrastructure globale).
    - **Le Locataire (Votre entreprise)** est responsable d'installer une serrure robuste sur sa propre porte, de fermer les fenêtres en partant, et de décider qui a le droit d'entrer dans l'appartement (sécurité des données, des accès et des configurations).
    - Si vous laissez votre porte grande ouverte et que vous vous faites cambrioler, c'est de votre responsabilité, pas de celle du propriétaire de l'immeuble.

**Exemple d'application professionnelle :**
Une start-up stocke les factures de ses clients sur un service de stockage cloud (S3). Lors d'un audit de sécurité, le responsable s'aperçoit que les factures sont accessibles publiquement sans mot de passe suite à une erreur humaine de configuration. Il applique immédiatement le modèle de responsabilité partagée en modifiant la politique d'accès du bucket pour exiger une authentification forte (MFA) et active le chiffrement automatique des données au repos.


### Panorama des solutions du marché (Commerciales & Open-Source)

Pour surveiller la configuration de sécurité dans le Cloud (CSPM) et identifier les mauvaises configurations de ressources :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Wiz.io** : Leader de la sécurité cloud (CNAPP) qui analyse en profondeur et sans agent les ressources AWS, Azure et GCP pour cartographier les risques et vecteurs d'attaque.
    *   **Palo Alto Prisma Cloud** : Plateforme complète de protection cloud couvrant la conformité, la sécurité des conteneurs et les vulnérabilités de l'infrastructure-as-code (IaC).
    *   **Microsoft Defender for Cloud** : Outil CSPM/CWPP de référence pour surveiller la posture de sécurité des environnements hybrides et multi-cloud.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **Prowler** : Outil open-source de référence écrit en Python pour évaluer la sécurité d'AWS, d'Azure et de GCP par rapport aux meilleures pratiques CIS (Center for Internet Security).
    *   **Scout Suite** : Outil d'audit de sécurité multi-cloud open-source qui utilise les APIs des fournisseurs cloud pour présenter les risques dans un rapport HTML clair.
    *   **Checkov / Terrascan** : Analyseurs statiques open-source pour scanner le code d'infrastructure (Terraform, CloudFormation, Kubernetes) afin de détecter les failles avant le déploiement.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Cloud Security Fundamentals"* (durée estimée : 1h30).
*   **Recherche complémentaire** : Visiter le site de l'OWASP et rechercher le top 10 des vulnérabilités de sécurité spécifiques au Cloud (OWASP Cloud Security Top 10) pour en comprendre les menaces courantes.


---

* [ANSSI - Externalisation vers le Cloud](https://cyber.gouv.fr)
* [CNIL - Cloud Computing](https://www.cnil.fr/fr/cloud-computing)

## 4. Exercice bonus

- **Objectif :** Analyse d'une faille de configuration Cloud.
- **Consignes :**
    1. Étudiez le cas réel ou fictif d'une fuite de données causée par un "Bucket S3" (espace de stockage en ligne Amazon) laissé ouvert publiquement sur Internet.
    2. Identifiez qui est responsable de cette faille selon le modèle de responsabilité partagée (AWS ou le client ?). Justifiez votre réponse.
    3. Proposez deux mesures d'audit automatique à mettre en place pour détecter ces faiblesses avant qu'un attaquant ne les trouve.
- **Correction pour le mentor :** Le client est responsable à 100% de la mauvaise configuration d'accès aux données dans le cloud, tandis qu'Amazon fournit l'infrastructure physique sécurisée. Pour prévenir ce risque, les apprenants doivent proposer : l'activation d'outils d'audit de configuration (ex. AWS Security Hub ou des scanners comme Prowler) et la mise en place de politiques de restriction d'accès globales interdisant par défaut le partage public des conteneurs de stockage.

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Bucket de stockage** | Conteneur logique de stockage d'objets (fichiers, images, sauvegardes) dans le cloud public. |
| **IaaS (Infrastructure as a Service)** | Modèle de cloud où le client loue des ressources matérielles virtualisées (serveurs, stockage, réseaux). |
| **PaaS (Platform as a Service)** | Modèle fournissant une plateforme complète d'exécution pour développer et héberger des applications sans gérer les OS. |
| **Responsabilité Partagée** | Principe fondamental délimitant les rôles de sécurité entre le fournisseur cloud (sécurité du cloud) et l'entreprise cliente (sécurité dans le cloud). |
| **SaaS (Software as a Service)** | Logiciel applicatif complet clé en main hébergé et administré directement par le fournisseur cloud. |

