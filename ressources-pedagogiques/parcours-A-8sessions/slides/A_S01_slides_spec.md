# Spécifications des slides — Session 01 : Découverte de la cybersécurité & paysage des menaces
Parcours : A 8 sessions  |  Module : Fondements Cyber  |  Format : Spécifications Markdown

---

## Slide 1 : Page de garde
* **Layout** : Titre (Emphase visuelle, fond sombre)
* **Texte affiché sur la slide** :
  * **Découverte de la Cybersécurité & Paysage des Menaces**
  * Parcours A — Session 01
  * *Bienvenue dans votre formation GLE Cybersécurité*
  * Nom du Mentor / IBM SkillsBuild
* **Visuels suggérés** : Fond bleu nuit profond avec un graphisme discret de réseau interconnecté ou un bouclier numérique stylisé. Logo officiel dans un angle.
* **Notes du présentateur** :
  * Accueillir chaleureusement les apprenants à leur arrivée.
  * Se présenter rapidement (parcours professionnel dans le domaine).
  * Rappeler la logistique générale : durée (90 min), règles de prise de parole (main levée, chat) et usage constructif des outils.
  * Valider que tout le monde entend correctement et voit le partage d'écran.

---

## Slide 2 : Objectifs de la séance & Sommaire
* **Layout** : Deux colonnes (Gauche : Objectifs, Droite : Sommaire)
* **Texte affiché sur la slide** :
  * **Nos objectifs aujourd'hui** :
    * Définir les piliers de la triade CIA.
    * Situer la sécurité offensive par rapport à la sécurité défensive.
    * Identifier les profils d'attaquants modernes et leurs motivations.
    * Comprendre les enjeux de la surface d'exposition d'une entreprise.
  * **Sommaire de la séance** :
    * 1. Brise-glace : Le mot "sécurité" pour vous (10 min)
    * 2. Les fondations : La Triade CIA (20 min)
    * 3. Activité pratique 1 : Détective CIA (20 min)
    * 4. Les acteurs de la menace & Surface d'exposition (20 min)
    * 5. Démo 1 : Découvrir sa surface publique (10 min)
    * 6. Quiz & Synthèse (10 min)
* **Visuels suggérés** : Icônes cibles pour les objectifs et icône de liste ordonnée pour le sommaire.
* **Notes du présentateur** :
  * Présenter les objectifs en insistant sur le fait qu'aucun prérequis technique n'est nécessaire.
  * Parcourir l'agenda rapidement pour rassurer sur le rythme de la session synchrone.

---

## Slide 3 : Brise-glace interactif
* **Layout** : Plein écran interactif
* **Texte affiché sur la slide** :
  * **Brise-glace : Qu'évoque la cybersécurité pour vous ?**
  * *Partagez vos idées sur le tableau partagé ou dans le chat :*
    * Un mot, une image, ou une expérience personnelle récente liée à la sécurité numérique.
    * Pas de mauvaise réponse !
* **Visuels suggérés** : Nuage de mots-clés d'illustration (Hacker, Virus, Protection, Cadenas) flouté en arrière-plan. Lien d'accès au tableau blanc interactif affiché en évidence.
* **Notes du présentateur** :
  * Lancer l'activité. Donner 3 minutes de réflexion individuelle et de dépôt d'idées.
  * Regrouper les idées similaires à voix haute (ex. "Je vois beaucoup de termes liés à la peur des virus, mais aussi à la protection des données personnelles").
  * Faire le lien avec le contenu théorique : la cybersécurité sert à protéger les actifs importants de manière structurée.

---

## Slide 4 : Le pilier de base : La Triade CIA
* **Layout** : Trois colonnes de contenu
* **Texte affiché sur la slide** :
  * **La Triade CIA : Confidentialité, Intégrité, Disponibilité**
  * *Le cadre de référence pour évaluer la sécurité.*
  * **Confidentialité** : Les données restent secrètes. Seuls les utilisateurs autorisés y accèdent (Ex. Chiffrement, Mots de passe).
  * **Intégrité** : Les données restent exactes et fiables. Pas de modification non autorisée (Ex. Signatures numériques, Hachage).
  * **Disponibilité** : Les systèmes restent accessibles quand on en a besoin (Ex. Sauvegardes, Redondance serveurs).
