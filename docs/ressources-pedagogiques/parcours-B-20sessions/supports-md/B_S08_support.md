# Session B08 — Durcissement des systèmes & endpoints
Parcours : B 20 sessions  |  Module : B — Systèmes & réseaux  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30) — inclut l'**Atelier de Synthèse 1**

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Le Principe du Moindre Privilège
    - Le Durcissement Système (Hardening)
    - Antivirus Traditionnel vs EDR
    - Une affaire réelle : Colonial Pipeline (2021), l'oléoduc paralysé par un compte dormant
    - L'**Atelier de Synthèse 1** : l'architecture réseau sécurisée de la PME MedDistri
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Le **principe du moindre privilège** protège le système en limitant les droits des utilisateurs au strict nécessaire pour leurs tâches courantes.
*   Le **durcissement (hardening)** réduit la surface d'attaque en fermant les ports locaux, en désactivant les services superflus et en chiffrant les données au repos.
*   La gestion des correctifs de sécurité (*patching*) est l'arme la plus efficace contre l'exploitation des failles de sécurité publiques (rappel WannaCry, B03).
*   L'**EDR** surpasse l'antivirus classique en analysant en continu les comportements des processus pour contrer les attaques inconnues et automatiser la réaction.

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Appliquer le principe du moindre privilège sur un système d'exploitation Windows ou Linux pour restreindre la surface d'attaque.
* Établir et déployer une checklist méthodologique de durcissement (*hardening*) de serveur ou de poste de travail.
* Différencier les mécanismes de détection par signatures d'un antivirus traditionnel de la détection comportementale d'un EDR (*Endpoint Detection and Response*).
* Concevoir collectivement l'architecture réseau sécurisée d'une PME en mobilisant les acquis du module B (**Atelier de Synthèse 1**, par sondages et chat).

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** En mai 2021, le plus grand oléoduc des États-Unis (Colonial Pipeline) a été paralysé par un rançongiciel, provoquant des pénuries d'essence sur la côte Est. Quel était le point d'entrée ?

    - A) Un compte VPN dormant, sans double authentification ✅
    - B) Une faille zero-day inconnue de tous
    - C) Un employé complice payé par les attaquants

    **Débrief mentor :** Réponse A : un simple compte VPN **qui n'aurait plus dû exister** — inactif mais jamais désactivé — dont le mot de passe circulait dans une fuite de données, et sans MFA (analyse Mandiant présentée au Congrès américain). Pas de génie, pas de zero-day : du ménage non fait. Ce soir, on apprend à faire ce ménage — c'est le durcissement — puis on assemble TOUT le module réseau dans votre premier Atelier de Synthèse. L'histoire complète de Colonial arrive en milieu de session.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Le durcissement industrialisé : benchmarks et GPO**
Expliquez comment le durcissement passe à l'échelle : les référentiels publics (**CIS Benchmarks**, guides de configuration de l'**ANSSI**) listent des centaines de points de contrôle par système ; les **GPO** (Group Policy Objects) d'Active Directory les déploient de façon centralisée sur tout un parc Windows (désactiver l'exécution automatique des supports USB, renommer le compte administrateur local, imposer les politiques de mots de passe). Message : on ne durcit pas 500 postes à la main — on définit une politique, on la déploie, on la **vérifie** (outils type OpenSCAP).

**2. EDR : la boîte noire comportementale**
Approfondissez la rupture antivirus → EDR : l'antivirus compare des empreintes de fichiers à une base de signatures — aveugle face au zero-day et au malware polymorphe (et aux attaques *fileless* vues en B03, qui n'écrivent aucun fichier). L'EDR observe les **comportements** : un document Word qui lance PowerShell, qui chiffre des fichiers en masse, qui contacte une IP inconnue — chaîne anormale, blocage, et **isolement réseau automatique** de la machine. L'EDR est aussi l'outil du SOC (B16) : il enregistre tout, comme une boîte noire d'avion.

**3. Les comptes dormants, angle mort du moindre privilège**
Colonial Pipeline (cas de la session) illustre un angle mort : le moindre privilège ne concerne pas que les droits des comptes actifs, mais l'**existence** même des comptes. Chaque compte oublié (ancien salarié, prestataire parti, service décommissionné) est une porte sans gardien — rappel direct de l'exercice bonus « offboarding » de B02. La revue périodique des comptes et accès est un contrôle simple, peu coûteux et redoutablement efficace.

