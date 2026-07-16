# Spécifications des slides — Session B15 : Conformité & réglementations vie privée (+ Atelier de Synthèse 3)
Parcours : B 20 sessions  |  Module : D — Gouvernance, risques & conformité  |  Format : Spécifications Markdown

> **Principe** : le texte affiché reste minimal (mots-clés, chiffres, schémas) ; le contenu riche est dans les notes orateur et le [plan de séance minuté](../plans-de-seance/B_S15_plan.md). Toutes les interactions passent par les sondages et le chat Livestorm.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Conformité & réglementations vie privée
  - Le droit avec des dents : RGPD, CNIL, DPO
  - Parcours B — Session B15 · **Atelier de Synthèse 3** inclus
- **Notes orateur** : Accueillir : dernière session du module D, ET troisième Atelier de Synthèse. Retour self-paced : « qui a repéré un bandeau cookies SANS bouton "tout refuser" ? Racontez ! » — « en fin de session, vous saurez pourquoi c'est illégal et ce que ça a coûté à certains. » Rappel B14 : la matrice V×G — « elle ressert ce soir : l'atelier ! »
- **Visuel suggéré** : Drapeau européen dont les étoiles entourent un cadenas, avec un marteau de justice au premier plan.
  - **alt-text** : Drapeau européen protégeant des données personnelles sous l'autorité d'un marteau de justice.
- **Élément interactif** : 💬 Chat d'accueil — les bandeaux cookies observés.

---

### Slide 2 — Objectifs & agenda
- **Type** : contenu
- **Points clés (bullets)** :
  - Maîtriser les 5 devoirs du RGPD et les **deux paliers** de sanctions.
  - Situer la CNIL (le gendarme) et le DPO (le pilote, en duo avec le RSSI).
  - Auditer une charte de confidentialité.
  - **Atelier de Synthèse 3** : la matrice de risques de MedDistri.
  - Agenda : RGPD → CNIL & DPO → audit de charte → Google & Clearview → ATELIER → quiz.
- **Notes orateur** : Le fil rouge : les données appartiennent aux PERSONNES, pas aux entreprises qui les collectent — tout en découle. Et la conformité a des dents : les amendes se calculent en % du chiffre d'affaires mondial.
- **Visuel suggéré** : Deux colonnes présentant les objectifs et l'agenda, avec l'atelier mis en évidence.
  - **alt-text** : Tableau des objectifs et de l'agenda de la session avec l'atelier de synthèse surligné.

---

### Slide 3 — Brise-glace : l'amende record
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **Sondage n°1** : l'amende RGPD record en Europe à ce jour ?
  - A) 50 M€ — B) 1,2 Md€ — C) 4 M€
- **Notes orateur** : Lancer le sondage n°1 (60-90 s). Réponse B : 1,2 milliard — Meta, 2023 (transferts UE→USA). Et la réponse A n'est pas anodine : 50 M€ = Google, CNIL 2019, la première grande amende — décortiquée tout à l'heure. La conformité n'est pas de la paperasse : c'est du droit avec des dents.
- **Visuel suggéré** : Podium des amendes RGPD avec trois marches chiffrées.
  - **alt-text** : Podium des plus grandes amendes RGPD illustrant l'ampleur des sanctions.
- **Élément interactif** : 📊 Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — Le RGPD : les 5 devoirs
- **Type** : schéma
- **Points clés (bullets)** :
  - **Consentement** : positif, libre, spécifique, éclairé — jamais pré-coché.
  - **Minimisation** : une donnée non collectée ne fuite pas.
  - **Conservation limitée** · **Registre des traitements** · **Notification 72 h**.
  - Donnée personnelle = identification directe **ou indirecte** (IP comprise).
