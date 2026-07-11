# Support de cours — Session 01 : Découverte de la cybersécurité & paysage des menaces
Parcours : A 8 sessions  |  Module : Fondements Cyber  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - La Triade CIA : La boussole de la cybersécurité
    - Le triptyque : Vulnérabilité, Menace, Risque
    - Offense vs Défense : Deux facettes d'une même pièce
    - Qui sont les attaquants modernes ?
    - Le paysage de la menace en chiffres (sources officielles récentes)
    - Deux études de cas réelles : l'hôpital de Corbeil-Essonnes et France Travail
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

Bienvenue dans le monde de la cybersécurité. À l'ère numérique, la protection des informations est devenue une priorité absolue pour les individus, les entreprises et les gouvernements. Ce support pose les bases indispensables de la discipline. Vous y découvrirez la triade "CIA" (Confidentialité, Intégrité, Disponibilité), le modèle conceptuel de base pour évaluer la sécurité de tout système d'information. Nous étudierons également les différences fondamentales entre l'approche offensive (comprendre comment attaquent les pirates) et défensive (sécuriser les infrastructures), avant de cartographier les profils d'attaquants modernes et leurs motivations réelles, souvent bien éloignées des clichés du cinéma. Enfin, nous ancrerons ces concepts dans la réalité grâce à des chiffres officiels récents et à deux affaires françaises majeures. Ce module constitue votre porte d'entrée vers une posture de vigilance active.

### Objectifs de la session

À l'issue de cette session, vous serez capable de :

- **Définir** les trois piliers de la triade CIA (Confidentialité, Intégrité, Disponibilité) et les reconnaître dans des incidents réels.
- **Distinguer** vulnérabilité, menace et risque, et expliquer la posture offensive par rapport à la posture défensive.
- **Identifier** les quatre profils d'attaquants majeurs (cybercriminels, États-nations, hacktivistes, menaces internes) et leurs motivations.
- **Expliquer** les conséquences concrètes d'une cyberattaque pour une organisation (financières, opérationnelles, légales, réputationnelles), chiffres et cas réels à l'appui.

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** À votre avis, dans quelle proportion des violations de données le facteur humain (erreur, manipulation, mot de passe volé) est-il impliqué ?

    - A) Environ 10 %
    - B) Environ 30 %
    - C) Environ 60 % ✅
    - D) Environ 90 %

    **Débrief mentor :** Selon le rapport *Data Breach Investigations Report* 2025 de Verizon, le facteur humain est impliqué dans environ 60 % des violations de données. Message clé de tout le parcours : la cybersécurité n'est pas qu'une affaire de technique, c'est d'abord une affaire de personnes — donc de chacun d'entre vous.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Évolution historique du paysage des menaces**
Prenez le temps d'expliquer comment nous sommes passés de virus informatiques créés par des passionnés (années 90) cherchant la notoriété, à une véritable industrie du cybercrime (Ransomware-as-a-Service, courtiers en accès initiaux). Détaillez la notion d'économie souterraine : les attaquants achètent des vulnérabilités et des accès sur le Dark Web comme on achète un service légal, avec catalogues, support client et programmes d'affiliation. Le groupe LockBit, démantelé partiellement en février 2024 par l'opération internationale « Cronos », fonctionnait exactement comme une franchise commerciale.

**2. La Triade CIA dans le détail**
- **Confidentialité** : Évoquez l'importance des contrôles d'accès physiques (badges) et logiques (chiffrement AES-256).
- **Intégrité** : Expliquez comment le hachage (SHA-256) permet de garantir qu'une donnée n'a pas été altérée par un "Man-in-the-Middle".
- **Disponibilité** : Abordez les plans de reprise d'activité (PRA), le rôle des clusters de serveurs, et l'impact d'une attaque DDoS sur les serveurs DNS.

**3. Contexte réglementaire (à mentionner sans approfondir — traité en session A5)**
La directive européenne **NIS 2**, en cours de déploiement en France, étend les obligations de cybersécurité à des dizaines de milliers d'entités (collectivités, PME de secteurs critiques). C'est un argument fort pour répondre à la question « pourquoi suis-je concerné ? » : la sécurité n'est plus optionnelle, y compris pour les petites structures.

