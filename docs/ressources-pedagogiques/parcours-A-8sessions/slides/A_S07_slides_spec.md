# Spécifications des slides — Session 07 : Réponse aux incidents & introduction au forensics
Parcours : A 8 sessions  |  Module : Réponse aux Incidents  |  Format : Spécifications Markdown  |  Modalité : Webinaire Livestorm

> **Principe directeur** : le texte affiché reste minimal ; le contenu riche est dans les notes du présentateur et dans le [plan d'animation minuté](../plans-de-seance/A_S07_plan.md), qui fait référence pour les verbatims et débriefs. Les numéros de sondages renvoient à la checklist Livestorm du plan (n°1 et n°9 sont volontairement identiques : mesure avant/après).

---

## Slide 1 : Page de garde
* **Layout** : Titre (Emphase visuelle, fond sombre)
* **Texte affiché sur la slide** :
  * **Réponse aux Incidents & Introduction au Forensics**
  * Parcours A — Session 07
  * *Contenir l'attaque, enquêter sur les traces et agir dans le respect des lois*
  * Nom du Mentor / IBM SkillsBuild
* **Visuels suggérés** : Graphisme dramatique mais professionnel simulant un flux de données intercepté, scindé en deux par un rayon lumineux. Logo officiel dans un angle.
* **Notes du présentateur** :
  * Accueillir ; retour devoirs A6 dans le chat : « le titre d'une alerte CERT-FR vue cette semaine ? » — lire 2-3 réponses.
  * Pivot : « A6 = détecter. Aujourd'hui : l'attaque est confirmée, elle est EN COURS. Que fait-on dans les 60 premières minutes ? »

---

## Slide 2 : Objectifs de la séance & Sommaire
* **Layout** : Deux colonnes (Gauche : Objectifs, Droite : Sommaire)
* **Texte affiché sur la slide** :
  * **Nos objectifs aujourd'hui** :
    * Dérouler les 6 étapes du cycle de réponse aux incidents (modèle SANS).
    * Maîtriser l'ordre de volatilité des preuves et la chaîne de contrôle.
    * Adopter le réflexe : isoler, jamais éteindre.
    * Situer le cadre légal (Code pénal) et la doctrine de non-paiement.
  * **Sommaire de la séance** :
    * 1. Le vote AVANT (6 min)
    * 2. Le cycle de réponse aux incidents (18 min)
    * 3. Activité : La Timeline du Détective (12 min)
    * 4. Forensics : préserver les preuves (12 min)
    * 5. Démo : une nuit en cellule de crise (10 min)
    * 6. Cadre légal, cas réels Maersk & CHSF (16 min)
    * 7. Quiz, vote APRÈS & synthèse (12 min)
* **Visuels suggérés** : Icônes cibles pour les objectifs et icône de liste pour le sommaire.
* **Notes du présentateur** :
  * Annoncer la mécanique spéciale du jour : un même vote en ouverture et en clôture — « la session se mesurera elle-même ».
  * Rythme : un sondage ou une question chat toutes les 8 minutes environ.

---

## Slide 3 : Le vote AVANT
* **Layout** : Plein écran interactif (sondage)
* **Texte affiché sur la slide** :
  * **📊 Sondage n°1 — Sans réfléchir trop longtemps...**
  * *Un poste affiche des signes d'infection active (fichiers qui disparaissent, trafic anormal). Votre TOUT premier geste ?*
    * A) Éteindre la machine (bouton d'alimentation)
    * B) Débrancher le câble réseau / couper le Wi-Fi, machine allumée
    * C) Lancer un scan antivirus complet
    * D) Prévenir tous les collègues par e-mail
  * **⚠️ Aucune correction maintenant — re-vote en fin de session !**
* **Visuels suggérés** : Écran d'ordinateur avec fichiers qui s'effacent ; un grand « ? » au centre ; bandeau « AVANT ».
* **Notes du présentateur** :
  * Lancer le sondage n°1, noter la répartition, NE RIEN corriger, ne donner aucun indice.
  * Verbatim : « je garde cette photographie au chaud — nous referons ce vote dans 80 minutes et nous comparerons. »

---

## Slide 4 : L'exercice d'évacuation
* **Layout** : Plein écran interactif (chat)
* **Texte affiché sur la slide** :
  * **💬 Dans le chat : quand l'alarme incendie sonne dans vos bureaux...**
  * *Qui fait quoi ? Et pourquoi est-ce que ça marche ?*
