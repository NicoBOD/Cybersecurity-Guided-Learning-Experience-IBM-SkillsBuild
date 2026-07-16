# Plan de séance — Session B12 : Sécurité & confidentialité des données (+ Atelier de Synthèse 2)
Parcours : B 20 sessions  |  Module : C — Identités, cloud & données  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (verbes d'action)
- **Modéliser** un plan de classification des données sur 4 niveaux de sensibilité.
- **Différencier** le chiffrement au repos et en transit, et expliquer le rôle du DLP.
- **Appliquer** la règle de sauvegarde 3-2-1 (copie hors site, hors ligne/immuable, restauration testée) face aux rançongiciels.
- **Construire** collectivement le plan de protection des données de MedDistri (**Atelier de Synthèse 2**).

## Prérequis & progression
- **Prérequis** : B09 à B11 (identités, cryptographie, cloud) — venir avec sa typologie de données sensibles (self-paced B11).
- **Lien de progression** : Clôture le module C en protégeant la donnée sur tout son cycle de vie, et assemble les acquis dans l'Atelier de Synthèse 2. Ouvre le module D : gouvernance, risques et conformité (RGPD en B15).

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama B12 ([spécifications](../slides/B_S12_slides_spec.md)) ; le **tableau blanc** (ou document partagé) est prêt pour rédiger les 5 règles d'or de l'atelier.
- [ ] Les contraintes MedDistri de l'atelier sont prêtes à afficher (voir [Ateliers de Synthèse](../projet/B_miniprojets.md)).
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Incendie de Strasbourg 2021 : combien de sites hors ligne ? | C) ~3,6 millions |
| 2 | 0:53 | Sondage | Atelier — la MFA des 15 commerciaux ? | B) Application d'authentification / FIDO2 |
| 3 | 0:58 | Sondage | Atelier — classer les fiches de paie sur le cloud ? | B) Confidentielles |
| 4 | 1:03 | Sondage | Atelier — où placer la 3e copie (3-2-1) ? | B) Cloud immuable hors site / coffre externe |
| 5 | 1:14 | Sondage | Vos données personnelles : où en êtes-vous ? | Opinion (pas de bonne réponse) |
| 6 | 1:18 | Sondage | HTTPS puis disque non chiffré : que manque-t-il ? | B) Le chiffrement au repos |
| 7 | 1:20 | Sondage | Que fait un DLP face à l'envoi de cartes bancaires ? | B) Bloque et alerte |
| 8 | 1:22 | Sondage | Pourquoi la copie hors site doit-elle être hors ligne/immuable ? | C) Les rançongiciels ciblent les sauvegardes |
| 9 | Tampon | Sondage | Incendie + sauvegardes dans les mêmes locaux : résultat ? | B) Perte définitive |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil & retour sur la typologie des données | 💬 Chat : données sensibles listées |
| 0:04–0:10 | Brise-glace : la nuit de Strasbourg | 📊 Sondage n°1 |
| 0:10–0:20 | Séquence 1 : La classification des données | 💬 Chat : la maison d'édition |
| 0:20–0:28 | Séquence 2 : Chiffrement (repos/transit) & DLP | Question rhétorique |
| 0:28–0:36 | Séquence 3 : La sauvegarde 3-2-1 | Question rhétorique |
| 0:36–0:44 | Chiffres clés & affaires OVHcloud + Morgan Stanley | 💬 Chat : réactions |
| 0:44–0:48 | Mini-scénario : les disques revendus | 🤔 Chat : A, B ou C |
| 0:48–1:14 | **Atelier de Synthèse 2 : le plan de protection MedDistri** | 📊 Sondages n°2, 3, 4 + 💬 règles d'or |
| 1:14–1:18 | Et vous ? Vos sauvegardes personnelles | 📊 Sondage n°5 |
| 1:18–1:24 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:24–1:27 | Exercice bonus : l'incendie fatal (tampon) | 📊 Sondage n°9 |
| 1:27–1:30 | Synthèse, clôture du module C & teaser B13 | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & retour sur le self-paced

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous — dernière session du module Identités, cloud et données, ET votre deuxième Atelier de Synthèse ! Votre mission de la semaine : les types de données sensibles d'une entreprise. Citez-en un dans le chat ! »

