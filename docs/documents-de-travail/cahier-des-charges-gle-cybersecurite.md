# Cahier des charges — Production des parcours GLE Cybersécurité (8 & 20 sessions)
### Document de mission destiné à l'agent IA « Antigravity »

---

## 0. Comment lire et utiliser ce document

- **Statut** : spécification de production. Antigravity doit s'y conformer pour *tous* les livrables.
- **Destinataire** : l'agent IA Antigravity (production des contenus). Bénéficiaire final : le mentor GLE (animation des sessions live).
- **Principe directeur n°1 — Produire par phases, jamais tout d'un coup.** Le volume total (≈ 28 sessions × plusieurs artefacts) dépasse ce qu'une seule réponse peut contenir avec qualité. Antigravity suit la **séquence de production** de la §8.
- **Principe directeur n°2 — Cohérence par gabarits.** Tout artefact respecte les **gabarits** de la §5, sans exception de format.
- **Principe directeur n°3 — Le curriculum est fourni, pas à inventer.** La cartographie des deux parcours (§4) sert de colonne vertébrale. Antigravity peut proposer des ajustements *mineurs*, mais doit les signaler et attendre validation avant de s'en écarter.

> ⚠️ **Points à faire valider par le mentor AVANT la production de masse** (voir §10) :
> 1. Le **budget horaire du parcours 20 sessions** (30h de live = au-delà de la norme GLE standard).
> 2. La **cartographie des deux parcours** (§4).
> 3. Les **gabarits** (§5), notamment le squelette .MD et la spec slides.

---

## 1. Contexte & rôle d'Antigravity

**Contexte programme.** IBM SkillsBuild est une plateforme d'apprentissage numérique gratuite (1000+ cours : IA, cybersécurité, data, cloud, compétences professionnelles), avec badges et certificats. Une **Guided Learning Experience (GLE)** est un format en **cohorte** sur quelques semaines, combinant **auto-apprentissage en ligne**, **sessions live animées par un mentor/expert**, **projet pratique** et **délivrance de credentials** (badges, certificats) pour des compétences « job-ready ».

**Rôle d'Antigravity.** Tu es à la fois **expert en pédagogie pour adultes** et **expert en cybersécurité**. Tu conçois des parcours alignés sur l'esprit SkillsBuild (cohortes, self-paced + live, projets, badges, employabilité). Tes contenus doivent être **techniquement corrects, clairs, sans jargon inutile**, et directement exploitables par le mentor en live avec un minimum de retouches.

**Deux parcours à produire, 100 % cybersécurité :**
- **Parcours A — 8 sessions** de 1h30 → orientation *fondamentaux + projet* (badge type « Cybersecurity Fundamentals »).
- **Parcours B — 20 sessions** de 1h30 → orientation *fondamentaux + approfondissements + pratique + projet(s)* (credential type « Cybersecurity Certificate »).

---

## 2. Paramètres globaux (à appliquer à TOUS les livrables)

