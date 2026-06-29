# Énoncé du Projet Capstone — Parcours B (20 sessions)
Parcours : B 20 sessions  |  Module : Consolidation & Évaluation  |  Format : Guide de projet final

---

## 1. Contexte de l'entreprise : "MedDistri"

Vous êtes consultant senior en cybersécurité pour le cabinet "CyberSûr". Vous êtes mandaté pour réaliser un audit complet et concevoir une stratégie globale de sécurisation pour **MedDistri**, une PME de 25 salariés qui distribue du matériel médical (pansements, instruments chirurgicaux, dispositifs connectés) à des cliniques et hôpitaux.

### L'infrastructure informatique actuelle de MedDistri :
*   **Effectifs et Usages** :
    *   15 commerciaux itinérants sur toute la France, équipés d'ordinateurs portables et de smartphones, se connectant régulièrement à distance depuis des réseaux Wi-Fi publics (hôtels, gares).
    *   5 logisticiens travaillant dans l'entrepôt pour la gestion des stocks et l'expédition.
    *   4 administratifs (RH, Comptabilité, Direction) au siège social.
    *   1 technicien informatique polyvalent assurant le rôle d'administrateur système de manière informelle, sans formation spécifique en sécurité.
*   **Systèmes et Réseau** :
    *   *Réseau local unique* : Pas de segmentation. Les ordinateurs des commerciaux, les ordinateurs de la comptabilité, le serveur de l'entrepôt et les smartphones des visiteurs en Wi-Fi partagent le même réseau local.
    *   *Serveur de fichiers local* : Un serveur physique sous Windows Server stocke les bases de données clients, les contrats commerciaux et la comptabilité dans un local technique non verrouillé.
    *   *Accès externe* : Pour permettre aux commerciaux d'accéder aux données, l'administrateur a ouvert le port 3389 (Remote Desktop Protocol - RDP) et le port 22 (SSH) directement sur Internet sans restriction d'adresses IP. Le mot de passe du compte administrateur est `Admin@MedDistri2025`.
*   **Services Cloud et Données** :
    *   L'entreprise utilise Microsoft 365 pour les e-mails, Teams et SharePoint. Le MFA (authentification multifacteur) n'est pas activé pour "ne pas ralentir le travail des commerciaux".
    *   La base de données contient des données personnelles de santé indirectes (historique des dispositifs médicaux achetés par les cliniques, associés aux coordonnées des médecins responsables).
*   **Sauvegardes** :
    *   Une sauvegarde hebdomadaire manuelle de la base de données est copiée sur un disque dur externe branché en permanence en USB sur le serveur de fichiers local.

---

## 2. Votre Mission

En groupes de **3 à 4 apprenants**, vous devez réaliser l'audit détaillé de l'infrastructure de MedDistri et concevoir un **Plan d'Action de Remédiation et de Résilience** complet. 

Votre proposition doit allier rigueur technique (segmentation, supervision, réponse à incident) et pragmatisme économique d'une PME. Le livrable écrit doit être compréhensible pour la directrice générale, Mme Legrand, tandis que les annexes techniques doivent être directement exploitables par le technicien informatique.

---

## 3. Livrables Attendus

### Livrable 1 : Le Rapport d'Audit et Plan d'Action Écrit (format PDF / Markdown)
Votre rapport de 6 à 10 pages devra comprendre les cinq sections suivantes :

1.  **Executive Summary (Synthèse managériale)** :
    *   Un résumé vulgarisé de 500 mots maximum décrivant le niveau de vulnérabilité actuel de la PME, les risques de faillite ou de sanctions juridiques (RGPD), et les bénéfices de la remédiation.
2.  **Analyse de Risques et Conformité RGPD** :
    *   *Matrice qualitative 4x4* : Identification et cotation brute/résiduelle de **5 risques majeurs** (ex. Ransomware, Fuite de données clients, Compromission d'un compte de facturation, etc.).
    *   *Plan de conformité RGPD* : Analyse des fichiers clients et des obligations légales (rôle du DPO, registre des traitements, mentions légales, politique d'exercice des droits).
3.  **Architecture Réseau Cible et Durcissement** :
    *   *Schéma d'architecture sécurisé (Format Mermaid ou dessin propre)* : Modélisation d'une architecture segmentée avec WAN, LAN administratif, LAN logistique, et une DMZ isolée pour les accès VPN et serveurs exposés.
    *   *Table de flux pare-feu* : Spécification des règles d'accès strictes autorisées entre chaque zone (ports, protocoles, sources, destinations).
    *   *Plan de durcissement* : Mesures de protection des terminaux (*endpoints*), fermeture des accès distants ouverts (ports 22, 3389) et mise en œuvre du MFA.
4.  **Stratégie de Résilience et Réponse aux Incidents** :
    *   *Politique de sauvegarde* : Modélisation de la règle de sauvegarde 3-2-1 (dont une copie immuable ou hors ligne).
    *   *Plan de Continuité et de Reprise d'Activité (PCA/PRA)* : Définition des objectifs de RTO (temps de reprise) et RPO (perte de données acceptable) pour le serveur de commandes.
    *   *Playbook Ransomware* : Fiche d'action réflexe étape par étape pour le confinement, la préservation des preuves techniques (RAM) et l'éradication.
5.  **Feuille de route chronologique et budgétée** :
    *   *Court terme (Mois 1)* : Mesures urgentes à coût quasi-nul (MFA, blocage ports, sauvegardes débranchées, sensibilisation).
    *   *Moyen terme (Mois 2-3)* : Projets techniques (mise en place du VPN, segmentation réseau, DPO externe).
    *   *Long terme (Mois 6+)* : Supervision continue (SIEM/Wazuh léger), audits de vulnérabilités réguliers, exercices de crise.

### Livrable 2 : Présentation de soutenance (5 Diapositives maximum)
Un jeu de diapositives clair et impactant pour un pitch oral de **7 minutes strictes** :

*   *Slide 1* : Contexte, enjeux clés et actifs de MedDistri.
*   *Slide 2* : Synthèse de l'audit et matrice des 5 risques prioritaires.
*   *Slide 3* : Schéma réseau cible et règles d'hygiène fondamentales (MFA, VPN).
*   *Slide 4* : Stratégie de résilience (Sauvegarde 3-2-1, PCA/PRA, Playbook incident).
*   *Slide 5* : Feuille de route opérationnelle (Phasage et budget estimé) et levée des objections de la direction.

---

## 4. Déroulé de l'Évaluation (Session B20)

*   **Le Pitch (7 minutes)** : Présentation orale chronométrée. Chaque membre de l'équipe doit prendre la parole de façon équitable.
*   **Questions-Réponses (8 minutes)** : Le mentor (jouant le rôle de Mme Legrand et d'un auditeur technique) et les autres apprenants interrogent le groupe sur ses choix d'architecture, son budget et ses priorités.
*   **Évaluation croisée** : Chaque groupe évalue les présentations de deux autres équipes en remplissant une grille d'évaluation constructive.
