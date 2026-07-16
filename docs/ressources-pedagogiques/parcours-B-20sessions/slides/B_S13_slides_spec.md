# Spécifications des slides — Session B13 : Gouvernance & cadres de sécurité
Parcours : B 20 sessions  |  Module : D — Gouvernance, risques & conformité  |  Format : Spécifications Markdown

> **Principe** : le texte affiché reste minimal (mots-clés, chiffres, schémas) ; le contenu riche est dans les notes orateur et le [plan de séance minuté](../plans-de-seance/B_S13_plan.md). Toutes les interactions passent par les sondages et le chat Livestorm.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Gouvernance & cadres de sécurité
  - Qui décide, qui assume, selon quelles règles ?
  - Parcours B — Session B13 · Ouverture du module Gouvernance, risques & conformité
- **Notes orateur** : Accueillir : depuis douze sessions on configure, à partir de ce soir on PILOTE. Retour self-paced : « en une phrase dans le chat : la différence entre PCA et PRA ? » (continuité pendant / reprise après — on y reviendra en B19). Rappel B12 : le cycle de vie de la donnée, OVHcloud, l'Atelier 2.
- **Visuel suggéré** : Salle de conseil d'administration stylisée avec un bouclier posé au centre de la table.
  - **alt-text** : Table de conseil d'administration avec un bouclier central symbolisant la cybersécurité comme sujet de direction.
- **Élément interactif** : 💬 Chat d'accueil — PCA vs PRA en une phrase.

---

### Slide 2 — Objectifs & agenda
- **Type** : contenu
- **Points clés (bullets)** :
  - Structurer une PSSI portée par la Direction.
  - Comparer ISO 27001 (management certifiable) et NIST CSF 2.0 (6 fonctions).
  - Distinguer le RSSI (conseille) de la Direction (décide, assume — NIS2).
  - Agenda : PSSI → comité de rédaction → référentiels → rôles → Uber & Yahoo → quiz.
- **Notes orateur** : Le fil rouge : la technique ferme les portes, la gouvernance décide quelles portes existent, qui a la clé, et vérifie. Deux affaires spectaculaires montreront ce qui arrive quand la gouvernance ment — un casier judiciaire et 350 millions de dollars.
- **Visuel suggéré** : Deux colonnes présentant les objectifs et l'agenda de la séance.
  - **alt-text** : Tableau présentant les objectifs d'apprentissage et les étapes de la session.

---

### Slide 3 — Brise-glace : la 6e fonction
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **Sondage n°1** : NIST CSF 2.0 (2024) ajoute une 6e fonction aux cinq historiques. Laquelle ?
  - A) *Govern* — Gouverner — B) *Attack* — C) *Insure*
- **Notes orateur** : Lancer le sondage n°1 (60-90 s). Réponse A : GOUVERNER (février 2024). Après dix ans, le référentiel technique le plus utilisé au monde a officialisé ce que le terrain criait : sans pilotage, les cinq fonctions techniques échouent. La gouvernance n'est pas une 6e étape : c'est le socle sous les cinq autres.
- **Visuel suggéré** : Roue à cinq segments historiques avec un moyeu central « GOVERN » nouvellement ajouté qui les relie tous.
  - **alt-text** : Roue des fonctions du NIST CSF avec la gouvernance au centre reliant les cinq fonctions historiques.
- **Élément interactif** : 📊 Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — La PSSI : le Code de la Route de l'entreprise
- **Type** : contenu
- **Points clés (bullets)** :
  - Le document stratégique **et juridique** de la sécurité.
  - Structure : champ d'application · rôles · règles d'usage · **sanctions**.
  - Sans signature de la Direction : une liste de conseils, pas une politique.
  - Le test d'une règle : **claire · mesurable · réaliste**.
