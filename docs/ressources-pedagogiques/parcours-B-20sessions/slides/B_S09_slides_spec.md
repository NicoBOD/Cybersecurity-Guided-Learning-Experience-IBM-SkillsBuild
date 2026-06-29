# Spécifications des slides — Session B09 : Gestion des identités et des accès (IAM)
Parcours : B 20 sessions  |  Module : C — Sécurité des Systèmes et Applications  |  Format : Spécifications Markdown

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Gestion des identités et des accès (IAM)
  - Identifier, authentifier, autoriser et tracer les activités des utilisateurs
  - Parcours B — Session B09
- **Notes orateur** : Bienvenue dans cette neuvième session. Aujourd'hui, nous allons nous attaquer à la gestion des identités et des accès, couramment appelée IAM. C'est l'un des piliers les plus importants de la cybersécurité moderne. Nous allons voir comment s'assurer que les bonnes personnes accèdent aux bonnes ressources, au bon moment, et comment prouver leur identité de manière robuste.
- **Visuel suggéré** : Représentation d'une empreinte digitale numérique lumineuse verte entourée de cercles concentriques de clés, de jetons d'accès et d'engrenages de sécurité.
  - **alt-text** : Graphisme de haute technologie illustrant la biométrie et le contrôle d'accès dans un style cyberpunk.
- **Élément interactif** : Question sondage : "Selon vous, quelle proportion des cyberattaques réussies impliquent l'utilisation de mots de passe volés ou compromis ?"

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Expliquer les quatre étapes fondamentales de l'IAM : Identification, Authentification, Autorisation et Audit.
  - Comparer le modèle de contrôle d'accès basé sur les rôles (RBAC) avec le modèle basé sur les attributs (ABAC).
  - Concevoir une politique d'authentification multifacteur (MFA) et d'authentification unique (SSO).
  - Sommaire : Les 4 piliers de l'IAM (25 min), Attribution des droits : RBAC vs ABAC (20 min), MFA & SSO (20 min), Exercice Matrice RBAC (15 min), Quiz (10 min).
- **Notes orateur** : Durant ces 90 minutes, nous allons découper l'IAM en quatre concepts clés. Nous étudierons les modèles de gestion des droits RBAC et ABAC, puis nous aborderons le fonctionnement du SSO et du MFA. Nous ferons un cas pratique de création de matrice de droits et nous terminerons par un quiz de validation.
- **Visuel suggéré** : Agenda minuté aligné à droite, avec les 3 compétences cibles affichées sous forme d'icônes à gauche.
  - **alt-text** : Tableau d'agenda minuté de la session synchrone d'IAM.

---

