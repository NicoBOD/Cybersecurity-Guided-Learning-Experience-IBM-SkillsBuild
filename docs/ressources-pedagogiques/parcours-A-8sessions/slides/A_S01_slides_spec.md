# Spécifications des slides — Session 01 : Découverte de la cybersécurité & paysage des menaces
Parcours : A 8 sessions  |  Module : Fondements Cyber  |  Format : Spécifications Markdown  |  Modalité : Webinaire Livestorm

> **Principe directeur** : le texte affiché reste minimal (mots-clés, chiffres, schémas) ; tout le contenu riche est dans les notes du présentateur et dans le [plan d'animation minuté](../plans-de-seance/A_S01_plan.md), qui fait référence pour les verbatims et débriefs. Les numéros de sondages renvoient à la checklist Livestorm du plan.

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
  * Rappeler le mode d'interaction Livestorm : tout passe par le **chat** et les **sondages** — pas de prise de parole micro.
  * Test du chat : « écrivez la ville d'où vous nous suivez » ; lire 3-4 réponses à voix haute.

---

## Slide 2 : Objectifs de la séance & Sommaire
* **Layout** : Deux colonnes (Gauche : Objectifs, Droite : Sommaire)
* **Texte affiché sur la slide** :
  * **Nos objectifs aujourd'hui** :
    * Définir les piliers de la triade CIA.
    * Distinguer vulnérabilité, menace et risque ; situer offense et défense.
    * Identifier les profils d'attaquants modernes et leurs motivations.
    * Mesurer les enjeux : chiffres officiels et cas réels français.
  * **Sommaire de la séance** :
    * 1. Brise-glace : le facteur humain (5 min)
    * 2. La Triade CIA + activité « Détective CIA » (20 min)
    * 3. Vulnérabilité, menace, risque & Offense/Défense (10 min)
    * 4. Les attaquants & le paysage en chiffres (15 min)
    * 5. Études de cas : CHSF & France Travail (10 min)
    * 6. Surface d'exposition & Démo OSINT (10 min)
    * 7. Quiz, dilemme final & synthèse (15 min)
* **Visuels suggérés** : Icônes cibles pour les objectifs et icône de liste ordonnée pour le sommaire.
* **Notes du présentateur** :
  * Présenter les objectifs en insistant sur le fait qu'aucun prérequis technique n'est nécessaire.
  * Parcourir l'agenda rapidement pour rassurer sur le rythme, et annoncer les nombreux sondages : « votre avis sera sollicité environ toutes les 8 minutes ».

---

## Slide 3 : Brise-glace — Le chiffre mystère
* **Layout** : Plein écran interactif (sondage)
* **Texte affiché sur la slide** :
  * **📊 Sondage n°1 — À votre avis...**
  * *Dans quelle proportion des violations de données le facteur humain (erreur, manipulation, mot de passe volé) est-il impliqué ?*
    * A) ~10 %  ·  B) ~30 %  ·  C) ~60 %  ·  D) ~90 %
  * (Réponse révélée après le vote)
* **Visuels suggérés** : Grand point d'interrogation stylisé, silhouettes humaines et cadenas en arrière-plan discret. Après le vote, afficher « ~60 % » en très grand.
* **Notes du présentateur** :
  * Lancer le sondage n°1 dans Livestorm, laisser 60-90 s, commenter la participation en direct.
  * Débrief : réponse C, ~60 % (Verizon DBIR 2025). Message clé de tout le parcours : la cybersécurité est d'abord une affaire de personnes — les participants deviennent une ligne de défense.
  * Si D majoritaire : valider l'intuition (certaines études élargies vont plus haut ; l'ordre de grandeur consensuel est 60 %).

---

## Slide 4 : Le pilier de base : La Triade CIA
* **Layout** : Trois colonnes de contenu
* **Texte affiché sur la slide** :
  * **La Triade CIA : Confidentialité, Intégrité, Disponibilité**
  * *Le cadre de référence pour évaluer la sécurité.*
  * **Confidentialité** : Les données restent secrètes. Seuls les utilisateurs autorisés y accèdent (Ex. Chiffrement, Mots de passe).
  * **Intégrité** : Les données restent exactes et fiables. Pas de modification non autorisée (Ex. Signatures numériques, Hachage).
  * **Disponibilité** : Les systèmes restent accessibles quand on en a besoin (Ex. Sauvegardes, Redondance serveurs).
