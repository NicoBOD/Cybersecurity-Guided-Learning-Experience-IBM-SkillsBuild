# Spécifications des slides — Session B04 : Ingénierie sociale & facteur humain
Parcours : B 20 sessions  |  Module : A — Fondations  |  Format : Spécifications Markdown

> **Principe** : le texte affiché reste minimal (mots-clés, chiffres, schémas) ; le contenu riche est dans les notes orateur et le [plan de séance minuté](../plans-de-seance/B_S04_plan.md). Toutes les interactions passent par les sondages et le chat Livestorm.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Ingénierie sociale & facteur humain
  - L'attaque qui ne vise ni vos machines, ni vos logiciels... mais vous
  - Parcours B — Session B04
- **Notes orateur** : Accueillir : dernière session du module Fondations. Retour sur le self-paced : « qui a vu la vidéo Stuxnet ? Tapez dans le chat UNE étape de la Kill Chain que vous y avez reconnue. » Rappel express de B03. Teaser tenu : l'histoire des 19 millions d'euros perdus sans un seul malware, c'est ce soir.
- **Visuel suggéré** : Fond sombre avec l'illustration stylisée d'un cerveau humain connecté à des engrenages numériques.
  - **alt-text** : Graphisme représentant un cerveau humain stylisé avec des connexions de circuits imprimés sur fond sombre.
- **Élément interactif** : 💬 Chat d'accueil — les étapes de la Kill Chain repérées dans Stuxnet.

---

### Slide 2 — Objectifs & agenda
- **Type** : contenu
- **Points clés (bullets)** :
  - Décoder les 5 leviers psychologiques de la manipulation.
  - Distinguer phishing, spear-phishing, smishing, vishing, baiting et BEC.
  - Construire les réflexes d'hygiène numérique et la vérification hors canal.
  - Agenda : leviers → activité « Décodez le levier » → canaux → Pathé & Arup → hygiène → quiz.
- **Notes orateur** : Ce soir, aucune ligne de code : nous étudions le maillon le plus ciblé — l'humain. Nous apprendrons à nommer les leviers de manipulation, à reconnaître les canaux, puis nous décortiquerons deux affaires à plusieurs dizaines de millions avant de repartir avec des réflexes concrets.
- **Visuel suggéré** : Deux colonnes épurées détaillant les objectifs pédagogiques et l'agenda de la séance.
  - **alt-text** : Liste structurée présentant l'agenda de la session et les compétences clés ciblées.

---

### Slide 3 — Brise-glace : 60 secondes chrono
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **Sondage n°1** : temps médian entre l'ouverture d'un phishing et la saisie des identifiants ?
  - A) Moins d'une minute — B) Un quart d'heure — C) Plus d'une heure
- **Notes orateur** : Lancer le sondage n°1 (60-90 s). Réponse A : moins de 60 secondes en médiane — ~21 s pour cliquer, ~28 s pour saisir (Verizon DBIR 2024). La manipulation est conçue pour faire agir AVANT de réfléchir. L'objectif de la session : installer le réflexe qui fait gagner LA minute qui déjoue presque tout.
- **Visuel suggéré** : Chronomètre géant affichant 60 secondes avec un curseur de souris approchant d'un lien.
  - **alt-text** : Chronomètre marquant une minute à côté d'un curseur prêt à cliquer sur un lien d'e-mail frauduleux.
- **Élément interactif** : 📊 Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — Les 5 leviers psychologiques
- **Type** : schéma
- **Points clés (bullets)** :
  - **Autorité** : le PDG, l'avocat, le policier.
  - **Urgence** : « dans 2 heures, votre compte sera suspendu ».
  - **Sympathie** : le faux support qui « rend service ».
  - **Peur** : l'amende, les poursuites.
  - **Preuve sociale** : « tous vos collègues l'ont déjà fait ».
