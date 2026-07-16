# Session B03 — Types d'attaques & vecteurs
Parcours : B 20 sessions  |  Module : A — Fondations  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - La typologie des logiciels malveillants (*malwares*)
    - Modéliser l'attaque : Cyber Kill Chain & MITRE ATT&CK
    - Attaques d'infrastructure et d'applications (DDoS, injections)
    - Deux affaires réelles : WannaCry et NotPetya (2017), les deux vers qui ont changé la cybersécurité mondiale
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Les malwares se différencient par leur propagation (vers autonomes vs virus dépendants d'une action humaine) et leurs buts (ransomwares pour rançonner, spywares pour espionner).
*   La Cyber Kill Chain modélise une attaque ciblée en 7 étapes : perturber une seule de ces étapes suffit à faire échouer l'intrusion.
*   Le framework MITRE ATT&CK offre un langage universel pour classifier les tactiques (buts) et les techniques (moyens) observées chez les attaquants — c'est là que sont documentées les TTP vues en B02.
*   Un DDoS utilise des machines infectées contrôlées à distance (botnets) pour saturer et mettre hors ligne des serveurs ; les injections SQL exploitent les sites web mal programmés.

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Classifier les principales familles de logiciels malveillants (*malwares*) en fonction de leur mode de propagation et de leur objectif.
* Modéliser le déroulement d'une cyberattaque complexe à l'aide des 7 étapes de la *Cyber Kill Chain*.
* Naviguer dans le framework d'analyse technique MITRE ATT&CK pour décoder les tactiques et techniques des attaquants.
* Expliquer le principe général des attaques par déni de service (DoS/DDoS) et des injections applicatives (web).

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** En mai 2017, le ver WannaCry a infecté plus de 200 000 machines dans 150 pays. En combien de temps ?

    - A) Un seul week-end ✅
    - B) Environ six mois
    - C) Un peu plus de deux ans

    **Débrief mentor :** Réponse A : l'essentiel de la propagation a eu lieu en **quelques heures**, le vendredi 12 mai 2017 (plus de 200 000 systèmes touchés dans 150 pays selon Europol). Aucun humain ne clique aussi vite : c'est la signature d'un **ver**, un malware qui se propage tout seul de machine en machine. Comprendre ces mécanismes de propagation — l'objet de cette session — c'est comprendre pourquoi certaines attaques se comptent en heures et d'autres en mois. Et promis : l'histoire complète de WannaCry arrive, avec son héros improbable.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Les limites du modèle Kill Chain**
La Cyber Kill Chain (Lockheed Martin, 2011) reste l'outil pédagogique de référence, mais précisez ses limites si la question vient : elle est **linéaire** alors que les attaques modernes itèrent (l'attaquant refait des boucles reconnaissance → exploitation à l'intérieur du réseau, ce qu'on appelle le mouvement latéral), et elle modélise mal les menaces internes ou les attaques sans malware. C'est pour cela que les professionnels la complètent avec MITRE ATT&CK, qui n'impose pas d'ordre : 14 tactiques (colonnes) couvrant tout le cycle, des centaines de techniques documentées sur des attaques réelles.

**2. L'arsenal moderne dépasse la taxonomie classique**
Les cinq familles présentées aux apprenants sont les fondations, mais mentionnez l'évolution : malwares **sans fichier** (*fileless*, exécutés en mémoire via des outils légitimes comme PowerShell — rien à détecter sur le disque), **macros piégées** dans les documents bureautiques (l'exercice bonus en traite), et chargeurs (*loaders*) qui téléchargent la charge finale en plusieurs étapes pour échapper aux antivirus. Message clé : les familles se **combinent** — WannaCry est à la fois un ver (propagation) et un ransomware (charge utile).

**3. EternalBlue : quand les cyberarmes fuient**
Les deux cas de la session exploitent **EternalBlue**, un exploit de la faille SMBv1 développé par la NSA américaine, volé puis publié par le groupe Shadow Brokers en avril 2017. Le correctif Microsoft (MS17-010) était disponible depuis **mars 2017** — deux mois avant WannaCry. Double leçon à faire passer : les cyberarmes étatiques finissent par se retourner contre tout le monde, et un correctif non appliqué est une porte ouverte documentée publiquement.

---

### Glossaire