**4. Discussion via le chat (à doser selon le temps)**
Demandez aux apprenants d'identifier l'actif le plus critique de leur entreprise actuelle ou passée, et de classer les impacts redoutés (perte de chiffre d'affaires vs perte de réputation). En grand groupe, faites-le via le chat et lisez 3 à 4 réponses à voix haute.

---

### Glossaire

*   **AES-256** — Standard de chiffrement symétrique hautement sécurisé utilisant des clés de 256 bits, considéré comme inviolable par la force brute actuelle.
*   **APT (Advanced Persistent Threat / Menace persistante avancée)** — Groupe d'attaquants disposant de moyens importants (souvent lié à un État), capable de s'introduire discrètement dans un système et d'y rester des mois pour espionner ou saboter.
*   **Confidentialité** — Garantie que seules les personnes autorisées ont accès aux données.
*   **DDoS (Distributed Denial of Service)** — Attaque par déni de service distribué visant à rendre un serveur ou un réseau indisponible en le submergeant de requêtes provenant de multiples sources.
*   **Défense en profondeur** — Stratégie consistant à superposer plusieurs couches de protection indépendantes, afin qu'une défaillance isolée ne suffise jamais à compromettre le système.
*   **Disponibilité** — Garantie que les données et les systèmes sont accessibles par les utilisateurs autorisés au moment où ils en ont besoin.
*   **Hameçonnage (Phishing)** — Technique consistant à usurper l'identité d'un tiers de confiance (banque, administration, collègue) pour pousser la victime à divulguer des informations ou à exécuter une action malveillante.
*   **Intégrité** — Garantie que les données ne sont pas modifiées, altérées ou supprimées de manière accidentelle ou malveillante.
*   **Menace** — Un événement ou une entité externe ayant le potentiel d'exploiter une vulnérabilité et de causer des dommages.
*   **OSINT (Open Source Intelligence)** — Renseignement d'origine « sources ouvertes » : collecte d'informations librement accessibles (sites web, réseaux sociaux, registres publics) utilisée par les attaquants comme par les défenseurs.
*   **RaaS (Ransomware-as-a-Service)** — Modèle économique cybercriminel où des développeurs vendent ou louent des rançongiciels à des affiliés qui exécutent les attaques.
*   **Rançongiciel (Ransomware)** — Logiciel malveillant qui chiffre les données d'une victime puis exige une rançon en échange de la clé de déchiffrement, souvent doublée d'une menace de publication des données volées (double extorsion).
*   **Risque** — La probabilité qu'une menace exploite une vulnérabilité et provoque un impact négatif (Risque = Menace × Vulnérabilité × Impact).
*   **SHA-256** — Algorithme de hachage cryptographique produisant une empreinte numérique unique de 256 bits pour vérifier l'intégrité d'une donnée.
*   **Surface d'exposition (ou surface d'attaque)** — Ensemble des points d'entrée d'une organisation visibles et accessibles depuis Internet, qu'un attaquant peut étudier puis exploiter.
*   **Sécurité défensive** — Ensemble des mesures de protection, de surveillance et de réaction déployées pour sécuriser un système (ex. gestion des pare-feux, surveillance SOC, réponse sur incident).
*   **Sécurité offensive** — Approche proactive consistant à tester les défenses en simulant des attaques réelles (ex. pentesting, red teaming).
*   **Triade CIA (Confidentialité, Intégrité, Disponibilité)** — Le modèle de référence de la sécurité de l'information. Chaque action de sécurité vise à garantir l'un ou plusieurs de ces piliers.
*   **Vulnérabilité** — Une faiblesse ou une faille présente dans un système, un logiciel, une procédure ou un comportement humain, susceptible d'être exploitée.

---

### 1. La Triade CIA : La boussole de la cybersécurité

!!! info "À retenir"
    Face à n'importe quel incident de sécurité, posez-vous toujours la même question : *quel pilier de la triade est touché ?* C'est le réflexe d'analyse numéro un du professionnel de la cybersécurité.

Toute stratégie de cybersécurité s'appuie sur trois piliers fondamentaux. Comprendre ces concepts permet de classifier les incidents et de concevoir des mesures de protection appropriées.

#### A. Confidentialité (*Confidentiality*)
La confidentialité consiste à s'assurer que l'information n'est divulguée qu'aux personnes ou processus autorisés. Si un pirate accède à votre boîte de messagerie ou si un employé consulte le dossier médical d'un patient sans autorisation, la confidentialité est compromise.

* *Mécanismes de protection* : Le chiffrement des données (rendre la lecture impossible sans clé de déchiffrement), les contrôles d'accès logiques (mots de passe, biométrie) et la classification des informations.
* *Exemple parlant* : une carte postale peut être lue par tous les intermédiaires ; une lettre cachetée, non. Le chiffrement transforme vos données numériques de « carte postale » en « lettre cachetée ».

#### B. Intégrité (*Integrity*)
L'intégrité garantit que l'information reste fiable, exacte et complète. Si un pirate intercepte un virement bancaire et remplace le RIB du destinataire par le sien, ou si un virus altère le code d'un logiciel médical pour fausser les doses administrées, c'est l'intégrité qui est impactée.

