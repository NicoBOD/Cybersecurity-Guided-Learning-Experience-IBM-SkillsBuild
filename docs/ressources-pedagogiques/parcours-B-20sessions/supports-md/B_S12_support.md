# Session B12 — Sécurité & confidentialité des données
Parcours : B 20 sessions  |  Module : C — Identités, cloud & données  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30) — inclut l'**Atelier de Synthèse 2**

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - La Classification des données
    - Chiffrement au repos vs en transit, et la Prévention des fuites (DLP)
    - La règle de sauvegarde 3-2-1
    - Deux affaires réelles : OVHcloud (2021), l'incendie qui a emporté les sauvegardes, et Morgan Stanley, les disques revendus mal effacés
    - L'**Atelier de Synthèse 2** : le plan de protection des données de MedDistri
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   La **classification des données** (Publique, Interne, Confidentielle, Secrète) adapte l'effort et le coût de sécurité à la valeur réelle des informations.
*   Le **chiffrement en transit** protège les données circulant sur le réseau, tandis que le **chiffrement au repos** protège les données écrites sur des supports physiques contre le vol matériel.
*   Le **DLP** surveille activement les postes et réseaux pour bloquer les fuites d'informations confidentielles vers l'extérieur de l'entreprise.
*   La règle de sauvegarde **3-2-1** (3 copies, 2 supports différents, 1 copie hors site/hors ligne) est le rempart ultime contre la perte de données et les attaques par rançongiciel.

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Concevoir et appliquer un plan de classification des données d'entreprise sur 4 niveaux de sensibilité.
* Différencier et configurer le chiffrement des données au repos (*at rest*) et des données en transit (*in transit*).
* Expliquer le fonctionnement logique d'une solution de prévention des fuites de données (DLP).
* Appliquer la règle de sauvegarde 3-2-1 pour concevoir une architecture de sauvegarde résiliente face aux rançongiciels.
* Construire collectivement le plan de protection des données de la PME MedDistri (**Atelier de Synthèse 2**, par sondages et chat).

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** En mars 2021, un datacenter brûle à Strasbourg. Combien de sites web se retrouvent hors ligne d'un coup ?

    - A) Environ 3 000
    - B) Environ 360 000
    - C) Environ 3,6 millions ✅

    **Débrief mentor :** Réponse C : environ 3,6 millions de sites hors ligne après l'incendie d'un datacenter d'OVHcloud à Strasbourg. Le plus dur n'était pas la panne : certains clients avaient leurs **sauvegardes dans le même bâtiment** que leurs serveurs — pour eux, la perte fut définitive. Ce soir, on apprend à protéger la donnée elle-même, à chaque étape de sa vie : la classer, la chiffrer, empêcher sa fuite... et surtout la sauvegarder de façon à survivre à TOUT — rançongiciel comme incendie. L'histoire complète arrive en milieu de session.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Chiffré ≠ protégé en toutes circonstances**
Le piège conceptuel à désamorcer (c'est la question de réflexion n°1) : le chiffrement au repos (BitLocker) protège un disque **éteint ou volé** — mais sur une machine allumée, session ouverte, les données sont déchiffrées à la volée : un malware actif ou un employé indélicat y accède en clair. D'où la complémentarité avec le **DLP** (bloquer la sortie des contenus classifiés — pièce jointe, clé USB, upload) et les journaux d'accès. Chaque outil couvre un état de la donnée : en transit (TLS), au repos (chiffrement), en usage (DLP, droits).

**2. Le cycle de vie complet — jusqu'à la destruction**
La protection des données a une étape systématiquement oubliée : la **fin de vie**. Un fichier « supprimé » reste récupérable (la suppression n'efface que l'index) ; un disque formaté se lit encore avec des outils grand public. Fin de vie sérieuse : effacement sécurisé certifié (réécritures multiples), ou **destruction physique** pour les supports les plus sensibles — et le chiffrement systématique en amont transforme tout disque égaré en brique illisible. L'affaire Morgan Stanley (95 M$ d'amendes cumulées) est le cas d'école : des serveurs décommissionnés revendus sans effacement fiable.

