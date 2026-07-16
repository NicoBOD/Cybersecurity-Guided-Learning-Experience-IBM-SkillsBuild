# Session B11 — Sécurité du cloud
Parcours : B 20 sessions  |  Module : C — Identités, cloud & données  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Le Modèle de Responsabilité Partagée
    - Les risques majeurs liés aux mauvaises configurations cloud
    - Règles d'or de la gouvernance des accès Cloud
    - Deux affaires réelles : Capital One (2019), la configuration qui a exposé 106 millions de dossiers, et Verizon (2017), le bucket public
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   La sécurité dans le cloud est une **responsabilité partagée** : le fournisseur sécurise l'infrastructure physique (*sécurité du cloud*), le client sécurise ses configurations et données (*sécurité dans le cloud*).
*   En **IaaS**, le client gère le système d'exploitation et le réseau virtuel. En **SaaS**, le client ne gère que ses données et les droits d'accès de ses utilisateurs.
*   Les **mauvaises configurations** (comme les buckets de stockage laissés publics ou l'écriture de clés d'API en dur dans le code) sont les principales sources d'incidents cyber dans le cloud.
*   L'administration d'infrastructures cloud requiert une isolation stricte du compte **Root**, le déploiement généralisé du **MFA** et l'application du moindre privilège via l'**IAM** (vue en B09).

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Analyser le modèle de responsabilité partagée et attribuer les devoirs de sécurité entre le client et le fournisseur pour les services IaaS, PaaS et SaaS.
* Identifier les menaces et erreurs de configuration majeures propres au cloud public (buckets de stockage exposés, secrets codés en dur).
* Définir les bonnes pratiques de sécurité d'accès (IAM, MFA) pour la gouvernance des consoles d'administration cloud.

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** Selon le cabinet d'analyse Gartner, quelle part des incidents de sécurité dans le cloud est imputable au CLIENT — et non au fournisseur (AWS, Azure, Google Cloud) ?

    - A) Environ la moitié
    - B) La quasi-totalité (de l'ordre de 99 %) ✅
    - C) Une minorité (~10 %) : les fournisseurs sont souvent en cause

    **Débrief mentor :** Réponse B : selon la célèbre prédiction de Gartner, la quasi-totalité des défaillances de sécurité cloud sont — et resteront — la faute du client, pas du fournisseur. Les datacenters d'AWS ou de Microsoft sont des forteresses ; ce qui fuit, ce sont les **configurations** : le bucket laissé public, la clé d'API dans le code, le compte sans MFA. Autrement dit : le cloud ne vous décharge PAS de la sécurité — il en redistribue les rôles. Comprendre cette frontière, c'est tout l'objet de ce soir.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. La frontière fine du modèle par service**
Détaillez la gradation avec des exemples nommés : en **IaaS** (AWS EC2, Azure VM), le client patche l'OS invité, configure le réseau logique et le chiffrement ; en **PaaS** (Heroku, Azure App Service), le fournisseur gère l'OS mais le client répond de son code et de ses dépendances ; en **SaaS** (Microsoft 365, Salesforce), il ne reste au client « que » les données, les identités et les configurations de partage — et c'est déjà énorme : la plupart des fuites SaaS viennent de partages trop larges et de comptes sans MFA. Point souvent ignoré : la **sauvegarde des données SaaS** reste à la charge du client (supprimer ≠ sauvegarder).