| Paramètre | Valeur imposée |
|---|---|
| **Langue des livrables** | **Français.** Les termes techniques standard restent en anglais (*firewall, SOC, SIEM, phishing, hardening, kill chain*…) et sont **glosés en français à la 1ère occurrence** de chaque session. |
| **Public cible** | Adultes / étudiants, bases numériques solides, **niveau débutant → intermédiaire** en cybersécurité. Pas de prérequis en programmation. |
| **Ton** | Professionnel, accessible, encourageant. Vouvoiement. Concret, exemples du quotidien et du monde de l'entreprise. |
| **Niveau technique** | Conceptuel et opérationnel « grand public éclairé ». **Pas** de contenu offensif réellement exploitable (pas de payloads, d'exploits fonctionnels, ni de pas-à-pas d'attaque réelle). L'ethical hacking est traité au niveau **concepts, posture et cadre légal**. |
| **Credentials visés** | Parcours A → « Cybersecurity Fundamentals ». Parcours B → « Cybersecurity Certificate ». Aligner les objectifs pédagogiques sur ces cibles. |
| **Format pédagogique** | GLE : articulation explicite **self-paced (modules en ligne, labs, quiz) ↔ live (séance synchrone de 1h30)**. Chaque session précise ce qui est fait *avant*, *pendant*, *après*. |
| **Styles d'apprentissage** | Alterner : exposé, démonstration, étude de cas, discussion, mini-projet/travail de groupe, quiz live, Q&A, récapitulatif. Aucune session ne doit être un monologue. |
| **Accessibilité** | Langage clair, phrases courtes, définitions à l'appui. Pour chaque visuel suggéré, prévoir une **description textuelle (alt-text)** exploitable. |
| **Propriété intellectuelle** | **Ne jamais reproduire** de texte protégé (extraits de normes ISO/NIST/CIS, articles, cours tiers, paroles, etc.). Toujours **reformuler** et **expliquer avec ses propres mots**. Les références aux normes se font par paraphrase + renvoi (« voir la norme X »). Contenu **original**. |
| **Self-paced SkillsBuild** | Rester **générique** : décrire le *type* de module et le *thème* (ex. « module d'introduction aux menaces », « lab de configuration de pare-feu »), pour que le mentor les mappe aux cours SkillsBuild réels. Ne pas inventer de titres exacts de cours SkillsBuild. |

### 2.1 Budgets horaires (cohérence GLE)

Repère SkillsBuild : ~**10–60h self-paced + 10–15h live sur 4 à 10 semaines**.

- **Parcours A (8 sessions)** : 8 × 1h30 = **12h de live** ✅ (dans la norme). Self-paced cible : **~1h30 à 3h par session**, soit **~12–24h** au total. Rythme suggéré : 1 session/semaine sur ~8 semaines.
- **Parcours B (20 sessions)** : 20 × 1h30 = **30h de live** ⚠️ **au-dessus de la norme GLE standard**. À traiter comme **cohorte étendue/intensive**. Options à proposer au mentor :
  - **Option 1** : 2 sessions/semaine sur ~10 semaines (intensif).
  - **Option 2** : 1 session/semaine sur ~20 semaines (étalé).
  - Self-paced cible : **~1h30 à 2h30 par session**, soit **~30–50h** au total.
  - Tant que le mentor n'a pas tranché, **planifier au conditionnel** et ne pas verrouiller le calendrier.

---

## 3. Conventions de nommage & organisation des fichiers

**Arborescence cible** (Antigravity la rappelle dans son manifeste, voir §8) :

```
/parcours-A-8sessions/
   /plans-de-seance/      A_S01_plan.md … A_S08_plan.md
   /supports-md/          A_S01_support.md … A_S08_support.md
   /slides/               A_S01_slides.pptx (+ A_S01_slides_spec.md)
   /projet/               A_capstone.md, A_grille_notation.md
   /outils/               A_banque_quiz.md, A_scripts_demo.md, A_messages.md
/parcours-B-20sessions/
   /plans-de-seance/      B_S01_plan.md … B_S20_plan.md
   /supports-md/          B_S01_support.md … B_S20_support.md
   /slides/               B_S01_slides.pptx (+ B_S01_slides_spec.md)
   /projet/               B_capstone.md, B_miniprojets.md, B_grille_notation.md
   /outils/               B_banque_quiz.md, B_scripts_demo.md, B_messages.md
/00_MANIFESTE.md          (index global + état d'avancement + glossaire commun)
```

**Règles de nommage des fichiers** : `<Parcours>_S<NN>_<type>.<ext>` (numéros sur 2 chiffres). Ex. : `B_S07_support.md`, `A_S03_slides.pptx`.

**Titre interne de chaque fichier** : toujours commencer par un H1 explicite, ex. `# Parcours B — Session 07 : Communications sécurisées`.

**Manifeste (`00_MANIFESTE.md`)** : table des matières des deux parcours + **tableau d'avancement** (artefact / statut : à faire / produit / validé) + **glossaire commun** des termes techniques (mis à jour au fil de l'eau pour garantir des définitions cohérentes d'une session à l'autre).

---

## 4. Architecture des deux parcours (cartographie à valider)

> Antigravity produit cette cartographie en **Phase 0** et la fait valider. Les objectifs sont rédigés avec des **verbes d'action** (taxonomie de Bloom : *identifier, expliquer, configurer, analyser, évaluer, concevoir*).

### 4.1 Parcours A — 8 sessions (Fondamentaux + Capstone)

