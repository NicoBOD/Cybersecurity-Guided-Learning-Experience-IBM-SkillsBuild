# Parcours A — Session 06 : Opérations de sécurité & gestion des vulnérabilités
Module : SecOps & Vulnérabilités  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (4, verbes d'action)
- **Expliquer** le cycle de détection d'une alerte de sécurité, de la génération d'un journal d'événements (*log*) jusqu'à sa qualification par un analyste SOC.
- **Distinguer** l'objectif et la méthodologie d'un scan automatisé de vulnérabilités par rapport à un test d'intrusion (*pentest*).
- **Interpréter** un score CVSS et le pondérer par le contexte d'exposition pour prioriser la remédiation.
- **Planifier** un calendrier opérationnel de gestion des correctifs (*patching*) minimisant les perturbations pour l'activité.

## Prérequis
- Sessions précédentes : A3, A5.
- Self-paced AVANT la séance (~90 min) : Module SkillsBuild sur les opérations de sécurité (introduction aux outils SIEM et à la journalisation des événements système).

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **8 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama S06 ([spécifications](../slides/A_S06_slides_spec.md)) — y compris la feuille de route de remédiation.
- [ ] Le [script de la Démo 6 — Lire une attaque dans les logs](../outils/A_scripts_demo.md#demo-6-analyse-logs) est relu ; l'extrait de logs est prêt à projeter (captures de secours préparées).
- [ ] Le chat est ouvert ; un modérateur remonte les questions si possible.
- [ ] Un minuteur est visible du mentor.

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Combien de CVE publiées en 2024 ? | C) ~40 000 |
| 2 | 0:28 | Sondage | Alerte « voyage impossible » : qualification ? | B) Vrai positif probable, escalade |
| 3 | 0:33 | Sondage | Alerte antivirus fichier de test EICAR ? | B) Faux positif documenté |
| 4 | 0:38 | Sondage | Patch : 8.5 interne ou 7.5 exposée ? | B) La 7.5 exposée |
| 5 | 1:17 | Sondage | Rôle principal d'un SIEM ? | B) Centraliser et corréler les logs |
| 6 | 1:19 | Sondage | Scan vs pentest : la différence ? | B) Automate vs expert humain |
| 7 | 1:21 | Sondage | CVSS 9.8 sur serveur exposé : réaction ? | B) Correctif sous 24h |
| 8 | Tampon | Sondage | Patch urgent : refuser ou tester 24h ? | B) Tester puis déployer |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil & retour sur les devoirs d'A5 | Chat : finalités relevées |
| 0:04–0:10 | Brise-glace : le déluge de failles | 📊 Sondage n°1 |
| 0:10–0:15 | Les caméras que personne ne regarde | 💬 Chat : débat |
| 0:15–0:28 | Séquence 1 : Logs, SIEM, SOC | Question rhétorique |
| 0:28–0:42 | Activité : L'Analyste SOC | 📊 Sondages n°2, 3, 4 |
| 0:42–0:52 | Séquence 2 : Scan vs Pentest & le score CVSS | Question rhétorique |
| 0:52–1:00 | Démo 6 : Lire une attaque dans les logs | Chat : prédictions |
| 1:00–1:08 | Séquence 3 : La gestion des correctifs | 💬 Chat : « qui tranche ? » |
| 1:08–1:17 | Chiffres & cas réels (Equifax, Log4Shell) | 💬 Chat : le vrai maillon faible |
| 1:17–1:23 | Quiz de validation | 📊 Sondages n°5, 6, 7 |
| 1:23–1:27 | Bonus : le dilemme du correctif (tampon) | 📊 Sondage n°8 |
| 1:27–1:30 | Synthèse, règle d'or & devoirs | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & retour sur les devoirs

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous ! La semaine dernière, je vous avais demandé de lire la politique de confidentialité d'un service que vous utilisez. En une phrase dans le chat : la finalité la plus surprenante que vous avez découverte ? »

**Points à dérouler :**
- Lire 2-3 réponses, relier à la minimisation (A5).
- Pivot : « A5 nous a appris QUI décide et ce que dit la loi — avec un chrono de 72 heures pour notifier une fuite. Mais ce chrono ne démarre que si quelqu'un VOIT la fuite. Aujourd'hui : comment on voit. Bienvenue aux opérations de sécurité. »

