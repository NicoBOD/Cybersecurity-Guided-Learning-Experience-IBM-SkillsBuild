# Parcours A — Session 02 : Menaces, attaques & ingénierie sociale
Module : Menaces  |  Durée : 90 min  |  Parcours : A 8 sessions

## Objectifs pédagogiques (4, verbes d'action)
- **Classifier** les principales familles de codes malveillants (*malware* : rançongiciels, chevaux de Troie, logiciels espions) selon leurs modes de fonctionnement.
- **Reconnaître** les indices de suspicion d'une tentative d'hameçonnage (*phishing*) par e-mail, SMS (*smishing*) ou téléphone (*vishing*).
- **Décrire** les grandes étapes d'une intrusion informatique en s'appuyant sur le concept simplifié de chaîne d'attaque (*cyber kill chain*).
- **Identifier** les biais psychologiques (urgence, peur, autorité, appât du gain) exploités par les attaquants lors d'une manipulation d'ingénierie sociale.

## Prérequis
- Sessions précédentes : A1 (paysage cyber, CIA).
- Self-paced AVANT la séance (~60 min) : Module d'auto-formation en ligne sur les types de logiciels malveillants courants et visionnage d'une courte vidéo explicative sur l'ingénierie sociale.

## Découpage temporel (90 min)
| Min | Segment | Format | Support |
|-----|---------|--------|---------|
| 0–5 | Accueil & introduction des thèmes du jour | Plénière | Slide titre & objectifs |
| 5–15 | Rappel interactif : Analyse rapide de SMS suspects en direct | Interactif | Partage d'écran / Exemples réels |
| 15–35 | Apport de contenu 1 : Typologie des malwares et introduction à la Cyber Kill Chain | Exposé participatif | Slides classification & schéma chaîne d'attaque |
| 35–55 | Activité 1 : Chasse aux e-mails de phishing suspects | Travail en binôme (breakout rooms) | Fiche d'activité A_S02 |
| 55–75 | Apport de contenu 2 : Les leviers psychologiques de l'ingénierie sociale + Démo 2 | Exposé + Démo narrative | Slides psychologie + Script démo audio |
| 75–85 | Quiz interactif & Session de Questions/Réponses (Q&A) | Interactif | Banque de quiz (Thème A2) |
| 85–90 | Synthèse, rappel des messages clés & devoirs pour A3 | Plénière | Slide de clôture & devoirs |

## Activités détaillées
- **Activité 1 — Chasse au phishing (Hameçonnage)** :
  - *Objectif* : Détecter les signaux faibles (anomalies) présents dans des courriels ou messages malveillants réels (anonymisés).
  - *Consignes pas-à-pas* :
    1. Organiser les apprenants en binômes.
    2. Fournir aux binômes un dossier de 4 captures d'écran de messages réels (2 tentatives de phishing, 1 message légitime mais maladroit, 1 spearphishing ciblé).
    3. Les apprenants doivent analyser les messages et lister pour chacun : l'expéditeur réel, l'adresse des liens cachés, les fautes de syntaxe, l'appel à l'action suspect et le levier psychologique utilisé.
    4. Mettre en commun les réponses en demandant à deux binômes de présenter leurs trouvailles pour les cas les plus difficiles.
  - *Livrable attendu* : Une fiche d'analyse identifiant les messages malveillants et explicitant les indices de fraude repérés.
  - *Durée* : 20 minutes (13 min de recherche, 7 min de restitution).
  - *Modalité* : Travail à deux (salle virtuelle ou voisin de table).
  - *Critères de réussite* : Identification sans erreur des 3 messages frauduleux, description correcte d'au moins 3 anomalies par message suspect.

- **Démonstration — Scénario d'ingénierie sociale par vishing (téléphone)** :
  - *Lien* : Renvoi au script de démonstration `A_scripts_demo.md#demo-2-vishing-scenario`.
  - *Description* : Le mentor joue de manière narrative ou simule (avec un apprenant volontaire) un appel de vishing où un faux conseiller technique utilise l'urgence et la peur d'un piratage bancaire pour extorquer un code MFA. Permet de faire prendre conscience du réalisme des manipulations vocales sans exiger d'outils informatiques.

## Questions d'interaction (pour stimuler la réflexion)
- "Si un e-mail provenant apparemment de votre direction générale vous demande de réaliser un virement confidentiel urgent sous peine de bloquer un contrat majeur, comment réagissez-vous ?" (Focus levier d'autorité)
- "Les logiciels antivirus suffisent-ils à bloquer une cyberattaque si un collaborateur donne volontairement son mot de passe au téléphone ?" (Focus facteur humain)
- "Pourquoi la phase de reconnaissance (1ère étape de la Kill Chain) est-elle essentielle pour que l'attaquant réussisse son ingénierie sociale ?" (Focus lien de progression)

## Articulation avec l'atelier de fin de parcours
- Cette session fournit les briques sur le facteur humain pour l'Atelier d'Audit Interactif MedDistri. Les apprenants y mobilisent les contre-mesures face à l'ingénierie sociale pour conseiller la directrice.

## Self-paced APRÈS la séance (~120 min) & évaluation formative
- Suivre le module interactif sur la sensibilisation à la sécurité et à la détection de l'ingénierie sociale.
- Quiz d'auto-évaluation en ligne (10 questions de type scénarios d'attaque).
- Exercice pratique individuel : inspecter sa propre boîte de messagerie (personnelle ou académique) et signaler au mentor un exemple réel suspect reçu récemment.

## Checklist matériel mentor
- [x] Supports de présentation (Slides S02)
- [x] Dossier d'images d'e-mails de test pour la chasse au phishing
- [x] Script d'animation audio pour la démo vishing (dans `A_scripts_demo.md`)
- [x] Outil de sondage interactif
- [x] Support complet de cours en format `.MD` (`A_S02_support.md`)
