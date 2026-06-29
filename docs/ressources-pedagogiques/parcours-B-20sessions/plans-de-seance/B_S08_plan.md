# Plan de séance — Session B08
Parcours : B 20 sessions  |  Module : B — Systèmes & réseaux  |  Durée : 1h30 (90 minutes)

## 1. Métadonnées de la session
* **Titre** : Durcissement des systèmes & endpoints (Validation Mini-projet 1)
* **Objectifs pédagogiques opérationnels** :
  * Appliquer le principe du moindre privilège sur un système d'exploitation (Windows/Linux).
  * Lister les étapes fondamentales du durcissement (*hardening*) d'un serveur et d'un poste de travail.
  * Comparer le fonctionnement d'un antivirus traditionnel (basé sur les signatures) avec un EDR (détection comportementale).
  * Restituer et valider le **Mini-projet 1 (Architecture réseau sécurisée)** à travers une évaluation croisée.
* **Prérequis** : B05 à B07.
* **Lien de progression** : Clôture le module infrastructurel (Systèmes & Réseaux) par la sécurisation des machines hôtes et l'intégration pratique (Mini-projet 1). Ouvre sur le contrôle d'accès logique et l'identité du module suivant (Module C).

---

## 2. Déroulé minuté (90 minutes)

| Minutage | Séquence | Contenu théorique & Activités | Rôle du Mentor | Rôle de l'Apprenant | Méthode pédagogique | Livrable / Jalon |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **00 - 10 min** *(10')* | **Brise-glace & Intro** | *Brise-glace : Le service inutile.* Réflexion sur les services actifs par défaut d'un OS (ex. partage de fichiers, bluetooth) et leur désactivation. | Anime la discussion sur le concept de réduction de surface d'attaque. | Émet des hypothèses sur la nécessité de désactiver les fonctionnalités inutilisées. | Interrogative / Discussion | Jalon : Liste de services OS à désactiver par défaut. |
| **10 - 30 min** *(20')* | **Apports Théoriques : Hardening** | *Durcissement et gestion des endpoints.* Moindre privilège, gestion des correctifs (patching), antivirus signature vs EDR. | Présente les étapes clés du durcissement (ex. CIS Benchmarks) et le fonctionnement de l'EDR. | Découvre les bases de l'administration système sécurisée et de la surveillance d'hôte. | Explicative | - |
| **30 - 45 min** *(15')* | **Démo : Checklist Hardening** | *Démonstration pratique de durcissement.* Présentation en direct d'une checklist de durcissement de système d'exploitation Windows ou Linux. | Réalise la démonstration (fermeture de ports locaux, politiques de groupes GPO). | Observe la démonstration et identifie les commandes appliquées. | Démonstrative | Jalon : Checklist de durcissement OS fournie. |
| **45 - 80 min** *(35')* | **Restitution Mini-projet 1** | *Restitution et évaluation croisée.* Présentation en petits groupes de l'architecture réseau sécurisée conçue pour l'entreprise fictive (Mini-projet 1). | Anime la soutenance, distribue les grilles d'évaluation croisée et arbitre les évaluations. | Pitch l'architecture réseau du groupe (3 min) et évalue celle de deux autres groupes (évaluation par pairs). | Active / Collaborative | **Livrable** : Rendu final du **Mini-projet 1** et grilles d'évaluation associées. |
| **80 - 90 min** *(10')* | **Quiz & Débriefing** | *Quiz & Transition.* Clôture du Module B, validation des acquis et introduction du Module C (Gestion des identités - IAM). | Lance le quiz et introduit les objectifs du module suivant. | Répond au quiz et note les consignes de travail autonome. | Interrogative | Jalon : Score au quiz individuel. |

---

## 3. Travail en autonomie (Self-paced)
* **Avant la session suivante (B09)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"System Hardening and Patch Management"* (durée estimée : 1h30).
  * **Transition Module C** : Identifier le concept de Single Sign-On (SSO) et lister les services que vous utilisez au quotidien qui s'appuient sur cette technologie (ex. Google Login, Microsoft Login).