* **Visuels suggérés** : Schéma en triangle (le triangle de la sécurité) reliant C, I et A avec des icônes explicites (Cadenas pour C, Clé à molette/Coche pour I, Sablier/Horloge pour A).
* **Notes du présentateur** :
  * Détailler chaque pilier à l'aide d'exemples simples de la vie courante (ex. pour C : le dossier médical ; pour I : la modification du solde bancaire ; pour A : la panne d'un site de vente en ligne).
  * Poser une question rapide : "Si un pirate bloque vos fichiers avec un ransomware mais ne les vole pas, quel pilier est touché ?" (Disponibilité).

---

## Slide 5 : Activité 1 — Le Détective CIA
* **Layout** : Consignes d'activité (Contenu structuré)
* **Texte affiché sur la slide** :
  * **Activité 1 : Détective CIA**
  * *Analysez les 3 cas réels d'incidents suivants et déterminez le pilier impacté :*
    * **Cas n°1** : Une panne réseau empêche les médecins d'accéder au dossier des patients aux urgences d'un hôpital pendant 4 heures.
    * **Cas n°2** : Un pirate intercepte le courriel d'un directeur financier et y dérobe la liste confidentielle des projets de rachat d'entreprises.
    * **Cas n°3** : Suite à un bug de logiciel de base de données, les fiches de paie de certains salariés indiquent le salaire de leur voisin.
  * **Consigne** : 10 min de réflexion par groupe de 3 dans vos sous-salles virtuelles. Nommez un rapporteur.
* **Visuels suggérés** : Icône de loupe ou de détective. Minuteur visuel de 10 minutes intégré au coin supérieur.
* **Notes du présentateur** :
  * Diviser la classe en sous-salles Zoom/Teams.
  * Circuler dans les salles pour guider les groupes si besoin.
  * Au retour en plénière, interroger 3 rapporteurs différents pour chaque cas et afficher les réponses au tableau.

---

## Slide 6 : Offense vs Défense & Menace vs Vulnérabilité
* **Layout** : Deux colonnes comparatives
* **Texte affiché sur la slide** :
  * **L'approche de la sécurité** :
    * **Sécurité Offensive (Offense)** : Tester les défenses en pensant comme l'attaquant. (Ex. Pentest, audits réels).
    * **Sécurité Défensive (Défense)** : Bâtir les remparts, surveiller et réparer. (Ex. Pare-feux, antivirus, processus).
  * **L'équation du risque** :
    * **Vulnérabilité** : Une faiblesse (ex. une serrure cassée).
    * **Menace** : Une entité malveillante (ex. un cambrioleur).
    * **Risque = Menace × Vulnérabilité × Impact** (ex. le cambrioleur s'introduit et vole les bijoux).
* **Visuels suggérés** : Dessin simple ou icône de deux épées croisées pour l'offense et un bouclier pour la défense. Schéma logique liant menace, vulnérabilité et risque.
* **Notes du présentateur** :
  * Expliquer qu'une bonne défense nécessite de comprendre l'attaque (offense).
  * Clarifier la différence sémantique entre vulnérabilité (interne à l'entreprise) et menace (externe), souvent confondues dans le langage courant.

---

## Slide 7 : Qui nous attaque ? Profils et Motivations
* **Layout** : Quatre colonnes de profils
* **Texte affiché sur la slide** :
  * **La cartographie des attaquants**
  * **1. Cybercriminels** :
    * *Motivation* : L'argent.
    * *Méthodes* : Ransomware, phishing de masse.
  * **2. États-Nations** :
    * *Motivation* : Espionnage, influence, sabotage.
    * *Méthodes* : Attaques ciblées avancées (APT).
  * **3. Hacktivistes** :
    * *Motivation* : Idéologie, politique.
    * *Méthodes* : Blocage de sites web, fuites publiques.
  * **4. Menaces Internes** :
    * *Motivation* : Vengeance, négligence.
    * *Méthodes* : Vol de fichiers par des employés.
* **Visuels suggérés** : Quatre silhouettes illustrées représentant les types d'attaquants avec des icônes de monnaie (cybercriminels), de drapeau/radar (États), de mégaphone/poing (hacktivistes) et de badge d'identité interne (menace interne).
* **Notes du présentateur** :
  * Casser le mythe du hacker à capuche en insistant sur l'aspect industriel de la cybercriminalité moderne (organisation en entreprises illégales avec support client pour les rançons).
  * Mettre en garde sur la menace interne, qui est le risque le plus difficile à intercepter techniquement.

---

## Slide 8 : Démo 1 — Découverte de la surface d'exposition d'une PME
* **Layout** : Démonstration (Capture d'écran / Console textuelle)
* **Texte affiché sur la slide** :
  * **Démonstration : Que voit un attaquant sur Internet ?**
  * *Recherche passives d'informations publiques (OSINT) :*
    * Étape 1 : Identification du domaine public (`entreprise.fr`).
    * Étape 2 : Scan DNS passif pour lister les serveurs de messagerie et serveurs web associés.
    * Étape 3 : Recherche d'identifiants ou d'e-mails d'employés divulgués sur des bases publiques.
  * **Objectif** : Comprendre pour fermer les portes d'entrée visibles de l'extérieur.
* **Visuels suggérés** : Capture d'écran propre montrant les résultats d'une requête de domaine (type DNS record) ou d'un outil de cartographie réseau de base.
* **Notes du présentateur** :
  * Exécuter la démonstration en suivant le script `A_scripts_demo.md#demo-1-osint` de manière fluide.
  * Insister sur le fait que toutes les informations recueillies le sont de manière légale et passive, sans intrusion active sur le système de la cible.
  * Montrer comment cela sert de phase de préparation pour les emails de phishing ciblés (spear-phishing) qui seront étudiés lors de la session suivante (A2).

---

## Slide 9 : Quiz interactif & Debriefing
* **Layout** : Contenu interactif (Quiz)
* **Texte affiché sur la slide** :
  * **Vrai ou Faux ?**
  * 1. *Le chiffrement d'un fichier garantit sa disponibilité.* ➔ **[Vrai / Faux ?]**
  * 2. *Une vulnérabilité est une faiblesse interne au système.* ➔ **[Vrai / Faux ?]**
  * 3. *Le but principal des hacktivistes est de voler des coordonnées de cartes de crédit.* ➔ **[Vrai / Faux ?]**
  * **Rejoignez le quiz sur vos smartphones !** (Lien à l'écran)
* **Visuels suggérés** : Un QR code géant permettant aux apprenants de se connecter directement à l'application de quiz (Kahoot/Wooclap).
* **Notes du présentateur** :
  * Lancer le quiz interactif. Commenter les réponses à la fin de chaque question.
  * *Réponses* : 1. Faux (garantit la confidentialité) ; 2. Vrai ; 3. Faux (motivation idéologique, les cartes de crédit concernent les cybercriminels).

---

## Slide 10 : Clôture & Devoirs
* **Layout** : Fin de session / Synthèse
* **Texte affiché sur la slide** :
  * **Pour aller plus loin : Vos devoirs (Self-paced)**
  * **Consignes avant la session A2** :
    * Suivre le module IBM SkillsBuild : *Introduction aux menaces cyber et logiciels malveillants*.
    * Durée estimée : ~60 min.
    * Note de passage requise au mini-quiz : 80%.
  * **Prochaine séance** : *Menaces, attaques & ingénierie sociale (A2)*.
  * Merci pour votre participation active !
* **Visuels suggérés** : Visuel du badge numérique d'achèvement de parcours. Icône de calendrier pour la date de la prochaine session.
* **Notes du présentateur** :
  * Remercier les apprenants pour leur écoute.
  * Expliquer comment accéder au cours SkillsBuild et comment valider la complétion de leur devoir.
  * Libérer la classe à l'heure exacte.