| # | Titre | Objectifs clés | Macro-thèmes | Prérequis | Lien de progression |
|---|---|---|---|---|---|
| A1 | Découverte de la cybersécurité & paysage des menaces | Définir la triade CIA ; situer offense vs défense ; nommer les acteurs et scénarios d'attaque | Fondamentaux | Aucun | Pose le vocabulaire pour tout le parcours |
| A2 | Menaces, attaques & ingénierie sociale | Distinguer familles de malware ; reconnaître le phishing ; décrire la *kill chain* (intro) | Menaces | A1 | Donne le « pourquoi » des défenses (A3–A4) |
| A3 | Sécurité des systèmes & réseaux | Expliquer architecture, pare-feu, segmentation, VPN, protocoles sécurisés | Réseaux/systèmes | A1–A2 | 1er pilier défensif (technique) |
| A4 | Sécurité du cloud, des données & des identités | Appliquer chiffrement, sauvegarde, IAM, MFA ; expliquer la responsabilité partagée | Cloud/Données/Identité | A3 | 2e pilier défensif (données/accès) |
| A5 | Gouvernance, risque, conformité & vie privée | Décrire politiques et cadres (ISO 27001 / NIST CSF, intro) ; notions RGPD ; évaluer un risque simple | GRC / Data privacy | A1–A4 | Cadre organisationnel englobant |
| A6 | Opérations de sécurité & gestion des vulnérabilités | Décrire SOC/SIEM/monitoring ; comprendre scan & priorisation (CVSS, intro) | SecOps / Vulnérabilités | A3–A5 | Passe au « run » et à la détection |
| A7 | Réponse aux incidents & introduction au forensics | Dérouler le cycle de réponse à incident ; exploiter journaux/traces ; aperçu ethical hacking | IR / Forensics / Pentest (intro) | A6 | Boucle « détecter → réagir → analyser » |
| A8 | Projet capstone — restitution & synthèse | Réaliser et présenter une évaluation de sécurité / investigation pour une PME | Intégration | A1–A7 | Consolide et évalue tout le parcours |

### 4.2 Parcours B — 20 sessions (Fondamentaux + approfondissements + pratique + projets)

Organisé en **6 modules**. Mini-projets jalonnés ; capstone sur les modules E–F.

**Module A — Fondations (S1–S4)**
- **B1** Introduction à la cybersécurité & triade CIA — vocabulaire, enjeux, métiers.
- **B2** Paysage des menaces & acteurs — États, cybercriminalité, *insiders*, hacktivistes ; motivations.
- **B3** Types d'attaques & vecteurs — malware, phishing, attaques web, DoS ; intro **MITRE ATT&CK** / *kill chain*.
- **B4** Ingénierie sociale & facteur humain — manipulation, sensibilisation, culture de sécurité.

**Module B — Systèmes & réseaux (S5–S8)**
- **B5** Fondamentaux réseau pour la sécurité — modèle OSI/TCP-IP, ports, protocoles.
- **B6** Défenses réseau — pare-feu, IDS/IPS, segmentation, DMZ.
- **B7** Communications sécurisées — VPN, TLS, Wi-Fi, protocoles sécurisés.
- **B8** Durcissement des systèmes & endpoints — *hardening* OS, *patching*, EDR. → **Mini-projet 1** : concevoir une **architecture réseau sécurisée**.

**Module C — Identités, cloud & données (S9–S12)**
- **B9** Gestion des identités et des accès (IAM) — authentification, autorisation, MFA, SSO, moindre privilège.
- **B10** Cryptographie essentielle — symétrique/asymétrique, hachage, PKI, certificats.
- **B11** Sécurité du cloud — responsabilité partagée, stockage, configuration, IAM cloud.
- **B12** Sécurité & confidentialité des données — classification, DLP, chiffrement *at rest/in transit*, sauvegarde. → **Mini-projet 2** : **plan de protection des données**.

**Module D — Gouvernance, risque & conformité (S13–S15)**
- **B13** Gouvernance & cadres de sécurité — ISO 27001, NIST CSF, CIS Controls (présentés, paraphrasés).
- **B14** Gestion des risques — évaluation, traitement, registre des risques.
- **B15** Conformité & réglementations vie privée — RGPD, réglementations sectorielles. → **Mini-projet 3** : **évaluation des risques + ébauche de politique de sécurité**.

**Module E — Opérations, détection & réponse (S16–S19)**
- **B16** Centre des opérations de sécurité (SOC) & supervision.
- **B17** SIEM, journalisation & détection — analyse de logs, alertes, corrélation. → **Mini-projet 4** : **analyser des logs d'un SIEM fictif**.
- **B18** Gestion des vulnérabilités — scan, priorisation (CVSS), remédiation.
- **B19** Réponse aux incidents & bases du forensics — cycle IR, preuves, rapport ; **introduction au pentest/ethical hacking** (concepts + cadre légal).

