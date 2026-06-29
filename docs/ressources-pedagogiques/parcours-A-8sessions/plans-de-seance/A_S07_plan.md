# Parcours A — Session 07 : Réponse aux incidents & introduction au forensics
Module : Réponse aux Incidents  |  Durée : 90 min  |  Parcours : A 8 sessions

## Objectifs pédagogiques (4, verbes d'action)
- **Dérouler** les six étapes clés du cycle de réponse aux incidents (Préparation, Identification, Confinement, Éradication, Restauration, Leçons apprises) lors d'un scénario de compromission.
- **Isoler** les traces chronologiques d'une intrusion à partir d'un scénario de logs simplifié pour reconstituer le déroulement de l'attaque.
- **Expliquer** l'importance de la chaîne de contrôle (*chain of custody*) pour préserver la validité légale des preuves numériques en investigation (*forensics*).
- **Distinguer** le cadre légal du piratage éthique par rapport aux intrusions informatiques illégales (selon la législation en vigueur).

## Prérequis
- Sessions précédentes : A1 à A6.
- Self-paced AVANT la séance (~60 min) : Lecture d'un article vulgarisé sur les notions fondamentales de forensics numérique. Découverte du cycle de réponse à incident (modèle NIST ou SANS).

## Découpage temporel (90 min)
| Min | Segment | Format | Support |
|-----|---------|--------|---------|
| 0–5 | Accueil, objectifs & logistique | Plénière | Slide titre & objectifs |
| 5–15 | Activité brise-glace : "Alerte Ransomware à 8h00 du matin !" (Brainstorming) | Interactif | Tableau blanc partagé |
| 15–35 | Apport de contenu 1 : Le cycle de Réponse aux Incidents (IR) | Exposé illustré | Slides phases de réponse à incident |
| 35–55 | Activité 1 : Reconstitution de la timeline d'un incident | Travail en binôme | Fiche d'activité A_S07 (Logs & Chronologie) |
| 55–75 | Apport de contenu 2 : Introduction au Forensics & Cadre légal du Pentesting | Exposé interactif | Slides chain of custody & cadre pénal |
| 75–85 | Démo 7 : Simulation narrative de gestion de crise + Quiz | Démo narrative + Quiz | Script de démo & Banque de quiz (Thème A7) |
| 85–90 | Clôture de la session et consignes pour le Capstone (Session A8) | Plénière | Slide de fin & consignes soutenances |

## Activités détaillées
- **Activité 1 — Reconstitution de la chronologie d'une attaque (Incident Timeline)** :
  - *Objectif* : Analyser des logs et alertes hétérogènes pour ordonner chronologiquement les étapes de l'attaque et localiser l'origine de l'intrusion (patient zéro).
  - *Consignes pas-à-pas* :
    1. Diviser les apprenants en binômes.
    2. Fournir aux apprenants une enveloppe contenant 5 extraits de logs ou alertes mélangés (Alerte 1 : Connexion réussie VPN à 3h00 de l'admin depuis une IP inhabituelle ; Alerte 2 : Détection de trafic anormal sortant vers un site d'archivage à 4h30 ; Alerte 3 : Alerte antivirus à 3h15 sur le poste d'un commercial ; Alerte 4 : Chiffrement massif des partages réseaux à 5h00 ; Alerte 5 : E-mail de phishing reçu par le commercial la veille à 14h00).
    3. Les apprenants doivent ordonner ces 5 événements sur une ligne du temps.
    4. Identifier par écrit le vecteur d'entrée initial (le phishing du commercial) et l'impact final (le chiffrement).
    5. Discuter des actions de confinement immédiates qui auraient pu stopper la chaîne de l'attaque.
  - *Livrable attendu* : Une frise chronologique (timeline) correcte liant les alertes avec identification formelle de l'origine de l'attaque.
  - *Durée* : 20 minutes (12 min de travail sur table, 8 min de correction partagée).
  - *Modalité* : Travail en binôme.
  - *Critères de réussite* : Chronologie 100% exacte, identification correcte du patient zéro (poste du commercial ciblé par phishing).

- **Démonstration — Simulation narrative d'une cellule de crise** :
  - *Lien* : Renvoi au script de démonstration `A_scripts_demo.md#demo-7-incident`.
  - *Description* : Le mentor anime un scénario interactif de type "Livre dont vous êtes le héros". Il présente une situation initiale de crise de sécurité à l'écran et donne deux choix aux apprenants (ex. "Option A : Éteindre immédiatement le serveur touché en coupant l'alimentation", "Option B : Isoler le serveur du réseau en débranchant le câble réseau tout en le laissant allumé"). Le mentor commente en direct les conséquences techniques et juridiques de chaque décision pour illustrer le compromis entre confinement et préservation des preuves en RAM (forensics).

## Questions d'interaction (pour stimuler la réflexion)
- "Pourquoi couper brusquement l'alimentation électrique d'une machine piratée nuit-il gravement à l'investigation numérique ?" (Focus volatilité de la mémoire RAM)
- "Si un expert en cybersécurité découvre une vulnérabilité critique sur le site public de sa banque et décide de l'exploiter pour prouver qu'il dit vrai, que risque-t-il ?" (Focus distinction pénal intrusion légale vs illégale)
- "Que signifie l'expression 'chaîne de contrôle' pour un disque dur saisi lors d'une attaque ?" (Focus intégrité de la preuve)

## Articulation avec le projet
- Dans cette dernière phase avant la soutenance, les apprenants finalisent le plan de réponse aux incidents pour la PME fictive du **Projet Capstone** : qui contacter en cas d'attaque, comment isoler les machines vulnérables et comment tirer les leçons de l'incident.

## Self-paced APRÈS la séance (~120 min) & évaluation formative
- Finaliser les livrables écrits du Projet Capstone (Rapport d'évaluation de sécurité pour la PME).
- Répéter la présentation orale en sous-groupe pour la soutenance de la session A8.
- Quiz d'auto-évaluation en ligne (10 questions théoriques sur la réponse aux incidents et le cadre légal).

## Checklist matériel mentor
- [x] Supports de présentation (Slides S07)
- [x] Fiche d'activité A_S07 (Les 5 cartes événements mélangées)
- [x] Script narratif interactif de crise cyber (dans `A_scripts_demo.md`)
- [x] Grille chronologique vierge à distribuer ou projeter
- [x] Support complet de cours en format `.MD` (`A_S07_support.md`)