- **Notes orateur** : Relance chat d'entrée : « pourquoi écrire des règles si les salariés sont de bonne foi ? » (harmoniser, prouver, sanctionner, survivre aux départs). Dérouler l'analogie du Code de la Route. Insister : une règle inapplicable sera contournée et décrédibilise tout le document (rappel B08).
- **Visuel suggéré** : Panneau de code de la route stylisé transformé en document signé d'un sceau de direction.
  - **alt-text** : Document de politique de sécurité présenté comme un code de la route signé par la direction.
- **Élément interactif** : 💬 Chat — pourquoi écrire les règles ?

---

### Slide 5 — Activité : le comité de rédaction PSSI
- **Type** : activité (sondages)
- **Points clés (bullets)** :
  - Trois sujets, trois formulations chacun — une seule mérite la PSSI.
  - 📊 **Sondage n°2** : les mots de passe · 📊 **n°3** : le télétravail · 📊 **n°4** : le document est-il prêt ?
  - Grille de lecture : claire ? mesurable ? réaliste ?
- **Notes orateur** : Lancer les trois sondages avec débrief : n°2 — le vœu pieux vs l'irréaliste vs la règle complète ; n°3 — « à éviter si possible » n'a aucune valeur d'audit ; n°4 — LE point de gouvernance : sans validation de la Direction, sanctions et règlement intérieur, rien n'est opposable. Une PSSI est un acte de direction, pas un document technique.
- **Visuel suggéré** : Table de comité avec trois propositions de règles sur des feuilles, tampons « adopté/rejeté ».
  - **alt-text** : Comité de rédaction examinant des propositions de règles de sécurité à adopter ou rejeter.
- **Élément interactif** : 📊 Sondages Livestorm n°2 à 4 — sélection collective des règles.

---

### Slide 6 — ISO 27001 : le management certifiable
- **Type** : contenu
- **Points clés (bullets)** :
  - Ne prescrit **aucun outil** : elle impose un **SMSI** (politiques, processus, audits, preuves).
  - Le moteur : **PDCA** — planifier, déployer, **vérifier**, ajuster.
  - À la clé : une **certification** opposable aux clients.
- **Notes orateur** : L'analogie du bâtiment : ISO = le code de la construction et le manuel de gestion de l'immeuble — comités, réévaluations, audits. La certification atteste que le management fonctionne et s'améliore — PAS que l'entreprise est impiratable (question de réflexion n°2). Le « Check » est la question n°8 du quiz.
- **Visuel suggéré** : Roue de Deming (PDCA) gravissant une pente avec une cale « SMSI », certificat au sommet.
  - **alt-text** : Roue de l'amélioration continue PDCA montant vers une certification ISO 27001.

---

### Slide 7 — NIST CSF 2.0 : les 6 fonctions
- **Type** : schéma
- **Points clés (bullets)** :
  - **Govern** (2024) : stratégie, rôles, politiques, chaîne d'approvisionnement — transversale.
  - Identify · Protect · **Detect** (B16) · **Respond** (B19) · **Recover** (B12 : 3-2-1, PCA/PRA).
  - ISO pilote le management ; le CSF structure l'action — **les deux se complètent**.
- **Notes orateur** : Dérouler les six fonctions en les reliant au parcours : Detect = la session SOC, Respond = la réponse aux incidents, Recover = vos sauvegardes et PCA/PRA. L'analogie : le CSF est le plan d'action des pompiers de l'immeuble — et depuis 2.0, qui dirige et rend des comptes. Question rhétorique : faut-il choisir ? Non — piloter avec le CSF, se certifier ISO.
- **Visuel suggéré** : Anneau des six fonctions avec GOVERN au centre, chaque fonction reliée à une session du parcours.
  - **alt-text** : Anneau des six fonctions du NIST CSF 2.0 avec la gouvernance au centre et les liens vers les sessions du parcours.

---

