# Parcours A — Session 08 : Grand Atelier d'Audit Interactif & Synthèse
Module : Consolidation & Clôture  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (4, verbes d'action)
- **Analyser** l'infrastructure d'une PME vulnérable à travers un scénario décisionnel collectif.
- **Arbitrer** et choisir les mesures de sécurité prioritaires à l'aide de sondages Livestorm, sous contrainte de budget.
- **Justifier** les choix d'hygiène informatique (VPN, MFA, sauvegardes) face à des objections métier réelles.
- **Synthétiser** les acquis du parcours (réflexes et cas réels) et préparer la suite de l'apprentissage.

## Prérequis
- Sessions A01 à A07 complétées.
- Self-paced AVANT la séance : relecture des aide-mémoires A1-A7 et du [dossier MedDistri](../projet/A_capstone.md) (contexte de l'entreprise).

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous) : 3 d'échauffement (définis dans le [support](../supports-md/A_S08_support.md)), 4 d'audit (définis dans le [dossier MedDistri](../projet/A_capstone.md)), 1 d'objection métier et 1 de bilan (support).
- [ ] Le partage d'écran est testé avec le diaporama S08 ([spécifications](../slides/A_S08_slides_spec.md)) — y compris la **jauge du Score de Résilience** (slide dédiée, mise à jour manuelle entre les sondages : 10 % → 35 % → 55 % → 80 % → 100 % si sans-faute).
- [ ] Le schéma « architecture cible » de MedDistri est prêt (slide 12) — en secours du tableau blanc.
- [ ] Le lien du questionnaire de satisfaction est prêt à coller dans le chat.
- [ ] Un minuteur est visible du mentor.

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:05 | Sondage | Chiffrer + menacer de publier = ? | A) Double extorsion |
| 2 | 0:07 | Sondage | E-mail « RIB changé » : réflexe ? | B) Canal alternatif initié par moi |
| 3 | 0:09 | Sondage | Poste infecté : premier geste ? | B) Débrancher sans éteindre |
| 4 | 0:22 | Sondage | Audit 1 : RDP/SSH exposés → action prioritaire ? | B) Fermer + VPN + MFA (+25 %) |
| 5 | 0:30 | Sondage | Audit 2 : convaincre sur le MFA M365 ? | A) 99,9 % Microsoft + fausses factures (+20 %) |
| 6 | 0:38 | Sondage | Audit 3 : le disque USB branché en permanence ? | B) Chiffré avec le serveur (+25 %) |
| 7 | 0:46 | Sondage | Audit 4 : allouer 2 000 € ? | B) VPN/MFA + sauvegarde cloud + formation (+20 %) |
| 8 | 0:53 | Sondage | Objection MFA de la directrice : quel argument ? | A) 99,9 % + coût de l'arrêt vs 3 secondes |
| 9 | 1:22 | Sondage | Meilleur ROI sécurité pour une TPE/PME ? | B) Mots de passe + MFA + sensibilisation |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:05 | Accueil solennel & règles de l'atelier | Chat : présence |
| 0:05–0:12 | Échauffement de l'auditeur | 📊 Sondages n°1, 2, 3 |
| 0:12–0:20 | Présentation du dossier MedDistri | 💬 Chat : « la faille qui vous choque le plus » |
| 0:20–0:52 | L'AUDIT — 4 décisions, 4 votes | 📊 Sondages n°4, 5, 6, 7 |
| 0:52–1:00 | Le dilemme des objections métier | 📊 Sondage n°8 |
| 1:00–1:12 | La feuille de route de remédiation collective | 💬 Chat : « lundi matin, je commence par... » |
| 1:12–1:20 | Score final & bilan de l'audit | Révélation de la jauge |
| 1:20–1:27 | La carte du parcours & la suite | 📊 Sondage n°9 |
| 1:27–1:30 | Clôture, badge & remerciements | Chat : « le parcours en un mot » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:05 — Accueil solennel & règles de l'atelier

**🎙️ Verbatim d'ouverture :**
> « Bonsoir à toutes et à tous — et bienvenue dans votre dernière session... qui n'est pas un cours. Ce soir, PAS de théorie nouvelle, PAS d'examen individuel. Ce soir, vous êtes un cabinet d'audit. Votre cliente s'appelle Mme Legrand, elle dirige MedDistri, une PME de distribution de matériel médical — et elle a besoin de vous. Les règles : à chaque décision, VOUS votez ; la majorité l'emporte ; chaque bonne décision fait monter le Score de Résilience Cyber de l'entreprise, qui démarre péniblement à 10 %. Objectif collectif : 80 % ou plus. L'audit est validé par la communauté — ou pas. Tapez "prêt" dans le chat si vous acceptez la mission. »

