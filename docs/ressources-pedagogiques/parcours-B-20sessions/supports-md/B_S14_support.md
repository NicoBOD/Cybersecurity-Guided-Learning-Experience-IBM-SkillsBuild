# Session B14 — Gestion des risques
Parcours : B 20 sessions  |  Module : D — Gouvernance, risques & conformité  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Qu'est-ce qu'un risque cyber ? (L'équation du risque)
    - Le Registre des risques et la Matrice de Criticité 4x4
    - Les 4 options de traitement du risque
    - Deux affaires réelles : Mondelez contre son assureur (l'« acte de guerre » NotPetya) et Merck, le bras de fer à 1,4 milliard
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Un **risque cyber** naît de la rencontre d'une menace et d'une vulnérabilité sur un actif de valeur pour l'entreprise.
*   L'évaluation du risque croise sa **vraisemblance** (probabilité d'occurrence) et sa **gravité** (impact financier, juridique ou d'image).
*   La **criticité brute** priorise les risques, tandis que la **criticité résiduelle** mesure le risque subsistant après l'application des contrôles de sécurité.
*   Il existe 4 réponses stratégiques au risque : **Réduire** (sécuriser), **Transférer** (assurance), **Éviter** (renoncer), ou **Accepter** (décision de direction, formalisée par écrit).

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer et articuler les composantes d'un risque cyber : actif, menace, vulnérabilité, impact et vraisemblance.
* Construire un registre des risques cyber pragmatique et calculer sa criticité à l'aide d'une matrice qualitative 4x4.
* Justifier et choisir une stratégie de traitement du risque adaptée parmi les 4 options fondamentales (réduire, transférer, éviter, accepter).

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** Un assureur peut-il refuser d'indemniser une entreprise victime d'une cyberattaque en invoquant... un « acte de guerre » ?

    - A) Oui — c'est déjà arrivé, pour des centaines de millions de dollars ✅
    - B) Non — c'est juridiquement impossible pour une attaque informatique
    - C) Uniquement si une guerre a été officiellement déclarée

    **Débrief mentor :** Réponse A : après l'attaque NotPetya (2017, vue en B03), attribuée à un sabotage étatique, plusieurs assureurs ont invoqué la clause d'**exclusion de guerre** de leurs contrats pour refuser d'indemniser des victimes collatérales — dont Mondelez (~100 M$ réclamés) et Merck (1,4 Md$ !). Les procès qui ont suivi sont devenus des cas d'école... que nous étudierons ce soir. Moralité d'ouverture : « transférer » un risque à un assureur ne le fait pas disparaître — encore faut-il lire la police. Ce soir, vous apprenez le métier d'arbitre des risques : les identifier, les coter, et choisir en connaissance de cause.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. EBIOS Risk Manager, la méthode française**
