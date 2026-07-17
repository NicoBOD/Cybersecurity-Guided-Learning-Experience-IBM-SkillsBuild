# Spécifications des slides — Session B19 : Simulation de crise cyber (Tabletop)
Parcours : B 20 sessions  |  Module : E — Opérations, détection & réponse  |  Format : Spécifications Markdown

> **Principe** : texte affiché minimal (mots-clés, chiffres, injects horodatés) ; le discours complet est dans le [plan de séance minuté](../plans-de-seance/B_S19_plan.md). Les slides 9 à 12 portent la dramaturgie de l'exercice : les afficher au moment exact des injects.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Simulation de crise cyber — Tabletop exercise
  - Ce soir, pas de cours : **vous êtes la cellule de crise**
  - Parcours B — Session B19
- **Notes orateur** : Accueil. Annoncer le format : une simulation en temps réel, chaque décision par vote, les arguments par le chat. B18 a donné la méthode ; ce soir, on la met sous pression.
- **Visuel suggéré** : Table de crise vue de dessus, téléphone décroché, horloge affichant 7h55.
  - **alt-text** : Salle de cellule de crise prête pour la simulation.

---

### Slide 2 — Le devoir de la semaine & objectifs
- **Type** : contenu
- **Points clés (bullets)** :
  - 💬 Chat : votre liste — les **4-5 fonctions** de votre cellule de crise ?
  - Objectifs : expliquer un tabletop (MJ, injects, RETEX) · décider sous pression (opérationnel, juridique, communication) · construire un communiqué conforme.
  - Parcours : théorie éclair → Hydro & Maersk → **la crise GigaVolt** (3 décisions + communiqué) → RETEX → quiz.
- **Notes orateur** : Récolter les listes, regrouper : Direction, IT, juridique/DPO, communication. Message clé : l'informatique n'y est pas seule — une crise cyber est un problème d'entreprise à déclencheur informatique.
- **Visuel suggéré** : Quatre chaises autour d'une table, étiquetées Direction / IT / Juridique / Communication.
  - **alt-text** : Les quatre fonctions de la cellule de crise autour de la table.
- **Élément interactif** : Question chat (réinvestissement du devoir de B18).

---

### Slide 3 — 📊 Sondage n°1 : le prix de la préparation
- **Type** : sondage
- **Points clés (bullets)** :
  - Économie moyenne sur le coût d'une violation, avec équipe de réponse ET plan **testé** ?
  - A) ~250 000 $ — B) ~1 M$ — C) ~2,66 M$
  - Source : IBM, *Cost of a Data Breach*, 2022
- **Notes orateur** : Réponse C. Le mot-clé : TESTÉ — un plan jamais exercé est une hypothèse. « Sous stress, on ne s'élève pas au niveau de ses ambitions : on retombe au niveau de son entraînement. » Enchaîner : alors entraînons-nous.
- **Visuel suggéré** : Deux colonnes de coût comparées, l'écart de 2,66 M$ surligné.
  - **alt-text** : Écart de coût d'une violation selon le niveau de préparation.
- **Élément interactif** : Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — Le tabletop : la crise sans les dégâts
- **Type** : contenu
- **Points clés (bullets)** :
  - Simulation **théorique** : zéro impact sur la production
  - Le **maître du jeu** anime et lance des **injects** (rebondissements ciblés)
  - Teste : les playbooks (B18) · la décision sous incertitude · la coordination technique/non-technique
  - Règle d'or : un bon exercice **révèle des failles** — s'il est parfait, il était trop facile
- **Notes orateur** : L'analogie de l'exercice d'évacuation incendie : on ne met pas le feu, on teste les réflexes — et « l'escalier B est bloqué » est un inject. Mentionner le guide ANSSI (2021) pour ceux qui voudront en organiser un.
- **Visuel suggéré** : Plateau de jeu stylisé avec cartes « inject » face cachée et sablier.
  - **alt-text** : L'exercice de crise représenté comme un jeu de plateau sérieux.

