# Session B15 — Conformité & réglementations vie privée
Parcours : B 20 sessions  |  Module : D — Gouvernance, risques & conformité  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30) — inclut l'**Atelier de Synthèse 3**

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Les Fondamentaux du RGPD (et les deux paliers de sanctions)
    - Le rôle de la CNIL et le Délégué à la Protection des Données (DPO)
    - Deux affaires réelles : Google (50 M€, CNIL 2019) et Clearview AI (20 M€ + astreinte)
    - L'**Atelier de Synthèse 3** : la matrice de risques de MedDistri
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Le **RGPD** impose des principes stricts (minimisation, limitation de conservation, consentement libre) pour protéger la vie privée des résidents européens.
*   En cas de violation de données personnelles, l'entreprise doit notifier la **CNIL sous 72 heures maximum** après en avoir pris connaissance.
*   Les sanctions prévues par le RGPD suivent **deux paliers** : jusqu'à 10 M€ ou 2 % du CA mondial pour certains manquements, jusqu'à **20 M€ ou 4 % du CA mondial** pour les plus graves — le montant le plus élevé étant retenu.
*   Le **DPO** orchestre la conformité interne, tient le registre des traitements obligatoire et fait l'interface avec l'autorité de contrôle.

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer les obligations réglementaires majeures d'un organisme au titre du RGPD (registre, consentement, sécurité, notification sous 72 h).
* Identifier le rôle d'autorité de la CNIL et mesurer les risques financiers et d'image associés aux sanctions pour non-conformité.
* Auditer une politique de confidentialité d'entreprise pour en extraire les clauses non conformes et proposer des corrections adaptées.
* Coter collectivement les risques majeurs de la PME MedDistri dans une matrice 4x4 (**Atelier de Synthèse 3**, par sondages et chat).

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** Quelle est, à ce jour, l'amende RGPD record infligée en Europe ?

    - A) 50 millions d'euros
    - B) 1,2 milliard d'euros ✅
    - C) 4 millions d'euros

    **Débrief mentor :** Réponse B : **1,2 milliard d'euros** contre Meta en 2023 (transferts de données vers les États-Unis sans garanties suffisantes) — et la réponse A n'est pas anodine : 50 M€, c'est l'amende infligée à Google par la CNIL en 2019, la première grande sanction du RGPD, que nous décortiquerons ce soir. Le message d'ouverture : la conformité n'est pas de la paperasse — c'est du droit avec des dents, et les amendes se comptent désormais en pourcentage du chiffre d'affaires MONDIAL. Ce soir : vos obligations, vos interlocuteurs (CNIL, DPO)... et l'Atelier de Synthèse 3 où vous coterez les risques de MedDistri.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Les deux paliers de sanctions — et ce que la CNIL sanctionne vraiment**
Précision juridique à donner exactement : le RGPD prévoit **deux plafonds** — jusqu'à 10 M€ ou 2 % du CA mondial (manquements « organisationnels » : registre, coopération, sécurité insuffisante...) et jusqu'à **20 M€ ou 4 %** (violations des principes fondamentaux : base légale, consentement, droits des personnes, transferts) — le montant le plus élevé étant retenu. En pratique, lisez des sanctions CNIL récentes avec les apprenants : on y trouve des manquements très concrets — mots de passe stockés en clair (rappel B10 !), absence de chiffrement, durées de conservation illimitées, défaut de minimisation. La conformité et la sécurité technique sont les deux faces de la même pièce.

**2. Privacy by Design et l'AIPD**
Le principe de **protection dès la conception** (*Privacy by Design*, article 25) : la conformité ne se rajoute pas à la fin — elle se conçoit (minimisation dans le formulaire, pseudonymisation en base, durées de purge automatiques). Pour les traitements à risque élevé, l'**AIPD** (Analyse d'Impact relative à la Protection des Données) est obligatoire — l'outil PIA de la CNIL la structure gratuitement. Le lien avec B14 est direct : l'AIPD EST une analyse de risques, centrée sur les personnes concernées plutôt que sur l'entreprise.

