# Plan de séance — Session B16 : Centre des opérations de sécurité (SOC) & supervision
Parcours : B 20 sessions  |  Module : E — Opérations de sécurité  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (verbes d'action)
- **Décrire** l'organisation d'un SOC moderne : les rôles L1 (triage), L2 (investigation), L3 (réponse & threat hunting), et l'option MSSP.
- **Qualifier** des alertes de sécurité (vrai vs faux positif) à partir du contexte, et documenter l'escalade.
- **Interpréter** les KPIs du SOC — MTTD et MTTR — et le rôle des playbooks et du SOAR pour les réduire.

## Prérequis & progression
- **Prérequis** : Modules B et C (les défenses à superviser) et D (la gouvernance qui les pilote).
- **Lien de progression** : Ouverture du module E — le SOC est l'organisation humaine de la détection ; B17 étudiera sa matière première (les journaux, le SIEM) avec l'Atelier de Synthèse 4.

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama B16 ([spécifications](../slides/B_S16_slides_spec.md)) — les trois fiches d'alertes de l'activité doivent être lisibles à l'écran.
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Temps moyen avant le mouvement latéral (CrowdStrike 2024) ? | A) Environ une heure |
| 2 | 0:46 | Sondage | Alerte A — SSH nocturne depuis l'Asie sur le serveur de paie ? | B) Vrai positif critique : escalade immédiate |
| 3 | 0:50 | Sondage | Alerte B — 80 échecs puis connexion (Verr Maj confirmé) ? | B) Faux positif documenté |
| 4 | 0:54 | Sondage | Alerte C — PowerShell exfiltrant vers l'extérieur ? | C) Vrai positif majeur : isoler puis escalader |
| 5 | 1:08 | Sondage | Votre organisation a-t-elle une supervision ? | Opinion (pas de bonne réponse) |
| 6 | 1:16 | Sondage | La mission première du L1 ? | B) Trier, qualifier, escalader |
| 7 | 1:18 | Sondage | Que mesurent MTTD et MTTR ? | A) Détection, puis neutralisation |
| 8 | 1:20 | Sondage | Ce qui distingue le threat hunting ? | C) Chercher ce qui n'a déclenché aucune alerte |
| 9 | Tampon | Sondage | Incident à 3h du matin, analyste absent : qui confine ? | B) Le playbook SOAR + EDR |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil, ouverture du module E & retour SOC/SIEM | 💬 Chat : définitions trouvées |
| 0:04–0:10 | Brise-glace : la course de 62 minutes | 📊 Sondage n°1 |
| 0:10–0:24 | Séquence 1 : Le SOC & ses trois niveaux | 💬 Chat : les urgences |
| 0:24–0:34 | Séquence 2 : Le cycle d'une alerte (FP/VP & fatigue) | Question rhétorique |
| 0:34–0:44 | Séquence 3 : MTTD, MTTR, playbooks & SOAR | Question rhétorique |
| 0:44–0:58 | Activité : La garde de nuit du L1 | 📊 Sondages n°2, 3, 4 |
| 0:58–1:08 | Chiffres clés & affaire SolarWinds (+ Target revisité) | 💬 Chat : réactions |
| 1:08–1:12 | Et chez vous ? La supervision | 📊 Sondage n°5 |
| 1:12–1:16 | Mini-scénario : l'alerte MFA du vendredi soir | 🤔 Chat : A, B ou C |
| 1:16–1:22 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:22–1:26 | Exercice bonus : 3h du matin (tampon) | 📊 Sondage n°9 |
| 1:26–1:30 | Synthèse, devoirs & teaser B17 | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & ouverture du module E

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous, et bienvenue dans le module Opérations de sécurité ! La gouvernance a décidé, les défenses sont posées — mais QUI regarde les écrans ? Votre recherche de la semaine : SOC et SIEM. En une phrase dans le chat : c'est quoi, un SOC ? »

**Points à dérouler :**
- Lire 2-3 définitions, valider : le centre d'opérations — l'équipe qui surveille et répond, 24/7. « Le SIEM, son outil principal, c'est la semaine prochaine. »
- Rappel express de B15 : le RGPD, les 72 h, l'Atelier 3.
- Annonce du programme : les trois niveaux d'analystes, l'art de qualifier une alerte, les deux chronomètres — et l'histoire de l'alerte banale qui a révélé l'attaque de la décennie.

**Transition scriptée :** « D'abord, mesurons l'urgence. Une question de vitesse. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (la course de 62 minutes)

**Consigne :** Lancer le **📊 Sondage n°1** — le temps moyen entre l'intrusion et le mouvement latéral. Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse A : 62 minutes en moyenne (CrowdStrike, 2024) — et le record observé est d'à peine plus de 2 minutes. Une heure : c'est votre fenêtre entre "l'attaquant est entré" et "l'attaquant se propage" — le mouvement latéral de B06. Toute la sécurité opérationnelle est une course contre ce chronomètre : détecter vite, qualifier juste, réagir plus vite encore. Bienvenue dans la tour de contrôle. »