- **Notes orateur** : L'ingénierie sociale attaque la décision humaine, pas la machine : l'attaquant fabrique un contexte où la victime contourne elle-même les règles. Dérouler les 5 leviers avec leurs exemples. Les leviers se combinent : autorité + urgence + secret = le cocktail du BEC. Pour les curieux : ce sont les principes d'influence de Cialdini — le marketing utilise les mêmes. Relance chat : « lequel avez-vous déjà vu dans un message reçu ? »
- **Visuel suggéré** : Cinq cartes à jouer illustrées, une par levier, disposées en éventail comme une main de poker.
  - **alt-text** : Cinq cartes à jouer représentant les leviers psychologiques de la manipulation disposées en éventail.
- **Élément interactif** : 💬 Chat — « quel levier avez-vous déjà rencontré ? »

---

### Slide 5 — Activité : Décodez le levier
- **Type** : activité (sondages)
- **Points clés (bullets)** :
  - Trois messages piégés, lus avec le ton.
  - 📊 **Sondages n°2, 3, 4** : quel est le levier DOMINANT ?
  - « L'avocat du PDG » · « Le colis à 1,95 € » · « Julien du support »
- **Notes orateur** : Lire chaque message avec le ton approprié (pressant, anodin, chaleureux), puis vote et débrief. N°2 : autorité + urgence + secret — le trio du BEC ; le secret est le signal d'alarme n°1. N°3 : urgence + montant dérisoire — l'objectif n'est pas 1,95 €, c'est la carte complète. N°4 : sympathie — et la demande finale est votre code MFA, celui qui valide la connexion que L'ATTAQUANT est en train de faire. Règle absolue : ce code ne se communique jamais.
- **Visuel suggéré** : Trois bulles de message (e-mail, SMS, appel téléphonique) avec un point d'interrogation au centre.
  - **alt-text** : Trois bulles de conversation représentant un e-mail, un SMS et un appel, autour d'un point d'interrogation.
- **Élément interactif** : 📊 Sondages Livestorm n°2 à 4 — identification collective des leviers.

---

### Slide 6 — Les canaux d'attaque
- **Type** : schéma
- **Points clés (bullets)** :
  - **Phishing** : e-mail massif — la pêche au filet.
  - **Spear-phishing** : ciblé via l'OSINT — la pêche au harpon.
  - **Smishing** : par SMS (faux colis, fausse amende).
  - **Vishing** : par téléphone — vise souvent les codes MFA.
  - **Baiting** : la clé USB « Salaires 2026 » sur le parking.
  - **BEC** : la fraude au président — l'aboutissement de tous les autres.
- **Notes orateur** : Même psychologie, canaux différents. Le spear-phishing se nourrit d'OSINT : tout ce que LinkedIn et le site de l'entreprise révèlent (fonctions, hiérarchie, projets, absences). Le smishing profite du petit écran qui masque les indices. Le vishing ajoute la voix — et bientôt la slide Arup montrera que même la vidéo se falsifie.
- **Visuel suggéré** : Six icônes de canaux (enveloppe, harpon, téléphone-SMS, combiné, clé USB, cravate) reliées à une même silhouette de cible humaine.
  - **alt-text** : Six icônes représentant les canaux d'ingénierie sociale convergeant vers une silhouette humaine ciblée.

---

### Slide 7 — 💬 La chasse aux indices
- **Type** : question chat
- **Points clés (bullets)** :
  - Un e-mail « Service Comptabilité — URGENT » affiché en grand.
  - 💬 « Tapez dans le chat TOUS les indices qui trahissent le faux. »
- **Notes orateur** : Afficher l'e-mail piégé du support en pleine page, lisible. Lire les réponses du chat et compléter : domaine expéditeur modifié (typosquatting), urgence artificielle (24h, pénalités), lien vers un domaine tiers, formulation impersonnelle, prétexte vague. Conclure : aucun indice ne demande de compétence technique — juste une minute d'attention.
- **Visuel suggéré** : Reproduction plein écran de l'e-mail frauduleux du support, sans annotations (les indices seront révélés au débrief).
  - **alt-text** : E-mail frauduleux affiché en plein écran imitant un service comptabilité avec objet urgent.
- **Élément interactif** : 💬 Question chat — la chasse aux indices.

---