* **Visuels suggérés** : Schéma en triangle (le triangle de la sécurité) reliant **C, I et D** (initiales françaises : Confidentialité, Intégrité, Disponibilité) avec des icônes explicites (Cadenas pour C, Coche/Sceau pour I, Horloge pour D). En légende discrète : « CIA = acronyme anglais *Confidentiality, Integrity, Availability* ».
* **Notes du présentateur** :
  * Lever d'emblée le piège de l'acronyme : « CIA » vient de l'anglais (*Availability* = Disponibilité) ; dans la suite de la session, on utilise les initiales françaises C, I et D.
  * Dérouler les trois analogies du support : la lettre cachetée (C), le cachet de cire (I), la bibliothèque aux portes fermées (D).
  * Question rhétorique : « Si un pirate bloque vos fichiers avec un ransomware mais ne les vole pas, quel pilier est touché ? » (Disponibilité).
  * **💬 Question chat** : « C, I ou D : laquelle serait la plus grave à perdre dans VOTRE métier ? » Lire 4-5 réponses ; conclure : la réponse dépend du métier (hôpital → D, banque → I, cabinet d'avocats → C).

---

## Slide 5 : Activité — Le Détective CIA
* **Layout** : Consignes d'activité + sondages successifs
* **Texte affiché sur la slide** :
  * **🕵️ Activité : Le Détective CIA — 3 enquêtes, 3 votes**
  * *Pour chaque incident, votez : quel pilier est touché ?*
    * **Enquête n°1** (📊 Sondage n°2) : Un rançongiciel chiffre la base comptable d'une entreprise.
    * **Enquête n°2** (📊 Sondage n°3) : Des e-mails RH avec fiches de paie sont interceptés, sans modification.
    * **Enquête n°3** (📊 Sondage n°4) : Une erreur de droits d'accès permet à tout employé de modifier les ventes.
  * **Attention : il y a des pièges dans les réponses !**
* **Visuels suggérés** : Icône de loupe ou de détective. Trois cartes « dossier d'enquête » numérotées, révélées l'une après l'autre.
* **Notes du présentateur** :
  * Lancer les sondages n°2, 3, 4 l'un après l'autre : ~1 min de vote + ~2 min de débrief chacun (réponses : Disponibilité, Confidentialité, Intégrité).
  * Débriefs obligatoires : la double extorsion (n°2, annonce du cas CHSF), la violation silencieuse (n°3), l'erreur humaine sans pirate (n°4).
  * Nommer le piège transversal : Non-répudiation, Authenticité et Résilience sont de vrais concepts, mais pas des piliers de la triade.

---

## Slide 6 : Offense vs Défense & L'équation du risque
* **Layout** : Deux colonnes comparatives
* **Texte affiché sur la slide** :
  * **L'équation du risque** :
    * **Vulnérabilité** : une faiblesse (la porte ouverte).
    * **Menace** : une entité malveillante (le cambrioleur).
    * **Risque = Menace × Vulnérabilité × Impact**
  * **L'approche de la sécurité** :
    * **Offensive (Red Team)** : tester les défenses en pensant comme l'attaquant (pentest — toujours avec autorisation écrite).
    * **Défensive (Blue Team)** : bâtir les remparts, surveiller, réagir (pare-feux, antivirus, processus).
* **Visuels suggérés** : Schéma logique liant menace, vulnérabilité et risque (porte ouverte + cambrioleur). Deux épées croisées (offense) face à un bouclier (défense).
* **Notes du présentateur** :
  * Dérouler l'exemple chiffré du support : serveur de paie exposé vs vieil ordinateur de salle de pause — même faille, risque radicalement différent, tout dépend de l'impact (parallèle avec l'assurance habitation).
  * Message clé : « on ne supprime pas les menaces, on ferme les portes ».
  * Point juridique à marteler : un pentest sans autorisation écrite est un délit (art. 323-1 et suivants du Code pénal). Mentionner la Purple Team (collaboration).

---

## Slide 7 : Qui nous attaque ? Profils et Motivations
* **Layout** : Quatre colonnes de profils + sondage
* **Texte affiché sur la slide** :
  * **La cartographie des attaquants**
  * **1. Cybercriminels** — *Motivation* : l'argent. *Méthodes* : ransomware (modèle RaaS), phishing de masse.
  * **2. États-Nations** — *Motivation* : espionnage, influence, sabotage. *Méthodes* : attaques ciblées longues (APT).
  * **3. Hacktivistes** — *Motivation* : idéologie. *Méthodes* : blocage de sites (DDoS), fuites publiques.
  * **4. Menaces Internes** — *Motivation* : vengeance... ou simple négligence. *Méthodes* : accès légitimes détournés.
  * **📊 Sondage n°5 : quelle est la menace n°1 pour VOTRE organisation ?**
* **Visuels suggérés** : Quatre silhouettes illustrées avec icônes : billets (cybercriminels), drapeau/radar (États), mégaphone (hacktivistes), badge d'employé (interne).
* **Notes du présentateur** :
  * Casser le mythe du hacker à capuche : industrie structurée, franchises RaaS, support client pour les rançons. Citer LockBit (opération « Cronos », février 2024).
  * Lancer le sondage n°5 (opinion, pas de bonne réponse). Débrief : les cybercriminels sont statistiquement la menace la plus probable ; la menace interne est presque toujours sous-estimée — souligner son accès privilégié.

---

## Slide 8 : Le paysage de la menace en chiffres
* **Layout** : Mosaïque de 5 grands chiffres (stat cards)
* **Texte affiché sur la slide** :
  * **La menace en chiffres (sources officielles)**
  * **~60 %** des violations impliquent le facteur humain *(Verizon DBIR 2025)*
  * **~4 400** événements de sécurité traités par l'ANSSI en 2024 *(Panorama 2024)*
  * **N°1** : l'hameçonnage, première menace en volume *(Cybermalveillance.gouv.fr 2024)*
  * **Record** de violations notifiées à la CNIL en 2024 (> 5 000)
  * **~4,4 M$** : coût moyen mondial d'une violation *(IBM 2025)*
* **Visuels suggérés** : Cinq cartes de statistiques avec les chiffres en très grand corps, la source en petit sous chaque carte. Pictogrammes sobres (personne, radar, hameçon, dossier, pièce de monnaie).
* **Notes du présentateur** :
  * Donner les ordres de grandeur plutôt que les décimales ; citer systématiquement source + année (crédibilité).
  * Les 3 messages : (1) l'attaque est un flux industriel permanent ; (2) les petites structures sont des cibles privilégiées ; (3) l'humain est la première porte d'entrée ET la première défense.
  * Question rhétorique : « Que peut faire un attaquant chez vous pendant les mois où il n'est pas détecté ? » — réponse en session A7.

---

## Slide 9 : Étude de cas n°1 — L'hôpital de Corbeil-Essonnes (2022)
* **Layout** : Frise chronologique + encadrés d'impact
* **Texte affiché sur la slide** :
  * **CHSF (Corbeil-Essonnes), nuit du 20 au 21 août 2022 — rançongiciel LockBit**
  * Systèmes chiffrés → retour au **papier**, transferts de patients
  * Rançon exigée : **10 M$** → refus (doctrine française)
  * Représailles : **~11 Go** de données patients publiées
  * Des **mois** de reconstruction, plusieurs **millions d'euros**
  * *Piliers touchés : Disponibilité ➜ puis Confidentialité (double extorsion)*
* **Visuels suggérés** : Frise chronologique de l'incident (intrusion → chiffrement → refus → fuite → reconstruction). Icône hôpital. Bandeaux C/I/D avec D et C en surbrillance.
* **Notes du présentateur** :
  * Raconter chronologiquement (le récit marque plus que les chiffres) : l'hôpital bascule en mode dégradé, les urgences trient au papier.
  * Expliquer le refus de payer : les établissements publics français ne paient pas, pour ne pas alimenter l'écosystème criminel.
  * Punchline : « "Les pirates ne s'attaquent pas aux hôpitaux" — si : plus la cible est critique, plus elle est censée payer vite. »
  * Faire le lien avec l'enquête n°1 du Détective CIA (rançongiciel = Disponibilité, puis double extorsion).

---

## Slide 10 : Étude de cas n°2 — France Travail (2024)
* **Layout** : Grand chiffre central + question chat
* **Texte affiché sur la slide** :
  * **France Travail, mars 2024 — l'une des plus grandes fuites françaises**
  * **43 millions** de personnes potentiellement concernées
  * Données : identité, n° de sécurité sociale, coordonnées
  * Ni mot de passe, ni RIB volés... **et pourtant** : hameçonnage crédible et usurpation d'identité pendant des années
  * *Pilier touché : Confidentialité (violation « silencieuse »)*
  * **💬 Dans le chat : quel indice vérifieriez-vous avant de cliquer sur un e-mail « France Travail » ?**
* **Visuels suggérés** : Le chiffre « 43 000 000 » en très grand. Icône d'enveloppe hameçonnée. Silhouette de la France en arrière-plan.
* **Notes du présentateur** :
  * Point d'entrée : des comptes de partenaires usurpés — le maillon faible est souvent chez le prestataire.
  * Expliquer l'effet différé : les données volées aujourd'hui alimentent les attaques de demain. Mentionner Viamedis/Almerys (~33 M d'assurés, février 2024) : 2024, année charnière.
  * Animer la question chat (indices : adresse d'expéditeur, lien survolé, ton d'urgence, demande inhabituelle). Conclure : « vous venez de commencer la session A2 sans le savoir » (ingénierie sociale).

---

## Slide 11 : Démo — La surface d'exposition d'une PME
* **Layout** : Démonstration (Capture d'écran / Console textuelle) + scénario
* **Texte affiché sur la slide** :
  * **Démonstration OSINT : que voit un attaquant sur Internet ?**
  * Étape 1 : identification du domaine public (`entreprise.fr`)
  * Étape 2 : scan DNS passif (serveurs de messagerie, serveurs web)
  * Étape 3 : recherche d'e-mails d'employés divulgués dans des fuites publiques
  * **Tout est légal et passif — aucune intrusion.**
  * **🤔 Et vous ? RDP ouvert + mot de passe `Admin2024` : A) je ne dis rien · B) je préviens le responsable · C) je teste moi-même**
* **Visuels suggérés** : Capture d'écran propre montrant les résultats d'une requête de domaine (type enregistrements DNS). Tableau des 4 éléments de surface d'exposition (DNS, web/cloud, ports RDP/SSH, réseaux sociaux) en rappel discret.
* **Notes du présentateur** :
  * Dérouler la [Démo 1 du guide des démonstrations](../outils/A_scripts_demo.md) ; en cas de souci technique, raconter la démo avec les captures de secours.
  * Insister deux fois : collecte passive et légale, c'est la phase de préparation du spear-phishing (annonce de la session A2).
  * Faire voter le scénario RDP dans le chat (A/B/C). Débrief : B ; C est illégal sans autorisation écrite même « pour aider » ; A = rappel du sondage n°1, la sécurité est l'affaire de tous.

---

## Slide 12 : Quiz de validation
* **Layout** : Contenu interactif (3 sondages successifs)
* **Texte affiché sur la slide** :
  * **✅ Quiz de validation — 3 questions, 3 votes**
  * **📊 Sondage n°6** : Un serveur non mis à jour depuis 2 ans, c'est... ? *(menace / vulnérabilité / risque / attaque)*
  * **📊 Sondage n°7** : Un collectif bloque le site d'un ministère pour protester. Motivation ? *(financière / géopolitique / idéologique / négligence)*
  * **📊 Sondage n°8** : Le pentest relève de... ? *(offensive / défensive / conformité / forensics)*
* **Visuels suggérés** : Trois cartes de questions révélées successivement, code couleur par question, icône de coche verte à la révélation des réponses.
* **Notes du présentateur** :
  * Annoncer l'esprit : un ancrage, pas une évaluation — « c'est maintenant qu'il faut se tromper ».
  * Lancer les sondages n°6, 7, 8 (~2 min chacun). Réponses : vulnérabilité ; idéologique ; sécurité offensive.
  * Débriefs : re-projeter Risque = Menace × Vulnérabilité × Impact (n°6) ; re-balayer les 4 profils en 20 s (n°7) ; rappeler l'autorisation écrite (n°8).

---

## Slide 13 : Dilemme décisionnel — Vous êtes aux commandes
* **Layout** : Mise en situation plein écran + sondage
* **Texte affiché sur la slide** :
  * **🚨 3 h du matin. Vous dirigez un hôpital.**
  * Un rançongiciel vient de bloquer les dossiers médicaux.
  * **📊 Sondage n°9 — Votre PREMIÈRE action :**
    * A) Payer immédiatement la rançon
    * B) Isoler le réseau et couper les liaisons des machines touchées
    * C) Restaurer les sauvegardes sur le même réseau actif
