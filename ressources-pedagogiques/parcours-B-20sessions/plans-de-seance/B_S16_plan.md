# Plan de séance — Session B16
Parcours : B 20 sessions  |  Module : E — Opérations, détection & réponse  |  Durée : 1h30 (90 minutes)

## 1. Métadonnées de la session
* **Titre** : Centre des opérations de sécurité (SOC) & supervision
* **Objectifs pédagogiques opérationnels** :
  * Décrire l'organisation, les rôles (L1, L2, L3) et les interactions au sein d'un Centre d'Opérations de Sécurité (SOC) moderne.
  * Modéliser le cycle de vie d'une alerte de sécurité et expliquer comment qualifier et éliminer un faux positif.
  * Interpréter et calculer les métriques de performance fondamentales d'un SOC : MTTD (temps moyen de détection) et MTTR (temps moyen de réponse).
* **Prérequis** : Modules B et C.
* **Lien de progression** : Introduit l'organisation humaine et fonctionnelle de la détection d'alertes. Elle est directement suivie par la session B17 qui étudiera l'outil technique principal du SOC (le SIEM) et l'analyse de logs réels.

---

## 2. Déroulé minuté (90 minutes)

| Minutage | Séquence | Contenu théorique & Activités | Rôle du Mentor | Rôle de l'Apprenant | Méthode pédagogique | Livrable / Jalon |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **00 - 15 min** *(15')* | **Brise-glace & Aiguillage** | *Brise-glace : La tour de contrôle.* Métaphore comparant le SOC aux aiguilleurs du ciel dans un aéroport gérant des milliers de vols réguliers et réagissant aux pannes. | Présente la métaphore, valide les devoirs sur les définitions SOC et SIEM de B15. | Participe à la métaphore, identifie la charge mentale liée au flux d'alertes continu. | Interrogative / Métaphorique | Jalon : Revue collective des concepts de supervision. |
| **15 - 35 min** *(20')* | **Apports Théoriques : Rôles** | *Organisation et métiers du SOC.* Rôle de l'analyste L1 (triage et filtrage), L2 (investigation approfondie), et L3 (réponse à incident et threat hunting). | Explique la répartition des tâches et la gestion du stress en salle de SOC. | Prend des notes, découvre le quotidien d'un analyste en sécurité opérationnelle. | Explicative | - |
| **35 - 50 min** *(15')* | **Apports Théoriques : KPIs** | *Traitement d'alertes & KPIs.* Cycle de qualification, faux positifs vs vrais positifs. Métriques de performance : MTTD (Mean Time To Detect) et MTTR (Mean Time To Respond). | Détaille les formules de calcul et l'intérêt d'automatiser le SOC (SOAR) pour réduire le MTTR. | Assimile l'importance de l'efficacité opérationnelle et des processus standardisés (Playbooks). | Explicative / Mathématique | - |
| **50 - 80 min** *(30')* | **Activité Pratique** | *Activité : Qualification et triage d'alertes.* Les apprenants étudient 3 alertes brutes de supervision (ex. connexion SSH depuis l'étranger, fichier suspect téléchargé par la DRH) et décident de l'action L1. | Distribue les 3 fiches d'alertes, conseille sur la recherche de contexte (localisation IP, rôles utilisateurs). | Analyse les alertes en groupe, qualifie (FP, VP, Escaler L2) et rédige un ticket d'escalade court. | Active / Collaborative | **Livrable** : Ticket de qualification et d'escalade d'alerte de sécurité rédigé. |
| **80 - 90 min** *(10')* | **Quiz & Devoirs** | *Quiz de session & Devoirs.* Validation des principes organisationnels du SOC. | Lance le quiz de fin de session et présente le travail autonome SkillsBuild. | Effectue le quiz en ligne et note les devoirs. | Interrogative | Jalon : Score au quiz individuel. |

---

## 3. Travail en autonomie (Self-paced)
* **Avant la session suivante (B17)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Security Operations Center (SOC) Fundamentals"* (durée estimée : 1h30).
  * **Recherche autonome** : Trouver la définition d'un log système (journal d'événements) et identifier les trois éléments obligatoires devant figurer dans chaque ligne de log (horodatage, source, événement).