---

### Slide 5 — La cellule de crise : qui décide de quoi
- **Type** : schéma
- **Points clés (bullets)** :
  - **Direction** : décide et assume (moyens d'urgence, payer ou non, déconnecter ou non — B13)
  - **IT/Sécurité** : éclaire — diagnostic, confinement, délais de restauration
  - **Juridique/DPO** : qualifie — CNIL **72 h** (B15) · plainte **72 h** (LOPMI, B02) · assureur (B14)
  - **Communication** : cadre — interne (couper les rumeurs) et externe (une seule voix)
- **Notes orateur** : Comparer avec les listes du chat. Insister sur la répartition : l'IT propose, la Direction décide, le juridique borne, la comm porte. Les deux « 72 h » ne sont pas les mêmes : notification CNIL et plainte assurantielle.
- **Visuel suggéré** : Table ronde à quatre secteurs colorés, une flèche « décision » convergeant vers la Direction.
  - **alt-text** : Répartition des responsabilités au sein de la cellule de crise.

---

### Slide 6 — Les 4 règles d'or de la communication de crise
- **Type** : contenu
- **Points clés (bullets)** :
  - 1. **Les faits** — jamais de mensonge, de spéculation, de coupable désigné sans preuve
  - 2. **Une voix** — porte-parole unique ; les salariés ne s'expriment pas (ni presse, ni réseaux)
  - 3. **L'empathie** — reconnaître, regretter, détailler les mesures engagées
  - 4. **La transparence contrôlée** — expliquer sans livrer de détails techniques exploitables
- **Notes orateur** : « Une mauvaise communication peut coûter plus cher que l'attaque. » Prévenir : dans une heure, un journaliste appellera — ces quatre règles seront votre grille de réponse.
- **Visuel suggéré** : Quatre pictogrammes alignés : balance (faits), mégaphone unique, main tendue, rideau entrouvert.
  - **alt-text** : Les quatre règles fondamentales de la communication de crise.

---

### Slide 7 — Affaire réelle : Norsk Hydro (2019)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - LockerGoga, 4h du matin — 35 000 salariés, 40 pays
  - Trois décisions en heures : **isoler massivement** (22 000 postes hors ligne) · **refuser de payer** · **transparence totale** (points presse quotidiens)
  - Usines en **mode manuel** : les classeurs papier ressortent
  - ~**70 M$** (chiffres de l'entreprise, 2019) — et une réputation **renforcée**
- **Notes orateur** : Le cas d'école mondial de la crise bien gérée. Les trois décisions dures étaient possibles parce que PRÉPARÉES : le mode manuel existait (PCA, B12), la position rançon était claire. La transparence a inversé le rapport de force médiatique : pas de rumeur à démentir, l'entreprise racontait sa propre histoire.
- **Visuel suggéré** : Usine d'aluminium avec opérateurs consultant des classeurs papier, conférence de presse en médaillon.
  - **alt-text** : Norsk Hydro en mode manuel pendant la crise LockerGoga.

---

### Slide 8 — Le cas revisité : Maersk (2017), côté cellule de crise
- **Type** : étude de cas
- **Points clés (bullets)** :
  - NotPetya (l'attaque vue en B03) — ici : la **reconstruction**
  - **10 jours** : ~4 000 serveurs et 45 000 postes reconstruits · ~**300 M$** déclarés (2017)
  - Sauvé par une copie d'annuaire survivante… au **Ghana** (coupure de courant)
  - ~80 % d'activité maintenue en mode dégradé improvisé
- **Notes orateur** : Le miroir de Hydro : l'improvisation héroïque a sauvé Maersk — une fois, et par chance. Une communication hors bande et des sauvegardes hors ligne préparées auraient coûté infiniment moins cher que ce coup de chance. Transition : « fermez vos notes. 7h55. Votre téléphone sonne. »
- **Visuel suggéré** : Porte-conteneurs à quai, un unique serveur allumé sur un planisphère au niveau du Ghana.
  - **alt-text** : La reconstruction de Maersk à partir d'un unique contrôleur de domaine survivant.

---

### Slide 9 — 🧪 CRISE — Inject 1 (lundi, 7h55)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **GigaVolt** — PME, 120 salariés, distribution de matériel électrique
  - 7h55, l'astreinte : « l'AD ne répond plus · extensions `.lokd` · écran de rançon »
  - 8h00 : la logistique démarre dans 30 minutes — plus un bon de livraison ne s'imprime
  - **Vous êtes la cellule de crise. À vous.**
- **Notes orateur** : Ton maître du jeu assumé. Lire l'inject, laisser 20 secondes de silence — le stress fait partie de l'exercice. Rappeler le fonctionnement : chaque décision = un vote, les arguments = le chat.
- **Visuel suggéré** : Écran de rançon stylisé (sans marque réelle) sur fond d'entrepôt à l'arrêt, horodatage « 07:55 » en surimpression.
  - **alt-text** : Début de la simulation : rançongiciel détecté chez GigaVolt à 7h55.

---

### Slide 10 — 📊 Décisions 1 & 2 : confiner, alerter
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **n°2 — 8h00, première action ?** A) Redémarrer les serveurs B) **Confiner sans éteindre + activer la cellule** ✅ C) Contacter les attaquants
  - 📊 **n°3 — 8h30, qui prévenir dans l'heure ?** A) L'IT seulement B) **Cellule complète + assureur + prestataire** ✅ C) Tous les clients immédiatement
  - 💬 Piège : la messagerie est chiffrée — vous les prévenez **comment ?**
