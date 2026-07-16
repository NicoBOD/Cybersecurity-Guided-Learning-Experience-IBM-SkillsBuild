# Plan de séance — Session B08 : Durcissement des systèmes & endpoints (+ Atelier de Synthèse 1)
Parcours : B 20 sessions  |  Module : B — Systèmes & réseaux  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (verbes d'action)
- **Appliquer** le principe du moindre privilège (droits, élévation temporaire, cycle de vie des comptes) sur un système Windows ou Linux.
- **Établir** une checklist de durcissement (*hardening*) de poste ou de serveur, déployable à l'échelle (GPO, référentiels CIS/ANSSI).
- **Différencier** l'antivirus à signatures de l'EDR comportemental.
- **Concevoir** collectivement l'architecture réseau sécurisée de la PME MedDistri en mobilisant tous les acquis du module B (**Atelier de Synthèse 1**).

## Prérequis & progression
- **Prérequis** : B05 à B07 (le module réseau complet) — venir avec ses notes et son schéma draw.io.
- **Lien de progression** : Clôture le module B en sécurisant la cible finale (la machine) et en assemblant toutes les briques dans l'Atelier de Synthèse 1. Ouvre le module C : l'identité comme nouveau périmètre (IAM, MFA, SSO à partir de B09).

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama B08 ([spécifications](../slides/B_S08_slides_spec.md)) ; le **tableau blanc interactif** (ou draw.io partagé) est prêt pour dessiner le schéma cible de l'atelier.
- [ ] Le schéma « réseau à plat » de MedDistri est prêt à afficher (voir [Ateliers de Synthèse](../projet/B_miniprojets.md)).
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Colonial Pipeline : le point d'entrée ? | A) Un compte VPN dormant, sans MFA |
| 2 | 0:53 | Sondage | Atelier — où placer le serveur web ? | B) DMZ sur port dédié du pare-feu |
| 3 | 0:58 | Sondage | Atelier — l'accès des 15 commerciaux ? | B) VPN + MFA |
| 4 | 1:03 | Sondage | Atelier — durcir le poste de la comptable ? | B) Compte standard + EDR + chiffrement |
| 5 | 1:14 | Sondage | Êtes-vous administrateur local de votre poste ? | Opinion (pas de bonne réponse) |
| 6 | 1:18 | Sondage | Un service par défaut inutile : que faire ? | B) Le désactiver |
| 7 | 1:20 | Sondage | EDR vs antivirus : la différence ? | A) Comportements vs signatures |
| 8 | 1:22 | Sondage | Le chiffrement de disque protège contre... ? | C) Le vol physique de la machine |
| 9 | Tampon | Sondage | La règle d'hygiène la plus simple contre l'installation de malwares ? | B) Retirer les droits admin locaux |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil & retour sur les schémas draw.io | 💬 Chat : équipements listés |
| 0:04–0:10 | Brise-glace : l'oléoduc et le compte dormant | 📊 Sondage n°1 |
| 0:10–0:18 | Séquence 1 : Le moindre privilège | Question rhétorique |
| 0:18–0:28 | Séquence 2 : Le durcissement en 5 étapes | 💬 Chat : la voiture neuve |
| 0:28–0:34 | Séquence 3 : Antivirus vs EDR | Question rhétorique |
| 0:34–0:42 | Chiffres clés & affaire Colonial Pipeline (+ Atlanta) | 💬 Chat : réactions |
| 0:42–0:46 | Mini-scénario : les droits admin du commercial | 🤔 Chat : A, B ou C |
| 0:46–1:14 | **Atelier de Synthèse 1 : l'architecture MedDistri** | 📊 Sondages n°2, 3, 4 + 💬 table de flux |
| 1:14–1:18 | Et vous ? Administrateur local ? | 📊 Sondage n°5 |
| 1:18–1:24 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:24–1:27 | Exercice bonus : la règle d'hygiène n°1 (tampon) | 📊 Sondage n°9 |
| 1:27–1:30 | Synthèse, clôture du module B & teaser B09 | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & retour sur le self-paced

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous — grande soirée : dernière session du module réseau, ET votre premier Atelier de Synthèse. Dans une heure, vous aurez conçu ensemble l'architecture sécurisée complète d'une PME. D'abord : qui a préparé son schéma draw.io ? Tapez dans le chat les équipements que vous y avez mis. »

