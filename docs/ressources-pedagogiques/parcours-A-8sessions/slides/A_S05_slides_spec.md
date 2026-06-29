# Spécifications des slides — Session 05 : Gouvernance, risque, conformité & vie privée
Parcours : A 8 sessions  |  Module : GRC & Vie Privée  |  Format : Spécifications Markdown

---

## Slide 1 : Page de garde
* **Layout** : Titre (Emphase visuelle, fond sombre)
* **Texte affiché sur la slide** :
  * **Gouvernance, Risque, Conformité & Vie Privée**
  * Parcours A — Session 05
  * *Organiser la cybersécurité : des lois aux choix stratégiques d'entreprise*
  * Nom du Mentor / IBM SkillsBuild
* **Visuels suggérés** : Graphique symbolisant la justice ou l'organisation (colonnes grecques stylisées de manière moderne, engrenages de conformité imbriqués). Logo officiel dans un angle.
* **Notes du présentateur** :
  * Accueillir les apprenants.
  * Faire la transition avec la session A4 (où nous avons vu le cloud et les sauvegardes). Expliquer qu'aujourd'hui nous prenons de la hauteur : comment la direction d'une entreprise structure sa sécurité et s'assure du respect des lois.

---

## Slide 2 : Objectifs de la séance & Sommaire
* **Layout** : Deux colonnes (Gauche : Objectifs, Droite : Sommaire)
* **Texte affiché sur la slide** :
  * **Nos objectifs aujourd'hui** :
    * Distinguer la gouvernance cyber et comprendre le rôle de la PSSI.
    * Connaître les référentiels de sécurité (ISO 27001 et NIST CSF).
    * Calculer et prioriser les risques cyber via une matrice qualitative 4x4.
    * Expliquer les obligations majeures du RGPD en matière de vie privée.
  * **Sommaire de la séance** :
    * 1. Brise-glace : Le coût du non-respect (10 min)
    * 2. Gouvernance cyber : La PSSI, ISO 27001 & NIST CSF (20 min)
    * 3. Gestion des risques : Matrice et traitement (20 min)
    * 4. Activité pratique 1 : Audit de risque PME (20 min)
    * 5. Protection des données : Le RGPD (10 min)
    * 6. Quiz de session & Debriefing (10 min)
* **Visuels suggérés** : Icônes cibles pour les objectifs et icône de liste pour le sommaire.
* **Notes du présentateur** :
  * Présenter les objectifs en montrant que la GRC permet de justifier les dépenses de sécurité (le "pourquoi" et non plus seulement le "comment").

---

## Slide 3 : Rappel & Brise-glace interactif
* **Layout** : Plein écran interactif
* **Texte affiché sur la slide** :
  * **Brise-glace : Le prix d'une fuite de données**
  * *À votre avis, quelle amende maximale une autorité comme la CNIL peut-elle infliger à une entreprise en cas de non-respect grave du RGPD ?*
    * A. 10 000 euros
    * B. 100 000 euros
    * C. Jusqu'à 20 millions d'euros ou 4% du chiffre d'affaires mondial
  * *Quelles peuvent être les autres conséquences pour l'entreprise ?*
* **Visuels suggérés** : Photo ou icône d'un marteau de justice sur fond sombre.
* **Notes du présentateur** :
  * Laisser 3 minutes de débat.
  * Révéler la bonne réponse (Réponse C). Préciser que même si la CNIL cherche d'abord à accompagner, les amendes peuvent être fatales pour une PME.
  * Rebondir sur les autres conséquences : perte de confiance des clients, mauvaise réputation dans la presse, etc.

---

## Slide 4 : La Gouvernance Cyber : PSSI & ISO 27001
* **Layout** : Deux colonnes
* **Texte affiché sur la slide** :
  * **La PSSI : La Constitution Cyber de l'entreprise**
    * Rédigée par le RSSI, validée et signée par la direction.
    * Elle fixe les règles obligatoires pour tous les collaborateurs (mots de passe, usage du matériel professionnel, gestion des accès).
  * **ISO 27001 : Amélioration continue (SMSI)**
    * Norme internationale de management de la sécurité.
    * Repose sur le cycle PDCA (Planifier, Déployer, Contrôler, Ajuster).
    * Garantit aux partenaires que la sécurité est auditée et gérée de manière dynamique.
* **Visuels suggérés** : Schéma du cycle PDCA (roue de Deming) adapté à la sécurité. Icône de document officiel avec sceau.
* **Notes du présentateur** :
  * Expliquer qu'un Système de Management de la Sécurité de l'Information (SMSI) est un cadre organisationnel.
  * Insister sur le fait que la PSSI a valeur juridique en entreprise (règlement intérieur).

---

## Slide 5 : Le NIST CSF (Cybersecurity Framework)
* **Layout** : Cinq colonnes horizontales ou verticales
* **Texte affiché sur la slide** :
  * **NIST CSF : Les 5 piliers de la résilience cyber**
  * **1. Identifier** : Cartographier les actifs, logiciels et risques.
  * **2. Protéger** : Déployer les barrières (chiffrement, accès, formation).
  * **3. Détecter** : Surveiller en continu (logs, alertes).
  * **4. Répondre** : Réagir en cas d'attaque (isolement, communication).
  * **5. Récupérer** : Restaurer les services et tirer les leçons.