---

### Glossaire

*   **CIS Benchmarks** — Référentiels publics de configuration sécurisée (Center for Internet Security) listant les points de durcissement par système ou logiciel.
*   **Chiffrement au repos** — Chiffrement des données stockées sur le disque (BitLocker, LUKS), protégeant contre le vol physique de la machine.
*   **Durcissement (Hardening)** — Processus de configuration visant à sécuriser un système d'exploitation ou une application en réduisant sa surface d'attaque.
*   **EDR (Endpoint Detection and Response)** — Solution de sécurité installée sur les terminaux surveillant les comportements pour détecter et bloquer les attaques sophistiquées en temps réel.
*   **GPO (Group Policy Object)** — Outil de l'infrastructure Microsoft Active Directory permettant de configurer de manière centralisée les règles de sécurité d'un parc de machines Windows.
*   **Moindre privilège** — Principe de sécurité consistant à n'accorder à un utilisateur ou processus que les droits strictement nécessaires à l'accomplissement de sa tâche.
*   **Patch Management** — Processus systématique de déploiement des mises à jour correctives logicielles pour combler les failles de sécurité.
*   **UAC (User Account Control)** — Mécanisme de sécurité Windows demandant l'approbation de l'utilisateur pour accorder des privilèges d'administration temporaires à un programme.

---

### Concepts clés

!!! info "À retenir"
    Après les murailles (B06) et les tunnels (B07), reste la cible finale de presque toutes les attaques : **la machine elle-même**. Un poste durci — comptes limités, services fermés, disque chiffré, correctifs à jour, EDR aux aguets — transforme la plupart des intrusions en impasses. Et le durcissement commence par une question d'inventaire : ce compte, ce service, ce port... a-t-il une raison d'exister ?

### 1. Le Principe du Moindre Privilège
Le principe du moindre privilège (*Least Privilege*) stipule qu'un utilisateur, un programme ou un processus ne doit posséder que les droits d'accès strictement nécessaires à l'accomplissement de sa tâche, et rien de plus.

*   **En pratique** : Les utilisateurs ne doivent jamais travailler au quotidien avec un compte disposant de privilèges d'administration globaux (compte Administrateur sous Windows ou `root` sous Linux).
*   **Élévation de privilèges** : Pour les tâches d'administration ponctuelles, l'administrateur doit utiliser un mécanisme d'élévation temporaire des droits (comme le contrôle de compte d'utilisateur **UAC** sous Windows, ou la commande `sudo` sous Linux), nécessitant une re-saisie de mot de passe.
*   **Le cycle de vie des comptes** : le moindre privilège s'applique aussi dans le temps — un compte qui ne sert plus (départ, fin de mission, service décommissionné) doit être **désactivé immédiatement**. Un compte dormant est une porte sans gardien (rappel de l'exercice « offboarding » de B02... et l'exacte cause de l'affaire Colonial Pipeline ci-dessous).
*   *Objectif de sécurité* : Limiter la portée d'une erreur de manipulation ou restreindre les droits qu'un pirate obtiendrait s'il parvenait à compromettre la session de l'utilisateur.

### 2. Le Durcissement Système (Hardening)
Par défaut, les systèmes d'exploitation (Windows, Linux, macOS) sont livrés configurés pour maximiser la compatibilité et la facilité d'utilisation, ce qui se fait souvent au détriment de la sécurité (nombreux services activés, ports ouverts, partages activés).
Le **durcissement** (*hardening*) désigne l'ensemble des configurations appliquées à un système pour réduire sa surface d'exposition aux attaques.

*   *L'analogie* : Une voiture neuve livrée par défaut avec toutes les vitres baissées, l'alarme désactivée et la boîte à gants déverrouillée. Le durcissement consiste à remonter les vitres, fermer les portes à clé, activer l'antidémarrage et fermer les coffres.