**3. Le paysage réglementaire s'élargit : NIS2, DORA, IA Act**
Situez le RGPD dans la vague réglementaire européenne (sans détailler) : **NIS2** (sécurité des entités essentielles et importantes — vue en B13), **DORA** (résilience numérique du secteur financier, applicable depuis janvier 2025), **IA Act** (premier cadre mondial sur l'intelligence artificielle, entré en vigueur en 2024, application progressive). Message : le métier de la conformité cyber est en pleine expansion — et les mécanismes appris ce soir (registre, analyse d'impact, notification, responsabilisation) se retrouvent dans tous ces textes.

---

### Glossaire

*   **AIPD (Analyse d'Impact)** — Étude obligatoire avant tout traitement de données à risque élevé, évaluant les impacts sur la vie privée des personnes concernées.
*   **CNIL** — Commission Nationale de l'Informatique et des Libertés. Autorité administrative publique française de régulation des données personnelles.
*   **Consentement (RGPD)** — Acte positif clair, libre, spécifique et éclairé — pas de cases pré-cochées, pas de consentement forcé.
*   **Donnée personnelle** — Toute information se rapportant à une personne physique identifiée ou identifiable de manière directe ou indirecte.
*   **DPO (Data Protection Officer)** — Délégué à la Protection des Données. Expert interne ou externe chargé de veiller à l'application du RGPD au sein de l'organisme.
*   **Minimisation des données** — Principe du RGPD exigeant de ne collecter que les données personnelles adéquates, pertinentes et limitées au strict nécessaire.
*   **Privacy by Design** — Principe imposant d'intégrer la protection des données dès la conception d'un produit ou d'un traitement, et non après coup.
*   **Registre des traitements** — Document interne obligatoire listant tous les traitements de données personnelles (qui, quoi, pourquoi, combien de temps, quelles sécurités).
*   **RGPD (Règlement Général sur la Protection des Données)** — Règlement européen (2018) imposant des obligations sur la protection et le traitement des données personnelles.
*   **Traitement de données** — Toute opération ou ensemble d'opérations portant sur des données personnelles (collecte, hébergement, modification, transfert).

---

### Concepts clés

!!! info "À retenir"
    Le RGPD tient en une idée : les données personnelles appartiennent aux **personnes**, pas aux entreprises qui les collectent. Tout en découle — le consentement libre, la minimisation, les durées limitées, les droits d'accès et d'effacement, la notification sous 72 h... et des sanctions calculées en pourcentage du chiffre d'affaires mondial pour que même les géants les sentent passer.

### 1. Les Fondamentaux du RGPD
Entré en application en mai 2018, le **RGPD** (Règlement Général sur la Protection des Données) est le cadre juridique européen régissant la collecte et le traitement des données à caractère personnel.

*   **Donnée à caractère personnel** : Toute information se rapportant à une personne physique identifiée ou identifiable directement ou indirectement (ex. un nom, une adresse email, un numéro de téléphone, une adresse IP, des données de localisation, ou un numéro de sécurité sociale).
*   **Traitement** : Toute opération appliquée à des données personnelles (la collecte, l'enregistrement, l'organisation, la conservation, la modification, la consultation, l'utilisation ou la suppression).

#### Les 5 devoirs clés des entreprises sous le RGPD :
1.  **Transparence et Consentement** : L'utilisateur doit être informé clairement de l'usage de ses données (but ou *finalité*). Le consentement doit être un acte positif clair, libre, spécifique et éclairé (ex. pas de cases pré-cochées pour l'envoi de publicités).
2.  **Minimisation des données** : Collecter uniquement les données strictement nécessaires au traitement (ex. un site e-commerce n'a pas besoin de collecter la profession de l'acheteur pour livrer un colis). C'est aussi le meilleur des leviers de sécurité : une donnée non collectée ne peut pas fuiter (rappel du sondage n°4 de B14 : le levier qui abaisse la **gravité**).
3.  **Limitation de la conservation** : Les données ne peuvent pas être stockées indéfiniment. Une durée de conservation précise doit être définie (ex. 3 ans maximum pour des données de prospects inactifs).
4.  **Registre des traitements** : Document interne obligatoire listant tous les traitements de données personnelles effectués au sein de l'entreprise (qui, quoi, pourquoi, combien de temps, quelles mesures de sécurité).
5.  **Notification des violations sous 72 heures** : En cas de violation de données personnelles (piratage, fuite), l'entreprise a l'obligation légale de notifier l'autorité de contrôle (**la CNIL** en France) dans un délai maximal de **72 heures après en avoir pris connaissance** — week-ends et jours fériés compris. Si la fuite présente un risque élevé pour les personnes concernées, l'entreprise doit également les informer individuellement.

### 2. Le rôle de la CNIL et les sanctions
La **CNIL** (*Commission Nationale de l'Informatique et des Libertés*) est le gendarme des données personnelles en France.

*   *Missions* : Conseiller les entreprises, informer les citoyens sur leurs droits (droits d'accès, de rectification, de suppression ou "droit à l'oubli") et contrôler les systèmes d'information (audits en ligne ou sur site physique).
*   *Sanctions — les deux paliers du RGPD* : selon la gravité du manquement, l'amende administrative peut atteindre **10 millions d'euros ou 2 % du chiffre d'affaires annuel mondial** (manquements organisationnels : registre, sécurité, coopération), et jusqu'à **20 millions d'euros ou 4 % du CA mondial** pour les violations les plus graves (principes fondamentaux, consentement, droits des personnes) — **le montant le plus élevé étant à chaque fois retenu**. S'y ajoute le préjudice d'image lié à la publication publique de la sanction.

### 3. Le Délégué à la Protection des Données (DPO — Data Protection Officer)
Le **DPO** est le pilote de la conformité au sein de l'entreprise.

*   *Rôle* : Il conseille la direction sur la protection de la vie privée, s'assure de la tenue à jour du registre des traitements, mène des Analyses d'Impact sur la Protection des Données (AIPD) pour les projets à risque élevé, et sert de point de contact unique pour les demandes des citoyens ainsi que pour la CNIL en cas de contrôle ou d'incident.
*   *DPO et RSSI, le duo* : le RSSI protège le patrimoine de l'entreprise, le DPO garantit les droits des personnes — en cas de fuite, l'un mène l'enquête technique, l'autre pilote les notifications légales. Deux casquettes distinctes, une coordination obligatoire.

### Activité — L'audit de la charte de confidentialité (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Affichez l'extrait de charte rédigé par le marketing d'EcoLog pour sa nouvelle plateforme e-commerce. Trois clauses, trois votes : pour chacune, les participants identifient l'infraction. Débriefez avec la correction conforme après chaque vote.

> **Extrait de la charte proposée par le marketing d'EcoLog :**
> *« EcoLog collecte vos informations lors de votre commande. (Clause A) Nous conservons vos données de carte bancaire de manière définitive afin de faciliter le paiement de vos futurs achats. (Clause B) En créant votre compte, vous acceptez sans réserve que vos données personnelles soient revendues à nos partenaires commerciaux sans possibilité d'opposition de votre part. (Clause C) Si vous souhaitez modifier ou supprimer vos données personnelles, vous devez formuler votre demande par courrier recommandé avec accusé de réception à l'attention de la direction au siège social. »*

*   **📊 Sondage n°2 — Clause A (les cartes bancaires « conservées définitivement ») :** Quel est le problème ?
    *   A) Aucun : c'est un service pratique pour le client
    *   B) Violation de la limitation de conservation : les données bancaires se suppriment après la transaction, sauf consentement explicite (et stockage sécurisé) ✅
    *   C) Le seul problème est technique : il suffirait de mieux chiffrer
*   **📊 Sondage n°3 — Clause B (la revente « sans opposition possible ») :** Quel est le problème ?
    *   A) Consentement forcé et suppression d'un droit : l'inscription ne peut pas être conditionnée à la revente, et le droit d'opposition ne se supprime pas ✅
    *   B) Aucun : l'utilisateur a accepté en créant son compte
    *   C) Il manque seulement la liste nominative des partenaires