*   **Botnet** — Réseau de machines infectées (ordinateurs, objets connectés) contrôlées à distance par un attaquant, utilisé notamment pour lancer des attaques DDoS massives.
*   **Command & Control (C2)** — Serveur externe contrôlé par un attaquant servant à envoyer des commandes à des systèmes piratés au sein d'un réseau cible.
*   **Cyber Kill Chain** — Modèle en 7 étapes théorisé par Lockheed Martin décrivant le cycle de vie d'une attaque ciblée.
*   **Exploit** — Code qui tire parti d'une vulnérabilité logicielle pour exécuter des actions non prévues (ex. EternalBlue exploitant la faille SMBv1).
*   **Injection SQL** — Attaque applicative consistant à faire exécuter des commandes de base de données via des champs de saisie mal contrôlés d'un site web.
*   **Payload (Charge utile)** — La partie du malware qui exécute l'action malveillante finale (chiffrer, espionner, détruire), par opposition au mécanisme de propagation.
*   **Trojan (Cheval de Troie)** — Programme nuisible camouflé sous l'apparence d'un logiciel légitime pour tromper l'utilisateur, souvent utilisé pour ouvrir une porte dérobée (*backdoor*).
*   **Wiper** — Malware de destruction pure : il efface ou corrompt les données sans possibilité de récupération, parfois déguisé en ransomware (cas NotPetya).
*   **Worm (Ver)** — Logiciel malveillant capable de se propager de manière autonome dans un réseau en exploitant des vulnérabilités, sans intervention humaine.
*   **Zero-day (Vulnérabilité 0-jour)** — Faille de sécurité logicielle non connue de l'éditeur, qui n'a donc encore fait l'objet d'aucun correctif.

---

### Concepts clés

!!! info "À retenir"
    Une attaque réussie est une **chaîne** d'étapes obligatoires, pas un coup de baguette magique. Le défenseur n'a pas besoin d'être parfait partout : briser un seul maillon — filtrer l'e-mail piégé, corriger la faille, bloquer la connexion sortante — suffit à faire échouer l'ensemble.

### 1. La typologie des logiciels malveillants (*malwares*)
Un *malware* (contraction de *malicious software*) est un programme développé dans le but de nuire à un système informatique. On les classe selon leur mode d'action et de propagation :

*   **Le virus** : Un programme qui s'attache à un fichier ou à un programme légitime. Il a besoin d'une action humaine (comme l'ouverture d'une application ou d'un fichier infecté) pour s'exécuter et se propager.
*   **Le ver (*worm*)** : Contrairement au virus, le ver est autonome. Il exploite les failles réseau pour se propager automatiquement de machine en machine, sans aucune interaction humaine. C'est le malware de la **vitesse** : quelques heures suffisent pour un tour du monde (WannaCry, ci-dessous).
*   **Le cheval de Troie (*Trojan horse*)** : Un programme malveillant qui se dissimule au sein d'un logiciel apparemment inoffensif et légitime (ex. un jeu gratuit ou un utilitaire de nettoyage). Une fois installé, il ouvre une porte dérobée (*backdoor*) pour l'attaquant.
*   **Le rançongiciel (*ransomware*)** : Il prend en otage les données de l'ordinateur en les chiffrant avec une clé mathématique robuste. L'attaquant exige le paiement d'une rançon en cryptomonnaies pour fournir la clé de déchiffrement — c'est la charge utile favorite de l'économie RaaS vue en B02.
*   **Le logiciel espion (*spyware*)** : Il s'installe discrètement pour surveiller l'activité de l'utilisateur (historique de navigation, captures d'écran) ou enregistrer les frappes au clavier (*keylogger*) afin de voler des identifiants et des mots de passe.

**Le point important : ces familles se combinent.** Un même malware peut se propager comme un ver ET chiffrer comme un ransomware ; un cheval de Troie peut livrer un spyware. On décrit donc toujours un malware par deux questions : *comment se propage-t-il ?* et *que fait-il une fois en place ?*

### 2. Modéliser l'attaque : Cyber Kill Chain & MITRE ATT&CK
Pour se défendre efficacement, il faut comprendre le parcours de l'attaquant. Deux cadres d'analyse font autorité :

#### La Cyber Kill Chain (Lockheed Martin)
Elle découpe une attaque ciblée en 7 étapes chronologiques obligatoires. Briser un seul maillon de cette chaîne suffit à stopper l'attaque :

