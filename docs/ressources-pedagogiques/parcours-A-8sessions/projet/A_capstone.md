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

---

## 5. Alternative d'animation interactive (Spécial Webinaire / Livestorm)

Si le cours est animé sous forme de webinaire interactif devant un public nombreux ou passif, la soutenance classique en groupe est remplacée par un **atelier d'audit interactif collectif** mené par le mentor.

### Fonctionnement de l'atelier :
Le mentor prend le rôle d'auditeur principal de MedDistri. Il partage son écran et déroule le diagnostic technique sous forme de scénario décisionnel. Pour chaque problème identifié, le mentor lance un sondage Livestorm auprès du public.

### Liste des Sondages à soumettre au public :

1. **Sondage 1 : L'accès distant vulnérable**
   * *Question :* Les ports SSH (22) et RDP (3389) de MedDistri sont ouverts à tous vents sur Internet. Quelle est la première mesure d'urgence à appliquer ?
     * A) Installer un antivirus gratuit sur le serveur.
     * B) Fermer les ports sur Internet et mettre en œuvre un accès VPN protégé par MFA *(Bonne réponse)*.
     * C) Modifier le mot de passe administrateur par un mot de passe de 20 caractères.
     * D) Ne rien changer pour ne pas perturber les commerciaux.
2. **Sondage 2 : La politique de sauvegarde**
   * *Question :* Le disque dur externe de sauvegarde est branché en permanence sur le serveur local de MedDistri. Quel est le risque majeur en cas d'attaque de type ransomware ?
     * A) Le disque dur externe peut être volé physiquement.
     * B) Les fichiers de sauvegarde présents sur le disque connecté seront également chiffrés par le ransomware *(Bonne réponse)*.
     * C) La sauvegarde va saturer le disque dur trop rapidement.
3. **Sondage 3 : L'authentification M365**
   * *Question :* La direction refuse le MFA sur Office 365, affirmant que c'est "trop contraignant". Quel argument est le plus adapté ?
     * A) Rappeler que le MFA bloque plus de 99% des attaques par usurpation de compte et évite une paralysie totale *(Bonne réponse)*.
     * B) Désactiver tous les comptes pour forcer le respect des consignes.
     * C) Recommander des mots de passe de 30 caractères sans MFA.
4. **Sondage 4 : Priorisation du budget**
   * *Question :* Le budget cyber annuel de MedDistri est limité à 2 000 €. Où devez-vous l'allouer en priorité ?
     * A) Réaliser un test d'intrusion par un cabinet externe.
     * B) Activer le MFA gratuit, souscrire à une solution de sauvegarde cloud immuable externe et former les utilisateurs *(Bonne réponse)*.
     * C) Embaucher un RSSI externe à temps partiel.

### Débriefing par le mentor :
Après chaque vote, le mentor analyse en direct les statistiques de réponse du public (ex. *"Vous êtes 80% à avoir voté pour le VPN avec MFA, et vous avez tout à fait raison : ouvrir RDP directement sur Internet équivaut à laisser la porte de l'entrepôt grande ouverte avec une pancarte explicative..."*) et fait le lien avec les notions théoriques vues durant le parcours.