*   **📊 Sondage n°4 — Clause C (le courrier recommandé au siège) :** Quel est le problème ?
    *   A) Aucun : l'écrit protège juridiquement l'entreprise
    *   B) Le délai de réponse n'est pas précisé, c'est tout
    *   C) L'exercice des droits est rendu inutilement complexe : il doit être aussi simple que la collecte (e-mail, formulaire) ✅

**Éléments de débriefing (pour le mentor) :**

- N°2 : la conservation illimitée viole la **limitation de conservation** ; la correction conforme : suppression après transaction, case d'option NON pré-cochée pour l'enregistrement, stockage sécurisé (tokenisation). Et non, le chiffrement (C) ne légalise pas une conservation illégale.
- N°3 : double infraction — le consentement doit être **libre** (pas de chantage à l'inscription) et le **droit d'opposition** est inaliénable ; la correction : opt-in facultatif, retirable à tout moment.
- N°4 : le principe de **symétrie** — exercer ses droits doit être aussi simple que donner ses données : un clic pour s'inscrire, un e-mail (dpo@ecolog.fr) ou un formulaire pour s'effacer. Le recommandé est une entrave caractérisée.
- Conclure : « trois clauses, trois infractions — et un marketing de bonne foi : la conformité se conçoit dès la rédaction (*Privacy by Design*), pas après la mise en ligne. »

### 4. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **1,2 milliard d'euros** : l'amende RGPD record, infligée à Meta en 2023 (transferts de données UE → États-Unis sans garanties suffisantes).
    - **50 millions d'euros** : l'amende infligée à Google par la CNIL en 2019 — la première grande sanction du RGPD (transparence et consentement), confirmée par le Conseil d'État en 2020.
    - **20 millions d'euros + 5,2 millions d'astreinte** : Clearview AI, sanctionnée par la CNIL en 2022 pour sa base de reconnaissance faciale, puis frappée d'une astreinte en 2023 pour ne pas s'être mise en conformité.

**Comment lire ces chiffres ?** (1) Les plafonds en % du CA mondial rendent la sanction dissuasive même pour les géants. (2) Le RGPD s'applique aux entreprises étrangères dès qu'elles traitent des données de résidents européens (Clearview est américaine). (3) Ignorer la sanction coûte encore plus cher : l'astreinte court par jour de retard.

### 5. Deux affaires réelles : la première grande amende et la société qui a dit non

#### Cas n°1 — Google vs CNIL (2019) : 50 millions pour un consentement introuvable

Janvier 2019, huit mois après l'entrée en application du RGPD : la CNIL inflige à **Google** une amende de **50 millions d'euros** — la première sanction d'envergure du règlement, sur plaintes d'associations (noyb, La Quadrature du Net). Les griefs ne portent pas sur un piratage, mais sur la **conception même** du parcours utilisateur : information diluée dans une arborescence de pages difficile à parcourir (défaut de **transparence**), et consentement à la personnalisation publicitaire ni **spécifique** (un accord global pré-configuré) ni **éclairé**. Google conteste ; le **Conseil d'État confirme** la sanction en 2020.

**Ce que ce cas illustre :** pas besoin de fuite pour être sanctionné — la CNIL juge aussi l'ergonomie du consentement (les cases pré-cochées et les parcours décourageants sont des infractions, pas des astuces) ; le RGPD s'applique aux géants américains dès lors qu'ils ciblent des résidents européens ; et la conformité se joue dans le **design** des produits — exactement le *Privacy by Design*.

#### Cas n°2 — Clearview AI (2022-2023) : 20 millions... plus l'astreinte

**Clearview AI**, société américaine, a constitué une base de plus de 30 milliards d'images de visages **aspirées sur Internet** (réseaux sociaux compris) pour vendre un service de reconnaissance faciale, notamment à des forces de l'ordre. Des résidents français figurent dans la base — sans le savoir, sans consentement, sans base légale. En 2022, la CNIL sanctionne : **20 millions d'euros** (le plafond), injonction de cesser la collecte et d'effacer les données des personnes concernées. Clearview ignore la décision... et la CNIL prononce en 2023 une **astreinte de 5,2 millions d'euros** supplémentaires. D'autres autorités européennes (Italie, Grèce, Royaume-Uni) ont sanctionné de même.

**Ce que ce cas illustre :** « les données étaient publiques » n'est PAS une base légale — la publication d'une photo n'autorise pas sa réutilisation biométrique ; les données biométriques sont des données **sensibles**, au régime renforcé ; et l'extraterritorialité a ses limites (recouvrer l'amende est difficile) mais les sanctions en chaîne ferment le marché européen — la conformité devient une condition d'accès au marché.

### Atelier de Synthèse 3 — La matrice de risques de MedDistri (Sondage Livestorm n°5 + chat)

**Le principe** (voir [Ateliers de Synthèse](../projet/B_miniprojets.md)) : ~20 minutes pour appliquer la méthode de B14 au cas MedDistri, en préparation du grand atelier final. Le mentor présente **trois scénarios de menace** ; le public cote, débat et propose les traitements — la matrice 4x4 se remplit en direct.

**Les trois scénarios à l'écran :**

1. **Rançongiciel** sur la base de données comptable (serveur de gestion).
2. **Vol de l'ordinateur portable** d'un commercial en déplacement (données clients à bord).
3. **Usurpation d'identité du dirigeant** pour une fraude au virement (le BEC de B04).

*   **📊 Sondage n°5 — La cotation collective :** Pour le scénario n°1 (rançongiciel sur la comptabilité), comment évaluez-vous l'**impact** sur l'activité de MedDistri ?
    *   A) Faible (1) — quelques heures de gêne
    *   B) Moyen (2) — un service ralenti quelques jours
    *   C) Majeur (3) — la facturation et les salaires bloqués ✅ *(défendable)*
    *   D) Critique (4) — la survie de l'entreprise menacée ✅ *(défendable)*

