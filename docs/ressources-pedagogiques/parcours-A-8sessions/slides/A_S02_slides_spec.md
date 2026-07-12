# Spécifications des slides — Session 02 : Menaces, attaques & ingénierie sociale
Parcours : A 8 sessions  |  Module : Menaces Cyber  |  Format : Spécifications Markdown  |  Modalité : Webinaire Livestorm

> **Principe directeur** : le texte affiché reste minimal ; le contenu riche est dans les notes du présentateur et dans le [plan d'animation minuté](../plans-de-seance/A_S02_plan.md), qui fait référence pour les verbatims et débriefs. Les numéros de sondages renvoient à la checklist Livestorm du plan.

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
  * Accueillir les apprenants ; test chat (« tapez OK »).
  * Faire le lien avec A1 en 30 secondes : triade C-I-D, profils d'attaquants, surface d'exposition OSINT — « aujourd'hui, on voit comment ils s'en servent ».
  * Annoncer la promesse de la session : repartir avec UN réflexe qui neutralise la plupart des attaques vues aujourd'hui.

---

## Slide 2 : Objectifs de la séance & Sommaire
* **Layout** : Deux colonnes (Gauche : Objectifs, Droite : Sommaire)
* **Texte affiché sur la slide** :
  * **Nos objectifs aujourd'hui** :
    * Classifier les grandes familles de logiciels malveillants (*malware*).
    * Identifier les leviers psychologiques de la manipulation.
    * Repérer les indices de phishing (e-mail, SMS, téléphone, visio).
    * Adopter le réflexe de la double validation par canal alternatif.
  * **Sommaire de la séance** :
    * 1. Brise-glace : la minute fatale (10 min)
    * 2. Typologie des malwares (12 min)
    * 3. L'ingénierie sociale : l'art de la manipulation (10 min)
    * 4. Activité : La Chasse au Phishing (14 min)
    * 5. La Cyber Kill Chain (7 min)
    * 6. Démo vishing + cas réels Pathé & Arup (17 min)
    * 7. Mise en situation, quiz & synthèse (16 min)
* **Visuels suggérés** : Icônes cibles pour les objectifs et icône de liste pour le sommaire.
* **Notes du présentateur** :
  * Parcourir les objectifs en soulignant l'importance d'une posture de suspicion saine au quotidien.
  * Annoncer le rythme interactif : un sondage ou une question chat toutes les 8 minutes environ.

---

## Slide 3 : Brise-glace — La minute fatale
* **Layout** : Plein écran interactif (sondage)
* **Texte affiché sur la slide** :
  * **📊 Sondage n°1 — À votre avis...**
  * *Combien de temps s'écoule, en médiane, entre l'ouverture d'un e-mail de phishing et la saisie des données par la victime ?*
    * A) Moins d'une minute  ·  B) ~1 heure  ·  C) ~1 journée  ·  D) ~1 semaine
  * (Réponse révélée après le vote)
* **Visuels suggérés** : Grand chronomètre stylisé. Après le vote, afficher « < 60 secondes » en très grand (21 s pour cliquer + 28 s pour saisir).
* **Notes du présentateur** :
  * Lancer le sondage n°1, laisser 60-90 s.
  * Débrief : réponse A (Verizon DBIR 2024). Message clé : la réflexion après coup ne sauve pas — c'est le réflexe avant le clic qui compte, et c'est l'objet de la session.

---

## Slide 4 : Vos histoires de messages suspects
* **Layout** : Plein écran interactif (chat)
* **Texte affiché sur la slide** :
  * **💬 Dans le chat : avez-vous déjà reçu un message suspect ?**
  * *SMS de colis, fausse contravention, e-mail alarmiste d'une administration...*
  * En une phrase : le message + l'indice qui vous a alerté.
* **Visuels suggérés** : Capture d'écran (floutée en partie) d'un SMS de phishing sur smartphone.
* **Notes du présentateur** :
  * Laisser ~3 minutes, lire 4-5 anecdotes à voix haute.
  * À chaque anecdote, nommer l'indice (URL, urgence, faute) et le levier psychologique — vocabulaire de la slide 6 introduit par l'expérience vécue.
  * Conclure : « vous avez déjà l'instinct ; on va en faire une méthode. »

---