**2. Anatomie de l'affaire Capital One (pour aller plus loin que le récit)**
Pour les questions techniques : l'attaquante a exploité un pare-feu applicatif (WAF) **mal configuré** pour faire exécuter au serveur des requêtes vers l'intérieur (technique dite **SSRF** — *Server-Side Request Forgery*), atteignant le **service de métadonnées** de l'instance cloud, qui distribue des identifiants temporaires. Ces identifiants portaient des droits **excessifs** (bien au-delà du besoin du WAF) sur le stockage. Trois leçons techniques : le moindre privilège s'applique aussi aux **machines** (pas qu'aux humains — rappel de la matrice B09) ; les services de métadonnées se protègent (versions durcies existent) ; et la surveillance des accès au stockage aurait détecté l'exfiltration.

**3. Les secrets dans le code : un fléau industrialisé**
Expliquez l'écosystème : des robots scannent en continu les plateformes publiques (GitHub notamment) à la recherche de clés d'API, mots de passe et jetons — une clé exposée est typiquement exploitée en **quelques minutes**. Usage favori : miner de la cryptomonnaie sur le compte de la victime (facture astronomique) ou pivoter vers les données. Parades : gestionnaires de secrets (le Vault de B10), scan automatique des dépôts avant publication, rotation des clés — et surtout : révoquer AVANT de nettoyer, car l'historique Git n'oublie rien.

---

### Glossaire

*   **Bucket de stockage** — Conteneur logique de stockage d'objets (fichiers, images, sauvegardes) dans le cloud public.
*   **CSPM (Cloud Security Posture Management)** — Famille d'outils analysant en continu les configurations cloud pour détecter les dérives (bucket public, MFA absent, droits excessifs).
*   **IaaS (Infrastructure as a Service)** — Modèle de cloud où le client loue des ressources matérielles virtualisées (serveurs, stockage, réseaux) et gère l'OS et tout ce qui est au-dessus.
*   **PaaS (Platform as a Service)** — Modèle fournissant une plateforme complète d'exécution pour développer et héberger des applications sans gérer les systèmes d'exploitation.
*   **Responsabilité Partagée** — Principe fondamental délimitant les rôles de sécurité entre le fournisseur cloud (sécurité DU cloud) et l'entreprise cliente (sécurité DANS le cloud).
*   **Root (compte racine)** — Compte de création d'un environnement cloud, aux pouvoirs illimités — à isoler, protéger par MFA matériel et ne jamais utiliser au quotidien.
*   **SaaS (Software as a Service)** — Logiciel applicatif complet clé en main hébergé et administré directement par le fournisseur cloud (ex. Microsoft 365, Salesforce).
*   **Secret codé en dur (hardcoded)** — Clé d'API, mot de passe ou jeton inscrit directement dans le code source — exposé à la moindre publication du code.
*   **SSRF (Server-Side Request Forgery)** — Attaque consistant à faire émettre par un serveur des requêtes vers des ressources internes auxquelles l'attaquant n'a pas accès directement.

---

### Concepts clés

!!! info "À retenir"
    Dans le cloud, le fournisseur vous loue des murs blindés — mais c'est VOUS qui fermez (ou non) la porte. La donnée, les identités et les configurations restent TOUJOURS la responsabilité du client, quel que soit le modèle : la quasi-totalité des incidents cloud sont des portes laissées ouvertes, pas des murs percés.

### 1. Le Modèle de Responsabilité Partagée
Contrairement à une infrastructure classique hébergée en local (on-premise) où l'entreprise gère tout, du câblage au logiciel, le cloud repose sur un partage des responsabilités de sécurité entre le **fournisseur de services cloud** (CSP — *Cloud Service Provider*) et le **client**.

*   **Sécurité DU cloud (Responsabilité du fournisseur)** : Concerne les infrastructures physiques (bâtiments sécurisés, serveurs physiques, alimentation électrique, réseaux de communication physiques) et la couche de virtualisation (l'hyperviseur).
*   **Sécurité DANS le cloud (Responsabilité du client)** : Concerne les données, le système d'exploitation de la machine virtuelle (dans le cas du IaaS), la configuration logique des réseaux (pare-feux cloud) et la gestion des accès et des identités (IAM).

*   *L'analogie de la colocation immobilière* :
    *   Le **propriétaire** (le fournisseur cloud) est responsable de l'intégrité de la toiture, de la solidité des murs et de la tuyauterie de l'immeuble.
    *   Le **locataire** (le client) est responsable de fermer sa porte à clé (configuration IAM), de ne pas laisser entrer de personnes suspectes, et d'assurer ses propres meubles et objets de valeur (ses données).

#### Application selon les types de services :
*   **IaaS (*Infrastructure as a Service*)** : Le fournisseur fournit uniquement le matériel virtuel. Le client doit configurer, sécuriser et mettre à jour le système d'exploitation (OS), le réseau logique et les applications. *Exemples : AWS EC2, Azure VM.*
*   **PaaS (*Platform as a Service*)** : Le fournisseur gère le matériel et le système d'exploitation. Le client est uniquement responsable du code de ses applications et de ses données. *Exemples : Heroku, Azure App Service.*
*   **SaaS (*Software as a Service*)** : Le fournisseur gère l'ensemble de l'application (infrastructure, OS, code). Le client est uniquement responsable de la configuration des comptes d'accès de ses utilisateurs et de la classification des données qu'il y injecte. *Exemples : Microsoft 365, Salesforce.*

> 💡 **Bon à savoir : « uniquement les données », c'est déjà énorme**
> Même en SaaS, il reste au client : les identités et le MFA, les règles de partage (qui voit quoi), la classification des données... et la **sauvegarde** — supprimer un fichier dans un outil SaaS n'est pas le sauvegarder, et le fournisseur ne restaure pas vos suppressions accidentelles au-delà de ses corbeilles. La plupart des fuites SaaS viennent de partages trop larges, pas de piratages.

### 2. Les risques majeurs liés aux mauvaises configurations cloud
Dans le cloud, les infrastructures sont gérées par logiciel (*Infrastructure as Code*). Une seule erreur de clic ou de ligne de code peut exposer instantanément l'entreprise à l'échelle mondiale.

*   **Les espaces de stockage (buckets) ouverts** : Configuration par erreur d'un bucket cloud (ex. AWS S3 ou Google Cloud Storage) en accès "Public" sans authentification, exposant des milliers de fichiers internes (factures, scans de pièces d'identité) à n'importe quel internaute ou moteur de recherche.
*   **Le vol de clés d'API et secrets codés en dur (*hardcoded*)** : Intégrer des clés de connexion d'administration cloud directement au milieu du code source des applications et publier ce code par mégarde sur des plateformes publiques comme GitHub. Les attaquants scannent en permanence ces plateformes — une clé exposée est typiquement exploitée en quelques minutes, souvent pour miner de la cryptomonnaie sur la facture de la victime. (Souvenez-vous d'Uber en B09 : le script aux identifiants codés en dur.)
*   **L'absence de MFA sur le compte administrateur global (Root)** : La compromission du mot de passe du compte racine d'une console cloud permet à un attaquant de détruire ou de rançonner l'ensemble des serveurs et sauvegardes de l'entreprise en quelques minutes.

### 3. Règles d'or de la gouvernance des accès Cloud
Pour sécuriser les consoles d'administration cloud, appliquez la politique du moindre privilège :

*   **Ne jamais utiliser le compte Root** (le compte de création du compte cloud) au quotidien. Ce compte doit être verrouillé dans un coffre-fort numérique avec un MFA matériel fort.
*   **Créer des comptes d'accès nominatifs** via le service IAM du fournisseur cloud pour chaque administrateur et imposer le **MFA obligatoire**.
*   **Utiliser le principe du moindre privilège** en attribuant des rôles spécifiques (ex. *Billing Administrator* pour la comptabilité, *Network Administrator* pour les réseaux) au lieu du rôle *Owner/Administrator* global — et l'appliquer aussi aux **machines et services** : un pare-feu applicatif n'a aucun besoin de lire tout le stockage (l'affaire Capital One en est la démonstration).
*   **Surveiller en continu** : les outils de CSPM détectent les dérives de configuration (bucket devenu public, MFA désactivé, droits excessifs) avant les attaquants.

### Activité — La matrice de responsabilité (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Affichez la matrice vide (6 tâches × 3 modèles). Trois lignes clés sont votées ; les autres sont remplies collectivement au débrief. Pour chaque tâche : qui est responsable en IaaS, PaaS, SaaS — le Client ou le Fournisseur ?

*   **📊 Sondage n°2 — Les correctifs de l'OS invité (ex. Linux de la machine virtuelle) :** Qui les applique ?
    *   A) IaaS : le Client · PaaS : le Fournisseur · SaaS : le Fournisseur ✅
    *   B) Le Client, dans les trois modèles
    *   C) Le Fournisseur, dans les trois modèles