* **Visuels suggérés** : Plan d'évacuation stylisé avec flèches vertes et point de rassemblement.
* **Notes du présentateur** :
  * Lire 3-4 réponses. Révéler : ça marche parce que c'est écrit, répété, et que chacun connaît son rôle — personne n'improvise.
  * Transposer : « la réponse aux incidents, c'est le plan d'évacuation de vos données. Six étapes. »

---

## Slide 5 : Le cycle de réponse aux incidents — 6 étapes (SANS)
* **Layout** : Processus circulaire ou frise
* **Texte affiché sur la slide** :
  * **Le cycle IR (modèle SANS) :**
  * 1. **Préparation** → 2. **Identification** → 3. **Confinement** → 4. **Éradication** → 5. **Restauration** → 6. **Leçons apprises**
  * *(Le NIST regroupe les mêmes réalités en 4 phases — les deux modèles se valent.)*
  * **L'ordre n'est pas négociable** : restaurer avant d'éradiquer = réinstaller la maison pendant que le cambrioleur a le double des clés.
* **Visuels suggérés** : Roue à 6 segments avec l'analogie pompiers en pictogrammes (consignes, alarme, porte coupe-feu, extincteur, réouverture, commission).
* **Notes du présentateur** :
  * Filer l'analogie pompiers étape par étape ; insister sur Confinement ≠ extinction (teaser de la démo).
  * La Préparation inclut le canal de communication de secours : « si la messagerie est chiffrée, comment se parle la cellule de crise ? »
  * Question rhétorique : « l'étape la plus souvent sautée ? » — la 6e, celle qui rapporte le plus.

---

## Slide 6 : Activité — La Timeline du Détective
* **Layout** : 5 cartes-événements (affichées dans le désordre) + 2 sondages
* **Texte affiché sur la slide** :
  * **🕵️ La Timeline du Détective — 5 constats en vrac, à vous de reconstituer l'histoire**
    * 🗂️ Mer. 02:00 — transfert de 10 Go vers l'extérieur
    * 🗂️ Mer. 02:05 — alerte SIEM « volume sortant anormal »
    * 🗂️ Mar. 03:20 — le compte parcourt les répertoires financiers
    * 🗂️ Lun. 09:12 — e-mail « portail RH » : identifiants saisis
    * 🗂️ Mar. 03:14 — connexion VPN depuis une IP inconnue
  * **📊 Sondage n°2** : lequel est le POINT DE DÉPART réel ? · **📊 Sondage n°3** : quelle défense unique aurait cassé la chaîne ?
* **Visuels suggérés** : Cinq cartes « constat » mélangées, qui se réordonnent en frise chronologique au débrief.
* **Notes du présentateur** :
  * Réponses : l'e-mail de lundi (le clic = patient zéro) ; le MFA sur le VPN.
  * Débrief : l'alerte n'est pas l'attaque, c'est sa découverte — 41 h plus tard. Reconstituer la frise en nommant les sessions : phishing (A2) → identifiants (A4) → latéral (A3) → exfiltration → alerte (A6).
  * Punchline : « la réponse aux incidents commence des mois avant l'incident, dans l'architecture. »

---

## Slide 7 : Forensics — L'ordre de volatilité
* **Layout** : Tableau hiérarchisé
* **Texte affiché sur la slide** :
  * **La scène de crime numérique : collecter sans modifier**
  * **Capturer d'abord ce qui s'évapore :**
    * 🔥 **RAM** — mots de passe en clair, clés de chiffrement, connexions de l'attaquant *(perdue à l'extinction !)*
    * ⚡ Connexions & processus actifs
    * 💧 Fichiers temporaires & caches
    * 🪨 Disque dur (copie bit-à-bit)
  * **D'où LE réflexe : débrancher le réseau isole l'attaquant · éteindre détruit les preuves.**
* **Visuels suggérés** : Pyramide de volatilité (du plus volatil en flammes au plus stable en pierre) ; ruban « scène de crime » jaune.
* **Notes du présentateur** :
  * Marteler la nuance : deux gestes qui se ressemblent (isoler / éteindre), deux conséquences opposées — c'est l'enjeu du vote AVANT.
  * Citer les outils pour la culture : FTK Imager (dump RAM), Volatility (analyse RAM), Autopsy (disque).

