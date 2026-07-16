# Spécifications des slides — Session B14 : Gestion des risques
Parcours : B 20 sessions  |  Module : D — Gouvernance, risques & conformité  |  Format : Spécifications Markdown

> **Principe** : le texte affiché reste minimal (mots-clés, chiffres, schémas) ; le contenu riche est dans les notes orateur et le [plan de séance minuté](../plans-de-seance/B_S14_plan.md). Toutes les interactions passent par les sondages et le chat Livestorm.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Gestion des risques
  - Coter, arbitrer, décider — par écrit
  - Parcours B — Session B14
- **Notes orateur** : Accueillir. Retour self-paced : « tapez dans le chat le risque NON informatique observé cette semaine » — lire 3-4 exemples : « pour chacun, quelqu'un a déjà décidé de le réduire, l'assurer, l'éviter ou le subir — ce soir, la même logique, mais méthodique. » Rappel B13 : PSSI signée, RSSI conseille / Direction assume — et l'enquête charte.
- **Visuel suggéré** : Balance de précision pesant un nuage d'orage numérique contre des pièces de monnaie.
  - **alt-text** : Balance pesant un risque cyber symbolisé par un orage contre son coût en pièces de monnaie.
- **Élément interactif** : 💬 Chat d'accueil — le risque non-IT observé.

---

### Slide 2 — Objectifs & agenda
- **Type** : contenu
- **Points clés (bullets)** :
  - Articuler l'équation du risque : actif, menace, vulnérabilité, impact, vraisemblance.
  - Coter dans la matrice 4x4 : criticité brute → résiduelle.
  - Choisir parmi les 4 traitements : réduire, transférer, éviter, accepter (par écrit).
  - Agenda : équation → matrice → traitements → registre IA générative → Mondelez & Merck → quiz.
- **Notes orateur** : Le fil rouge : le risque ne s'élimine pas, il s'ARBITRE — et l'analyse de risques est le traducteur entre la technique et la direction (des CVE aux euros). Deux procès d'assurance à un milliard illustreront les limites du transfert.
- **Visuel suggéré** : Deux colonnes présentant les objectifs et l'agenda de la séance.
  - **alt-text** : Tableau présentant les objectifs d'apprentissage et les étapes de la session.

---

### Slide 3 — Brise-glace : l'« acte de guerre »
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **Sondage n°1** : un assureur peut-il refuser d'indemniser une cyberattaque en invoquant un « acte de guerre » ?
  - A) Oui, c'est déjà arrivé — B) Impossible juridiquement — C) Seulement en guerre déclarée
- **Notes orateur** : Lancer le sondage n°1 (60-90 s). Réponse A : après NotPetya (B03), attribuée à un sabotage étatique, des assureurs ont invoqué l'exclusion de guerre — 100 M$ pour Mondelez, 1,4 Md$ pour Merck. Moralité d'ouverture : transférer un risque ne le fait pas disparaître — encore faut-il lire la police.
- **Visuel suggéré** : Contrat d'assurance dont une clause est surlignée en rouge, sur fond d'écrans en panne.
  - **alt-text** : Contrat d'assurance avec une clause d'exclusion surlignée devant des écrans touchés par une cyberattaque.
- **Élément interactif** : 📊 Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — L'équation du risque
- **Type** : schéma
- **Points clés (bullets)** :
  - **Actif** (la valeur) · **Menace** (B02) · **Vulnérabilité** (B03-B08) · **Impact** (B01) · **Vraisemblance**.
  - La grammaire : « la MENACE exploite la VULNÉRABILITÉ pour atteindre l'ACTIF et causer un IMPACT. »
  - « Le pare-feu est vieux » n'est PAS un risque — c'est une vulnérabilité.
- **Notes orateur** : Relance chat d'entrée : « rouler sans ceinture, code de carte dans le téléphone : pourquoi certains le font-ils ? » — la perception du risque est biaisée, la méthode corrige. Faire reformuler un exemple complet par le chat. Vous connaissez déjà tous les ingrédients — ce soir on les assemble. C'est la question n°8 du quiz.
- **Visuel suggéré** : Engrenage à cinq pièces étiquetées (actif, menace, vulnérabilité, impact, vraisemblance) qui s'emboîtent en une phrase.
  - **alt-text** : Cinq pièces d'engrenage formant la phrase type de formulation d'un risque cyber.
- **Élément interactif** : 💬 Chat — perception du risque et reformulation.

---

### Slide 5 — La matrice de criticité 4x4
- **Type** : schéma
- **Points clés (bullets)** :
  - **Criticité = Vraisemblance (1-4) × Gravité (1-4)** → score de 1 à 16.
  - Zones : faible (1-4) · moyen (5-8) · **critique (9-16)**.
  - La valeur de la cotation : la **discussion** qu'elle force et la **priorisation** qu'elle produit.
