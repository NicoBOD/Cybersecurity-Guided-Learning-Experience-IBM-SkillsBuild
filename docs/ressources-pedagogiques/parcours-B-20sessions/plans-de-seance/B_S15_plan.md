# Plan de séance — Session B15 : Conformité & réglementations vie privée (+ Atelier de Synthèse 3)
Parcours : B 20 sessions  |  Module : D — Gouvernance, risques & conformité  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (verbes d'action)
- **Expliquer** les devoirs majeurs du RGPD (consentement, minimisation, conservation, registre, notification sous 72 h) et les deux paliers de sanctions.
- **Identifier** les rôles de la CNIL et du DPO (en duo avec le RSSI).
- **Auditer** une politique de confidentialité pour en extraire les clauses non conformes.
- **Coter** collectivement les risques de MedDistri dans la matrice 4x4 (**Atelier de Synthèse 3**).

## Prérequis & progression
- **Prérequis** : B13 (gouvernance) et B14 (matrice de risques — révisée pour l'atelier).
- **Lien de progression** : Clôture le module D et son cycle gouvernance → risques → conformité. Ouvre le module E : les opérations de sécurité (SOC en B16, SIEM en B17).

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous) — le n°5 (cotation) comporte **4 options (A-D)**.
- [ ] Le partage d'écran est testé avec le diaporama B15 ([spécifications](../slides/B_S15_slides_spec.md)) ; la matrice 4x4 vide de l'atelier est prête à remplir (tableau blanc ou slide dédiée).
- [ ] Les trois scénarios MedDistri de l'atelier sont prêts à afficher (voir [Ateliers de Synthèse](../projet/B_miniprojets.md)).
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | L'amende RGPD record en Europe ? | B) 1,2 milliard d'euros |
| 2 | 0:30 | Sondage | Clause A — cartes bancaires conservées « définitivement » ? | B) Violation de la limitation de conservation |
| 3 | 0:34 | Sondage | Clause B — revente « sans opposition possible » ? | A) Consentement forcé + droit supprimé |
| 4 | 0:38 | Sondage | Clause C — recommandé AR au siège ? | C) Exercice des droits inutilement complexe |
| 5 | 0:55 | Sondage | Atelier — impact du rançongiciel sur la compta (1-4) ? | C ou D (majeur/critique — selon débat) |
| 6 | 1:16 | Sondage | Les plafonds de sanction du RGPD ? | B) Deux paliers : 10 M€/2 % et 20 M€/4 % |
| 7 | 1:18 | Sondage | Une adresse IP est-elle une donnée personnelle ? | B) Oui, identification indirecte |
| 8 | 1:20 | Sondage | Le rôle du registre des traitements ? | A) Recenser qui/quoi/pourquoi/durée/sécurités |
| 9 | Tampon | Sondage | Traceurs publicitaires : que faut-il implémenter ? | B) Une CMP avec refus aussi simple que l'accord |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil & retour sur les bandeaux cookies | 💬 Chat : observations |
| 0:04–0:10 | Brise-glace : l'amende record | 📊 Sondage n°1 |
| 0:10–0:22 | Séquence 1 : Les fondamentaux du RGPD | 💬 Chat : donnée personnelle ou pas ? |
| 0:22–0:28 | Séquence 2 : CNIL & DPO | Question rhétorique |
| 0:28–0:42 | Activité : L'audit de la charte EcoLog | 📊 Sondages n°2, 3, 4 |
| 0:42–0:52 | Chiffres clés & affaires Google + Clearview | 💬 Chat : réactions |
| 0:52–1:12 | **Atelier de Synthèse 3 : la matrice de MedDistri** | 📊 Sondage n°5 + 💬 cotations & traitements |
| 1:12–1:16 | Mini-scénario : les 72 heures du week-end | 🤔 Chat : A, B ou C |
| 1:16–1:22 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:22–1:26 | Exercice bonus : les traceurs (tampon) | 📊 Sondage n°9 |
| 1:26–1:30 | Synthèse, clôture du module D & teaser B16 | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & retour sur le self-paced

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous — dernière session du module Gouvernance, et votre troisième Atelier de Synthèse ! Votre observation de la semaine : les bandeaux cookies. Qui a repéré un bandeau SANS bouton "tout refuser" ? Racontez dans le chat. »