**3. Sauvegarder ne suffit pas : il faut restaurer**
Le point de maturité à transmettre : une sauvegarde n'existe que si la **restauration a été testée**. Métriques à introduire simplement : RPO (combien de données puis-je perdre ? → fréquence des sauvegardes) et RTO (combien de temps pour redémarrer ? → vitesse de restauration). Les rançongiciels modernes chassent les sauvegardes connectées AVANT de chiffrer la production (plus de 9 attaques sur 10 les ciblent, selon Veeam) — d'où le trio : hors ligne, immuable, testé. Rappel utile : Maersk (B03) n'a survécu que par un contrôleur de domaine fortuitement hors ligne au Ghana.

---

### Glossaire

*   **Chiffrement au repos (At Rest)** — Protection des données écrites sur un support de stockage statique (disque dur, base de données) par chiffrement cryptographique, contre le vol matériel.
*   **Chiffrement en transit (In Transit)** — Protection des données en cours de déplacement sur un réseau de communication à l'aide de protocoles sécurisés (TLS, SSH, VPN).
*   **Classification des données** — Répartition des informations en niveaux de sensibilité (Publique, Interne, Confidentielle, Secrète) pour proportionner leur protection.
*   **DLP (Data Loss Prevention)** — Technologie logicielle de surveillance et de blocage conçue pour empêcher l'exfiltration accidentelle ou malveillante de données d'entreprise.
*   **Effacement sécurisé** — Suppression irréversible des données d'un support en fin de vie (réécritures certifiées ou destruction physique) — un simple formatage ne suffit pas.
*   **RPO / RTO** — Perte de données maximale admissible (fréquence des sauvegardes) / durée maximale admissible de restauration (vitesse de reprise).
*   **Sauvegarde 3-2-1** — Méthodologie de sauvegarde imposant de conserver au moins 3 copies des données, sur 2 supports différents, avec 1 copie délocalisée hors-site.
*   **Sauvegarde hors ligne (Offline Backup)** — Copie de sauvegarde stockée sur un support physiquement déconnecté du réseau informatique (bandes, disques débranchés), isolée des attaques cyber.
*   **Sauvegarde immuable** — Sauvegarde dont le contenu est protégé contre toute écriture, modification ou suppression pendant une période définie, idéale contre les rançongiciels.

---

### Concepts clés