### Slide 8 — Qui décide ? Direction vs RSSI
- **Type** : schéma
- **Points clés (bullets)** :
  - **Le RSSI** : analyse, rédige, recommande, sensibilise — il **conseille**.
  - **La Direction** : valide les budgets, accepte le risque résiduel — elle **décide et assume**.
  - **NIS2** : la responsabilité des organes de direction devient légale.
  - Le rattachement compte : sous la DSI, le RSSI juge son propre patron.
- **Notes orateur** : La répartition canonique (question n°6 du quiz). NIS2 : directive européenne de 2022, en cours de transposition — des milliers d'entités concernées, et les dirigeants explicitement responsables de la supervision des risques. Relance chat : « chez vous, qui serait tenu responsable d'une fuite majeure ? Tapez le poste » — la bonne réponse tend vers « la direction », pas « l'informaticien ».
- **Visuel suggéré** : Balance à deux plateaux : mallette d'expertise (RSSI) et sceau de décision (Direction), avec un texte de loi « NIS2 » en arrière-plan.
  - **alt-text** : Balance illustrant la répartition entre l'expertise du RSSI et la décision de la direction sous le regard de NIS2.
- **Élément interactif** : 💬 Chat — qui est responsable chez vous ?

---

### Slide 9 — Le paysage en chiffres
- **Type** : chiffres clés
- **Points clés (bullets)** :
  - **Février 2024** : NIST CSF 2.0 — la fonction *Govern* rejoint les cinq historiques.
  - **350 M$** de décote + 35 M$ d'amende SEC : Yahoo, la fuite cachée (2017-2018).
  - **2022** : première condamnation pénale d'un CSO pour la gestion d'une violation (Uber).
- **Notes orateur** : Trois lectures : les référentiels eux-mêmes ont conclu que la technique sans gouvernance échoue ; cacher une fuite coûte plus cher que la fuite ; la responsabilité se chiffre en millions — et désormais en casiers judiciaires. Transition : les deux histoires.
- **Visuel suggéré** : Trois grands chiffres en typographie XXL avec leurs sources et années en petit.
  - **alt-text** : Trois statistiques géantes sur la gouvernance de la cybersécurité avec leurs sources.

---

### Slide 10 — Affaire n°1 : le CSO d'Uber (2016-2022)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - 2016 : une fuite massive... pendant une enquête du régulateur.
  - **100 000 $** versés aux attaquants, maquillés en « bug bounty » + accord de confidentialité.
  - Révélée un an plus tard par la nouvelle direction.
  - 2022 : le CSO **condamné** — obstruction et dissimulation.
- **Notes orateur** : Dérouler la chronologie. Leçons : la gestion d'incident est un acte de GOUVERNANCE, pas une opération discrète ; le bug bounty (outil légitime) ne blanchit pas une extorsion ; le professionnel doit savoir dire non — par écrit — à sa hiérarchie. Annoncer : « dans dix minutes, ce dilemme sera le vôtre. »
- **Visuel suggéré** : Enveloppe de récompense « bug bounty » dont dépasse un bâillon, devant un marteau de justice.
  - **alt-text** : Fausse récompense de bug bounty dissimulant un accord de silence, jugée par un marteau de justice.

---

### Slide 11 — Affaire n°2 : Yahoo (2013-2017)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - 2013-2014 : des fuites gigantesques — jusqu'à **3 milliards de comptes**.
  - Le silence interne... jusqu'à la négociation du rachat par Verizon.
  - **–350 M$** sur le prix de vente · 35 M$ d'amende SEC (2018).
- **Notes orateur** : Raconter : l'entreprise savait, n'a rien dit — ni aux utilisateurs ni aux investisseurs ; la vérité éclate en pleine due diligence. Leçons : une violation est une information FINANCIÈRE majeure ; la dissimulation a transformé l'incident en scandale de gouvernance ; la cyber est un sujet de conseil d'administration — ce qu'actent CSF 2.0 et NIS2. Relance chat : « quel détail vous marque le plus ? »
- **Visuel suggéré** : Étiquette de prix d'acquisition barrée et réécrite à la baisse, sur fond de serveurs fuyants.
  - **alt-text** : Prix de rachat d'une entreprise réduit de 350 millions de dollars à cause de fuites dissimulées.