## Slide 5 : La galerie des horreurs : Les logiciels malveillants
* **Layout** : Quatre blocs d'information
* **Texte affiché sur la slide** :
  * **Typologie des logiciels malveillants (*Malware*)** — *la question qui classe tout : que cherche-t-il à faire ?*
  * **1. Ransomware (Rançongiciel)** : chiffre les fichiers et exige une rançon (double extorsion). ➜ *Extorquer*
  * **2. Cheval de Troie (Trojan)** : se cache dans un logiciel légitime, ouvre une porte dérobée. ➜ *Ouvrir une porte*
  * **3. Logiciel Espion (Spyware/Keylogger)** : enregistre frappes et écrans, en silence. ➜ *Observer*
  * **4. Ver (Worm)** : se propage seul par les failles du réseau. ➜ *Se propager*
* **Visuels suggérés** : Icônes correspondantes (coffre cadenassé, cheval de bois, loupe d'espion, chenille), plus un bandeau « verbe d'action » sous chaque bloc.
* **Notes du présentateur** :
  * Illustrer chaque famille : rançongiciel → rappel express du CHSF vu en A1 ; trojan → le mythe grec, c'est la victime qui le fait entrer ; ver → ce qui a permis à WannaCry (A1) de faire le tour du monde sans un clic.
  * **💬 Question chat** : « Un antivirus gratuit douteux qui installe un keylogger : combien de familles dans cette phrase ? » (Réponse : 2 — trojan + spyware ; les familles se combinent).

---

## Slide 6 : L'ingénierie sociale : Manipuler l'humain
* **Layout** : Deux colonnes (Gauche : Leviers, Droite : Canaux)
* **Texte affiché sur la slide** :
  * **Les leviers psychologiques** :
    * **L'Urgence** : agir vite pour empêcher de réfléchir.
    * **L'Autorité** : usurper un chef, la police, les impôts.
    * **La Confiance** : se faire passer pour un habitué (EDF, La Poste, un collègue).
    * **La Curiosité / L'Appât du gain** : cadeau, révélation, fichier "salaires".
  * **Les canaux d'attaque** :
    * **Phishing** (e-mail de masse) · **Spear-phishing** (ultra-ciblé) · **Smishing** (SMS) · **Vishing** (téléphone) · et désormais la **visio deepfake**.
* **Visuels suggérés** : Schéma d'engrenages de la manipulation ; icônes e-mail, SMS, combiné téléphonique, caméra.
* **Notes du présentateur** :
  * Dérouler l'analogie du faux agent du gaz (pas d'effraction : on lui ouvre la porte).
  * Expliquer la logique économique : masse (volume) vs ciblé (préparation OSINT de la session A1, gains démultipliés).
  * Question rhétorique : « pourquoi appeler la comptabilité le vendredi à 17h45 ? » (urgence + fatigue + hiérarchie injoignable).
  * Annoncer la mutation IA : plus de fautes d'orthographe, voix et visages clonés — cas à 25 M$ dans quelques slides.

---

## Slide 7 : Activité — La Chasse au Phishing
* **Layout** : Consignes d'activité + 4 visuels successifs (un par sondage)
* **Texte affiché sur la slide** :
  * **🎣 La Chasse au Phishing — 4 messages, 4 votes**
  * *Pour chaque message : Phishing, Légitime, ou Je ne sais pas ?*
    * **Message 1** (📊 Sondage n°2) : SMS « Chronopost, frais de douane 1,95 € »
    * **Message 2** (📊 Sondage n°3) : e-mail « Netflix » — suspension imminente
    * **Message 3** (📊 Sondage n°4) : message interne IT... avec des fautes
    * **Message 4** (📊 Sondage n°5) : e-mail du DAF — « le RIB a changé »
  * **Attention : les pièges vont dans les deux sens !**
* **Visuels suggérés** : Quatre reconstitutions visuelles de messages (SMS smartphone, e-mail Netflix du support, e-mail interne sobre, e-mail professionnel signé) révélées une à une, avec annotation en direct au débrief.
* **Notes du présentateur** :
  * ~3 min par message : vote, puis analyse annotée à l'écran (survoler les liens sans cliquer).
  * Débriefs clés : lien raccourci = destination masquée (n°2) ; typosquatting + IP (n°3) ; fautes ≠ fraude, c'est la demande qui compte (n°4) ; changement de RIB = vérification par canal alternatif, TOUJOURS (n°5).
  * Le n°5 doit faire mal : la personnalisation (OSINT) désarme la vigilance — c'est la démonstration du spear-phishing.

