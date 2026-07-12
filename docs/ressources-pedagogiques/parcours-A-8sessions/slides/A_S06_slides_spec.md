# Spécifications des slides — Session 06 : Opérations de sécurité & gestion des vulnérabilités
Parcours : A 8 sessions  |  Module : SecOps & Vulnérabilités  |  Format : Spécifications Markdown  |  Modalité : Webinaire Livestorm

> **Principe directeur** : le texte affiché reste minimal ; le contenu riche est dans les notes du présentateur et dans le [plan d'animation minuté](../plans-de-seance/A_S06_plan.md), qui fait référence pour les verbatims et débriefs. Les numéros de sondages renvoient à la checklist Livestorm du plan.

---

## Slide 1 : Page de garde
* **Layout** : Titre (Emphase visuelle, fond sombre)
* **Texte affiché sur la slide** :
  * **Opérations de Sécurité & Gestion des Vulnérabilités**
  * Parcours A — Session 06
  * *Surveiller les signaux faibles, identifier les faiblesses logicielles et prioriser les correctifs*
  * Nom du Mentor / IBM SkillsBuild
* **Visuels suggérés** : Une salle de contrôle sombre avec des écrans de surveillance géants affichant des graphiques et des alertes de sécurité (style SOC). Logo officiel dans un angle.
* **Notes du présentateur** :
  * Accueillir ; retour devoirs A5 dans le chat : « la finalité la plus surprenante trouvée dans une politique de confidentialité ? » — lire 2-3 réponses.
  * Pivot : « le chrono des 72 h d'A5 ne démarre que si quelqu'un VOIT la fuite. Aujourd'hui : comment on voit. »

---

## Slide 2 : Objectifs de la séance & Sommaire
* **Layout** : Deux colonnes (Gauche : Objectifs, Droite : Sommaire)
* **Texte affiché sur la slide** :
  * **Nos objectifs aujourd'hui** :
    * Comprendre la chaîne de détection : logs → SIEM → SOC.
    * Distinguer scan de vulnérabilités et test d'intrusion.
    * Interpréter un score CVSS et le pondérer par l'exposition.
    * Gérer les correctifs sans casser la production.
  * **Sommaire de la séance** :
    * 1. Brise-glace : le déluge de failles (6 min)
    * 2. Logs, SIEM, SOC (18 min)
    * 3. Activité : L'Analyste SOC (14 min)
    * 4. Scan vs Pentest & CVSS (10 min)
    * 5. Démo : lire une attaque dans les logs (8 min)
    * 6. Gestion des correctifs (8 min)
    * 7. Cas réels Equifax & Log4Shell, quiz & synthèse (26 min)
* **Visuels suggérés** : Icônes cibles pour les objectifs et icône de liste pour le sommaire.
* **Notes du présentateur** :
  * Annoncer la promesse : « à la fin, vous saurez trier les alertes et les failles comme un professionnel ».
  * Rythme : un sondage ou une question chat toutes les 8 minutes environ.

---

## Slide 3 : Brise-glace — Le déluge de failles
* **Layout** : Plein écran interactif (sondage)
* **Texte affiché sur la slide** :
  * **📊 Sondage n°1 — À votre avis...**
  * *Combien de nouvelles vulnérabilités (CVE) ont été publiées dans le monde en 2024 ?*
    * A) ~4 000  ·  B) ~15 000  ·  C) ~40 000  ·  D) ~500
  * (Réponse révélée après le vote)
* **Visuels suggérés** : Compteur qui défile ; après le vote, « ~40 000 » en très grand avec « > 100 par jour » en dessous.
* **Notes du présentateur** :
  * Lancer le sondage n°1, laisser 60-90 s.
  * Débrief : réponse C — record historique. Message clé : personne ne peut tout corriger ; la sécurité opérationnelle est une affaire de PRIORISATION, pas de perfection.

---

