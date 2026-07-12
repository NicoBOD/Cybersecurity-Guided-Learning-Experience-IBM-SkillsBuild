# Parcours A — Session 05 : Gouvernance, risque, conformité & vie privée
Module : GRC & Vie Privée  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (4, verbes d'action)
- **Décrire** la place et le rôle de la gouvernance, de la gestion des risques et de la conformité (GRC) dans la stratégie cyber d'une organisation.
- **Identifier** la structure et les objectifs fondamentaux des référentiels de sécurité internationaux (ISO 27001, NIST CSF 2.0 et ses 6 fonctions).
- **Évaluer** un risque cyber simple en estimant sa vraisemblance et son impact à l'aide d'une matrice qualitative d'analyse de risques, et choisir une stratégie de traitement.
- **Expliquer** les principes directeurs du RGPD (consentement, finalité, minimisation, droits des personnes) et les obligations en cas de violation.

## Prérequis
- Sessions précédentes : A1 à A4.
- Self-paced AVANT la séance (~60 min) : Lecture d'articles synthétiques sur le rôle de la CNIL et les droits fondamentaux conférés par le RGPD. Visionnage d'une courte introduction méthodologique sur ce qu'est un risque (menace vs vulnérabilité).

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **10 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama S05 ([spécifications](../slides/A_S05_slides_spec.md)) — y compris la matrice 4×4.
- [ ] Le [script de la Démo 5 — Matrice de risques en direct](../outils/A_scripts_demo.md#demo-5-matrice-risques) est relu ; la feuille de calcul (ou le tableau visuel) est prête à projeter.
- [ ] Le chat est ouvert ; un modérateur remonte les questions si possible.
- [ ] Un minuteur est visible du mentor.

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Amende maximale RGPD ? | C) 20 M€ / 4 % du CA mondial (le plus élevé) |
| 2 | 0:39 | Sondage | Scénario A (portable volé, criticité 9) : stratégie ? | A) Réduire (chiffrement + MFA) |
| 3 | 0:44 | Sondage | Scénario B (ransomware facturation, criticité 12) ? | B) Réduire puis transférer le résiduel |
| 4 | 0:49 | Sondage | Scénario C (inondation, criticité 4) ? | B) Réduire à coût marginal + accepter documenté |
| 5 | 1:08 | Sondage | Obligation en cas de fuite de données ? | A) Notifier la CNIL sous 72 h |
| 6 | 1:11 | Sondage | Facturer le droit d'accès d'un client ? | B) Non, gratuit |
| 7 | 1:22 | Sondage | PSSI = règlement intérieur ? | A) Vrai |
| 8 | 1:24 | Sondage | Transférer un risque le fait disparaître ? | B) Faux |
| 9 | 1:26 | Sondage | Minimisation = collecter le moins possible ? | A) Vrai |
| 10 | Tampon | Sondage | N° de sécurité sociale dans un fichier de prospection ? | B) Non (minimisation) |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil & retour sur les devoirs d'A4 | Chat : « MFA activé ? » |
| 0:04–0:10 | Brise-glace : le prix du non-respect | 📊 Sondage n°1 |
| 0:10–0:15 | Qui décide, qui paie ? (la voiture de course) | 💬 Chat : débat |
| 0:15–0:29 | Séquence 1 : Gouvernance — PSSI, ISO 27001, NIST CSF 2.0 | Question rhétorique |
| 0:29–0:39 | Séquence 2 : La gestion des risques (matrice & stratégies) | Question rhétorique |
| 0:39–0:53 | Activité : Le Comité des Risques | 📊 Sondages n°2, 3, 4 |
| 0:53–1:01 | Démo 5 : La matrice de risques en direct | Chat : cotations proposées |
| 1:01–1:15 | Séquence 3 : Le RGPD (principes, droits, 72 h) | 📊 Sondages n°5, 6 |
| 1:15–1:22 | Chiffres & cas réels : Google, Meta, Clearview AI | 💬 Chat : « tout accepté sans lire » |
| 1:22–1:27 | Quiz de validation | 📊 Sondages n°7, 8, 9 |
| 1:27–1:30 | Synthèse, règle d'or & devoirs | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & retour sur les devoirs

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous, et bienvenue dans la seconde moitié du parcours ! Petit contrôle d'hygiène numérique : la semaine dernière, je vous avais demandé d'installer un gestionnaire de mots de passe et d'activer le MFA sur votre messagerie. Tapez "fait", "en cours" ou "pas encore" dans le chat — sans jugement, mais avec un petit rappel : c'est LE geste au meilleur rapport protection/effort. »