Situez la méthode de référence de l'**ANSSI** sans en faire un cours : EBIOS RM structure l'analyse en ateliers successifs — du cadrage (socle de sécurité, valeurs métier) aux scénarios stratégiques (qui pourrait nous attaquer et pourquoi — les sources de risque de B02) puis opérationnels (comment, techniquement — les chemins d'attaque de B03), jusqu'au plan de traitement. Le message : la matrice 4x4 de ce soir est la version « PME pragmatique » de démarches plus outillées ; la logique (vraisemblance × gravité, brut → résiduel) reste identique à toutes les échelles.

**2. L'assurance cyber : ce qu'elle couvre, ce qu'elle exige**
Précisez le fonctionnement réel : l'assurance couvre typiquement les frais de remédiation, l'interruption d'activité, l'assistance juridique et de crise — et elle **exige** désormais un socle de sécurité à la souscription (MFA, sauvegardes, EDR : le questionnaire d'assurance ressemble à notre parcours !). En France, la loi **LOPMI (2023)** conditionne l'indemnisation d'une cyber-rançon au dépôt de plainte sous 72 h (rappel du débat de B02). Et depuis les contentieux NotPetya, le marché a réécrit ses **clauses d'exclusion de guerre** pour les préciser (exigences du Lloyd's de Londres en 2023 sur les attaques soutenues par des États) — lisez les exclusions AVANT de compter sur le transfert.

**3. Le risque, langage de la direction**
Le basculement de posture à transmettre : la direction ne comprend ni les CVE ni les VLAN — elle comprend la vraisemblance, l'impact en euros et les options de traitement. L'analyse de risques est le **traducteur** entre la technique (modules A-C) et la gouvernance (B13) : c'est elle qui transforme « il nous faut un EDR » en « ce risque coté 12/16 passe à 3/16 pour 15 k€/an ». Un RSSI qui parle risque obtient des budgets ; un RSSI qui parle technique obtient des hochements de tête.

---

### Glossaire

*   **Actif (Asset)** — Tout élément physique, virtuel ou humain ayant de la valeur pour la réalisation de la mission de l'entreprise.
*   **Assurance Cyber** — Contrat d'assurance spécifique destiné à couvrir les pertes financières et les frais de remédiation consécutifs à une cyberattaque.
*   **EBIOS RM** — Méthode française d'analyse et de management des risques cyber publiée par l'ANSSI, structurée en ateliers (du cadrage aux plans de traitement).
*   **Exclusion de guerre** — Clause d'un contrat d'assurance excluant les dommages causés par des actes de guerre ou assimilés — invoquée par des assureurs après NotPetya.
*   **Impact** — Conséquence négative (financière, légale, opérationnelle, réputationnelle) découlant de la réalisation d'un risque.
*   **Registre des risques** — Document centralisant l'ensemble des risques identifiés dans un organisme, leurs évaluations et les actions de traitement associées.
*   **Risque Résiduel** — Niveau de risque subsistant après la mise en œuvre des mesures de traitement et des contrôles de sécurité.
*   **Shadow IT** — Utilisation de systèmes, logiciels ou services informatiques par des employés sans l'autorisation ou le contrôle formel de la DSI.
*   **Vraisemblance (Likelihood)** — Estimation de la probabilité ou de la fréquence à laquelle un scénario de menace cyber peut se produire.
*   **Vulnérabilité** — Faille ou faiblesse logique, physique ou organisationnelle permettant à un attaquant de compromettre un système.

---

### Concepts clés

!!! info "À retenir"
    Le risque ne s'élimine pas : il s'**arbitre**. On l'identifie (actif, menace, vulnérabilité), on le cote (vraisemblance × gravité), puis on choisit — réduire, transférer, éviter ou accepter — en connaissance de cause et par écrit. L'analyse de risques est le traducteur entre la technique et la direction : elle transforme des CVE en euros et des inquiétudes en décisions.

### 1. Qu'est-ce qu'un risque cyber ? (L'équation du risque)
En sécurité de l'information, le risque n'est pas un concept abstrait. Il se définit comme la possibilité qu'un événement indésirable survienne et affecte l'activité de l'entreprise.

Pour caractériser un risque, on décompose l'équation en plusieurs éléments :

*   **L'Atout / Actif (*Asset*)** : Ce qui a de la valeur pour l'entreprise et doit être protégé (ex. les fichiers de brevets, la base de données clients, le serveur de messagerie).
*   **La Menace (*Threat*)** : L'événement redouté d'origine externe ou interne qui pourrait causer un dommage (ex. un ransomware, un employé malveillant, une panne électrique, un incendie).
*   **La Vulnérabilité (*Vulnerability*)** : La faiblesse ou la faille exploitable au sein du système d'information (ex. l'absence de mises à jour système, un personnel non formé au phishing, l'absence de pare-feu local).
*   **L'Impact (*Impact*)** : La conséquence préjudiciable pour l'entreprise si la menace se concrétise (perte financière, amende réglementaire, atteinte à la réputation, arrêt de la production).
*   **La Probabilité / Vraisemblance (*Likelihood*)** : La plausibilité que la menace réussisse à exploiter la vulnérabilité sur une période donnée.

!!! note "Formulation logique d'un risque"
    Un risque se formule toujours ainsi : *« La **menace** [ex. un ransomware] pourrait exploiter la **vulnérabilité** [ex. ports RDP ouverts sur Internet] pour atteindre l'**actif** [ex. serveurs de fichiers] et causer un **impact** [ex. arrêt complet de l'activité pendant 5 jours]. »* — Vous connaissez déjà tous les ingrédients : les menaces (B02), les vulnérabilités (B03-B08), les actifs (B12). Ce soir, on les assemble.

### 2. Le Registre des risques et la Matrice de Criticité 4x4
Pour prioriser les chantiers de sécurité, les entreprises listent leurs risques dans un **registre des risques** et évaluent leur **criticité brute** (le risque sans aucune mesure de sécurité).

On évalue qualitativement sur une échelle de 1 à 4 :

*   **Vraisemblance / Probabilité (V)** : 1 (Rare) | 2 (Possible) | 3 (Probable) | 4 (Presque certain).
*   **Gravité / Impact (G)** : 1 (Mineur) | 2 (Modéré) | 3 (Majeur) | 4 (Critique/Catastrophique).
*   **Criticité (C)** = Vraisemblance × Gravité. Le score varie de 1 à 16.

#### Matrice qualitative de criticité :
*   **1 à 4** : Risque Faible (à surveiller simplement).
*   **5 à 8** : Risque Moyen (mesures de sécurité à planifier).
*   **9 à 16** : Risque Élevé / Critique (mesures d'atténuation immédiates obligatoires).

La cotation est **qualitative et collégiale** : sa valeur vient moins de la précision du chiffre que de la discussion qu'elle force (le métier et la technique autour de la même table) et de la **priorisation** qu'elle produit — on traite le 12 avant le 4.

### 3. Les 4 options de traitement du risque
Une fois les risques identifiés et évalués, l'entreprise doit décider comment y répondre. Elle dispose de 4 stratégies fondamentales :

1.  **Réduire / Atténuer (*Mitigate*)** : C'est la stratégie la plus courante. Elle consiste à mettre en place des mesures de sécurité pour réduire la probabilité ou l'impact du risque (ex. installer un EDR pour réduire la probabilité d'infection, ou faire des sauvegardes 3-2-1 pour réduire l'impact d'un ransomware).
2.  **Transférer (*Transfer*)** : Transférer la responsabilité financière ou opérationnelle à un tiers.
    *   *Exemples* : Souscrire à une **cyber-assurance** (transfert financier) ou confier l'hébergement de ses données à un hébergeur cloud hautement sécurisé et certifié (transfert opérationnel — en gardant en tête la responsabilité partagée de B11 !).
    *   *La limite* : le transfert ne fait pas disparaître le risque — l'assurance rembourse des euros, pas la confiance des clients ni les données fuitées. Et les contrats ont des exclusions (les affaires de ce soir).
3.  **Éviter (*Avoid*)** : Renoncer à l'activité ou à la technologie à l'origine du risque.
    *   *Exemple* : Interdire l'utilisation d'une application mobile tierce de partage de fichiers non sécurisée pour les documents internes confidentiels.
4.  **Accepter (*Accept*)** : Décider sciemment d'assumer le risque sans mettre en place de mesures supplémentaires, généralement parce que le coût des mesures de protection dépasse la valeur de ce qu'on protège. **L'acceptation d'un risque doit être formalisée par écrit et signée par la Direction Générale** (rappel B13 : le RSSI conseille, la Direction assume — et un risque non arbitré est un risque accepté par accident).

### Activité — La ligne de registre : l'IA générative chez EcoLog (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Affichez le contexte : chez EcoLog, les équipes marketing utilisent des services d'**IA générative publics et gratuits** pour relire contrats de partenaires et données clients nominatives — sans validation de la DSI (du *Shadow IT* caractérisé). Vous allez construire ensemble la ligne de registre de ce risque : cotation brute, traitement, cotation résiduelle. Un sondage par étape, débrief entre chaque.

*   **📊 Sondage n°2 — La cotation brute :** L'usage est quotidien (Vraisemblance = 4) et une fuite de secrets commerciaux ou de données personnelles serait majeure (Gravité = 3). Quelle criticité brute ?
    *   A) 7 — on additionne V et G
    *   B) 12 sur 16 — on multiplie : risque critique, traitement immédiat ✅
    *   C) 3 — on retient la gravité seule
*   **📊 Sondage n°3 — La stratégie de traitement :** EcoLog décide : charte d'usage de l'IA + blocage des IA publiques au pare-feu + mise à disposition d'un outil d'IA interne sécurisé. Quelle stratégie est-ce ?
    *   A) Éviter : on renonce à l'IA générative
    *   B) Transférer : c'est le problème du fournisseur d'IA désormais
    *   C) Réduire / Atténuer : on abaisse la vraisemblance sans renoncer à l'usage ✅