**Transition scriptée :** « Et dans cette tour de contrôle, trois métiers bien distincts. »

### 0:10–0:24 — Séquence 1 : Le SOC & ses trois niveaux

**Points de contenu à dérouler (support §1) :**
- **Le SOC** : la tour de contrôle — humains + outils, surveillance, détection, réponse, 24/7.
- Dérouler l'**analogie des urgences** avec la relance chat : *« L1, L2, L3 : qui est l'infirmier de tri, le médecin de garde, le chirurgien ? »*
- **L1** : trier le flux, qualifier FP/VP, escalader documenté. **L2** : investiguer (processus, journaux, l'EDR de B08 en microscope), prescrire. **L3** : les crises majeures — et le ***threat hunting*** : chercher par hypothèses ce qui n'a déclenché AUCUNE alerte (la réponse au « comment détecter un APT » posée depuis la Banque du Bangladesh, B02).
- **L'économie du 24/7** : 3×8, week-ends, congés → 8 à 10 analystes minimum ; d'où le **MSSP** pour les PME (un SOC mutualisé, enrichi de CTI — les IoC d'un client protègent tous les autres).

**Transition scriptée :** « Le cœur du métier L1 tient en une question : cette alerte dit-elle vrai ? »

### 0:24–0:34 — Séquence 2 : Le cycle d'une alerte

**Points de contenu à dérouler (support §2) :**
- Le chemin : événement brut → règle de détection → alerte → **qualification**.
- **Faux positif** : l'activité légitime qui ressemble à une attaque — l'exemple de l'outil d'inventaire qui scanne le réseau.
- **Vrai positif** : la menace avérée — intervention immédiate.
- **La fatigue des alertes** : noyé sous les FP, on traite superficiellement... et on rate le VP. 44 % des alertes jamais investiguées (Cisco, 2017).
- L'arme du L1 : le **contexte** — qui, où, quand, est-ce habituel ? Question rhétorique : *« Une connexion à 3h du matin est-elle suspecte ? »* — ça dépend : de qui, d'où, sur quoi. Le contexte décide. (L'activité arrive.)

**Transition scriptée :** « Reste à mesurer la performance — deux chronomètres suffisent. »

### 0:34–0:44 — Séquence 3 : MTTD, MTTR, playbooks & SOAR

**Points de contenu à dérouler (support §3) :**
- **MTTD** : de l'intrusion à la détection. **MTTR** : de la détection à la neutralisation.
- **Les deux vont ensemble** : détecter en 30 secondes ne sert à rien si l'on réagit en 24 heures — le rançongiciel aura tout chiffré (62 minutes !). Question rhétorique : *« Lequel des deux améliore-t-on avec des processus plutôt qu'avec des outils ? »* — le MTTR, largement.
- **Les playbooks** : la réaction écrite à l'avance, par type d'alerte — y compris la vérification humaine des alertes « banales mais sensibles » (MFA, comptes à privilèges).
- **Le SOAR** : la réaction automatisée — IP malveillante contactée (IoC) → isolement EDR en secondes, même à 3h du matin (l'exercice bonus).

**Transition scriptée :** « Assez de théorie. Vous prenez la garde : trois alertes tombent sur votre console. »

### 0:44–0:58 — Activité : La garde de nuit du L1 (Sondages n°2 à 4)

**Consigne :** Afficher chaque alerte avec son contexte (support, activité « La garde de nuit »), 30 secondes de lecture, puis lancer les **📊 Sondages n°2, 3, 4** (~4-5 min chacun : lecture, vote, débrief).

**🎙️ Verbatim de lancement :**
> « Vous êtes l'analyste L1 de garde chez EcoLog. Alerte A : connexion SSH réussie sur le serveur de paie, 3h15 du matin, adresse IP en Asie. L'admin habite en France, aucun ticket nocturne. Votre qualification ? »

**Débriefs scriptés (points obligatoires) :**
- N°2 (VP critique) : le faisceau d'indices — serveur sensible + heure + géolocalisation + aucun ticket. Le L1 n'attend pas la certitude : il escalade avec un dossier propre. Rappel B06 : l'alerte de 2h du matin non traitée, c'était Target.
- N°3 (FP documenté) : le réflexe d'or — **vérifier le contexte** avant de trancher (l'annuaire, puis l'appel). Et on documente la clôture : un FP non documenté reviendra demain.
- N°4 (VP majeur → isoler) : la chaîne comportementale type (l'EDR de B08 est fait pour ça) ; isoler UN poste coûte peu, la propagation coûte tout — isoler D'ABORD, investiguer ensuite. « PowerShell est légitime » : oui — c'est précisément pourquoi les attaquants l'adorent (B03, *fileless*).

**Transition scriptée :** « Trois alertes, trois bonnes décisions. Voyons maintenant l'alerte la plus rentable de l'histoire de la cybersécurité. »

### 0:58–1:08 — Chiffres clés & affaire SolarWinds

**Chiffres (2 min, support §4) :** 62 minutes avant le mouvement latéral (CrowdStrike 2024) ; ~18 000 organisations touchées par la mise à jour piégée SolarWinds (2020) ; 44 % des alertes jamais investiguées (Cisco, 2017).

**Cas — SolarWinds/Mandiant, 2020 (6 min, support §5) :** raconter : l'alerte banale — un deuxième téléphone MFA enrôlé sur un compte VPN ; l'analyste qui applique le playbook et **appelle** l'employé (« ce n'est pas moi ») ; l'investigation qui révèle la compromission... par la mise à jour d'un logiciel légitime — SolarWinds Orion, piégé à la source (chaîne d'approvisionnement, comme NotPetya en B03) ; ~18 000 organisations, des agences fédérales, une centaine activement espionnées pendant des mois sans aucune alerte ; et Mandiant qui révèle publiquement et partage les IoC (la CTI de B02 en action).

**Le contre-exemple — Target revisité (2 min) :** mêmes ingrédients en 2013 — les outils détectent, le SOC de Bangalore remonte... et personne n'agit à Minneapolis : 40 millions de cartes. La différence entre les deux affaires ne tient ni au budget ni aux outils : elle tient au **processus de qualification et d'escalade**. Relance chat : *« Quel détail vous marque le plus ? »*

### 1:08–1:12 — Sondage n°5 : et chez vous, la supervision ?

**Consigne :** Lancer le **📊 Sondage n°5** (opinion) — votre organisation a-t-elle une supervision de sécurité ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « C est majoritaire dans les PME — c'est le point aveugle : des défenses, mais personne qui regarde. La voie réaliste pour une PME, c'est le MSSP — en vérifiant trois choses au contrat : la connaissance de VOTRE contexte métier, les délais de réaction garantis (le MTTR s'écrit dans le contrat), et la réversibilité. Et une supervision même partielle — les alertes EDR plus une astreinte — vaut infiniment mieux que rien. »

### 1:12–1:16 — 🤔 Mini-scénario : l'alerte MFA du vendredi soir

**Consigne :** Afficher le mini-scénario du support : vendredi 17h50, « nouvel appareil MFA enrôlé » sur un compte admin, l'utilisateur ne répond pas. *« Tapez A, B ou C dans le chat. »*

**Débrief :** B — c'est mot pour mot l'alerte qui a révélé SolarWinds, et le week-end est la fenêtre préférée des attaquants (le vendredi soir du BEC, B04). Le calcul : désactiver un appareil MFA coûte cinq minutes et un désagrément lundi ; un attaquant équipé d'un MFA valide pendant 60 heures coûte potentiellement l'entreprise (62 minutes suffisent). A parie l'entreprise sur une probabilité ; C offre le week-end à l'adversaire.

**Transition scriptée :** « Trois questions pour valider votre prise de garde. »

### 1:16–1:22 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : le L1 trie, qualifie et escalade ; MTTD = détection, MTTR = neutralisation ; le threat hunting cherche ce qui n'a déclenché aucune alerte. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/B_S16_support.md).

### 1:22–1:26 — Exercice bonus (Sondage n°9) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°9** — incident à 3h du matin, analyste absent : qui confine ? Débrief : le playbook SOAR + EDR (B) — l'automatisation protège quand l'humain dort ; le pare-feu local (A) laisse passer ce qu'il ne connaît pas ; redémarrer (C) détruit des preuves sans confiner — teaser B19 : préserver la mémoire vive. À couper en cas de retard.

### 1:26–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Ce soir : trois métiers — trier, investiguer, résoudre ; un art — qualifier par le contexte ; deux chronomètres — détecter et neutraliser ; et deux histoires jumelles aux fins opposées — Target et SolarWinds. La différence tenait en un geste : vérifier. Un mot que vous retenez, dans le chat ! »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Self-paced : cours IBM SkillsBuild *"Security Operations Center (SOC) Fundamentals"* (~1h30) + recherche : qu'est-ce qu'un log (journal d'événements) et ses trois éléments obligatoires (horodatage, source, événement) — préparation directe de B17.
- Teaser B17 : « la semaine prochaine : la matière première du SOC — les journaux. Vous lirez de VRAIS logs d'attaque ligne par ligne, avec l'Atelier de Synthèse 4. Indice : une seule ligne de log peut contenir toute une tentative de piratage. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**Exercice bonus n°9** (1:22–1:26) — il est dans le support en exercice bonus.
2. Compresser le contre-exemple Target à 1 min (le parallèle en une phrase).
3. Raccourcir le débrief du sondage n°5 à 1 min.
4. Ne JAMAIS couper : l'activité de triage, le cas SolarWinds, le quiz.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°3 : ce que SolarWinds implique pour la conception des playbooks).
2. Faire qualifier par le chat une 4ᵉ alerte improvisée (ex. un compte de service qui se connecte depuis un poste bureautique).
3. Questions/réponses libres.

## Travail en autonomie (Self-paced)
* **Avant la session suivante (B17)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Security Operations Center (SOC) Fundamentals"* (durée estimée : 1h30).
  * **Recherche autonome** : Trouver la définition d'un log système (journal d'événements) et identifier les trois éléments obligatoires devant figurer dans chaque ligne de log (horodatage, source, événement).