- **Notes orateur** : Relance chat : « donnée personnelle ou pas : une adresse IP ? une plaque ? la météo ? » (les deux premières : oui). La minimisation est le levier qui abaisse la GRAVITÉ (rappel B14, sondage n°4). Dérouler l'analogie du restaurant : l'inspecteur d'hygiène, l'opt-in des épices, le groupe sanguin pour une pizza.
- **Visuel suggéré** : Main ouverte à cinq doigts, un devoir RGPD par doigt.
  - **alt-text** : Main dont chaque doigt représente un devoir fondamental du RGPD.
- **Élément interactif** : 💬 Chat — donnée personnelle ou pas ?

---

### Slide 5 — Les sanctions : deux paliers — et deux acteurs
- **Type** : contenu
- **Points clés (bullets)** :
  - Palier 1 : jusqu'à **10 M€ ou 2 %** du CA mondial (manquements organisationnels).
  - Palier 2 : jusqu'à **20 M€ ou 4 %** (principes fondamentaux, consentement, droits) — le plus élevé retenu.
  - **CNIL** : conseille, contrôle, sanctionne... et publie.
  - **DPO** : registre, AIPD, point de contact — en duo avec le RSSI.
- **Notes orateur** : Le « % du CA mondial » explique le 1,2 Md€ de Meta : le plafond suit la taille. Le duo DPO/RSSI : patrimoine vs droits des personnes — en cas de fuite, enquête technique + notifications légales. Question rhétorique : que trouve-t-on dans une sanction CNIL ? Des mots de passe en clair, pas de chiffrement — la conformité et la technique sont les deux faces de la même pièce (activité de la semaine).
- **Visuel suggéré** : Escalier à deux marches chiffrées (2 %, 4 %) gravi par un personnage CNIL, un DPO tenant un registre à côté.
  - **alt-text** : Deux paliers de sanctions RGPD avec les rôles de la CNIL et du DPO.

---

### Slide 6 — Activité : l'audit de la charte EcoLog
- **Type** : activité (sondages)
- **Points clés (bullets)** :
  - La charte du marketing, affichée en grand — trois clauses suspectes.
  - 📊 **Sondage n°2** : les CB « conservées définitivement » ? · 📊 **n°3** : la revente « sans opposition » ? · 📊 **n°4** : le recommandé AR au siège ?
- **Notes orateur** : Vous êtes le DPO d'EcoLog. Lire chaque clause, vote, débrief avec la correction conforme : n°2 — limitation de conservation (le chiffrement ne légalise pas) ; n°3 — consentement forcé + droit d'opposition inaliénable ; n°4 — la symétrie : exercer ses droits doit être aussi simple que donner ses données. Conclure : trois infractions de bonne foi — le Privacy by Design existe pour ça.
- **Visuel suggéré** : Document de charte projeté avec trois clauses surlignées et des tampons d'audit.
  - **alt-text** : Charte de confidentialité auditée avec trois clauses non conformes surlignées.
- **Élément interactif** : 📊 Sondages Livestorm n°2 à 4 — audit collectif de la charte.

---

### Slide 7 — Le paysage en chiffres
- **Type** : chiffres clés
- **Points clés (bullets)** :
  - **1,2 Md€** : Meta (2023) — le record (transferts UE→USA).
  - **50 M€** : Google (CNIL, 2019) — la première grande sanction, confirmée en 2020.
  - **20 M€ + 5,2 M€ d'astreinte** : Clearview AI (CNIL, 2022-2023).
- **Notes orateur** : Trois lectures : les plafonds en % rendent la sanction dissuasive même pour les géants ; le RGPD s'applique aux entreprises étrangères dès qu'elles traitent des données de résidents européens ; ignorer la sanction coûte encore plus cher — l'astreinte court. Transition : les deux histoires.
- **Visuel suggéré** : Trois grands chiffres en typographie XXL avec leurs sources et années en petit.
  - **alt-text** : Trois montants de sanctions RGPD emblématiques avec leurs sources.

---