---

## Slide 8 : Forensics — La chaîne de contrôle
* **Layout** : Processus en 4 étapes
* **Texte affiché sur la slide** :
  * **Rendre une preuve recevable devant un tribunal :**
    * 1. **Copie bit-à-bit** du support original
    * 2. **Empreinte SHA-256** identique = copie prouvée conforme
    * 3. **Original scellé** sous clé — on n'analyse QUE la copie
    * 4. **Journal des manipulations** : qui, quand, pourquoi
* **Visuels suggérés** : Sac de preuve scellé + étiquette d'empreinte numérique ; tampon « CONFORME ».
* **Notes du présentateur** :
  * Reboucler avec A1 : le hachage est le « cachet de cire » — il ne cache rien, il prouve l'intégrité.
  * Question rhétorique : « pourquoi jamais l'original ? » — analyser, c'est déjà modifier ; une preuve modifiée est une preuve morte.

---

## Slide 9 : Démo 7 — Une nuit en cellule de crise
* **Layout** : Mise en situation narrative + 2 sondages
* **Texte affiché sur la slide** :
  * **🚨 3h12 du matin. Le serveur de fichiers chiffre ses propres données. Vous êtes seul d'astreinte.**
  * *Un scénario dont VOUS écrivez la suite :*
    * **📊 Sondage n°4 — Décision 1** : éteindre le serveur ou l'isoler du réseau ?
    * **📊 Sondage n°5 — Décision 2** : restaurer immédiatement ou préserver puis restaurer sur base saine ?