1.  **Reconnaissance** : Collecte d'informations sur la cible (adresses email, serveurs exposés).
2.  **Armement (*Weaponization*)** : Création d'une charge utile malveillante (ex. un document Word piégé avec un exploit).
3.  **Livraison (*Delivery*)** : Envoi de la charge utile (ex. email de phishing, clé USB déposée).
4.  **Exploitation** : Déclenchement du code malveillant en exploitant une vulnérabilité sur la machine cible.
5.  **Installation** : Établissement d'une présence permanente sur la machine compromise (installation d'un cheval de Troie).
6.  **Commandement & Contrôle (C2 - *Command & Control*)** : Ouverture d'un canal de communication chiffré vers un serveur externe contrôlé par l'attaquant pour recevoir des ordres.
7.  **Actions sur Objectifs** : Réalisation de l'objectif final (vol de données, chiffrement des serveurs, destruction de systèmes).

À chaque étape correspond une parade : sensibilisation et filtrage e-mail à la Livraison, correctifs à l'Exploitation, surveillance des connexions sortantes au C2, sauvegardes aux Actions sur objectifs. C'est le principe de la **défense en profondeur** : chaque couche pallie la défaillance d'une autre.

#### Le framework MITRE ATT&CK
Il s'agit d'une encyclopédie mondiale et dynamique recensant les comportements réels des attaquants sous forme de matrice. Elle structure les **tactiques** (le but de l'attaquant, ex. *Accès initial*) et les **techniques** (comment il y parvient, ex. *Phishing*). C'est précisément là que sont documentées les **TTP** des groupes vus en B02 : la fiche du Lazarus Group y liste ses techniques observées, attaque par attaque. Contrairement à la Kill Chain, ATT&CK n'impose pas d'ordre chronologique — il cartographie tout ce qui a réellement été observé sur le terrain.

### Activité — Reconstruction d'incident : le piratage de PlastiqueNord (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Affichez le récit ci-dessous et lisez-le à voix haute. Les événements sont volontairement dans le désordre. Lancez ensuite les trois sondages : pour chaque événement proposé, les participants votent sur l'étape correspondante de la Kill Chain. Débriefez après chaque vote, puis reconstituez la chaîne complète collectivement.

> **Récit de l'incident (dans le désordre)** :
>
> *   *Événement A* : Les attaquants chiffrent les bases de données de production de l'usine PlastiqueNord et affichent une demande de rançon sur tous les serveurs.
> *   *Événement B* : L'attaquant effectue des recherches sur LinkedIn pour lister les adresses e-mail des gestionnaires RH de l'entreprise.
> *   *Événement C* : Le cheval de Troie configuré par l'attaquant télécharge un utilitaire persistant qui s'exécute automatiquement à chaque démarrage du serveur.
> *   *Événement D* : Le serveur de PlastiqueNord établit une connexion sortante chiffrée toutes les 5 minutes vers l'adresse IP externe du serveur pirate pour recevoir des instructions.
> *   *Événement E* : Le gestionnaire RH clique sur le lien présent dans le mail, ce qui déclenche une faille de sécurité dans son navigateur web non mis à jour.
> *   *Événement F* : L'attaquant conçoit un e-mail de phishing ciblé contenant un lien vers une page web maquillée et y intègre un code d'exploitation de navigateur.
> *   *Événement G* : L'attaquant envoie l'e-mail de phishing usurpant l'identité du service comptable à l'équipe RH.

*   **📊 Sondage n°2 — Événement B (les recherches LinkedIn) :** À quelle étape de la Kill Chain correspond-il ?
    *   A) Reconnaissance ✅
    *   B) Livraison (*Delivery*)
    *   C) Exploitation
*   **📊 Sondage n°3 — Événement D (la connexion sortante toutes les 5 minutes) :** À quelle étape correspond-il ?
    *   A) Installation
    *   B) Commandement & Contrôle (C2) ✅
    *   C) Actions sur objectifs
*   **📊 Sondage n°4 — Événement C (l'utilitaire qui s'exécute à chaque démarrage) :** À quelle étape correspond-il ?
    *   A) Armement (*Weaponization*)
    *   B) Exploitation
    *   C) Installation ✅

**Éléments de débriefing (pour le mentor) :**