- **Élément interactif** : 💬 Chat — réactions aux deux affaires.

---

### Slide 12 — Et chez vous ? La charte signée
- **Type** : sondage (opinion)
- **Points clés (bullets)** :
  - 📊 **Sondage n°5** : une charte informatique formellement signée existe-t-elle chez vous ?
  - A) Oui, preuve à l'appui — B) Elle existe « quelque part » — C) Je ne sais pas.
- **Notes orateur** : B est extrêmement répandu : le document existe, le portage n'existe pas — ni opposable, ni auditable. Les trois questions de lundi matin : où est-elle ? qui l'a signée ? la Direction l'a-t-elle validée ? Enchaîner sur le mini-scénario du faux bug bounty : « tapez A, B ou C » (réponse B — refuser, notifier la CNIL sous 72 h, documenter, mettre par écrit ; c'est mot pour mot le scénario Uber).
- **Visuel suggéré** : Classeur poussiéreux étiqueté « charte » sur une étagère, à côté d'un registre de signatures vide.
  - **alt-text** : Charte informatique oubliée sur une étagère avec un registre de signatures resté vide.
- **Élément interactif** : 📊 Sondage Livestorm n°5 (opinion) puis 🤔 mini-scénario en chat (A/B/C).

---

### Slide 13 — Quiz de validation
- **Type** : quiz (sondages)
- **Points clés (bullets)** :
  - 📊 **Sondage n°6** : qui accepte le risque résiduel et assume ?
  - 📊 **Sondage n°7** : ISO 27001 vs NIST CSF — la différence ?
  - 📊 **Sondage n°8** : le « C » de PDCA ?
- **Notes orateur** : Lancer les trois sondages à la suite (~2 min chacun), débriefs scriptés dans le support : le RSSI conseille, la Direction décide et assume (NIS2 le grave dans le droit) ; management certifiable vs cadre opérationnel — les deux se complètent ; Check = vérifier (audits, indicateurs) — sans vérification, pas d'amélioration continue. Si le temps le permet, enchaîner sur le bonus n°9 (la preuve d'audit).
- **Visuel suggéré** : Trois cartes de quiz numérotées 6, 7, 8 avec l'icône de sondage Livestorm.
  - **alt-text** : Trois cartes de questions de quiz numérotées, associées à des sondages en direct.
- **Élément interactif** : 📊 Sondages Livestorm n°6 à 8 (+ n°9 en tampon).

---

### Slide 14 — Synthèse & prochaine session
- **Type** : récap
- **Points clés (bullets)** :
  - Une politique n'existe que **signée par la Direction**.
  - ISO 27001 certifie le management · NIST CSF 2.0 structure l'action (**Govern** au centre).
  - Le RSSI conseille · la Direction assume — et **cacher coûte plus cher que réparer**.
  - Self-paced : SkillsBuild *« Governance and Risk Management - Part 1 »* + l'enquête charte + un risque non-IT observé.
  - Prochaine session — B14 : la gestion des risques.
- **Notes orateur** : Faire écrire dans le chat UN mot retenu, en lire 4-5. Rappeler le triple devoir (cours, enquête charte, observation d'un risque non informatique — préparation directe de B14). Teaser B14 : « combien vaut un risque ? Une formule qui tient sur un ticket de métro, une matrice à seize cases — et l'assureur qui a refusé de payer 100 millions de dollars en invoquant... un acte de guerre. » Terminer à l'heure exacte.
- **Visuel suggéré** : Récapitulatif en quatre vignettes (PSSI signée, deux référentiels, balance des rôles, transparence) et un panneau « B14 » fléché.
  - **alt-text** : Synthèse en quatre vignettes des thèmes de gouvernance avec un panneau indiquant la prochaine session B14.
- **Élément interactif** : Chat de clôture — « un mot que vous retenez ».
