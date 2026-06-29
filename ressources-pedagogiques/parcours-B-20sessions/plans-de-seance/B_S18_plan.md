# Plan de séance — Session B18
Parcours : B 20 sessions  |  Module : E — Opérations, détection & réponse  |  Durée : 1h30 (90 minutes)

## 1. Métadonnées de la session
* **Titre** : Introduction à la réponse aux incidents
* **Objectifs pédagogiques opérationnels** :
  * Lister et définir les six phases du cycle de gestion des incidents selon le standard NIST SP 800-61 r2.
  * Différencier et planifier les étapes de confinement (bloquer l'attaque), d'éradication (nettoyer les traces) et de recouvrement (restaurer la production).
  * Rédiger une fiche réflexe (Playbook d'action rapide) destinée à un premier répondant face à une attaque par rançongiciel.
* **Prérequis** : B12 (Sauvegarde) et B17 (Logs).
* **Lien de progression** : Donne la méthode technique et organisationnelle pour faire face à une crise cyber. Cette session sert d'armature théorique pour la simulation de crise en temps réel (B19) et le plan d'action du Capstone (B20).

---

## 2. Déroulé minuté (90 minutes)

| Minutage | Séquence | Contenu théorique & Activités | Rôle du Mentor | Rôle de l'Apprenant | Méthode pédagogique | Livrable / Jalon |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **00 - 15 min** *(15')* | **Brise-glace & Au Feu !** | *Brise-glace : Le départ de feu.* Analogie entre les gestes d'urgence en cas d'incendie physique et les gestes d'urgence en cas d'alerte cyber (panique, confinement, alerte). | Anime la métaphore de sécurité incendie, valide les devoirs de B17 sur les méthodes de confinement réseau. | Déduit les similarités : isoler la source, alerter les secours, ne pas propager. | Interrogative / Discussion | Jalon : Liste d'actions d'urgence comparées. |
| **15 - 35 min** *(20')* | **Apports Théoriques : Cycle NIST** | *Le cycle de vie de la réponse à incident.* Les 6 phases du NIST SP 800-61 : Préparation, Détection/Analyse, Confinement, Éradication, Recouvrement, Post-incident. | Expose chaque phase en insistant sur l'importance du retour d'expérience (Leçons apprises). | Découvre le cadre officiel d'un plan de réponse à incident. | Explicative / Visuelle | - |
| **35 - 50 min** *(15')* | **Apports Théoriques : Confinement** | *Stratégies de confinement et de préservation des preuves.* Pourquoi couper le réseau mais laisser la machine allumée ? Capture de RAM, arrêt des VMs compromises. | Présente les erreurs classiques (éteindre le PC infecté au bouton, propageant le ransomware ou détruisant les clés de déchiffrement en RAM). | Comprend l'importance de préserver les indices pour l'investigation numérique. | Explicative | - |
| **50 - 80 min** *(30')* | **Activité Pratique** | *Activité : La Fiche Réflexe Ransomware.* En sous-groupes, les apprenants rédigent une fiche de procédure "premier répondant" d'une page pour un technicien helpdesk recevant un appel d'un utilisateur infecté. | Distribue le template de fiche, conseille sur la clarté des consignes (éviter le jargon pour le helpdesk). | Rédige les étapes chronologiques (Isoler le PC du Wi-Fi/Ethernet, remonter au SOC, ne pas payer, etc.). | Active / Collaborative | **Livrable** : Fiche réflexe "Premier Répondant Ransomware" prête à l'emploi. |
| **80 - 90 min** *(10')* | **Quiz & Devoirs** | *Quiz de session & Devoirs.* Évaluation sur les phases NIST et consignes pour l'exercice de crise. | Lance le quiz de session et présente les modalités de la simulation de crise B19. | Répond aux questions et s'organise pour le rôle à jouer en session B19. | Interrogative | Jalon : Score au quiz individuel. |

---

## 3. Travail en autonomie (Self-paced)
* **Avant la session suivante (B19)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Incident Response Fundamentals"* (durée estimée : 1h30).
  * **Préparation de la simulation** : Lire le document de mise en situation de crise de l'entreprise "GigaVolt" et s'attribuer un rôle (Directeur de crise, Responsable IT, Responsable Comm, Expert Sécurité).