- N°2 : la Reconnaissance ne touche pas au système de la victime — LinkedIn est public. C'est pourtant l'étape qui décide de tout : qui sera visé, avec quel prétexte. (Rappel : la surface d'exposition humaine.)
- N°3 : le piège est A. L'installation a déjà eu lieu ; ici la machine « téléphone » régulièrement à l'attaquant pour recevoir des ordres — la signature du C2. Notez le sens **sortant** de la connexion : les pare-feux bloquent l'entrant, pas ce qui sort (question de réflexion n°1).
- N°4 : l'exécution au démarrage = **persistance** = Installation. L'Exploitation, c'était l'événement E (le clic qui déclenche la faille du navigateur).
- **Reconstitution complète à l'écran :** B (Reconnaissance) → F (Armement) → G (Livraison) → E (Exploitation) → C (Installation) → D (C2) → A (Actions sur objectifs). Conclure : « à quelle étape auriez-vous pu casser cette chaîne ? Réponse : à toutes — filtrage e-mail en G, navigateur à jour en E, détection des connexions sortantes en D, sauvegardes en A. »

### 3. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **Plus de 200 000 machines dans 150 pays** touchées par le ver WannaCry en quelques heures, le 12 mai 2017 (Europol).
    - **Environ 19 000 rendez-vous et opérations annulés** dans le système de santé britannique (NHS) à cause de WannaCry (rapport du National Audit Office, 2017).
    - **Plus de 10 milliards de dollars** de dégâts mondiaux pour NotPetya (estimation des autorités américaines) — souvent citée comme l'attaque la plus coûteuse de l'histoire.
    - **Deux mois** : le temps écoulé entre la publication du correctif Microsoft MS17-010 (mars 2017) et WannaCry (mai 2017). Les victimes étaient celles qui n'avaient pas appliqué un correctif disponible.

**Comment lire ces chiffres ?** (1) Un ver se mesure en heures, pas en mois — la réaction aussi doit l'être. (2) Les dégâts ne sont pas « informatiques » : ce sont des opérations chirurgicales annulées et des usines à l'arrêt. (3) La plus grande catastrophe cyber de l'histoire exploitait une faille **déjà corrigée** : la mise à jour est l'arme défensive au meilleur rapport coût/efficacité.

### 4. Deux affaires réelles : les vers jumeaux de 2017

#### Cas n°1 — WannaCry (mai 2017) : le ver-rançongiciel stoppé par un nom de domaine

Le vendredi 12 mai 2017, un malware d'un genre nouveau déferle : **WannaCry** combine un **ver** (propagation autonome via EternalBlue, un exploit de la faille Windows SMBv1 volé à la NSA et publié un mois plus tôt) et un **ransomware** (chiffrement des données, rançon de 300 $ en bitcoins). En quelques heures : plus de 200 000 machines dans 150 pays. Au Royaume-Uni, le **NHS** est frappé de plein fouet — environ 19 000 rendez-vous et opérations annulés, des ambulances déroutées. En France, **Renault** stoppe plusieurs usines par précaution.

Le rebondissement : un chercheur britannique de 22 ans analyse le code et remarque que le malware interroge un nom de domaine inexistant avant chaque infection. Il enregistre ce domaine pour quelques dollars... et déclenche sans le savoir le « **kill switch** » : le ver, croyant être analysé dans un environnement de test, cesse de se propager. L'attaque sera attribuée par plusieurs États au groupe **Lazarus** — celui-là même dont vous avez rempli la fiche d'identité en B02.

**Ce que ce cas illustre :** la vitesse d'un ver (aucune campagne de phishing ne touche 150 pays en une journée) ; la combinaison des familles (ver + ransomware) ; et la leçon centrale : le correctif existait depuis **deux mois**. WannaCry n'a pas exploité une faille inconnue, mais l'inertie des mises à jour.

#### Cas n°2 — NotPetya (juin 2017) : le faux rançongiciel qui a coûté 10 milliards

Six semaines plus tard, le 27 juin 2017, rebelote — en pire. **NotPetya** se présente comme un ransomware, mais c'est un déguisement : c'est un **wiper**, un destructeur — payer ne récupère rien, le chiffrement est irréversible par conception. Le vecteur initial est vicieux : la mise à jour piégée d'un logiciel de comptabilité ukrainien (M.E.Doc) — une attaque par la **chaîne d'approvisionnement** (*supply chain*). Une fois dans un réseau, NotPetya se propage comme un ver (EternalBlue, encore, plus le vol de mots de passe en mémoire) et détruit tout sur son passage.

Dégâts collatéraux mondiaux : le géant du transport maritime **Maersk** voit 45 000 PC et des milliers de serveurs détruits en quelques minutes ; l'entreprise ne survit numériquement que grâce à un contrôleur de domaine au **Ghana**, épargné par une coupure électrique fortuite, et réinstalle toute son informatique en une dizaine de jours (coût estimé : de l'ordre de 300 M$). En France, **Saint-Gobain** chiffre l'impact à environ 250 M€ de ventes perdues. Total mondial : **plus de 10 milliards de dollars** selon les autorités américaines, qui attribuent l'attaque à un sabotage étatique visant l'Ukraine.