- **Notes orateur** : Le registre des risques : la mémoire de l'arbitrage. La cotation est qualitative et collégiale — on traite le 12 avant le 4. Relance chat : « cotez : incendie du local serveur — V ? G ? » — lire les cotations, souligner les écarts : « vos désaccords sont exactement la discussion qu'une entreprise doit avoir. »
- **Visuel suggéré** : Matrice 4x4 en dégradé vert-jaune-rouge avec des pastilles de risques positionnées.
  - **alt-text** : Matrice de criticité seize cases colorées du vert au rouge avec des risques positionnés.
- **Élément interactif** : 💬 Chat — cotation express collective.

---

### Slide 6 — Les 4 traitements du risque
- **Type** : schéma
- **Points clés (bullets)** :
  - **Réduire** : abaisser la vraisemblance (EDR, MFA) ou l'impact (sauvegardes).
  - **Transférer** : assurance, externalisation — des euros, pas la réputation.
  - **Éviter** : renoncer — parfois la meilleure décision.
  - **Accepter** : légitime, MAIS écrit, signé, daté, réexaminé.
- **Notes orateur** : Dérouler l'analogie de l'alpinisme : casque et guide / assurance hélicoptère (en vérifiant l'altitude couverte !) / renoncer au sommet / y aller en le disant par écrit. Question rhétorique : quelle stratégie choisit-on le plus souvent sans s'en rendre compte ? ACCEPTER, par silence — d'où le registre. Rappel B13 : un risque non arbitré est un risque accepté par accident.
- **Visuel suggéré** : Carrefour de montagne à quatre sentiers étiquetés, un alpiniste consultant sa carte.
  - **alt-text** : Alpiniste choisissant entre quatre sentiers représentant les stratégies de traitement du risque.

---

### Slide 7 — Activité : la ligne de registre — l'IA générative chez EcoLog
- **Type** : activité (sondages)
- **Points clés (bullets)** :
  - Le marketing colle contrats et données clients dans des IA publiques gratuites.
  - 📊 **Sondage n°2** : la cotation brute ? · 📊 **n°3** : la stratégie ? · 📊 **n°4** : la cotation résiduelle ?
  - La ligne de registre se remplit à l'écran au fil des votes.
- **Notes orateur** : Lancer les trois sondages avec débrief : n°2 — on MULTIPLIE : 12/16, critique ; n°3 — blocage + charte + IA interne = Réduire (on garde l'usage, on abaisse la vraisemblance — l'alternative sécurisée évite le contournement, B08) ; n°4 — 3/16, jamais nul, et la gravité ne bouge pas : les mesures réduisent la probabilité, pas les conséquences (abaisser la gravité = minimiser les données — teaser B15). Conclure : « exactement l'exercice de l'Atelier 3, la semaine prochaine, sur MedDistri. »
- **Visuel suggéré** : Ligne de registre vide à six champs projetée, remplie progressivement.
  - **alt-text** : Ligne de registre des risques à compléter progressivement pendant l'activité collective.
- **Élément interactif** : 📊 Sondages Livestorm n°2 à 4 — construction collective de la ligne de registre.

---

### Slide 8 — Le paysage en chiffres
- **Type** : chiffres clés
- **Points clés (bullets)** :
  - **~100 M$** : Mondelez vs Zurich — l'exclusion de guerre invoquée (2018 → accord 2022).
  - **1,4 Md$** : Merck — la justice donne raison à l'assuré (2023, accord 2024).
  - **2023** : le marché (Lloyd's) réécrit ses clauses d'exclusion des attaques étatiques.
- **Notes orateur** : Trois lectures : le transfert a des limites écrites en petits caractères ; la qualification juridique d'une attaque (crime ? guerre ?) vaut des milliards ; le marché s'adapte — les polices d'aujourd'hui exigent un socle de sécurité et précisent leurs exclusions. Transition : les deux histoires.
- **Visuel suggéré** : Trois grands chiffres en typographie XXL avec leurs sources et années en petit.
  - **alt-text** : Trois statistiques géantes sur les contentieux d'assurance cyber avec leurs sources.

---

### Slide 9 — Affaire n°1 : Mondelez vs Zurich (2018-2022)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - NotPetya détruit serveurs et logistique : **~100 M$** déclarés.
  - L'assureur refuse : exclusion des « **actes de guerre** » (attaque attribuée à un État).
  - Quatre ans de procédure → accord **confidentiel** (2022).
- **Notes orateur** : Raconter : le géant d'Oreo et Milka, victime collatérale de NotPetya ; l'attribution étatique publique qui se retourne contre la victime ; l'industrie entière suspendue au procès. Leçons : le contrat a des exclusions ; l'attribution géopolitique (B02) a des conséquences assurantielles ; l'incertitude juridique est elle-même un risque — quatre ans pour connaître le sort de 100 M$.
- **Visuel suggéré** : Tablettes de chocolat et biscuits stylisés bloqués sur un tapis roulant à l'arrêt, contrat d'assurance en surimpression.
  - **alt-text** : Chaîne de production agroalimentaire à l'arrêt derrière un contrat d'assurance contesté.

---

### Slide 10 — Affaire n°2 : Merck (2017-2024)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Même attaque, même clause — **1,4 milliard de dollars** réclamés.
  - Les tribunaux donnent **raison à Merck** (2023) : la clause « guerre » ne s'applique pas telle quelle au cyber.
  - Accord définitif en 2024 — et le marché **réécrit** ses exclusions.
- **Notes orateur** : Raconter : 40 000 machines touchées, la production de vaccins perturbée ; la justice du New Jersey : une clause rédigée pour des conflits armés ne couvre pas une cyberattaque touchant des civils hors zone de guerre. Conséquence : les exigences du Lloyd's (2023) — les contrats récents définissent précisément les attaques étatiques exclues. Leçon opérationnelle : faire relire ses clauses cyber par un juriste — quelques milliers d'euros contre 1,4 milliard d'incertitude. Relance chat : « quel détail vous marque le plus ? »
- **Visuel suggéré** : Marteau de justice tranchant entre un missile barré et un écran d'ordinateur, chiffre « 1,4 Md$ » en arrière-plan.
  - **alt-text** : Justice tranchant qu'une cyberattaque n'est pas un acte de guerre au sens du contrat d'assurance.
- **Élément interactif** : 💬 Chat — réactions aux deux affaires.

---

### Slide 11 — Et chez vous ? L'assurance cyber
- **Type** : sondage (opinion)
- **Points clés (bullets)** :
  - 📊 **Sondage n°5** : votre organisation a-t-elle une assurance cyber ?
  - A) Oui, et je sais ce qu'elle couvre — B) Oui, mais mystère — C) Non / je ne sais pas.
- **Notes orateur** : Selon les baromètres AMRAE, l'assurance cyber reste concentrée sur les grandes entreprises. Deux messages : elle EXIGE désormais un socle (MFA, sauvegardes, EDR — le questionnaire ressemble à notre parcours) ; et pour les B : que couvre notre police, qu'exclut-elle ? Mondelez l'a découvert après le sinistre. Enchaîner sur le mini-scénario de l'acceptation orale : « tapez A, B ou C » (réponse B — la faire formaliser : fiche signée, datée, réexaminée ; l'acceptation orale n'engage que celui qui l'écoute).
- **Visuel suggéré** : Parapluie dont certaines baleines sont manquantes, étiqueté « police cyber ».
  - **alt-text** : Parapluie incomplet symbolisant une couverture d'assurance cyber aux exclusions méconnues.
- **Élément interactif** : 📊 Sondage Livestorm n°5 (opinion) puis 🤔 mini-scénario en chat (A/B/C).

---

### Slide 12 — Quiz de validation
- **Type** : quiz (sondages)
- **Points clés (bullets)** :
  - 📊 **Sondage n°6** : pourquoi le résiduel n'est-il jamais nul ?
  - 📊 **Sondage n°7** : que transfère une cyber-assurance ?
  - 📊 **Sondage n°8** : la formulation correcte d'un risque ?
- **Notes orateur** : Lancer les trois sondages à la suite (~2 min chacun), débriefs scriptés dans le support : la sécurité parfaite n'existe pas — le résiduel s'accepte par écrit ; l'assurance transfère l'impact financier, dans les limites du contrat (Mondelez/Merck en une question) ; la grammaire du risque — « le pare-feu est vieux » n'est qu'une vulnérabilité. Si le temps le permet, enchaîner sur le bonus n°9 (le groupe électrogène).
- **Visuel suggéré** : Trois cartes de quiz numérotées 6, 7, 8 avec l'icône de sondage Livestorm.
  - **alt-text** : Trois cartes de questions de quiz numérotées, associées à des sondages en direct.
- **Élément interactif** : 📊 Sondages Livestorm n°6 à 8 (+ n°9 en tampon).

---

### Slide 13 — Synthèse & prochaine session
- **Type** : récap
- **Points clés (bullets)** :
  - Une grammaire (menace → vulnérabilité → actif → impact) · une mesure (V × G) · quatre décisions.
  - Accepter, c'est **par écrit** — et transférer, c'est **après lecture des exclusions**.
  - Self-paced : SkillsBuild *« Governance and Risk Management - Part 2 »* + réviser B13-B14 pour l'Atelier 3 + observer les bandeaux cookies.
  - Prochaine session — B15 : Conformité & vie privée + **Atelier de Synthèse 3**.
- **Notes orateur** : Faire écrire dans le chat UN mot retenu, en lire 4-5. Insister sur la préparation de l'Atelier 3 (réviser la matrice). Teaser B15 : « la conformité — RGPD, CNIL — et VOUS coterez les risques de MedDistri. Avec des amendes bien réelles : 50 millions pour Google, 1,2 milliard pour Meta. La loi a des dents. » Terminer à l'heure exacte.
- **Visuel suggéré** : Récapitulatif en quatre vignettes (équation, matrice, carrefour des traitements, contrat lu à la loupe) et un panneau « B15 — Atelier » fléché.
  - **alt-text** : Synthèse en quatre vignettes de la gestion des risques avec un panneau annonçant la session B15 et son atelier.
- **Élément interactif** : Chat de clôture — « un mot que vous retenez ».