*   **📊 Sondage n°3 — La classification et la protection des données sensibles :** Qui en répond ?
    *   A) Le Fournisseur, dès qu'on est en SaaS
    *   B) Le Client, TOUJOURS, quel que soit le modèle ✅
    *   C) Personne : les données sont protégées par défaut dans le cloud
*   **📊 Sondage n°4 — La configuration du pare-feu applicatif web (WAF) :** Qui s'en charge ?
    *   A) Le Fournisseur, dans les trois modèles
    *   B) Le Client, dans les trois modèles
    *   C) IaaS et PaaS : le Client · SaaS : le Fournisseur ✅

**Éléments de débriefing (pour le mentor) :**

- N°2 : le critère est « qui a la main sur la couche ? » — en IaaS, le client voit et gère l'OS, donc il le patche (et WannaCry, B03, a montré le prix de l'oubli) ; en PaaS/SaaS, l'OS est masqué.
- N°3 : LA ligne à retenir de toute la session — **la donnée appartient toujours au client**. Le fournisseur héberge, le client répond du contenu, de sa classification, de son partage... et de sa sauvegarde.
- N°4 : en IaaS/PaaS, l'application est celle du client — son filtrage aussi ; en SaaS, le fournisseur protège le logiciel qu'il édite. Et un WAF mal configuré côté client... c'est l'affaire Capital One qui arrive.
- **Compléter la matrice à l'écran** avec les trois lignes restantes : sécurité physique (Fournisseur ×3), correctifs applicatifs (Client en IaaS/PaaS, Fournisseur en SaaS), identités & MFA (**Client ×3** — l'autre ligne invariante, rappel B09).

