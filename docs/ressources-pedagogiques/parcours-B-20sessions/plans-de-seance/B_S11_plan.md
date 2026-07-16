# Plan de séance — Session B11 : Sécurité du cloud
Parcours : B 20 sessions  |  Module : C — Identités, cloud & données  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (verbes d'action)
- **Analyser** le modèle de responsabilité partagée et attribuer les devoirs de sécurité (client vs fournisseur) pour les services IaaS, PaaS et SaaS.
- **Identifier** les risques majeurs propres au cloud public : buckets exposés, secrets codés en dur, comptes d'administration sans MFA.
- **Appliquer** les règles de gouvernance des accès cloud (Root isolé, comptes IAM nominatifs, moindre privilège — y compris pour les identités techniques).

## Prérequis & progression
- **Prérequis** : B09 (IAM) et B10 (chiffrement) — les deux briques que le cloud met à l'épreuve.
- **Lien de progression** : Transpose le contrôle d'accès et le chiffrement dans l'écosystème cloud, qui héberge les données d'entreprise dont B12 organisera la protection (classification, sauvegardes, Atelier de Synthèse 2).

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama B11 ([spécifications](../slides/B_S11_slides_spec.md)) — la matrice de responsabilité vide doit pouvoir être remplie à l'écran.
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Part des incidents cloud imputable au client (Gartner) ? | B) La quasi-totalité (~99 %) |
| 2 | 0:46 | Sondage | Qui applique les correctifs de l'OS invité ? | A) Client en IaaS, Fournisseur en PaaS/SaaS |
| 3 | 0:50 | Sondage | Qui répond de la protection des données ? | B) Le client, toujours |
| 4 | 0:54 | Sondage | Qui configure le WAF ? | C) Client en IaaS/PaaS, Fournisseur en SaaS |
| 5 | 1:08 | Sondage | La frontière de responsabilité est-elle claire chez vous ? | Opinion (pas de bonne réponse) |
| 6 | 1:16 | Sondage | Que recouvre la « sécurité DU cloud » ? | A) L'infrastructure physique et l'hyperviseur |
| 7 | 1:18 | Sondage | La bonne pratique du compte Root ? | C) Jamais au quotidien : coffre + MFA matériel |
| 8 | 1:20 | Sondage | Pourquoi les attaquants scannent-ils GitHub ? | B) Pour trouver des secrets codés en dur |
| 9 | Tampon | Sondage | Un bucket de paie en accès public : quelle faille ? | B) Une mauvaise configuration cloud |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil & retour IaaS/PaaS/SaaS | 💬 Chat : les exemples trouvés |
| 0:04–0:10 | Brise-glace : la faute à qui ? | 📊 Sondage n°1 |
| 0:10–0:24 | Séquence 1 : La responsabilité partagée & les 3 modèles | 💬 Chat : la colocation |
| 0:24–0:34 | Séquence 2 : Les mauvaises configurations | Question rhétorique |
| 0:34–0:44 | Séquence 3 : La gouvernance des accès cloud | Question rhétorique |
| 0:44–0:58 | Activité : La matrice de responsabilité | 📊 Sondages n°2, 3, 4 |
| 0:58–1:08 | Chiffres clés & affaires Capital One + Verizon | 💬 Chat : réactions |
| 1:08–1:12 | Et chez vous ? La frontière | 📊 Sondage n°5 |
| 1:12–1:16 | Mini-scénario : la clé d'API sur GitHub | 🤔 Chat : A, B ou C |
| 1:16–1:22 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:22–1:26 | Exercice bonus : le bucket public (tampon) | 📊 Sondage n°9 |
| 1:26–1:30 | Synthèse, devoirs & teaser B12 | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & retour sur le self-paced

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous ! Ce soir, vos données déménagent chez quelqu'un d'autre : le cloud. Votre recherche de la semaine : IaaS, PaaS, SaaS. Tapez dans le chat un exemple de service pour l'une des trois catégories. »