**Transition scriptée :** « Et pour comprendre l'ampleur de la tâche, un chiffre d'abord. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (le déluge de failles)

**Consigne :** Lancer le **📊 Sondage n°1** — *« Combien de nouvelles vulnérabilités (CVE) publiées dans le monde en 2024 ? »* Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse C : environ 40 000 — un record, plus de 100 nouvelles failles référencées CHAQUE JOUR. Personne, nulle part, ne peut tout corriger tout de suite. La sécurité opérationnelle n'est donc pas une affaire de perfection : c'est une affaire de PRIORISATION. À la fin de cette session, vous saurez faire ce tri comme un professionnel. »

**Transition scriptée :** « Mais avant de corriger, il faut voir. Petite question de bon sens. »

### 0:10–0:15 — 💬 Les caméras que personne ne regarde

**Consigne :** Question chat — *« Un centre commercial installe 200 caméras dernier cri... mais n'embauche personne au PC sécurité. Que valent ces caméras ? Et à quoi serviront-elles quand même, après un cambriolage ? Vos réponses dans le chat. »* Lire 3-4 réponses.

**🎙️ Formulation de synthèse :**
> « Exactement : en direct, elles ne valent rien — personne ne regarde. Après coup, elles valent de l'or — on peut reconstituer le film. Les LOGS de vos systèmes, c'est pareil : sans surveillance, ils ne préviennent rien, mais ils enregistrent tout. La chaîne complète — caméras, alarme intelligente, agents — s'appelle en cybersécurité : logs, SIEM, SOC. Détaillons. »

### 0:15–0:28 — Séquence 1 : Logs, SIEM, SOC

**Points de contenu à dérouler (support §1) :**
- **Les logs** : chaque connexion, modification, blocage = une ligne écrite. Projeter l'exemple de log du support et le lire à voix haute champ par champ. Relier à A5 : sans logs, impossible de savoir quoi notifier à la CNIL sous 72h — ni même qu'il y a quelque chose à notifier.
- **Le SIEM** : des millions de lignes/jour ; l'outil ne lit pas les lignes, il lit les **combinaisons**. Dérouler la règle de corrélation du support (50 échecs + 10 Go sortants = alerte). Insister : chaque événement isolé est anodin ; c'est la combinaison qui fait l'attaque.
- **Le SOC** : les humains qui qualifient — vrai positif ou faux positif. Les 3 niveaux : T1 trie, T2 investigue, T3 chasse (threat hunting). Introduire la **fatigue des alertes** : crier au loup mille fois, et le loup finit par passer — d'où le SOAR qui automatise les réponses répétitives (playbooks).

**Question rhétorique (0:26) :** *« À votre avis, quelle proportion des alertes d'un SOC sont des faux positifs ? »* — laisser 5 secondes : « la majorité, souvent l'écrasante majorité. Le tri est LE métier. Et justement : vous embauchez... enfin, VOUS êtes embauchés. »

### 0:28–0:42 — Activité : L'Analyste SOC (Sondages n°2 à 4)