**Points à dérouler :**
- Lire 3-4 listes du chat (attendu : pare-feu, DMZ, switch, VPN...) — « gardez ce schéma sous les yeux, il va servir. »
- Rappel express de B07 : TLS, VPN, Wi-Fi — et DigiNotar.
- Annonce du programme : durcir la machine elle-même (la cible finale), puis l'atelier MedDistri.

**Transition scriptée :** « On commence par l'histoire d'un oléoduc de 9 000 kilomètres arrêté par... un mot de passe. Devinez le point d'entrée. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (Colonial Pipeline)

**Consigne :** Lancer le **📊 Sondage n°1** — le point d'entrée de l'attaque Colonial Pipeline (2021). Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse A : un compte VPN dormant — plus utilisé, jamais désactivé — dont le mot de passe circulait dans une fuite, et sans double authentification. Pas de zero-day, pas de génie : du ménage non fait. C'est toute la leçon de ce soir : le durcissement, c'est l'art de fermer ce qui n'a pas de raison d'être ouvert — les comptes, les services, les ports. L'histoire complète arrive en milieu de session. »

**Transition scriptée :** « Premier principe, le plus important de la sécurité des systèmes : le moindre privilège. »

### 0:10–0:18 — Séquence 1 : Le moindre privilège

**Points de contenu à dérouler (support §1) :**
- La définition : le strict nécessaire — pour un utilisateur, un programme, un processus.
- **En pratique** : jamais d'administrateur (ou `root`) au quotidien ; l'élévation temporaire et tracée via UAC (Windows) ou `sudo` (Linux).
- **Le cycle de vie des comptes** : le moindre privilège s'applique aussi dans le temps — un compte qui ne sert plus se désactive immédiatement (rappel de l'offboarding de B02... et de Colonial).
- Question rhétorique : *« Si vous cliquez sur une pièce jointe piégée avec un compte standard, que peut faire le malware ? »* — pas grand-chose : ni s'installer en profondeur, ni modifier le système. Le moindre privilège transforme l'infection en incident mineur.

**Transition scriptée :** « Le moindre privilège limite les dégâts. Le durcissement, lui, réduit les portes d'entrée. »

### 0:18–0:28 — Séquence 2 : Le durcissement en 5 étapes

**Points de contenu à dérouler (support §2) :**
- L'analogie de la **voiture neuve** livrée vitres baissées et boîte à gants ouverte — relance chat : *« Pourquoi les systèmes sont-ils livrés "ouverts" par défaut ? »* (compatibilité et confort avant sécurité).
- **Les 5 étapes** : (1) désactiver services et protocoles inutiles (SMBv1 — le vecteur de WannaCry, Telnet) ; (2) les correctifs, vite pour le critique (rappel du scénario « wormable » de B03) ; (3) les politiques locales (mots de passe, verrouillage de compte, comptes par défaut désactivés) ; (4) le chiffrement du disque (BitLocker/LUKS — contre le vol physique) ; (5) le pare-feu local actif.
- **Le passage à l'échelle** : les référentiels publics (CIS Benchmarks, guides ANSSI) + le déploiement centralisé par **GPO** — on ne durcit pas 500 postes à la main ; on définit, on déploie, on vérifie (OpenSCAP).

**Transition scriptée :** « Le poste est durci. Reste à le surveiller — et l'antivirus de papa ne suffit plus. »

### 0:28–0:34 — Séquence 3 : Antivirus vs EDR

**Points de contenu à dérouler (support §3) :**
- **L'antivirus à signatures** : la liste de photos de cambrioleurs connus — aveugle face au zero-day, au polymorphe, au *fileless* (B03).
- **L'EDR** : les capteurs de mouvement — il observe les **comportements** : un Word qui lance PowerShell, qui chiffre en masse, qui contacte une IP inconnue → blocage + **isolement réseau automatique** de la machine.
- Question rhétorique : *« Souvenez-vous du mini-scénario de B06 — l'alerte de 2h du matin. Qui isole le poste quand personne ne regarde ? »* — l'EDR, précisément. C'est aussi la boîte noire qu'exploitera le SOC (B16).