**Matrice complète (corrigé de référence) :**

| N° | Tâche de Sécurité | Modèle IaaS | Modèle PaaS | Modèle SaaS | Justification |
|---|---|---|---|---|---|
| **1** | Sécurité physique | **Fournisseur** | **Fournisseur** | **Fournisseur** | Le fournisseur gère toujours la sécurité physique de ses datacenters. |
| **2** | Correctifs OS invité | **Client** | **Fournisseur** | **Fournisseur** | En IaaS, le client a la main sur l'OS, il doit donc le patcher lui-même. En PaaS et SaaS, l'OS est masqué et géré par le fournisseur. |
| **3** | Protection des données | **Client** | **Client** | **Client** | **La donnée appartient toujours au client**, c'est à lui de la classer et de la protéger, quel que soit le modèle. |
| **4** | Configuration WAF | **Client** | **Client** | **Fournisseur** | En IaaS/PaaS, le client développe/configure son application et son filtrage. En SaaS, le fournisseur protège l'application qu'il édite. |
| **5** | Correctifs applicatifs | **Client** | **Client** | **Fournisseur** | En SaaS, le logiciel est mis à jour directement par le fournisseur de service. |
| **6** | Identités & MFA | **Client** | **Client** | **Client** | C'est au client de gérer qui a le droit d'accéder à son espace cloud et d'activer le MFA. |

### 4. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **La quasi-totalité (~99 %)** des défaillances de sécurité cloud sont imputables au client, non au fournisseur (prédiction publiée en 2019 par le cabinet Gartner, devenue référence du secteur).
    - **Environ 106 millions de dossiers clients** exposés dans l'affaire Capital One (2019) — 80 M$ d'amende du régulateur bancaire américain (2020) et 190 M$ d'accord d'indemnisation.
    - **Environ 14 millions de dossiers clients Verizon** exposés en 2017 par un simple bucket de stockage configuré en accès public chez un prestataire (découverte du cabinet UpGuard).