* *Mécanismes de protection* : Les signatures numériques, les fonctions de hachage (empreintes numériques uniques permettant de vérifier qu'un fichier n'a pas été modifié) et les historiques d'audit non modifiables.
* *Exemple parlant* : le cachet de cire sur une lettre ancienne ne rendait pas la lettre illisible, mais prouvait qu'elle n'avait pas été ouverte ni modifiée en chemin. C'est exactement le rôle d'une empreinte SHA-256.

#### C. Disponibilité (*Availability*)
La disponibilité assure que les systèmes informatiques, les réseaux et les données sont accessibles en temps voulu par les utilisateurs autorisés. Si une attaque par déni de service (DoS) sature le site e-commerce d'une enseigne commerciale durant les soldes, ou si un rançongiciel (ransomware) bloque l'accès aux ordinateurs d'une clinique, la disponibilité est rompue.

* *Mécanismes de protection* : La redondance des infrastructures (serveurs de secours), les sauvegardes régulières, et la maintenance préventive du matériel.
* *Exemple parlant* : une bibliothèque dont tous les livres seraient intacts et confidentiels, mais dont les portes resteraient fermées aux lecteurs, ne servirait à rien. Une donnée inaccessible perd sa valeur, même intacte.

!!! question "💬 Question chat — À vous de jouer"
    Pensez à votre métier ou à votre quotidien : laquelle des trois lettres — **C**, **I** ou **D** — serait la plus grave à perdre pour vous ? Tapez la lettre dans le chat, en précisant votre contexte si vous le souhaitez (ex. « D — je travaille en logistique »). Le mentor lira quelques réponses et montrera que la réponse dépend du métier : un hôpital privilégie la disponibilité, une banque l'intégrité, un cabinet d'avocats la confidentialité.

### Exercice d'application — Le Détective CIA (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Lancez les trois sondages suivants l'un après l'autre sur Livestorm. Après chaque sondage, affichez les résultats et déroulez le débrief avant de passer au suivant. C'est l'activité phare de la première moitié de session : prenez le temps de commenter.

*   **📊 Sondage n°2 :** Un rançongiciel chiffre la base de données comptable d'une entreprise. Quel pilier de la triade CIA est principalement rompu ?
    *   A) Confidentialité
    *   B) Intégrité
    *   C) Disponibilité ✅
    *   D) Non-répudiation
*   **📊 Sondage n°3 :** Un attaquant intercepte des e-mails RH contenant des fiches de paie sans les modifier. Quel pilier est violé ?
    *   A) Confidentialité ✅
    *   B) Intégrité
    *   C) Disponibilité
    *   D) Authenticité
*   **📊 Sondage n°4 :** Un administrateur modifie par erreur un droit d'accès, permettant à n'importe quel employé de modifier les données de vente. Quel pilier est compromis ?
    *   A) Confidentialité
    *   B) Intégrité ✅
    *   C) Disponibilité
    *   D) Résilience

**Éléments de débriefing (pour le mentor) :**

- Le chiffrement par rançongiciel bloque l'accès aux données : c'est la **Disponibilité** qui tombe en premier (et souvent la Confidentialité ensuite, si les données sont aussi volées — c'est la « double extorsion »).
- L'interception d'e-mails RH viole le secret des informations (**Confidentialité**), même sans aucune modification.
- La modification non autorisée ou accidentelle des ventes fausse la fiabilité des données (**Intégrité**) — notez qu'aucun « pirate » n'est nécessaire : l'erreur humaine suffit.
- Piège pédagogique : les distracteurs « Non-répudiation », « Authenticité » et « Résilience » sont de vrais concepts de sécurité, mais ne font pas partie de la triade. Les nommer permet d'élargir le vocabulaire.

### 2. Le triptyque : Vulnérabilité, Menace, Risque

En sécurité, ces trois termes ont des sens bien distincts qu'il convient de ne pas confondre :

* La **vulnérabilité** est la porte ouverte (ex. un logiciel non mis à jour ou un mot de passe trop simple).
* La **menace** est le cambrioleur (ex. un groupe de cybercriminels qui cherche à voler des données).
* Le **risque** est la probabilité que le cambrioleur trouve la porte ouverte et s'introduise dans la maison pour dérober des biens (l'impact).

Sécuriser un système consiste à réduire les vulnérabilités pour minimiser la probabilité de réalisation du risque. On ne peut pas supprimer les menaces (les cambrioleurs existeront toujours), mais on peut fermer les portes.

**Exemple chiffré pour fixer les idées.** Prenons la formule *Risque = Menace × Vulnérabilité × Impact* appliquée à deux cas :