**Module F — Capstone (S20)**
- **B20** Projet capstone — restitution & clôture (préparé sur les modules E–F).

### 4.3 Stratégie de factorisation (8 ⊂ 20)

Le parcours A est, pour l'essentiel, une **version condensée** du parcours B. Antigravity produit d'abord les **blocs de concepts** (définitions, schémas, analogies, exemples) puis **ajuste la profondeur** selon le parcours, au lieu de réécrire deux fois. Correspondance indicative :

| Session A | ≈ Condensé de sessions B |
|---|---|
| A1 | B1 + B2 |
| A2 | B3 + B4 |
| A3 | B5 + B6 + B7 (+ aperçu B8) |
| A4 | B9 + B11 + B12 (+ B10 allégé) |
| A5 | B13 + B14 + B15 |
| A6 | B16 + B17 + B18 |
| A7 | B19 |
| A8 (capstone) | Version allégée du capstone B20 |

**Règle** : le **glossaire commun** (manifeste) et la **banque de quiz** sont mutualisés ; les items sont **tagués par thème** et réutilisés dans les deux parcours avec un niveau de difficulté adapté.

---

## 5. Gabarits réutilisables (OBLIGATOIRES)

> Tout artefact respecte le gabarit correspondant. Antigravity ne change pas la structure d'une session à l'autre ; seul le contenu varie.

### 5.1 Gabarit « Plan de séance » (un par session)

```
# Parcours <A/B> — Session <NN> : <Titre>
Module : <le cas échéant>  |  Durée : 90 min  |  Parcours : <A 8 sessions / B 20 sessions>

## Objectifs pédagogiques (3 à 5, verbes d'action)
- ...

## Prérequis
- Sessions précédentes : ...
- Self-paced AVANT la séance (~X min) : <type de module / thème SkillsBuild>, <lab>, <quiz>

## Découpage temporel (90 min)  — adapter selon le contenu
| Min | Segment | Format | Support |
|-----|---------|--------|---------|
| 0–5   | Accueil & rappel des objectifs | plénière | slide titre |
| 5–15  | Brise-glace / rappel session précédente | interactif | sondage |
| 15–40 | Apport de contenu 1 | exposé + démo | slides |
| 40–55 | Activité / étude de cas | groupe | fiche d'activité |
| 55–75 | Apport de contenu 2 + démonstration | exposé + démo | slides + script démo |
| 75–85 | Quiz live / Q&A | interactif | banque de quiz |
| 85–90 | Récapitulatif & devoirs | plénière | slide récap |

> Schéma par défaut, à ajuster. Éviter le brise-glace systématique de 10 min sur toutes les sessions : varier (rappel éclair, étude de cas d'ouverture, mini-sondage).

## Activités détaillées
- **Activité 1 — <titre>** : objectif, consignes pas-à-pas, livrable attendu, durée, modalité (solo/binôme/groupe), critères de réussite.
- **Démonstration — <titre>** : renvoi au script de démo (voir outils).

## Questions d'interaction (pour stimuler la réflexion)
- ... (questions ouvertes, mises en situation, « que feriez-vous si… »)

## Articulation avec le(s) projet(s)
- Lien avec le capstone / mini-projet : quelle brique cette session apporte-t-elle ?

## Self-paced APRÈS la séance (~X min) & évaluation formative
- <module/thème>, <quiz d'auto-évaluation>, <lecture>

## Checklist matériel mentor
- [ ] Slides  [ ] Fiche(s) d'activité  [ ] Script(s) démo  [ ] Quiz live  [ ] Support .MD
```

### 5.2 Gabarit Support de cours `.MD` (un par session)

```
# Session <NN> — <Titre>

## Objectifs de la session
- ... (repris du plan de séance, formulés côté apprenant)

## Concepts clés
### <Concept 1>
Explication simple + analogie + exemple concret. Termes EN glosés à la 1ère occurrence.
### <Concept 2>
...
> 💡 *Encadré « bon à savoir »* : nuance, idée reçue à corriger, bonne pratique.

## Activités / exercices
### Exercice 1 — <titre>
**Objectif :** ...  **Consignes :** étape par étape.  **Livrable :** ...  **Corrigé / éléments de réponse :** ...

## Questions de réflexion
1. ...
2. ...

## Résumé / points à retenir
- 4 à 7 points essentiels.

## Glossaire de la session
- **Terme (EN)** — définition courte en français.

## Pour aller plus loin (self-paced)
- <type de module / thème SkillsBuild>, <lab>, <ressource générique>
```