### Slide 8 — Affaire n°1 : Google vs CNIL (2019)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Huit mois après l'entrée en application du RGPD.
  - **Aucun piratage** : information diluée + consentement publicitaire ni spécifique ni éclairé.
  - **50 M€** — confirmés par le Conseil d'État (2020).
- **Notes orateur** : Raconter : les plaintes d'associations (noyb, La Quadrature du Net), l'arborescence illisible, l'accord global pré-configuré. Leçons : la CNIL juge l'ERGONOMIE du consentement — les parcours décourageants sont des infractions, pas des astuces ; le RGPD s'applique aux géants américains ; la conformité se joue dans le design des produits (Privacy by Design).
- **Visuel suggéré** : Labyrinthe de menus de paramétrage menant à une minuscule case de consentement.
  - **alt-text** : Labyrinthe de paramètres symbolisant une information diluée et un consentement introuvable.

---

### Slide 9 — Affaire n°2 : Clearview AI (2022-2023)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **30 milliards de visages** aspirés sur Internet — reconnaissance faciale commerciale.
  - Des Français dans la base : sans consentement, sans base légale.
  - **20 M€** + injonction d'effacer... ignorée → **astreinte de 5,2 M€**.
- **Notes orateur** : Raconter : le service vendu aux forces de l'ordre, les sanctions en chaîne en Europe (Italie, Grèce, Royaume-Uni). Leçons : « les données étaient publiques » n'est PAS une base légale — publier une photo n'autorise pas sa réutilisation biométrique ; le biométrique est une donnée SENSIBLE ; la conformité est une condition d'accès au marché européen. Relance chat : « quel détail vous marque le plus ? »
- **Visuel suggéré** : Mosaïque de visages pixellisés aspirés dans un entonnoir, barrée d'un panneau d'interdiction européen.
  - **alt-text** : Visages collectés en masse vers une base de reconnaissance faciale interdite en Europe.
- **Élément interactif** : 💬 Chat — réactions aux deux affaires.

---

### Slide 10 — Atelier de Synthèse 3 : les trois menaces de MedDistri
- **Type** : atelier (présentation)
- **Points clés (bullets)** :
  - ① **Rançongiciel** sur la base comptable.
  - ② **Vol du portable** d'un commercial (données clients à bord).
  - ③ **Fraude au virement** par usurpation du dirigeant (le BEC de B04).
  - Rappel : Criticité = Vraisemblance (1-4) × Gravité (1-4).
- **Notes orateur** : La matrice de B14 ressort — MedDistri tient son comité des risques, et c'est vous. Présenter les trois scénarios (3 min), rappeler la grille, annoncer le déroulé : un vote de cotation, un débat au chat, la matrice remplie en direct.
- **Visuel suggéré** : Trois cartes de scénarios menaçants posées devant une matrice 4x4 vide.
  - **alt-text** : Trois scénarios de menace à coter dans une matrice de criticité vide.

---

### Slide 11 — Atelier : votez, débattez, cotez
- **Type** : atelier (sondage + chat)
- **Points clés (bullets)** :
  - 📊 **Sondage n°5** : l'impact du rançongiciel sur la compta ? (1) Faible — (2) Moyen — (3) Majeur — (4) Critique.
  - 💬 « Défendez votre cotation en une phrase ! »
  - Puis scénarios ② et ③ : V ? G ? **et quel traitement de B14 ?**
- **Notes orateur** : Vote n°5 puis débat : côté 3 — « la compta bloque salaires et facturation » ; côté 4 — « une PME sans trésorerie meurt en quelques semaines » ; trancher collectivement (les deux se défendent : la discussion EST l'exercice) ; vraisemblance élevée (les rançongiciels frappent d'abord les PME — ANSSI, B01). Scénarios ② et ③ au chat : chiffrement B08 + effacement distant = réduire l'impact ; contre-appel B04 + double validation = réduire la vraisemblance. Remplir la matrice en direct. Synthèse : « trois risques, trois traitements, vingt minutes — un comité des risques. Chaque parade vient d'une session du parcours ; le grand atelier final assemblera tout. »
- **Visuel suggéré** : Matrice 4x4 projetée se remplissant de pastilles numérotées au fil des votes.
  - **alt-text** : Matrice de criticité remplie en direct avec les trois risques cotés collectivement.