| Situation | Menace | Vulnérabilité | Impact | Niveau de risque |
| :--- | :--- | :--- | :--- | :--- |
| Serveur de paie accessible sur Internet avec un mot de passe faible | Élevée (les cybercriminels scannent Internet en permanence) | Élevée (mot de passe devinable, pas de MFA) | Élevé (salaires bloqués, données personnelles volées) | **Critique** |
| Vieil ordinateur de la salle de pause, sans données, isolé du réseau | Élevée (les mêmes attaquants existent) | Élevée (système obsolète) | Quasi nul (aucune donnée, aucun accès) | **Faible** |

La leçon : la même vulnérabilité ne produit pas le même risque selon l'impact. C'est pour cela que toute démarche de sécurité commence par la question « qu'est-ce qui est critique pour moi ? » — exactement comme une assurance habitation évalue d'abord la valeur de ce qu'elle couvre.

### 3. Offense vs Défense : Deux facettes d'une même pièce

* **La Sécurité Offensive (Offense)** cherche à penser comme l'attaquant. Elle utilise des méthodes de tests d'intrusion pour découvrir les failles avant qu'elles ne soient exploitées par des cybercriminels. Elle est indispensable pour valider la robustesse réelle des systèmes.
* **La Sécurité Défensive (Défense)** englobe toutes les mesures passives et actives de protection. Elle installe les barrières (antivirus, pare-feux), surveille les accès en continu et met en œuvre les processus de réaction et de reconstruction. Elle représente le travail quotidien de sécurisation.

Dans le vocabulaire du métier, on parle de **Red Team** (l'équipe rouge, qui attaque de manière contrôlée et autorisée) et de **Blue Team** (l'équipe bleue, qui défend). Les exercices où les deux collaborent et partagent leurs enseignements en temps réel sont appelés **Purple Team**. Retenez surtout ceci : un test d'intrusion n'est légal que s'il est **explicitement autorisé par écrit** par le propriétaire du système — sans autorisation, les mêmes gestes constituent un délit (articles 323-1 et suivants du Code pénal français).

### 4. Qui sont les attaquants modernes ?

Le cliché de l'adolescent isolé piratant la NASA depuis sa chambre est obsolète. Aujourd'hui, les acteurs de menaces sont structurés :

1. **Les Cybercriminels** : Motivés par l'appât du gain financier (ransomware, vol de données bancaires, revente d'informations). Ils opèrent en bandes organisées, avec une véritable logique d'entreprise : les groupes de rançongiciel comme **LockBit** ou **Conti** ont fonctionné avec des « franchisés » (modèle RaaS), des négociateurs et même un « support client » pour guider les victimes dans le paiement. C'est la menace la plus probable pour la quasi-totalité des organisations.
2. **Les États-Nations** : Motivés par l'espionnage industriel, l'influence géopolitique, le sabotage d'infrastructures critiques ou le vol d'informations stratégiques. Ils disposent de ressources financières et techniques quasi illimitées et opèrent dans la durée : on parle de **menaces persistantes avancées (APT)**, capables de rester tapies des mois dans un réseau avant d'agir.
3. **Les Hacktivistes** : Motivés par des revendications idéologiques, politiques ou écologiques. Ils cherchent à défigurer des sites web (*defacement*) ou à bloquer l'accès à des services (attaques DDoS) pour faire entendre leur voix — des collectifs comme Anonymous en sont l'exemple le plus connu. L'impact est souvent plus médiatique que technique, mais la gêne opérationnelle est réelle.
4. **Les Menaces Internes** : Employés mécontents, collaborateurs négligents ou prestataires indélicats. Ils possèdent déjà des accès légitimes au réseau, ce qui les rend particulièrement difficiles à détecter. Attention : la menace interne n'est pas toujours malveillante — le collaborateur pressé qui clique sur une pièce jointe piégée ou qui envoie un fichier au mauvais destinataire en fait aussi partie.

!!! tip "📊 Sondage Livestorm n°5 — Votre perception (sondage d'opinion, pas de bonne réponse)"
    **Question :** Quel profil d'attaquant représente, selon vous, la menace n°1 pour VOTRE organisation ?

    - A) Les cybercriminels
    - B) Les États-nations
    - C) Les hacktivistes
    - D) La menace interne

    **Débrief mentor :** Il n'y a pas de bonne réponse universelle — c'est tout l'intérêt. Statistiquement, les cybercriminels opportunistes sont la menace la plus probable pour la majorité des organisations (ils attaquent ce qui est mal fermé, pas ce qui est prestigieux). Mais la menace interne est presque toujours sous-estimée dans ce sondage : soulignez-le si les résultats le confirment.

### 5. Le paysage de la menace en chiffres

