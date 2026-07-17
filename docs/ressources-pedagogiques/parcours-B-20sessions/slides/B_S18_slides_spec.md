# Spécifications des slides — Session B18 : Introduction à la réponse aux incidents
Parcours : B 20 sessions  |  Module : E — Opérations, détection & réponse  |  Format : Spécifications Markdown

> **Principe** : texte affiché minimal (mots-clés, chiffres, schémas) ; le discours complet est dans le [plan de séance minuté](../plans-de-seance/B_S18_plan.md). Chaque interaction Livestorm est signalée sur la slide concernée.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Introduction à la réponse aux incidents
  - Avant : gérer les vulnérabilités · Pendant : confiner sans détruire les preuves · Après : apprendre
  - Parcours B — Session B18
- **Notes orateur** : Accueil. B16 : l'équipe qui surveille ; B17 : les traces qu'elle lit ; ce soir : l'alerte est confirmée — on fait quoi ? Session en deux temps : colmater avant, réagir pendant et après.
- **Visuel suggéré** : Un extincteur stylisé posé à côté d'un serveur, alarme discrète en fond.
  - **alt-text** : La réponse aux incidents illustrée par l'urgence maîtrisée.

---

### Slide 2 — Le devoir de la semaine & objectifs
- **Type** : contenu
- **Points clés (bullets)** :
  - 💬 Chat : une action technique concrète pour **isoler** une machine compromise ?
  - Objectifs : prioriser des correctifs (CVSS × exposition) · citer le cycle NIST/PICERL · appliquer les gestes du premier répondant (isoler sans éteindre).
  - Parcours : vulnérabilités → comité de priorisation → Equifax → cycle de réponse → la RAM → fiche réflexe → quiz.
- **Notes orateur** : Récolter : câble, Wi-Fi, VLAN d'isolement, règle pare-feu, EDR. Valider et annoncer les deux activités collectives (priorisation par sondages, fiche réflexe par chat).
- **Visuel suggéré** : Câble réseau débranché en gros plan, liste d'objectifs à droite.
  - **alt-text** : Isolement réseau d'une machine et objectifs de la session.
- **Élément interactif** : Question chat (réinvestissement du devoir de B17).

---

### Slide 3 — 📊 Sondage n°1 : l'avalanche
- **Type** : sondage
- **Points clés (bullets)** :
  - Combien de nouvelles vulnérabilités (CVE) publiées dans le monde en 2024 ?
  - A) ~4 000 — B) ~15 000 — C) plus de 40 000
  - Source : programme CVE / base NVD, 2024
- **Notes orateur** : Réponse C — plus de cent par jour, un record. Personne ne peut tout corriger : la compétence n'est pas de patcher, c'est de TRIER. Enchaîner sur le cycle.
- **Visuel suggéré** : Compteur défilant de CVE avec la barre des 40 000 dépassée.
  - **alt-text** : Volume record de vulnérabilités publiées en 2024.
- **Élément interactif** : Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — Avant l'incident : le cycle des vulnérabilités
- **Type** : schéma
- **Points clés (bullets)** :
  - **1. Identifier** : scan (Nessus, OpenVAS) × base **CVE**
  - **2. Évaluer** : score **CVSS** 0-10 — pondéré par l'**exposition** de l'actif
  - **3. Remédier** : patch (définitif) · mesure compensatoire (temporaire) · acceptation (formelle)
  - **4. Vérifier** : re-scanner — des correctifs échouent en silence
  - CVE = le cas déclaré · CWE = la maladie en général
- **Notes orateur** : Cycle continu, jamais terminé. Marteler : le score technique seul ne fait pas la priorité — c'est gravité × exposition, la criticité V×G de B14 appliquée aux failles. CVE/CWE : l'analogie médicale en 30 secondes.
- **Visuel suggéré** : Anneau à quatre flèches (identifier → évaluer → remédier → vérifier) tournant en continu.
  - **alt-text** : Cycle continu de gestion des vulnérabilités en quatre étapes.

---

### Slide 5 — Le cas limite : la faille zero-day
- **Type** : contenu
- **Points clés (bullets)** :
  - Inconnue de l'éditeur → **aucun correctif** (« zéro jour » pour se préparer)
  - Invisible pour l'antivirus par signature
  - Parades **architecturales** : EDR comportemental (B08) · segmentation (B06) · défense en profondeur
  - Très recherchée (et très chère) chez les attaquants étatiques
- **Notes orateur** : On ne patche pas ce qui n'a pas de patch : on limite ce que la faille peut atteindre et on détecte le comportement anormal qu'elle produit. Transition : trois dossiers sur la table du comité sécurité.
- **Visuel suggéré** : Sablier affichant « 0 », entouré des trois parades en pictogrammes.
  - **alt-text** : Vulnérabilité zero-day et ses parades architecturales.

---