**Transition scriptée :** « Chiffrons tout cela — puis retour sur l'oléoduc. »

### 0:34–0:42 — Chiffres clés & affaire Colonial Pipeline

**Chiffres (2 min, support §4) :** ~4,4 M$ de rançon payés (confirmé par le PDG), ~2,3 M$ récupérés par la justice un mois plus tard ; le point d'entrée : un compte VPN dormant sans MFA (Mandiant) ; et l'asymétrie d'Atlanta 2018 : ~52 000 $ demandés, jusqu'à ~17 M$ de reconstruction.

**Cas — Colonial Pipeline, 2021 (5 min, support §5) :** raconter : le 7 mai 2021, le rançongiciel DarkSide (un RaaS — le modèle de B02) détecté sur le réseau informatique ; l'entreprise arrête l'oléoduc par précaution — près de la moitié des carburants de la côte Est, files d'attente, achats de panique, état d'urgence ; la rançon payée, la saisie partielle par le DOJ ; et l'enquête : un compte VPN dormant, un mot de passe issu d'une fuite, pas de MFA. Trois contrôles simples — revue des comptes, MFA, non-réutilisation des mots de passe — auraient CHACUN suffi.

**Cas complémentaire — Atlanta, 2018 (1 min) :** la ville refuse de payer les ~52 000 $ (SamSam)... mais faute de préparation, la reconstruction coûte des millions. Moralité : refuser de payer est la bonne doctrine — à condition d'avoir durci et sauvegardé AVANT. Relance chat : *« Quel détail vous marque le plus ? »*

### 0:42–0:46 — 🤔 Mini-scénario : les droits admin du commercial

**Consigne :** Afficher le mini-scénario du support : le commercial qui part demain et « a besoin des droits admin ». *« Tapez A, B ou C dans le chat. »*

**Débrief :** B — le moindre privilège n'est pas le refus du besoin, c'est le refus du privilège **permanent** pour un besoin **ponctuel** : installation par le support, ou élévation temporaire et tracée. A laisse un poste à pleins pouvoirs longtemps après le déplacement ; C pousse au contournement (PC personnel, clé USB). La sécurité qui organise le OUI encadré est obéie ; celle qui dit toujours non finit contournée.

**Transition scriptée :** « Et maintenant, le grand moment : tout le module B sur un seul schéma. Ouvrez vos notes — MedDistri vous attend. »

### 0:46–1:14 — Atelier de Synthèse 1 : l'architecture MedDistri (Sondages n°2 à 4)

**Format** (cf. [Ateliers de Synthèse](../projet/B_miniprojets.md)) : ~28 minutes, entièrement par sondages et chat.

**1. Présentation du cas (5 min) :** afficher le schéma **à plat** de MedDistri (PME de distribution de matériel médical, 40 salariés : postes bureautique, serveur web vitrine, serveur de gestion/comptabilité, 15 commerciaux nomades — tout sur le même réseau, aucun filtrage interne).

**🎙️ Verbatim de lancement :**
> « Voici le réseau de MedDistri tel qu'il existe aujourd'hui. Prenez dix secondes... et dites-moi dans le chat : qu'est-ce qui vous choque ? » — lire les réponses (attendu : tout communique avec tout, serveur web exposé au milieu des postes, aucun VPN) : « vous venez de décrire TV5 Monde et Target. Réparons cela. »

**2. Les trois décisions d'architecture (12 min) :** lancer les **📊 Sondages n°2, 3, 4** l'un après l'autre (~4 min chacun : énoncé, vote, débrief).

- N°2 (le serveur web → DMZ sur port dédié du pare-feu) : C l'expose sans protection ; A reproduit Target (le serveur exposé au milieu des postes). Rappeler la règle d'or : aucun flux initié DMZ → LAN.
- N°3 (les commerciaux → VPN + MFA) : A est le scénario force brute de B05 (RDP exposé) ; C sacrifie l'activité. Et rappeler Colonial : un VPN sans MFA ni revue des comptes est lui-même une porte.
- N°4 (le poste de la comptable → compte standard + EDR + chiffrement) : A est un mythe (deux antivirus se neutralisent) ; C ignore le fileless et le vol physique. Trois couches : limiter (moindre privilège), détecter (EDR), protéger le disque (chiffrement).