#### Les 5 étapes indispensables du durcissement :
1.  **Désactivation des services et protocoles inutiles** : Désactiver les services non requis pour le rôle du serveur (ex. désactiver le service d'impression sur un serveur de base de données). Supprimer les anciens protocoles réseau vulnérables comme SMBv1 (le vecteur de WannaCry, B03) ou Telnet.
2.  **Gestion rigoureuse des correctifs (*Patch Management*)** : Appliquer systématiquement les correctifs de sécurité du système d'exploitation et des applications tierces pour fermer les failles connues — en délai court pour les failles critiques (rappel du mini-scénario « wormable » de B03).
3.  **Configuration des politiques de sécurité locales** : Imposer une longueur minimale de mots de passe, limiter le nombre de tentatives de connexion échouées (verrouillage temporaire du compte) et désactiver les comptes par défaut (comme le compte "Invité").
4.  **Chiffrement des disques durs** : Activer le chiffrement au repos (BitLocker sur Windows, LUKS sur Linux) pour empêcher un attaquant ayant volé physiquement la machine d'accéder aux données en branchant le disque dur sur un autre ordinateur.
5.  **Pare-feu local actif** : Activer et configurer le pare-feu local de l'hôte (Windows Defender Firewall ou UFW/iptables sous Linux) pour bloquer les flux réseau entrants non autorisés directement au niveau du système d'exploitation.

À l'échelle d'un parc, ces règles ne s'appliquent pas à la main : les référentiels publics (**CIS Benchmarks**, guides **ANSSI**) fournissent les listes de contrôle, et les **GPO** d'Active Directory les déploient de façon centralisée sur des centaines de postes.

### 3. Antivirus Traditionnel vs EDR
La protection des machines hôtes (*endpoints*) a fortement évolué pour faire face à la sophistication des malwares.

*   **L'Antivirus traditionnel** : Fonctionne principalement par **signatures**. Il calcule l'empreinte mathématique (hachage) d'un fichier suspect et la compare à une base de données mondiale de signatures de malwares connus.
    *   *Limite* : Il est inefficace face aux menaces inconnues (attaques Zero-Day), aux fichiers malveillants modifiés à la volée (malwares polymorphes) et aux attaques **sans fichier** (*fileless*, vues en B03) qui n'écrivent rien sur le disque.
*   **L'EDR (*Endpoint Detection and Response*)** : Il agit comme une boîte noire et un agent de surveillance intelligent sur la machine. Il surveille en continu les actions des processus, les modifications de fichiers et le comportement réseau.
    *   *Force* : Il détecte les anomalies comportementales. Si un fichier Word démarre discrètement un script PowerShell pour chiffrer des fichiers dans vos documents, l'EDR repère cette anomalie comportementale (inconnue en termes de signature), bloque le processus suspect et isole la machine du réseau local pour éviter la propagation.

### 4. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **Environ 4,4 millions de dollars** de rançon payés par Colonial Pipeline en mai 2021 (montant confirmé par son PDG) — dont environ 2,3 M$ récupérés un mois plus tard par la justice américaine.
    - **Un compte VPN dormant sans MFA** : le point d'entrée de l'attaque, identifié par les analystes de Mandiant lors de l'enquête (2021).
    - **~52 000 $ de rançon demandée... jusqu'à ~17 M$ de reconstruction** : l'asymétrie de l'attaque SamSam contre la ville d'Atlanta en 2018 (estimations rapportées par la presse américaine).

**Comment lire ces chiffres ?** (1) Les plus grandes pannes partent souvent du plus petit oubli : un compte à désactiver. (2) Payer ne dispense pas de reconstruire — et la justice ne récupère pas toujours (rappel du débat de B02). (3) Refuser de payer se prépare AVANT l'attaque : sauvegardes, durcissement, plan de reprise — sinon la facture décuple.

### 5. Une affaire réelle : Colonial Pipeline (2021), l'oléoduc arrêté par un mot de passe

Le 7 mai 2021, **Colonial Pipeline** — l'oléoduc qui achemine près de la moitié des carburants de la côte Est américaine — détecte un rançongiciel du groupe **DarkSide** (un RaaS, exactement le modèle économique étudié en B02) sur son réseau informatique. Par précaution, l'entreprise **arrête l'oléoduc lui-même** : près de 9 000 km de conduites à sec pendant plusieurs jours, des files d'attente aux stations-service, des achats de panique, l'état d'urgence déclaré dans plusieurs États. L'entreprise paie environ **4,4 M$** de rançon (75 bitcoins) ; la justice américaine en récupérera environ 2,3 M$ un mois plus tard en saisissant le portefeuille des attaquants.

L'enquête (Mandiant) révèle un point d'entrée d'une banalité désarmante : un **compte VPN dormant** — plus utilisé, jamais désactivé — dont le mot de passe figurait dans une fuite de données antérieure, et **sans double authentification**. Aucun exploit sophistiqué : une porte oubliée, avec une clé qui traînait sur Internet.

**Ce que ce cas illustre :** le durcissement est d'abord un travail d'**inventaire et de ménage** (comptes dormants, services inutiles, accès obsolètes) ; la MFA sur les accès distants n'est pas une option (rappel B04 : elle bloque l'écrasante majorité des attaques automatisées) ; et l'impact d'une cyberattaque déborde l'informatique — ici, c'est l'approvisionnement en carburant d'une côte entière qui s'est arrêté. **Cas complémentaire — Atlanta (2018)** : la ville refuse de payer les ~52 000 $ exigés par le rançongiciel SamSam... mais, faute de préparation, la reconstruction coûtera des millions (jusqu'à ~17 M$ selon les estimations). Moralité : refuser de payer est la bonne doctrine — à condition d'avoir durci et sauvegardé AVANT.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Un commercial vous appelle : « Je pars en déplacement demain matin, il me faut les droits administrateur sur mon portable pour installer le logiciel de démonstration du client. » **Tapez A, B ou C dans le chat :**

    - A) Lui donner les droits administrateur permanents : il est autonome et pressé.
    - B) Faire installer le logiciel par le support aujourd'hui même, ou lui accorder une élévation temporaire, tracée et limitée à cette installation. ✅
    - C) Refuser : aucun logiciel non standard, jamais, quelle que soit la raison.

    **Débrief mentor :** B — le moindre privilège n'est pas le refus du besoin, c'est le refus du privilège **permanent** pour un besoin **ponctuel**. A crée un poste où le moindre clic malheureux s'exécute avec les pleins pouvoirs (et qui le restera longtemps après le déplacement). C sacrifie l'activité à la sécurité — le commercial trouvera un contournement pire (PC personnel, clé USB...). La sécurité qui dit toujours non finit contournée ; celle qui organise le OUI encadré est obéie.