**Déroulé de l'atelier (pour le mentor) :**

1. **Présentation (3 min)** : les trois scénarios, et le rappel de la grille (V × G, 1 à 16).
2. **Vote n°5 + débat (7 min)** : lancer le sondage sur l'impact du scénario 1 — puis faire **justifier dans le chat** : *« défendez votre cotation en une phrase ! »* (attendu côté C : « la compta bloque salaires et facturation » ; côté D : « une PME sans trésorerie ni facturation meurt en quelques semaines »). Trancher collectivement (3 ou 4 — les deux se défendent : c'est la discussion qui compte), coter la vraisemblance à l'oral avec le chat (élevée : les rançongiciels frappent d'abord les PME — ANSSI, B01), placer le risque dans la matrice.
3. **Les deux autres scénarios au chat (7 min)** : pour le vol du portable et la fraude au virement, demander directement au chat : *« V ? G ? et surtout : quel traitement de B14 proposez-vous ? »* — attendu : portable → chiffrement du disque (B08) + effacement à distance = réduire l'impact ; fraude au virement → procédure de contre-appel (B04) + double validation = réduire la vraisemblance. Remplir la matrice en direct.
4. **Synthèse (3 min)** : la matrice complète à l'écran — « trois risques cotés, trois plans de traitement, en vingt minutes : c'est un comité des risques que vous venez de tenir. Et remarquez : chaque traitement vient d'une session du parcours. Le grand atelier final (B20) assemblera TOUT. »

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Vendredi, 18h. Votre équipe confirme une fuite de données clients chez MedDistri. Le prestataire vous glisse : « Le délai de notification de 72 heures, c'est en jours ouvrés — on a jusqu'à mercredi, profitez du week-end. » **Tapez A, B ou C dans le chat :**

    - A) Il a raison : les délais légaux se comptent toujours en jours ouvrés.
    - B) Faux : les 72 heures courent dès la prise de connaissance, week-end compris — on documente et on notifie la CNIL sans attendre. ✅
    - C) Peu importe : on ne notifie que si des clients se plaignent.

    **Débrief mentor :** B — le délai de 72 heures court à compter de la **prise de connaissance** de la violation, calendaire, week-ends et jours fériés compris (une notification initiale même incomplète peut être complétée ensuite). A est une légende tenace ; C est le scénario Uber de B13 — la non-notification transforme la victime en fautif. Le réflexe : documenter dès la découverte (chronologie, périmètre, mesures) — c'est aussi ce que l'assureur (B14) et l'auditeur (B13) demanderont.