Pour dépasser les impressions et ancrer la discussion dans les faits, voici quelques repères issus de sources officielles et de rapports de référence. Retenez les ordres de grandeur plus que les valeurs exactes : ils suffisent à comprendre pourquoi la cybersécurité est devenue un enjeu de direction générale, et plus seulement un sujet de service informatique.

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **Le facteur humain est impliqué dans environ 60 % des violations de données** : erreur, hameçonnage, identifiants volés (Verizon, *Data Breach Investigations Report*, 2025).
    - **L'ANSSI a traité près de 4 400 événements de sécurité en 2024**, en hausse d'environ 15 % sur un an ; les TPE/PME/ETI et les collectivités territoriales restent les premières victimes des attaques par rançongiciel (ANSSI, *Panorama de la cybermenace 2024*).
    - **L'hameçonnage demeure la menace n°1** en volume pour les particuliers comme pour les entreprises françaises, selon la plateforme nationale d'assistance Cybermalveillance.gouv.fr (rapport d'activité 2024), qui reçoit chaque année des centaines de milliers de demandes d'aide.
    - **Les violations de données notifiées à la CNIL ont atteint un niveau record en 2024** (plus de 5 000 notifications, en forte hausse sur un an), portées par plusieurs fuites de très grande ampleur (CNIL, bilan 2024).
    - **Une violation de données coûte en moyenne environ 4,4 millions de dollars** dans le monde, et plusieurs mois s'écoulent en moyenne entre l'intrusion initiale et son confinement complet (IBM, *Cost of a Data Breach Report*, 2025).

**Comment lire ces chiffres ?** Trois messages s'en dégagent : (1) l'attaque n'est pas un événement rare qui n'arrive qu'aux autres — c'est un flux continu et industrialisé ; (2) les petites structures sont des cibles privilégiées, précisément parce qu'elles se croient trop petites pour intéresser les attaquants ; (3) l'humain est à la fois le premier vecteur d'attaque et la première ligne de défense — d'où l'importance de la sensibilisation que vous suivez en ce moment même.

### 6. Deux études de cas réelles (France)

#### Cas n°1 — L'hôpital de Corbeil-Essonnes : quand la Disponibilité s'effondre

Dans la nuit du 20 au 21 août 2022, le Centre Hospitalier Sud Francilien (CHSF) de Corbeil-Essonnes, qui dessert un bassin de plusieurs centaines de milliers d'habitants, est frappé par le rançongiciel **LockBit**. Les systèmes sont chiffrés : plus d'accès aux dossiers patients informatisés, aux résultats de laboratoire, à l'imagerie médicale. L'hôpital bascule en « mode dégradé » : retour au papier et au stylo, transfert des patients les plus critiques vers d'autres établissements, déprogrammation d'interventions. Les attaquants exigent une rançon de 10 millions de dollars. Conformément à la doctrine française (les établissements publics ne paient pas, pour ne pas alimenter l'écosystème criminel), l'hôpital refuse. En représailles, les attaquants publient environ 11 Go de données volées, incluant des données de patients et de personnels : la violation de **Disponibilité** se double alors d'une violation de **Confidentialité**. Le retour à un fonctionnement normal a demandé des mois, pour un coût de remédiation de plusieurs millions d'euros — très supérieur au budget annuel de sécurité informatique de l'établissement à l'époque.

**Ce que ce cas illustre :** la triade CIA en action (D puis C), la double extorsion, le coût réel d'une attaque (bien au-delà de la rançon), et une idée reçue qui tombe : « les pirates ne s'attaquent pas aux hôpitaux ». Si : ce qui compte pour un cybercriminel, c'est la criticité de la cible — donc sa propension à payer vite.

#### Cas n°2 — France Travail : la Confidentialité à l'échelle nationale

En mars 2024, France Travail (ex-Pôle emploi) révèle une intrusion majeure : des attaquants, ayant usurpé des comptes d'agents partenaires, ont pu exfiltrer des données personnelles concernant potentiellement **43 millions de personnes** — l'une des plus importantes fuites de données jamais enregistrées en France. Les données concernées : identité, date de naissance, numéro de sécurité sociale, coordonnées. Ni mots de passe, ni coordonnées bancaires — et pourtant le danger est considérable : ces informations permettent de fabriquer des campagnes d'hameçonnage ultra-crédibles (« Bonjour Mme X, votre dossier n° Y nécessite une mise à jour... ») et des tentatives d'usurpation d'identité pendant des années. La CNIL a immédiatement rappelé aux personnes concernées de redoubler de vigilance face aux messages se réclamant de France Travail. La même année, les opérateurs de tiers payant Viamedis et Almerys avaient déjà été victimes d'une fuite touchant environ 33 millions d'assurés — 2024 restera comme une année charnière pour la prise de conscience française.

**Ce que ce cas illustre :** une violation de **Confidentialité** pure (aucun système bloqué, aucun fichier modifié), le rôle des accès de partenaires comme maillon faible, et l'effet domino : les données volées aujourd'hui alimentent les attaques de demain.

!!! question "💬 Question chat — Transition vers la session A2"
    Vous recevez demain un e-mail de « France Travail » vous demandant de confirmer vos coordonnées bancaires pour « maintenir vos droits ». **Citez dans le chat un indice que vous vérifieriez avant de cliquer.** Le mentor relèvera les bonnes intuitions (adresse de l'expéditeur, lien survolé sans cliquer, ton alarmiste, demande inhabituelle — France Travail ne demande jamais de coordonnées bancaires par e-mail) : c'est exactement le programme de la session A2 sur l'ingénierie sociale.

!!! info "Pour situer à l'international : deux attaques qui ont marqué l'histoire"
    - **WannaCry (mai 2017)** : ce rançongiciel s'est propagé automatiquement à des centaines de milliers de machines dans environ 150 pays en quelques jours, en exploitant une faille Windows... pour laquelle un correctif existait depuis deux mois. Le service de santé britannique (NHS) a dû annuler des milliers de rendez-vous et d'opérations. Leçon : appliquer les mises à jour n'est pas de la bureaucratie, c'est un geste vital.
    - **NotPetya (juin 2017)** : déguisé en rançongiciel, ce logiciel était en réalité un outil de **sabotage** (les données étaient détruites, pas récupérables). Diffusé via la mise à jour piégée d'un logiciel comptable ukrainien, il a paralysé des multinationales entières : le transporteur Maersk a chiffré ses pertes à environ 300 millions de dollars, le français Saint-Gobain à environ 250 millions d'euros. Les dégâts mondiaux ont été estimés à près de 10 milliards de dollars. Leçon : votre sécurité dépend aussi de celle de vos fournisseurs (attaque dite « de chaîne d'approvisionnement »).

---

### Focus pratique : la surface d'exposition numérique

Pour comprendre comment un attaquant initie ses recherches, on étudie la **surface d'exposition numérique**. Il s'agit de l'ensemble des points d'entrée d'une organisation qui sont visibles et accessibles depuis Internet. L'attaquant procède comme un cambrioleur qui fait le tour du pâté de maisons : il observe (souvent avec de simples recherches OSINT, parfaitement légales), il note les portes et fenêtres, puis il choisit la plus mal fermée.

| Élément de la surface d'exposition | Risque associé | Mesure d'hygiène de base |
| :--- | :--- | :--- |
| **Noms de domaine et serveurs DNS** | Usurpation de nom de domaine, redirection frauduleuse. | Verrouillage des registres, protocoles DNSSEC. |
| **Serveurs web & applications cloud** | Exploitation de failles logicielles non patchées. | Scans réguliers, application stricte des mises à jour. |
| **Ports de connexion ouverts (ex. RDP, SSH)** | Attaques par force brute sur les identifiants d'accès. | Limitation des accès par VPN, filtrage IP, MFA obligatoire. |
| **Employés sur les réseaux sociaux** | Collecte d'informations d'ingénierie sociale (phishing ciblé). | Sensibilisation aux données partagées publiquement. |

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Vous découvrez que le serveur de votre PME expose un accès de bureau à distance (RDP) ouvert à tout Internet, protégé par le mot de passe `Admin2024`. Trois options s'offrent à vous — **votez mentalement, puis défendez votre choix dans le chat** :

    - A) Ce n'est pas mon rôle, je ne dis rien.
    - B) Je préviens immédiatement le responsable informatique ou la direction.
    - C) Je teste moi-même le mot de passe « pour vérifier ».

    **Débrief mentor :** B, évidemment — mais insistez sur pourquoi C est une très mauvaise idée : tester un accès sans autorisation écrite est illégal, même avec de bonnes intentions. La bonne posture du citoyen numérique : signaler, jamais exploiter. Quant à A, rappelez le chiffre du sondage n°1 : la sécurité est l'affaire de tous.

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Pour bien comprendre la cybersécurité, imaginez l'analogie d'un **château fort médiéval** :
    - **Les Douves et le Pont-levis** agissent comme le pare-feu : ils filtrent les accès et n'autorisent le passage que par une seule entrée surveillée.
    - **Les Gardes à l'intérieur de la cour** sont l'Antivirus/EDR : s'il y a un intrus ou une bagarre dans la cour, ils interviennent immédiatement.
    - **La Salle du trésor (donjon)** représente les données sensibles. Elle nécessite plusieurs clés et l'accord de plusieurs officiers (Authentification Multifacteur - MFA).
    - **Les Espions et éclaireurs** représentent la sécurité offensive : ils étudient les faiblesses des murs du château pour les réparer avant qu'une armée ennemie ne les attaque.

    Cette superposition de protections indépendantes porte un nom : la **défense en profondeur**. Aucune muraille n'est infranchissable ; l'objectif est qu'aucune brèche isolée ne suffise à atteindre le trésor.

**Exemple d'application professionnelle :**
Dans un cabinet de conseil financier, un consultant perd son ordinateur portable dans le train. Grâce à la *défense en profondeur*, le disque dur de la machine est chiffré en AES-256 (Confidentialité préservée), les comptes d'accès sont désactivés à distance (Disponibilité contrôlée), et aucun attaquant ne peut usurper son identité car le MFA est requis pour se connecter au réseau de l'entreprise. Chaque couche de sécurité a joué son rôle pour éviter la catastrophe. Comparez avec le CHSF : un hôpital, des couches de défense moins nombreuses, et un incident qui devient une crise nationale — c'est toute la différence que fait l'anticipation.

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour mettre en œuvre une stratégie globale de défense en profondeur et anticiper les menaces actuelles, plusieurs solutions coexistent sur le marché :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Microsoft Defender for Endpoint (et Suite Defender/Entra)** : Leader du Magic Quadrant de Gartner pour la protection des endpoints (EPP/EDR) et des identités, particulièrement intégré pour les environnements Windows.
    *   **CrowdStrike Falcon** : Référence du marché des EDR/XDR cloud-natifs, reconnu pour ses capacités de détection des menaces avancées et sa Threat Intelligence intégrée.
    *   **SentinelOne Singularity** : Solution EDR/XDR utilisant l'intelligence artificielle comportementale sur l'agent pour bloquer et restaurer les systèmes en cas d'attaque par ransomware.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **Wazuh** : Plateforme open-source complète d'XDR et de supervision de sécurité. Elle assure la détection des intrusions, la surveillance de l'intégrité des fichiers, l'évaluation de la configuration et la réponse active.
    *   **ClamAV** : Moteur antivirus open-source standard, principalement utilisé sur les serveurs de fichiers et serveurs de messagerie Linux pour détecter les malwares.
    *   **Greenbone Community Edition (OpenVAS)** : Scanner de vulnérabilités open-source réputé pour identifier les failles de sécurité actives sur un réseau d'entreprise.

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après la démonstration OSINT. Ces trois questions valident les acquis au-delà de la triade (déjà testée par le Détective CIA).

*   **📊 Sondage n°6 :** Un serveur qui n'a pas été mis à jour depuis deux ans, c'est... ?
    *   A) Une menace
    *   B) Une vulnérabilité ✅
    *   C) Un risque
    *   D) Une attaque