**Consigne :** Annoncer : « vous prenez votre poste au SOC pour la garde du matin ; trois tickets attendent dans la file. » Lancer les **📊 Sondages n°2, 3, 4** (~4-5 min chacun : présentation, vote, débrief). Situations, options et débriefs complets : voir le [support, section « L'Analyste SOC »](../supports-md/A_S06_support.md).

**🎙️ Verbatim de lancement :**
> « Il est 8h00, vous êtes analyste de niveau 1, café à la main. Trois tickets dans la file. Pour chacun : votre qualification, par vote. Ticket n°1 : le compte de M. Diallo s'est connecté depuis Lyon à 8h02... puis depuis Singapour à 8h31. »

**Débriefs scriptés (points obligatoires) :**
- N°2 (voyage impossible) : on bloque d'abord, on s'excuse ensuite — un blocage à tort coûte un appel au support, un vol de compte coûte une crise. Nuance VPN personnel → investigation niveau 2, pas sanction automatique.
- N°3 (EICAR) : le piège est « j'ignore sans consigner » — un faux positif se DOCUMENTE : c'est ainsi qu'on affine les règles et qu'on combat la fatigue des alertes.
- N°4 (8.5 vs 7.5) : le score dit la gravité intrinsèque, **l'exposition dit l'urgence réelle** — rappel de la formule du risque d'A1. Annonce : « ce raisonnement a un nom et une échelle : le CVSS, tout de suite. »

### 0:42–0:52 — Séquence 2 : Scan vs Pentest & le score CVSS

**Points de contenu à dérouler (support §2 et §3) :**
- **Scan de vulnérabilités** : le radar automatique — systématique, fréquent, peu coûteux ; compare le parc à la base CVE ; produit des faux positifs, rate les failles logiques.
- **Pentest** : le pilote d'essai — un humain qui improvise, combine, contourne ; coûteux mais réaliste ; TOUJOURS avec autorisation écrite (rappel A1, cadre légal approfondi en A7).
- Stratégie : scans fréquents + pentest périodique — l'un n'exclut pas l'autre.
- **CVE** : le dictionnaire mondial des failles (citer CVE-2021-44228 : « retenez ce numéro, on le retrouve dans 20 minutes »).
- **CVSS** : la note de gravité 0.0 → 10.0 (version actuelle 4.0 ; échelle commune avec la 3.1). Les 4 critères vulgarisés : exploitable à distance ? facile ? privilèges requis ? impact C-I-D ? Projeter l'échelle des 4 zones.
- La règle opérationnelle : 9.8 exposée = correctif sous 24h ; 3.2 locale = maintenance planifiée.

**Question rhétorique (0:50) :** *« Une CVSS 10.0, ça existe ? »* — « Oui. Il y en a même une que le monde entier a corrigée en pleine nuit — patience, elle arrive. »

### 0:52–1:00 — Démo 6 : Lire une attaque dans les logs

**Consigne :** Dérouler la [Démo 6 — Lire une attaque dans les logs](../outils/A_scripts_demo.md#demo-6-analyse-logs) en partage d'écran : projeter l'extrait de journal d'authentification (fictif), le faire lire au chat ligne par ligne, faire deviner l'attaque avant de la nommer.

**🎙️ Question centrale de la démo :**
> « Voici 60 secondes de la vie d'un serveur SSH exposé. Lisez avec moi... Que voyez-vous ? Vos hypothèses dans le chat ! »

**Points de débrief obligatoires :**
- La rafale d'échecs (force brute), puis LE succès — et surtout ce qui suit le succès (heure inhabituelle, téléchargement d'outil).
- Montrer comment la règle SIEM du début de session aurait levé l'alerte automatiquement — et rappeler A3 : ce serveur SSH n'aurait jamais dû être exposé sans filtrage.
- En cas de pépin technique : l'extrait est dans le script de démo, la lecture se fait sur les captures de secours.

**Transition scriptée :** « Détecter, prioriser... reste à corriger. Et là, une objection célèbre vous attend : "on ne touche pas à la production". »

### 1:00–1:08 — Séquence 3 : La gestion des correctifs

**Points de contenu à dérouler (support §3 + Focus pratique) :**
- La fenêtre critique : publication du correctif → application du correctif. Les attaquants automatisent l'exploitation en **quelques jours, parfois quelques heures** — la fenêtre est devenue LA métrique de survie.
- Projeter la **feuille de route de remédiation** du support ligne par ligne : Log4Shell 10.0 exposée = immédiat ; PwnKit 7.8 interne = sous 7 jours ; divulgation locale 4.3 = cycle mensuel. C'est le sondage n°4, industrialisé.
- Le compromis sécurité/production : tester avant de déployer (environnement de test, déploiement progressif) — mais tester n'est pas enterrer : le correctif critique attend des heures, pas des trimestres.

**Interaction (1:06) — 💬 Question chat :**
> « Dans votre organisation : quand la sécurité dit "patch immédiat" et la production dit "surtout pas maintenant"... qui tranche ? Répondez en un mot. » — lire 3-4 réponses, relier à la gouvernance d'A5 (c'est un arbitrage de direction, pas un bras de fer de couloir).

### 1:08–1:17 — Chiffres & cas réels

**Chiffres (2 min, support §4) :** re-projeter les ~40 000 CVE/an ; l'exploitation en quelques jours ; rappel A1 : plusieurs mois en moyenne pour confiner une intrusion (IBM 2025) — « la détection est le multiplicateur de tout le reste ».

