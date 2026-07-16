# Plan de séance — Session B06 : Défenses réseau
Parcours : B 20 sessions  |  Module : B — Systèmes & réseaux  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (verbes d'action)
- **Expliquer** le fonctionnement d'un pare-feu et comparer le filtrage sans état (*stateless*), à état (*stateful*) et de nouvelle génération (NGFW).
- **Différencier** le rôle et le positionnement d'un IDS (détecter, passif) et d'un IPS (bloquer, actif) dans l'architecture réseau.
- **Modéliser** une architecture réseau segmentée (WAN / LAN / DMZ) et construire sa table de filtrage avec la politique *Default Deny*.

## Prérequis & progression
- **Prérequis** : B05 (couches, ports, paquets).
- **Lien de progression** : B05 a appris à lire le trafic ; B06 apprend à le filtrer et à cloisonner le réseau. B07 sécurisera ensuite le contenu des flux eux-mêmes (chiffrement TLS, VPN).

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama B06 ([spécifications](../slides/B_S06_slides_spec.md)) — la table de filtrage doit pouvoir être remplie en direct à l'écran (slide dédiée ou tableur partagé).
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Target 2013 : par où sont-ils entrés ? | B) Le prestataire de chauffage |
| 2 | 0:44 | Sondage | Règle : clients Internet → site e-commerce ? | A) WAN → DMZ, TCP/443, Allow |
| 3 | 0:48 | Sondage | Règle : mises à jour du serveur web ? | B) DMZ → WAN, TCP/443, Allow |
| 4 | 0:52 | Sondage | Règle : administration SSH du serveur ? | A) LAN → DMZ, TCP/22, Allow |
| 5 | 1:08 | Sondage | Votre réseau est-il segmenté ? | Opinion (pas de bonne réponse) |
| 6 | 1:16 | Sondage | Stateful vs stateless ? | A) Mémoire du contexte des connexions |
| 7 | 1:18 | Sondage | IDS vs IPS ? | B) Détecte/alerte vs bloque en temps réel |
| 8 | 1:20 | Sondage | Qu'apporte un NGFW ? | C) L'inspection profonde du contenu (DPI) |
| 9 | Tampon | Sondage | Serveur DMZ compromis : qu'est-ce qui protège le LAN ? | B) La règle DMZ → LAN interdite |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil & retour sur l'inventaire Wi-Fi | 💬 Chat : nombre d'appareils |
| 0:04–0:10 | Brise-glace : l'entrée improbable de Target | 📊 Sondage n°1 |
| 0:10–0:26 | Séquence 1 : Les pare-feux et leurs générations | 💬 Chat : l'intrus du portier |
| 0:26–0:34 | Séquence 2 : IDS & IPS | Question rhétorique |
| 0:34–0:44 | Séquence 3 : Segmentation, DMZ & VLAN | Question rhétorique |
| 0:44–0:58 | Activité : La table de filtrage d'EcoLog | 📊 Sondages n°2, 3, 4 |
| 0:58–1:08 | Chiffres clés & affaires Target + thermomètre | 💬 Chat : réactions |
| 1:08–1:12 | Et chez vous ? La segmentation | 📊 Sondage n°5 |
| 1:12–1:16 | Mini-scénario : l'alerte de 2h du matin | 🤔 Chat : A, B ou C |
| 1:16–1:22 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:22–1:26 | Exercice bonus : le confinement DMZ (tampon) | 📊 Sondage n°9 |
| 1:26–1:30 | Synthèse, devoirs & teaser B07 | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & retour sur le self-paced

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous ! La semaine dernière, vous avez appris à lire le trafic ; ce soir, on apprend à le FILTRER. Mais d'abord, votre inventaire de la semaine : combien d'appareils avez-vous comptés sur votre Wi-Fi domestique ? Le chiffre dans le chat ! »