### Atelier de Synthèse 1 — L'architecture sécurisée de MedDistri (Sondages Livestorm n°2 à 4)

**Le principe** (voir [Ateliers de Synthèse](../projet/B_miniprojets.md)) : 30 minutes pour assembler TOUS les acquis du module B sur un cas concret. Le mentor affiche le réseau **à plat** de la PME MedDistri (distribution de matériel médical, 40 salariés : postes bureautique, serveur web vitrine, serveur de gestion/comptabilité, 15 commerciaux nomades — tout sur le même réseau, aucun filtrage interne). Le public construit l'architecture cible par sondages et chat.

*   **📊 Sondage n°2 — Le serveur web public (acquis B06) :** Où placer le serveur web vitrine de MedDistri ?
    *   A) Sur le commutateur des postes de travail, c'est plus simple à administrer
    *   B) Sur un port dédié du pare-feu, dans une DMZ aux règles de filtrage étanches ✅
    *   C) Directement branché sur la box Internet, devant le pare-feu
*   **📊 Sondage n°3 — Les commerciaux nomades (acquis B05/B07) :** Comment les 15 commerciaux accèdent-ils au serveur de gestion depuis l'extérieur ?
    *   A) En exposant le service RDP du serveur sur Internet, protégé par mot de passe
    *   B) Par un VPN d'entreprise avec double authentification (MFA) ✅
    *   C) Aucun accès distant : ils attendent de revenir au bureau
*   **📊 Sondage n°4 — Les postes de travail (acquis B08) :** Quelle combinaison de durcissement prioritaire pour le poste de la comptable ?
    *   A) Installer deux antivirus de marques différentes pour doubler la protection
    *   B) Compte utilisateur standard (pas administrateur) + EDR + chiffrement du disque ✅
    *   C) Un antivirus à jour suffit, le reste est superflu

**Déroulé de l'atelier (pour le mentor) :**