---

### Questions de réflexion
1. Si une entreprise sous-traite le stockage de ses fichiers clients à un hébergeur cloud américain, qui est responsable de la conformité des données personnelles au titre du RGPD : l'entreprise (responsable de traitement) ou l'hébergeur cloud (sous-traitant) ?
2. Quelle est la différence fondamentale entre la "sécurité informatique" classique (gérée par le RSSI) et la "conformité RGPD" (supervisée par le DPO) ? Comment ces deux fonctions doivent-elles collaborer lors d'une fuite de données ?
3. Dans l'affaire Google, aucune donnée n'a fuité — et l'amende a pourtant atteint 50 M€. Qu'est-ce que cela nous apprend sur la nature des obligations RGPD ?

**Corrigé / Éléments de réponse :**

1. Les deux sont responsables. L'entreprise (responsable de traitement) doit s'assurer que le sous-traitant est conforme (contrat, garanties — et vigilance sur les transferts hors UE, cf. l'amende Meta), et le sous-traitant doit garantir la sécurité des données hébergées. Écho direct à la responsabilité partagée de B11.
2. Le RSSI protège le patrimoine de l'entreprise. Le DPO s'assure du respect des droits des personnes. En cas de fuite, ils coordonnent l'enquête technique (RSSI) et les notifications légales (DPO).
3. Le RGPD n'est pas qu'une réglementation de sécurité : il encadre la **loyauté** du traitement — transparence, consentement, finalités. On peut être inattaquable techniquement et lourdement sanctionné pour la conception même de son parcours utilisateur.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez le respect du RGPD et de la conformité en cybersécurité comme les **normes d'hygiène obligatoires d'un restaurant** :
    - La loi vous impose d'avoir une cuisine propre, d'afficher la provenance des viandes et de jeter les produits périmés sous peine de fermeture par l'inspecteur d'hygiène (la CNIL).
    - **Le consentement (Opt-In)** correspond au fait de demander explicitement au client s'il souhaite des épices dans son plat, plutôt que de lui en mettre d'office et de le forcer à les retirer (Opt-Out).
    - **La minimisation des données** consiste à ne pas demander le groupe sanguin de votre client simplement pour lui livrer une pizza. On ne demande que le strict nécessaire (nom, adresse).
    - **Le DPO (Délégué à la Protection)** est le chef hygiéniste du restaurant qui contrôle régulièrement les frigos et forme les cuisiniers aux règles légales.

**Exemple d'application professionnelle :**
Une plateforme e-commerce française collecte les données de ses clients pour livrer ses produits. Suite à une mise en conformité RGPD, elle modifie son formulaire d'inscription : les cases d'inscription à la newsletter ne sont plus pré-cochées (consentement explicite), et les comptes inactifs depuis plus de 3 ans sont automatiquement supprimés (limitation de la conservation). Elle nomme également un DPO externe.

### Panorama des solutions du marché (Commerciales & Open-Source)

Le maintien de la conformité RGPD et la gestion des cookies/consentements des sites Web s'appuient sur les outils suivants :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **OneTrust Privacy** : Solution leader mondial pour la gestion intégrée du registre de traitement RGPD, le suivi des droits des personnes et la gestion des consentements en ligne (bandeau de cookies).
    *   **Didomi** : Plateforme européenne majeure de gestion du consentement (CMP) et de conformité de la collecte de données privées sur le web et les applications mobiles.
    *   **Axeptio** : Solution de gestion des cookies reconnue pour son approche visuelle ludique et ergonomique facilitant le respect du RGPD pour les PME.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **PIA Tool (CNIL)** : Outil officiel open-source et gratuit de la CNIL française pour mener l'Analyse d'Impact relative à la Protection des Données (AIPD/PIA) obligatoire pour les traitements de données sensibles.
    *   **Klaro!** : Gestionnaire de cookies et de consentement web open-source très léger, permettant de bloquer les scripts de suivi tiers sans licence commerciale payante.

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après le mini-scénario.

*   **📊 Sondage n°6 :** Quels sont les plafonds de sanction prévus par le RGPD ?
    *   A) Un plafond unique de 20 M€ pour toutes les infractions
    *   B) Deux paliers : jusqu'à 10 M€ ou 2 % du CA mondial, et jusqu'à 20 M€ ou 4 % pour les manquements les plus graves — le plus élevé retenu ✅
    *   C) 4 % du bénéfice net français