**Points à dérouler :**
- Commenter la proportion, encourager les « pas encore ».
- Pivot : « jusqu'ici, nous avons vu la technique : chiffrer, filtrer, sauvegarder. Aujourd'hui, on monte au comité de direction : QUI décide de tout cela ? Avec quel budget ? Et que dit la LOI ? Bienvenue dans la GRC. »

**Transition scriptée :** « Et pour comprendre pourquoi la loi s'invite au comité de direction, commençons par le prix de la désinvolture. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (le prix du non-respect)

**Consigne :** Lancer le **📊 Sondage n°1** — *« Quelle amende maximale la CNIL peut-elle infliger en cas de manquement grave au RGPD ? »* Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse C : jusqu'à 20 millions d'euros ou 4 % du chiffre d'affaires mondial — et attention, c'est le montant LE PLUS ÉLEVÉ des deux qui sert de plafond. Il existe même deux paliers : 10 millions ou 2 % pour certains manquements, le double pour les plus graves. Et ce n'est pas de la dissuasion théorique : le record européen dépasse le milliard d'euros — on verra qui et pourquoi en fin de session. Précision importante : la CNIL commence toujours par accompagner. Mais pour une PME, même une amende modérée PLUS la une des journaux, c'est souvent fatal. »

**Transition scriptée :** « Des amendes, des budgets, des décisions... mais au fait : chez vous, qui décide ? »

### 0:10–0:15 — 💬 Qui décide, qui paie ?

**Consigne :** Question chat — *« Dans votre organisation (ou une que vous connaissez), qui décide du budget sécurité informatique : le technicien, le DSI, le dirigeant, personne ? Répondez en un mot dans le chat. »* Lire 4-5 réponses.

**🎙️ Formulation de synthèse (l'analogie de la voiture de course) :**
> « Réponses variées — et c'est le problème que la GRC résout. Imaginez une voiture de course : le RISQUE, c'est l'accident — casque, airbags, pneus vérifiés. La CONFORMITÉ, c'est le code de la route — avec ses amendes. Et la GOUVERNANCE, c'est le pilote et son écurie : qui fixe la stratégie, le budget, les règles d'équipe. Une voiture sans pilote ne gagne pas de championnat, quelle que soit la qualité de ses pneus. Aujourd'hui, on apprend à piloter. »

### 0:15–0:29 — Séquence 1 : Gouvernance — PSSI, ISO 27001, NIST CSF 2.0

**Points de contenu à dérouler (support §1) :**
- La gouvernance = « qui fait quoi, comment, sous quelle autorité » ; le RSSI propose, la direction décide et signe.
- **La PSSI** : la loi interne — rédigée par le RSSI, signée par la DG, valeur de règlement intérieur. Exemples de règles concrètes (mots de passe, clés USB, arrivées ET départs — le « Leaver » d'A4).
- **ISO 27001** : une méthode, pas une liste d'outils ; le cycle PDCA (roue de Deming) ; la certification comme argument commercial (« prouver à ses clients qu'on gère »).
- **NIST CSF 2.0** : les **6 fonctions** — insister sur la nouveauté : la version 2.0 (février 2024) a ajouté **Gouverner** en socle des cinq historiques (Identifier, Protéger, Détecter, Répondre, Récupérer). Argument pédagogique : « il a fallu dix ans au NIST pour graver officiellement ce que cette session raconte : la sécurité se pilote en comité de direction. »
- Repère méta : le parcours A suit ce cadre — A1-A5 = Gouverner/Identifier/Protéger ; A6-A7 = Détecter/Répondre/Récupérer.

**Question rhétorique (0:27) :** *« À votre avis, pourquoi une certification ISO 27001 fait-elle gagner des appels d'offres ? »* — réponse : elle remplace la confiance déclarative (« on est sérieux, promis ») par une preuve auditée.

**Transition scriptée :** « La gouvernance fixe le cap. Mais avec un budget limité, comment choisir ses batailles ? Réponse : en cotant les risques. »

### 0:29–0:39 — Séquence 2 : La gestion des risques

**Points de contenu à dérouler (support §2 + Focus pratique) :**
- Le principe : on ne sécurise pas tout à 100 % — on **priorise**. Prolongement chiffré de la formule d'A1 (*Risque = Menace × Vulnérabilité × Impact*) : on passe de l'intuition à la cotation.
- **Criticité = Vraisemblance (1-4) × Impact (1-4)** ; projeter la matrice 4×4 du support avec ses trois zones (Rouge 12-16 : traitement obligatoire ; Orange 4-9 : réduction planifiée ; Verte 1-3 : acceptation suivie).
- Point de lecture subtil : la criticité 4 s'obtient de trois façons (4×1, 2×2, 1×4) — l'événement rarissime mais critique mérite la même vigilance que le fréquent mais bénin.
- **Les 4 stratégies** avec l'analogie de l'assuré : le vélo à 50 € (accepter), la voiture (réduire + transférer), le verglas nocturne (éviter). Marteler la nuance de « transférer » : l'assurance rembourse des frais, elle ne restaure ni les données ni la réputation.
- « Accepter » = décision documentée, datée, signée, réévaluée — pas de l'aveuglement.

**Question rhétorique (0:37) :** *« Quelle criticité donneriez-vous à un rançongiciel sur votre serveur de facturation ? »* — laisser 5 secondes : « gardez votre chiffre en tête, vous allez voter dessus. »

### 0:39–0:53 — Activité : Le Comité des Risques (Sondages n°2 à 4)

**Consigne :** Annoncer : « vous siégez au comité des risques de la PME ; le RSSI présente trois scénarios cotés ; le comité — vous — vote la stratégie. » Lancer les **📊 Sondages n°2, 3, 4** (~4-5 min par scénario : présentation + cotation, vote, débrief). Scénarios, options et débriefs complets : voir le [support, section « Le Comité des Risques »](../supports-md/A_S05_support.md).

**🎙️ Verbatim de lancement :**
> « Séance du comité des risques, trois dossiers à l'ordre du jour. Pour chacun : la cotation du RSSI, puis votre vote sur la stratégie — Réduire, Transférer, Éviter ou Accepter. Les quatre réponses existent dans la vraie vie ; à vous de choisir la bonne au bon endroit. Dossier n°1 : le portable volé... »

**Débriefs scriptés (points obligatoires) :**
- N°2 (portable, criticité 9) : Réduire — le chiffrement effondre l'IMPACT (un portable chiffré volé = incident matériel, pas fuite : le consultant d'A1). « Éviter » (interdire les portables) tuerait l'activité pour tuer le risque.
- N°3 (ransomware, criticité 12) : zone rouge = traitement obligatoire ; le piège est « Transférer seulement » — l'assurance rembourse, elle ne restaure rien, et les assureurs exigent désormais MFA et sauvegardes avant de couvrir. La bonne réponse combine : réduire d'abord, transférer le résiduel.
- N°4 (inondation, criticité 4) : la différence entre B et C est TOUTE la maturité d'une gouvernance — accepter se documente, se date, se signe, se réévalue. Et la copie hors site est déjà exigée par le 3-2-1 d'A4 : coût marginal.
- Conclure : « trois scénarios, trois stratégies — la matrice n'est pas un exercice d'école, c'est un outil d'allocation de budget. »

