# Spécifications des slides — Session 07 : Réponse aux incidents & introduction au forensics
Parcours : A 8 sessions  |  Module : Réponse aux Incidents  |  Format : Spécifications Markdown

---

## Slide 1 : Page de garde
* **Layout** : Titre (Emphase visuelle, fond sombre)
* **Texte affiché sur la slide** :
  * **Réponse aux Incidents & Introduction au Forensics**
  * Parcours A — Session 07
  * *Contenir l'attaque, enquêter sur les traces et agir dans le respect des lois*
  * Nom du Mentor / IBM SkillsBuild
* **Visuels suggérés** : Graphisme dramatique mais professionnel simulant un flux de données intercepté ou des lignes de codes bleues et vertes scindées en deux par un rayon lumineux. Logo officiel dans un angle.
* **Notes du présentateur** :
  * Accueillir les apprenants.
  * Faire le lien avec la session précédente (surveillance active SOC et détection des menaces). Expliquer qu'aujourd'hui, nous traitons le cas où l'attaque a réussi : comment réagir rapidement pour limiter la casse.

---

## Slide 2 : Objectifs de la séance & Sommaire
* **Layout** : Deux colonnes (Gauche : Objectifs, Droite : Sommaire)
* **Texte affiché sur la slide** :
  * **Nos objectifs aujourd'hui** :
    * Mémoriser les 6 étapes du cycle de réponse aux incidents (NIST/SANS).
    * Comprendre la notion d'ordre de volatilité lors de la collecte de preuves.
    * Expliquer le rôle de la chaîne de contrôle (*chain of custody*).
    * Situer les limites juridiques du piratage éthique (Code pénal).
  * **Sommaire de la séance** :
    * 1. Brise-glace : Le feu dans les bureaux (10 min)
    * 2. Le cycle de réponse aux incidents (20 min)
    * 3. Introduction au Forensics : Preuves et volatilité (20 min)
    * 4. Activité pratique 1 : Gestion de crise Rançongiciel (20 min)
    * 5. Cadre légal et piratage éthique (10 min)
    * 6. Quiz de session & Debriefing (10 min)
* **Visuels suggérés** : Icônes cibles pour les objectifs et icône de liste pour le sommaire.
* **Notes du présentateur** :
  * Présenter les objectifs en insistant sur l'analogie avec les pompiers ou les secouristes (importance de procédures écrites rigoureuses).

---

## Slide 3 : Rappel & Brise-glace interactif
* **Layout** : Plein écran interactif
* **Texte affiché sur la slide** :
  * **Brise-glace : Que feriez-vous en cas d'incendie ?**
  * *Imaginons qu'une fumée suspecte sorte de la photocopieuse du bureau.*
    * Est-ce le moment de concevoir le plan d'évacuation de l'immeuble ?
    * Pourquoi a-t-on des consignes d'évacuation déjà affichées sur les portes ?
    * Pourquoi la cybersécurité a-t-elle besoin de la même préparation ?
* **Visuels suggérés** : Photo ou dessin humoristique d'un exercice d'évacuation incendie d'entreprise.
* **Notes du présentateur** :
  * Laisser 3 minutes de débat.
  * Faire le lien : en cybersécurité, concevoir sa réponse pendant l'attaque est la garantie d'échouer. Il faut des processus de réaction (les *Playbooks* ou plans de réponse aux incidents) rédigés à l'avance.

---

## Slide 4 : Le cycle de réponse aux incidents (IR)
* **Layout** : Processus chronologique horizontal
* **Texte affiché sur la slide** :
  * **Le cycle de réponse aux incidents (NIST / SANS)**
  * **1. Préparation** : Outils, plans de crise, formation des équipes.
  * **2. Identification** : Découvrir, qualifier et analyser l'attaque.
  * **3. Confinement** : Isoler les systèmes touchés pour stopper la contagion.
  * **4. Éradication** : Nettoyer les malwares, effacer les accès dérobés.
  * **5. Restauration** : Reconstruire, tester et remettre en production.
  * **6. Leçons apprises** : Analyser pour corriger et améliorer.
