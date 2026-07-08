# Parcours A — Session 04 : Sécurité du cloud, des données & des identités
Module : Cloud, Données & Identités  |  Durée : 90 min  |  Parcours : A 8 sessions

## Objectifs pédagogiques (4, verbes d'action)
- **Appliquer** le principe du moindre privilège lors de la définition de rôles et d'accès utilisateurs au sein d'une organisation.
- **Distinguer** la répartition des rôles de sécurité entre le client et le fournisseur dans le modèle de responsabilité partagée du *cloud*.
- **Expliquer** la différence entre le chiffrement des données au repos (*at rest*) et le chiffrement en transit (*in transit*).
- **Concevoir** une politique de sauvegarde de données résiliente en appliquant de manière stricte la règle 3-2-1.

## Prérequis
- Sessions précédentes : A1, A2, A3.
- Self-paced AVANT la séance (~60 min) : Module SkillsBuild sur les bases du Cloud Computing (modèles IaaS, PaaS, SaaS) et les bases de la gestion des identités.

## Découpage temporel (90 min)
| Min | Segment | Format | Support |
|-----|---------|--------|---------|
| 0–5 | Accueil, logistique & présentation de la séance | Plénière | Slide titre & objectifs |
| 5–15 | Débat participatif : "Mot de passe fort : humain vs machine" | Interactif | Tableau blanc / Échanges libres |
| 15–35 | Apport de contenu 1 : IAM, moindre privilège, MFA & gestionnaires de mots de passe | Exposé interactif | Slides IAM, moindre privilège & MFA |
| 35–55 | Activité 1 : Construction d'une matrice d'accès RBAC | Travail en binôme | Fiche d'activité A_S04 (Matrice de rôles) |
| 55–75 | Apport de contenu 2 : Chiffrement, responsabilité partagée cloud & règle 3-2-1 | Exposé structuré | Slides responsabilité, chiffrement & sauvegarde |
| 75–85 | Démo 4 : Gestion des identités & MFA + Quiz interactif | Démo + Quiz live | Script de démo & Banque de quiz (Thème A4) |
| 85–90 | Clôture de la session, consignes du self-paced et devoirs | Plénière | Slide de fin & devoirs |

## Activités détaillées
- **Activité 1 — Construction d'une matrice d'accès RBAC (Role-Based Access Control)** :
  - *Objectif* : Structurer la gestion des droits d'accès logiques d'une PME en appliquant le principe du moindre privilège.
  - *Consignes pas-à-pas* :
    1. Regrouper les apprenants en binômes.
    2. Fournir aux apprenants la liste des utilisateurs d'une PME fictive (ex. Commercial, Responsable RH, Technicien Support, Directeur Financier) et les dossiers partagés sur leur espace de stockage cloud (ex. Dossier Contrats, Dossier Salaires, Fiches Techniques Clients, Rapports Comptables).
    3. Les apprenants doivent compléter un tableau à double entrée (matrice d'accès) en définissant les droits de chaque rôle (Lecture seule - L, Écriture/Lecture - E/L, Aucun accès - X) pour chaque dossier.
    4. Demander à chaque binôme de justifier le droit d'accès attribué ou refusé pour au moins deux rôles.
  - *Livrable attendu* : Une matrice de droits logiques dûment complétée et justifiée.
  - *Durée* : 20 minutes (12 min de travail pratique, 8 min de débriefing).
  - *Modalité* : Travail en binôme.
  - *Critères de réussite* : Application rigoureuse du moindre privilège (ex. interdire l'accès au dossier RH et Comptabilité pour le Commercial et le Technicien Support ; n'accorder que le strict nécessaire).

- **Démonstration — Configuration et gestion sécurisée des identités** :
  - *Lien* : Renvoi au script de démonstration `A_scripts_demo.md#demo-4-gestion-identites`.
  - *Description* : Le mentor démontre comment fonctionne l'authentification multifacteur (MFA) à l'aide d'une application d'authentification (générant des codes à usage unique - OTP) et comment un gestionnaire de mots de passe permet de créer, stocker et remplir automatiquement des identifiants complexes sans avoir à s'en souvenir.

## Questions d'interaction (pour stimuler la réflexion)
- "Si un pirate parvient à usurper les identifiants d'accès du directeur financier sur un service SaaS (ex. Office 365/Google Workspace) faute de MFA, qui est responsable de l'intrusion : Microsoft/Google ou l'entreprise ?" (Focus modèle de responsabilité partagée cloud)
- "Pourquoi n'est-il pas recommandé de sauvegarder les fichiers de travail d'un ordinateur de bureau uniquement sur un disque dur externe branché en permanence en USB sur cette même machine ?" (Focus résilience face aux rançongiciels et règle 3-2-1)
- "Quelle est la différence concrète entre chiffrer un e-mail en transit (TLS) et chiffrer un fichier de base de données au repos sur un disque dur ?" (Focus transit vs repos)

## Articulation avec l'atelier de fin de parcours
- Cette session apporte la dimension "Identité & Données" de l'Atelier d'Audit Interactif MedDistri. Les notions de MFA, VPN et de règle de sauvegarde 3-2-1 y sont testées lors des choix décisionnels.

## Self-paced APRÈS la séance (~90 min) & évaluation formative
- Suivre le module sur la gestion des identités, le contrôle des accès dans les infrastructures cloud et la protection des données.
- Configurer à titre d'exercice d'application personnelle un gestionnaire de mots de passe gratuit et activer la MFA sur l'un de ses comptes personnels.
- Quiz d'auto-évaluation en ligne (10 questions de type scénarios sur la cryptographie de base, le cloud et la sauvegarde).

## Checklist matériel mentor
- [x] Supports de présentation (Slides S04)
- [x] Fiche d'activité A_S04 (Scénario de PME pour la matrice RBAC)
- [x] Script de démo d'outils d'authentification (dans `A_scripts_demo.md`)
- [x] Outil de dessin / tableau partagé pour la restitution de la matrice
- [x] Support complet de cours en format `.MD` (`A_S04_support.md`)