1. **Présentation (5 min)** : afficher le schéma à plat de MedDistri et faire réagir le chat : *« Qu'est-ce qui vous choque sur ce schéma ? »* (attendu : tout communique avec tout, serveur web exposé au milieu des postes, aucun VPN — les fantômes de TV5 Monde et Target).
2. **Votes n°2 à 4 (12 min)** : un sondage par décision d'architecture, débrief après chaque vote (éléments ci-dessous).
3. **La table de flux collective (8 min)** : dessiner le schéma cible au tableau blanc (WAN → pare-feu → DMZ / LAN segmenté / VLAN) et construire la table de filtrage à partir des propositions du **chat** (*« proposez-moi une règle : source → destination → port → action »*), en réutilisant la méthode d'EcoLog (B06). Terminer par la ligne `Any → Any : Deny`.
4. **Synthèse (3 min)** : le schéma final à l'écran — chaque brique du module B y figure : segmentation (B06), VPN/MFA et TLS (B07), postes durcis et EDR (B08), et la surveillance des flux (B05).

**Éléments de débriefing (pour le mentor) :**

- N°2 : la réponse C expose le serveur sans aucune protection ; la A reproduit Target (le serveur exposé au milieu des postes). La DMZ sur port dédié du pare-feu isole ce qui est « perdable » — règle d'or : aucun flux initié DMZ → LAN.
- N°3 : la réponse A, c'est le scénario force brute de B05 (des milliards de tentatives par an sur RDP) ; la C sacrifie l'activité. VPN + MFA : la fonction est conservée, le chemin est sécurisé — et souvenez-vous de Colonial : le VPN sans MFA et sans revue des comptes est lui-même une porte.
- N°4 : la réponse A est un mythe (deux antivirus se neutralisent souvent) ; la C ignore les attaques sans fichier et le vol physique. La combinaison gagnante empile trois couches : moindre privilège (limiter les dégâts), EDR (détecter le comportement), chiffrement (protéger le disque volé).

!!! tip "📊 Sondage Livestorm n°5 — Et vous ? (sondage d'opinion, pas de bonne réponse)"
    **Question :** Sur votre poste de travail professionnel actuel, êtes-vous administrateur local ?

    - A) Oui, et je m'en sers régulièrement
    - B) Non : un compte standard, le support gère les installations
    - C) Je ne sais pas / Je n'ai jamais vérifié

    **Débrief mentor :** Sondage d'opinion — un miroir de la maturité des organisations. B est la cible (avec un processus d'élévation fluide, comme dans le mini-scénario du commercial). A est fréquent en PME : chaque clic s'exécute alors avec les pleins pouvoirs. C est une réponse précieuse : vérifier prend 30 secondes (essayez d'installer un logiciel) — c'est votre action de la semaine. Aucun jugement : l'objectif du parcours est précisément de faire évoluer ces pratiques.

---

### Questions de réflexion
1. Si une entreprise déploie des EDR de dernière génération sur tous ses postes, peut-elle se dispenser d'appliquer les mises à jour de sécurité de son système d'exploitation ? Pourquoi la défense en profondeur reste-t-elle indispensable ?
2. Quelle est la différence fondamentale entre le rôle d'un administrateur système qui fait du "durcissement" et un analyste SOC qui surveille les alertes EDR ? Comment ces deux activités se complètent-elles ?
3. Dans l'affaire Colonial Pipeline, aucune faille logicielle n'a été exploitée. Listez les trois contrôles simples qui, chacun séparément, auraient suffi à empêcher l'attaque.

**Corrigé / Éléments de réponse :**

