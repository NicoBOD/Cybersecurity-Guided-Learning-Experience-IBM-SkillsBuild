# Plan de séance — Session B11
Parcours : B 20 sessions  |  Module : C — Identités, cloud & données  |  Durée : 1h30 (90 minutes)

## 1. Métadonnées de la session
* **Titre** : Sécurité du cloud
* **Objectifs pédagogiques opérationnels** :
  * Analyser le modèle de responsabilité partagée pour les services IaaS, PaaS et SaaS.
  * Identifier les risques majeurs de sécurité liés aux mauvaises configurations dans les infrastructures cloud publics (ex. espaces de stockage ouverts, clés d'API hardcodées).
  * Définir et appliquer des règles de sécurisation des accès IAM spécifiques aux consoles d'administration cloud.
* **Prérequis** : B09 et B10.
* **Lien de progression** : Transpose les concepts de contrôle d'accès (B09) et de chiffrement (B10) dans l'écosystème cloud, qui héberge la majorité des données d'entreprise étudiées en B12.

---

## 2. Déroulé minuté (90 minutes)

| Minutage | Séquence | Contenu théorique & Activités | Rôle du Mentor | Rôle de l'Apprenant | Méthode pédagogique | Livrable / Jalon |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **00 - 15 min** *(15')* | **Brise-glace & Coloc** | *Brise-glace : La colocation.* Métaphore comparant le propriétaire d'un appartement loué (le cloud provider) et le locataire (le client) pour introduire la répartition des devoirs de sécurité. | Anime la discussion métaphorique et valide les devoirs de B10 sur la classification IaaS/PaaS/SaaS. | Participe à la métaphore et identifie qui gère quoi (la serrure, l'assurance, les meubles). | Interrogative / Discussion | Jalon : Revue de la typologie des services cloud. |
| **15 - 35 min** *(20')* | **Apports Théoriques : Partage** | *Modèle de responsabilité partagée.* Répartition stricte de la sécurité entre le fournisseur cloud (sécurité *du* cloud) et le client (sécurité *dans* le cloud). | Explique le modèle de responsabilité partagée et projette les grilles de répartition d'AWS, Microsoft 365 et Google Cloud. | Prend des notes, pose des questions sur les frontières de responsabilité. | Explicative / Visuelle | - |
| **35 - 50 min** *(15')* | **Apports Théoriques : Menaces Cloud** | *Mauvaises configurations cloud.* Fuites de buckets de stockage publics, vol de clés d'API sur les dépôts de code publics (GitHub), et piratage de consoles de management sans MFA. | Présente des exemples récents d'incidents cloud causés par de simples erreurs de configuration. | Analyse les vecteurs d'attaque spécifiques au cloud. | Explicative | - |
| **50 - 80 min** *(30')* | **Activité Pratique** | *Activité : Matrice de responsabilité.* Les apprenants reçoivent 10 tâches de sécurité (ex. patching de l'OS invité, sauvegarde des données, sécurité physique des disques) et doivent les attribuer selon le modèle cloud choisi (IaaS, PaaS, SaaS). | Distribue le modèle de tableau comparatif, passe dans les salons pour valider la logique d'attribution. | Remplit la matrice d'attribution en groupe et justifie ses choix face au mentor. | Active / Collaborative | **Livrable** : Matrice de responsabilité partagée complétée et argumentée. |
| **80 - 90 min** *(10')* | **Quiz & Devoirs** | *Quiz de session & Devoirs.* Évaluation des connaissances de sécurité cloud et présentation du travail autonome. | Lance le quiz de session et présente le travail autonome SkillsBuild. | Répond au quiz et note les consignes pour la session B12. | Interrogative | Jalon : Score au quiz individuel. |

---

## 3. Travail en autonomie (Self-paced)
* **Avant la session suivante (B12)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Cloud Security Fundamentals"* (durée estimée : 1h30).
  * **Préparation du Mini-projet 2** : Relire les consignes sur la protection des données et identifier les différents types de données sensibles traitées au sein d'une entreprise (RH, R&D, Clients, Finances).
