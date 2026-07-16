# Spécifications des slides — Session B16 : Centre des opérations de sécurité (SOC) & supervision
Parcours : B 20 sessions  |  Module : E — Opérations de sécurité  |  Format : Spécifications Markdown

> **Principe** : le texte affiché reste minimal (mots-clés, chiffres, schémas) ; le contenu riche est dans les notes orateur et le [plan de séance minuté](../plans-de-seance/B_S16_plan.md). Toutes les interactions passent par les sondages et le chat Livestorm.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - SOC & supervision
  - Qui regarde les écrans — et à quelle vitesse ?
  - Parcours B — Session B16 · Ouverture du module Opérations de sécurité
- **Notes orateur** : Accueillir : la gouvernance a décidé, les défenses sont posées — qui regarde ? Retour self-paced : « en une phrase dans le chat : c'est quoi, un SOC ? » (le SIEM, son outil, c'est la semaine prochaine). Rappel B15 : RGPD, 72 h, Atelier 3. Annonce : les trois niveaux, l'art de qualifier, les deux chronomètres — et l'alerte banale qui a révélé l'attaque de la décennie.
- **Visuel suggéré** : Salle de supervision aux écrans muraux, silhouettes d'analystes devant des cartes de flux.
  - **alt-text** : Salle d'un centre d'opérations de sécurité avec écrans de supervision et analystes.
- **Élément interactif** : 💬 Chat d'accueil — le SOC en une phrase.

---

### Slide 2 — Objectifs & agenda
- **Type** : contenu
- **Points clés (bullets)** :
  - Décrire l'organisation du SOC : L1, L2, L3 — et l'option MSSP.
  - Qualifier une alerte par le contexte : vrai ou faux positif.
  - Interpréter MTTD et MTTR — et les réduire (playbooks, SOAR).
  - Agenda : les 3 niveaux → le cycle d'alerte → les KPIs → la garde de nuit → SolarWinds → quiz.
- **Notes orateur** : Le fil rouge : une alerte ne vaut que par l'humain (ou le playbook) qui la traite. Deux histoires jumelles aux fins opposées le prouveront — Target et SolarWinds.
- **Visuel suggéré** : Deux colonnes présentant les objectifs et l'agenda de la séance.
  - **alt-text** : Tableau présentant les objectifs d'apprentissage et les étapes de la session.

---

### Slide 3 — Brise-glace : la course de 62 minutes
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **Sondage n°1** : temps moyen entre l'intrusion et le début du mouvement latéral ?
  - A) ~1 heure — B) ~1 jour — C) ~1 semaine
- **Notes orateur** : Lancer le sondage n°1 (60-90 s). Réponse A : 62 minutes en moyenne (CrowdStrike 2024), record ~2 minutes. Une heure : la fenêtre du défenseur entre « il est entré » et « il se propage » (B06). Toute la sécurité opérationnelle est une course contre ce chronomètre.
- **Visuel suggéré** : Chronomètre géant affichant 62:00 avec une silhouette d'intrus progressant entre deux serveurs.
  - **alt-text** : Chronomètre de 62 minutes illustrant le délai moyen avant le mouvement latéral d'un attaquant.