*   **📊 Sondage n°4 — La cotation résiduelle :** Après ces mesures, la fuite devient rare (V = 1)... mais si elle survient, l'impact légal reste identique (G = 3). Quelle criticité résiduelle, et pourquoi la gravité n'a-t-elle pas bougé ?
    *   A) 3 sur 16 (risque faible) — les mesures réduisent la probabilité, pas les conséquences d'une fuite si elle survient ✅
    *   B) 0 — le risque a disparu grâce au blocage
    *   C) 12 — rien ne change tant que l'IA existe

**Éléments de débriefing (pour le mentor) :**

- N°2 : criticité = V **×** G = 12/16, zone critique de la matrice — traitement immédiat obligatoire. (L'addition — piège A — écraserait les écarts : un 4×4 vaudrait autant qu'un simple cumul de moyens.)
- N°3 : la nuance clé — on n'a PAS renoncé à l'IA (ce serait Éviter) : on garde l'usage en abaissant la vraisemblance par trois leviers complémentaires — technique (blocage), organisationnel (charte), et alternative sécurisée (sinon : contournement, rappel B08). C'est l'atténuation type.
- N°4 : la leçon la plus fine de la session — le résiduel n'est **jamais nul** (B est le piège), et ici les mesures n'agissent que sur la vraisemblance : SI une fuite survient malgré tout, l'amende et le préjudice restent majeurs. Pour abaisser la gravité, il faudrait d'autres leviers (minimiser les données soumises, pseudonymisation — teaser B15).
- **Afficher la ligne de registre complète** (corrigé ci-dessous) : « voilà une ligne de registre professionnelle — c'est exactement l'exercice de l'Atelier de Synthèse 3, la semaine prochaine, sur MedDistri. »