**Points à dérouler :**
- Lire 3-4 observations : « gardez-les en tête — en fin de session, vous saurez exactement pourquoi ces bandeaux sont illégaux, et ce qu'ils ont coûté à certains géants. »
- Rappel express de B14 : la matrice V×G, les 4 traitements, Mondelez — « la matrice ressert ce soir : l'atelier ! »
- Annonce du programme : le RGPD et ses dents, la CNIL, l'audit d'une charte — et la matrice de MedDistri.

**Transition scriptée :** « D'abord, mesurons les dents de la loi. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (l'amende record)

**Consigne :** Lancer le **📊 Sondage n°1** — l'amende RGPD record en Europe ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse B : 1,2 MILLIARD d'euros — Meta, 2023, pour des transferts de données vers les États-Unis sans garanties suffisantes. Et la réponse A n'était pas anodine : 50 millions, c'est Google en 2019, la première grande amende du RGPD, infligée par la CNIL française — on la décortique tout à l'heure. Le message : la conformité n'est pas de la paperasse, c'est du droit avec des dents — calculées en pourcentage du chiffre d'affaires MONDIAL. »

**Transition scriptée :** « Voyons ce que ce règlement exige — cinq devoirs, pas un de plus. »

### 0:10–0:22 — Séquence 1 : Les fondamentaux du RGPD