* **Visuels suggérés** : Ambiance sombre « salle serveur la nuit », horloge 03:12, deux chemins qui bifurquent façon « livre dont vous êtes le héros ».
* **Notes du présentateur** :
  * Suivre le [script de la Démo 7](../outils/A_scripts_demo.md#demo-7-incident) : raconter les conséquences du choix majoritaire ET du choix écarté à chaque embranchement.
  * Réponses : isoler sans éteindre (préserver la RAM) ; préserver puis restaurer sur infrastructure assainie (sinon la porte dérobée re-compromet tout).
  * Conclure : « vous venez de vivre les étapes 3-4-5 du cycle et leurs pièges — en A8, ce sera à l'échelle d'une entreprise. »

---

## Slide 10 : Le cadre légal & la doctrine
* **Layout** : Deux colonnes
* **Texte affiché sur la slide** :
  * **Le Code pénal (art. 323-1 et s. — STAD) :**
    * Accès/maintien frauduleux : jusqu'à **2 ans / 60 000 €**
    * Avec altération de données : **3 ans / 100 000 €**
    * Entrave au fonctionnement : **5 ans / 150 000 €**
    * *Un système mal sécurisé n'est PAS une excuse légale.*
  * **Le piratage éthique** : ordre de mission **écrit** — périmètre, période, outils. Hors périmètre = délit.
  * **La doctrine française : ne pas payer les rançons** *(ANSSI)* — et porter plainte (condition d'indemnisation par les cyber-assurances).
* **Visuels suggérés** : Balance de justice ; contrat avec tampon « ORDRE DE MISSION » ; billet barré.
* **Notes du présentateur** :
  * Rappeler le scénario RDP d'A1 et le pentest d'A6 : signaler, jamais exploiter.
  * **💬 Chat** : « un chercheur exploite la faille de sa banque "pour prouver qu'il dit vrai" : héros ou délinquant ? Votez H ou D. » — au sens pénal : délinquant, quelle que soit l'intention ; la voie légale = signalement responsable.

---

## Slide 11 : L'incident en chiffres
* **Layout** : Mosaïque de grands chiffres (stat cards)
* **Texte affiché sur la slide** :
  * **Les chronomètres de la crise (sources citées)**
  * **Plusieurs mois** : délai moyen intrusion → confinement *(IBM 2025 — l'IR vise des heures)*
  * **72 h** : notification CNIL après DÉCOUVERTE d'une violation *(RGPD — rappel A5)*
  * **300 M$ / 10 jours** : les pertes et la reconstruction de Maersk après NotPetya *(2017)*
  * **0 €** : la doctrine française sur les rançons — ne pas payer *(ANSSI)*
* **Visuels suggérés** : Cartes de statistiques avec pictogrammes chronomètres ; chiffres en très grand corps.
* **Notes du présentateur** :
  * Message : la réponse aux incidents est une course contre deux chronos — celui de l'attaquant et celui du régulateur ; et le coût dépend moins de l'attaque que de la préparation.
  * Transition : « la preuve par Maersk. »

---

## Slide 12 : Deux cas réels — Maersk (2017) & retour à Corbeil-Essonnes
* **Layout** : Deux panneaux « étude de cas » + question chat
* **Texte affiché sur la slide** :
  * **Maersk / NotPetya, 2017 — la reconstruction héroïque** : ~4 000 serveurs et 45 000 postes détruits en minutes → l'unique sauvegarde survivante : un serveur au **Ghana**, hors ligne grâce à une **coupure de courant** → reconstruction mondiale en **10 jours**, ~**300 M$** de pertes.
  * **CHSF, 2022 — le cas d'A1 revisité** : identification nocturne → confinement & mode dégradé → **refus de payer** (doctrine) → des mois de reconstruction → leçons apprises nationales.
  * **💬 Dans le chat : chez vous, une copie survivrait-elle à un incident détruisant TOUT ce qui est connecté ? oui / non / je ne sais pas**
* **Visuels suggérés** : Porte-conteneurs + prise électrique débranchée (Maersk) ; hôpital + cycle IR en 6 segments surlignés (CHSF).
* **Notes du présentateur** :
  * Punchlines : « sauvés par une panne d'électricité — le 3-2-1 immuable d'A4 institutionnalise ce que le hasard a offert à Maersk » ; « la réponse aux incidents est un sport de direction générale ».
  * Chat : commenter la part de « je ne sais pas » — c'est ce qu'un exercice de crise révèle avant la réalité.

---

## Slide 13 : Quiz de validation
* **Layout** : Contenu interactif (3 sondages successifs)
* **Texte affiché sur la slide** :
  * **✅ Quiz de validation — 3 questions, 3 votes**
  * **📊 Sondage n°6** : Que capture-t-on en PREMIER lors de la collecte ? *(disque / RAM et connexions / e-mails / sauvegardes)*
  * **📊 Sondage n°7** : À quoi sert le hachage dans la chaîne de contrôle ?
  * **📊 Sondage n°8** : Le pentester peut-il tester le sous-traitant « pour être complet » ?
* **Visuels suggérés** : Trois cartes de questions révélées successivement, coche verte à la révélation.
* **Notes du présentateur** :
  * Réponses : la RAM d'abord (ordre de volatilité) ; prouver que la copie est identique à l'original ; non — hors périmètre écrit = délit.
  * Enchaîner immédiatement sur le vote APRÈS (slide suivante) — c'est le clou de la session.

---

## Slide 14 : Le vote APRÈS & clôture
* **Layout** : Sondage + comparaison avant/après + synthèse
* **Texte affiché sur la slide** :
  * **📊 Sondage n°9 — LE MÊME vote qu'en ouverture :**
  * *Poste infecté : votre TOUT premier geste ?* (A éteindre · B débrancher le réseau · C scan antivirus · D e-mail collectif)
  * **Vos trois réflexes : 🔌 ISOLER, jamais éteindre · 🧊 PRÉSERVER (RAM d'abord, hachage) · 📋 PRÉPARER (plan, canal de secours, exercice)**
  * **Prochaine séance : le Grand Atelier d'Audit MedDistri (A8)** — relisez vos aide-mémoires A1-A7 + le dossier MedDistri !
* **Visuels suggérés** : Deux histogrammes côte à côte « AVANT / APRÈS » ; badge « prêt pour l'audit » ; logo IBM SkillsBuild.
* **Notes du présentateur** :
  * Relancer le sondage identique, afficher les deux répartitions, commenter la progression : « ce delta, c'est ce que vous emportez ce soir. »
  * Révéler enfin la réponse : B — l'extinction détruit la RAM (clés, preuves) ; le scan laisse l'attaquant connecté ; l'e-mail collectif peut alerter l'attaquant.
  * Consignes A8 (relire aide-mémoires + dossier MedDistri) ; « la direction de MedDistri compte sur vous ». Libérer à l'heure exacte.