!!! info "À retenir"
    La donnée se protège à chaque état de sa vie : **classée** dès sa création (l'effort suit la valeur), **chiffrée** en transit et au repos, **surveillée** en usage (DLP), **sauvegardée** en 3-2-1 avec une copie hors ligne... et **détruite** proprement en fin de vie. La plupart des catastrophes viennent d'une seule étape négligée.

### 1. La Classification des données
Pour protéger efficacement les informations, il faut d'abord savoir ce que l'on possède et quelle est sa valeur. Il est impossible (et inutilement coûteux) de protéger une simple brochure publique avec le même niveau de sécurité qu'un brevet secret de fabrication.

La classification consiste à répartir les données en 4 niveaux types de sensibilité :

1.  **Publique** : Données qui peuvent être divulguées sans aucun risque pour l'entreprise (ex. site web externe, communiqués de presse, catalogues).
2.  **Interne** : Données réservées à l'usage exclusif des employés de l'entreprise. Leur divulgation externe causerait un embarras mineur ou une perte d'efficacité (ex. organigramme interne, notes de service, procédures techniques).
3.  **Confidentielle** : Données sensibles dont la divulgation externe porterait préjudice à l'entreprise, à ses clients ou à ses employés (ex. données de paie des RH, fichiers clients, bilans comptables non publiés, contrats de fournisseurs).
4.  **Secrète (ou Strictement Confidentielle)** : Données stratégiques vitales. Leur fuite menacerait directement la pérennité, la compétitivité ou la survie légale de l'entreprise (ex. brevets industriels non déposés, codes sources de logiciels propriétaires, projets de fusion-acquisition).

*   *L'analogie de la maison d'édition* :
    *   **Publique** : Les livres imprimés exposés en vitrine de la librairie.
    *   **Interne** : Le planning de travail des équipes éditoriales dans le couloir des bureaux.
    *   **Confidentielle** : Les coordonnées bancaires et contrats de droits d'auteur des écrivains.
    *   **Secrète** : Le manuscrit inédit du prochain best-seller mondial encore confidentiel.

### 2. Chiffrement au repos vs en transit
Pour préserver la confidentialité des données à travers leur cycle de vie, la cryptographie (B10) s'applique à deux états différents :

*   **Chiffrement en transit (*in transit*)** : Concerne les données en cours de déplacement sur un réseau (ex. entre votre navigateur et un site web, ou entre deux serveurs). On utilise des protocoles de transport chiffrés comme **TLS (HTTPS)**, **SSH**, ou des **VPN** pour empêcher l'interception passive des flux (B07).
*   **Chiffrement au repos (*at rest*)** : Concerne les données stockées de manière statique sur un support physique (disque dur d'ordinateur, serveurs de stockage NAS, bases de données, clés USB). On utilise des logiciels comme **BitLocker** (Windows), **LUKS** (Linux) ou le chiffrement natif des bases de données pour empêcher la lecture des données si le disque physique est volé ou accédé directement hors du système d'exploitation (B08).

> 💡 **Bon à savoir : chiffré ne veut pas dire invulnérable**
> Le chiffrement au repos protège un disque **éteint ou volé**. Sur une machine allumée, session ouverte, les données sont déchiffrées à la volée : un malware actif y accède en clair. Chaque état de la donnée a son outil : TLS en transit, chiffrement au repos, DLP et droits d'accès en usage.

### 3. La Prévention des fuites de données (DLP — Data Loss Prevention)
Une solution de **DLP** est un outil logiciel qui inspecte automatiquement le trafic réseau, les terminaux utilisateurs et les serveurs de stockage pour détecter et empêcher l'extraction non autorisée d'informations sensibles en dehors du périmètre de l'entreprise.

*   *Fonctionnement* : Le DLP utilise des règles d'analyse de contenu (expressions régulières, mots-clés, empreintes de fichiers). Si un employé tente de copier un fichier de R&D contenant le mot "PROTOTYPE" sur une clé USB personnelle ou d'envoyer par email une liste contenant des numéros de cartes de crédit, le DLP bloque l'action et alerte l'équipe de sécurité.
*   *Le prérequis* : le DLP ne vaut que par la **classification** — sans elle, il ne sait pas quoi bloquer (tout ou rien). La classification décide, le DLP applique.

### 4. La règle de sauvegarde 3-2-1
Face à la recrudescence des rançongiciels (*ransomwares*) qui chiffrent les serveurs de l'entreprise pour réclamer une rançon, la seule garantie de reprise d'activité réside dans les sauvegardes. La règle d'or industrielle est la méthodologie **3-2-1** :

*   **3 copies** : Conserver au moins trois exemplaires de vos données (la donnée originale de production + au moins deux copies de sauvegarde indépendantes).
*   **2 supports différents** : Stocker ces sauvegardes sur au moins deux types de médias technologiques distincts (ex. un disque dur externe branché localement et un serveur de stockage réseau NAS). Cela protège contre la défaillance matérielle d'une technologie spécifique.
*   **1 copie hors site** : Conserver au moins une copie des sauvegardes dans un lieu géographique différent de l'original (ex. dans le Cloud sécurisé ou sur un disque transporté physiquement dans un autre bâtiment).
*   *Mesure moderne anti-ransomware* : Cette copie hors site doit être **hors ligne** (sauvegarde déconnectée physiquement du réseau) ou **immuable**, car les ransomwares modernes recherchent activement les serveurs de sauvegarde connectés au réseau pour les détruire avant de chiffrer la production.
*   *Et le test de restauration* : une sauvegarde n'existe que si la restauration a été **testée** — deux questions guident tout : combien de données puis-je perdre (RPO → fréquence) et en combien de temps dois-je redémarrer (RTO → vitesse de restauration).

**Exemple de mise en œuvre (cas ArchiTech, agence de 5 dessinateurs CAO) :** copie n°1 = le serveur de production (SSD en RAID, utilisé au quotidien) ; copie n°2 = un NAS dans une pièce technique distincte, alimenté chaque nuit (panne du serveur → restauration locale rapide) ; copie n°3 = stockage cloud chiffré **immuable** (ou rotation de disques déposés dans un coffre externe) — celle qui survit à l'incendie des locaux ET au rançongiciel qui a atteint tout le réseau local.

### 5. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **Environ 3,6 millions de sites web** hors ligne après l'incendie du datacenter OVHcloud de Strasbourg (mars 2021) — et des données définitivement perdues pour les clients dont les sauvegardes étaient co-localisées.
    - **95 millions de dollars d'amendes cumulées** pour Morgan Stanley (60 M$ du régulateur bancaire en 2020, 35 M$ du gendarme boursier en 2022) : des équipements de stockage décommissionnés revendus sans effacement fiable.
    - **Plus de 9 attaques par rançongiciel sur 10** ciblent aussi les sauvegardes de la victime (rapport Veeam *Ransomware Trends*).

**Comment lire ces chiffres ?** (1) Le sinistre physique existe encore à l'ère du cloud — la copie hors site n'est pas une option. (2) La donnée reste dangereuse jusqu'à sa destruction certifiée. (3) La sauvegarde connectée n'est plus une protection contre le rançongiciel : hors ligne ou immuable, sinon rien.

### 6. Deux affaires réelles : l'incendie de Strasbourg et les disques baladeurs

#### Cas n°1 — OVHcloud (2021) : l'incendie qui a emporté les sauvegardes

Dans la nuit du 9 au 10 mars 2021, un incendie ravage **SBG2**, l'un des datacenters d'**OVHcloud** à Strasbourg — le leader européen de l'hébergement. Environ **3,6 millions de sites web** passent hors ligne : sites d'entreprises, boutiques en ligne, services publics. Le fondateur d'OVH lance sur les réseaux un message resté célèbre : *« Nous recommandons d'activer votre plan de reprise d'activité »* — révélant au passage que beaucoup de clients... n'en avaient pas. Pour la plupart, la panne fut temporaire. Mais pour certains, la perte fut **définitive** : leurs sauvegardes étaient hébergées dans le même datacenter que leurs serveurs — parfois dans la même salle. Le « 1 hors site » de la règle 3-2-1 n'était pas respecté... et des entreprises ont perdu des années de travail dans la nuit.

**Ce que ce cas illustre :** le cloud n'abolit pas le risque physique — un datacenter est un bâtiment qui peut brûler ; la responsabilité de la sauvegarde reste au **client** (rappel direct de B11 : la donnée, toujours au client — beaucoup pensaient qu'« OVH s'en occupait ») ; et le « hors site » de la règle 3-2-1 signifie une **séparation géographique réelle**, pas une autre salle du même bâtiment.

#### Cas n°2 — Morgan Stanley : les serveurs revendus avec les données dedans

Entre 2016 et 2019, la banque américaine **Morgan Stanley** décommissionne des serveurs et équipements de stockage contenant les données de millions de clients. Le prestataire chargé de l'opération revend une partie du matériel **sans effacement fiable** — des disques contenant encore des données personnelles non chiffrées se retrouvent aux enchères, rachetés par des tiers. Certains ne seront jamais récupérés. Sanctions : **60 M$** d'amende du régulateur bancaire (2020), puis **35 M$** du gendarme boursier (2022) — près de 95 M$ pour une opération de « ménage » ratée.

**Ce que ce cas illustre :** le cycle de vie de la donnée va **jusqu'à la destruction** — supprimer un fichier n'efface que l'index, formater ne suffit pas : il faut un effacement sécurisé certifié ou une destruction physique ; le **chiffrement systématique au repos** aurait transformé chaque disque égaré en brique illisible (la moitié du problème disparaissait) ; et la sous-traitance, une fois encore, transporte la responsabilité sans la transférer.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    MedDistri renouvelle son parc : 40 ordinateurs partent à la reprise, et le prestataire propose de racheter aussi les anciens disques du serveur. **Tapez A, B ou C dans le chat :**

    - A) Supprimer les fichiers et vider la corbeille avant la remise du matériel.
    - B) Exiger un effacement sécurisé certifié (ou la destruction physique des disques les plus sensibles) — et vérifier que le chiffrement au repos était actif sur tout le parc. ✅
    - C) Formater rapidement chaque disque : c'est suffisant.

    **Débrief mentor :** B — la suppression (A) n'efface que l'index : les données se récupèrent avec des outils grand public ; le formatage rapide (C) à peine mieux. La fin de vie sérieuse : effacement certifié à réécritures multiples, destruction physique pour le plus sensible, et un certificat du prestataire (la traçabilité protège juridiquement). Et si le chiffrement au repos était actif depuis le début, chaque disque égaré n'est qu'une brique illisible — Morgan Stanley a payé 95 M$ pour cette leçon.

