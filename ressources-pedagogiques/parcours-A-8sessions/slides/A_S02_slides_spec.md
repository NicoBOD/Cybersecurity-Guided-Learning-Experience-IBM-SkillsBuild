# Spécifications des slides — Session 02 : Menaces, attaques & ingénierie sociale
Parcours : A 8 sessions  |  Module : Menaces Cyber  |  Format : Spécifications Markdown

---

## Slide 1 : Page de garde
* **Layout** : Titre (Emphase visuelle, fond sombre)
* **Texte affiché sur la slide** :
  * **Menaces, Attaques & Ingénierie Sociale**
  * Parcours A — Session 02
  * *Comprendre les armes des cybercriminels pour mieux s'en défendre*
  * Nom du Mentor / IBM SkillsBuild
* **Visuels suggérés** : Graphisme sombre avec des représentations abstraites de codes binaires colorés ou de maillons d'une chaîne brisée. Logo officiel dans un angle.
* **Notes du présentateur** :
  * Accueillir les apprenants et faire le lien avec la session précédente (la triade CIA et les profils d'attaquants).
  * Annoncer le programme : aujourd'hui, nous explorons comment les attaquants concrétisent leurs menaces, en ciblant le logiciel et l'humain.

---

## Slide 2 : Objectifs de la séance & Sommaire
* **Layout** : Deux colonnes (Gauche : Objectifs, Droite : Sommaire)
* **Texte affiché sur la slide** :
  * **Nos objectifs aujourd'hui** :
    * Classifier les grandes familles de logiciels malveillants (*malware*).
    * Identifier les ressorts psychologiques de la manipulation humaine.
    * Repérer les indices de phishing (e-mail, SMS, téléphone).
    * Décomposer les phases d'une attaque avec la *Cyber Kill Chain*.
  * **Sommaire de la séance** :
    * 1. Brise-glace : Le piège du phishing (10 min)
    * 2. Les logiciels malveillants : Typologie des *malwares* (20 min)
    * 3. L'ingénierie sociale : L'art de la manipulation (20 min)
    * 4. Activité pratique 1 : Chasse au phishing (20 min)
    * 5. Modéliser l'attaque : La Cyber Kill Chain (10 min)
    * 6. Démo 2 & Quiz final (10 min)
* **Visuels suggérés** : Icônes cibles pour les objectifs et icône de liste pour le sommaire.
* **Notes du présentateur** :
  * Parcourir les objectifs en soulignant l'importance d'adopter une posture de suspicion saine au quotidien.

---

## Slide 3 : Rappel & Brise-glace interactif
* **Layout** : Plein écran interactif
* **Texte affiché sur la slide** :
  * **Brise-glace : Avez-vous déjà reçu un message suspect ?**
  * *Partagez vos anecdotes :*
    * Un SMS suspect de livraison de colis, une fausse contravention de stationnement, ou un e-mail alarmiste d'une administration ?
    * Comment avez-vous réagi ? Quel indice vous a mis la puce à l'oreille ?
* **Visuels suggérés** : Capture d'écran (floutée en partie) d'un SMS de phishing sur smartphone.
* **Notes du présentateur** :
  * Laisser 3 minutes aux apprenants pour raconter leurs histoires dans le chat ou prendre la parole.
  * Rebondir sur les indices partagés (faute d'orthographe, ton menaçant, URL suspecte).
  * Expliquer que ces arnaques s'appuient sur l'ingénierie sociale que nous allons détailler aujourd'hui.

---

## Slide 4 : La galerie des horreurs : Les logiciels malveillants
* **Layout** : Quatre blocs d'information
* **Texte affiché sur la slide** :
  * **Typologie des logiciels malveillants (*Malware*)**
  * **1. Ransomware (Rançongiciel)** :
    * *Action* : Chiffre les fichiers et demande de l'argent.
  * **2. Cheval de Troie (Trojan)** :
    * *Action* : Se cache dans un logiciel légitime pour ouvrir un accès dérobé.
  * **3. Logiciel Espion (Spyware)** :
    * *Action* : Enregistre les frappes clavier (keylogger) et espionne en douce.
  * **4. Ver (Worm)** :
    * *Action* : Se propage tout seul à travers les failles de sécurité du réseau.
* **Visuels suggérés** : Icônes correspondantes à chaque type (Coffre cadenassé pour Ransomware, Cheval en bois pour Trojan, Silhouette d'espion avec loupe pour Spyware, Chenille/Ver pour Worm).
* **Notes du présentateur** :
  * Expliquer le fonctionnement de chaque malware avec des exemples (ex. Wannacry pour le Ver/Ransomware).
  * Rappeler que la propagation des malwares nécessite souvent au départ une action humaine (ouvrir une pièce jointe ou brancher une clé USB).

---

## Slide 5 : L'ingénierie sociale : Manipuler l'humain
* **Layout** : Deux colonnes (Gauche : Leviers, Droite : Canaux)
* **Texte affiché sur la slide** :
  * **Les leviers psychologiques de la manipulation** :
    * **L'Urgence** : Faire agir rapidement pour court-circuiter la réflexion.
    * **L'Autorité** : Usurper l'identité d'un chef ou d'un policier.
    * **La Confiance** : Se faire passer pour un partenaire habituel.
    * **La Curiosité / L'Appât du gain** : Promettre un cadeau ou une révélation.
  * **Les différents canaux d'attaque** :
    * **Phishing** : Hameçonnage générique par e-mail.
    * **Spear-phishing** : Hameçonnage ciblé et ultra-personnalisé.
    * **Smishing** : Hameçonnage par SMS.
    * **Vishing** : Hameçonnage vocal (par téléphone).
* **Visuels suggérés** : Schéma montrant les engrenages de la manipulation mentale. Icônes d'e-mail, de smartphone, de bulle SMS et de combiné téléphonique.
* **Notes du présentateur** :
  * Expliquer qu'un attaquant étudie sa cible sur les réseaux sociaux (OSINT de la session A1) pour concevoir un spear-phishing redoutable.
  * Mettre l'accent sur le vishing (arnaque au faux conseiller bancaire) très répandu actuellement.

---

## Slide 6 : Activité 1 — Chasse au Phishing
* **Layout** : Consignes de travail (Activité pratique)
* **Texte affiché sur la slide** :
  * **Activité 1 : Chasser les indices de Phishing**
  * *Analysez le message de phishing projeté à l'écran par votre mentor :*
    * Identifiez l'expéditeur réel.
    * Repérez l'urgence artificielle.
    * Examinez le lien cible sans cliquer dessus.
    * Relevez les fautes de syntaxe ou incohérences.
  * **Consignes** : 10 min en binôme dans vos salles de travail. Listez au moins 3 indices de fraude.
* **Visuels suggérés** : Capture d'un faux e-mail bancaire ou de messagerie cloud. Minuteur visuel de 10 min.
* **Notes du présentateur** :
  * Lancer l'activité.
  * Fournir le document ou projeter l'e-mail test.
  * Lors du débriefing, annoter en direct sur le partage d'écran les zones suspectes trouvées par les étudiants.

---

## Slide 7 : La Cyber Kill Chain
* **Layout** : Ligne de temps / Processus chronologique
* **Texte affiché sur la slide** :
  * **La Cyber Kill Chain : Le plan de route de l'attaquant**
  * *Brisez un seul maillon pour stopper l'attaque !*
  * 1. **Reconnaissance** : Recherche d'informations sur la cible.
  * 2. **Armement** : Conception du malware inséré dans un document.
  * 3. **Livraison** : Envoi de l'e-mail de phishing à la victime.
  * 4. **Exploitation** : Le malware s'exécute en profitant d'une faille.
  * 5. **Installation** : Le malware s'implante sur l'ordinateur.
  * 6. **C2 (Commande & Contrôle)** : Prise de contrôle à distance par le pirate.
  * 7. **Actions sur objectifs** : Chiffrement ou vol de données final.
* **Visuels suggérés** : Chaîne à 7 maillons reliant chronologiquement les étapes, avec des couleurs changeantes (de vert à rouge) et des icônes explicites.
* **Notes du présentateur** :
  * Parcourir la chaîne pas-à-pas en montrant comment les mesures de sécurité interviennent à chaque maillon pour stopper la progression (ex. bloquer l'e-mail à l'étape 3, avoir un antivirus à l'étape 5).

---

## Slide 8 : Démo 2 — Jeu de rôle de Vishing (Ingénierie Sociale)
* **Layout** : Démonstration interactive / Script narratif
* **Texte affiché sur la slide** :
  * **Démonstration : Simulation de Vishing (Hameçonnage vocal)**
  * *Le scénario :*
    * Un attaquant appelle un employé en prétendant être du service support.
    * Il prétend qu'une cyberattaque est en cours sur l'ordinateur de la victime.
    * Il demande le code d'authentification multifacteur reçu par SMS pour "bloquer l'accès".
  * **Objectif** : Observer la puissance de la pression psychologique.
* **Visuels suggérés** : Silhouette de combiné téléphonique avec des ondes sonores représentant l'interaction.
* **Notes du présentateur** :
  * Jouer le scénario avec un étudiant volontaire (ou simuler le dialogue de manière théâtrale d'après `A_scripts_demo.md#demo-2-vishing`).
  * Mettre en évidence les techniques verbales d'urgence et d'autorité.
  * Demander aux étudiants d'analyser à quel moment la victime aurait dû refuser et raccrocher.

---

## Slide 9 : Quiz live & Debriefing
* **Layout** : Contenu interactif (Quiz)
* **Texte affiché sur la slide** :
  * **Quiz rapide : Testez vos réflexes !**
  * 1. *Quel malware est caractérisé par sa capacité à se propager de lui-même sans action humaine ?* ➔ **[Virus / Ver / Keylogger ?]**
  * 2. *Qu'est-ce que le spear-phishing ?* ➔ **[Hameçonnage de masse / Hameçonnage ultra-ciblé ?]**
  * 3. *Quel est le levier psychologique le plus utilisé pour pousser à l'action immédiate ?* ➔ **[La politesse / L'urgence / L'indifférence ?]**
* **Visuels suggérés** : QR code de connexion au quiz Kahoot/Wooclap de la session.
* **Notes du présentateur** :
  * Lancer les questions de la banque de quiz. Debriefer en direct les réponses et éclaircir les doutes.
  * *Réponses* : 1. Ver ; 2. Hameçonnage ultra-ciblé ; 3. L'urgence.

---

## Slide 10 : Clôture & Devoirs
* **Layout** : Fin de session / Devoirs
* **Texte affiché sur la slide** :
  * **Vos devoirs avant la prochaine séance (Self-paced)** :
    * Suivre le module IBM SkillsBuild : *Introduction aux réseaux et à la sécurité réseau*.
    * Durée estimée : ~90 min.
    * Exercice d'application : Relever 3 indices de phishing sur les e-mails de votre boîte personnelle (exercice d'observation).
  * **Prochaine séance** : *Sécurité des systèmes & réseaux (A3)*.
  * Restez vigilants et ne partagez jamais vos codes d'accès !
* **Visuels suggérés** : Calendrier de la session 3. Logo IBM SkillsBuild.
* **Notes du présentateur** :
  * Rappeler la consigne de ne jamais communiquer un code d'authentification (SMS, application) reçu sur son mobile à qui que ce soit, pas même au support informatique légitime.
  * Clôturer la session.