**Comment lire ces chiffres ?** (1) Le maillon faible du cloud n'est pas la technologie du fournisseur : c'est la configuration du client. (2) Une seule erreur de configuration s'expose au monde entier, instantanément — c'est la différence avec le datacenter interne. (3) Le régulateur ne poursuit pas AWS : il poursuit le client — la responsabilité juridique suit la responsabilité de configuration.

### 5. Deux affaires réelles : le pare-feu trop bavard et le bucket grand ouvert

#### Cas n°1 — Capital One (2019) : 106 millions de dossiers derrière une configuration

Juillet 2019. La banque américaine **Capital One** — pionnière revendiquée du cloud — découvre qu'une attaquante a téléchargé les données d'environ **106 millions** de demandes de crédit (États-Unis et Canada), dont des numéros de sécurité sociale et de comptes bancaires. Le mode opératoire tient en trois maillons, tous côté client : un **pare-feu applicatif mal configuré**, que l'attaquante détourne pour faire émettre au serveur des requêtes internes (technique **SSRF**) ; le **service de métadonnées** de l'instance cloud, qui lui remet des identifiants temporaires ; et des identifiants aux **droits excessifs** — ce pare-feu pouvait lire des centaines d'espaces de stockage qu'il n'avait aucune raison de voir. L'attaquante — une ancienne ingénieure du fournisseur cloud — s'en vante en ligne, ce qui la fera arrêter. Bilan : 80 M$ d'amende du régulateur bancaire, 190 M$ d'indemnisation.

**Ce que ce cas illustre :** le fournisseur n'a pas été piraté — chaque maillon défaillant relevait du client (la matrice de responsabilité en action) ; le **moindre privilège s'applique aussi aux machines** : un composant n'a pas à voir au-delà de son besoin (rappel de l'Admin_IT de B09) ; et la surveillance des accès au stockage aurait vu l'exfiltration — la configuration se surveille en continu (CSPM), pas une fois par an.

#### Cas n°2 — Verizon (2017) : 14 millions de dossiers dans un bucket public

Été 2017. Un chercheur du cabinet **UpGuard** découvre, librement accessible sur Internet, un bucket de stockage cloud contenant les dossiers d'environ **14 millions de clients** de l'opérateur américain Verizon : noms, numéros, et pour certains les codes PIN de leurs comptes. Aucun piratage : le bucket, géré par un **prestataire** de Verizon, était simplement configuré en accès public. Des robots parcourent en permanence l'espace d'adressage des services de stockage cloud à la recherche exacte de ce type d'oubli — le chercheur est arrivé avant les attaquants... cette fois.

**Ce que ce cas illustre :** le bucket public est LA fuite cloud archétypale — une case cochée au mauvais endroit, et l'exposition est mondiale et silencieuse ; la chaîne de sous-traitance transporte la responsabilité (le prestataire configure, le donneur d'ordre assume — Target, encore) ; et la détection ne doit rien au hasard : des outils (CSPM) repèrent ces expositions en continu, exactement comme le font les scanners des attaquants.

!!! tip "📊 Sondage Livestorm n°5 — Et chez vous ? (sondage d'opinion, pas de bonne réponse)"
    **Question :** Votre organisation utilise le cloud (Microsoft 365, Google Workspace, AWS...). La frontière de responsabilité fournisseur/client y est-elle claire pour vous ?

    - A) Oui : les rôles sont posés, documentés, et la configuration est surveillée
    - B) On utilise le cloud, mais la frontière est floue — « c'est le fournisseur qui gère », pense-t-on
    - C) Je ne sais pas / Nous n'utilisons pas (encore) le cloud

    **Débrief mentor :** Sondage d'opinion — B est la réponse la plus répandue, et la plus dangereuse : « c'est le fournisseur qui gère » est vrai pour les murs, faux pour les portes. Question à poser lundi matin : qui, chez nous, vérifie les règles de partage, le MFA et les configurations de stockage ? Si la réponse est « personne », vous venez d'identifier votre premier chantier — l'Atelier de Synthèse de la semaine prochaine (B12) vous y aidera.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Un développeur de MedDistri vous prévient, paniqué : il vient de publier par erreur sur un dépôt GitHub **public** du code contenant la clé d'API d'administration du compte cloud. **Tapez A, B ou C dans le chat :**

    - A) Supprimer le dépôt au plus vite : la clé disparaîtra avec lui.
    - B) Révoquer immédiatement la clé, puis auditer l'activité du compte cloud — et seulement ensuite nettoyer le dépôt. ✅
    - C) Repasser le dépôt en privé : plus personne ne pourra le lire.

    **Débrief mentor :** B — l'ordre est vital : des robots scannent GitHub en continu, une clé exposée est typiquement exploitée en **minutes** ; il faut donc considérer la clé comme déjà volée : révoquer d'abord, auditer ensuite (des serveurs de minage tournent peut-être déjà sur votre facture). A et C partagent la même illusion : l'historique Git conserve tout, et des copies ont pu être faites dès la publication. Féliciter le développeur d'avoir alerté vite (culture du signalement, B04) — et prévenir la récidive : gestionnaire de secrets (B10) + scan automatique des dépôts.