### Atelier de Synthèse 2 — Le plan de protection des données de MedDistri (Sondages Livestorm n°2 à 4)

**Le principe** (voir [Ateliers de Synthèse](../projet/B_miniprojets.md)) : ~25 minutes pour assembler les acquis du module C sur le cas MedDistri. Le mentor rappelle les contraintes : 15 commerciaux en déplacement permanent, données migrées vers le cloud (suite bureautique SaaS), mots de passe enregistrés dans les navigateurs, fiches de paie stockées sur l'espace de partage. Le public construit le plan de durcissement des accès et de protection des données par sondages, puis rédige collectivement les règles d'or par chat.

*   **📊 Sondage n°2 — La MFA des nomades (acquis B09) :** Quelle méthode de MFA préconisez-vous pour les 15 commerciaux ?
    *   A) L'authentification par SMS : simple et universelle
    *   B) Une application d'authentification (ou une clé physique FIDO2) ✅
    *   C) Aucune : un bon mot de passe suffit s'il est long
*   **📊 Sondage n°3 — La classification (acquis B12) :** Les fiches de paie stockées sur l'espace de partage cloud doivent être classées :
    *   A) Internes : tous les salariés peuvent les voir
    *   B) Confidentielles : accès restreint aux RH et à la direction, chiffrement et traçabilité ✅
    *   C) Publiques : elles seront déclarées à l'administration de toute façon