Exigences : structuré pour être **animé tel quel** (le mentor n'a pas à réécrire) ; les corrigés sont fournis ; longueur indicative **800–1500 mots** par support (selon densité).

### 5.3 Gabarit Spec de présentation `.PPTX` (un par session)

Antigravity peut **générer directement le `.pptx`** (capacité confirmée). Il produit **en plus** un fichier `_slides_spec.md` lisible par un humain, suivant ce schéma — afin que la structure soit transformable/contrôlable.

**Métadonnées du deck** : objectif, public, **nombre de slides cible 12–16** (une séance de 90 min est surtout faite d'activité/discussion, pas de slides), thème graphique sobre (police lisible, contraste élevé, 1 idée par slide).

```
### Slide <n> — <Titre de la slide>
- **Type** : titre / contenu / étude de cas / schéma / quiz / récap
- **Points clés (bullets)** : 3 à 5 puces courtes
- **Notes orateur** : ce que le mentor dit (2–4 phrases) — script d'animation
- **Visuel suggéré** : description précise (ex. « schéma réseau : Internet → pare-feu → DMZ → LAN segmenté ») + **alt-text**
- **Élément interactif** (si pertinent) : question, sondage, mini-quiz, sondage à main levée
```

Structure de deck recommandée : (1) Titre & objectifs — (2) Rappel/accroche — (3–8) Contenu par concept, avec au moins **1 schéma** et **1 étude de cas** — (9–11) Activité + restitution — (12–14) Démo + points clés — (15) Quiz live — (16) Récap & devoirs.

### 5.4 Gabarit Question de quiz (banque mutualisée)

```
- ID : <THEME-NNN>
  Thème : <fondamentaux / réseaux / cloud-données / GRC / secops / vulnérabilités / IR-forensics / pentest>
  Parcours : A / B / A+B
  Difficulté : facile / moyen / difficile
  Type : QCM / Vrai-Faux / Question ouverte
  Question : ...
  Options (QCM) : a) ... b) ... c) ... d) ...
  Réponse correcte : ...
  Feedback / explication : pourquoi c'est juste, pourquoi les autres sont faux.
```

Couverture cible : **≥ 8–10 items par thème**, répartis sur les 3 niveaux de difficulté.

### 5.5 Gabarit Script de démonstration (rejouable par le mentor)

```
## Démo — <Titre>
- **Objectif pédagogique** : ...
- **Durée** : ~X min   **Session(s) liée(s)** : <A/B S..>
- **Pré-requis / mise en place** : (environnement fictif, fichiers d'exemple fournis dans le script — pas d'outil offensif réel)
- **Déroulé pas-à-pas** : étape 1 (ce que je montre / ce que je dis) → étape 2 → ...
- **Résultat attendu** : ce que les apprenants doivent observer/comprendre.
- **Points de discussion** : 2–3 questions à poser pendant la démo.
- **Pièges fréquents / erreurs à éviter** : ...
```

Démos minimales attendues : **analyse d'un log simple** (extraire l'essentiel d'un journal fictif) ; **lecture d'un schéma réseau** ; **walkthrough d'un scénario attaque/défense** (narratif, non opérationnel).

### 5.6 Gabarits Messages aux apprenants

Produire des modèles prêts à personnaliser : **(1) Message de bienvenue** (cadre, objectifs, calendrier, credential) ; **(2) Règles & charte de cohorte** (assiduité, participation, entraide, code de conduite, **usage éthique/légal** des connaissances) ; **(3) Rappel avant séance** (self-paced à faire, matériel) ; **(4) Consigne de projet** (capstone / mini-projet : contexte, livrables, échéance) ; **(5) Récapitulatif après séance** (points clés, devoirs) ; **(6) Message de fin / obtention du badge**.

---

## 6. Projets & évaluation

### 6.1 Capstone — Parcours A (8 sessions)

Scénario réaliste **PME** (ex. *« TechBoutique », e-commerce de 25 personnes*). Au choix ou combiné : **(a)** mini-évaluation de sécurité + recommandations, ou **(b)** investigation d'un incident simple (à partir d'éléments fournis).

Décrire dans `A_capstone.md` : **contexte** ; **livrables attendus** (ex. rapport de 3–5 pages + présentation de 8–10 slides) ; **étapes de réalisation** réparties sur les sessions A6–A8 ; **critères d'évaluation** ; **grille de notation simple** (voir §6.4).

### 6.2 Capstone — Parcours B (20 sessions)

Scénario PME/ETI plus riche, **intégrateur** des 6 modules. Ex. : *« À partir d'un dossier d'entreprise fictive, réaliser une évaluation de sécurité de bout en bout : cartographie des risques, faiblesses réseau/cloud/identité, analyse de logs d'un incident, plan de réponse à incident, et feuille de route de remédiation priorisée. »*

Livrables : **dossier complet** (rapport structuré + annexes : registre des risques, schéma d'architecture cible, extrait d'analyse de logs, plan IR) + **soutenance** (12–15 slides). Étapes réparties des modules D→F. Travail individuel ou en équipe (à préciser).

### 6.3 Mini-projets intermédiaires — Parcours B uniquement

Détaillés dans `B_miniprojets.md`, chacun avec contexte / livrable / étapes / critères :
- **MP1 (après S8)** — concevoir une **architecture réseau sécurisée** (schéma + justification segmentation/pare-feu/VPN).
- **MP2 (après S12)** — rédiger un **plan de protection des données** (classification, chiffrement, sauvegarde, accès).
- **MP3 (après S15)** — réaliser une **évaluation des risques** + **ébauche de politique de sécurité**.
- **MP4 (après S17)** — **analyser des logs d'un SIEM fictif** (identifier l'activité suspecte, formuler des hypothèses, proposer une réaction).