*   **📊 Sondage n°7 :** Un collectif bloque le site web d'un ministère pour protester contre une loi. Quelle est sa motivation principale ?
    *   A) Financière
    *   B) Géopolitique
    *   C) Idéologique ✅
    *   D) La négligence
*   **📊 Sondage n°8 :** Le test d'intrusion (pentest) relève de... ?
    *   A) La sécurité offensive ✅
    *   B) La sécurité défensive
    *   C) La conformité réglementaire
    *   D) L'investigation numérique (forensics)

**Éléments de débriefing (pour le mentor) :**

- N°6 : le serveur obsolète est la *porte ouverte* (vulnérabilité). La menace, c'est l'attaquant qui rôde ; le risque, c'est la combinaison des deux avec l'impact. Reprenez la formule Risque = Menace × Vulnérabilité × Impact.
- N°7 : motivation idéologique = hacktivisme. Rappel : l'argent → cybercriminels ; l'espionnage/le sabotage → États ; la négligence → menace interne involontaire.
- N°8 : le pentest simule l'attaque pour tester la défense — sécurité offensive, toujours avec une autorisation écrite préalable.

### Questions de réflexion

1. Votre organisation (ou une organisation que vous connaissez bien) devait-elle plutôt craindre une atteinte à la Confidentialité, à l'Intégrité ou à la Disponibilité ? Qu'est-ce qui changerait dans ses priorités de protection ?
2. Pourquoi dit-on que « l'on ne peut pas supprimer les menaces, seulement réduire les vulnérabilités » ? Trouvez un contre-exemple apparent et discutez-le.
3. Le CHSF a refusé de payer la rançon, conformément à la doctrine française. Quels sont les arguments pour et contre le paiement d'une rançon, du point de vue d'un dirigeant ? Et du point de vue de la société tout entière ?
4. Après la fuite France Travail, quelles précautions concrètes une personne concernée devrait-elle prendre, sachant que ses données circuleront pendant des années ?