*   **📊 Sondage n°7 :** Une adresse IP est-elle une donnée personnelle au sens du RGPD ?
    *   A) Non : c'est une donnée purement technique
    *   B) Oui : elle permet d'identifier indirectement une personne physique ✅
    *   C) Uniquement si la personne a un site web
*   **📊 Sondage n°8 :** Quel est le rôle du registre des traitements ?
    *   A) Recenser tous les traitements de données personnelles : qui, quoi, pourquoi, combien de temps, avec quelles sécurités ✅
    *   B) Enregistrer les mots de passe des salariés en lieu sûr
    *   C) Lister les cyberattaques subies par l'entreprise

**Éléments de débriefing (pour le mentor) :**

- N°6 : les deux paliers — et le « % du CA mondial » explique le 1,2 Md€ de Meta : le plafond suit la taille de l'entreprise.
- N°7 : la définition est volontairement large — « identifiable directement ou **indirectement** » : IP, localisation, identifiants publicitaires... en font partie.
- N°8 : le registre est la **cartographie** de la conformité — c'est le premier document que la CNIL demande en contrôle, et le premier chantier de toute mise en conformité.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Introduction to Data Privacy and GDPR"* (durée estimée : 1h30).
*   **Activité pratique** : Rendez-vous sur le site de la CNIL (cnil.fr) et lisez le résumé d'une sanction récente prononcée à l'encontre d'une entreprise pour comprendre quels manquements techniques (mots de passe trop faibles, absence de chiffrement) ont été sanctionnés.
*   [CNIL — Comprendre le RGPD](https://www.cnil.fr/fr/comprendre-le-rgpd)
*   [CNIL — Notifier une violation de données](https://www.cnil.fr/fr/notifier-une-violation-de-donnees-personnelles)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Conformité réglementaire des sites internet.
*   **📊 Sondage Livestorm n°9 :** Un site web d'entreprise utilise des traceurs publicitaires. Que devez-vous implémenter pour être conforme aux directives de la CNIL/RGPD ?
    *   A) Un bandeau d'information simple sans bouton de refus.
    *   B) Une plateforme de gestion du consentement (CMP) permettant de refuser ou d'accepter facilement les traceurs avant tout dépôt ✅
    *   C) Rien, les cookies publicitaires ne sont pas réglementés.