### Slide 8 — Le paysage en chiffres
- **Type** : chiffres clés
- **Points clés (bullets)** :
  - **< 60 s** pour tomber dans un phishing (Verizon DBIR 2024).
  - **~2,8 milliards $** de pertes BEC déclarées en 2024 aux États-Unis (FBI IC3).
  - **Menace n°1** des particuliers en France : l'hameçonnage (Cybermalveillance.gouv.fr, 2024).
  - **> 99,9 %** des attaques automatisées bloquées par la MFA (Microsoft, 2019).
- **Notes orateur** : Trois lectures : la victime tombe en secondes, donc la défense doit être un réflexe ; le BEC coûte des milliards sans un seul malware, donc la procédure vaut tous les antivirus ; la MFA est la mesure au meilleur rapport effort/protection — mais le sondage n°4 a montré qu'elle se protège aussi. Transition : voici ce que ces mécanismes donnent en vrai.
- **Visuel suggéré** : Quatre grands chiffres en typographie XXL, chacun avec sa source et son année en petit.
  - **alt-text** : Quatre statistiques géantes sur l'ingénierie sociale avec leurs sources : vitesse, pertes BEC, menace principale et efficacité MFA.

---

### Slide 9 — Affaire n°1 : Pathé (2018)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Des e-mails « du siège parisien » : une acquisition confidentielle à Dubaï.
  - Un mois de virements « urgents et discrets ».
  - **Plus de 19 millions d'euros** — sans un seul malware.
- **Notes orateur** : Raconter : la filiale néerlandaise du groupe de cinéma français, le domaine ressemblant, le scénario cohérent, le trio autorité + urgence + secret. Les deux dirigeants — des cadres expérimentés, pas des naïfs — ont été licenciés. La parade était purement procédurale : un seul contre-appel au siège, sur un numéro connu, aurait tout arrêté.
- **Visuel suggéré** : Façade de cinéma stylisée avec un fil d'e-mails s'envolant vers un compte offshore symbolisé par un coffre.
  - **alt-text** : Illustration d'une salle de cinéma reliée par un flux d'e-mails frauduleux à un coffre-fort étranger.

---

### Slide 10 — Affaire n°2 : Arup (2024)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Un e-mail suspect... et l'employé demande une visio : bon réflexe !
  - À l'écran : le directeur financier et des collègues reconnus.
  - Une quinzaine de virements : **~25 millions de dollars**.
  - Tout était **deepfake** — chaque visage, chaque voix.
- **Notes orateur** : Le twist : la vérification a utilisé le canal que l'attaquant contrôlait — une visio truquée « confirme » une demande truquée. À l'ère des deepfakes (générés à partir d'enregistrements publics), reconnaître un visage ou une voix ne prouve plus rien : seule la vérification par un canal indépendant compte — rappeler soi-même un numéro connu, procédure interne à deux personnes. Relance chat : « auriez-vous été piégé ? Honnêtement. »
- **Visuel suggéré** : Écran de visioconférence avec des vignettes de participants dont les visages se pixellisent en fils de code.
  - **alt-text** : Fenêtre de visioconférence dont les visages des participants se décomposent en pixels révélant leur nature synthétique.
- **Élément interactif** : 💬 Chat — réactions au cas Arup.

---

### Slide 11 — Et chez vous ? La procédure qui sauve
- **Type** : sondage (opinion)
- **Points clés (bullets)** :
  - 📊 **Sondage n°5** : une procédure formalisée de contre-vérification des virements / RIB chez vous ?
  - A) Oui, formalisée — B) Des habitudes informelles — C) Non / je ne sais pas.