**Ce que ce cas illustre :** l'étiquette « ransomware » peut cacher un sabotage (motivation géopolitique — retour à la typologie de B02) ; la chaîne d'approvisionnement est un vecteur redoutable (votre sécurité dépend de celle de vos fournisseurs de logiciels) ; et une coupure de courant au Ghana rappelle une règle d'or : des **sauvegardes hors ligne**, déconnectées du réseau, sont le dernier rempart.

!!! tip "📊 Sondage Livestorm n°5 — Et chez vous ? (sondage d'opinion, pas de bonne réponse)"
    **Question :** WannaCry exploitait un correctif disponible depuis deux mois. Dans votre organisation (ou une que vous connaissez bien), les mises à jour de sécurité sont appliquées...

    - A) Rapidement après leur publication, de façon systématique
    - B) Lors de fenêtres de maintenance planifiées, avec un certain délai
    - C) Irrégulièrement / Je ne sais pas du tout

    **Débrief mentor :** Sondage d'opinion — l'objectif est la prise de conscience. B est la réalité majoritaire et c'est déjà bien, SI le délai est maîtrisé et raccourci pour les failles critiques « de type ver ». Les réponses C sont précieuses : ne pas savoir est déjà une information — qui, dans l'organisation, porte cette responsabilité ? La gestion des vulnérabilités a sa session dédiée dans le module E.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Vous êtes responsable informatique. Un éditeur publie un correctif critique pour une faille « wormable » (exploitable par un ver, comme EternalBlue) sur vos serveurs. Problème : l'appliquer impose de redémarrer des serveurs de production utilisés toute la journée. **Tapez A, B ou C dans le chat :**

    - A) Attendre la grande maintenance annuelle prévue dans 7 mois.
    - B) Planifier une fenêtre d'urgence sous quelques jours (test rapide, redémarrage de nuit, communication aux équipes). ✅
    - C) Tout redémarrer immédiatement en pleine journée, sans prévenir personne.

    **Débrief mentor :** B — une faille wormable critique se traite en **jours**, pas en mois (souvenez-vous : WannaCry = 2 mois d'inertie = 150 pays touchés). A est exactement l'erreur des victimes de 2017 ; C crée une panne certaine pour éviter une panne hypothétique — la sécurité ne doit pas saboter l'activité qu'elle protège. La bonne réponse est un **arbitrage organisé** : évaluer, tester vite, déployer vite, communiquer.

### 5. Attaques d'infrastructure et d'applications
En dehors des logiciels malveillants, les attaquants ciblent les capacités physiques ou logiques des serveurs :

*   **Déni de service (DoS/DDoS)** : L'attaquant sature la bande passante réseau ou les ressources d'un serveur à l'aide de millions de requêtes simultanées pour le rendre inaccessible aux utilisateurs légitimes. On parle de DDoS (Déni de service **distribué**) lorsque ces requêtes proviennent d'un réseau mondial de machines infectées contrôlées à distance (un réseau de robots ou *botnet*). Exemple marquant : en 2016, le botnet **Mirai** — des centaines de milliers de caméras et d'objets connectés infectés — a lancé des attaques de l'ordre du térabit par seconde, rendant Twitter, Netflix ou Spotify inaccessibles en frappant leur prestataire DNS commun (Dyn). L'attaque touche la **Disponibilité** de la triade vue en B01.
*   **Les injections web (SQL)** : Attaque applicative consistant à envoyer des commandes de base de données (SQL) déguisées en simples entrées utilisateur (dans un formulaire de connexion par exemple). Si le site est mal programmé, le serveur exécute ces commandes, permettant à l'attaquant de voler ou de supprimer l'ensemble de la base de données. C'est une atteinte à la **Confidentialité** et à l'**Intégrité** — et l'une des failles les plus anciennes et toujours les plus exploitées du web (référencée par l'OWASP, l'organisme de référence de la sécurité applicative).

---

### Questions de réflexion
1. Pourquoi la phase de Commandement et Contrôle (C2) de la Kill Chain nécessite-t-elle généralement une connexion *sortante* (du réseau de l'entreprise vers Internet) plutôt qu'une connexion *entrante* ? (Indice : pensez au comportement par défaut des pare-feux réseau.)
2. Si vous bloquez l'envoi des e-mails malveillants (étape de Livraison), l'attaquant peut-il tout de même compromettre vos serveurs ? Pourquoi la défense doit-elle être organisée en « couches » ?
3. NotPetya se présentait comme un ransomware alors que c'était un wiper. Pourquoi cette distinction change-t-elle tout pour la victime — et que révèle-t-elle sur la motivation de l'attaquant ?

**Corrigé / Éléments de réponse :**

1. Les pare-feux d'entreprise bloquent presque toutes les connexions entrantes non sollicitées, mais autorisent les flux sortants (navigation web). L'attaquant fait donc « téléphoner » le malware vers l'extérieur pour contourner le filtrage — d'où l'importance de surveiller aussi le trafic sortant.
2. L'attaquant peut trouver d'autres vecteurs (clé USB, faille exposée sur Internet, chaîne d'approvisionnement comme NotPetya). La défense en profondeur permet qu'une couche pallie la défaillance d'une autre.
3. Face à un vrai ransomware, payer peut (sans garantie) rendre les données ; face à un wiper, payer ne rend rien : la destruction est irréversible par conception. Le déguisement révèle la motivation : pas l'argent, mais le sabotage (géopolitique dans le cas NotPetya) — la typologie de B02 s'applique aux malwares aussi.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez les différents malwares et méthodes d'attaque informatique à l'aide d'une **comparaison biologique et historique** :
    - **Le virus** est comme un virus biologique : il a besoin de s'accrocher à un hôte (un fichier légitime, comme un document Word) et attend qu'un humain l'exécute pour se propager.
    - **Le ver (worm)** est comme une bactérie autonome : il n'a besoin de personne pour s'exécuter. Il se déplace tout seul dans les canalisations (le réseau) de machine en machine en exploitant des vulnérabilités.
    - **Le Cheval de Troie (Trojan)** est identique au mythe grec : il ressemble à un cadeau inoffensif (un logiciel gratuit, un PDF de facture) mais contient en réalité des attaquants cachés.
    - **L'attaque Zero-day** correspond à l'émergence d'une nouvelle maladie dont personne ne possède encore le vaccin (aucun correctif existant).
    - **Le DDoS** est une manifestation qui bloque l'entrée d'un magasin : chaque manifestant (machine infectée) est inoffensif, c'est la foule qui paralyse.

**Exemple d'application professionnelle :**
Dans une usine de production, une clé USB piégée est introduite sur un poste. Le malware installé exploite une faille non corrigée pour se propager de façon autonome (comportement de ver) à l'ensemble des automates industriels du réseau interne non segmenté, provoquant l'arrêt complet de la chaîne de production. La segmentation du réseau (étudiée au module B) aurait confiné l'infection à un seul atelier.

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour analyser les fichiers suspects et cartographier les tactiques d'attaque selon le framework MITRE ATT&CK :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Any.Run** : Service de sandbox interactif en ligne, permettant d'exécuter des malwares dans un navigateur et d'observer leurs comportements réseau et système en temps réel.
    *   **Joe Sandbox** : Outil d'analyse de malware automatisé haut de gamme pour les fichiers Windows, macOS, Android et Linux.
    *   **Palo Alto Networks WildFire** : Moteur d'analyse comportementale de fichiers dans le cloud, intégré nativement aux pare-feux Palo Alto pour bloquer les menaces Zero-day.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **Cuckoo Sandbox / CAPE Sandbox** : Logiciels open-source d'analyse de malware automatisée. Ils permettent de lancer un fichier suspect dans une machine virtuelle isolée et de générer un rapport détaillé sur ses activités.
    *   **Yara** : Outil d'analyse open-source permettant de créer des règles textuelles pour identifier et classer les fichiers malveillants sur la base de patterns binaires ou textuels.
    *   **MITRE ATT&CK Navigator** : Outil web libre d'exploration pour cartographier les défenses d'une entreprise par rapport aux tactiques réelles des attaquants.

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après la séquence sur les attaques d'infrastructure.

*   **📊 Sondage n°6 :** Quelle est la différence fondamentale entre un ver et un virus ?
    *   A) Le ver se propage de façon autonome, sans action humaine ✅
    *   B) Le virus est toujours plus dangereux que le ver
    *   C) Le ver ne s'attaque qu'aux serveurs, jamais aux postes de travail