---

### Questions de réflexion
1. Si un pirate vole les accès d'un développeur et modifie le code source d'un site web hébergé en PaaS pour y ajouter une porte dérobée, le fournisseur de cloud est-il responsable de cet incident ? Justifiez votre réponse à l'aide de la matrice de responsabilité.
2. Pourquoi le cloud public augmente-t-il les risques liés aux erreurs humaines de configuration par rapport à un centre de données classique interne ?
3. Dans l'affaire Capital One, le pare-feu applicatif disposait de droits de lecture sur des centaines d'espaces de stockage. Reformulez le problème avec le vocabulaire de B09 (moindre privilège, RBAC) — et proposez la parade.

**Corrigé / Éléments de réponse :**

1. Non. En PaaS, le fournisseur gère l'infrastructure, mais le client reste responsable de la sécurité de son application, de son code source et de la gestion de ses accès (identités des développeurs — MFA, moindre privilège).
2. Le cloud permet de déployer des ressources en un clic à l'échelle mondiale ; une erreur de configuration (ex : un bucket public) expose immédiatement les données à tout Internet — là où une erreur interne restait confinée derrière le pare-feu de l'entreprise.
3. C'est une violation du moindre privilège appliqué aux identités **techniques** : le rôle attaché au pare-feu cumulait des droits sans rapport avec sa fonction (comme un Admin_IT qui lirait les factures). Parade : un rôle dédié aux permissions minimales strictement nécessaires, revu périodiquement, et une alerte sur tout accès inhabituel au stockage.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez le modèle de responsabilité partagée dans le cloud comme la **location d'un appartement** :
    - **Le Propriétaire (Fournisseur Cloud - AWS/Azure/GCP)** est responsable des murs, de la solidité du toit, de la porte d'entrée de l'immeuble et des canalisations (sécurité physique et de l'infrastructure globale).
    - **Le Locataire (Votre entreprise)** est responsable d'installer une serrure robuste sur sa propre porte, de fermer les fenêtres en partant, et de décider qui a le droit d'entrer dans l'appartement (sécurité des données, des accès et des configurations).
    - Si vous laissez votre porte grande ouverte et que vous vous faites cambrioler, c'est de votre responsabilité, pas de celle du propriétaire de l'immeuble.

**Exemple d'application professionnelle :**
Une start-up stocke les factures de ses clients sur un service de stockage cloud. Lors d'un audit de sécurité, le responsable s'aperçoit que les factures sont accessibles publiquement sans mot de passe suite à une erreur humaine de configuration. Il applique immédiatement le modèle de responsabilité partagée en modifiant la politique d'accès du bucket pour exiger une authentification forte (MFA), active le chiffrement automatique des données au repos et déploie un outil de CSPM pour détecter toute dérive future.

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

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après le mini-scénario.

*   **📊 Sondage n°6 :** Que recouvre exactement la « sécurité DU cloud » (par opposition à la sécurité DANS le cloud) ?
    *   A) L'infrastructure physique et la couche de virtualisation — la part du fournisseur ✅
    *   B) La configuration des accès et le chiffrement des données — la part du client
    *   C) Uniquement la protection contre les incendies de datacenters