**Points à dérouler :**
- Lire 4-5 chiffres du chat, souligner la surprise habituelle (téléviseur, imprimante, assistant vocal, ampoules...) : « chacun de ces appareils est une machine sur votre réseau — retenez ce sentiment, on y revient ce soir avec une histoire d'aquarium. »
- Rappel express de B05 : les couches, les ports, TV5 Monde et son réseau « à plat ».
- Annonce du programme : les pare-feux et leurs générations, la surveillance IDS/IPS, la segmentation — et la construction collective d'une vraie table de filtrage.

**Transition scriptée :** « On commence par une devinette à 200 millions de dollars. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (l'entrée improbable)

**Consigne :** Lancer le **📊 Sondage n°1** — Target 2013 : par où les attaquants sont-ils entrés ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse B : par les identifiants d'un prestataire de chauffage et climatisation. Pas une faille exotique, pas un génie du code : un petit fournisseur hameçonné, dont l'accès au portail de facturation a mené... jusqu'aux caisses enregistreuses de 1 800 magasins. Comment passe-t-on d'un portail de facturation à des caisses enregistreuses ? Réponse : quand rien ne les sépare. Construire ces séparations, c'est le programme du soir — et l'histoire complète de Target arrive en seconde partie. »

**Transition scriptée :** « Première muraille : le pare-feu. Et pour le comprendre, engageons un portier. »

### 0:10–0:26 — Séquence 1 : Les pare-feux et leurs générations

**Points de contenu à dérouler (support §1) :**
- Le principe fondateur : **Default Deny** — tout ce qui n'est pas explicitement autorisé est interdit. (Insister : c'est une philosophie, pas un détail technique — on autorise des besoins, on ne bloque pas des menaces.)
- **Stateless** : le portier qui vérifie la liste d'invités mais oublie votre visage (chaque paquet jugé isolément).
- **Stateful** : le portier au bracelet tamponné — il se souvient des connexions initiées et laisse revenir les réponses ; tout paquet entrant non sollicité est bloqué.
- **NGFW** : l'agent des douanes — passeport (IP), trajet (état), et ouverture de la valise (**DPI** — il reconnaît l'application réelle, même sur le port 443).
- **WAF** : le spécialiste posté devant les serveurs web (anti-injections SQL vues en B03, XSS).
- Relance chat (0:22) : *« Le portier stateful laisse-t-il entrer un paquet qui ne répond à aucune connexion sortante ? Oui ou non dans le chat. »* — non : c'est exactement sa valeur ajoutée.

**Transition scriptée :** « Le pare-feu applique la loi. Mais qui surveille ce qui passe légalement les frontières ? »

### 0:26–0:34 — Séquence 2 : IDS & IPS