**Points à dérouler :**
- Lire 3-4 exemples du chat, corriger si besoin (EC2 = IaaS, Heroku = PaaS, Microsoft 365 = SaaS).
- Rappel express de B10 : chiffrer / hacher / certifier — « ces outils vont servir : le cloud les met tous à l'épreuve. »
- Annonce du programme : la frontière de responsabilité, les erreurs qui coûtent des millions, la gouvernance des accès — et l'affaire des 106 millions de dossiers.

**Transition scriptée :** « Première question, et son résultat va cadrer toute la soirée. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (la faute à qui ?)

**Consigne :** Lancer le **📊 Sondage n°1** — la part des incidents cloud imputable au client selon Gartner. Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse B : la quasi-totalité — de l'ordre de 99 % selon la prédiction devenue référence de Gartner. Les datacenters d'AWS ou de Microsoft sont des forteresses ; ce qui fuit, ce sont VOS configurations : le bucket laissé public, la clé dans le code, le compte sans MFA. Retenez la formule : le cloud ne vous décharge pas de la sécurité — il en redistribue les rôles. Toute la soirée sert à savoir exactement lesquels. »

**Transition scriptée :** « Pour comprendre cette frontière, emménageons dans une colocation. »

### 0:10–0:24 — Séquence 1 : La responsabilité partagée & les 3 modèles

**Points de contenu à dérouler (support §1) :**
- L'**analogie de la colocation** : le propriétaire répond des murs, du toit, de la tuyauterie ; le locataire ferme sa porte à clé et assure ses meubles. Relance chat : *« Si le locataire laisse sa porte ouverte et se fait cambrioler — la faute à qui ? »*
- La formule canonique : sécurité **DU** cloud (fournisseur : physique, hyperviseur) vs sécurité **DANS** le cloud (client : données, identités, configurations).
- **La gradation IaaS → PaaS → SaaS** avec exemples nommés : en IaaS (EC2), le client patche l'OS (WannaCry, B03, s'applique au cloud aussi !) ; en PaaS (Heroku), il répond de son code ; en SaaS (M365), il lui reste les données, les identités, les partages... et la **sauvegarde** (supprimer ≠ sauvegarder — le fournisseur ne restaure pas vos suppressions au-delà de ses corbeilles).
- **Les deux lignes invariantes** : quelles que soient les couches, les DONNÉES et les IDENTITÉS restent toujours au client.

**Transition scriptée :** « Voyons maintenant à quoi ressemblent concrètement les portes laissées ouvertes. »

### 0:24–0:34 — Séquence 2 : Les mauvaises configurations

**Points de contenu à dérouler (support §2) :**
- **Le bucket public** : une case cochée au mauvais endroit → des milliers de fichiers internes lisibles par tout Internet et indexables. L'exposition est mondiale, instantanée et silencieuse.
- **Les secrets codés en dur** : la clé d'API dans le code publié sur GitHub — des robots scannent en continu, exploitation typique en **minutes** (minage de cryptomonnaie sur votre facture, pivot vers les données). Rappel Uber (B09) : le script aux identifiants en dur.
- **Le Root sans MFA** : le compte racine compromis = l'entreprise entière détruite ou rançonnée en minutes, sauvegardes cloud comprises.
- Question rhétorique : *« Quel point commun entre ces trois risques ? »* — aucun n'est une faille du fournisseur : ce sont des choix (ou des oublis) du client. La prédiction de Gartner, en pratique.

**Transition scriptée :** « La parade tient en trois règles de gouvernance — les voici. »

### 0:34–0:44 — Séquence 3 : La gouvernance des accès cloud