## Slide 4 : Les caméras que personne ne regarde
* **Layout** : Plein écran interactif (chat)
* **Texte affiché sur la slide** :
  * **💬 Dans le chat : un centre commercial installe 200 caméras dernier cri... mais n'embauche personne au PC sécurité.**
  * *Que valent ces caméras ? Et à quoi serviront-elles quand même, après un cambriolage ?*
* **Visuels suggérés** : Mur d'écrans de vidéosurveillance allumés... devant une chaise vide.
* **Notes du présentateur** :
  * Lire 3-4 réponses. Révéler : en direct, rien (personne ne regarde) ; après coup, de l'or (le film se reconstitue).
  * Transposer : logs = caméras ; SIEM = alarme intelligente ; SOC = agents. La chaîne complète, maintenant en détail.

---

## Slide 5 : La chaîne de détection — Logs, SIEM, SOC
* **Layout** : Schéma en trois étages
* **Texte affiché sur la slide** :
  * **1. Les LOGS** : chaque action laisse une trace écrite
    * `2026-06-29 16:30:12 | IP: 192.168.1.100 | User: j.dupont | LOGIN_SUCCESS`
  * **2. Le SIEM** : lit les **combinaisons** — *50 échecs de connexion + 10 Go sortants = alerte critique*
  * **3. Le SOC** : les humains qui qualifient — vrai positif ou faux positif ?
    * T1 trie · T2 investigue · T3 chasse (*threat hunting*) · le SOAR automatise (playbooks)
* **Visuels suggérés** : Pyramide à trois étages (logs → SIEM → SOC) avec un flux d'événements qui se raréfie en montant ; pictogramme « fatigue des alertes » (cloche débordante).
* **Notes du présentateur** :
  * Lire la ligne de log champ par champ ; relier aux 72 h de la CNIL (A5) : sans logs, rien à notifier — ni à savoir.
  * Marteler : chaque événement isolé est anodin, c'est la combinaison qui fait l'attaque.
  * Question rhétorique : « quelle proportion d'alertes sont des faux positifs ? » (la majorité — le tri est LE métier).

---

## Slide 6 : Activité — L'Analyste SOC
* **Layout** : Consignes d'activité + 3 sondages successifs
* **Texte affiché sur la slide** :
  * **🖥️ L'Analyste SOC — la garde du matin, 3 tickets, 3 votes**
    * **Ticket 1** (📊 Sondage n°2) : compte connecté à Lyon 8h02... puis Singapour 8h31
    * **Ticket 2** (📊 Sondage n°3) : alerte antivirus sur le fichier de test (EICAR) d'un technicien
    * **Ticket 3** (📊 Sondage n°4) : deux failles « Élevées » — 8.5 interne ou 7.5 exposée, laquelle d'abord ?
* **Visuels suggérés** : Interface de file de tickets SOC stylisée, trois cartes révélées une à une.
* **Notes du présentateur** :
  * ~4-5 min par ticket. Réponses : vrai positif probable + escalade ; faux positif documenté ; la 7.5 exposée.
  * Débriefs clés : bloquer d'abord, s'excuser ensuite (n°2) ; un faux positif se documente toujours — tuning et anti-fatigue (n°3) ; le score dit la gravité, l'exposition dit l'urgence (n°4 — pont vers le CVSS).

---

## Slide 7 : Trouver les failles — Scan vs Pentest
* **Layout** : Deux colonnes comparatives
* **Texte affiché sur la slide** :
  * **Le Scan de vulnérabilités** — *le radar automatique*
    * Automatisé, fréquent, peu coûteux · compare le parc à la base **CVE** · faux positifs possibles, failles logiques ratées
  * **Le Test d'intrusion (Pentest)** — *le pilote d'essai*
    * Expert humain, combine et improvise · réaliste mais coûteux · **toujours avec autorisation écrite**
  * **La bonne stratégie : les deux** — scans fréquents + pentest périodique
* **Visuels suggérés** : Radar automatique vs pilote d'essai casqué ; logos neutres d'outils (scanner / loupe).
* **Notes du présentateur** :
  * Citer Nessus/OpenVAS pour les scans ; rappeler le cadre légal du pentest (A1, approfondi en A7).
  * Citer CVE-2021-44228 comme exemple d'identifiant : « retenez ce numéro, on le retrouve dans 20 minutes. »