**Cas n°1 — Equifax, 2017 (4 min, support §5) :** raconter : mars 2017, faille critique Apache Struts publiée, correctif disponible LE JOUR MÊME ; chez Equifax, inventaire incomplet, correctif non appliqué sur un portail critique ; intrusion deux mois plus tard, 76 jours sans détection (l'outil de surveillance était lui-même mal configuré — certificat expiré depuis des mois) ; ~147 millions de personnes touchées, ~700 millions de dollars d'accord, PDG/DSI/RSSI partis. Punchline : « le correctif existait du premier au dernier jour. Ce ne sont pas les outils qui ont failli, c'est le processus. »

**Cas n°2 — Log4Shell, 2021 (3 min, support §5) :** raconter : 9 décembre 2021, CVE-2021-44228, CVSS **10.0**, bibliothèque Java omniprésente ; scanners malveillants en quelques heures ; la pire semaine de l'année pour les équipes sécurité mondiales — d'abord SAVOIR où Log4j se cache, puis corriger, parfois plusieurs fois. Punchline : « l'outil compromis était celui qui écrit les logs — l'ironie parfaite. Et la différence entre 48 heures et 6 mois s'est jouée sur trois choses préparées AVANT : l'inventaire, les scans, le processus d'urgence. »

**Interaction (1:15) — 💬 Question chat :** *« Chez Equifax : le VRAI maillon faible — la technique, le processus ou l'organisation ? »* — lire 3-4 réponses ; conclure : processus et organisation — la GRC d'A5 rejoint la technique.

### 1:17–1:23 — Quiz de validation (Sondages n°5 à 7)

**Consigne :** Lancer les **📊 Sondages n°5, 6, 7** à la suite (~2 min chacun). Réponses : centraliser/corréler les logs ; automate vs expert humain ; correctif sous 24h. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/A_S06_support.md).

### 1:23–1:27 — Bonus : le dilemme du correctif (Sondage n°8) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°8** — le technicien qui refuse le patch urgent par peur de casser la production. Débrief : tester 24h puis déployer ; rappeler Equifax — ne pas patcher a aussi un coût, en centaines de millions. À couper en cas de retard (l'exercice reste dans le support en bonus).

### 1:27–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Trois réflexes à emporter : VOIR — des logs, un SIEM, des humains qui trient ; PRIORISER — le score CVSS multiplié par l'exposition, jamais l'un sans l'autre ; CORRIGER VITE — la fenêtre correctif-attaque se compte en jours. Equifax avait les outils et a perdu 700 millions ; les mieux préparés ont réglé Log4Shell en 48 heures. La différence ? Le processus. Tapez dans le chat le mot que vous retenez. »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Devoirs : module IBM SkillsBuild sur la réponse aux incidents (~60 min) + s'abonner au fil d'alertes du CERT-FR (gratuit — « le réflexe professionnel n°1 »).
- Teaser A7 : « la semaine prochaine : l'alerte a sonné, l'attaque est confirmée — que fait-on dans les 60 premières minutes ? Réponse aux incidents et enquête numérique. Indice : le premier réflexe n'est PAS d'éteindre la machine. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper le **Bonus n°8** (1:23–1:27) — il est dans le support en exercice bonus.
2. Compresser Log4Shell à 90 secondes (CVSS 10.0 + punchline inventaire).
3. Ne JAMAIS couper : l'Analyste SOC, la démo 6, le cas Equifax.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°2 : le SOC de la PME à budget zéro — très concret pour ce public).
2. Approfondir la démo 6 : faire formuler au chat la règle de corrélation qui aurait détecté l'attaque.
3. Ouvrir une séquence questions/réponses libre.

## Articulation avec l'atelier de fin de parcours
- Cette session apporte les notions de priorisation des vulnérabilités et de détection, utiles pour le calcul du score de résilience lors de l'Atelier d'Audit Interactif MedDistri (RDP exposé, sauvegardes connectées, budget contraint).

## Self-paced APRÈS la séance (~90 min) & évaluation formative
- Suivre le module d'auto-formation en ligne sur l'évaluation des vulnérabilités logicielles (CVE et CVSS).
- S'abonner au fil d'alertes du CERT-FR et parcourir les deux dernières alertes publiées (titre + systèmes concernés).
- Quiz d'auto-évaluation en ligne (10 questions sur le cycle SecOps et le CVSS).
