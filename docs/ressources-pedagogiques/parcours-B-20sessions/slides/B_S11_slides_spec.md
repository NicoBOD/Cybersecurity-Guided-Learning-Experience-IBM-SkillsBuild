# Spécifications des slides — Session B11 : Sécurité du cloud
Parcours : B 20 sessions  |  Module : C — Identités, cloud & données  |  Format : Spécifications Markdown

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Sécurité du cloud
  - Modèle de responsabilité partagée, sécurité des conteneurs, et gestion des configurations
  - Parcours B — Session B11
- **Notes orateur** : Bienvenue dans cette onzième session. Aujourd'hui, nous allons parler de la sécurité du cloud. Avec la généralisation du cloud computing (IaaS, PaaS, SaaS), la manière de concevoir la sécurité a radicalement changé. Nous allons étudier comment se partagent les responsabilités entre le fournisseur cloud et le client, les risques de mauvaise configuration et comment sécuriser les accès à ces infrastructures.
- **Visuel suggéré** : Illustration d'un nuage numérique transparent traversé par des lignes de données sécurisées et surmonté d'un bouclier holographique vert cyberpunk.
  - **alt-text** : Nuage informatique stylisé et protégé par un bouclier de sécurité.
- **Élément interactif** : Question sondage : "Qui pense que les données stockées chez AWS ou Microsoft Azure sont, par défaut, 100% sécurisées par le fournisseur ?"

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Analyser le modèle de responsabilité partagée selon les types de service (IaaS, PaaS, SaaS).
  - Identifier les risques majeurs de mauvaise configuration (ex: seaux de stockage publics).
  - Configurer et sécuriser des politiques d'accès IAM sur un tenant de cloud public.
  - Sommaire : Le Modèle de Responsabilité Partagée (20 min), Les erreurs de configuration cloud (20 min), IAM & Moindre Privilège Cloud (25 min), Activité d'audit de politique IAM (15 min), Quiz (10 min).
- **Notes orateur** : Au cours de cette séance, nous allons tout d'abord décortiquer le modèle de responsabilité partagée. Ensuite, nous verrons les erreurs classiques de configuration comme les seaux de stockage ouverts à tous les vents. Nous aborderons ensuite la sécurisation fine de l'IAM cloud, avant d'effectuer un audit pratique et de terminer par notre quiz de validation.
- **Visuel suggéré** : Liste ordonnée de l'agenda et des objectifs synchrone présentés dans deux boîtes contrastées.
  - **alt-text** : Tableau d'agenda de la session synchrone de 90 minutes.

---

### Slide 3 — Qu'est-ce que le Cloud ? Les 3 Modèles de Service
- **Type** : contenu
- **Points clés (bullets)** :
  - **IaaS (Infrastructure as a Service)** : Fournit des serveurs virtuels et du stockage brute (ex: AWS EC2, Azure VM).
  - **PaaS (Platform as a Service)** : Fournit un environnement d'exécution pour développer des applications sans gérer l'OS (ex: Heroku, AWS Elastic Beanstalk).
  - **SaaS (Software as a Service)** : Fournit une application clé en main accessible via un navigateur (ex: Microsoft 365, Salesforce).
- **Notes orateur** : Pour bien sécuriser le cloud, il faut comprendre ce que l'on loue. En IaaS, on loue des machines vides : on gère tout, de l'OS aux données. En PaaS, on loue une plateforme pour y déposer son code : l'OS est géré par le fournisseur. En SaaS, on loue un logiciel fini et configuré : on ne gère que les utilisateurs et les données.
- **Visuel suggéré** : Schéma comparatif en trois colonnes (IaaS, PaaS, SaaS) empilant les couches matérielles et logicielles.
  - **alt-text** : Comparatif des modèles de services cloud IaaS, PaaS et SaaS.

---