*   **📊 Sondage n°4 — La sauvegarde (acquis B12) :** Où placer la troisième copie (règle 3-2-1) des données critiques de MedDistri ?
    *   A) Sur un deuxième NAS, dans la même salle serveur que le premier
    *   B) Dans un stockage cloud chiffré et immuable, géographiquement distinct (ou des disques en coffre externe) ✅
    *   C) La corbeille de la suite SaaS conserve tout : inutile de sauvegarder

**Déroulé de l'atelier (pour le mentor) :**

1. **Présentation du cas (4 min)** : rappeler les contraintes de MedDistri et faire réagir le chat : *« Qu'est-ce qui vous inquiète le plus dans cette situation ? »* (attendu : mots de passe dans les navigateurs, paie accessible à tous, aucune MFA).
2. **Les trois décisions (12 min)** : lancer les **📊 Sondages n°2, 3, 4** avec débrief entre chaque (éléments ci-dessous).
3. **Les règles d'or collectives (7 min)** : rédiger en direct, à partir du chat, les **5 règles de sécurité des accès et données cloud** de MedDistri : *« Proposez une règle en une phrase ! »* — attendues : MFA obligatoire partout ; gestionnaire de mots de passe (fin des mots de passe navigateur) ; classification et restriction des partages ; chiffrement au repos sur tous les postes ; sauvegarde 3-2-1 avec copie immuable testée.
4. **Synthèse (3 min)** : « ce plan tient sur une page — et il couvre tout le module C : les identités (B09), le chiffrement (B10), le cloud (B11) et les données (ce soir). »

**Éléments de débriefing (pour le mentor) :**

- N°2 : le SMS est la MFA la plus fragile (SIM swapping, rappel B09) — pour des nomades, l'application d'authentification est le standard, la clé FIDO2 l'idéal (résistante à l'hameçonnage). C n'est plus défendable : les mots de passe seuls se volent et se rejouent (B09, B10).
- N°3 : les fiches de paie cumulent données personnelles et bancaires — Confidentielles par nature : accès RH/direction, chiffrement, traçabilité des consultations. Le réflexe de classification décide de tout le reste (partages, DLP, chiffrement).
- N°4 : A viole le « 1 hors site » — c'est exactement le scénario OVHcloud ; C confond corbeille et sauvegarde (rappel B11 : supprimer ≠ sauvegarder, la corbeille SaaS a une durée limitée et un rançongiciel peut la vider). B coche tout : hors site, immuable, indépendant du réseau de production.

!!! tip "📊 Sondage Livestorm n°5 — Et vous ? (sondage d'opinion, pas de bonne réponse)"
    **Question :** Vos données personnelles importantes (photos, documents) : où en êtes-vous ?

    - A) Sauvegarde 3-2-1 ou presque (copie locale + copie cloud/externe)
    - B) Une copie quelque part, pas très à jour
    - C) Tout est au même endroit — je croise les doigts

    **Débrief mentor :** Sondage d'opinion — C est fréquent et personne ne juge : la prise de conscience arrive souvent... après la perte. Le kit minimal personnel : un disque externe branché UNIQUEMENT le temps de la sauvegarde (hors ligne le reste du temps) + une copie cloud chiffrée. Dix ans de photos de famille valent bien deux heures de configuration — c'est l'action personnelle de la semaine.