### Slide 3 — Les 4 étapes logiques de l'IAM
- **Type** : contenu
- **Points clés (bullets)** :
  - **Identification** : Déclarer qui vous êtes (ex. nom d'utilisateur, adresse e-mail).
  - **Authentification (AuthN)** : Prouver qui vous êtes (ex. mot de passe, empreinte).
  - **Autorisation (AuthZ)** : Accorder les droits (ex. droit de lecture, d'écriture).
  - **Audit (Responsabilité)** : Tracer les actions dans les journaux d'événements (logs).
- **Notes orateur** : L'IAM n'est pas juste un mot de passe. C'est un processus en 4 étapes distinctes. L'identification déclare une identité. L'authentification vérifie la preuve de cette identité. L'autorisation accorde les droits et l'audit enregistre tout pour des besoins d'investigation ultérieurs.
- **Visuel suggéré** : Une frise chronologique horizontale présentant les 4 étapes avec des icônes d'utilisateur, de clé, de cadenas ouvert et de loupe d'analyse de logs.
  - **alt-text** : Frise chronologique présentant le parcours logique de l'identification à l'audit.

---

### Slide 4 — L'analogie de l'immeuble sécurisé
- **Type** : schéma
- **Points clés (bullets)** :
  - **Identification** : *"Bonjour, je suis Alice, consultante externe."*
  - **Authentification** : Alice présente son passeport officiel à l'accueil.
  - **Autorisation** : L'accueil lui remet un badge programmé uniquement pour le 1er étage.
  - **Audit** : Chaque passage de badge d'Alice est enregistré dans le registre de sécurité.
- **Notes orateur** : Pour bien fixer ces notions, reprenons l'analogie d'un bâtiment physique. Vous vous présentez à l'accueil : c'est l'identification. L'agent de sécurité contrôle votre pièce d'identité : c'est l'authentification. Il vous remet un badge d'accès limité à certains étages : c'est l'autorisation. Enfin, l'historique des portes que vous ouvrez est enregistré : c'est l'audit.
- **Visuel suggéré** : Illustration d'un hall d'accueil d'entreprise moderne avec un portillon de sécurité et un écran affichant les logs de passage.
  - **alt-text** : Bande dessinée modélisant les étapes de contrôle d'accès dans un bâtiment d'entreprise.

---

### Slide 5 — L'Authentification Multifacteur (MFA)
- **Type** : contenu
- **Points clés (bullets)** :
  - Vise à neutraliser le vol simple de mot de passe.
  - Utilise **au moins deux facteurs de catégories différentes** :
    - *Ce que je sais* : Mot de passe, code PIN.
    - *Ce que je possède* : Clé YubiKey, code sur smartphone (OTP), application d'authentification.
    - *Ce que je suis* : Caractéristique biométrique (empreinte, visage).
  - Deux mots de passe différents $\neq$ MFA (ce sont deux facteurs de même nature).
- **Notes orateur** : Le mot de passe seul est trop facile à voler par phishing ou force brute. Pour sécuriser un accès, on ajoute du MFA. Mais attention, pour que ce soit du MFA, il faut utiliser des facteurs de natures différentes. Saisir deux codes secrets n'est pas du MFA. Il faut combiner ce que vous savez (votre mot de passe) et ce que vous possédez (votre smartphone ou une clé USB matérielle de sécurité).
- **Visuel suggéré** : Schéma d'une balance avec trois plateaux représentant le Savoir, la Possession et la Biométrie, tous connectés pour valider une identité.
  - **alt-text** : Illustration des 3 catégories de facteurs d'authentification.

---

### Slide 6 — RBAC : Le contrôle d'accès basé sur les rôles
- **Type** : schéma
- **Points clés (bullets)** :
  - **RBAC (Role-Based Access Control)**.
  - Les permissions sont attribuées à des **rôles métier** (ex: RH, Comptable, AdminIT).
  - Les utilisateurs sont affectés à ces rôles.
  - Idéal pour les structures stables et la simplicité de gestion.
  - Évite de configurer des droits individuels machine par machine.
- **Notes orateur** : Le modèle RBAC lie les accès aux fonctions de l'employé. Si vous êtes dans l'équipe RH, vous êtes affecté au rôle "RH" et vous héritez automatiquement des droits d'écriture sur les dossiers du personnel. C'est le modèle le plus classique, simple à mettre en place et très lisible pour les audits de sécurité.
- **Visuel suggéré** : Schéma d'association : Utilisateurs $\rightarrow$ Rôles (Boîtes étiquetées RH, Informatique, Finances) $\rightarrow$ Permissions de dossiers.
  - **alt-text** : Schéma structurel de l'attribution des droits par rôles professionnels.

---

### Slide 7 — ABAC : Le contrôle d'accès basé sur les attributs
- **Type** : contenu
- **Points clés (bullets)** :
  - **ABAC (Attribute-Based Access Control)**.
  - Évalue les droits de manière dynamique et granulaire.
  - Se base sur des attributs contextuels :
    - *Attribut du sujet* : Fonction, habilitation.
    - *Attribut de la ressource* : Sensibilité du document.
    - *Attribut environnemental* : Heure de connexion, adresse IP de connexion.
- **Notes orateur** : Le modèle ABAC est beaucoup plus intelligent et granulaire que le RBAC. Au lieu de dire "Alice a le rôle comptable donc elle accède au fichier", on va vérifier son rôle, mais aussi l'heure et son adresse IP. Par exemple : Alice ne peut modifier les fichiers financiers que pendant les heures de bureau et uniquement si elle est connectée au réseau local du siège de l'entreprise.
- **Visuel suggéré** : Un organigramme de décision complexe combinant l'identité d'un utilisateur, sa géolocalisation IP et l'heure système pour autoriser l'accès à un fichier confidentiel.
  - **alt-text** : Représentation d'une politique de filtrage dynamique ABAC selon plusieurs variables.

---

### Slide 8 — Single Sign-On (SSO) : Authentification unique
- **Type** : schéma
- **Points clés (bullets)** :
  - Permet d'accéder à toutes ses applications professionnelles en s'authentifiant une seule fois auprès d'un fournisseur d'identité central (IdP).
  - *Avantages* :
    - Élimine la lassitude des mots de passe (un seul mot de passe fort à mémoriser).
    - Centralise la révocation des accès (si le salarié part, on désactive son compte SSO et il perd tous ses accès instantanément).
- **Notes orateur** : Le SSO simplifie la vie des utilisateurs : au lieu d'avoir 50 mots de passe pour 50 outils différents, ils s'identifient une seule fois auprès d'un portail d'entreprise. Pour la sécurité, c'est génial : on peut imposer une double authentification forte à ce portail unique, et si un collaborateur quitte l'entreprise, on coupe son compte SSO pour révoquer l'intégralité de ses accès en une seule action.
- **Visuel suggéré** : Schéma montrant un utilisateur s'identifiant sur un portail central qui génère des jetons de connexion sécurisés vers différentes icônes d'outils cloud (e-mail, CRM, cloud d'entreprise).
  - **alt-text** : Architecture de fonctionnement d'un portail SSO d'entreprise.

---

### Slide 9 — Le revers de la médaille du SSO
- **Type** : contenu
- **Points clés (bullets)** :
  - **Risque majeur** : Point de défaillance unique (Single Point of Failure).
  - Si le mot de passe du compte SSO est compromis $\rightarrow$ l'attaquant accède à **toutes** les applications de l'entreprise.
  - **Mesures compensatoires obligatoires** :
    - Imposer du MFA ultra-robuste sur le SSO.
    - Surveiller les alertes de connexions suspectes (ex: connexions simultanées depuis deux pays différents).
- **Notes orateur** : Le SSO a un défaut majeur : c'est un point de défaillance unique. Si un pirate réussit à usurper les identifiants SSO d'un utilisateur, il a les clés de toute la maison. Pour protéger ce point critique, le MFA est obligatoire sur les portails SSO, de même que la surveillance active des connexions inhabituelles, comme une connexion depuis Paris suivie 5 minutes après d'une connexion depuis un autre continent.
- **Visueliez suggéré** : Un trousseau contenant une clé géante dorée brisée en deux, avec une alerte rouge clignotante à côté du mot "Compromission".
  - **alt-text** : Graphisme de sécurité représentant le risque du point de défaillance unique sur un compte centralisé.

---

### Slide 10 — Activité pratique : La matrice RBAC de "MediDistri"
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **Scénario** : Concevoir la matrice de droits pour MediDistri.
  - **Rôles** : RH_Manager, Comptable, Admin_IT, Stagiaire_Marketing.
  - **Ressources** : Dossier Candidats RH, Base Factures, Console AWS, Portail Actualités.
  - **Permissions** : Écriture (W), Lecture seule (R), Aucun accès (N).
  - **Objectif** : Remplir la matrice en appliquant le principe du moindre privilège.
- **Notes orateur** : Passons au cas pratique. Vous allez concevoir la matrice d'accès de l'entreprise MediDistri. Pour chaque profil d'employé, vous devez décider s'il doit pouvoir écrire, lire ou n'avoir aucun accès à nos 4 ressources cibles. N'oubliez pas notre règle d'or : le moindre privilège. Un administrateur système n'a pas à lire les dossiers RH confidentiels.
- **Visuel suggéré** : Tableau vide croisant les 4 rôles et les 4 ressources à évaluer.
  - **alt-text** : Matrice de droits RBAC vierge pour l'atelier collaboratif.
- **Élément interactif** : Travail collaboratif en équipes de 3 à 4 personnes pour concevoir la matrice de droits.

---

### Slide 11 — Quiz de validation
- **Type** : quiz
- **Points clés (bullets)** :
  - 1. Quel concept IAM correspond à l'acte de vérifier l'identité d'un utilisateur par un mot de passe et un SMS ?
  - 2. Quelle est la différence majeure entre le modèle RBAC et le modèle ABAC ?
  - 3. Est-il correct de dire que le SSO diminue le risque d'usurpation s'il n'est pas protégé par du MFA ?
- **Notes orateur** : Testons vos connaissances sur l'IAM. Répondez au quiz sur votre outil de vote. Portez une attention particulière à la distinction entre Authentification et Autorisation, et aux limites de sécurité du SSO.
- **Visuel suggéré** : Code QR vert de connexion au quiz à gauche et questions à choix multiples à droite.
  - **alt-text** : QR Code d'accès au vote électronique de fin de session.
- **Élément interactif** : Vote synchrone en temps réel avec correction immédiate.

---

### Slide 12 — Conclusion & Travail autonome
- **Type** : récap
- **Points clés (bullets)** :
  - **Résumé** : Piliers IAM (identification, authentification, autorisation, audit), MFA (catégories distinctes), RBAC vs ABAC, SSO (avantages et surveillance).
  - **Devoirs** : Suivre le cours *"Identity and Access Management Fundamentals"* sur IBM SkillsBuild (~1h30).
  - **Recherche** : Découvrir comment fonctionnent les protocoles de SSO modernes **SAML 2.0** et **OIDC (OpenID Connect)**.
  - Prochaine session : *Cryptographie essentielle (B10)*.
- **Notes orateur** : Nous avons sécurisé les accès de nos systèmes ! Pour consolider cela, suivez le module de cours d'IAM sur IBM SkillsBuild et renseignez-vous sur les technologies SAML et OIDC qui permettent au SSO de fonctionner de façon standardisée sur le web. Bonne semaine à tous et à la prochaine séance !
- **Visuel suggéré** : Badge d'achèvement de cours d'IBM SkillsBuild et logotypes des protocoles SAML 2.0 et OpenID Connect.
  - **alt-text** : Visuels de badges IBM SkillsBuild et logos des standards SAML/OIDC.