---

## Slide 8 : La Cyber Kill Chain
* **Layout** : Ligne de temps / Processus chronologique
* **Texte affiché sur la slide** :
  * **La Cyber Kill Chain : Le plan de route de l'attaquant**
  * *Brisez un seul maillon pour stopper l'attaque !*
  * 1. **Reconnaissance** → 2. **Armement** → 3. **Livraison** → 4. **Exploitation** → 5. **Installation** → 6. **C2 (Commande & Contrôle)** → 7. **Actions sur objectifs**
  * Sous la chaîne : *sensibilisation (1,3,4) · filtrage mail (3) · mises à jour (4) · antivirus/EDR (5) · surveillance réseau (6)*
* **Visuels suggérés** : Chaîne à 7 maillons (couleurs du vert au rouge) avec, en dessous, les contre-mesures alignées sous les maillons qu'elles brisent.
* **Notes du présentateur** :
  * Dérouler avec l'exemple fil rouge d'un spear-phishing (LinkedIn → PDF piégé → e-mail → lecteur pas à jour → installation → C2 → exfiltration).
  * Question rhétorique : « à quelle étape cette formation agit-elle ? » (3 et 4 — vous êtes une contre-mesure).
  * Mentionner MITRE ATT&CK comme prolongement moderne (ressource).

---

## Slide 9 : Démo 2 — Simulation de Vishing
* **Layout** : Démonstration interactive / Script narratif
* **Texte affiché sur la slide** :
  * **Démonstration : Simulation de Vishing (hameçonnage vocal)**
  * *Le scénario :*
    * Un « technicien support » appelle : une cyberattaque serait en cours sur votre poste.
    * Il lui faut « d'urgence » le code d'authentification reçu par SMS pour « bloquer l'accès ».
  * **💬 Pendant la démo : notez dans le chat le moment où VOUS auriez raccroché.**
* **Visuels suggérés** : Silhouette de combiné téléphonique avec ondes sonores ; ambiance « appel entrant » plein écran.
* **Notes du présentateur** :
  * Jouer théâtralement le [script de la Démo 2](../outils/A_scripts_demo.md#demo-2-vishing) (les deux voix, ou en duo avec le modérateur).
  * Débrief : lire les moments de rupture notés dans le chat ; nommer les leviers (urgence, autorité, peur).
  * Règle absolue : un code SMS/application ne se communique JAMAIS — le vrai support ne le demande jamais.

---

## Slide 10 : L'hameçonnage en chiffres
* **Layout** : Mosaïque de grands chiffres (stat cards)
* **Texte affiché sur la slide** :
  * **L'ingénierie sociale en chiffres (sources citées)**
  * **< 1 min** : temps médian entre ouverture d'un phishing et saisie des données *(Verizon DBIR 2024)*
  * **N°1** : l'hameçonnage, première menace des particuliers ; piratage de compte en tête côté pros *(Cybermalveillance.gouv.fr 2024)*
  * **~2,8 Md$** : pertes BEC déclarées au FBI par an, rien qu'aux États-Unis *(FBI IC3 2024)*
  * **~60 %** des violations impliquent le facteur humain *(rappel A1 — Verizon DBIR 2025)*
* **Visuels suggérés** : Cartes de statistiques, chiffres en très grand corps, sources en petit ; pictogrammes chronomètre, hameçon, billets, silhouette.
* **Notes du présentateur** :
  * Message : l'ingénierie sociale est l'industrie la plus rentable du cybercrime — elle attaque ce qui ne se met pas à jour : nos réflexes.
  * La bonne nouvelle : le « correctif humain » existe — la procédure de double validation — et il est gratuit.

---

## Slide 11 : Deux fraudes réelles — Pathé (2018) & Arup (2024)
* **Layout** : Deux panneaux « étude de cas » + scénario chat
* **Texte affiché sur la slide** :
  * **Pathé, 2018 — l'arnaque au président** : faux e-mails du « siège », acquisition « secrète » à Dubaï → **~19,2 M€** virés. Leviers : autorité + urgence + secret.
  * **Arup, 2024 — la visio deepfake** : e-mail suspect... « confirmé » en visioconférence par un DAF et des collègues 100 % générés par IA → **~25 M$** virés.
  * **🤔 Et vous ? Votre DG vous appelle en visio pour un virement urgent : A) j'exécute · B) je le rappelle sur son numéro interne · C) je réponds à l'e-mail pour confirmer**