*   **📊 Sondage n°7 :** Selon le principe de la Cyber Kill Chain, que faut-il réussir pour faire échouer une attaque complète ?
    *   A) Bloquer simultanément les 7 étapes
    *   B) Briser un seul maillon de la chaîne ✅
    *   C) Identifier l'attaquant avant qu'il n'agisse
*   **📊 Sondage n°8 :** Une injection SQL exploite avant tout...
    *   A) Une faille du réseau Wi-Fi de l'entreprise
    *   B) Un site web mal programmé qui exécute des saisies utilisateur comme des commandes ✅
    *   C) Un mot de passe administrateur trop faible

**Éléments de débriefing (pour le mentor) :**

- N°6 : le critère de classement n°1 est la **propagation**. « Plus dangereux » n'est pas un critère technique — un ver-ransomware comme WannaCry cumule les deux dangers.
- N°7 : c'est le message le plus rassurant de la session — le défenseur n'a pas besoin d'être parfait partout, l'attaquant, si.
- N°8 : l'injection SQL est un défaut de **programmation** (les saisies ne sont pas contrôlées) — ni le réseau ni les mots de passe n'y changent rien. D'où l'importance de la sécurité applicative (OWASP).

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Introduction to Cybersecurity Tools & Cyber Attacks"* (~1h30).
*   **Ressource complémentaire** : Visiter le site officiel d'ATT&CK (attack.mitre.org) et cliquer sur la technique "Phishing" (T1566) pour observer comment les techniques sont documentées mondialement.
*   [Cybermalveillance — Fiche Ransomware](https://www.cybermalveillance.gouv.fr/tous-nos-contenus/fiches-reflexes/rancongiciels-ransomwares)
*   [OWASP — Vulnérabilités applicatives](https://owasp.org/)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Compréhension des mécanismes de contournement des protections par défaut.
*   **📊 Sondage Livestorm n°9 :** Un fichier joint nommé `rapport.docx` contient des macros désactivées par défaut par Microsoft Word. L'utilisateur clique sur « Activer le contenu » car le document affiche : « activez les macros pour déchiffrer le texte ». Que se passe-t-il ?
    *   A) Le document est déchiffré de manière sécurisée.
    *   B) Le code malveillant de la macro s'exécute et télécharge un chargeur (*loader*) en mémoire ✅
    *   C) L'antivirus bloque systématiquement l'action, sans exception possible.