**Points de contenu à dérouler (support §3) :**
- **Le Root au coffre** : jamais au quotidien, MFA matériel, procédure d'urgence documentée — le parallèle exact du compte administrateur local de B08.
- **Des comptes IAM nominatifs** avec MFA obligatoire — l'IAM de B09 transposé à la console cloud.
- **Le moindre privilège... y compris pour les machines** : des rôles spécifiques (facturation, réseau) plutôt qu'un rôle global — et les identités techniques aussi : un composant n'a pas à voir au-delà de son besoin (l'affaire Capital One arrive).
- **La surveillance continue (CSPM)** : les configurations dérivent — les outils de posture détectent le bucket devenu public ou le MFA désactivé avant les scanners des attaquants.
- Question rhétorique : *« Qui, chez vous, serait alerté si un bucket passait en public un dimanche soir ? »* — si la réponse est « personne », c'est le chantier n°1.

**Transition scriptée :** « À vous de tracer la frontière : la matrice de responsabilité, ligne par ligne, par votes. »

### 0:44–0:58 — Activité : La matrice de responsabilité (Sondages n°2 à 4)

**Consigne :** Afficher la matrice vide (support, activité « La matrice de responsabilité ») : 6 tâches × 3 modèles. Lancer les **📊 Sondages n°2, 3, 4** (~4-5 min chacun : énoncé, vote, débrief), puis compléter collectivement les trois lignes restantes.

**🎙️ Verbatim de lancement :**
> « Six tâches de sécurité, trois modèles de cloud — et une seule question à chaque fois : qui est responsable, le client ou le fournisseur ? Première tâche : les correctifs de l'OS de la machine virtuelle. Votez ! »

**Débriefs scriptés (points obligatoires) :**
- N°2 (OS invité) : le critère est « qui a la main sur la couche ? » — en IaaS le client voit l'OS, donc il le patche ; en PaaS/SaaS l'OS est masqué. WannaCry s'applique au cloud aussi.
- N°3 (données) : LA ligne de la session — **la donnée appartient toujours au client** : classification, protection, partage, sauvegarde.
- N°4 (WAF) : en IaaS/PaaS l'application est celle du client, son filtrage aussi ; en SaaS le fournisseur protège son logiciel. « Et un WAF mal configuré côté client... c'est l'histoire qui arrive. »
- **Compléter la matrice** : sécurité physique (Fournisseur ×3), correctifs applicatifs (Client/Client/Fournisseur), identités & MFA (**Client ×3** — la seconde ligne invariante, rappel B09).

**Transition scriptée :** « Cette matrice vaut des centaines de millions. Preuve en deux affaires. »

### 0:58–1:08 — Chiffres clés & deux affaires réelles

**Chiffres (2 min, support §4) :** ~99 % des défaillances cloud imputables au client (Gartner) ; ~106 millions de dossiers Capital One (2019), 80 M$ d'amende + 190 M$ d'accord ; ~14 millions de dossiers Verizon exposés par un bucket public (UpGuard, 2017).

**Cas n°1 — Capital One, 2019 (5 min, support §5) :** dérouler la chaîne, côté client de bout en bout : le WAF **mal configuré** → la technique SSRF (faire émettre au serveur des requêtes internes) → le service de métadonnées qui remet des identifiants temporaires → des droits **excessifs** (le pare-feu pouvait lire des centaines d'espaces de stockage sans rapport avec sa fonction) → ~106 millions de dossiers téléchargés. L'attaquante — une ancienne ingénieure du fournisseur — s'en vante en ligne et se fait arrêter. Leçons : le fournisseur n'a pas été piraté ; le moindre privilège s'applique aux **machines** (rappel : l'Admin_IT de B09 qui ne lit pas les factures) ; la surveillance du stockage aurait vu l'exfiltration.

**Cas n°2 — Verizon, 2017 (3 min, support §5) :** le chercheur d'UpGuard découvre ~14 millions de dossiers clients librement accessibles — un bucket configuré en public par un **prestataire**. Aucun piratage. Les robots scannent en permanence ces espaces : le chercheur est arrivé avant les attaquants, cette fois. Leçons : la fuite cloud archétypale ; la sous-traitance transporte la responsabilité (Target, encore) ; la détection ne doit rien au hasard — CSPM. Relance chat : *« Quel détail vous marque le plus ? »*

### 1:08–1:12 — Sondage n°5 : et chez vous ?

**Consigne :** Lancer le **📊 Sondage n°5** (opinion) — la frontière de responsabilité est-elle claire chez vous ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « B est la réponse la plus répandue — et la plus dangereuse : "c'est le fournisseur qui gère" est vrai pour les murs, faux pour les portes. La question à poser lundi matin : qui, chez nous, vérifie les règles de partage, le MFA et les configurations de stockage ? Si la réponse est "personne", vous venez d'identifier votre premier chantier — et l'Atelier de Synthèse de la semaine prochaine vous y aidera. »

### 1:12–1:16 — 🤔 Mini-scénario : la clé d'API sur GitHub

**Consigne :** Afficher le mini-scénario du support : le développeur a publié un dépôt public contenant la clé d'API du compte cloud. *« Tapez A, B ou C dans le chat. »*

**Débrief :** B — l'ordre est vital : la clé est à considérer comme **déjà volée** (les robots scannent en minutes) → révoquer d'abord, auditer l'activité ensuite (des serveurs de minage tournent peut-être déjà), nettoyer en dernier. A et C partagent la même illusion : l'historique Git n'oublie rien et des copies existent peut-être déjà. Féliciter le développeur d'avoir alerté (culture du signalement, B04) ; prévenir la récidive : gestionnaire de secrets (B10) + scan automatique des dépôts.

**Transition scriptée :** « Trois questions pour fixer la frontière. »

### 1:16–1:22 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : la sécurité DU cloud = physique + hyperviseur (la part du fournisseur) ; le Root = coffre + MFA matériel, jamais au quotidien ; GitHub est scanné pour les secrets codés en dur. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/B_S11_support.md).

### 1:22–1:26 — Exercice bonus (Sondage n°9) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°9** — le bucket de paie en accès public : quelle faille ? Débrief : une mauvaise configuration cloud (B) — ni force brute, ni faille du fournisseur : le cas Verizon en une question, et la prédiction Gartner en pratique. À couper en cas de retard.

### 1:26–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Le cloud vous loue des murs blindés — c'est vous qui fermez les portes. Deux lignes ne bougent jamais : les données et les identités sont TOUJOURS à vous. Configurez au moindre privilège, isolez le Root, ne codez jamais un secret en dur, surveillez vos configurations comme les attaquants les scannent. Un mot que vous retenez, dans le chat ! »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Self-paced : cours IBM SkillsBuild *"Cloud Security Fundamentals"* (~1h30) + préparation de l'Atelier de Synthèse 2 : identifier les types de données sensibles traitées dans une entreprise (RH, R&D, clients, finances) — ils serviront directement en B12.
- Teaser B12 : « la semaine prochaine : vos données elles-mêmes — les classer, les chiffrer, les sauvegarder. Avec l'Atelier de Synthèse 2, et l'histoire d'un datacenter parti en fumée... avec les sauvegardes rangées dans le même bâtiment. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**Exercice bonus n°9** (1:22–1:26) — il est dans le support en exercice bonus.
2. Compresser le cas Verizon à 1 min (l'essentiel : bucket public, prestataire, découvert par un chercheur).
3. Raccourcir le débrief du sondage n°5 à 1 min.
4. Ne JAMAIS couper : l'activité matrice, le cas Capital One, le quiz.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°3 : Capital One reformulé avec le vocabulaire de B09).
2. Étendre la matrice : faire voter par le chat 2-3 tâches supplémentaires (sauvegarde des données SaaS, chiffrement au repos, journalisation).
3. Questions/réponses libres.

## Travail en autonomie (Self-paced)
* **Avant la session suivante (B12)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Cloud Security Fundamentals"* (durée estimée : 1h30).
  * **Préparation de l'Atelier de Synthèse 2** : Identifier les différents types de données sensibles traitées au sein d'une entreprise (RH, R&D, clients, finances) — ils serviront directement à la classification en B12.