**Points à dérouler :**
- Lire 4-5 réponses (attendu : paie, données clients, R&D, santé, finances) : « gardez cette liste — elle est la matière première de l'atelier de ce soir. »
- Rappel express de B11 : la responsabilité partagée, Capital One, « la donnée toujours au client ».
- Annonce du programme : classer, chiffrer, surveiller, sauvegarder — puis l'atelier MedDistri.

**Transition scriptée :** « On commence dans la nuit du 9 au 10 mars 2021, à Strasbourg. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (la nuit de Strasbourg)

**Consigne :** Lancer le **📊 Sondage n°1** — combien de sites hors ligne après l'incendie du datacenter ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse C : environ 3,6 millions de sites web hors ligne — l'incendie du datacenter SBG2 d'OVHcloud. Mais le vrai drame n'est pas la panne : certains clients avaient leurs sauvegardes DANS LE MÊME BÂTIMENT que leurs serveurs. Pour eux, la perte fut définitive. Ce soir, on protège la donnée à chaque étape de sa vie — et on termine par la règle qui aurait tout sauvé. L'histoire complète arrive en milieu de session. »

**Transition scriptée :** « Première étape de la vie d'une donnée : lui donner une étiquette. »

### 0:10–0:20 — Séquence 1 : La classification des données

**Points de contenu à dérouler (support §1) :**
- Le principe : on ne protège pas une brochure comme un brevet — l'effort suit la valeur.
- **Les 4 niveaux** avec l'analogie de la maison d'édition : Publique (les livres en vitrine), Interne (le planning dans le couloir), Confidentielle (les contrats des auteurs), Secrète (le manuscrit du prochain best-seller).
- Relance chat (0:16) : *« La liste des salaires de MedDistri : quel niveau ? Et le menu de la cantine ? »* — lire et corriger en direct.
- Le rôle pivot : la classification décide de TOUT le reste (droits, partages, chiffrement, DLP, sauvegardes).

**Transition scriptée :** « L'étiquette est posée. Maintenant : protéger la donnée dans chacun de ses états. »

### 0:20–0:28 — Séquence 2 : Chiffrement (repos/transit) & DLP

**Points de contenu à dérouler (support §2-3) :**
- **En transit** : TLS/SSH/VPN (B07) — protéger le trajet.
- **Au repos** : BitLocker/LUKS (B08, B10) — protéger le support volé ou éteint.
- **Le piège conceptuel** : machine allumée, session ouverte = données déchiffrées à la volée — un malware actif lit tout. Chaque état a son outil.
- **En usage : le DLP** — le gardien de sortie : il inspecte les flux (e-mail, USB, upload) et bloque les contenus classifiés ; l'exemple des numéros de cartes bancaires. Prérequis absolu : la classification (sans elle, tout ou rien).
- Question rhétorique : *« HTTPS protège-t-il votre fichier une fois arrivé sur le serveur ? »* — non : le trajet, pas le stockage (question n°6 du quiz).

**Transition scriptée :** « Reste le filet de sécurité ultime — celui qui sauve quand tout le reste a échoué. »

### 0:28–0:36 — Séquence 3 : La sauvegarde 3-2-1

**Points de contenu à dérouler (support §4) :**
- **3 copies** (production + 2 sauvegardes indépendantes) · **2 supports** différents · **1 hors site** — séparation géographique RÉELLE.
- **La mise à jour anti-rançongiciel** : la copie hors site doit être **hors ligne ou immuable** — les rançongiciels modernes chassent les sauvegardes connectées avant de chiffrer (plus de 9 attaques sur 10, selon Veeam).
- **Restaurer se teste** : RPO (combien puis-je perdre ? → fréquence) et RTO (en combien de temps redémarrer ? → vitesse) — une sauvegarde jamais restaurée n'existe pas.
- Dérouler l'**exemple ArchiTech** (support) : production RAID + NAS local nocturne + cloud immuable/coffre externe — qui survit à la panne, au rançongiciel ET à l'incendie.
- Question rhétorique : *« Maersk (B03) a survécu grâce à quoi ? »* — un serveur fortuitement hors ligne au Ghana. La chance n'est pas une stratégie : la copie hors ligne, si.