- **Élément interactif** : 📊 Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — Le SOC : les urgences de l'entreprise
- **Type** : schéma
- **Points clés (bullets)** :
  - **L1 — l'infirmier de tri** : qualifier le flux, escalader documenté.
  - **L2 — le médecin de garde** : investiguer (l'EDR en microscope), prescrire.
  - **L3 — le chirurgien** : les crises majeures + le **threat hunting**.
  - 24/7 = 8 à 10 analystes minimum → le **MSSP** pour les PME.
- **Notes orateur** : Dérouler l'analogie des urgences avec la relance chat : « qui est l'infirmier, le médecin, le chirurgien ? » Le threat hunting : chercher par hypothèses (les TTP de B02-B03) ce qui n'a déclenché AUCUNE alerte — la réponse au « comment détecter un APT » posée depuis la Banque du Bangladesh. L'économie du 24/7 explique le MSSP : un SOC mutualisé, enrichi de CTI.
- **Visuel suggéré** : Service d'urgences stylisé à trois postes (tri, consultation, bloc) avec des écrans d'alertes à la place des patients.
  - **alt-text** : Urgences hospitalières transposées en centre de sécurité avec les trois niveaux d'analystes.
- **Élément interactif** : 💬 Chat — l'analogie des urgences.

---

### Slide 5 — Le cycle d'une alerte : vrai ou faux positif ?
- **Type** : contenu
- **Points clés (bullets)** :
  - Événement brut → règle → alerte → **qualification**.
  - **FP** : le légitime qui ressemble à une attaque (l'outil d'inventaire qui scanne).
  - **VP** : la menace avérée — intervention immédiate.
  - ⚠️ **Fatigue des alertes** : 44 % jamais investiguées (Cisco, 2017).
- **Notes orateur** : L'arme du L1 : le CONTEXTE — qui, où, quand, est-ce habituel ? Question rhétorique : une connexion à 3h du matin est-elle suspecte ? Ça dépend — de qui, d'où, sur quoi. La fatigue des alertes est le danger silencieux : noyé sous les FP, on traite superficiellement et on rate le VP — Target en démonstration tout à l'heure.
- **Visuel suggéré** : Entonnoir d'événements se réduisant en alertes, avec un aiguillage FP (classé) / VP (escaladé) et un analyste submergé en arrière-plan.
  - **alt-text** : Entonnoir de tri des alertes de sécurité entre faux positifs classés et vrais positifs escaladés.

---

### Slide 6 — MTTD & MTTR : les deux chronomètres
- **Type** : schéma
- **Points clés (bullets)** :
  - **MTTD** : de l'intrusion → à la détection.
  - **MTTR** : de la détection → à la neutralisation.
  - Détecter en 30 s ne sert à rien si l'on réagit en 24 h.
  - **Playbooks** (la réaction écrite) + **SOAR** (la réaction automatisée, en secondes).
- **Notes orateur** : Question rhétorique : lequel améliore-t-on avec des processus plutôt que des outils ? Le MTTR, largement. Les playbooks incluent la vérification humaine des alertes « banales mais sensibles » (MFA, comptes à privilèges — SolarWinds arrive). Le SOAR : IP malveillante contactée → isolement EDR automatique, même à 3h du matin (l'exercice bonus).
- **Visuel suggéré** : Frise d'un incident avec deux chronomètres : intrusion→détection (MTTD) et détection→neutralisation (MTTR).
  - **alt-text** : Frise temporelle d'un incident illustrant les métriques MTTD et MTTR.

---

### Slide 7 — Activité : la garde de nuit du L1
- **Type** : activité (sondages)
- **Points clés (bullets)** :
  - Trois alertes sur votre console — qualifiez et décidez.
  - 📊 **Sondage n°2** : SSH nocturne depuis l'Asie sur la paie ? · 📊 **n°3** : 80 échecs puis connexion ? · 📊 **n°4** : PowerShell qui exfiltre ?
- **Notes orateur** : Afficher chaque alerte AVEC son contexte, 30 s de lecture, vote, débrief : n°2 — faisceau d'indices (serveur sensible + heure + géoloc + aucun ticket) : VP critique, escalade documentée (l'alerte de 2h non traitée, c'était Target) ; n°3 — le réflexe d'or : vérifier le contexte (annuaire, appel) : FP documenté ; n°4 — chaîne comportementale type : isoler D'ABORD (un poste coûte peu, la propagation coûte tout), investiguer ensuite. PowerShell légitime ? Oui — c'est pourquoi les attaquants l'adorent (B03).
- **Visuel suggéré** : Console de supervision affichant trois cartes d'alertes avec leurs contextes.
  - **alt-text** : Console d'analyste avec trois alertes de sécurité à qualifier pendant l'activité.
- **Élément interactif** : 📊 Sondages Livestorm n°2 à 4 — triage collectif.

---

### Slide 8 — Le paysage en chiffres
- **Type** : chiffres clés
- **Points clés (bullets)** :
  - **62 min** en moyenne avant le mouvement latéral — record : ~2 min (CrowdStrike, 2024).
  - **~18 000 organisations** touchées par la mise à jour piégée SolarWinds (2020).
  - **44 %** des alertes jamais investiguées (Cisco, 2017).
- **Notes orateur** : Trois lectures : la fenêtre de réaction se compte en minutes ; la plus grande attaque de la décennie a été découverte par UNE alerte vérifiée ; et le vrai risque du SOC n'est pas de manquer d'outils, mais de se noyer. Transition : l'histoire de cette alerte.
- **Visuel suggéré** : Trois grands chiffres en typographie XXL avec leurs sources et années en petit.
  - **alt-text** : Trois statistiques géantes sur la détection des intrusions avec leurs sources.

---

### Slide 9 — Affaire : SolarWinds (2020)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - L'alerte banale : un **2ᵉ téléphone MFA** enrôlé sur un compte VPN.
  - Le playbook : **appeler l'employé** — « ce n'est pas moi ».
  - La découverte : la mise à jour piégée de SolarWinds Orion (**chaîne d'approvisionnement**).
  - ~18 000 organisations · des agences fédérales · des **mois** sans aucune alerte.
- **Notes orateur** : Raconter : Mandiant, géant de la cybersécurité, compromis par un logiciel légitime ; l'analyste qui vérifie une alerte que 99 % des SOC auraient close ; la révélation publique et le partage des IoC (la CTI de B02 en action). Leçon : pas d'IA miraculeuse — un humain, un playbook, un contre-appel (le réflexe de B04, version SOC).
- **Visuel suggéré** : Un téléphone en surbrillance dans une mer d'alertes grises, relié à une carte mondiale d'organisations compromises.
  - **alt-text** : Une seule alerte de téléphone MFA mise en évidence révélant un réseau mondial de compromissions.

---

### Slide 10 — Le contre-exemple : Target, revisité
- **Type** : étude de cas
- **Points clés (bullets)** :
  - 2013 : les outils **détectent** · le SOC de Bangalore **remonte**...
  - ... et personne n'agit à Minneapolis : **40 millions de cartes**.
  - Mêmes ingrédients que SolarWinds — issue inverse.
  - La différence : le **processus de qualification et d'escalade**.
- **Notes orateur** : Le parallèle en deux minutes (cas complet vu en B06) : ni le budget ni les outils ne différencient les deux affaires — le processus, si. C'est tout l'objet des playbooks : écrire QUI fait QUOI quand l'alerte tombe, et vérifier que la chaîne fonctionne. Relance chat : « quel détail vous marque le plus ? »
- **Visuel suggéré** : Deux chaînes d'escalade côte à côte : l'une aboutit à une action, l'autre s'interrompt en pointillés.
  - **alt-text** : Comparaison de deux chaînes de traitement d'alerte, l'une aboutie, l'autre interrompue.
- **Élément interactif** : 💬 Chat — réactions aux deux affaires.

---

### Slide 11 — Et chez vous ? La supervision
- **Type** : sondage (opinion)
- **Points clés (bullets)** :
  - 📊 **Sondage n°5** : votre organisation a-t-elle une supervision de sécurité ?
  - A) SOC interne — B) Externalisée (MSSP) — C) Aucune / je ne sais pas.
