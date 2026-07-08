# Spécifications des slides — Session 08 : Grand Atelier d'Audit Interactif & Synthèse
Parcours : A 8 sessions  |  Module : Consolidation & Clôture  |  Format : Spécifications Markdown

---

## Slide 1 : Page de garde
* **Layout** : Titre (Emphase visuelle, fond sombre)
* **Texte affiché sur la slide** :
  * **Grand Atelier d'Audit Interactif & Synthèse**
  * Parcours A — Session 08
  * *Analyser, décider et sécuriser l'entreprise MedDistri*
  * Nom du Mentor / IBM SkillsBuild
* **Notes du présentateur** :
  * Accueillir les apprenants pour cette session finale interactive.
  * Expliquer qu'aucun travail individuel n'est évalué aujourd'hui : nous allons mener un audit collectif en direct via les sondages Livestorm.

---

## Slide 2 : Objectifs de la séance & Sommaire
* **Layout** : Deux colonnes (Gauche : Objectifs, Droite : Sommaire)
* **Texte affiché sur la slide** :
  * **Nos objectifs aujourd'hui** :
    * Mener l'audit de sécurité interactif de MedDistri.
    * Voter les priorités de remédiation technique (MFA, VPN, Sauvegarde).
    * Calculer le Score de Résilience Cyber final de l'entreprise.
    * Synthétiser les notions clés du parcours A.
  * **Sommaire de la séance** :
    * 1. Lancement de l'Atelier d'Audit MedDistri (10 min)
    * 2. Phase décisionnelle & Sondages interactifs (45 min)
    * 3. Débriefing technique & Schéma cible (15 min)
    * 4. Synthèse globale & Certifications IBM SkillsBuild (20 min)

---

## Slide 3 : Contexte de MedDistri
* **Layout** : Contenu structuré (Les vulnérabilités initiales)
* **Texte affiché sur la slide** :
  * **MedDistri : PME de 25 salariés (Matériel médical)**
  * *Les faiblesses identifiées :*
    * **Réseau** : Réseau local plat, pas de cloisonnement.
    * **Accès** : RDP (3389) et SSH (22) ouverts sur le web sans VPN, mots de passe faibles.
    * **Cloud** : Suite Microsoft 365 utilisée sans authentification multifacteur (MFA).
    * **Sauvegarde** : Disque USB connecté en permanence au serveur de fichiers.
    * **Données** : Pas de registre RGPD pour les fichiers clients.
* **Notes du présentateur** :
  * Présenter le cas d'usage. Notre objectif collectif est de faire passer le score de résilience de MedDistri de 10% à plus de 80%.

---

## Slide 4 : Sondage 1 — Sécurisation des accès d'administration
* **Layout** : Interactif (Sondage Livestorm)
* **Texte affiché sur la slide** :
  * **Sondage 1 : Ports ouverts sur Internet**
  * *Les ports RDP (3389) et SSH (22) sont ouverts sur l'IP publique de MedDistri. Quelle est la première mesure d'urgence ?*
    * **Choix A** : Installer un antivirus gratuit sur le serveur.
    * **Choix B** : Fermer l'accès direct aux ports, déployer un VPN d'accès distant et activer le MFA *(Bonne réponse)*.
    * **Choix C** : Changer le mot de passe administrateur par un mot de passe complexe de 20 caractères.
* **Notes du présentateur** :
  * Lancer le sondage sur Livestorm. Laisser 1 minute.
  * Débriefer : Changer le mot de passe ne suffit pas face aux failles Zero-day RDP. Seul le VPN avec MFA sécurise l'accès.

---

## Slide 5 : Sondage 2 — Protection Microsoft 365
* **Layout** : Interactif (Sondage Livestorm)
* **Texte affiché sur la slide** :
  * **Sondage 2 : Activation du MFA**
  * *La direction craint que le MFA ne ralentisse la productivité des commerciaux. Comment argumenter ?*
    * **Choix A** : Expliquer que le MFA bloque 99% des piratages de comptes Microsoft et protège contre le vol de données clients *(Bonne réponse)*.
    * **Choix B** : Rendre obligatoire un mot de passe complexe de 30 caractères sans MFA.
    * **Choix C** : Ne rien changer car les commerciaux refusent la contrainte.

---

## Slide 6 : Sondage 3 — Politique de sauvegarde
* **Layout** : Interactif (Sondage Livestorm)
* **Texte affiché sur la slide** :
  * **Sondage 3 : Sauvegarde USB branchée en permanence**
  * *Pourquoi cette méthode est-elle particulièrement vulnérable ?*
    * **Choix A** : Le disque USB chauffe trop vite.
    * **Choix B** : En cas de ransomware, le disque USB connecté sera également chiffré par le malware *(Bonne réponse)*.
    * **Choix C** : La sauvegarde manuelle prend trop de temps.
* **Notes du présentateur** :
  * Expliquer la règle de sauvegarde 3-2-1.

---

## Slide 7 : Schéma réseau cible MedDistri
* **Layout** : Schéma technique / Tableau blanc
* **Texte affiché sur la slide** :
  * **La segmentation réseau recommandée**
  * *Schéma cible :*
    * **LAN Admin** (Isolé) : Données RH et comptables.
    * **DMZ** (Zone Démilitarisée) : Serveurs accessibles.
    * **WAN** (Internet) : Filtré par un pare-feu NGFW.
    * **VPN d'accès distant** : Chiffré et protégé par MFA pour les commerciaux.
* **Notes du présentateur** :
  * Dessiner en direct ou commenter le schéma de flux réseau sécurisé.

---

## Slide 8 : Synthèse du parcours A
* **Layout** : Récapitulatif thématique
* **Texte affiché sur la slide** :
  * **Ce que vous maîtrisez désormais :**
    * **Module 1 & 2** : Triade CIA, surface d'exposition, phishing.
    * **Module 3 & 4** : Pare-feux, DMZ, VPN, MFA, Sauvegarde 3-2-1, Cloud.
    * **Module 5 & 6** : PSSI, RGPD, score CVSS, vulnérabilités.
    * **Module 7** : Confinement, Forensics, réponse aux incidents.
* **Notes du présentateur** :
  * Féliciter les apprenants. Demander à chacun d'écrire sa notion clé préférée dans le chat.

---

## Slide 9 : Célébration & Certifications
* **Layout** : Célébration
* **Texte affiché sur la slide** :
  * **Félicitations pour votre réussite !**
  * *Obtention de vos badges de compétences.*
  * **Prochaines étapes :**
    * 1. Valider vos quiz sur la plateforme IBM SkillsBuild.
    * 2. Demander votre badge numérique officiel de fin de parcours.
    * 3. Partager votre réussite sur LinkedIn !
* **Notes du présentateur** :
  * Montrer la procédure pour réclamer le badge sur la plateforme.

---

## Slide 10 : Clôture générale
* **Layout** : Remerciements et ressources
* **Texte affiché sur la slide** :
  * **Pour continuer à vous former :**
    * SecNumAcadémie (MOOC gratuit de l'ANSSI).
    * Bulletins d'actualités Cybermalveillance.gouv.fr.
  * **Merci à tous pour votre assiduité et vos échanges !**