* **Visuels suggérés** : Flèche de processus chronologique en 6 étapes, de gauche à droite, avec des icônes pour chaque étape (ex. Bouclier pour préparation, Loupe pour identification, Ciseau/Barrière pour confinement, Poubelle pour éradication, Flèche circulaire pour restauration, Cerveau pour leçons apprises).
* **Notes du présentateur** :
  * Détailler chaque phase.
  * Insister sur le fait que la phase de confinement (étape 3) doit intervenir avant de nettoyer la machine (étape 4), sous peine de voir le pirate se propager ailleurs.

---

## Slide 5 : Forensics : L'analyse scientifique du crime numérique
* **Layout** : Deux colonnes
* **Texte affiché sur la slide** :
  * **L'ordre de volatilité des données**
  * *Collecter les preuves de la plus volatile à la moins volatile :*
    * **1. Mémoire Vive (RAM)** : Connexions actives, mots de passe en clair (Disparaît si la machine est éteinte !).
    * **2. États du réseau & Processus** : Trafic en cours.
    * **3. Disque dur (Stockage physique)** : Fichiers persistants, journaux de log.
  * **La chaîne de contrôle (*Chain of Custody*)** :
    * Procédure documentant qui a saisi, transporté et analysé la preuve.
    * Empreinte numérique cryptographique (hachage) calculée à chaque étape pour prouver l'absence d'altération de la copie d'analyse.
* **Visuels suggérés** : Représentation d'une clé USB d'analyse ou d'un ruban de "scène de crime" jaune barrant un clavier.
* **Notes du présentateur** :
  * Expliquer pourquoi éteindre un ordinateur infecté par appui long sur le bouton d'alimentation peut détruire les preuves les plus précieuses contenues dans la RAM.
  * Expliquer le rôle du hachage de fichier pour certifier l'intégrité de la preuve.

---

## Slide 6 : Le cadre légal en France (Code pénal)
* **Layout** : Contenu structuré d'avertissement juridique
* **Texte affiché sur la slide** :
  * **Les atteintes aux systèmes informatiques (STAD)**
  * *Code pénal — Articles 323-1 et suivants :*
    * **Accès ou maintien frauduleux** dans un système informatique ➔ Jusqu'à 3 ans d'emprisonnement et 100 000 € d'amende.
    * **Entrave ou altération** du fonctionnement du système ➔ Jusqu'à 5 ans d'emprisonnement et 150 000 € d'amende.
    * **L'incompétence de la cible n'est pas une excuse** : Pénétrer dans un système informatique mal sécurisé reste un délit pénal.
  * **Piratage Éthique** : Un contrat écrit explicite (ordre de mission) doit être signé par le client avant toute action de test d'intrusion.
* **Visuels suggérés** : Logo officiel de la justice ou icône de balance avec un avertissement de sécurité.
* **Notes du présentateur** :
  * Rappeler la limite stricte entre les activités ludiques de type "Capture The Flag" (CTF) autorisées et l'intrusion non sollicitée sur un site public.
  * Insister sur le fait qu'en tant que professionnels de la cybersécurité, la déontologie et le respect scrupuleux du cadre contractuel sont prioritaires.

---