### Slide 4 — Le Modèle de Responsabilité Partagée (Shared Responsibility)
- **Type** : schéma
- **Points clés (bullets)** :
  - **Règle d'or** : Le fournisseur cloud sécurise *le* Cloud (sécurité physique, serveurs réels, réseaux physiques).
  - Le client sécurise *dans* le Cloud (données, identités, configuration des pare-feux, systèmes d'exploitation en IaaS).
  - Plus on monte vers le SaaS, plus la responsabilité du fournisseur cloud augmente, mais le client garde **toujours** la responsabilité de ses données et des accès (IAM).
- **Notes orateur** : C'est le concept le plus important. Si vos données fuient à cause d'un mot de passe trop simple ou d'un seau de stockage public, ce n'est pas la faute d'AWS ou d'Azure, c'est la vôtre. Le fournisseur garantit la sécurité physique des centres de données et du réseau sous-jacent. Le client est responsable de la configuration de ses ressources et de la protection de ses comptes.
- **Visuel suggéré** : Diagramme montrant la séparation des responsabilités entre le fournisseur (partie basse, en gris) et le client (partie haute, en vert) pour l'IaaS, le PaaS et le SaaS.
  - **alt-text** : Diagramme du modèle de responsabilité partagée dans le cloud.

---

### Slide 5 — La menace n°1 dans le Cloud : La mauvaise configuration
- **Type** : contenu
- **Points clés (bullets)** :
  - Ce ne sont pas des failles logicielles complexes qui causent la majorité des fuites cloud, mais des **erreurs humaines de configuration**.
  - **Seaux de stockage publics (ex: S3 Bucket Open)** : Des bases de données ou fichiers confidentiels exposés sans mot de passe sur Internet.
  - **Secrets codés en dur** : Clés API d'administration cloud laissées dans le code source hébergé sur des dépôts GitHub publics.
  - **Ports d'administration ouverts** : Ports SSH (22) ou RDP (3389) ouverts à toute la Terre.
- **Notes orateur** : Dans le cloud, les attaquants n'ont pas besoin de trouver des failles Zero-Day complexes. Ils écrivent des scripts qui scannent en permanence le web à la recherche de seaux de stockage S3 mal configurés et ouverts sans mot de passe. Ils scannent aussi GitHub à la recherche de clés d'API cloud oubliées par les développeurs dans leur code.
- **Visuel suggéré** : Un dossier de fichiers posé sur un nuage avec un panneau routier jaune "Accès Public" et un cadenas brisé.
  - **alt-text** : Représentation d'une fuite de données due à un stockage cloud public non sécurisé.

---

### Slide 6 — IAM Cloud : La nouvelle frontière du réseau
- **Type** : contenu
- **Points clés (bullets)** :
  - Dans le cloud, le réseau classique disparait $\rightarrow$ l'**IAM devient le nouveau périmètre de sécurité**.
  - Tout accès à une ressource cloud est une requête API évaluée par le système IAM.
  - Règle absolue : Ne jamais utiliser le compte racine (*Root Account*) pour les tâches courantes.
  - Mettre en place un contrôle d'accès au niveau des ressources via le moindre privilège.
- **Notes orateur** : Dans un centre de données traditionnel, on protège les ressources avec un pare-feu physique. Dans le cloud, n'importe quelle ressource a une adresse IP publique potentielle. C'est l'IAM qui sert de barrière. Si votre politique IAM est mal configurée, un compte utilisateur compromis peut détruire l'intégralité de vos serveurs virtuels.
- **Visuel suggéré** : Schéma conceptuel où les murs de briques de pare-feu réseau classiques se transforment en un portail IAM d'authentification dans le nuage.
  - **alt-text** : Remplacement des frontières réseau physiques par l'IAM cloud.

---

### Slide 7 — Exemple de politique IAM Cloud (JSON)
- **Type** : schéma
- **Points clés (bullets)** :
  - Structure typique d'une politique de sécurité cloud (AWS IAM Policy) :
    - `Effect` : `Allow` ou `Deny` (Autoriser ou Interdire).
    - `Action` : L'opération API autorisée (ex: `s3:GetObject`).
    - `Resource` : La ressource ciblée (ex: l'identifiant du seau de stockage).
  - Règle de sécurité : Éviter l'usage de jokers (ex: `Action: "*"`) qui accordent des droits illimités.
- **Notes orateur** : Les politiques d'accès dans le cloud s'écrivent souvent en JSON. Elles décrivent précisément qui a le droit de faire quoi sur quelle ressource. Il faut proscrire l'utilisation de l'étoile ou joker qui donne les droits d'administration complets. Soyez toujours le plus restrictif possible.
- **Visuel suggéré** : Extrait de code JSON formaté et coloré illustrant une politique AWS IAM restrictive autorisant uniquement la lecture d'un bucket spécifique.
  - **alt-text** : Extrait de code d'une politique IAM au format JSON.

---

### Slide 8 — La sécurité des conteneurs dans le Cloud
- **Type** : contenu
- **Points clés (bullets)** :
  - Les conteneurs (ex: Docker) encapsulent l'application et ses dépendances.
  - Partagent le noyau du système d'exploitation de l'hôte (différent d'une machine virtuelle complète).
  - **Bonnes pratiques de sécurité** :
    - Scanner les images de conteneurs à la recherche de vulnérabilités connues (CVE).
    - Ne jamais exécuter un conteneur en tant qu'utilisateur `root` sur l'hôte.
    - Limiter les ressources (CPU, RAM) allouées pour éviter les attaques par déni de service.
- **Notes orateur** : De nombreuses applications cloud s'exécutent aujourd'hui dans des conteneurs légers comme Docker. Contrairement aux machines virtuelles, les conteneurs partagent le noyau de l'OS hôte. Si un conteneur est compromis et s'exécute avec les droits d'administration root, l'attaquant peut s'échapper du conteneur et prendre le contrôle total du serveur serveur hôte.
- **Visuel suggéré** : Un conteneur de transport maritime rouge verrouillé par un code de sécurité numérique vert posé sur un navire porte-conteneurs virtuel.
  - **alt-text** : Représentation symbolique de la sécurité des conteneurs logiciels.

---

### Slide 9 — Outils de détection Cloud : CSPM
- **Type** : contenu
- **Points clés (bullets)** :
  - **CSPM (Cloud Security Posture Management)**.
  - Outil qui scanne en continu vos infrastructures cloud.
  - Détecte automatiquement les dérives de sécurité :
    - Comptes sans MFA.
    - Bases de données exposées publiquement.
    - Clés de chiffrement non rotatives.
  - Compare votre configuration aux standards de conformité (ex: CIS Benchmarks).
- **Notes orateur** : Comment surveiller des milliers de ressources déployées dans le cloud par des dizaines de développeurs ? C'est le rôle du CSPM. Cet outil scanne en permanence votre infrastructure cloud et lève des alertes dès qu'un développeur crée une ressource non conforme aux règles de sécurité de l'entreprise.
- **Visuel suggéré** : Tableau de bord de sécurité cloud synthétique montrant des jauges de conformité, des camemberts de risques et des boutons d'auto-remédiation.
  - **alt-text** : Interface utilisateur simplifiée d'un outil CSPM.

---

### Slide 10 — Activité pratique : Audit d'une politique IAM compromise
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **Scénario** : L'équipe de développement d'EcoLog a écrit la politique IAM suivante pour un stagiaire :
    - `Effect: Allow`, `Action: *`, `Resource: arn:aws:s3:::ecolog-prod-data/*`.
  - **Objectifs** :
    - Identifier le problème de sécurité dans cette politique.
    - Réécrire cette politique en appliquant le moindre privilège (le stagiaire doit uniquement pouvoir lire les fichiers).
    - Expliquer l'impact d'une compromission des clés API de ce stagiaire.
- **Notes orateur** : Dans cet exercice pratique, vous allez auditer une politique d'accès IAM rédigée par un développeur pressé pour un stagiaire. Identifiez l'erreur majeure et réécrivez cette politique en JSON de manière sécurisée pour n'accorder que le droit de lecture de fichiers au stagiaire.
- **Visuel suggéré** : Deux politiques JSON face-à-face : à gauche, la politique vulnérable avec une étoile rouge clignotante, à droite, la politique corrigée et sécurisée.
  - **alt-text** : Comparatif visuel de politiques d'accès cloud vulnérable et durcie.
- **Élément interactif** : Travail en petits groupes de 15 minutes suivi d'une correction pas à pas en session plénière.

---

### Slide 11 — Quiz de validation
- **Type** : quiz
- **Points clés (bullets)** :
  - 1. En IaaS, qui est responsable de la sécurité du système d'exploitation de la machine virtuelle ?
  - 2. Pourquoi l'usage de jokers (`*`) dans les politiques IAM cloud est-il considéré comme une mauvaise pratique ?
  - 3. Quelle est la fonction principale d'un outil CSPM ?
- **Notes orateur** : C'est le moment du quiz. Préparez-vous à répondre pour valider les notions de responsabilité partagée, d'écriture de politique IAM sécurisée et de surveillance automatisée par CSPM.
- **Visuel suggéré** : QR Code d'accès au questionnaire interactif à gauche, questions à choix multiples à droite.
  - **alt-text** : QR Code vert cyberpunk de connexion au questionnaire interactif.
- **Élément interactif** : Quiz en direct avec affichage des statistiques de réponses des apprenants.

---

### Slide 12 — Conclusion & Travail autonome
- **Type** : récap
- **Points clés (bullets)** :
  - **Résumé** : Modèle de responsabilité partagée (fournisseur = du cloud, client = dans le cloud), risques majeurs de configurations, sécurité IAM (JSON, pas de jokers), et surveillance continue (CSPM).
  - **Devoirs** : Compléter le module *"Cloud Security Fundamentals"* sur IBM SkillsBuild (~1h30).
  - **Défi** : Explorer l'interface gratuite de console d'un fournisseur cloud (AWS/Azure/GCP) et simuler la création d'un utilisateur sans aucun droit par défaut.
  - Prochaine session : *Sécurité & confidentialité des données (B12)*.
- **Notes orateur** : Nous avons posé les bases de la sécurité du cloud ! N'oubliez pas de finaliser le cours sur IBM SkillsBuild. La semaine prochaine, nous verrons comment protéger spécifiquement l'actif le plus précieux des organisations : les données elles-mêmes. Bonne semaine à tous !
- **Visuel suggéré** : Badge d'achèvement de cours d'IBM SkillsBuild pour la sécurité cloud.
  - **alt-text** : Badge de réussite du cours Cloud Security d'IBM SkillsBuild.
