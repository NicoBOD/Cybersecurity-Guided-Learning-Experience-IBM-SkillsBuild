# Plan de séance — Session B09
Parcours : B 20 sessions  |  Module : C — Identités, cloud & données  |  Durée : 1h30 (90 minutes)

## 1. Métadonnées de la session
* **Titre** : Gestion des identités et des accès (IAM)
* **Objectifs pédagogiques opérationnels** :
  * Distinguer les quatre étapes clés de l'IAM : Identification (qui êtes-vous ?), Authentification (prouvez-le !), Autorisation (qu'avez-vous le droit de faire ?), et Audit (qu'avez-vous fait ?).
  * Comparer les modèles de contrôle d'accès RBAC (Role-Based Access Control) et ABAC (Attribute-Based Access Control).
  * Concevoir une politique d'authentification multifacteur (MFA) et de Single Sign-On (SSO) adaptée aux besoins de sécurité et d'ergonomie d'une entreprise.
* **Prérequis** : Module B (Systèmes & réseaux).
* **Lien de progression** : Cette session jette les bases logiques du contrôle d'accès aux données. Elle est prolongée par la session B10, qui présentera les mécanismes cryptographiques permettant de sécuriser ces accès et l'intégrité des identités numériques.

---

## 2. Déroulé minuté (90 minutes)

| Minutage | Séquence | Contenu théorique & Activités | Rôle du Mentor | Rôle de l'Apprenant | Méthode pédagogique | Livrable / Jalon |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **00 - 15 min** *(15')* | **Brise-glace & Revue** | *Brise-glace : Le trousseau de clés.* Les apprenants partagent leurs astuces de gestion de mots de passe et le mentor introduit le concept d'IAM. | Anime le débat sur les gestionnaires de mots de passe, fait la transition avec B08. | Donne ses retours d'expérience et participe à la revue de B08. | Interrogative / Discussion | Jalon : Revue des bonnes pratiques de gestion des clés. |
| **15 - 35 min** *(20')* | **Apports Théoriques : Cycle IAM** | *Les 4 piliers de l'IAM.* Identification, Authentification (facteurs d'authentification), Autorisation, et Audit (traçabilité des logs). | Explique le cycle de vie d'une identité et le principe du MFA. Projette des schémas d'architectures SSO. | Assimile les concepts d'authentification forte et de centralisation des accès. | Explicative / Visuelle | - |
| **35 - 50 min** *(15')* | **Apports Théoriques : RBAC vs ABAC** | *Contrôle d'accès logique.* Différences entre le modèle RBAC (basé sur le rôle métier) et ABAC (basé sur des attributs dynamiques comme l'heure ou la géolocalisation). | Compare les deux modèles et donne des exemples de règles de filtrage d'accès. | Découvre la gestion granulaire des droits d'accès aux dossiers partagés. | Explicative | - |
| **50 - 80 min** *(30')* | **Activité Pratique** | *Activité : La Matrice RBAC.* À partir d'un organigramme d'entreprise et d'une liste de ressources (compta, RH, serveurs), les apprenants tracent la matrice de droits (R/W/D) des différents rôles. | Distribue l'organigramme de l'entreprise "MediDistri", guide la structuration des rôles. | Rédige la matrice d'attribution des privilèges par groupe en veillant au moindre privilège. | Active / Collaborative | **Livrable** : Tableau de droits réseau configuré selon le modèle RBAC. |
| **80 - 90 min** *(10')* | **Quiz & Devoirs** | *Quiz de session & Devoirs.* Validation des principes IAM et présentation de la suite. | Lance le quiz de fin de session et présente le travail autonome SkillsBuild. | Répond au quiz et note les consignes de travail autonome. | Interrogative | Jalon : Score au quiz individuel. |

---

## 3. Travail en autonomie (Self-paced)
* **Avant la session suivante (B10)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Identity and Access Management Fundamentals"* (durée estimée : 1h30).
  * **Recherche autonome** : Trouver la définition du terme "sel cryptographique" (salt) et comprendre pourquoi il est indispensable pour stocker des mots de passe en base de données.