## 3. Ressources complémentaires

* **IBM SkillsBuild** : Cours "Introduction to Cybersecurity" pour approfondir l'histoire et les fondamentaux.
* **ANSSI — [Panorama de la cybermenace](https://cyber.gouv.fr)** : le rapport annuel de référence sur l'état de la menace en France (synthèse lisible par des non-spécialistes).
* **[Cybermalveillance.gouv.fr](https://www.cybermalveillance.gouv.fr)** : la plateforme nationale d'assistance aux victimes ; consultez son rapport d'activité annuel et ses fiches réflexes.
* **[CNIL — Violations de données personnelles](https://www.cnil.fr)** : bilans annuels des notifications de violations et conseils aux personnes concernées.
* **NIST SP 800-12** : Guide d'introduction à la sécurité de l'information pour comprendre le cycle de protection.

## 4. Exercice bonus (Dilemme Décisionnel - Livestorm)

*   **Objectif :** Analyse d'impact rapide et priorisation, en écho direct au cas réel du CHSF étudié plus haut.
*   **📊 Sondage Livestorm n°9 :** Une attaque par rançongiciel cible un hôpital. Les dossiers médicaux sont inaccessibles. Quelle est la première action d'urgence à voter ?
    *   A) Payer immédiatement la rançon demandée.
    *   B) Isoler physiquement le réseau et éteindre les liaisons réseau des machines affectées pour confiner l'attaque ✅
    *   C) Reconstruire les serveurs à partir des sauvegardes sur le même réseau actif.