## Slide 7 : Focus pratique — Chaîne de contrôle d'une preuve
* **Layout** : Diagramme de flux logique
* **Texte affiché sur la slide** :
  * **Processus d'analyse forensics sécurisé**
  * 1. **Machine cible** ➔ 2. **Acquisition** (Copie bit-à-bit du disque d'origine) ➔ 3. **Calcul de l'empreinte** (Hachage SHA-256) ➔ 4. **Analyse** (Uniquement sur la copie).
  * *L'original physique reste scellé sous clé dans un coffre-fort.*
  * Toute manipulation de la preuve est inscrite dans la fiche de suivi de la chaîne de contrôle (Nom, Date, Heure, Action).
* **Visuels suggérés** : Représentation graphique d'une enveloppe de scellé étiquetée contenant un disque dur, reliée à un schéma de calcul de hachage.
* **Notes du présentateur** :
  * Expliquer qu'une empreinte numérique SHA-256 est comme une signature biologique unique. Si un seul bit change sur la copie lors de l'analyse, l'empreinte de fin sera totalement différente, ce qui invalidera la preuve au tribunal.

---

## Slide 8 : Activité 1 — Crise Rançongiciel en direct
* **Layout** : Consignes de travail (Activité pratique)
* **Texte affiché sur la slide** :
  * **Activité 1 : Face au Rançongiciel (Ransomware)**
  * *Scénario :*
    * Un comptable voit ses fichiers se renommer en `.locked` et son écran réclamer une rançon. Son poste est connecté en Ethernet au réseau local de la PME.
  * **Analysez les deux options d'action d'urgence :**
    * **Option A** : Éteindre immédiatement le poste par appui physique long sur le bouton ON/OFF pour "stopper" le virus.
    * **Option B** : Débrancher immédiatement le câble Ethernet pour isoler la machine, mais la laisser allumée.
  * **Consignes** : 15 min de réflexion en groupe de 4. Justifiez votre choix au regard du confinement et de la préservation des preuves (RAM).
* **Visuels suggérés** : Image de l'extension de fichier `.locked` ou d'une demande de rançon fictive. Minuteur de 15 minutes.
* **Notes du présentateur** :
  * Répartir la classe en groupes.
  * Rappeler la notion de mémoire volatile (RAM) étudiée lors de cette session.
  * Lors de la mise en commun, faire valider l'Option B (confinement réseau immédiat, sauvegarde de la RAM de la machine restée allumée).

---

## Slide 9 : Quiz de validation & Débriefing
* **Layout** : Contenu interactif (Quiz)
* **Texte affiché sur la slide** :
  * **Quiz live : Testez vos connaissances !**
  * 1. *Quelle est la première étape à mener face à une contagion de ransomware active sur le réseau ?* ➔ **[L'éradication / Le confinement / Les leçons apprises ?]**
  * 2. *Parmi les éléments suivants, quel est le plus volatil ?* ➔ **[La RAM / Le disque dur HDD / La clé USB de sauvegarde ?]**
  * 3. *Est-il légal de scanner les failles d'un site web public sans contrat préalable écrit ?* ➔ **[Oui, si on ne vole rien / Non, c'est illégal ?]**
* **Visuels suggérés** : QR code Kahoot/Wooclap de la session.
* **Notes du présentateur** :
  * Lancer les questions.
  * *Réponses* : 1. Le confinement ; 2. La RAM ; 3. Non, c'est illégal (accès frauduleux à un STAD).

---

## Slide 10 : Clôture & Devoirs
* **Layout** : Fin de session / Devoirs
* **Texte affiché sur la slide** :
  * **Vos devoirs avant la dernière séance (Self-paced)** :
    * Finaliser la rédaction de votre livrable écrit pour le **Projet Capstone** (Audit de sécurité d'une PME).
    * Préparer vos diapositives de présentation pour votre pitch oral de soutenance.
    * Relire la grille d'évaluation du projet fournie par votre mentor.
  * **Prochaine séance** : *Projet Capstone — restitution & synthèse (A8)*.
  * Bravo pour votre parcours, préparez bien vos présentations finales !
* **Visuels suggérés** : Logo IBM SkillsBuild. Icône de diplôme ou de badge numérique.
* **Notes du présentateur** :
  * Encourager chaleureusement les apprenants pour le travail final du capstone.
  * Rappeler les modalités de passage de la soutenance (10 min de pitch + 10 min de questions).
  * Clôturer la session.