* **Visuels suggérés** : Deux cartes « dossier » avec logo de contexte neutre (cinéma / ingénierie), montants en très grand ; pictogramme masque numérique pour le deepfake.
* **Notes du présentateur** :
  * Raconter chronologiquement (le récit marque) : chez Pathé, le SECRET a neutralisé la double validation ; chez Arup, l'employé s'est méfié... et le deepfake a vaincu sa méfiance.
  * Faire voter A/B/C dans le chat ; débrief : B — seule une vérification INITIÉE PAR VOUS sur un canal INDÉPENDANT casse le scénario (C = répondre à l'attaquant).
  * Punchlines : « le BEC ne cible pas les naïfs, il cible les processus » ; « je l'ai vu en visio ne prouve plus rien ».

---

## Slide 12 : Mise en situation BEC — Les cartes cadeaux
* **Layout** : Mise en situation + 2 sondages
* **Texte affiché sur la slide** :
  * **🚨 Un e-mail pressant « de la direction » : acheter des cartes cadeaux, d'urgence et en toute discrétion.**
  * **📊 Sondage n°6** : De quel type d'attaque s'agit-il ? *(Ransomware / Spear-phishing-BEC / DDoS / Spyware)*
  * **📊 Sondage n°7** : Quelle est l'action la plus sûre ? *(Répondre à l'e-mail / Obéir / Vérifier par canal alternatif / Transférer à tous les collègues)*
* **Visuels suggérés** : Reconstitution d'e-mail sobre + cartes cadeaux ; les deux questions en cartes distinctes.
* **Notes du présentateur** :
  * Réponses : B (BEC) puis C (canal alternatif initié par soi).
  * Débrief : ne jamais confirmer via le canal d'origine ; le bon circuit de signalement = service informatique, pas l'e-mail groupé aux collègues.
  * Relier aux cas réels : même mécanique que Pathé, en miniature.

---

## Slide 13 : Quiz de validation
* **Layout** : Contenu interactif (3 sondages successifs)
* **Texte affiché sur la slide** :
  * **✅ Quiz de validation — 3 questions, 3 votes**
  * **📊 Sondage n°8** : Quel malware se propage tout seul, sans action humaine ? *(virus / ver / keylogger / trojan)*
  * **📊 Sondage n°9** : L'envoi de l'e-mail piégé = quelle étape de la Kill Chain ? *(reconnaissance / armement / livraison / exploitation)*
  * **📊 Sondage n°10** : Quel levier court-circuite la réflexion ? *(politesse / urgence / curiosité / confiance)*
* **Visuels suggérés** : Trois cartes de questions révélées successivement, coche verte à la révélation.
* **Notes du présentateur** :
  * Annoncer l'esprit : ancrage, pas évaluation. Réponses : ver ; livraison ; urgence.
  * Débriefs : ver vs virus (fichier hôte) ; re-balayer la chaîne en 30 s ; l'urgence = signal d'alarme n°1, commun à tous les cas du jour.

---

## Slide 14 : Clôture & Devoirs
* **Layout** : Fin de session / Synthèse
* **Texte affiché sur la slide** :
  * **Votre boîte à outils de la session 02 :**
    * 🦠 4 familles de malwares · 🧠 4 leviers de manipulation · ⛓️ 7 maillons de la Kill Chain · 🇫🇷🇭🇰 2 fraudes réelles
  * **LA règle d'or : toute demande sensible se vérifie par un canal alternatif que VOUS initiez.**
  * **💬 Dans le chat : le réflexe que vous retenez**
  * **Devoirs avant A3** : module IBM SkillsBuild *Introduction aux réseaux et à la sécurité réseau* (~90 min) + relever 3 indices de phishing dans votre boîte mail (sans cliquer) ; SMS frauduleux → transfert au 33700.
  * **Prochaine séance** : *Sécurité des systèmes & réseaux (A3)*.
* **Visuels suggérés** : Bandeau « règle d'or » très visible ; calendrier de la session 3 ; logo IBM SkillsBuild.
* **Notes du présentateur** :
  * Lire 4-5 réflexes du chat à voix haute.
  * Marteler une dernière fois : jamais un code SMS/app à qui que ce soit ; jamais un RIB changé sans vérification initiée par soi.
  * Teaser A3 : « les remparts techniques qui rattrapent les clics malheureux ». Libérer à l'heure exacte.