### 0:53–1:01 — Démo 5 : La matrice de risques en direct

**Consigne :** Dérouler la [Démo 5 — Construire une matrice de risques en direct](../outils/A_scripts_demo.md#demo-5-matrice-risques) en partage d'écran : reprendre les trois scénarios votés, les placer dans la feuille de calcul, puis montrer l'effet du traitement — la criticité **brute** qui devient **résiduelle** (ex. le ransomware passe de 12 à 6 après sauvegardes immuables + EDR).

**Points de débrief obligatoires :**
- Faire proposer par le chat la cotation d'un 4e scénario (ex. « fuite d'un fichier RH par e-mail mal adressé ») et le placer en direct.
- Montrer que la matrice se lit AVANT/APRÈS : c'est l'outil qui justifie le budget (« voilà ce que vos 20 000 € achètent : un passage du rouge à l'orange »).
- En cas de pépin technique : la matrice du support (Focus pratique) se déroule à l'oral.

**Transition scriptée :** « Le risque est coté, le budget arbitré. Reste la troisième lettre : la Conformité — et en Europe, elle a un nom : RGPD. »

### 1:01–1:15 — Séquence 3 : Le RGPD (Sondages n°5 et 6)

**Points de contenu à dérouler (support §3) :**
- Le champ d'application : toute entité, où qu'elle soit, traitant des données de résidents européens.
- Ce qu'est une **donnée personnelle** (jusqu'à l'adresse IP) — faire réagir : « votre adresse IP est une donnée personnelle : surpris ? »
- **Les 4 principes**, chacun avec son exemple : finalité (le numéro de livraison non revendu), minimisation (« le moindre privilège de la donnée » — écho A4), consentement actif (la case pré-cochée interdite), droits des personnes (accès gratuit, rectification, effacement).
- **Les obligations en cas de violation** : notification CNIL sous 72 h (le chrono court dès la découverte — d'où l'importance de la détection, teaser A6), information des personnes si risque élevé (France Travail, A1 : c'est exactement ce qui s'est passé).

**Interaction (1:08) :** Lancer les **📊 Sondages n°5 puis 6** (l'obligation des 72 h ; la gratuité du droit d'accès). Débriefs dans le [support, « Exercice d'application RGPD »](../supports-md/A_S05_support.md).

**Transition scriptée :** « Tout cela vous semble peut-être encore abstrait. Trois noms vont le rendre très concret : Google, Meta, Clearview. »

### 1:15–1:22 — Chiffres & cas réels

**Chiffres (2 min, support §4) :** projeter les montants — **1,2 Md€** (Meta, 2023, record : transferts de données vers les États-Unis) ; **50 M€** (Google, CNIL, 2019) ; **20 M€** (Clearview AI, CNIL, 2022 : la reconnaissance faciale nourrie de photos aspirées sur le web) ; plusieurs milliards cumulés en Europe depuis 2018.

**Cas développé — Google vs CNIL, 2019 (3-4 min, support §5) :** raconter : huit mois après l'entrée en application du RGPD, 50 M€ — la sanction fondatrice. Le point clé : **ni piratage, ni fuite** — des manquements de PRINCIPES : information diluée dans les menus, consentement ni éclairé ni spécifique (la case unique valant accord global). Punchline : « un système parfaitement sécurisé peut être parfaitement illégal. La conformité ne se réduit pas à la sécurité. »

**Interaction (1:20) — 💬 Question chat :** *« Pensez au dernier site où vous avez "tout accepté" sans lire : quelle donnée pensez-vous lui avoir confiée sans vraiment le vouloir ? »* — lire 3-4 réponses, conclure : « c'est exactement ce que finalité et consentement visent à corriger — et votre exercice de la semaine vous le fera vérifier. »

### 1:22–1:27 — Quiz de validation (Sondages n°7 à 9)

**Consigne :** Lancer les **📊 Sondages n°7, 8, 9** à la suite (~90 s chacun). Réponses : Vrai ; Faux ; Vrai. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/A_S05_support.md).

### 1:27–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Trois lettres à emporter : G comme GOUVERNANCE — qui décide, avec quel budget, et le NIST CSF 2.0 l'a gravé dans le marbre avec sa fonction Gouverner ; R comme RISQUE — on ne supprime jamais un risque, on le cote et on le traite : Réduire, Transférer, Éviter, Accepter ; C comme CONFORMITÉ — et souvenez-vous de Google : pas besoin d'être piraté pour être sanctionné. Tapez dans le chat le mot que vous retenez. »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Devoirs : module IBM SkillsBuild *Opérations de sécurité, surveillance et gestion des logs* (~70 min) + exercice individuel : consulter la politique de confidentialité d'un service en ligne habituel et relever les finalités d'usage de ses données.
- Teaser A6 : « la semaine prochaine, on descend dans la salle des machines : le SOC, les alertes, les vulnérabilités — comment on DÉTECTE une attaque. Rappelez-vous : le chrono des 72 heures ne démarre que si quelqu'un s'aperçoit de la fuite... »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Compresser la démo 5 (0:53–1:01) à 5 min : placer les trois scénarios sans le 4e proposé par le chat.
2. Compresser les chiffres (1:15) : les trois montants en 60 secondes, puis le seul cas Google.
3. Ne JAMAIS couper : le Comité des Risques, la séquence RGPD avec ses sondages, le cas Google.
4. Le **📊 Sondage n°10** (bonus minimisation) est le tampon officiel : en autonomie si besoin.

**Si vous êtes en avance :**
1. Lancer le **📊 Sondage n°10** (le numéro de sécurité sociale dans le fichier de prospection) — écho direct au cas Google sur le consentement générique.
2. Dérouler les **Questions de réflexion** du support (notamment la n°3 : la cyber-assurance, vice ou vertu ? — excellent débat de chat).
3. Ouvrir une séquence questions/réponses libre.

## Articulation avec l'atelier de fin de parcours
- Cette session fournit les notions de conformité et de traitement de risques pour l'Atelier d'Audit Interactif MedDistri, permettant d'adopter une posture de conseil sur le RGPD et l'allocation du budget cyber (cotation des risques et arbitrages).

## Self-paced APRÈS la séance (~90 min) & évaluation formative
- Suivre le cours en ligne d'introduction à la protection des données personnelles (RGPD) ou le module équivalent d'un organisme national (type CNIL en France).
- Auto-évaluation en ligne (10 questions sur le RGPD, les cadres ISO 27001 / NIST CSF et l'analyse de risques).
- Lecture suggérée : Le guide de sécurité des données personnelles (recommandations CNIL ou agence cyber nationale).