**Ligne de registre complète (corrigé de référence) :**

| Composante du Risque | Descriptif technique / Valeurs |
|---|---|
| **Actif menacé** | Données de contrats commerciaux et données nominatives de clients. |
| **Description du Risque** | Des salariés du marketing (menace) soumettent des contrats et des données nominatives (actifs) à des outils d'IA publics non validés par la DSI (vulnérabilité), provoquant la fuite ou la réutilisation non contrôlée de données d'entreprise. |
| **Impact business potentiel** | Fuite de secrets industriels vers le domaine public, violation de la confidentialité des données clients entraînant des sanctions financières de la CNIL et rupture de confiance des clients. |
| **Cotation Brute** | Vraisemblance (1-4) = **4** \| Gravité (1-4) = **3** \| **Criticité Brute = 12 / 16 (Risque Critique)** |
| **Stratégie de traitement** | **Réduire / Atténuer** : Blocage technique des URL d'IA non sécurisées sur le pare-feu, charte d'usage et sensibilisation, mise à disposition d'une plateforme d'IA interne sécurisée. |
| **Cotation Résiduelle** | Vraisemblance (1-4) = **1** \| Gravité (1-4) = **3** \| **Criticité Résiduelle = 3 / 16 (Risque Faible / Acceptable)** |

### 4. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **~100 millions de dollars** : le montant en jeu quand l'assureur de Mondelez a invoqué l'exclusion « acte de guerre » après NotPetya (litige ouvert en 2018, accord confidentiel en 2022).
    - **1,4 milliard de dollars** : la réclamation de Merck pour NotPetya — la justice américaine a jugé (2023) que l'exclusion de guerre ne s'appliquait pas à cette cyberattaque, avant un accord final (2024).
    - **2023** : le marché de l'assurance (exigences du Lloyd's de Londres) réécrit ses clauses d'exclusion pour les attaques soutenues par des États — conséquence directe de ces contentieux.

**Comment lire ces chiffres ?** (1) Le transfert de risque a des limites écrites en petits caractères. (2) La qualification juridique d'une cyberattaque (crime ? guerre ?) vaut des milliards. (3) Le marché s'adapte : les polices d'aujourd'hui exigent un socle de sécurité et précisent leurs exclusions — lire AVANT de signer.

### 5. Deux affaires réelles : l'« acte de guerre » et le bras de fer à 1,4 milliard

#### Cas n°1 — Mondelez vs Zurich (2018-2022) : quand l'assureur dit « c'est la guerre »