**Points de contenu à dérouler (support §2) :**
- Le problème : un flux **autorisé** peut transporter une attaque (exploit dans du HTTPS légitime).
- **IDS** : passif, sur copie du trafic (port miroir) — détecte par signatures ou comportement, **alerte** mais ne bloque pas.
- **IPS** : actif, sur le chemin (*inline*) — détruit le paquet malveillant en temps réel.
- Le compromis : le passif n'arrête rien ; l'actif peut se tromper — un faux positif coupe du trafic légitime (sur un système critique, un IPS mal réglé fait plus de dégâts qu'une attaque). D'où la pratique : démarrer en détection, activer la prévention règle par règle.
- Question rhétorique : *« Une alerte que personne ne lit, ça vaut combien ? »* — rien. Garder la question en tête pour l'affaire Target.

**Transition scriptée :** « Troisième pilier, le plus important de la soirée : découper le réseau en zones. »

### 0:34–0:44 — Séquence 3 : Segmentation, DMZ & VLAN

**Points de contenu à dérouler (support §3) :**
- Le danger n°1 : le **mouvement latéral** — rappel TV5 Monde (B05) : un réseau à plat, et l'intrusion périphérique atteint le cœur.
- Les trois zones : **WAN** (Internet, non sûr), **LAN** (l'interne), **DMZ** (la zone tampon pour tout ce qui doit être exposé : web, messagerie).
- **La règle d'or de la DMZ** : aucun flux initié DMZ → LAN. La DMZ est conçue pour être « perdable » : un serveur exposé compromis ne doit mener nulle part.
- **Les VLAN** : la segmentation à l'intérieur du LAN (bureautique / production / IoT / invités) — l'aéroport et ses zones à badges (analogie du support).
- Question rhétorique : *« Chez Target, dans quelle zone aurait dû vivre le portail fournisseurs ? »* — une zone étanche, sans aucun chemin vers les caisses.

**Transition scriptée :** « À vous de jouer : EcoLog vous confie son pare-feu. On écrit les règles ensemble. »

### 0:44–0:58 — Activité : La table de filtrage d'EcoLog (Sondages n°2 à 4)

**Consigne :** Afficher le contexte EcoLog (support, activité « La table de filtrage ») : LAN employés `192.168.10.0/24`, DMZ avec serveur web `192.168.20.5`, WAN. Pour chaque besoin métier, lire l'énoncé, lancer le sondage (**📊 n°2, 3, 4**, ~4-5 min chacun), débriefer, et remplir la table à l'écran ligne par ligne.

**🎙️ Verbatim de lancement :**
> « EcoLog vient d'installer son pare-feu : par défaut, TOUT est bloqué — Default Deny. À nous d'ouvrir uniquement ce qui est justifié. Besoin n°1 : les clients doivent visiter le site e-commerce en HTTPS. Quelle règle écrivez-vous ? »

**Débriefs scriptés (points obligatoires) :**
- N°2 : la question clé d'une règle est **qui initie la connexion** — le client Internet vers le serveur exposé (WAN → DMZ, 443). La réponse B ouvrirait le LAN au monde entier.
- N°3 : même protocole, direction inversée — c'est le serveur qui initie (DMZ → WAN, 443). La réponse C violerait la règle d'or (DMZ → LAN).
- N°4 : l'administration va DE la zone de confiance VERS la zone exposée (LAN → DMZ, 22) — jamais l'inverse ; et la réponse C exposerait le SSH au monde entier (retour à la force brute de B05).
- **Conclure** : afficher la table complète (5 lignes, corrigé du support), ajouter à l'oral la règle des employés (LAN → WAN, 80/443) et la ligne finale `Any → Any : Deny` — « cette dernière ligne transforme une liste de règles en politique de sécurité. »

**Transition scriptée :** « Cette table de cinq lignes vaut des centaines de millions. La preuve par deux histoires vraies. »

### 0:58–1:08 — Chiffres clés & deux affaires réelles

**Chiffres (2 min, support §4) :** 40 millions de cartes + 70 millions de dossiers clients (Target, 2013) ; plus de 200 M$ de coûts cumulés, accord de 18,5 M$ avec 47 États (2017), démission du PDG ; ~10 Go exfiltrés via un thermomètre d'aquarium (incident de 2017, rapporté par Darktrace en 2018).

**Cas n°1 — Target, 2013 (5 min, support §5) :** dérouler la chaîne complète : le prestataire de chauffage hameçonné → le portail fournisseurs → le mouvement latéral jusqu'aux caisses de 1 800 magasins → le malware qui lit les cartes en mémoire au moment du paiement, en pleine période de Noël. Le détail accablant : les outils de détection ont généré des alertes... qui n'ont pas été traitées à temps (rappel de la question rhétorique : une alerte que personne ne lit ne vaut rien). Conclusion : avec une vraie segmentation, l'attaque s'arrêtait au portail de facturation.

**Cas n°2 — Le casino et le thermomètre, 2017 (3 min, support §5) :** incident de 2017 rapporté par Darktrace en 2018 : le thermomètre connecté de l'aquarium du hall, sur le même réseau que les systèmes métier → tremplin vers la base des clients VIP → ~10 Go exfiltrés par le thermomètre. Boucler avec l'inventaire Wi-Fi du début de session : « votre téléviseur, votre imprimante, vos ampoules — que peuvent-ils joindre chez vous ? » Un VLAN IoT étanche transforme l'anecdote en non-événement. Relance chat : *« Quel détail vous marque le plus ? »*

### 1:08–1:12 — Sondage n°5 : et chez vous ?

**Consigne :** Lancer le **📊 Sondage n°5** (opinion) — le réseau que vous connaissez le mieux est-il segmenté ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Pas de bonne réponse. Si vous avez répondu B — un Wi-Fi invité — c'est déjà une vraie segmentation, et la plus accessible qui soit : la plupart des box la proposent. Si vous avez répondu C, vous savez désormais pourquoi "à plat" est le mot qui fait peur : TV5, Target, le casino — trois histoires, une seule cause racine. L'atelier B08 vous fera dessiner votre propre schéma segmenté : ce sondage est votre point de départ. »

### 1:12–1:16 — 🤔 Mini-scénario : l'alerte de 2h du matin

**Consigne :** Afficher le mini-scénario du support : l'IDS alerte à 2h du matin — un poste du LAN (salarié en congés) multiplie les connexions vers le serveur de paie sur un port inhabituel. *« Tapez A, B ou C dans le chat. »*

**Débrief :** B — toutes les caractéristiques du mouvement latéral (poste inactif, cible sensible, port inhabituel, heure creuse) : on **confine d'abord** (isoler UN poste coûte peu), on investigue ensuite. A est l'erreur de Target — l'alerte générée mais non traitée ; C réalise le déni de service à la place de l'attaquant. La réponse graduée s'apprend en B19.

**Transition scriptée :** « Trois questions pour valider vos murailles. »

### 1:16–1:22 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : la mémoire du contexte des connexions ; l'IDS détecte/alerte vs l'IPS bloque en temps réel ; le NGFW apporte l'inspection du contenu (DPI). Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/B_S06_support.md).

### 1:22–1:26 — Exercice bonus (Sondage n°9) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°9** — le serveur DMZ compromis : qu'est-ce qui protège la comptabilité interne ? Débrief : la règle de pare-feu interdisant tout flux initié DMZ → LAN (B) — ni l'antivirus ni le mot de passe du serveur déjà compromis. La DMZ est conçue pour être « perdable » sans que le cœur tombe. À couper en cas de retard.

### 1:26–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Ce soir, vous avez construit des murailles : un pare-feu qui n'autorise que le justifié — Default Deny ; des sentinelles — IDS qui alerte, IPS qui bloque ; et des zones étanches — DMZ, VLAN — pour qu'un fournisseur hameçonné ou un thermomètre compromis reste une anecdote. Un mot que vous retenez, dans le chat ! »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Self-paced : cours IBM SkillsBuild *"Network Security - Part 2"* (~1h30) + dessiner un schéma pare-feu/switch/DMZ/LAN avec draw.io (brouillon pour l'atelier B08) + observer le cadenas TLS de son navigateur sur quelques sites (préparation directe de B07).
- Teaser B07 : « vos murailles sont en place — mais qui LIT vos données pendant qu'elles voyagent ? La semaine prochaine : chiffrement, TLS, VPN — et l'histoire de la petite extension de navigateur qui a forcé le web entier à passer au HTTPS. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**Exercice bonus n°9** (1:22–1:26) — il est dans le support en exercice bonus.
2. Compresser le cas du thermomètre à 1 min (l'essentiel : IoT = machine comme une autre → VLAN dédié).
3. Raccourcir le débrief du sondage n°5 à 1 min.
4. Ne JAMAIS couper : l'activité table de filtrage, le cas Target, le quiz.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°3 : « avoir des outils » vs « avoir une sécurité opérationnelle »).
2. Esquisser en direct le schéma EcoLog complet (WAN/pare-feu/DMZ/LAN) sur le tableau blanc interactif ou via draw.io partagé.
3. Questions/réponses libres.

## Travail en autonomie (Self-paced)
* **Avant la session suivante (B07)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Network Security - Part 2"* (durée estimée : 1h30).
  * **Exercice de conception** : Dessiner un schéma réseau simple (pare-feu, switch, DMZ, LAN) avec un outil gratuit comme draw.io — il servira de brouillon pour l'atelier de synthèse B08.
  * **Observation pratique** : Inspecter le cadenas de sécurité du navigateur sur des sites internet courants pour identifier la version de TLS et l'autorité de certification émettrice.