**Transition scriptée :** « Deux histoires vraies pour peser chaque règle — un incendie et une vente aux enchères. »

### 0:36–0:44 — Chiffres clés & deux affaires réelles

**Chiffres (2 min, support §5) :** ~3,6 millions de sites hors ligne (OVHcloud, 2021) ; 95 M$ d'amendes cumulées pour Morgan Stanley (60 + 35) ; plus de 9 attaques par rançongiciel sur 10 ciblent les sauvegardes (Veeam).

**Cas n°1 — OVHcloud, 2021 (4 min, support §6) :** raconter : la nuit du 9 au 10 mars, SBG2 ravagé ; 3,6 millions de sites hors ligne ; le message du fondateur — « activez votre plan de reprise d'activité » — révélant que beaucoup n'en avaient pas ; et les clients aux sauvegardes co-localisées : perte définitive, des années de travail. Leçons : le cloud n'abolit pas le risque physique ; la sauvegarde reste au client (B11 : la donnée, toujours au client) ; « hors site » = séparation géographique réelle.

**Cas n°2 — Morgan Stanley (3 min, support §6) :** raconter : les serveurs décommissionnés entre 2016 et 2019, le prestataire qui revend sans effacement fiable, les disques pleins de données clients aux enchères, certains jamais récupérés ; 60 M$ + 35 M$ d'amendes. Leçons : le cycle de vie va jusqu'à la destruction (supprimer n'efface que l'index, formater ne suffit pas) ; le chiffrement au repos systématique aurait tout changé ; la sous-traitance transporte la responsabilité. Relance chat : *« Quel détail vous marque le plus ? »*

### 0:44–0:48 — 🤔 Mini-scénario : les disques revendus

**Consigne :** Afficher le mini-scénario du support : MedDistri renouvelle son parc, le prestataire rachète disques compris. *« Tapez A, B ou C dans le chat. »*

**Débrief :** B — effacement sécurisé certifié (réécritures multiples), destruction physique pour le plus sensible, certificat du prestataire — et vérifier que le chiffrement au repos était actif (chaque disque égaré devient une brique illisible). A n'efface que l'index ; C à peine mieux. Morgan Stanley a payé 95 M$ pour cette leçon.

**Transition scriptée :** « Et maintenant, l'atelier : MedDistri passe au cloud, et c'est vous qui écrivez son plan de protection. »

### 0:48–1:14 — Atelier de Synthèse 2 : le plan de protection MedDistri (Sondages n°2 à 4)

**Format** (cf. [Ateliers de Synthèse](../projet/B_miniprojets.md)) : ~26 minutes, entièrement par sondages et chat.

**1. Présentation du cas (4 min) :** afficher les contraintes : 15 commerciaux en déplacement permanent, données migrées vers une suite bureautique SaaS, mots de passe enregistrés dans les navigateurs, fiches de paie sur l'espace de partage commun.

**🎙️ Verbatim de lancement :**
> « Voici la situation réelle de MedDistri après sa migration cloud. Prenez dix secondes... et dites-moi dans le chat : qu'est-ce qui vous inquiète le PLUS ? » — lire les réponses (attendu : mots de passe navigateur, paie accessible à tous, pas de MFA) : « tout y est. Corrigeons, décision par décision. »

**2. Les trois décisions (12 min) :** lancer les **📊 Sondages n°2, 3, 4** (~4 min chacun : énoncé, vote, débrief).

- N°2 (MFA → application/FIDO2) : le SMS est la MFA la plus fragile (SIM swapping, B09) ; pour des nomades : application d'authentification en standard, clé FIDO2 en idéal. « Un bon mot de passe suffit » n'est plus défendable (B09, B10).
- N°3 (fiches de paie → Confidentielles) : données personnelles + bancaires = accès RH/direction, chiffrement, traçabilité. La classification décide de tout le reste.
- N°4 (3e copie → cloud immuable hors site) : A est le scénario OVHcloud exact ; C confond corbeille et sauvegarde (B11 : supprimer ≠ sauvegarder). B coche tout : hors site, immuable, indépendant.