Juin 2017 : **NotPetya** (B03) ravage des milliers d'entreprises. Parmi les victimes collatérales, le géant agroalimentaire **Mondelez** (Oreo, Milka...) : des milliers de serveurs et de portables détruits, la logistique paralysée — environ **100 millions de dollars** de dégâts déclarés à son assureur, Zurich. Réponse de l'assureur : refus d'indemniser, au titre de la clause d'**exclusion des actes de guerre** — les États-Unis et leurs alliés venaient d'attribuer publiquement NotPetya à un sabotage étatique russe visant l'Ukraine. Mondelez attaque en justice en 2018 ; l'affaire, suivie par toute l'industrie, se conclut par un **accord confidentiel en 2022**.

**Ce que ce cas illustre :** « Transférer » un risque ne le fait pas disparaître — le contrat a des exclusions, et l'attribution géopolitique d'une attaque (B02) peut se retourner contre la victime ; une police d'assurance se lit AVANT le sinistre, exclusions comprises ; et l'incertitude juridique est elle-même un risque : quatre ans de procédure avant de connaître le sort de 100 M$.

#### Cas n°2 — Merck (2017-2024) : la justice tranche à 1,4 milliard

Même attaque, autre géant : le laboratoire pharmaceutique **Merck** chiffre ses dégâts NotPetya à **1,4 milliard de dollars** (40 000 machines touchées, production de vaccins perturbée) et réclame l'indemnisation à ses assureurs — qui invoquent la même exclusion de guerre. Cette fois, la justice va au bout du raisonnement : les tribunaux du New Jersey donnent **raison à Merck** (confirmé en appel en 2023) — la clause, rédigée pour des conflits armés traditionnels, ne pouvait s'appliquer telle quelle à une cyberattaque touchant des civils hors zone de guerre. Un accord définitif intervient en 2024, avant que la Cour suprême de l'État ne se prononce.

**Ce que ce cas illustre :** la même clause, deux issues différentes — le langage contractuel hérité du monde physique s'applique mal au cyber ; la victoire de Merck a poussé tout le marché à **réécrire** ses exclusions (exigences du Lloyd's, 2023) : les contrats récents définissent précisément les attaques étatiques exclues ; et pour l'acheteur d'assurance, la leçon est opérationnelle — faire relire les clauses cyber par un juriste vaut quelques milliers d'euros... contre 1,4 milliard d'incertitude.

!!! tip "📊 Sondage Livestorm n°5 — Et chez vous ? (sondage d'opinion, pas de bonne réponse)"
    **Question :** Votre organisation dispose-t-elle d'une assurance cyber ?

    - A) Oui — et je sais en gros ce qu'elle couvre
    - B) Oui, je crois — mais j'ignore ce qu'elle couvre et exige
    - C) Non / Je ne sais pas

    **Débrief mentor :** Sondage d'opinion — selon les baromètres du secteur (AMRAE), l'assurance cyber reste très concentrée sur les grandes entreprises : dans les PME, C domine largement. Deux messages : (1) l'assurance est un levier de TRANSFERT utile, mais elle exige désormais un socle (MFA, sauvegardes, EDR — le questionnaire de souscription ressemble à notre parcours !) ; (2) si vous avez répondu B, la question de lundi matin s'impose : que couvre notre police, et surtout — qu'exclut-elle ? Mondelez l'a découvert après le sinistre.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    En comité de direction, vous présentez un risque coté 9/16 (élevé) avec un plan de réduction à 20 k€. Le directeur général tranche, à l'oral : « Trop cher, on prend le risque. On passe au point suivant. » **Tapez A, B ou C dans le chat :**

    - A) Acter la décision : le DG a tranché, le sujet est clos.
    - B) Respecter la décision... et la faire **formaliser par écrit** : fiche d'acceptation du risque, cotation, motivation, signature de la Direction, date de réexamen. ✅
    - C) Mettre en place le plan de réduction discrètement, sans le dire : c'est pour le bien de l'entreprise.

    **Débrief mentor :** B — accepter un risque est une stratégie **légitime** (parfois la bonne !), mais c'est une décision de gouvernance : elle se documente, se signe et se réexamine (l'audit demandera la preuve — rappel B13 : ce qui n'est pas écrit n'existe pas). A laisse le RSSI porter seul, de fait, une décision qui n'est pas la sienne ; C est une faute professionnelle (dépense non autorisée, gouvernance contournée) — et si le RSSI est convaincu que le refus est dangereux, l'écrit est précisément son outil pour le dire. La formule : l'acceptation orale n'engage que celui qui l'écoute.