*   **Guide d'animation (pour le mentor) :** L'éditeur a fermé la porte (macros désactivées par défaut)... alors l'attaquant demande poliment à la victime de l'ouvrir elle-même. C'est un pont parfait vers la session B04 : quand la technique est bloquée, l'attaquant manipule l'humain. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Botnet** | Réseau de machines infectées contrôlées à distance, carburant des attaques DDoS massives (ex. Mirai, 2016). |
| **Command & Control (C2)** | Serveur externe de l'attaquant vers lequel la machine compromise ouvre une connexion **sortante** pour recevoir des ordres. |
| **Cyber Kill Chain** | Modèle en 7 étapes (Lockheed Martin) du cycle de vie d'une attaque — briser un maillon suffit. |
| **Exploit** | Code tirant parti d'une vulnérabilité (ex. EternalBlue sur la faille SMBv1). |
| **Injection SQL** | Commandes de base de données glissées dans les champs de saisie d'un site mal programmé. |
| **Trojan (Cheval de Troie)** | Programme nuisible camouflé en logiciel légitime, ouvrant souvent une porte dérobée. |
| **Wiper** | Malware de destruction irréversible, parfois déguisé en ransomware (NotPetya, 2017). |
| **Worm (Ver)** | Malware autonome se propageant seul par le réseau — se mesure en heures (WannaCry, 2017). |
| **Zero-day** | Faille inconnue de l'éditeur, donc sans correctif existant. |

**La règle d'or de la session :** une attaque est une chaîne, pas un éclair — filtrez la livraison, corrigez vite les failles « wormables », surveillez les connexions sortantes et gardez des sauvegardes hors ligne : un seul maillon brisé, et l'attaque échoue.