**Points de contenu à dérouler (support §1) :**
- **La donnée personnelle** : identification directe OU indirecte — relance chat : *« Donnée personnelle ou pas : une adresse IP ? une plaque d'immatriculation ? la météo ? »* (les deux premières : oui !).
- **Les 5 devoirs** : transparence et consentement (acte positif, libre, éclairé — pas de cases pré-cochées) ; **minimisation** (le meilleur levier de sécurité : une donnée non collectée ne fuite pas — c'est le levier qui abaisse la GRAVITÉ, rappel B14) ; conservation limitée ; **registre des traitements** ; **notification sous 72 h** (calendaires, dès la prise de connaissance).
- **Les deux paliers de sanction** : jusqu'à 10 M€ ou 2 % du CA mondial — et jusqu'à 20 M€ ou 4 % pour les manquements les plus graves, le plus élevé retenu.
- L'analogie du restaurant (support) : l'inspecteur d'hygiène, l'opt-in des épices, le groupe sanguin pour une pizza.

**Transition scriptée :** « Qui fait respecter tout cela ? Deux acteurs : un gendarme et un pilote. »

### 0:22–0:28 — Séquence 2 : CNIL & DPO

**Points de contenu à dérouler (support §2-3) :**
- **La CNIL** : conseiller, informer sur les droits (accès, rectification, oubli), contrôler (en ligne et sur site), sanctionner — et publier ses sanctions (le préjudice d'image en prime).
- **Le DPO** : le pilote interne — registre, AIPD pour les traitements à risque, point de contact unique des citoyens et de la CNIL.
- **Le duo DPO/RSSI** : le RSSI protège le patrimoine, le DPO garantit les droits des personnes — en cas de fuite : enquête technique (RSSI) + notifications légales (DPO). Deux casquettes, une coordination.
- Question rhétorique : *« Lisez une sanction CNIL récente : qu'y trouve-t-on ? »* — des mots de passe en clair, l'absence de chiffrement, des durées illimitées : la conformité et la technique sont les deux faces de la même pièce (c'est l'activité pratique de la semaine).

**Transition scriptée :** « À vous d'auditer : le marketing d'EcoLog a rédigé sa charte de confidentialité. Trois clauses, trois votes... et trois problèmes. »

### 0:28–0:42 — Activité : L'audit de la charte EcoLog (Sondages n°2 à 4)

**Consigne :** Afficher l'extrait de charte (support, activité « L'audit de la charte »), le lire à voix haute, puis lancer les **📊 Sondages n°2, 3, 4** (~4-5 min chacun : clause, vote, débrief avec correction conforme).

**🎙️ Verbatim de lancement :**
> « Vous êtes le DPO d'EcoLog. Le marketing vous soumet sa charte, plein de bonne volonté. Clause A : "nous conservons vos données de carte bancaire de manière définitive pour faciliter vos futurs achats." Quel est le problème ? »

**Débriefs scriptés (points obligatoires) :**
- N°2 (clause A) : violation de la **limitation de conservation** — suppression après transaction, sauf consentement explicite (case NON pré-cochée) et stockage sécurisé. Le chiffrement ne légalise pas une conservation illégale.
- N°3 (clause B) : double infraction — consentement **forcé** (l'inscription ne se conditionne pas à la revente) et **droit d'opposition** supprimé (il est inaliénable). Correction : opt-in facultatif, retirable.
- N°4 (clause C) : le principe de **symétrie** — exercer ses droits doit être aussi simple que donner ses données : un e-mail ou un formulaire, pas un recommandé au siège.
- Conclure : « trois infractions de bonne foi — la conformité se conçoit dès la rédaction : c'est le *Privacy by Design*. »

**Transition scriptée :** « Et quand on ne conçoit pas conforme ? Deux affaires — un géant et un hors-la-loi assumé. »

### 0:42–0:52 — Chiffres clés & deux affaires réelles

**Chiffres (2 min, support §4) :** 1,2 Md€ — Meta, 2023, le record ; 50 M€ — Google, CNIL 2019, la première grande sanction (confirmée par le Conseil d'État en 2020) ; 20 M€ + 5,2 M€ d'astreinte — Clearview AI (2022-2023).

**Cas n°1 — Google vs CNIL, 2019 (4 min, support §5) :** raconter : huit mois après l'entrée en application du RGPD, sur plaintes d'associations ; PAS de piratage — les griefs portent sur la **conception** : information diluée dans une arborescence illisible (transparence), consentement publicitaire ni spécifique ni éclairé ; 50 M€, confirmés en 2020. Leçons : la CNIL juge l'ergonomie du consentement ; le RGPD s'applique aux géants américains ciblant l'Europe ; la conformité se joue dans le design des produits.

**Cas n°2 — Clearview AI, 2022-2023 (4 min, support §5) :** raconter : plus de 30 milliards de visages aspirés sur Internet pour vendre de la reconnaissance faciale ; des Français dans la base — sans consentement ni base légale ; 20 M€ (le plafond) + injonction d'effacer ; la société ignore la décision → **astreinte de 5,2 M€** (2023) ; sanctions en chaîne en Europe. Leçons : « les données étaient publiques » n'est PAS une base légale ; le biométrique est une donnée sensible ; la conformité est une condition d'accès au marché européen. Relance chat : *« Quel détail vous marque le plus ? »*

**Transition scriptée :** « Changement de casquette : la matrice de B14 ressort — MedDistri attend son comité des risques. »

### 0:52–1:12 — Atelier de Synthèse 3 : la matrice de MedDistri (Sondage n°5 + chat)

**Format** (cf. [Ateliers de Synthèse](../projet/B_miniprojets.md)) : ~20 minutes, par sondage et chat.

**1. Présentation (3 min) :** afficher les trois scénarios de menace : ① rançongiciel sur la base comptable ; ② vol du portable d'un commercial (données clients à bord) ; ③ usurpation du dirigeant pour une fraude au virement (le BEC de B04). Rappel de la grille : V × G, 1 à 16.

**2. Vote n°5 + débat (7 min) :** lancer le **📊 Sondage n°5** — l'impact du scénario ① sur l'activité (1 à 4) — puis faire justifier dans le **chat** : *« défendez votre cotation en une phrase ! »* (attendu côté 3 : « la compta bloque salaires et facturation » ; côté 4 : « une PME sans trésorerie meurt en quelques semaines »). Trancher collectivement — 3 et 4 se défendent : **la discussion EST l'exercice**. Coter la vraisemblance à l'oral (élevée — les rançongiciels frappent d'abord les PME : ANSSI, B01), placer le risque dans la matrice à l'écran.

**3. Les deux autres scénarios au chat (7 min) :** *« Scénario ② — V ? G ? et quel traitement de B14 ? »* (attendu : chiffrement du disque B08 + effacement à distance = réduire l'impact) ; *« Scénario ③ ? »* (attendu : contre-appel B04 + double validation = réduire la vraisemblance). Remplir la matrice en direct, corriger, valoriser.

**4. Synthèse (3 min) :**
> « Trois risques cotés, trois traitements, vingt minutes : vous venez de tenir un comité des risques. Et remarquez — chaque parade vient d'une session du parcours : le chiffrement de B08, le contre-appel de B04, les sauvegardes de B12. Le grand atelier final assemblera TOUT. »

### 1:12–1:16 — 🤔 Mini-scénario : les 72 heures du week-end

**Consigne :** Afficher le mini-scénario du support : fuite confirmée vendredi 18h — « le délai est en jours ouvrés, profitez du week-end ». *« Tapez A, B ou C dans le chat. »*

**Débrief :** B — les 72 heures courent dès la **prise de connaissance**, calendaires, week-ends compris (une notification initiale incomplète se complète ensuite). A est une légende tenace ; C est le scénario Uber de B13. Le réflexe : documenter dès la découverte — l'assureur (B14) et l'auditeur (B13) le demanderont aussi.

**Transition scriptée :** « Trois questions pour clore le module en beauté. »

### 1:16–1:22 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : les deux paliers (10 M€/2 % et 20 M€/4 %, le plus élevé retenu) ; l'IP est une donnée personnelle (identification indirecte) ; le registre recense qui/quoi/pourquoi/durée/sécurités. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/B_S15_support.md).

### 1:22–1:26 — Exercice bonus (Sondage n°9) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°9** — traceurs publicitaires : que faut-il implémenter ? Débrief : une CMP où **refuser est aussi simple qu'accepter** (B) — les bandeaux sans « tout refuser » ont valu des sanctions à plusieurs géants. Boucler avec les observations du début de session : « qui avait repéré un bandeau non conforme ? Vous savez maintenant le nommer. » À couper en cas de retard.

### 1:26–1:30 — Synthèse & clôture du module D

**🎙️ Verbatim de synthèse :**
> « Module Gouvernance, risques et conformité : terminé ! Vous savez écrire une politique qui engage (B13), coter et arbitrer un risque (B14), et ce soir : les cinq devoirs du RGPD, les deux paliers de sanction, et un comité des risques mené en vingt minutes. Prochaine étape : redescendre dans la salle des machines — le module Opérations. Un mot que vous retenez, dans le chat ! »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Self-paced : cours IBM SkillsBuild *"Introduction to Data Privacy and GDPR"* (~1h30) + lire une sanction CNIL récente (cnil.fr) + rechercher les acronymes **SOC** et **SIEM** — transition directe vers le module E.
- Teaser B16 : « la semaine prochaine : le SOC, la tour de contrôle de la sécurité. Avec l'histoire de l'alerte qui a révélé l'une des plus grandes attaques de la décennie — un simple deuxième téléphone enregistré sur un compte... et un analyste qui a pris la peine de vérifier. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**Exercice bonus n°9** (1:22–1:26) — il est dans le support en exercice bonus.
2. Compresser le cas Clearview à 2 min (l'essentiel : « données publiques » ≠ base légale, l'astreinte).
3. Dans l'atelier, traiter le scénario ③ en 2 min (cotation orale rapide).
4. Ne JAMAIS couper : l'audit de la charte, le cas Google, l'Atelier de Synthèse, le quiz.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°3 : sanctionné sans fuite — la loyauté du traitement).
2. Étendre l'atelier : faire coter un 4ᵉ scénario proposé par le chat.
3. Questions/réponses libres sur l'ensemble du module D.

## Travail en autonomie (Self-paced)
* **Avant la session suivante (B16)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Introduction to Data Privacy and GDPR"* (durée estimée : 1h30).
  * **Activité pratique** : Lire le résumé d'une sanction CNIL récente (cnil.fr) et repérer les manquements techniques sanctionnés (mots de passe faibles, absence de chiffrement...).
  * **Transition Module E** : Rechercher la signification des acronymes SOC (Security Operations Center) et SIEM (Security Information and Event Management).
