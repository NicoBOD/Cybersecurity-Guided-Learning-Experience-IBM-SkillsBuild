# Plan de séance — Session B03 : Types d'attaques & vecteurs
Parcours : B 20 sessions  |  Module : A — Fondations  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (verbes d'action)
- **Classifier** les principales familles de logiciels malveillants (virus, vers, chevaux de Troie, rançongiciels, spywares) selon leur propagation et leur objectif.
- **Modéliser** le déroulement d'une cyberattaque à l'aide des 7 étapes de la *Cyber Kill Chain* et situer le rôle de MITRE ATT&CK.
- **Expliquer** le principe des attaques par déni de service (DoS/DDoS) et des injections applicatives (SQL).

## Prérequis & progression
- **Prérequis** : B01 (triade CIA) et B02 (typologie des attaquants, TTP).
- **Lien de progression** : Après QUI attaque (B02), cette session détaille COMMENT — l'arsenal et la mécanique des attaques. Elle prépare le facteur humain et l'ingénierie sociale (B04) et justifie les protections réseau du module B.

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama B03 ([spécifications](../slides/B_S03_slides_spec.md)) ; prévoir un onglet ouvert sur attack.mitre.org (fiche T1566) si démonstration en direct.
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | WannaCry : 200 000 machines, 150 pays... en combien de temps ? | A) Un seul week-end |
| 2 | 0:42 | Sondage | Événement B (recherches LinkedIn) : quelle étape ? | A) Reconnaissance |
| 3 | 0:46 | Sondage | Événement D (connexion sortante régulière) : quelle étape ? | B) Commandement & Contrôle |
| 4 | 0:50 | Sondage | Événement C (exécution à chaque démarrage) : quelle étape ? | C) Installation |
| 5 | 1:04 | Sondage | Les mises à jour chez vous : quel rythme ? | Opinion (pas de bonne réponse) |
| 6 | 1:17 | Sondage | Différence fondamentale ver / virus ? | A) Le ver se propage seul |
| 7 | 1:19 | Sondage | Que suffit-il pour faire échouer une attaque (Kill Chain) ? | B) Briser un seul maillon |
| 8 | 1:21 | Sondage | Une injection SQL exploite avant tout... | B) Un site web mal programmé |
| 9 | Tampon | Sondage | Macro Word « Activer le contenu » : que se passe-t-il ? | B) Le code malveillant s'exécute |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil & retour veille CERT-FR | 💬 Chat : alertes trouvées |
| 0:04–0:10 | Brise-glace : la vitesse d'un ver | 📊 Sondage n°1 |
| 0:10–0:24 | Séquence 1 : Typologie des malwares | 💬 Chat : « déjà croisé ? » |
| 0:24–0:34 | Séquence 2 : La Cyber Kill Chain | Question rhétorique |
| 0:34–0:40 | MITRE ATT&CK (& lien TTP de B02) | Démo écran (option) |
| 0:40–0:54 | Activité : Reconstruction d'incident PlastiqueNord | 📊 Sondages n°2, 3, 4 |
| 0:54–1:04 | Deux affaires réelles : WannaCry & NotPetya | 💬 Chat : réactions |
| 1:04–1:08 | Et chez vous ? Le rythme des mises à jour | 📊 Sondage n°5 |
| 1:08–1:12 | Mini-scénario : le correctif « wormable » | 🤔 Chat : A, B ou C |
| 1:12–1:17 | Séquence 3 : DDoS & injections SQL | Question rhétorique |
| 1:17–1:23 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:23–1:26 | Exercice bonus : la macro piégée (tampon) | 📊 Sondage n°9 |
| 1:26–1:30 | Synthèse, devoirs & teaser B04 | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & retour sur la veille

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous ! Troisième session — et d'abord, votre mission de la semaine : qui s'est abonné aux alertes du CERT-FR ? Tapez dans le chat le produit ou le logiciel concerné par une alerte que vous avez repérée. »

**Points à dérouler :**
- Lire 3-4 alertes citées dans le chat ; féliciter, souligner la variété (« en une semaine de veille, vous avez déjà vu passer des failles sur des produits que vous utilisez »).
- Rappel express de B02 : les quatre familles d'attaquants, l'économie RaaS, la CTI.
- Annonce du programme : après QUI attaque, place à COMMENT — l'arsenal (malwares), la méthode (Kill Chain), et deux catastrophes mondiales décortiquées.