* **Visuels suggérés** : Ambiance sombre « salle de crise », horloge affichant 03:00, écran verrouillé stylisé. Les trois options en grandes cartes.
* **Notes du présentateur** :
  * Segment tampon : peut être coupé en cas de retard (l'exercice reste dans le support en bonus).
  * Débrief : B — isoler coupe la propagation latérale ; A ne garantit rien et finance le crime (choix écarté par le CHSF, boucle avec la slide 9) ; C = « reconstruire la maison pendant l'incendie », les sauvegardes seraient chiffrées à leur tour.

---

## Slide 14 : Clôture & Devoirs
* **Layout** : Fin de session / Synthèse
* **Texte affiché sur la slide** :
  * **Votre boîte à outils de la session 01 :**
    * 🧭 La triade CIA · ⚖️ Risque = Menace × Vulnérabilité × Impact · 🎭 4 profils d'attaquants · 🇫🇷 2 cas réels
  * **💬 Dans le chat : UN mot que vous retenez d'aujourd'hui**
  * **Devoirs avant la session A2** : module IBM SkillsBuild *Introduction aux menaces cyber et logiciels malveillants* (~60 min, mini-quiz : 80 %)
  * **Prochaine séance** : *Menaces, attaques & ingénierie sociale (A2)*
  * Merci pour votre participation active !
* **Visuels suggérés** : Visuel du badge numérique d'achèvement de parcours. Icône de calendrier pour la date de la prochaine session.
* **Notes du présentateur** :
  * Lire 4-5 mots du chat à voix haute (renforcement collectif).
  * Expliquer comment accéder au cours SkillsBuild et valider la complétion du devoir.
  * Teaser A2 : « on entre dans la tête des attaquants — d'ici là, méfiez-vous des e-mails de France Travail ».
  * Libérer la classe à l'heure exacte.