### Slide 6 — 📊 Activité : le comité de priorisation (n°2, 3, 4)
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **n°2 — Dossier A** : CVSS 9.8, serveur web **exposé Internet**, correctif dispo → sous 24 h ? maintenance ? accepter ?
  - 📊 **n°3 — Dossier B** : la même faille, serveur de **test isolé** → même urgence ?
  - 📊 **n°4 — Dossier C** : correctif qui risque de **casser la facturation** → jamais ? compenser-tester-déployer ? forcer ?
- **Notes orateur** : Un dossier → un vote → un débrief. N°2 : pire profil au pire endroit = priorité 1 (« retenez ce dossier : c'est celui qu'Equifax a laissé traîner »). N°3 : même score, contexte opposé — le score environnemental. N°4 : le faux dilemme sécurité/production se résout par la séquence : compenser, tester, déployer.
- **Visuel suggéré** : Trois dossiers cartonnés étiquetés A/B/C avec tampon de priorité à apposer.
  - **alt-text** : Les trois dossiers de l'activité de priorisation des correctifs.
- **Élément interactif** : Sondages Livestorm n°2, 3, 4.

---

### Slide 7 — Affaire réelle : Equifax (2017)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Mars 2017 : faille Struts publiée (CVE-2017-5638), **correctif disponible le jour même**
  - Consigne interne envoyée… serveur jamais patché — re-scan qui ne le voit pas
  - **76 jours** d'exfiltration invisibles (certificat expiré sur l'inspection du trafic)
  - **147 millions** de personnes · accord jusqu'à **700 M$** (FTC, 2019) · PDG, DSI, RSSI démissionnent
- **Notes orateur** : Dérouler la chaîne des maillons cassés : inventaire, application, vérification, détection, communication de crise. 💬 Chat : « quel maillon a cédé en premier ? » — puis conclure : pas un exploit de génie, une chaîne de négligences ordinaires.
- **Visuel suggéré** : Chaîne dont chaque maillon porte une étiquette (inventaire, patch, re-scan, certificat), tous fissurés.
  - **alt-text** : La chaîne de défaillances de l'affaire Equifax.
- **Élément interactif** : Question chat « le premier maillon ».

---

### Slide 8 — Le stress test mondial : Log4Shell (2021)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - CVE-2021-44228 — score **CVSS 10.0** : à distance, sans compte, trivial
  - **Log4j** : une bibliothèque de journalisation présente dans d'innombrables logiciels
  - Le problème n°1 du week-end : **« où l'utilise-t-on ? »** — l'inventaire, encore
  - Réponse type : mesure compensatoire (WAF) immédiate → campagne de correctifs (CERT-FR/ANSSI)
- **Notes orateur** : Le monde entier a vécu le même scénario en même temps. La gestion des vulnérabilités vit ou meurt par l'inventaire : on ne protège que ce qu'on sait posséder — le tout premier contrôle depuis A01. Transition : et quand malgré tout, une faille passe ?
- **Visuel suggéré** : Planisphère avec des alertes s'allumant simultanément sur tous les continents.
  - **alt-text** : Log4Shell, une vulnérabilité critique mondiale et simultanée.

---

### Slide 9 — Le cycle de réponse : NIST SP 800-61 / PICERL
- **Type** : schéma
- **Points clés (bullets)** :
  - NIST : **4 phases** — Préparation · Détection & Analyse · Confinement-Éradication-Recouvrement · Post-incident
  - PICERL (SANS) : les mêmes réalités en **6 étapes** mnémotechniques
  - La phase la plus sautée : le **REX** — la seule qui empêche de revivre le même incident
- **Notes orateur** : Précision de rigueur : le NIST regroupe confinement-éradication-recouvrement en UNE phase (on itère entre les trois) ; PICERL les déplie. Préparation = tout ce qu'on a déjà construit (B12 sauvegardes, playbooks, première partie de ce soir). « Sans REX, vous ne sortez pas d'un incident — vous attendez le suivant. »
- **Visuel suggéré** : Tableau de correspondance NIST (4 lignes) ↔ PICERL (6 lignes), flèche de cycle qui reboucle.
  - **alt-text** : Correspondance entre les quatre phases NIST et les six étapes PICERL.

---

### Slide 10 — Confiner, éradiquer, recouvrer : l'incendie de cuisine
- **Type** : schéma
- **Points clés (bullets)** :
  - **Confinement** : fermer la porte de la cuisine — isoler pour protéger le reste
  - **Éradication** : éteindre à la source, déblayer — malwares, portes dérobées, comptes compromis, **faille d'origine**
  - **Recouvrement** : repeindre, remplacer la cuisinière — restaurer (B12), valider, surveiller
- **Notes orateur** : Insister sur l'éradication : nettoyer les malwares ne suffit pas — il faut aussi les portes dérobées ET la faille exploitée, sinon le recouvrement restaure un environnement piégé (question de réflexion n°2). Remise en production progressive et sous surveillance renforcée.
- **Visuel suggéré** : Triptyque incendie de cuisine : porte fermée / extincteur en action / cuisine rénovée.
  - **alt-text** : Les trois temps opérationnels de la réponse illustrés par un incendie domestique.