**Points à dérouler :**
- Lire l'enthousiasme du chat ; rappeler qu'aucun travail individuel n'est évalué.
- Annoncer le déroulé : échauffement, dossier, 4 décisions d'audit, objections métier, feuille de route, score final, et la carte du parcours pour finir.

### 0:05–0:12 — Échauffement de l'auditeur (Sondages n°1 à 3)

**Consigne :** Lancer les **📊 Sondages n°1, 2, 3** à un rythme soutenu (~2 min chacun : vote 45-60 s + débrief éclair). Questions et débriefs : voir le [support, « Échauffement de l'auditeur »](../supports-md/A_S08_support.md).

**🎙️ Verbatim de lancement :**
> « Avant d'entrer chez le client, tout auditeur vérifie ses instruments. Trois questions éclair pour dérouiller les réflexes des sept dernières semaines — top chrono. »

**Points de débrief éclair :** double extorsion → « retenez ce mot, MedDistri est dans la santé, comme le CHSF » ; canal alternatif → « Pathé, 19,2 millions » ; isoler sans éteindre → « votre vote d'A7, gravé je l'espère ».

### 0:12–0:20 — Présentation du dossier MedDistri

**Consigne :** Projeter le contexte (slide) et raconter MedDistri comme une visite client : l'entrepôt, le placard à balais, le technicien débordé, les 15 commerciaux nomades. Dérouler les 6 éléments d'infrastructure du [dossier](../projet/A_capstone.md) SANS commenter les failles — c'est le travail de l'auditoire.

**Interaction (0:18) — 💬 Question chat :**
> « Vous venez de visiter MedDistri. AVANT tout vote : quelle faille vous choque le plus ? Un mot dans le chat. » — lire 4-5 réponses, ne rien valider : « gardez vos intuitions, l'audit commence. »

### 0:20–0:52 — L'AUDIT : 4 décisions, 4 votes (Sondages n°4 à 7)

**Consigne :** Dérouler les quatre sondages d'audit du [dossier MedDistri](../projet/A_capstone.md) (~8 min chacun) selon le rituel : présenter la situation (1 min) → vote (1-2 min) → **faire argumenter le chat AVANT de révéler** (2 min) → débrief scripté du dossier (2-3 min) → **mise à jour de la jauge à l'écran** (10 % → 35 % → 55 % → 80 % → 100 %).

**🎙️ Rituel de mise à jour du score (à chaque bonne décision majoritaire) :**
> « Décision actée. Le technicien de MedDistri s'exécute... et le Score de Résilience passe à [X] %. Mme Legrand respire un peu mieux. Décision suivante. »

**Points de débrief obligatoires (détail complet dans le dossier) :**
- **N°4 (RDP/SSH)** : le serveur-appât d'A3 — scanné en minutes ; le mot de passe `Admin@MedDistri2025` suit un schéma prévisible ; VPN + MFA, seule voie nomade sûre.
- **N°5 (MFA M365)** : 99,9 % (Microsoft, A4) ; les fausses factures = la mécanique Pathé (A2) — l'argument qui parle à une DG.
- **N°6 (sauvegarde USB)** : le NAS piégé d'A4 ; rappeler OVHcloud (le hors-site protège aussi du feu) et Maersk (A7 : la survie ne se confie pas au hasard).
- **N°7 (budget 2 000 €)** : l'hygiène avant les outils ; le pentest n'est pas inutile, il est PRÉMATURÉ (A6 : scan d'abord) ; c'est la logique du Comité des Risques d'A5.

**En cas de réponse majoritaire incorrecte :** ne pas accorder le gain ; ouvrir un débat contradictoire de 2 minutes dans le chat (« défendez vos choix ! ») ; re-voter en « seconde délibération » — le gain est acquis si le vote bascule. C'est prévu dans le bilan du dossier.

### 0:52–1:00 — Le dilemme des objections métier (Sondage n°8)

**Consigne :** Lancer le **📊 Sondage n°8** — la directrice refuse le MFA (perte de temps des commerciaux). Débrief complet dans le [support](../supports-md/A_S08_support.md).

**Points de débrief obligatoires :** l'argument chiffré + coût d'opportunité (A : 99,9 % et « 3 secondes contre 3 semaines d'arrêt ») ; pourquoi B est FAUX en l'état (le RGPD exige des mesures « appropriées », pas nommément le MFA — un auditeur n'invente jamais une obligation légale) ; pourquoi C échoue toujours (la sécurité imposée sans adhésion est contournée). Conclure : « auditer, c'est 50 % de technique et 50 % de conviction. »

### 1:00–1:12 — La feuille de route de remédiation collective

**Points de contenu à dérouler (support, « Priorisation et réalisme budgétaire ») :**
- Reconstituer À PARTIR DES VOTES la feuille de route en trois horizons : court terme/budget nul (fermer les ports, MFA, mots de passe — décisions n°4-5) ; moyen terme (VPN, 3-2-1 déconnecté, registre RGPD — décisions n°6-7) ; long terme (sensibilisation, scans A6, PSSI A5, exercice de crise A7).
- Montrer l'architecture cible à l'écran (schéma : serveur isolé, accès VPN+MFA, sauvegarde hors ligne, zones séparées — l'héritage d'A3).
- L'exercice de vulgarisation : « comment le dire à Mme Legrand ? » — transformer chaque mesure en bénéfice business.

**Interaction (1:09) — 💬 Question chat :**
> « Dernière ligne de l'audit : si MedDistri était VOTRE organisation, que feriez-vous lundi matin en arrivant ? Une seule mesure, la première. » — lire 5-6 réponses, souligner la convergence (MFA et fermeture des ports arrivent toujours en tête — « vos réflexes sont installés »).

### 1:12–1:20 — Score final & bilan de l'audit

**Consigne :** Révéler la jauge finale avec cérémonie. Si ≥ 80 % : valider l'audit au nom de la communauté (verbatim ci-dessous). Sinon : « seconde délibération » sur les décisions manquées (re-vote après débat), puis validation.

**🎙️ Verbatim de validation :**
> « Score de Résilience final de MedDistri : [X] %. Il y a 90 minutes, cette entreprise était une statistique en puissance — un ransomware avant Noël, une fuite RGPD au printemps. Elle est maintenant [X] % plus résiliente, pour moins de 2 000 euros, grâce à VOS décisions. L'audit est officiellement validé par la communauté des apprenants. Mme Legrand vous remercie — et moi aussi. »

### 1:20–1:27 — La carte du parcours & la suite (Sondage n°9)

**Points de contenu à dérouler (support, « La carte du parcours ») :**
- Projeter le tableau des 8 sessions : le réflexe à vie + le cas réel de chaque session (CHSF, Pathé/Arup, Target/Mirai, Capital One/OVHcloud, Google/Meta, Equifax/Log4Shell, Maersk, MedDistri). « Chacune de ces histoires est un argument que vous pouvez ressortir en réunion. »
- Lancer le **📊 Sondage n°9** (le meilleur ROI sécurité) — débrief : le verdict de l'audit, généralisé ; la charte de 80 pages que personne ne lit est l'anti-PSSI.
- La suite : le badge IBM SkillsBuild (comment le récupérer) ; les certifications (CompTIA Security+ comme premier objectif réaliste) ; la pratique légale (TryHackMe, Root-Me — jamais de « test » sauvage, cf. A7) ; la veille déjà en place (CERT-FR d'A6, Panorama ANSSI annuel).

### 1:27–1:30 — Clôture & remerciements

**🎙️ Verbatim de clôture :**
> « Huit sessions, sept réflexes, dix histoires vraies — et un audit réussi. Vous êtes arrivés en vous demandant si la cybersécurité était pour vous ; vous repartez en ayant sécurisé une entreprise. Avant de nous quitter : le parcours en UN mot, dans le chat. [Lire une dizaine de mots à voix haute.] Le lien du questionnaire de satisfaction arrive dans le chat — vos retours façonnent les prochaines promotions. Merci, sincèrement. Prenez soin de vos données — et de celles des autres. »

**Points de clôture :**
- Coller le lien de satisfaction dans le chat ; rappeler le badge et le message de clôture qui suivra par e-mail.
- Terminer à l'heure exacte — c'est la dernière impression.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Compresser l'échauffement (0:05–0:12) à 2 sondages (garder n°2 et n°3).
2. Réduire la feuille de route (1:00–1:12) à 8 min : les trois horizons sans l'exercice de vulgarisation.
3. Ne JAMAIS couper : les 4 sondages d'audit avec leurs débats, la révélation du score, la carte du parcours.
4. Le **📊 Sondage n°9** peut basculer en question chat rapide si nécessaire.

**Si vous êtes en avance :**
1. Étendre les débats de « seconde délibération » même sur les bonnes réponses (« un volontaire pour défendre l'option C ? »).
2. Dérouler les **Questions de réflexion** du support (notamment la n°3 : quel réflexe s'érodera en premier ?).
3. Ouvrir une séquence questions/réponses libre sur les métiers et parcours de formation cyber.

## Articulation avec le parcours
- Cette session est le consolidateur final : chaque sondage d'audit mobilise explicitement les sessions A1 à A7 (voir le fil rouge dans le [dossier MedDistri](../projet/A_capstone.md)).

## Après la séance
- Message de clôture (Message 5 de `A_messages.md`) : félicitations, badge, ressources pour continuer.
- Questionnaire de satisfaction et suggestions pour les prochaines promotions.