---

### Questions de réflexion
1. Si vous chiffrez un disque dur externe au repos à l'aide de BitLocker, et que vous le laissez branché en permanence sur un ordinateur de bureau infecté par un malware actif, le chiffrement empêchera-t-il le malware de voler ou de modifier vos fichiers ? Justifiez votre réponse.
2. Pourquoi la classification des données est-elle considérée comme un prérequis indispensable avant de configurer les règles d'un logiciel de prévention des fuites de données (DLP) ?
3. Dans l'affaire OVHcloud, des clients avaient pourtant « des sauvegardes ». Qu'est-ce qui, dans leur application de la règle 3-2-1, a transformé un incendie en perte définitive — et quelle case du modèle de responsabilité partagée (B11) avaient-ils mal lue ?

**Corrigé / Éléments de réponse :**

1. Non, si l'ordinateur est allumé et la session ouverte, le disque est déchiffré à la volée. Le malware peut donc accéder aux fichiers en clair — le chiffrement au repos protège le support volé ou éteint, pas la machine compromise en fonctionnement.
2. Le DLP a besoin de savoir quelles données sont sensibles (confidentielles, restreintes) pour appliquer les bonnes règles ; sans classification, tout est bloqué ou rien n'est bloqué.
3. Le « 1 hors site » manquait : leurs sauvegardes partageaient le même bâtiment (parfois la même salle) que la production — aucune séparation géographique réelle. Et côté responsabilité partagée : la sauvegarde des données reste à la charge du client — « l'hébergeur s'en occupe » n'était écrit dans aucun contrat standard.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez la protection et la sauvegarde de vos données d'entreprise à l'aide de l'analogie d'une **collection de photos de famille précieuses** :
    - Conserver toutes vos photos sur un seul ordinateur portable chez vous, c'est courir un risque majeur en cas de vol ou d'incendie.
    - **La règle de sauvegarde 3-2-1** s'applique ainsi :
      - Vous gardez les photos originales sur votre ordinateur (Copie 1).
      - Vous copiez ces photos sur un disque dur externe chez vous (Copie 2, support physique différent).
      - Vous envoyez une copie chiffrée de ces photos sur un serveur de stockage en ligne cloud (Copie 3, hors-site dans un lieu géographique différent).
    - Pour éviter qu'un cambrioleur (rançongiciel) ne détruise votre disque de sauvegarde en même temps que votre ordinateur, vous le débranchez du réseau et le mettez dans un coffre-fort (sauvegarde hors-ligne/immuable).

**Exemple d'application professionnelle :**
Une PME de santé met en œuvre la règle 3-2-1 pour ses dossiers médicaux. Lorsqu'une cyberattaque par ransomware frappe les postes internes et chiffre tous les disques durs connectés, l'administrateur peut restaurer l'intégralité du système en quelques heures grâce à la copie externe déconnectée stockée hors-site — parce que la restauration avait été testée deux mois plus tôt.

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour assurer la confidentialité des données (DLP) et appliquer la règle de sauvegarde 3-2-1 de manière robuste :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Veeam Backup & Replication** : Le leader mondial de la sauvegarde pour environnements physiques, virtuels et cloud, offrant le chiffrement AES-256 et des référentiels de stockage immuables.
    *   **Forcepoint DLP (Data Loss Prevention)** : Solution de référence pour analyser, classifier et empêcher l'exfiltration de fichiers sensibles sur les postes de travail, le réseau et le cloud.
    *   **Rubrik / Commvault** : Plateformes de sauvegarde et de gestion de données haut de gamme, axées sur la détection des ransomwares et la restauration rapide des fichiers.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **Duplicati** : Logiciel de sauvegarde open-source gratuit fonctionnant sous Windows, macOS et Linux. Il compresse, chiffre et envoie les sauvegardes vers des destinations cloud locales ou distantes.
    *   **BorgBackup / Restic** : Outils de sauvegarde en ligne de commande ultra-rapides et légers sous Linux, supportant la déduplication des données et le chiffrement authentifié.
    *   **OpenDLP** : Scanner open-source permettant de rechercher et d'identifier les données personnelles (cartes de crédit, données de santé) stockées à l'insu de l'entreprise sur ses disques.

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après le sondage d'opinion n°5.

