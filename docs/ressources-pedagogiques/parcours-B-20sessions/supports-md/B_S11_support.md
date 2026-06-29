# Session B11 — Sécurité du cloud

## Objectifs de la session
À la fin de cette session, vous serez capable de :

* Analyser le modèle de responsabilité partagée et attribuer les devoirs de sécurité entre le client et le fournisseur pour les services IaaS, PaaS et SaaS.
* Identifier les menaces et erreurs de configuration majeures propres au cloud public (buckets de stockage exposés, secrets codés en dur).
* Définir les bonnes pratiques de sécurité d'accès (IAM, MFA) pour la gouvernance des consoles d'administration cloud.

---

## Concepts clés

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

## Activités / exercices

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

## Questions de réflexion
1. Si un pirate vole les accès d'un développeur et modifie le code source d'un site web hébergé en PaaS pour y ajouter une porte dérobée, le fournisseur de cloud est-il responsable de cet incident ? Justifiez votre réponse à l'aide de la matrice de responsabilité.
2. Pourquoi le cloud public augmente-t-il les risques liés aux erreurs humaines de configuration par rapport à un centre de données classique interne ?

---

## Résumé / points à retenir
*   La sécurité dans le cloud est une **responsabilité partagée** : le fournisseur sécurise l'infrastructure physique (*sécurité du cloud*), le client sécurise ses configurations et données (*sécurité dans le cloud*).
*   En **IaaS**, le client gère le système d'exploitation et le réseau virtuel. En **SaaS**, le client ne gère que ses données et les droits d'accès de ses utilisateurs.
*   Les **mauvaises configurations** (comme les buckets de stockage S3 laissés publics ou l'écriture de clés d'API en dur dans le code) sont les principales sources d'incidents cyber dans le cloud.
*   L'administration d'infrastructures cloud requiert une isolation stricte du compte **Root**, le déploiement généralisé du **MFA** et l'application du moindre privilège via l'**IAM**.

---

## Glossaire de la session
*   **IaaS (Infrastructure as a Service)** — Modèle de cloud où le client loue des ressources matérielles virtualisées (serveurs, stockage, réseaux).
*   **PaaS (Platform as a Service)** — Modèle fournissant une plateforme complète d'exécution pour développer et héberger des applications sans gérer les OS.
*   **SaaS (Software as a Service)** — Logiciel applicatif complet clé en main hébergé et administré directement par le fournisseur cloud.
*   **Bucket de stockage** — Conteneur logique de stockage d'objets (fichiers, images, sauvegardes) dans le cloud public.

---

## Pour aller plus loin (self-paced)
*   **Sur IBM SkillsBuild** : Suivre le cours *"Cloud Security Fundamentals"* (durée estimée : 1h30).
*   **Recherche complémentaire** : Visiter le site de l'OWASP et rechercher le top 10 des vulnérabilités de sécurité spécifiques au Cloud (OWASP Cloud Security Top 10) pour en comprendre les menaces courantes.
