# Énoncé du Projet Capstone — Parcours A (8 sessions)
Parcours : A 8 sessions  |  Module : Consolidation  |  Format : Guide de projet

---

## 1. Contexte de l'entreprise : "MedDistri"

Vous êtes consultant junior en cybersécurité pour le cabinet "CyberSûr". Vous venez de décrocher une mission d'évaluation auprès de **MedDistri**, une PME de 25 salariés spécialisée dans la distribution de matériel médical (pansements, masques, petits instruments) pour les cliniques et hôpitaux.

### L'infrastructure informatique de MedDistri :
* **Effectifs** : 15 commerciaux en télétravail ou déplacement régulier, 5 personnes en logistique (entrepôt), 4 personnes en administration (RH, compta, direction) et 1 technicien informatique polyvalent jouant le rôle d'administrateur système de manière informelle.
* **Systèmes locaux** : Un serveur de fichiers physique situé dans un placard à balai dans l'entrepôt. Il stocke les dossiers administratifs, la comptabilité et les fichiers de propriété industrielle de l'entreprise (plans de produits, brevets).
* **Accès distant** : Pour accéder au serveur à distance, le technicien a configuré un accès ouvert sur Internet sur le port 22 (SSH) et le port 3389 (Bureau à distance Windows) sans restriction d'adresses IP. Le mot de passe du compte administrateur est `Admin@MedDistri2025`.
* **Services Cloud** : L'entreprise utilise la suite Microsoft 365 pour les courriels, Teams et le partage de documents commerciaux sur OneDrive. L'authentification multifacteur (MFA) n'est pas activée car les utilisateurs trouvent cela "trop lourd au quotidien".
* **Sauvegardes** : Le technicien informatique effectue une sauvegarde manuelle de la base de données de ventes chaque vendredi soir sur un disque dur externe branché en permanence au serveur de l'entrepôt.
* **Sécurité & Vie Privée** : L'entreprise n'a pas de Politique de Sécurité des Systèmes d'Information (PSSI) écrite ni de registre de traitement des données RGPD, bien qu'elle gère des fichiers contenant des données nominatives de ses clients (médecins, directeurs de cliniques) et les historiques de commandes.

---

## 2. Votre Mission

En groupes de **3 à 4 apprenants**, vous devez réaliser l'audit de sécurité simplifié de MedDistri et proposer un plan d'action d'hygiène cyber réaliste et pragmatique. Votre livrable doit être adapté à la taille de la structure (PME) et compréhensible pour sa directrice générale, Mme Legrand, qui n'a pas de profil informatique.

---

## 3. Livrables Attendus

### Livrable 1 : Le Rapport d'Audit écrit (format PDF / Markdown)
Votre rapport de 3 à 5 pages devra comprendre les quatre sections suivantes :
1. **Executive Summary (Synthèse managériale)** : Un résumé de 500 mots maximum vulgarisé à l'attention de Mme Legrand, décrivant la situation, le risque financier global de faillite en cas d'attaque, et le coût estimé de vos recommandations de base.
2. **Analyse de risques** : L'identification de 3 risques prioritaires sous forme de tableau, cotés selon la formule $C = V \times I$ (Matrice 4x4 apprise en session 5). Chaque risque doit être décrit en termes de Menace, Vulnérabilité et Impact.
3. **Diagnostic technique et organisationnel** :
   * Analyse critique de l'architecture d'accès à distance (ports 22 et 3389).
   * Analyse critique de la politique de sauvegarde face à la menace des rançongiciels.
   * Évaluation de la conformité RGPD (fichiers clients).
4. **Feuille de route de remédiation** : Une chronologie claire divisée en trois étapes :
   * *Court terme (Mois 1 — Budget quasi-nul)* : Actions immédiates d'urgence.
   * *Moyen terme (Mois 2-3 — Investissements de base)* : Projets d'infrastructure et d'IAM.
   * *Long terme (Mois 6+ — Consolidation)* : Suivi, formation et audits.

### Livrable 2 : Présentation de soutenance (5 Diapositives)
Un jeu de diapositives structuré pour un pitch de **10 minutes strictes** :
* Slide 1 : Titre et contexte de MedDistri.
* Slide 2 : La matrice des 3 risques majeurs identifiés.
* Slide 3 : Recommandations techniques urgentes (MFA, VPN, ports).
* Slide 4 : Règle de sauvegarde 3-2-1 et plan d'hygiène informatique.
* Slide 5 : Feuille de route chronologique et argumentaire face aux objections de productivité.

---

## 4. Modalités de la soutenance (Session 08)

* **Le Pitch** : Chaque équipe dispose de **10 minutes** de présentation orale. Tous les membres du groupe doivent prendre la parole de manière équilibrée.
* **Questions-Réponses** : 10 minutes de questions posées par le mentor (qui joue le rôle de Mme Legrand) et par les autres apprenants de la classe.
* **Évaluation par les pairs** : Chaque apprenant devra remplir une grille d'évaluation constructive pour deux autres groupes.