1. L'EDR détecte les comportements malveillants, mais si la faille n'est pas corrigée, la vulnérabilité reste ouverte et l'attaquant pourrait désactiver l'EDR ou trouver un moyen de contournement. Chaque couche pallie la défaillance d'une autre (défense en profondeur).
2. L'administrateur prévient (réduction de la surface d'attaque), le SOC détecte et réagit aux menaces résiduelles. L'un sans l'autre est incomplet : un parc durci sans surveillance laisse passer l'inconnu ; une surveillance sur un parc non durci croule sous les alertes.
3. (1) La revue périodique des comptes : le compte VPN dormant aurait été désactivé ; (2) la MFA sur l'accès VPN : le mot de passe volé n'aurait pas suffi ; (3) l'interdiction de réutiliser des mots de passe (et la surveillance des fuites) : le mot de passe compromis n'aurait pas ouvert la porte.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez le durcissement d'un système informatique (Hardening) comme la sécurisation d'une **maison neuve** :
    - Par défaut, le constructeur installe de nombreuses fenêtres, des portes de service et laisse parfois des clés standard.
    - **Le durcissement (Hardening)** consiste à condamner les fenêtres inutilisées (désactiver les services et ports inutiles), à changer les codes par défaut, et à installer des serrures multipoints (le moindre privilège).
    - **L'Antivirus classique** est comparable à une liste de photos de cambrioleurs connus affichée à l'entrée. Si le voleur se déguise, l'antivirus le laisse passer.
    - **L'EDR (Endpoint Detection and Response)** est similaire à un détective privé et des capteurs de mouvements installés dans chaque pièce : il analyse les comportements inhabituels (quelqu'un tente de casser un mur à l'intérieur) et bloque l'action immédiatement.

**Exemple d'application professionnelle :**
Dans le cadre d'un projet de sécurisation, le service informatique applique une politique de durcissement sur les serveurs de fichiers : désactivation du protocole vulnérable SMBv1, fermeture des ports SSH d'administration directe, et restriction stricte des droits d'accès administrateurs locaux. Quelques mois plus tard, un malware s'exécute sur le réseau interne mais ne peut pas se propager car les services réseau vulnérables ont été désactivés.

### Boîte à outils — Checklist de durcissement d'un poste Windows 11 (modèle GPO)

Modèle de référence pour le déploiement de 50 postes en entreprise (à adapter — c'est la logique qui compte : chaque règle répond à un risque identifié) :

| N° | Règle de durcissement technique | Risque de sécurité mitigé (si non appliquée) |
|---|---|---|
| **1** | Désactiver les ports USB pour le stockage de masse externe | Atténue l'introduction accidentelle ou volontaire de malwares via des clés USB infectées (le *baiting* de B04), et évite la fuite de données par copie physique non autorisée. |
| **2** | Activer BitLocker avec authentification au démarrage | Protège contre le vol physique : sans chiffrement, un voleur lit tout le disque en le branchant sur une autre machine, sans connaître le mot de passe Windows. |
| **3** | Configurer le pare-feu Windows en mode restrictif | Bloque les connexions entrantes non sollicitées de pirates ou de vers se propageant sur le réseau local, notamment sur un Wi-Fi public. |
| **4** | Imposer le verrouillage automatique de session après 5 min d'inactivité | Empêche une personne de passage d'accéder aux données ou d'agir sous l'identité de l'employé qui s'éloigne sans verrouiller. |
| **5** | Interdire le fonctionnement quotidien avec des privilèges administrateur | Limite la portée d'une infection : le malware s'exécute avec des droits limités et ne peut ni s'installer en profondeur ni modifier le système. |

### Panorama des solutions du marché (Commerciales & Open-Source)

Le durcissement des systèmes d'exploitation et la protection des endpoints nécessitent des solutions EDR comportementales :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **CrowdStrike Falcon** : Référence des EDR cloud-natifs pour surveiller l'activité des endpoints et stopper les attaques "sans fichier" en temps réel.
    *   **SentinelOne Singularity** : Solution EDR/XDR utilisant l'intelligence artificielle pour bloquer les comportements suspects de manière autonome sur l'appareil.
    *   **Microsoft Defender for Endpoint** : Solution EPP/EDR nativement intégrée dans l'écosystème Windows, simplifiant le déploiement et l'administration.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **Wazuh** : Plateforme XDR open-source intégrant détection d'intrusions sur l'hôte, vérification des fichiers critiques (FIM) et détection des configurations non conformes.
    *   **OpenSCAP** : Outil open-source d'analyse de conformité vérifiant automatiquement qu'un système respecte les guides de durcissement officiels (CIS, ANSSI).
    *   **OSSEC** : Système open-source de détection d'intrusions basé sur l'hôte effectuant l'analyse de logs et le contrôle d'intégrité.

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après le sondage d'opinion n°5.

*   **📊 Sondage n°6 :** Lors du durcissement d'un serveur, que faire d'un service installé par défaut mais inutile pour son rôle (ex. le service d'impression sur un serveur de bases de données) ?
    *   A) Le laisser : il pourrait servir un jour
    *   B) Le désactiver : tout service actif est une surface d'attaque supplémentaire ✅
    *   C) Le mettre à jour, puis l'oublier