**Transition scriptée :** « On commence par une question de vitesse. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (la vitesse d'un ver)

**Consigne :** Lancer le **📊 Sondage n°1** — WannaCry, 200 000 machines dans 150 pays : en combien de temps ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse A : un seul week-end — et pour l'essentiel, quelques heures du vendredi 12 mai 2017, selon Europol. Réfléchissez : aucune campagne d'e-mails piégés ne touche 150 pays en une journée, aucun humain ne clique aussi vite. Quand une attaque va à cette vitesse, c'est qu'aucun humain n'est dans la boucle : c'est un VER, un malware qui se propage tout seul. Cette session vous donne la grille pour classer tout ce bestiaire — et en fin de session, l'histoire complète de WannaCry, avec son héros à 10 dollars. »

**Transition scriptée :** « Commençons par mettre de l'ordre dans le zoo des malwares. »

### 0:10–0:24 — Séquence 1 : Typologie des malwares

**Points de contenu à dérouler (support §1) :**
- Le mot juste : *malware* (logiciel malveillant) — « virus » n'est qu'UNE famille parmi d'autres.
- Les deux questions de classement : *comment se propage-t-il ?* et *que fait-il une fois en place ?*
- **Virus** : s'accroche à un fichier hôte, a besoin d'une action humaine (analogie : le virus biologique).
- **Ver** : autonome, exploite les failles réseau (analogie : la bactérie qui circule seule dans les canalisations).
- **Cheval de Troie** : le cadeau piégé du mythe grec — la victime l'installe elle-même ; ouvre une porte dérobée.
- **Rançongiciel** : chiffre et rançonne — la charge utile favorite de l'économie RaaS vue en B02.
- **Spyware / keylogger** : la discrétion absolue — observer, enregistrer les frappes, voler les identifiants.
- Point clé : les familles se **combinent** (annonce : WannaCry = ver + ransomware).
- Relance chat (0:20) : *« Qui a déjà croisé l'un de ces malwares, au travail ou à la maison ? Tapez la famille dans le chat. »* — lire 3-4 réponses.

**Transition scriptée :** « Vous savez maintenant QUOI craindre. Voyons COMMENT une attaque se déroule, étape par étape — et pourquoi c'est une excellente nouvelle pour les défenseurs. »

### 0:24–0:34 — Séquence 2 : La Cyber Kill Chain

**Points de contenu à dérouler (support §2) :**
- L'idée fondatrice (Lockheed Martin) : une attaque ciblée est une **chaîne de 7 étapes obligatoires**.
- Dérouler les 7 étapes avec l'exemple fil rouge d'un e-mail piégé : Reconnaissance (LinkedIn) → Armement (le document piégé) → Livraison (l'envoi) → Exploitation (le clic qui déclenche la faille) → Installation (la persistance) → C2 (la machine « téléphone » à l'attaquant) → Actions sur objectifs (chiffrement, vol).
- Question rhétorique : *« Pour gagner, le défenseur doit-il bloquer les 7 étapes ? »* — non : **une seule**. Filtrer l'e-mail, corriger la faille, détecter la connexion sortante : chaque couche pallie la défaillance d'une autre — c'est la défense en profondeur.
- À chaque étape sa parade (donner le tableau oralement : sensibilisation/filtrage → Livraison ; correctifs → Exploitation ; surveillance du trafic sortant → C2 ; sauvegardes → Actions).

**Transition scriptée :** « La Kill Chain est la vue d'ensemble. Pour le détail technique, les professionnels utilisent une encyclopédie mondiale. »

### 0:34–0:40 — MITRE ATT&CK

**Points de contenu à dérouler (support §2) :**
- ATT&CK : la matrice des comportements réellement observés — **tactiques** (le but : accès initial, persistance...) × **techniques** (le moyen : phishing, injection...).
- Le lien avec B02 : c'est ici que sont documentées les **TTP** des groupes — la fiche « Lazarus Group » liste ses techniques, attaque par attaque.
- Différence avec la Kill Chain : pas d'ordre imposé, exhaustivité de terrain.
- **Option démonstration (2 min)** : partager l'écran sur attack.mitre.org, ouvrir la technique « Phishing » (T1566) — montrer la description, les groupes qui l'utilisent, les parades. C'est le devoir de la semaine passée qui prend vie.

**Transition scriptée :** « Assez de théorie : une usine vient de se faire pirater, et c'est vous qui menez l'enquête. »

### 0:40–0:54 — Activité : Reconstruction d'incident (Sondages n°2 à 4)

**Consigne :** Afficher le récit de l'incident **PlastiqueNord** (support, activité « Reconstruction d'incident ») : 7 événements dans le désordre, lus à voix haute. Puis lancer les **📊 Sondages n°2, 3, 4** l'un après l'autre (~4 min chacun : rappel de l'événement, vote, débrief).

**🎙️ Verbatim de lancement :**
> « Voici le rapport d'incident de l'usine PlastiqueNord — sept événements, livrés dans le désordre par les journaux systèmes. Votre mission d'analyste : replacer chacun dans la Kill Chain. On commence par l'événement B : l'attaquant liste les e-mails des RH sur LinkedIn. Quelle étape ? »

**Débriefs scriptés (points obligatoires) :**
- N°2 (LinkedIn → Reconnaissance) : aucune intrusion à ce stade — tout est public. C'est pourtant l'étape qui décide de qui sera visé et avec quel prétexte.
- N°3 (connexion sortante → C2) : le piège est « Installation » — mais l'installation a déjà eu lieu ; ici, la machine « téléphone » régulièrement pour recevoir des ordres. Souligner le sens **sortant** : les pare-feux bloquent l'entrant, pas ce qui sort.
- N°4 (exécution au démarrage → Installation) : persistance = survivre au redémarrage. L'Exploitation, c'était le clic (événement E).
- **Reconstitution complète à l'écran** : B → F → G → E → C → D → A. Conclure : *« à quelle étape auriez-vous cassé cette chaîne ? Réponse : à n'importe laquelle — c'est toute la beauté du modèle. »*

**Transition scriptée :** « PlastiqueNord est fictive. Les deux histoires qui suivent ne le sont pas — et elles ont eu lieu à six semaines d'intervalle. »

### 0:54–1:04 — Deux affaires réelles : WannaCry & NotPetya

**Cas n°1 — WannaCry, mai 2017 (5 min, support §4) :** raconter chronologiquement : l'exploit EternalBlue volé à la NSA et publié par les Shadow Brokers ; le 12 mai, la déferlante — plus de 200 000 machines, 150 pays, le NHS britannique avec ~19 000 rendez-vous et opérations annulés (National Audit Office), Renault qui stoppe des usines par précaution ; puis le rebondissement : un chercheur de 22 ans enregistre pour quelques dollars un nom de domaine trouvé dans le code — et déclenche le « kill switch » qui stoppe le ver. Attribution : le groupe Lazarus — « celui dont vous avez rempli la fiche d'identité la semaine dernière ». Leçon : le correctif MS17-010 existait depuis DEUX MOIS.

**Cas n°2 — NotPetya, juin 2017 (5 min, support §4) :** six semaines plus tard, en pire : un faux ransomware, en réalité un **wiper** (payer ne rend rien) ; le vecteur : la mise à jour piégée d'un logiciel comptable ukrainien — l'attaque par la chaîne d'approvisionnement ; les dégâts collatéraux : Maersk, 45 000 PC détruits, sauvé par un contrôleur de domaine au Ghana épargné grâce à une coupure de courant, ~300 M$ ; Saint-Gobain, ~250 M€ de ventes perdues ; total mondial : plus de 10 milliards de dollars (estimation des autorités américaines) — l'attaque la plus coûteuse de l'histoire, attribuée à un sabotage étatique visant l'Ukraine. Relance chat : *« Quel détail vous marque le plus ? »* — lire 2-3 réactions.

**Transition scriptée :** « Ces deux catastrophes exploitaient une faille corrigée depuis deux mois. Alors, question directe. »

### 1:04–1:08 — Sondage n°5 : et chez vous ?

**Consigne :** Lancer le **📊 Sondage n°5** (opinion) — à quel rythme les mises à jour de sécurité sont-elles appliquées dans votre organisation ? Vote 60-90 s, annoncer qu'il n'y a pas de bonne réponse.

**🎙️ Débrief scripté :**
> « Pas de bonne réponse — mais une prise de conscience. Les fenêtres planifiées (réponse B) sont la réalité majoritaire, et c'est sain... SI le délai se compte en jours pour les failles critiques de type ver. Et si vous avez répondu C — "je ne sais pas" — c'est déjà une information précieuse : quelqu'un porte-t-il ce sujet chez vous ? La gestion des vulnérabilités aura sa session dédiée dans le module E. »

### 1:08–1:12 — 🤔 Mini-scénario : le correctif « wormable »

**Consigne :** Afficher le mini-scénario du support : un correctif critique pour une faille wormable impose de redémarrer des serveurs de production. *« Tapez A, B ou C dans le chat. »*

**Débrief :** B — une faille wormable se traite en **jours**, pas en mois : fenêtre d'urgence, test rapide, redémarrage de nuit, communication. A est exactement l'erreur des victimes de 2017 ; C crée une panne certaine pour éviter une panne hypothétique. La sécurité est un arbitrage organisé, pas un réflexe de panique.

**Transition scriptée :** « Dernière pièce de l'arsenal : les attaques qui ne passent pas par un malware installé chez vous. »

### 1:12–1:17 — Séquence 3 : DDoS & injections SQL

**Points de contenu à dérouler (support §5) :**
- **DDoS** : saturer un serveur sous des millions de requêtes issues d'un **botnet** ; l'analogie de la manifestation qui bloque l'entrée du magasin ; l'exemple Mirai (2016) — des centaines de milliers de caméras et objets connectés, des attaques de l'ordre du térabit par seconde, Twitter et Netflix inaccessibles via leur prestataire DNS. Atteinte à la **Disponibilité** (B01).
- **Injection SQL** : des commandes de base de données glissées dans un formulaire mal programmé ; atteinte à la Confidentialité et à l'Intégrité ; l'une des failles les plus anciennes et toujours exploitées (référence OWASP).
- Question rhétorique : *« Quel point commun entre ces deux attaques ? »* — aucun malware à installer chez la victime : on exploite ce qui est déjà exposé.

**Transition scriptée :** « Vérifions les fondamentaux : trois questions, trois votes. »

### 1:17–1:23 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : le ver se propage seul ; briser un seul maillon suffit ; l'injection SQL exploite un site mal programmé. Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/B_S03_support.md).

### 1:23–1:26 — Exercice bonus (Sondage n°9) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°9** — la macro Word « Activer le contenu » : que se passe-t-il ? Débrief : le code malveillant s'exécute et télécharge un chargeur (B) ; l'éditeur avait fermé la porte (macros désactivées par défaut), l'attaquant demande poliment à la victime de l'ouvrir elle-même. Pont parfait vers B04 : quand la technique est bloquée, on manipule l'humain. À couper en cas de retard.

### 1:26–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Ce soir : le zoo des malwares — classés par propagation et par charge utile ; la Kill Chain — sept étapes, un seul maillon à briser ; MITRE ATT&CK — l'encyclopédie du réel ; et deux catastrophes mondiales qui tenaient à un correctif de deux mois. Avant de partir : tapez dans le chat UN mot que vous retenez. »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Self-paced : module IBM SkillsBuild *"Introduction to Cybersecurity Tools & Cyber Attacks"* (~1h30) + regarder la vidéo recommandée sur Stuxnet et repérer les étapes de sa propagation (réinvestissement direct de la Kill Chain).
- Teaser B04 : « la semaine prochaine, l'arme la plus efficace de toutes — et ce n'est pas un logiciel. Une entreprise de cinéma française a perdu 19 millions d'euros sans qu'un seul malware ne soit utilisé. Comment ? Réponse jeudi. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**Exercice bonus n°9** (1:23–1:26) — il est dans le support en exercice bonus.
2. Sauter la démonstration MITRE ATT&CK en direct (0:34–0:40 ramené à 4 min sur slide seule).
3. Compresser le débrief du sondage n°5 à 1 min.
4. Ne JAMAIS couper : la Reconstruction d'incident, les deux affaires réelles, le quiz.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°3 : ransomware ou wiper — pourquoi la distinction change tout).
2. Prolonger la démonstration MITRE ATT&CK : ouvrir la fiche du Lazarus Group et retrouver les techniques vues dans les cas réels.
3. Questions/réponses libres.

## Travail en autonomie (Self-paced)
* **Avant la session suivante (B04)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Introduction to Cybersecurity Tools & Cyber Attacks"* (~1h30).
  * **Recherche autonome** : Regarder la vidéo recommandée sur le fonctionnement de l'attaque Stuxnet et identifier les différentes étapes de sa propagation (les replacer mentalement dans la Cyber Kill Chain).