---

### Questions de réflexion
1. Quelle est la différence entre le risque *Brut* et le risque *Résiduel* ? Pourquoi un risque résiduel n'est-il presque jamais égal à zéro ?
2. Une entreprise décide d'acheter une cyber-assurance pour couvrir les pertes financières en cas de rançongiciel. A-t-elle éliminé son risque ? Quelle composante du risque (vraisemblance ou gravité de l'impact) l'assurance permet-elle de transférer ?
3. Dans les affaires Mondelez et Merck, la même clause d'exclusion a produit deux issues différentes. Qu'est-ce que cela nous apprend sur le traitement « Transférer » — et que vérifieriez-vous aujourd'hui avant de signer une police cyber ?

**Corrigé / Éléments de réponse :**

1. Le risque brut est le risque initial sans aucune protection. Le risque résiduel est celui qui reste après les mesures de sécurité. Il n'est jamais nul car la sécurité parfaite est impossible.
2. L'assurance ne réduit ni la probabilité (vraisemblance) de l'attaque ni la fuite de données ; elle transfère uniquement l'impact financier — et encore, dans les limites des plafonds et exclusions du contrat.
3. Le transfert repose sur un contrat, donc sur son interprétation : ambiguïté = risque juridique. Avant de signer : les exclusions (guerre/attaques étatiques, négligence), les plafonds et franchises, les exigences de sécurité (MFA, sauvegardes) dont le non-respect annule la couverture, et les délais/procédures de déclaration (LOPMI : plainte sous 72 h pour les rançons en France).

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez la gestion des risques cyber à l'aide de l'analogie d'une **expédition d'alpinisme en montagne** :
    - **L'actif critique** est votre vie et celle de votre équipe.
    - **La menace** est le danger naturel : une avalanche ou une tempête.
    - **La vulnérabilité** est le fait de ne pas avoir de doudoune chaude ou d'attaquer la paroi sans cordes d'assurance.
    - **Le traitement du risque** se décline en 4 options :
      - **Réduire (Mitigation)** : Porter un casque, prendre une corde et un guide de haute montagne (mettre un pare-feu et MFA).
      - **Transférer (Transfer)** : Souscrire à une assurance assistance rapatriement en hélicoptère (assurance cyber) — en lisant bien si elle couvre l'altitude où vous grimpez !
      - **Éviter (Avoidance)** : Annuler l'ascension de ce sommet dangereux et choisir une randonnée plate (renoncer à utiliser une application risquée).
      - **Accepter (Acceptance)** : Savoir que le risque existe, mais décider d'y aller quand même — en le disant à voix haute, par écrit, avant de partir.

**Exemple d'application professionnelle :**
Une PME souhaite ouvrir sa base de données de production à ses prestataires externes. L'analyse de risques montre qu'une mauvaise configuration peut entraîner le vol de la base. Pour traiter ce risque, le RSSI décide de réduire le risque en imposant un accès via un VPN avec MFA, et de le transférer en mettant à jour la police d'assurance cyber — après vérification de ses exclusions.

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour évaluer, documenter et suivre les plans de traitement des risques de sécurité (méthode EBIOS RM ou ISO 27005) :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Archer GRC (anciennement RSA Archer)** : Suite logicielle haut de gamme et leader historique pour la gestion intégrée des risques (IRM) et l'évaluation quantitative des risques cyber.
    *   **Tenable Risk Manager** : Solution d'évaluation continue de l'exposition aux risques techniques sur l'Active Directory et les infrastructures associées.
    *   **ServiceNow Risk Management** : Intégration complète du flux d'évaluation des risques dans les processus de gestion des services informatiques (ITIL).
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **Monarc** : Outil de gestion des risques open-source réputé pour sa conformité avec ISO 27005, permettant de générer automatiquement des arbres de menaces et des plans de traitement.
    *   **PIA Tool (CNIL)** : Le logiciel open-source de la CNIL qui permet de mener une analyse de risques sur les données personnelles en évaluant l'impact et la vraisemblance des menaces de manière structurée.

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après le mini-scénario.