*   **📊 Sondage n°7 :** Quelle est la bonne pratique concernant le compte Root d'une console cloud ?
    *   A) Le partager entre administrateurs pour la continuité de service
    *   B) L'utiliser au quotidien : c'est le compte le plus complet
    *   C) Ne jamais l'utiliser au quotidien : coffre-fort + MFA matériel, comptes IAM nominatifs pour tout le reste ✅
*   **📊 Sondage n°8 :** Pourquoi les attaquants scannent-ils en continu les plateformes de code publiques comme GitHub ?
    *   A) Pour voler des idées de logiciels innovants
    *   B) Pour y trouver des secrets codés en dur (clés d'API, mots de passe) exploitables en quelques minutes ✅
    *   C) Pour signaler gentiment les bugs aux développeurs

**Éléments de débriefing (pour le mentor) :**

- N°6 : la formule à mémoriser — le fournisseur sécurise le cloud (murs, hyperviseur), le client sécurise ce qu'il met DANS le cloud (données, identités, configurations).
- N°7 : le Root est au cloud ce que le compte administrateur est au poste de travail (B08) — puissance maximale, usage minimal ; le quotidien passe par des comptes IAM nominatifs, MFA obligatoire.
- N°8 : le mini-scénario en version quiz — une clé publiée = une clé volée ; révoquer d'abord, toujours.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Cloud Security Fundamentals"* (durée estimée : 1h30).
*   **Recherche complémentaire** : Visiter le site de l'OWASP et rechercher le top 10 des risques de sécurité spécifiques au Cloud pour en comprendre les menaces courantes.
*   [ANSSI — Externalisation vers le Cloud](https://cyber.gouv.fr)
*   [CNIL — Cloud Computing](https://www.cnil.fr/fr/cloud-computing)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Évaluation des fuites de données dans le cloud.
*   **📊 Sondage Livestorm n°9 :** Un bucket de stockage cloud contenant des fiches de paie est configuré par erreur en accès "Public" sans authentification. De quel type de faille s'agit-il ?
    *   A) Une attaque par force brute.
    *   B) Une mauvaise configuration de sécurité cloud (*misconfiguration*) ✅
    *   C) Une faille logicielle du fournisseur cloud.
*   **Guide d'animation (pour le mentor) :** Rappelez que la majorité des fuites de données dans le cloud résultent de mauvaises configurations de droits d'accès par les clients, et non de failles internes d'AWS ou Microsoft — c'est le cas Verizon, et la prédiction de Gartner du début de session. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Responsabilité partagée** | Le fournisseur sécurise le cloud (murs), le client sécurise DANS le cloud (portes) — ~99 % des incidents sont côté client (Gartner). |
| **IaaS / PaaS / SaaS** | La frontière glisse : le client gère respectivement l'OS et tout au-dessus / son code et ses données / ses données et identités. |
| **Les 2 lignes invariantes** | Les DONNÉES et les IDENTITÉS restent toujours au client, quel que soit le modèle. |
| **Bucket public** | La fuite cloud archétypale — une case cochée, une exposition mondiale (Verizon 2017). |
| **Secret codé en dur** | Une clé dans le code publié = une clé volée en minutes ; révoquer d'abord, nettoyer ensuite. |
| **Compte Root** | Coffre-fort + MFA matériel, jamais au quotidien — comptes IAM nominatifs pour tout le reste. |
| **Moindre privilège machine** | Les rôles techniques aussi : un WAF n'a pas à lire le stockage (Capital One 2019). |
| **CSPM** | La surveillance continue des configurations — détecter la dérive avant les scanners des attaquants. |

**La règle d'or de la session :** le cloud vous loue des murs blindés, mais c'est vous qui fermez les portes — données et identités restent toujours votre responsabilité : configurez au moindre privilège, imposez le MFA, ne codez jamais un secret en dur, et surveillez vos configurations aussi assidûment que les attaquants les scannent.