### 6.4 Grilles de notation (simples, réutilisables)

Grille par critères, échelle 1–4 (insuffisant / en développement / satisfaisant / excellent). Critères types : **exactitude technique**, **pertinence des recommandations**, **clarté du livrable**, **priorisation/justification**, **qualité de la présentation**. Fournir une **version capstone** (pondérée) et une **version mini-projet** (allégée) dans `*_grille_notation.md`. Inclure des **descripteurs courts** par niveau pour faciliter la notation par le mentor.

---

## 7. Outils complémentaires à produire

- **Banque de quiz** (`*_banque_quiz.md`) — par thème, format §5.4, pour l'évaluation formative en live. Mutualisée A/B, items tagués.
- **Scripts de démonstration** (`*_scripts_demo.md`) — format §5.5 ; au minimum les 3 démos citées (log, schéma réseau, scénario attaque/défense), plus toute démo utile par session.
- **Messages modèles** (`*_messages.md`) — les 6 modèles de la §5.6.

---

## 8. Séquence de production (phasage) & protocole d'interaction

> **Règle d'or** : ne pas tenter de tout produire en une réponse. Avancer **phase par phase**, par **lots (batches)**, en demandant la validation du mentor entre les grandes phases.

### 8.1 Séquence recommandée

| Phase | Livrable | Granularité (lot) | Validation avant suite |
|---|---|---|---|
| **0** | Manifeste + cartographie des 2 parcours (§4) + confirmation des paramètres (§2, dont budget horaire B) + gabarits retenus (§5) | 1 réponse | **OUI** (point de contrôle clé) |
| **1** | Parcours A — plans de séance | 2 lots de 4 sessions (A1–A4, puis A5–A8) | Après le 1er lot |
| **2** | Parcours A — supports `.MD` | 2 lots de 4 | — |
| **3** | Parcours A — specs slides + `.pptx` | 2 lots de 4 | — |
| **4** | Parcours A — capstone + grille + banque quiz (thèmes A) + scripts démo + messages | 1–2 réponses | **OUI** (clôture Parcours A) |
| **5** | Parcours B — plans de séance | lots de 4–5 (par module) | Après le 1er lot |
| **6** | Parcours B — supports `.MD` | lots de 4–5 | — |
| **7** | Parcours B — specs slides + `.pptx` | lots de 4–5 | — |
| **8** | Parcours B — mini-projets + capstone + grilles + banque quiz (compléments) + scripts démo + messages | 2–3 réponses | — |
| **9** | Consolidation : mise à jour du manifeste, index global, **passe QA** (§9) sur l'ensemble | 1 réponse | **OUI** (livraison finale) |