---

### Slide 11 — La règle d'or de la RAM
- **Type** : contenu
- **Points clés (bullets)** :
  - ❌ **Ne jamais éteindre** une machine compromise — la RAM volatile contient : processus actifs, connexions, adresses des attaquants… parfois **la clé de chiffrement**
  - ❌ Ne pas redémarrer (risque de chiffrement du démarrage) · ne pas « nettoyer »
  - ✅ **Isoler du réseau, laisser allumé** — ordre de volatilité : RAM → réseau → disques (copie) → journaux déportés (B17)
  - ⚖️ Plainte sous **72 h** pour l'indemnisation assurantielle (LOPMI 2023, vu en B02)
- **Notes orateur** : Le réflexe instinctif est l'erreur. Éteindre = passer l'éponge sur la scène de crime. Les journaux déportés de B17 sont déjà en lieu sûr — la RAM, elle, ne survit qu'à une condition : le courant. Transition : « testons ça à chaud — lundi, 10h04, le téléphone sonne. »
- **Visuel suggéré** : Barrette de RAM posée comme une pièce à conviction sous scellé numéroté.
  - **alt-text** : La mémoire vive comme preuve à préserver en priorité.

---

### Slide 12 — 🤔 L'appel du lundi matin & la fiche réflexe
- **Type** : étude de cas
- **Points clés (bullets)** :
  - 🤔 « Mon écran affiche une demande de rançon ! » — A) Éteindre B) **Isoler, laisser allumé, escalader** ✅ C) Redémarrer
  - 💬 Puis, ensemble : les **5 étapes** de la fiche réflexe helpdesk (une par message dans le chat)
  - Modèle : isoler → maintenir l'alimentation → collecter (heure, photo, derniers fichiers) → escalader [CRITIQUE] → consigner
  - Les 3 qualités d'une fiche : zéro jargon · interdits explicites (ne pas éteindre, **ne pas payer**) · escalade nominative
- **Notes orateur** : Mini-scénario d'abord (débrief : les trois gestes dans l'ordre), puis co-rédaction : récolter les étapes dans le chat, écrire la fiche en direct, comparer au modèle du support. Rappeler la position constante de l'ANSSI : ne pas payer (B02).
- **Visuel suggéré** : Combiné téléphonique + fiche réflexe à cinq cases numérotées se remplissant.
  - **alt-text** : Scénario d'appel d'urgence et fiche réflexe premier répondant.
- **Élément interactif** : Scénario A/B/C dans le chat, puis co-rédaction de la fiche par le chat.

---

### Slide 13 — 📊 Votre plan, le quiz & le bonus
- **Type** : quiz
- **Points clés (bullets)** :
  - 📊 **n°5 (opinion)** : votre organisation a-t-elle un plan de réponse ? (Testé / Papier / Non-je ne sais pas)
  - 📊 **n°6** : CVE vs CWE ? → le cas déclaré vs la maladie en général
  - 📊 **n°7** : rançongiciel actif : premier geste ? → isoler SANS éteindre
  - 📊 **n°8** : pourquoi ne jamais éteindre ? → la RAM volatile (preuves, parfois la clé)
  - 📊 **n°9 (bonus)** : correctif urgent vs production ? → pilote 24 h puis déploiement en anneaux
- **Notes orateur** : N°5 sans bonne réponse — repère : un plan jamais testé est une hypothèse (IBM CODB : plan testé = violations moins coûteuses), teaser direct de B19. Quiz : débrief 30 s chacun (éléments dans le support). N°9 = tampon : le couper si retard.
- **Visuel suggéré** : Cinq cartes de vote alignées, la première marquée « opinion », la dernière « bonus ».
  - **alt-text** : Les sondages de fin de session, de l'opinion au bonus.
- **Élément interactif** : Sondages Livestorm n°5 à 8 (+ n°9 bonus).

---

### Slide 14 — Synthèse, devoirs & prochaine session
- **Type** : récap
- **Points clés (bullets)** :
  - Prioriser = gravité × exposition · isoler sans éteindre · faire le REX
  - Equifax : une faille connue, un correctif disponible, 700 M$ de négligences ordinaires
  - Self-paced : IBM SkillsBuild *"Incident Response Fundamentals"* (~1h30) + votre liste : les 4-5 fonctions de VOTRE cellule de crise
  - Prochaine session (B19) : on ne prend plus de notes — on **vit** une crise (exercice sur table interactif)
- **Notes orateur** : Boucler la session, donner les devoirs (la liste de cellule de crise sert dès l'ouverture de B19). Teaser : « le scénario se déroulera en temps réel, et c'est vous qui prendrez chaque décision, par sondages. Rendez-vous en cellule de crise. » Terminer à l'heure.
- **Visuel suggéré** : Porte de salle de crise entrouverte, lumière allumée, badge SkillsBuild en coin.
  - **alt-text** : Synthèse de la session et invitation à la simulation de crise B19.
- **Élément interactif** : Question chat de clôture (« un mot retenu »).