---

## Slide 8 : Prioriser — Le score CVSS
* **Layout** : Échelle graduée + critères
* **Texte affiché sur la slide** :
  * **CVSS (v4.0) : la gravité d'une faille, de 0.0 à 10.0**
  * Critères : exploitable à distance ? · facile à exploiter ? · privilèges requis ? · impact C-I-D ?
  * `[0.0-3.9] Faible · [4.0-6.9] Moyenne · [7.0-8.9] Élevée · [9.0-10.0] Critique`
  * **Règle d'or : le score dit la gravité, l'exposition dit l'urgence.**
    * *9.8 exposée = correctif sous 24 h · 3.2 locale = maintenance planifiée*
* **Visuels suggérés** : Thermomètre gradué en 4 zones colorées ; balance « score × exposition ».
* **Notes du présentateur** :
  * Préciser : v4.0 = standard actuel (fin 2023), échelle commune avec la v3.1 encore répandue dans les outils.
  * Reboucler avec le ticket 3 de l'activité : c'est le même raisonnement, formalisé.
  * Question rhétorique : « une 10.0, ça existe ? » — « oui, et le monde entier l'a corrigée en pleine nuit. Patience. »

---

## Slide 9 : Démo 6 — Lire une attaque dans les logs
* **Layout** : Console textuelle (extrait de journal)
* **Texte affiché sur la slide** :
  * **Démonstration : 60 secondes de la vie d'un serveur SSH exposé**
  * Extrait de journal d'authentification projeté (fictif)
  * **💬 Dans le chat : que voyez-vous ? Vos hypothèses avant la révélation !**