*   **Guide d'animation (pour le mentor) :** Refuser doit être **aussi simple** qu'accepter — les bandeaux sans bouton « tout refuser » ont valu des sanctions à plusieurs géants du web. Relier à l'observation de la semaine (les bandeaux repérés par les participants) : qui a vu un bandeau non conforme ? Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Donnée personnelle** | Toute information identifiant directement OU indirectement une personne (IP comprise). |
| **Les 5 devoirs** | Consentement éclairé · minimisation · conservation limitée · registre · notification 72 h. |
| **Les 2 paliers de sanction** | 10 M€ / 2 % du CA mondial — 20 M€ / 4 % pour les plus graves (le plus élevé retenu). |
| **CNIL** | Le gendarme français : conseil, contrôle, sanction — et publication des décisions. |
| **DPO** | Le pilote de la conformité : registre, AIPD, point de contact CNIL — en duo avec le RSSI. |
| **Privacy by Design** | La conformité se conçoit dès le produit (minimisation, pseudonymisation, purges). |
| **Notification 72 h** | Délai calendaire dès la prise de connaissance — week-ends compris (cas Uber en contre-exemple). |

**La règle d'or de la session :** les données appartiennent aux personnes — collectez le minimum, dites la vérité sur l'usage, facilitez les droits, notifiez sous 72 heures... et souvenez-vous de Google et Clearview : la conformité n'est pas une option technique, c'est une condition d'accès au marché européen.