### 8.2 Protocole d'interaction

1. **Toujours commencer par la Phase 0.** Ne rien produire en masse avant validation de la cartographie et des paramètres.
2. **Tenir le manifeste à jour** après chaque lot (statut des artefacts + glossaire commun).
3. **Annoncer le plan du lot** en tête de réponse (« Ce lot produit A1–A4 : plans de séance »), puis livrer.
4. **Demander explicitement la validation** entre les grandes phases : « Validez-vous ce lot ? Je poursuis avec le suivant ? ».
5. **Cohérence** : réutiliser le glossaire et les blocs de concepts (factorisation §4.3) ; ne pas redéfinir un terme différemment d'une session à l'autre.
6. **Gestion de la longueur** : si un lot risque d'être tronqué, le **scinder** et le signaler, plutôt que de bâcler ou couper en plein milieu.
7. **Auto-contrôle** : appliquer la checklist §9 à chaque artefact avant de le livrer.
8. **Signaler tout écart** proposé par rapport à la cartographie validée, et attendre l'accord.

---

## 9. Barre de qualité & checklist d'auto-contrôle

**Definition of Done — un artefact est « terminé » si :**

- ✅ **Exactitude technique** : aucune affirmation fausse ou obsolète en cybersécurité ; nuances présentes là où c'est nécessaire.
- ✅ **Alignement pédagogique** : objectifs ↔ activités ↔ évaluation cohérents ; verbes d'action ; niveau débutant→intermédiaire respecté.
- ✅ **Conformité au gabarit** (§5) : structure et sections exactes ; nommage de fichier correct (§3) ; H1 conforme.
- ✅ **Budget temps réaliste** : la séance tient en 90 min ; self-paced dans les bornes (§2.1).
- ✅ **Langue** : français ; termes EN glosés à la 1ère occurrence ; glossaire de session présent (pour les `.MD`).
- ✅ **Propriété intellectuelle** : aucun texte protégé reproduit ; contenu reformulé/original ; normes paraphrasées.
- ✅ **Sécurité du contenu** : pas de matériel offensif réellement exploitable ; ethical hacking au niveau concepts + cadre légal.
- ✅ **Accessibilité** : langage clair ; **alt-text** fourni pour chaque visuel suggéré.
- ✅ **Exploitable tel quel** : le mentor peut animer/utiliser sans réécriture significative (corrigés, notes orateur, consignes complètes).
- ✅ **Cohérence inter-sessions** : terminologie et définitions alignées avec le manifeste.

**Mini-checklist par type d'artefact :**
- *Plan de séance* : découpage 90 min bouclé ? activités avec livrable + critères ? questions d'interaction ? lien projet ? self-paced avant/après ?
- *Support .MD* : 6 sections du gabarit ? corrigés des exercices ? glossaire ? longueur 800–1500 mots ?
- *Slides* : 12–16 slides ? ≥ 1 schéma + 1 étude de cas + 1 quiz ? notes orateur sur chaque slide ? alt-text ?
- *Quiz* : ≥ 8–10 items/thème ? 3 niveaux ? feedback explicatif ?
- *Projets* : contexte + livrables + étapes + grille ? réaliste pour le niveau ?

---

## 10. Premier livrable attendu d'Antigravity (Phase 0)

En **première réponse**, Antigravity produit **uniquement** :

1. Le **manifeste** (`00_MANIFESTE.md`) : index des 2 parcours + tableau d'avancement (vide) + amorce du **glossaire commun**.
2. La **cartographie détaillée** des 2 parcours (§4), avec pour chaque session : titre, objectifs (verbes d'action), prérequis, lien de progression.
3. La **proposition de calendrier** pour le parcours B (Option 1 vs Option 2, §2.1) et la **confirmation des paramètres globaux** (§2).
4. Une **note de factorisation** (§4.3) et la **liste des gabarits** qui seront utilisés (§5).
5. Une **question de validation** claire au mentor : « Validez-vous cette architecture et ces paramètres ? Sur quel parcours commençons-nous la production détaillée (Phase 1 ou Phase 5) ? ».

> Antigravity **ne commence pas** la production des plans de séance, supports, slides ou projets tant que la Phase 0 n'est pas validée par le mentor.

---

*Fin du cahier des charges.*