* **Visuels suggérés** : Terminal sombre avec les lignes de log qui apparaissent progressivement ; surlignage rouge sur la rafale d'échecs, vert sur la connexion réussie.
* **Notes du présentateur** :
  * Suivre le [script de la Démo 6](../outils/A_scripts_demo.md#demo-6-analyse-logs) : lecture ligne à ligne, chat en prédiction, révélation (force brute → succès → actions post-intrusion).
  * Montrer la règle SIEM qui aurait détecté automatiquement ; rappeler A3 (ce port n'aurait pas dû être exposé sans filtrage).
  * Secours : captures d'écran préparées, la démo se raconte.

---

## Slide 10 : Corriger — La gestion des correctifs
* **Layout** : Tableau de feuille de route
* **Texte affiché sur la slide** :
  * **La fenêtre critique : publication du correctif → application** *(les attaquants : quelques jours, parfois quelques heures)*
  * **Feuille de route de remédiation :**
    * `CVE-2021-44228 « Log4Shell » · 10.0 · exposée` → **immédiat (24 h)**
    * `CVE-2021-4034 « PwnKit » · 7.8 · interne` → **sous 7 jours**
    * `divulgation locale · 4.3 · postes internes` → **cycle mensuel**
  * **Tester avant de déployer — mais tester n'est pas enterrer.**
* **Visuels suggérés** : Tableau à trois lignes avec pastilles de priorité ; sablier « fenêtre critique ».
* **Notes du présentateur** :
  * Dérouler la feuille de route ligne par ligne : c'est le ticket 3 de l'activité, industrialisé.
  * **💬 Chat** : « quand la sécurité dit "patch immédiat" et la production dit "pas maintenant"... qui tranche chez vous ? » — relier à la gouvernance d'A5.

---

## Slide 11 : La vulnérabilité en chiffres
* **Layout** : Mosaïque de grands chiffres (stat cards)
* **Texte affiché sur la slide** :
  * **La réalité du terrain (sources citées)**
  * **~40 000** CVE publiées en 2024 — record historique *(base CVE/NVD)*
  * **Quelques jours** entre publication d'une faille critique et exploitation massive *(CERT/éditeurs)*
  * **147 M** de personnes touchées par Equifax 2017 — un correctif non appliqué
  * **Plusieurs mois** en moyenne pour confiner une intrusion *(IBM 2025 — rappel A1)*
* **Visuels suggérés** : Cartes de statistiques, chiffres en très grand corps, sources en petit.
* **Notes du présentateur** :
  * Les 3 messages : le flux est industriel (prioriser ou se noyer) ; la course se joue en jours ; la détection est le multiplicateur de tout le reste.
  * Transition : « deux histoires pour rendre tout cela très concret. »

---

## Slide 12 : Deux cas réels — Equifax (2017) & Log4Shell (2021)
* **Layout** : Deux panneaux « étude de cas » + question chat
* **Texte affiché sur la slide** :
  * **Equifax, 2017 — le correctif ignoré** : faille publiée en mars, correctif disponible le jour même → non appliqué → intrusion, **76 jours sans détection** → **147 M de personnes**, ~**700 M$** d'accord, PDG/DSI/RSSI partis.
  * **Log4Shell, déc. 2021 — la faille du siècle** : CVE-2021-44228, **CVSS 10.0**, bibliothèque omniprésente → scanners malveillants en **quelques heures** → des mois de remédiation mondiale.
  * **💬 Dans le chat : chez Equifax, le vrai maillon faible — technique, processus ou organisation ?**
* **Visuels suggérés** : Deux cartes « dossier » : jauge de crédit fissurée (Equifax), bûche Java en flammes (Log4Shell). Chiffres en très grand.
* **Notes du présentateur** :
  * Raconter chronologiquement ; punchlines : « le correctif existait du premier au dernier jour » ; « l'outil compromis était celui qui écrit les logs ».
  * Insister sur le triptyque préparé AVANT la crise : inventaire, scans, processus d'urgence.
  * Chat : conclure processus + organisation — la GRC d'A5 rejoint la technique.

---

## Slide 13 : Quiz de validation
* **Layout** : Contenu interactif (3 sondages successifs)
* **Texte affiché sur la slide** :
  * **✅ Quiz de validation — 3 questions, 3 votes**
  * **📊 Sondage n°5** : Le rôle principal d'un SIEM ? *(bloquer les virus / centraliser et corréler les logs / remplacer les analystes / scanner les failles)*
  * **📊 Sondage n°6** : Scan vs pentest : la différence fondamentale ?
  * **📊 Sondage n°7** : CVSS 9.8 sur un serveur exposé : votre réaction ?
* **Visuels suggérés** : Trois cartes de questions révélées successivement, coche verte à la révélation.
* **Notes du présentateur** :
  * Réponses : centraliser/corréler ; automate vs expert humain (avec autorisation écrite) ; correctif ou contournement sous 24 h.
  * Si le temps le permet : **📊 Sondage n°8** (bonus : le technicien qui refuse le patch → tester 24 h puis déployer ; rappeler Equifax).

---

## Slide 14 : Clôture & Devoirs
* **Layout** : Fin de session / Synthèse
* **Texte affiché sur la slide** :
  * **Vos trois réflexes de la session 06 :**
    * 👁️ **VOIR** — logs, SIEM, et des humains qui trient
    * ⚖️ **PRIORISER** — score CVSS × exposition
    * ⏱️ **CORRIGER VITE** — la fenêtre se compte en jours
  * **💬 Dans le chat : le mot que vous retenez**
  * **Devoirs avant A7** : module IBM SkillsBuild sur la réponse aux incidents (~60 min) + s'abonner aux alertes du CERT-FR.
  * **Prochaine séance** : *Réponse aux incidents & introduction au forensics (A7)*.
* **Visuels suggérés** : Trois pictogrammes des réflexes ; capture du fil d'alertes CERT-FR ; logo IBM SkillsBuild.
* **Notes du présentateur** :
  * Lire 4-5 mots du chat.
  * Teaser A7 : « l'alerte a sonné, l'attaque est confirmée : que fait-on dans les 60 premières minutes ? Indice : on n'éteint PAS la machine. »
  * Libérer à l'heure exacte.