- **Notes orateur** : C est majoritaire dans les PME — le point aveugle : des défenses, personne qui regarde. La voie réaliste : le MSSP, en vérifiant trois clauses (contexte métier, délais garantis — le MTTR s'écrit dans le contrat, réversibilité). Une supervision partielle (EDR + astreinte) vaut mieux que rien. Enchaîner sur le mini-scénario de l'alerte MFA du vendredi soir : « tapez A, B ou C » (réponse B — désactiver l'appareil, suspendre, vérifier par un autre canal : c'est l'alerte SolarWinds, et le week-end est la fenêtre préférée des attaquants).
- **Visuel suggéré** : Trois salles : une salle de supervision animée, un écran de prestataire distant, une salle d'écrans éteints.
  - **alt-text** : Trois niveaux de supervision de sécurité, du SOC interne à l'absence totale de surveillance.
- **Élément interactif** : 📊 Sondage Livestorm n°5 (opinion) puis 🤔 mini-scénario en chat (A/B/C).

---

### Slide 12 — Quiz de validation
- **Type** : quiz (sondages)
- **Points clés (bullets)** :
  - 📊 **Sondage n°6** : la mission première du L1 ?
  - 📊 **Sondage n°7** : que mesurent MTTD et MTTR ?
  - 📊 **Sondage n°8** : ce qui distingue le threat hunting ?
- **Notes orateur** : Lancer les trois sondages à la suite (~2 min chacun), débriefs scriptés dans le support : le L1 trie, qualifie et escalade (ni héros, ni presse-bouton) ; les deux chronomètres vont ensemble ; le hunting part du principe que les outils ont raté quelque chose — hypothèse, traces, confirmation. Si le temps le permet, enchaîner sur le bonus n°9 (3h du matin, le SOAR).
- **Visuel suggéré** : Trois cartes de quiz numérotées 6, 7, 8 avec l'icône de sondage Livestorm.
  - **alt-text** : Trois cartes de questions de quiz numérotées, associées à des sondages en direct.
- **Élément interactif** : 📊 Sondages Livestorm n°6 à 8 (+ n°9 en tampon).

---

### Slide 13 — Synthèse & prochaine session
- **Type** : récap
- **Points clés (bullets)** :
  - Trois métiers · un art (qualifier par le contexte) · deux chronomètres.
  - Target et SolarWinds : la différence tenait en un geste — **vérifier**.
  - Self-paced : SkillsBuild *« SOC Fundamentals »* + la définition d'un log (horodatage, source, événement).
  - Prochaine session — B17 : le SIEM & l'analyse de logs + **Atelier de Synthèse 4**.
- **Notes orateur** : Faire écrire dans le chat UN mot retenu, en lire 4-5. Rappeler le devoir (la recherche sur les logs prépare directement B17). Teaser B17 : « la matière première du SOC : les journaux. Vous lirez de VRAIS logs d'attaque ligne par ligne — une seule ligne peut contenir toute une tentative de piratage. » Terminer à l'heure exacte.
- **Visuel suggéré** : Récapitulatif en trois vignettes (niveaux, qualification, chronomètres) et un panneau « B17 — Atelier » fléché.
  - **alt-text** : Synthèse en trois vignettes du fonctionnement du SOC avec un panneau annonçant la session B17.
- **Élément interactif** : Chat de clôture — « un mot que vous retenez ».
