# Parcours A — Session 06 : Opérations de sécurité & gestion des vulnérabilités
Module : SecOps & Vulnérabilités  |  Durée : 90 min  |  Parcours : A 8 sessions

## Objectifs pédagogiques (4, verbes d'action)
- **Expliquer** le cycle de détection d'une alerte de sécurité, de la génération d'un journal d'événements (*log*) jusqu'à sa prise en charge par un analyste SOC.
- **Distinguer** l'objectif et la méthodologie d'un audit par scan automatisé de vulnérabilités par rapport à un test d'intrusion (*pentest*).
- **Interpréter** les composantes d'un score de gravité CVSS pour prioriser la remédiation des failles de sécurité découvertes.
- **Planifier** un calendrier opérationnel de gestion des correctifs (*patching*) minimisant les perturbations pour l'activité d'une entreprise.

## Prérequis
- Sessions précédentes : A3, A5.
- Self-paced AVANT la séance (~90 min) : Module SkillsBuild sur les opérations de sécurité (introduction aux outils SIEM et à la journalisation des événements système).

## Découpage temporel (90 min)
| Min | Segment | Format | Support |
|-----|---------|--------|---------|
| 0–5 | Accueil, logistique & présentation de la séance | Plénière | Slide titre & objectifs |
| 5–15 | Rappel interactif : "Qui écrit les logs et pourquoi ?" | Interactif | Question ouverte / Tableau blanc |
| 15–35 | Apport de contenu 1 : Les opérations de sécurité (SOC et SIEM) | Exposé illustré | Slides organisation SOC & corrélation SIEM |
| 35–50 | Activité 1 : Calcul de priorité CVSS et plan d'action | Travail en petits groupes (3-4) | Fiche d'activité A_S06 |
| 50–70 | Apport de contenu 2 : Découvrir les failles (Scan vs Pentest) & gérer les patchs | Exposé structuré | Slides vulnérabilités (CVE) & patching |
| 70–85 | Démo 6 : Analyse de logs suspectes + Quiz live | Démo + Quiz interactif | Script de démo & Banque de quiz (Thème A6) |
| 85–90 | Clôture de la session & consignes du travail pour A7 | Plénière | Slide récapitulatif & devoirs |

## Activités détaillées
- **Activité 1 — Priorisation de correctifs avec les scores CVSS** :
  - *Objectif* : Utiliser le référentiel CVSS pour classer des failles de sécurité et planifier leur remédiation selon le contexte métier d'une PME.
  - *Consignes pas-à-pas* :
    1. Répartir les apprenants en sous-groupes de 3 ou 4.
    2. Distribuer une liste de 3 vulnérabilités découvertes lors d'un scan sur le réseau de l'entreprise (Vulnérabilité 1 : Faille d'exécution de code à distance sur le serveur web public, CVSS 9.8 ; Vulnérabilité 2 : Faille d'élévation de privilèges sur les postes de travail locaux, CVSS 7.2 ; Vulnérabilité 3 : Faille de divulgation d'informations mineure sur un serveur d'archives interne, CVSS 4.3).
    3. Les groupes doivent calculer l'ordre de priorité (de 1 à 3) de traitement de ces failles.
    4. Proposer une action corrective pour chacune (appliquer le correctif immédiat, planifier à la prochaine maintenance, mettre en place une règle de filtrage temporaire).
    5. Faire présenter par un rapporteur les arbitrages du groupe (notamment l'impact métier si le serveur web est critique).
  - *Livrable attendu* : Un tableau de priorisation des vulnérabilités avec justification du calendrier de patching proposé.
  - *Durée* : 15 minutes (10 min de réflexion pratique, 5 min de partage).
  - *Modalité* : Travail en petits groupes.
  - *Critères de réussite* : Justification cohérente de la priorité (commencer par la faille critique exposée sur Internet), réalisme du plan d'action proposé.

- **Démonstration — Lecture et analyse de journaux d'événements (logs)** :
  - *Lien* : Renvoi au script de démonstration `A_scripts_demo.md#demo-6-analyse-logs`.
  - *Description* : Le mentor montre à l'écran un extrait de logs d'authentification (fictif) contenant des centaines de tentatives d'accès échouées en quelques secondes sur le port SSH, suivies d'une connexion réussie. Le mentor aide les apprenants à identifier l'attaque (force brute) et montre comment un analyste SOC utilise ces données pour déclencher une alerte.

## Questions d'interaction (pour stimuler la réflexion)
- "Un scanneur de vulnérabilités automatique détecte-t-il les faiblesses humaines comme la sensibilité des employés à l'ingénierie sociale ? Quel outil utiliser pour cela ?" (Focus limites des outils auto vs pentest/audit de sensibilisation)
- "Pourquoi ne peut-on pas appliquer immédiatement et automatiquement tous les correctifs de sécurité sur tous les serveurs d'une entreprise à la minute où ils sortent ?" (Focus risques de régression applicative ou interruption d'activité)
- "Dans l'analogie d'une maison, à quoi correspondent respectivement les journaux d'événements (logs) et le SIEM ?" (Focus vulgarisation SecOps)

## Articulation avec le projet
- Dans le **Projet Capstone**, les apprenants devront inclure une recommandation opérationnelle sur la mise en place d'une surveillance (externalisation vers un SOC managé) et la création d'un calendrier périodique de gestion des correctifs (patching) pour maintenir le niveau de sécurité à jour.

## Self-paced APRÈS la séance (~90 min) & évaluation formative
- Suivre le module d'auto-formation en ligne sur l'évaluation des vulnérabilités logicielles (CVE et CVSS).
- Réaliser un exercice pratique en ligne de décodage d'alertes de sécurité simplifiées.
- Quiz d'auto-évaluation en ligne (10 questions sur le cycle SecOps et le CVSS).

## Checklist matériel mentor
- [x] Supports de présentation (Slides S06)
- [x] Fiche d'activité A_S06 (Cas de vulnérabilités CVSS)
- [x] Fichier d'exemple de logs fictifs pour la démonstration (dans `A_scripts_demo.md`)
- [x] Outil de partage de tableau blanc interactif
- [x] Support complet de cours en format `.MD` (`A_S06_support.md`)