- **Notes orateur** : N°2 : redémarrer détruit la RAM (B18) ; confiner = segments isolés, accès distants coupés, machines allumées — et activer la cellule est une ACTION. N°3 : l'IT seule = décisions juridiques et comm en retard ; les clients tout de suite = paniquer avant de savoir. La question piège amène la communication hors bande : annuaire imprimé, téléphones personnels, messagerie externe convenue — préparés AVANT.
- **Visuel suggéré** : Deux cartes de décision côte à côte avec minuteur, pictogramme « réseau coupé, machine allumée ».
  - **alt-text** : Les deux premières décisions de la cellule de crise GigaVolt.
- **Élément interactif** : Sondages Livestorm n°2 et n°3 + question chat.

---

### Slide 11 — 🕙 Inject 2 (10h30) : la rançon
- **Type** : sondage
- **Points clés (bullets)** :
  - E-mail sur la boîte **personnelle** du dirigeant : « **500 000 €** ou publication des données clients — 48 h » (double extorsion, B02)
  - Info RSSI : les sauvegardes de la veille sont **saines et hors ligne** (B12)
  - 📊 **n°4 — Payer ?** A) Payer discrètement B) **Non : plainte (72 h), notification CNIL préparée (72 h), restauration après éradication** ✅ C) Ignorer sans plainte ni notification
- **Notes orateur** : Débrief long (le cœur de l'exercice) : payer ne garantit rien (Colonial Pipeline a payé ET restauré sur sauvegardes), finance l'écosystème, signale un payeur ; « discrètement » est illusoire, la fuite est réelle → CNIL. C est la pire option : sans plainte sous 72 h, l'indemnisation saute (LOPMI 2023) ; sans notification, l'amende s'ajoute. Si débat : négocier pour gagner du temps n'est pas payer ; la position se fixe À FROID.
- **Visuel suggéré** : Compte à rebours « 48:00:00 » au-dessus de trois cartes de décision, coffre de sauvegardes intact en arrière-plan.
  - **alt-text** : La décision de la rançon sous compte à rebours.
- **Élément interactif** : Sondage Livestorm n°4.

---

### Slide 12 — 🕑 Inject 3 (14h00) : le journaliste — et le communiqué
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Un journaliste a vu vos données sur un forum · un salarié tweete « on est piratés ! »
  - 🤔 **Que lui répondez-vous ?** A) Nier B) **Reconnaître factuellement, annoncer un communiqué, renvoyer au porte-parole** ✅ C) Tout détailler
  - 💬 Puis, ensemble : le communiqué en 6 blocs — faits · mesures · touché/pas touché · CNIL + clients · regrets · **contact presse unique**