*   **Guide d'animation (pour le mentor) :** Expliquez pourquoi isoler le réseau (B) est indispensable pour couper la propagation latérale avant d'envisager la restauration. Le paiement de la rançon (A) n'offre aucune garantie et finance le cybercrime — c'est le choix qu'a écarté le CHSF. Restaurer sur un réseau encore compromis (C) revient à reconstruire la maison pendant l'incendie : les sauvegardes seraient chiffrées à leur tour.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **AES-256** | Standard de chiffrement symétrique hautement sécurisé utilisant des clés de 256 bits, considéré comme inviolable par la force brute actuelle. |
| **APT (Menace persistante avancée)** | Groupe d'attaquants aux moyens importants (souvent étatique), capable de rester des mois dans un système pour espionner ou saboter. |
| **Confidentialité** | Garantie que seules les personnes autorisées ont accès aux données. |
| **DDoS (Distributed Denial of Service)** | Attaque par déni de service distribué visant à rendre un serveur ou un réseau indisponible en le submergeant de requêtes provenant de multiples sources. |
| **Défense en profondeur** | Superposition de couches de protection indépendantes : aucune défaillance isolée ne doit suffire à compromettre le système. |
| **Disponibilité** | Garantie que les données et les systèmes sont accessibles par les utilisateurs autorisés au moment où ils en ont besoin. |
| **Hameçonnage (Phishing)** | Usurpation d'un tiers de confiance pour pousser la victime à divulguer des informations ou exécuter une action malveillante. |
| **Intégrité** | Garantie que les données ne sont pas modifiées, altérées ou supprimées de manière accidentelle ou malveillante. |
| **Menace** | Un événement ou une entité externe ayant le potentiel d'exploiter une vulnérabilité et de causer des dommages. |
| **OSINT** | Renseignement en sources ouvertes : collecte d'informations librement accessibles, utilisée par les attaquants comme par les défenseurs. |
| **RaaS (Ransomware-as-a-Service)** | Modèle économique cybercriminel où des développeurs vendent ou louent des rançongiciels à des affiliés qui exécutent les attaques. |
| **Rançongiciel (Ransomware)** | Logiciel malveillant qui chiffre les données puis exige une rançon, souvent doublée d'une menace de publication (double extorsion). |
| **Risque** | La probabilité qu'une menace exploite une vulnérabilité et provoque un impact négatif (Risque = Menace × Vulnérabilité × Impact). |
| **SHA-256** | Algorithme de hachage cryptographique produisant une empreinte numérique unique de 256 bits pour vérifier l'intégrité d'une donnée. |
| **Surface d'exposition** | Ensemble des points d'entrée d'une organisation visibles depuis Internet, qu'un attaquant peut étudier puis exploiter. |
| **Sécurité défensive** | Ensemble des mesures de protection, de surveillance et de réaction déployées pour sécuriser un système (ex. gestion des pare-feux, surveillance SOC, réponse sur incident). |
| **Sécurité offensive** | Approche proactive consistant à tester les défenses en simulant des attaques réelles (ex. pentesting, red teaming). |
| **Triade CIA (Confidentialité, Intégrité, Disponibilité)** | Le modèle de référence de la sécurité de l'information. Chaque action de sécurité vise à garantir l'un ou plusieurs de ces piliers. |
| **Vulnérabilité** | Une faiblesse ou une faille présente dans un système, un logiciel, une procédure ou un comportement humain, susceptible d'être exploitée. |