* **Visuels suggérés** : Représentation graphique en 5 blocs de couleur distincts, chacun portant le nom d'un pilier NIST (Identifier en gris, Protéger en bleu, Détecter en jaune, Répondre en orange, Récupérer en vert).
* **Notes du présentateur** :
  * Expliquer que le NIST CSF est très populaire car extrêmement opérationnel et facile à traduire en projets techniques concrets.
  * Montrer la complémentarité avec l'ISO 27001 (l'un structure le management, l'autre structure l'action).

---

## Slide 6 : Évaluer le risque : Matrice 4x4
* **Layout** : Contenu structuré avec graphique/tableau
* **Texte affiché sur la slide** :
  * **L'évaluation qualitative du risque**
  * **Criticité = Vraisemblance (1 à 4) × Impact (1 à 4)**
  * *La matrice de cotation des risques :*
    * **Impact** : Négligeable (1), Modéré (2), Majeur (3), Critique (4).
    * **Vraisemblance** : Très rare (1), Improbable (2), Probable (3), Presque certain (4).
  * *Les 4 stratégies de traitement du risque :*
    * **Réduire** (sécuriser) | **Transférer** (assurance) | **Éviter** (supprimer l'activité) | **Accepter** (assumer).
* **Visuels suggérés** : Grille colorée 4x4 (matrice qualitative avec dégradé vert ➔ jaune ➔ rouge) indiquant les criticités brutes.
* **Notes du présentateur** :
  * Détailler la formule mathématique simple de la criticité.
  * Donner un exemple concret pour illustrer chaque stratégie de traitement (ex. installer un pare-feu = réduire ; s'assurer contre le vol de données = transférer).

---

## Slide 7 : Le RGPD & la Vie Privée
* **Layout** : Deux colonnes
* **Texte affiché sur la slide** :
  * **RGPD : Règlement Général sur la Protection des Données**
  * *4 règles fondamentales pour chaque traitement de données :*
    * **1. Finalité précise** : On collecte pour un besoin défini, pas "au cas où".
    * **2. Minimisation** : Uniquement les données strictement nécessaires.
    * **3. Consentement & Transparence** : L'utilisateur doit accepter activement et être informé.
    * **4. Respect des droits** : Droit d'accès, de modification et de suppression définitive ("droit à l'oubli").
* **Visuels suggérés** : Icône de bouclier étoilé européen ou de carte d'identité protégée.
* **Notes du présentateur** :
  * Expliquer la notion de donnée personnelle (toute information permettant d'identifier directement ou indirectement une personne physique).
  * Préciser que le RGPD s'applique aux entreprises du monde entier dès lors qu'elles traitent des données de résidents européens.

---

## Slide 8 : Activité 1 — Registre des risques d'une PME
* **Layout** : Consignes de travail (Activité pratique)
* **Texte affiché sur la slide** :
  * **Activité 1 : Audit et traitement des risques d'une PME**
  * *Étude de cas :*
    * Une PME stocke ses 10 000 coordonnées clients sur un ordinateur connecté sans antivirus à jour, avec le mot de passe "123456".
  * **Travail à réaliser en groupe :**
    * 1. Évaluer la vraisemblance (1-4) et l'impact (1-4) du vol de ce fichier.
    * 2. Calculer la criticité brute.
    * 3. Proposer 3 mesures de réduction de ce risque.
  * **Consignes** : 15 min en sous-salle. Remplissez le registre de risques partagé.
* **Visuels suggérés** : Extrait de tableau de registre de risques vierge. Minuteur visuel de 15 minutes.
* **Notes du présentateur** :
  * Envoyer les apprenants dans les sous-salles virtuelles.
  * S'assurer qu'ils utilisent bien la matrice 4x4 vue précédemment.
  * Au retour en plénière, confronter les notes de criticité obtenues et valider les plans d'action (mots de passe, antivirus, chiffrement).

---

## Slide 9 : Quiz live & Validation
* **Layout** : Contenu interactif (Quiz)
* **Texte affiché sur la slide** :
  * **Vrai ou Faux ?**
  * 1. *La PSSI d'une entreprise a valeur de règlement intérieur.* ➔ **[Vrai / Faux ?]**
  * 2. *Transférer un risque signifie que le risque disparaît du système.* ➔ **[Vrai / Faux ?]**
  * 3. *Le principe de minimisation consiste à collecter le moins de données personnelles possibles pour un but donné.* ➔ **[Vrai / Faux ?]**
* **Visuels suggérés** : Code QR Kahoot/Wooclap de la session.
* **Notes du présentateur** :
  * Lancer les questions de la banque de quiz. Debriefer les résultats.
  * *Réponses* : 1. Vrai ; 2. Faux (il est partagé avec un tiers, comme l'assureur, mais l'impact opérationnel demeure) ; 3. Vrai.

---

## Slide 10 : Clôture & Devoirs
* **Layout** : Fin de session / Devoirs
* **Texte affiché sur la slide** :
  * **Vos devoirs avant la prochaine séance (Self-paced)** :
    * Suivre le module IBM SkillsBuild : *Opérations de sécurité, surveillance et gestion des logs*.
    * Durée estimée : ~70 min.
    * Exercice individuel : Consulter la politique de confidentialité de l'un de vos services en ligne habituels et relever les finalités d'usage de vos données personnelles.
  * **Prochaine séance** : *Opérations de sécurité & gestion des vulnérabilités (A6)*.
  * Merci pour votre investissement !
* **Visuels suggérés** : Logo IBM SkillsBuild. Icône de cadenas RGPD.
* **Notes du présentateur** :
  * Saluer et encourager les apprenants.
  * Répondre aux dernières questions s'il y en a.
  * Fermer la session synchrone.