*   **📊 Sondage n°6 :** Pourquoi le risque résiduel n'est-il presque jamais égal à zéro ?
    *   A) Parce que les outils de sécurité sont mal conçus
    *   B) Parce que la sécurité parfaite n'existe pas : les mesures réduisent le risque sans l'éliminer ✅
    *   C) Parce que les assureurs l'interdisent contractuellement
*   **📊 Sondage n°7 :** Que transfère exactement une cyber-assurance ?
    *   A) La vraisemblance de l'attaque : les pirates évitent les entreprises assurées
    *   B) La totalité du risque : l'entreprise n'a plus rien à faire
    *   C) L'impact financier (dans les limites du contrat) — ni la probabilité, ni les données fuitées, ni la réputation ✅
*   **📊 Sondage n°8 :** Quelle est la formulation correcte d'un risque dans un registre ?
    *   A) « Le pare-feu est vieux »
    *   B) « Une menace exploite une vulnérabilité pour atteindre un actif et causer un impact » ✅
    *   C) « L'informatique, c'est risqué »

**Éléments de débriefing (pour le mentor) :**

- N°6 : c'est la cotation résiduelle du sondage n°4 — V=1 mais jamais 0, et la gravité peut rester entière. Le résiduel restant s'accepte... par écrit.
- N°7 : Mondelez et Merck en une question — et même l'impact financier n'est transféré que « dans les limites du contrat » : plafonds, franchises, exclusions.
- N°8 : la grammaire du risque — menace × vulnérabilité × actif → impact. « Le pare-feu est vieux » est une vulnérabilité, pas un risque : il manque le scénario et la conséquence.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Cybersecurity Governance and Risk Management - Part 2"* (durée estimée : 1h30).
*   **Recherche de méthodologie** : Rechercher les grandes lignes de la méthode d'analyse de risques française **EBIOS RM** (développée par l'ANSSI) pour comprendre comment l'État et les grandes organisations modélisent les scénarios de cyberattaques.
*   [Cybermalveillance — Assurance cyber](https://www.cybermalveillance.gouv.fr/)
*   [ANSSI — La méthode EBIOS Risk Manager](https://cyber.gouv.fr/la-methode-ebios-risk-manager)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Choix des stratégies de traitement des risques.
*   **📊 Sondage Livestorm n°9 :** L'analyse de risques montre qu'une coupure électrique majeure paralyserait l'entrepôt. Le coût d'un groupe électrogène est de 50 000 €, tandis que la perte estimée d'une panne est de 5 000 €. Quelle décision de traitement des risques devez-vous proposer ?
    *   A) Réduire le risque en achetant le groupe électrogène.
    *   B) Accepter le risque (ou souscrire une assurance spécifique) car le coût de la mesure dépasse largement la perte potentielle ✅
    *   C) Ignorer l'analyse de risques.
*   **Guide d'animation (pour le mentor) :** La notion d'adéquation coût/bénéfice : la sécurité doit être proportionnée aux enjeux — dépenser 50 k€ pour éviter 5 k€ de perte est une mauvaise décision de gestion. Et l'acceptation, on l'a vu, se formalise par écrit. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **L'équation du risque** | Une menace exploite une vulnérabilité sur un actif → un impact, avec une vraisemblance. |
| **Criticité** | Vraisemblance (1-4) × Gravité (1-4) = 1 à 16 ; faible (1-4), moyen (5-8), critique (9-16). |
| **Brut vs Résiduel** | Avant / après mesures — le résiduel n'est jamais nul, et il s'accepte par écrit. |
| **Réduire** | Abaisser la vraisemblance (EDR, MFA) ou l'impact (sauvegardes) — la stratégie la plus courante. |
| **Transférer** | Assurance ou externalisation — l'impact financier seulement, dans les limites du contrat (Mondelez, Merck). |
| **Éviter** | Renoncer à l'activité ou à la technologie à l'origine du risque. |
| **Accepter** | Décision de Direction, formalisée, signée, datée, réexaminée. |
| **EBIOS RM** | La méthode française (ANSSI) — la même logique, industrialisée en ateliers. |

**La règle d'or de la session :** le risque s'arbitre, ne s'élimine pas — cotez (V × G), traitez (réduire, transférer, éviter, accepter), écrivez. Et souvenez-vous de Mondelez : un risque « transféré » sans lire les exclusions du contrat est un risque accepté sans le savoir.