- **Élément interactif** : 📊 Sondage Livestorm n°5 (cotation, 4 options) + 💬 chat — débat et traitements.

---

### Slide 12 — 🤔 Que feriez-vous ? Les 72 heures du week-end
- **Type** : scénario
- **Points clés (bullets)** :
  - Vendredi 18h : fuite de données confirmée chez MedDistri.
  - « Le délai de 72 h, c'est en jours ouvrés — profitez du week-end. »
  - A) Il a raison — B) Faux : 72 h calendaires dès la prise de connaissance — C) On notifie seulement si plainte.
- **Notes orateur** : Réponses par chat (A/B/C). Débrief : B — le délai court dès la prise de connaissance, week-ends compris (une notification initiale incomplète se complète ensuite). A est une légende tenace ; C est le scénario Uber de B13. Le réflexe : documenter dès la découverte — l'assureur et l'auditeur le demanderont aussi.
- **Visuel suggéré** : Chronomètre de 72 heures démarrant sur un calendrier de week-end.
  - **alt-text** : Compte à rebours de 72 heures courant à travers un week-end sur un calendrier.
- **Élément interactif** : 🤔 Mini-scénario — réponse A/B/C dans le chat.

---

### Slide 13 — Quiz de validation
- **Type** : quiz (sondages)
- **Points clés (bullets)** :
  - 📊 **Sondage n°6** : les plafonds de sanction du RGPD ?
  - 📊 **Sondage n°7** : une adresse IP est-elle une donnée personnelle ?
  - 📊 **Sondage n°8** : le rôle du registre des traitements ?
- **Notes orateur** : Lancer les trois sondages à la suite (~2 min chacun), débriefs scriptés dans le support : les deux paliers (le % du CA mondial explique le 1,2 Md€ de Meta) ; l'identification indirecte suffit (IP, localisation) ; le registre est la cartographie de la conformité — le premier document demandé en contrôle. Si le temps le permet, enchaîner sur le bonus n°9 (les traceurs).
- **Visuel suggéré** : Trois cartes de quiz numérotées 6, 7, 8 avec l'icône de sondage Livestorm.
  - **alt-text** : Trois cartes de questions de quiz numérotées, associées à des sondages en direct.
- **Élément interactif** : 📊 Sondages Livestorm n°6 à 8 (+ n°9 en tampon).

---

### Slide 14 — Synthèse & fin du module Gouvernance, risques & conformité
- **Type** : récap
- **Points clés (bullets)** :
  - Les données appartiennent aux **personnes** : minimiser, dire la vérité, faciliter les droits, notifier sous 72 h.
  - Module D terminé : gouverner (B13), arbitrer (B14), se conformer (B15).
  - Self-paced : SkillsBuild *« Data Privacy and GDPR »* + une sanction CNIL lue + acronymes SOC & SIEM.
  - Prochaine session — B16 : le SOC, la tour de contrôle (module E — Opérations).
- **Notes orateur** : Faire écrire dans le chat UN mot retenu, en lire 4-5. Féliciter pour le module et l'atelier. Teaser B16 : « redescendons dans la salle des machines : le SOC. Avec l'histoire de l'alerte qui a révélé l'une des plus grandes attaques de la décennie — un simple deuxième téléphone enregistré... et un analyste qui a pris la peine de vérifier. » Terminer à l'heure exacte.
- **Visuel suggéré** : Frise des trois sessions du module D cochées, la matrice MedDistri en vignette, flèche vers un panneau « Module E — Opérations ».
  - **alt-text** : Frise de progression du module gouvernance validé avec l'ouverture du module opérations.
- **Élément interactif** : Chat de clôture — « un mot que vous retenez ».