- **Notes orateur** : Sondage d'opinion, pas de bonne réponse — un diagnostic. La vigilance individuelle ne suffit pas face à un scénario professionnel : il faut une procédure qui tienne même quand l'humain est convaincu (double validation au-dessus d'un seuil, contre-appel obligatoire, aucun changement de RIB sans vérification). Enchaîner immédiatement sur le mini-scénario du faux RIB : « tapez A, B ou C » (scénario au support ; réponse B — rappeler au numéro habituel ; piège du C : si la boîte est compromise, c'est l'attaquant qui répond).
- **Visuel suggéré** : Organigramme simple en trois étapes : demande reçue → contre-appel numéro connu → validation à deux.
  - **alt-text** : Schéma de procédure de double vérification des demandes de virement en trois étapes.
- **Élément interactif** : 📊 Sondage Livestorm n°5 (opinion) puis 🤔 mini-scénario en chat (A/B/C).

---

### Slide 12 — L'hygiène numérique : les 4 piliers
- **Type** : contenu
- **Points clés (bullets)** :
  - **Mots de passe** : longs, uniques, dans un gestionnaire.
  - **MFA partout** — et son code ne se communique JAMAIS.
  - **Vérification hors canal** : raccrocher, rappeler un numéro connu.
  - **Culture du signalement** : l'erreur signalée en 5 min vaut mieux que le silence de 3 jours.
- **Notes orateur** : Question rhétorique : « que préférez-vous — une victime qui signale en 5 minutes, ou un "bon élève" qui se tait 3 jours ? » Punir la victime garantit que la prochaine se taira. Présenter la Boîte à outils du support : le kit d'onboarding « 5 réflexes » (EcoLog) — l'exercice de la semaine est de l'adapter à sa propre organisation.
- **Visuel suggéré** : Quatre piliers de temple stylisés supportant un fronton « Sécurité », chacun étiqueté d'un pilier d'hygiène.
  - **alt-text** : Temple à quatre colonnes représentant les piliers de l'hygiène numérique soutenant la sécurité de l'entreprise.

---

### Slide 13 — Quiz de validation
- **Type** : quiz (sondages)
- **Points clés (bullets)** :
  - 📊 **Sondage n°6** : phishing vs spear-phishing — la différence essentielle ?
  - 📊 **Sondage n°7** : on vous demande votre code MFA au téléphone : que signifie cette demande ?
  - 📊 **Sondage n°8** : un collaborateur signale son erreur — réaction adaptée ?
- **Notes orateur** : Lancer les trois sondages à la suite (~2 min chacun), débriefs scriptés dans le support : la personnalisation est LE multiplicateur du spear-phishing ; aucun organisme légitime ne demande jamais un code MFA (connaître votre nom ne prouve rien — les données circulent dans les fuites, cf. France Travail en B01) ; la culture du signalement est un investissement. Si le temps le permet, enchaîner sur le bonus n°9 (l'anomalie qui alerte : le typosquatting).
- **Visuel suggéré** : Trois cartes de quiz numérotées 6, 7, 8 avec l'icône de sondage Livestorm.
  - **alt-text** : Trois cartes de questions de quiz numérotées, associées à des sondages en direct.
- **Élément interactif** : 📊 Sondages Livestorm n°6 à 8 (+ n°9 en tampon).

---

### Slide 14 — Synthèse & fin du module Fondations
- **Type** : récap
- **Points clés (bullets)** :
  - 5 leviers à nommer · 6 canaux à reconnaître · 1 réflexe : **vérifier hors canal**.
  - Pathé & Arup : des millions perdus — et une minute de vérification pour les sauver.
  - Module A terminé : quoi protéger (B01), qui attaque (B02), comment (B03), le maillon humain (B04).
  - Self-paced : SkillsBuild *« Social Engineering »* + adapter le kit « 5 réflexes » + préparer IP/IPv4/IPv6.
  - Prochaine session — B05 : Fondamentaux Réseau (module B).
- **Notes orateur** : Faire écrire dans le chat UN mot retenu, en lire 4-5. Clôturer le module Fondations en félicitant le groupe. Teaser B05 : « changement de décor : le module Systèmes & réseaux. Vous découvrirez comment vos données voyagent sur Internet — et à quel point il est facile de les lire au passage quand rien n'est chiffré. » Terminer à l'heure exacte.
- **Visuel suggéré** : Frise des quatre sessions du module A cochées, flèche vers un panneau « Module B — Réseaux ».
  - **alt-text** : Frise de progression montrant les quatre sessions du module Fondations validées et l'ouverture du module Réseaux.
- **Élément interactif** : Chat de clôture — « un mot que vous retenez ».