*   **📊 Sondage n°7 :** Qu'est-ce qui distingue fondamentalement un EDR d'un antivirus traditionnel ?
    *   A) L'EDR analyse les comportements des processus (et peut isoler la machine) ; l'antivirus compare des signatures de fichiers connus ✅
    *   B) L'EDR est gratuit, l'antivirus est payant
    *   C) L'EDR ne fonctionne que sur les serveurs
*   **📊 Sondage n°8 :** Contre quel scénario le chiffrement du disque (BitLocker/LUKS) protège-t-il principalement ?
    *   A) Les e-mails d'hameçonnage
    *   B) Les attaques par déni de service
    *   C) Le vol physique de la machine : le disque est illisible sur un autre ordinateur ✅

**Éléments de débriefing (pour le mentor) :**

- N°6 : « il pourrait servir un jour » est l'ennemi du durcissement — chaque service actif est une porte de plus à surveiller. On active à la demande, on ne désactive pas à l'incident.
- N°7 : signatures = photos de cambrioleurs connus ; comportement = capteurs de mouvement. Face au zero-day, au polymorphe et au *fileless*, seule la seconde approche voit quelque chose.
- N°8 : le chiffrement au repos répond au scénario du portable volé dans le train — sans lui, le mot de passe Windows ne protège rien (le disque se lit ailleurs).

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"System Hardening and Patch Management"* (durée estimée : 1h30).
*   **Ressource complémentaire** : Visiter le site de l'ANSSI (cyber.gouv.fr) et consulter le "Guide de configuration d'un système Windows" ou les recommandations de durcissement Linux pour observer le niveau d'exigence technique requis en milieu professionnel.
*   [ANSSI — Déploiement client Windows](https://cyber.gouv.fr)
*   [Cybermalveillance — Mises à jour](https://www.cybermalveillance.gouv.fr/tous-nos-contenus/bonnes-pratiques/mises-a-jour)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Choix des stratégies de restriction des privilèges.
*   **📊 Sondage Livestorm n°9 :** Pour empêcher un malware de s'installer ou de modifier des fichiers système critiques sur les postes utilisateurs, quelle est la règle d'hygiène la plus simple à appliquer ?
    *   A) Installer deux antivirus différents.
    *   B) Retirer les privilèges d'administrateur local aux utilisateurs standards ✅
    *   C) Modifier les mots de passe tous les 5 jours.
*   **Guide d'animation (pour le mentor) :** Sans privilèges d'administrateur, la majorité des malwares ne peuvent ni modifier le système ni s'installer en profondeur — la mesure au meilleur rapport coût/efficacité du poste de travail. (A est un mythe : deux antivirus se neutralisent souvent ; C épuise les utilisateurs sans bénéfice équivalent.) Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Chiffrement au repos** | BitLocker/LUKS : le disque volé est illisible sur une autre machine. |
| **CIS Benchmarks / guides ANSSI** | Les référentiels publics du durcissement, déployés en masse via GPO. |
| **Durcissement (Hardening)** | Réduire la surface d'attaque : services désactivés, correctifs à jour, politiques verrouillées, disque chiffré, pare-feu local. |
| **EDR** | Surveillance comportementale du poste : détecte l'inconnu, bloque, isole la machine — la boîte noire du SOC. |
| **GPO** | Le bras armé d'Active Directory pour déployer les politiques de sécurité sur tout un parc Windows. |
| **Moindre privilège** | Le strict nécessaire, y compris dans le temps : un compte dormant est une porte sans gardien (Colonial Pipeline). |
| **Patch Management** | Le déploiement systématique des correctifs — en jours pour les failles critiques. |
| **UAC / sudo** | L'élévation temporaire et tracée des droits, à la demande. |

**La règle d'or de la session :** un poste durci transforme l'intrusion en impasse — comptes limités et révisés, services justifiés, disque chiffré, correctifs rapides, EDR aux aguets. Et souvenez-vous de Colonial Pipeline : le ménage non fait (un compte dormant, pas de MFA) a arrêté un oléoduc de 9 000 km.