**3. La table de flux collective (8 min) :** dessiner le schéma cible au tableau blanc (WAN → pare-feu → DMZ / LAN segmenté en VLAN / passerelle VPN) et construire la table de filtrage à partir du **chat** : *« Proposez-moi une règle : source → destination → port → action. »* Reprendre la méthode EcoLog (B06), corriger en direct, terminer par `Any → Any : Deny`.

**4. Synthèse de l'atelier (3 min) :**
> « Regardez ce schéma : chaque brique du module y est. La lecture des flux, c'est B05. La DMZ, les VLAN et cette table de filtrage, c'est B06. Le VPN, la MFA et le TLS, c'est B07. Les postes durcis et l'EDR, c'est ce soir. Ce schéma, c'est VOTRE travail — et c'est exactement ce qu'un consultant facture. »

### 1:14–1:18 — Sondage n°5 : êtes-vous administrateur local ?

**Consigne :** Lancer le **📊 Sondage n°5** (opinion). Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Sans jugement — c'est un miroir de la maturité des organisations. B est la cible, avec un processus d'élévation fluide comme pour notre commercial. A est fréquent en PME : chaque clic s'exécute alors avec les pleins pouvoirs. Et si vous avez répondu C : vérifier prend 30 secondes — essayez d'installer un logiciel. C'est votre action de la semaine. »

### 1:18–1:24 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : désactiver le service inutile ; l'EDR analyse les comportements (vs signatures) ; le chiffrement de disque protège contre le vol physique. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/B_S08_support.md).

### 1:24–1:27 — Exercice bonus (Sondage n°9) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°9** — la règle d'hygiène la plus simple contre l'installation de malwares ? Débrief : retirer les droits d'administrateur local (B) — la mesure au meilleur rapport coût/efficacité du poste de travail ; deux antivirus (A) se neutralisent souvent ; changer les mots de passe tous les 5 jours (C) épuise sans bénéfice équivalent. À couper en cas de retard.

### 1:27–1:30 — Synthèse & clôture du module B

**🎙️ Verbatim de synthèse :**
> « Module Systèmes & réseaux : terminé ! Vous savez lire le trafic, bâtir des murailles, chiffrer les communications, durcir les machines — et vous venez de concevoir l'architecture complète d'une PME. Prochaine étape : le module Identités & accès. Car une question reste ouverte : les murailles sont là... mais qui a les clés ? Un mot que vous retenez, dans le chat ! »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Self-paced : cours IBM SkillsBuild *"System Hardening and Patch Management"* (~1h30) + vérifier si l'on est administrateur local de son poste + identifier le concept de SSO et lister ses usages quotidiens (Google Login, Microsoft Login) — transition directe vers B09.
- Teaser B09 : « la semaine prochaine, le module Identités : mots de passe, MFA, SSO — et pourquoi l'identité est devenue LE nouveau périmètre de sécurité. Avec une question piège : la MFA est-elle vraiment incontournable ? Des attaquants ont appris à la fatiguer... »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**Exercice bonus n°9** (1:24–1:27) — il est dans le support en exercice bonus.
2. Compresser le cas Atlanta à une phrase (l'asymétrie 52 k$ / 17 M$).
3. Dans l'atelier, réduire la table de flux collective à 3 règles (les votes n°2-4 sont prioritaires).
4. Ne JAMAIS couper : l'Atelier de Synthèse, le cas Colonial, le quiz.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°3 : les trois contrôles qui auraient chacun suffi à empêcher Colonial).
2. Étoffer la table de flux MedDistri (règles pour l'accès des commerciaux au cloud, la maintenance du prestataire...).
3. Questions/réponses libres sur l'ensemble du module B.

## Travail en autonomie (Self-paced)
* **Avant la session suivante (B09)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"System Hardening and Patch Management"* (durée estimée : 1h30).
  * **Action pratique** : Vérifier si votre compte quotidien est administrateur local de votre poste (tenter une installation de logiciel : la demande d'élévation vous répond).
  * **Transition Module C** : Identifier le concept de Single Sign-On (SSO) et lister les services que vous utilisez au quotidien qui s'appuient sur cette technologie (ex. Google Login, Microsoft Login).