- **Notes orateur** : Mini-scénario d'abord (débrief : nier alors qu'il A les données = le mensonge devient l'histoire ; tout détailler = spéculation + infos exploitables ; le tweet rappelle : consigne de silence dès la première heure). Puis co-construction : récolter les blocs dans le chat, assembler en direct, afficher le modèle du support. Souligner le bloc 3 : dire ce qui n'a PAS été volé compte autant.
- **Visuel suggéré** : Combiné téléphonique tendu au-dessus d'une page de communiqué à six blocs vides à remplir.
  - **alt-text** : L'appel du journaliste et le squelette du communiqué de crise.
- **Élément interactif** : Scénario A/B/C dans le chat, puis co-rédaction du communiqué par le chat.

---

### Slide 13 — 📊 L'opinion, le RETEX, le quiz & le bonus
- **Type** : quiz
- **Points clés (bullets)** :
  - 📊 **n°5 (opinion)** : sous pression réelle, votre organisation paierait-elle ? (Oui / Non / Aucune idée)
  - 💬 **RETEX à chaud** : la décision la plus difficile + une chose à préparer à l'avance
  - 📊 **n°6** : un « inject » ? → le rebondissement ciblé du MJ · 📊 **n°7** : ordre de reprise ? → éradiquer PUIS restaurer · 📊 **n°8** : qui parle ? → le porte-parole unique
  - 📊 **n°9 (bonus)** : pourquoi ne pas réinstaller immédiatement ? → préserver les traces
- **Notes orateur** : N°5 : « aucune idée » est la réponse la plus utile — la décision n'a jamais été préparée. RETEX : regrouper les propositions (annuaire de crise, hors bande, position rançon écrite, sauvegardes testées, porte-parole) — « cette liste EST le livrable d'un vrai exercice ». Quiz : débrief 30 s chacun. N°9 = tampon.
- **Visuel suggéré** : Tableau de RETEX à deux colonnes (« difficile » / « à préparer ») entouré des cartes de quiz.
  - **alt-text** : Le retour d'expérience et les sondages de validation de fin de session.
- **Élément interactif** : Sondages Livestorm n°5 à 8 (+ n°9 bonus) + RETEX par le chat.

---

### Slide 14 — Synthèse, devoirs & prochaine session
- **Type** : récap
- **Points clés (bullets)** :
  - Ce soir : confiner sans détruire · alerter par les bons canaux · refuser sous pression · parler d'une seule voix · transformer l'exercice en plan d'action
  - Self-paced : terminer le cursus IBM SkillsBuild + récupérer ses badges · **réviser les modules A→E et les 4 Ateliers de Synthèse**
  - Prochaine session (B20) : le **Grand Atelier d'Audit MedDistri** — l'audit complet d'une PME, voté et construit ensemble
  - « Sous stress, on retombe au niveau de son entraînement. »
- **Notes orateur** : Boucler : le RETEX du chat est le vrai livrable. Devoirs : la révision générale prépare B20 qui mobilisera TOUT le parcours. Teaser : « architecture, comptes, sauvegardes, gouvernance — vous auditerez tout, vous voterez les constats, vous construirez le plan de remédiation. La boucle sera bouclée. » Terminer à l'heure.
- **Visuel suggéré** : Loupe posée sur le logo MedDistri, badges SkillsBuild alignés en bas.
  - **alt-text** : Annonce du Grand Atelier d'Audit final et rappel des devoirs.
- **Élément interactif** : Question chat de clôture (« un mot retenu »).