*   **📊 Sondage n°6 :** Un fichier confidentiel est envoyé via HTTPS puis stocké sur un serveur dont le disque n'est pas chiffré. Quelle protection manque-t-il ?
    *   A) Le chiffrement en transit
    *   B) Le chiffrement au repos ✅
    *   C) Aucune : HTTPS protège le fichier pour toujours
*   **📊 Sondage n°7 :** Un employé tente d'envoyer par e-mail un fichier contenant des numéros de cartes bancaires. Que fait une solution DLP correctement configurée ?
    *   A) Elle chiffre automatiquement l'e-mail avant l'envoi
    *   B) Elle bloque l'envoi et alerte l'équipe de sécurité ✅
    *   C) Elle supprime le compte e-mail de l'employé
*   **📊 Sondage n°8 :** Pourquoi la copie hors site de la règle 3-2-1 doit-elle être hors ligne ou immuable ?
    *   A) Parce que le stockage hors ligne coûte moins cher
    *   B) Pour accélérer la restauration en cas de panne
    *   C) Parce que les rançongiciels modernes recherchent et détruisent les sauvegardes connectées avant de chiffrer la production ✅

**Éléments de débriefing (pour le mentor) :**

- N°6 : chaque état a son outil — TLS protège le trajet, pas le stockage : arrivé sur le disque, le fichier vit sa propre vie (vol du disque, accès direct). Les deux chiffrements se complètent, ne se remplacent pas.
- N°7 : le DLP bloque ET alerte — il applique la classification (sans elle, il est aveugle). Ni justicier (C), ni chiffreur (A) : un gardien de sortie.
- N°8 : plus de 9 attaques sur 10 ciblent les sauvegardes (Veeam) — une sauvegarde joignable par le réseau est une sauvegarde condamnée. Hors ligne, immuable... et restauration testée.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Data Security and Privacy"* (durée estimée : 1h30).
*   **Recherche complémentaire** : Renseignez-vous sur le règlement **RGPD** (Règlement Général sur la Protection des Données). Identifiez comment la classification et la pseudonymisation des données personnelles aident à se conformer à la législation européenne — il sera au cœur de la session B15.
*   [CNIL — Guide de la sécurité des données personnelles](https://www.cnil.fr/fr/guide-de-la-securite-des-donnees-personnelles)
*   [Cybermalveillance — Protéger ses données](https://www.cybermalveillance.gouv.fr/)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Application de la résilience opérationnelle.
*   **📊 Sondage Livestorm n°9 :** Un incendie détruit intégralement les bureaux de l'entreprise. Vos sauvegardes sont stockées sur deux disques durs externes dans les mêmes locaux. Que se passe-t-il ?
    *   A) Les données sont sauvées car il y a deux disques.
    *   B) Les données sont définitivement perdues car aucun support n'était externalisé ✅
    *   C) Les données peuvent être récupérées dans le cloud automatiquement sans configuration préalable.
*   **Guide d'animation (pour le mentor) :** Le « 3-2 » était respecté (3 copies, 2 supports)... mais pas le « 1 » : aucune copie hors site — c'est très exactement le drame vécu par certains clients d'OVHcloud en 2021. Deux disques dans le même bâtiment partagent le même destin. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Classification (4 niveaux)** | Publique · Interne · Confidentielle · Secrète — l'effort de protection suit la valeur. |
| **Chiffrement en transit** | TLS/SSH/VPN : protéger le trajet (B07). |
| **Chiffrement au repos** | BitLocker/LUKS : protéger le support volé ou éteint — pas la machine allumée compromise. |
| **DLP** | Le gardien de sortie : bloque l'exfiltration des contenus classifiés — aveugle sans classification. |
| **Sauvegarde 3-2-1** | 3 copies, 2 supports, 1 hors site — et la copie hors site : **hors ligne ou immuable**. |
| **RPO / RTO** | Combien puis-je perdre ? / En combien de temps dois-je redémarrer ? — et la restauration se TESTE. |
| **Effacement sécurisé** | Supprimer ≠ effacer : réécritures certifiées ou destruction physique en fin de vie (Morgan Stanley). |

**La règle d'or de la session :** suivez la donnée sur toute sa vie — classée à la création, chiffrée en transit et au repos, surveillée en usage, sauvegardée en 3-2-1 (copie hors site, hors ligne, testée), détruite proprement à la fin. OVHcloud et Morgan Stanley rappellent que l'étape négligée finit toujours par se payer.