**3. Les 5 règles d'or collectives (7 min) :** rédiger en direct depuis le **chat** : *« Proposez une règle en une phrase ! »* — attendues : MFA partout ; gestionnaire de mots de passe (fin du stockage navigateur) ; classification + partages restreints ; chiffrement au repos sur tous les postes ; 3-2-1 avec copie immuable testée. Compléter ce que le chat n'a pas trouvé.

**4. Synthèse de l'atelier (3 min) :**
> « Ce plan tient sur une page — et il couvre tout le module : les identités et la MFA, c'est B09. Le chiffrement, c'est B10. Le cloud et ses responsabilités, c'est B11. La classification et les sauvegardes, c'est ce soir. Une page, quatre sessions, et une PME transformée. »

### 1:14–1:18 — Sondage n°5 : et vous, vos sauvegardes ?

**Consigne :** Lancer le **📊 Sondage n°5** (opinion) — vos données personnelles importantes : où en êtes-vous ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « C est fréquent, et personne ne juge : la prise de conscience arrive souvent après la perte. Le kit minimal personnel : un disque externe branché UNIQUEMENT le temps de la sauvegarde, plus une copie cloud chiffrée. Dix ans de photos de famille valent bien deux heures de configuration — c'est votre action personnelle de la semaine. »

### 1:18–1:24 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : il manque le chiffrement au repos ; le DLP bloque et alerte ; les rançongiciels ciblent les sauvegardes connectées. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/B_S12_support.md).

### 1:24–1:27 — Exercice bonus (Sondage n°9) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°9** — l'incendie détruit les bureaux, les deux disques de sauvegarde étaient sur place : résultat ? Débrief : perte définitive (B) — le « 3-2 » était respecté, pas le « 1 » : deux disques dans le même bâtiment partagent le même destin. C'est très exactement le drame d'OVHcloud. À couper en cas de retard.

### 1:27–1:30 — Synthèse & clôture du module C

**🎙️ Verbatim de synthèse :**
> « Module Identités, cloud et données : terminé ! Vous savez prouver une identité, choisir le bon outil cryptographique, tracer la frontière du cloud — et ce soir, suivre une donnée de sa création à sa destruction. Prochaine étape : qui DÉCIDE de tout cela, et selon quelles règles ? Le module Gouvernance commence la semaine prochaine. Un mot que vous retenez, dans le chat ! »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Self-paced : cours IBM SkillsBuild *"Data Security and Privacy"* (~1h30) + mettre en place sa sauvegarde personnelle + rechercher les définitions de PCA et PRA (Plan de Continuité / de Reprise d'Activité) — transition directe vers le module D.
- Teaser B13 : « la semaine prochaine, on monte à l'étage stratégie : la gouvernance — qui décide, qui est responsable, selon quels référentiels ? NIST, ISO 27001, ANSSI... et pourquoi la sécurité sans pilotage finit toujours par échouer. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**Exercice bonus n°9** (1:24–1:27) — il est dans le support en exercice bonus.
2. Compresser le cas Morgan Stanley à 1 min (l'essentiel : disques revendus non effacés, 95 M$).
3. Dans l'atelier, réduire les règles d'or à 3 (les votes n°2-4 sont prioritaires).
4. Ne JAMAIS couper : l'Atelier de Synthèse, le cas OVHcloud, le quiz.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°3 : OVHcloud relu avec la responsabilité partagée de B11).
2. Étendre l'atelier : faire classer par sondage improvisé 2-3 documents supplémentaires de MedDistri (catalogue produits, contrats fournisseurs, code du site web).
3. Questions/réponses libres sur l'ensemble du module C.

## Travail en autonomie (Self-paced)
* **Avant la session suivante (B13)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Data Security and Privacy"* (durée estimée : 1h30).
  * **Action personnelle** : Mettre en place (ou vérifier) sa sauvegarde personnelle : un disque externe hors ligne + une copie cloud chiffrée.
  * **Transition Module D** : Rechercher la définition d'un Plan de Continuité d'Activité (PCA) et d'un Plan de Reprise d'Activité (PRA).
