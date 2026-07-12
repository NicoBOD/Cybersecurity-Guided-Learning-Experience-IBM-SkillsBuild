# Support de cours — Session 05 : Gouvernance, risque, conformité & vie privée
Parcours : A 8 sessions  |  Module : GRC & Vie Privée  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - La Gouvernance et ses référentiels : ISO 27001 & NIST CSF 2.0
    - La Gestion des Risques : Évaluer pour mieux investir
    - La Conformité et la Vie Privée : Le RGPD
    - Les sanctions en chiffres et des amendes réelles : Google (50 M€), Meta (1,2 Md€), Clearview AI (20 M€)
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

La cybersécurité n'est pas uniquement une affaire de configurations techniques et de pare-feux. Pour être efficace, elle doit être intégrée dans la stratégie globale de l'entreprise à travers la Gouvernance, la Gestion des Risques et la Conformité (GRC). Ce support de cours détaille le cadre organisationnel de la cybersécurité. Vous découvrirez les référentiels de sécurité internationaux indispensables comme la norme ISO 27001 et le NIST CSF (dans sa version 2.0), qui guident les entreprises dans la structuration de leur sécurité. Nous étudierons ensuite la méthodologie de l'analyse de risques pour apprendre à prioriser les efforts de protection selon l'impact et la vraisemblance des menaces. Enfin, nous aborderons le RGPD, le règlement qui encadre la protection de la vie privée et des données personnelles, devenu un enjeu juridique et de réputation majeur — les amendes réelles étudiées dans cette session, dont un record à plus d'un milliard d'euros, en témoignent.

### Objectifs de la session

À l'issue de cette session, vous serez capable de :

- **Décrire** la place et le rôle de la gouvernance, de la gestion des risques et de la conformité (GRC) dans la stratégie cyber d'une organisation.
- **Identifier** la structure des référentiels internationaux (ISO 27001, NIST CSF 2.0 et ses 6 fonctions).
- **Évaluer** un risque cyber simple (Criticité = Vraisemblance × Impact) et choisir une stratégie de traitement adaptée.
- **Expliquer** les principes directeurs du RGPD (finalité, minimisation, consentement, droits des personnes) et les obligations en cas de violation.

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** À votre avis, quelle amende maximale une autorité comme la CNIL peut-elle infliger en cas de manquement grave au RGPD ?

    - A) 10 000 euros
    - B) 100 000 euros
    - C) Jusqu'à 20 millions d'euros ou 4 % du chiffre d'affaires mondial annuel — le montant le plus élevé étant retenu ✅

    **Débrief mentor :** Réponse C — et ce n'est pas théorique : l'amende record en Europe dépasse le **milliard d'euros** (cas Meta, étudié plus loin). Préciser le mécanisme : deux paliers de sanctions (jusqu'à 10 M€ / 2 % du CA mondial pour certains manquements, jusqu'à 20 M€ / 4 % pour les plus graves), et c'est toujours **le montant le plus élevé** des deux termes qui sert de plafond. Ajouter : la CNIL privilégie d'abord l'accompagnement, mais pour une PME, même une amende « modérée » plus la perte de confiance des clients peuvent être fatales.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. La méthodologie de Gestion des Risques (EBIOS RM)**
Expliquez que le risque ne s'élimine jamais totalement, il se gère. Détaillez les 4 stratégies de traitement du risque :
- *Accepter* le risque (impact faible, coût de protection disproportionné).
- *Réduire* le risque (mettre en place un pare-feu, chiffrer, sauvegarder).
- *Transférer* le risque (souscrire une assurance cyber ou externaliser) — en rappelant qu'on transfère l'impact financier, jamais la responsabilité ni le dommage opérationnel.
- *Éviter* le risque (fermer le service exposé, renoncer au traitement).
Pour aller plus loin : la méthode EBIOS Risk Manager de l'ANSSI structure cette démarche en ateliers (socle de sécurité, sources de risques, scénarios stratégiques et opérationnels, traitement).

**2. Les exigences critiques du RGPD**
Passez du temps sur le RGPD avec des cas concrets :
- Le principe du *"Privacy by Design"* (la protection intégrée dès la conception).
- Le *"Registre des traitements"* obligatoire pour cartographier les données.
- La procédure stricte de *notification sous 72h* à la CNIL en cas de violation de données présentant un risque (art. 33), et l'information des personnes concernées si le risque est élevé (art. 34).
- Le rôle indépendant et stratégique du DPO (Data Protection Officer) par rapport au RSSI.

**3. Les normes ISO 27000 et le NIST CSF 2.0**
Démystifiez l'ISO 27001 : il s'agit d'un système de management (SMSI) basé sur l'amélioration continue (Roue de Deming : Plan-Do-Check-Act), pas d'une liste de logiciels à acheter. Point d'actualité important : le **NIST CSF est passé en version 2.0 en février 2024** et compte désormais **6 fonctions** — la fonction **Gouverner (Govern)** a été ajoutée en socle des cinq historiques, précisément pour rappeler que la cybersécurité se pilote au niveau de la direction. C'est un excellent argument pédagogique : le module GRC que vous animez correspond à cette fonction.

**4. Le paysage réglementaire s'épaissit (à mentionner sans approfondir)**
Au-delà du RGPD : la directive européenne **NIS 2** (déjà évoquée en A1) étend les obligations de cybersécurité à des dizaines de milliers d'entités en France ; le règlement **DORA**, applicable depuis janvier 2025, impose la résilience opérationnelle numérique au secteur financier ; et l'**AI Act** encadre progressivement les systèmes d'intelligence artificielle. Message aux apprenants : la conformité cyber n'est plus une niche juridique, c'est un paysage réglementaire complet — et un argument budgétaire majeur pour les RSSI.

---

### Glossaire

*   **Analyse de risques** — Processus méthodique consistant à identifier, évaluer et hiérarchiser les risques pesant sur les actifs numériques d'un organisme.
*   **BYOD (Bring Your Own Device)** — Pratique consistant pour les collaborateurs à utiliser leurs équipements personnels (ordinateurs, smartphones) dans le cadre professionnel.
*   **CNIL (Commission Nationale de l'Informatique et des Libertés)** — Autorité administrative publique française chargée de veiller au respect de la protection des données personnelles (les équivalents existent dans chaque État européen).
*   **Criticité résiduelle** — Niveau de risque qui subsiste après l'application des mesures de traitement, par opposition à la criticité brute évaluée avant traitement.
*   **Donnée personnelle** — Toute information se rapportant à une personne physique identifiée ou identifiable (ex. nom, e-mail, adresse IP, numéro de téléphone, données de santé).
*   **DPO (Data Protection Officer)** — Délégué à la protection des données chargé de veiller à la conformité de l'organisme vis-à-vis du RGPD.
*   **EBIOS RM (EBIOS Risk Manager)** — Méthode française d'analyse et de management des risques numériques publiée par l'ANSSI.
*   **GRC (Gouvernance, Risques et Conformité)** — Approche intégrée visant à aligner l'informatique sur les objectifs de l'entreprise, à gérer les risques associés et à respecter les obligations réglementaires.
*   **ISO/CEI 27001** — Norme internationale décrivant les exigences pour la mise en place d'un Système de Management de la Sécurité de l'Information (SMSI).
*   **NIST CSF (Cybersecurity Framework)** — Cadre méthodologique américain de référence. Sa version 2.0 (2024) est structurée autour de **6 fonctions** : Gouverner, Identifier, Protéger, Détecter, Répondre, Récupérer.
*   **PSSI (Politique de Sécurité des Systèmes d'Information)** — Document de référence formalisant les règles, directives et exigences de sécurité devant être respectées au sein d'une organisation.
*   **RGPD (Règlement Général sur la Protection des Données)** — Texte réglementaire européen encadrant la collecte, le traitement et le stockage des données personnelles au sein de l'Union européenne ou visant ses résidents.

---

### 1. La Gouvernance et ses référentiels : ISO 27001 & NIST CSF

!!! info "À retenir"
    La gouvernance répond à une question simple : **qui décide quoi, avec quel budget, et qui rend des comptes ?** Sans réponse à cette question, les meilleurs outils techniques des sessions précédentes restent des dépenses sans stratégie.

La gouvernance cyber consiste à définir "qui fait quoi, comment et sous quelle autorité" pour sécuriser le patrimoine informationnel de l'entreprise.

#### A. La PSSI : La loi interne
La Politique de Sécurité des Systèmes d'Information (PSSI) est rédigée par le RSSI (Responsable de la Sécurité des SI) et signée par la Direction Générale. Elle a valeur de règlement intérieur. Elle fixe les règles obligatoires (ex. longueur des mots de passe, interdiction d'utiliser des clés USB personnelles, processus d'accueil des nouveaux arrivants — et de départ : le « Leaver » de la session A4).

#### B. ISO 27001 : L'approche par l'amélioration continue
La norme ISO 27001 n'impose pas de technologies précises, mais une méthode. Elle repose sur le principe de l'amélioration continue (Cycle PDCA : Plan-Do-Check-Act) afin de s'assurer que l'entreprise évalue constamment ses menaces et ajuste ses défenses. Une certification ISO 27001 prouve aux clients et partenaires que l'organisation gère sa sécurité de manière professionnelle — c'est un argument commercial autant qu'un cadre interne.

#### C. Le NIST CSF 2.0 : Le cadre pragmatique
Très utilisé à l'international, le Cybersecurity Framework du NIST structure la sécurité en fonctions opérationnelles. Sa **version 2.0 (février 2024)** en compte **six** — la fonction « Gouverner » ayant été ajoutée en socle des cinq historiques :

1. **Gouverner** (*Govern*) : Définir la stratégie, les rôles, les responsabilités et la supervision des risques — la fonction ajoutée par la v2.0, qui irrigue toutes les autres.
2. **Identifier** (*Identify*) : Cartographier les actifs, les systèmes, les données et les risques.
3. **Protéger** (*Protect*) : Mettre en œuvre les barrières de protection (sensibilisation, accès, chiffrement).
4. **Détecter** (*Detect*) : Identifier la survenue d'incidents de sécurité (journalisation, alertes).
5. **Répondre** (*Respond*) : Réagir aux incidents détectés (confinement, communication).
6. **Récupérer** (*Recover*) : Restaurer les systèmes pour revenir à la normale après un incident.

Repère pédagogique : votre parcours suit exactement ce cadre — les sessions A1 à A5 couvrent Gouverner/Identifier/Protéger ; les sessions A6 et A7 couvriront Détecter, Répondre et Récupérer.

### 2. La Gestion des Risques : Évaluer pour mieux investir

Il est impossible de sécuriser un système à 100%. Le budget d'une entreprise étant limité, celle-ci doit prioriser ses investissements. C'est l'objectif de l'analyse de risques — le prolongement méthodique de la formule *Risque = Menace × Vulnérabilité × Impact* vue en session A1 : on passe de l'intuition à la cotation.

Un risque se caractérise par deux facteurs :

* **La Vraisemblance (ou Probabilité)** : Quelle est la chance que l'événement redouté se produise (de 1 - Très rare à 4 - Presque certain) ?
* **L'Impact (ou Gravité)** : Si l'événement se produit, quels seront les dommages financiers, juridiques ou de réputation (de 1 - Négligeable à 4 - Critique) ?

**Criticité brute** = *Vraisemblance* × *Impact* — et après traitement, on réévalue : c'est la **criticité résiduelle**, celle que la direction accepte en connaissance de cause.

#### Les 4 stratégies de traitement du risque :
1. **Réduire** : Mettre en place des mesures de sécurité pour baisser l'impact ou la vraisemblance (ex. installer un pare-feu, chiffrer les portables, sauvegarder en 3-2-1).
2. **Transférer** : Partager le risque avec un tiers (ex. souscrire une cyber-assurance qui paiera les frais en cas d'attaque). Attention : on transfère l'impact financier, **pas** l'interruption d'activité ni la responsabilité légale.
3. **Éviter** : Supprimer l'activité qui génère le risque (ex. renoncer à héberger un fichier contenant des données hautement sensibles).
4. **Accepter** : Décider — de manière **documentée et assumée par la direction** — de ne rien faire, car le coût de la protection est plus élevé que le coût de l'impact potentiel.

Analogie utile : c'est exactement votre raisonnement d'assuré au quotidien. Le vélo d'occasion à 50 € : vous acceptez le risque de vol. La voiture : vous le réduisez (antivol) et le transférez (assurance). Conduire sur le verglas une nuit de tempête : vous évitez. Personne ne « supprime » le risque routier — on le gère.

### 3. La Conformité et la Vie Privée : Le RGPD

Le RGPD impose des règles strictes à toute entité (publique ou privée) collectant ou traitant des données personnelles de résidents européens — où qu'elle soit dans le monde.

#### Les 4 grands principes du RGPD :
1. **La finalité** : Les données doivent être collectées pour un but précis et légitime, et ne pas être réutilisées à d'autres fins (ex. si un client donne son numéro pour une livraison, l'entreprise ne peut pas le revendre pour de la prospection publicitaire sans son accord).
2. **La minimisation** : Collecter uniquement les données strictement nécessaires (ne pas demander le numéro de sécurité sociale pour s'inscrire à une newsletter) — c'est le « moindre privilège » de la donnée, en écho à la session A4.
3. **La transparence et le consentement** : L'utilisateur doit donner son accord explicite (bouton d'acceptation actif, pas de case pré-cochée) et savoir exactement ce qui sera fait de ses données.
4. **Les droits des personnes** : Droit d'accès (savoir quelles données sont conservées — gratuitement), droit de rectification (les modifier) et droit à l'effacement dit « droit à l'oubli » (demander leur suppression).

En cas de violation de données présentant un risque pour les personnes, l'organisme doit **notifier la CNIL sous 72 heures** — et informer les personnes concernées si le risque est élevé. En cas de manquement, les autorités de contrôle peuvent prononcer des amendes administratives à deux paliers : jusqu'à **10 millions d'euros ou 2 % du chiffre d'affaires mondial annuel**, et pour les manquements les plus graves jusqu'à **20 millions d'euros ou 4 %** — le montant le plus élevé étant à chaque fois retenu.

---

### Focus pratique
Les entreprises projettent les risques identifiés dans une matrice visuelle pour cibler les risques prioritaires (ceux situés dans la zone rouge).

```text
    Impact ➔
    [ 1:Négligeable ] [ 2:Modéré ] [ 3:Majeur ] [ 4:Critique ]
  Vraisemblance ⬇
  [ 4:Presque sûr ]  (Moyen-4)    (Moyen-8)   (ÉLEVÉ-12)  (ÉLEVÉ-16)
  [ 3:Probable    ]  (Faible-3)   (Moyen-6)   (Moyen-9)   (ÉLEVÉ-12)
  [ 2:Improbable  ]  (Faible-2)   (Moyen-4)   (Moyen-6)   (Moyen-8)
  [ 1:Très rare   ]  (Faible-1)   (Faible-2)  (Faible-3)  (Moyen-4)
```

* **Zone Rouge — ÉLEVÉ (12-16)** : Traitement obligatoire et immédiat.
* **Zone Orange — Moyen (4-9)** : Surveillance active et réduction planifiée.
* **Zone Verte — Faible (1-3)** : Acceptation du risque sous réserve de suivi.

*Note de lecture* : la criticité 4 s'obtient de trois manières (4×1, 2×2, 1×4) et tombe toujours en zone orange — un événement rarissime mais critique (l'inondation de la salle serveur) mérite la même vigilance qu'un événement fréquent mais bénin.

### Activité — Le Comité des Risques (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Annoncez : « vous siégez au comité des risques de la PME. Trois scénarios sont sur la table ; pour chacun, le comité — c'est-à-dire vous — vote la stratégie de traitement. » Pour chaque scénario : présentez-le, donnez la cotation proposée par le RSSI, lancez le sondage, débriefez.

*   **📊 Sondage n°2 — Scénario A :** Vol d'un ordinateur portable contenant la liste des clients (cotation RSSI : Vraisemblance 3 × Impact 3 = **criticité 9, zone orange**). Quelle stratégie prioritaire ?
    *   A) Réduire : chiffrement systématique des disques + MFA (l'impact s'effondre) ✅
    *   B) Éviter : interdire les ordinateurs portables dans l'entreprise
    *   C) Accepter : les vols sont rares, tant pis
*   **📊 Sondage n°3 — Scénario B :** Rançongiciel sur le serveur de facturation interne (cotation : Vraisemblance 3 × Impact 4 = **criticité 12, zone rouge**). Quelle décision du comité ?
    *   A) Accepter : notre antivirus suffira bien
    *   B) Réduire (sauvegardes 3-2-1 immuables, EDR, correctifs) puis transférer le résiduel (cyber-assurance) ✅
    *   C) Transférer uniquement : l'assurance paiera tout, inutile d'investir
*   **📊 Sondage n°4 — Scénario C :** Inondation de la salle serveur, bâtiment en zone non inondable (cotation : Vraisemblance 1 × Impact 4 = **criticité 4, zone orange basse**). Quelle décision ?
    *   A) Éviter : déménager l'entreprise immédiatement
    *   B) Réduire à coût marginal (copie hors site — déjà exigée par le 3-2-1) et accepter le résiduel de façon documentée ✅
    *   C) Ne rien faire et ne rien documenter : c'est trop improbable

**Éléments de débriefing (pour le mentor) :**

- N°2 : la bonne réponse réduit l'**impact** (un portable chiffré volé = un incident matériel, pas une fuite de données — souvenez-vous du consultant d'A1) ; « éviter » est disproportionné : on tuerait l'activité pour tuer le risque.
- N°3 : zone rouge = traitement obligatoire. Le piège est C : l'assurance rembourse des frais, elle ne restaure ni les données ni la production ni la réputation — **on transfère l'impact financier, pas le sinistre**. Et les assureurs exigent désormais des mesures de réduction (MFA, sauvegardes) avant de couvrir.
- N°4 : accepter n'est pas ignorer — c'est une décision **documentée, datée et signée** par la direction, réévaluée chaque année. La différence entre B et C est toute la maturité d'une gouvernance.
- Conclure : trois scénarios, trois stratégies différentes — c'est la preuve que la matrice n'est pas un exercice théorique mais un outil d'allocation de budget.

### 4. Les sanctions en chiffres : la conformité n'est pas optionnelle

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **1,2 milliard d'euros** : l'amende RGPD record, infligée à Meta en mai 2023 (autorité irlandaise, sous coordination européenne) pour des transferts de données d'utilisateurs européens vers les États-Unis sans garanties suffisantes.
    - **50 millions d'euros** : la première grande amende française, infligée à Google par la CNIL dès 2019 pour défaut de transparence et de consentement valable (cas détaillé ci-dessous).
    - **20 millions d'euros** : l'amende CNIL contre Clearview AI (2022), qui aspirait les photos publiées sur le web pour bâtir une base biométrique de reconnaissance faciale — sans le consentement de quiconque.
    - **Plusieurs milliards d'euros** : le cumul des amendes RGPD prononcées en Europe depuis 2018 — et rappel de la session A1 : les violations notifiées à la CNIL ont atteint un record en 2024.

**Comment lire ces chiffres ?** (1) Le RGPD est appliqué, y compris contre les plus grands acteurs mondiaux — l'argument « personne ne contrôle » est mort. (2) Les sanctions frappent des manquements de **principes** (transparence, consentement, base légale), pas seulement des fuites techniques : on peut être sanctionné sans avoir été piraté. (3) Pour une PME, le vrai coût n'est souvent pas l'amende mais la perte de confiance — la conformité est un actif commercial.

### 5. Étude de cas : Google et la CNIL (2019) — la sanction fondatrice

En janvier 2019, huit mois à peine après l'entrée en application du RGPD, la CNIL inflige à Google une amende de **50 millions d'euros** — la première sanction d'ampleur du règlement en Europe, à l'époque un record. Le grief ne porte ni sur un piratage, ni sur une fuite : il porte sur les **principes**. Lors de la configuration d'un téléphone Android, l'information donnée à l'utilisateur sur l'usage de ses données (personnalisation publicitaire notamment) était **diluée dans une arborescence de menus et de documents**, peu claire et incomplète ; et le consentement recueilli n'était ni éclairé (l'utilisateur ne pouvait pas mesurer la portée de son accord), ni spécifique (une case unique valait accord global — l'inverse du consentement actif exigé).

**Ce que ce cas illustre :** les quatre principes de la session — transparence et consentement en tête — ont une valeur juridique concrète ; aucune vulnérabilité technique n'a été exploitée, et pourtant la sanction est tombée. La conformité ne se réduit pas à la sécurité : un système parfaitement sécurisé peut être parfaitement illégal. Et depuis, l'échelle a changé : Meta, 1,2 milliard d'euros en 2023 — le RGPD a des dents, et elles poussent.

!!! question "💬 Question chat — À vous de jouer"
    Pensez au dernier site ou à la dernière application où vous avez « tout accepté » sans lire. **Dans le chat : quelle donnée personnelle pensez-vous lui avoir confiée sans vraiment le vouloir ?** Le mentor lit 3-4 réponses et conclut : c'est précisément ce que les principes de finalité et de consentement visent à corriger — et l'exercice self-paced de cette semaine vous fera vérifier votre intuition.

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Pour comprendre la Gouvernance, le Risque et la Conformité (GRC), imaginez la conduite d'une **voiture de course** :
    - **Le Risque** c'est l'accident de la route. Pour le gérer, vous portez un casque, installez des airbags et vérifiez l'usure de vos pneus avant de partir.
    - **La Conformité (RGPD)** ce sont les règles du code de la route et les limitations de vitesse imposées par la loi sous peine de fortes amendes.
    - **La Gouvernance** c'est le pilote et son équipe qui décident de la destination de la voiture, du budget disponible pour l'entretien et des règles internes de sécurité pour l'équipe technique.
    - Et la fonction **Gouverner** du NIST CSF 2.0, c'est la reconnaissance officielle qu'une voiture sans pilote ni stratégie de course n'a jamais gagné un championnat — quelle que soit la qualité de ses pneus.

**Exemple d'application professionnelle :**
Une PME du secteur médical souhaite lancer une application mobile de suivi de patients. Avant le développement, le RSSI mène une analyse de risques (impact d'une fuite de données de santé : critique) et s'assure de la conformité réglementaire (RGPD). L'entreprise nomme un DPO (Délégué à la Protection des Données), chiffre les bases de données, applique le *Privacy by Design* (minimisation dès la conception) et met en place un registre des traitements pour documenter la conformité. Le coût de cette démarche préventive : quelques semaines de travail. Le coût du même chantier après une fuite et une mise en demeure de la CNIL : sans commune mesure.

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour piloter la conformité RGPD, la gouvernance de sécurité (ISO 27001) et l'analyse de risques, voici les solutions de référence :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **OneTrust GRC** : Leader du marché pour la gestion de la conformité réglementaire (RGPD/CCPA), de la confidentialité et de la gouvernance des risques tiers.
    *   **ServiceNow GRC** : Plateforme intégrée haut de gamme pour l'analyse de risques d'entreprise et le suivi de la conformité aux audits ISO 27001.
    *   **Securiti.ai** : Solution axée sur la détection automatique des données personnelles et la conformité RGPD multi-cloud.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **PIA Tool (CNIL)** : Logiciel open-source gratuit fourni par la CNIL française pour mener des Analyses d'Impact sur la Protection des Données (AIPD/PIA) réglementaires.
    *   **Monarc** : Outil open-source de gestion de risques développé par le gouvernement luxembourgeois, permettant de mener des évaluations de risques conformes à ISO 27005.
    *   **EBIOS RM Manager** : Modèles d'analyse de risques libres basés sur la méthodologie de l'ANSSI pour structurer la gouvernance cyber.

### Exercice d'application RGPD (Sondages Livestorm n°5 et 6)

**Consignes pour le mentor :** Lancez les sondages de conformité RGPD à la suite.

*   **📊 Sondage n°5 :** En cas de fuite de données personnelles (ex. intrusion et vol de fichier clients), quelle est l'obligation légale de l'entreprise selon le RGPD ?
    *   A) Notifier la CNIL dans un délai maximal de 72 heures ✅
    *   B) Attendre la fin de l'enquête interne (sans limite de temps) avant d'en parler.
    *   C) Publier immédiatement un communiqué dans la presse sans prévenir la CNIL.
*   **📊 Sondage n°6 :** Un client demande à consulter toutes les données personnelles que vous stockez sur lui. Avez-vous le droit de lui facturer cette recherche ?
    *   A) Oui, pour couvrir les frais de traitement informatique.
    *   B) Non, l'accès à ses propres données est gratuit d'après le droit d'accès du RGPD ✅
    *   C) Oui, uniquement s'il n'est plus client chez vous.

**Éléments de débriefing (pour le mentor) :**
- Le délai de 72h pour notifier la CNIL est strict — il court à partir de la découverte de la violation, d'où l'importance de la détection (teaser de la session A6). Et si le risque pour les personnes est élevé, il faut aussi informer les personnes elles-mêmes (souvenez-vous de France Travail en A1).
- Le droit d'accès est gratuit. L'entreprise doit avoir un processus prêt pour extraire ces données.

### Quiz de validation (Sondages Livestorm n°7 à 9)

**Consignes pour le mentor :** À lancer en fin de session, après l'étude de cas.

*   **📊 Sondage n°7 :** Vrai ou faux — la PSSI d'une entreprise a valeur de règlement intérieur.
    *   A) Vrai ✅
    *   B) Faux
*   **📊 Sondage n°8 :** Vrai ou faux — transférer un risque (cyber-assurance) fait disparaître le risque du système.
    *   A) Vrai
    *   B) Faux : seul l'impact financier est partagé ; l'interruption d'activité et la responsabilité demeurent ✅
*   **📊 Sondage n°9 :** Vrai ou faux — le principe de minimisation consiste à collecter le moins de données personnelles possible pour un but donné.
    *   A) Vrai ✅
    *   B) Faux

**Éléments de débriefing (pour le mentor) :**

- N°7 : signée par la direction, opposable aux collaborateurs — c'est la « loi interne ».
- N°8 : rejouer le débrief du Comité des Risques (sondage n°3) : l'assurance rembourse, elle ne restaure rien.
- N°9 : le « moindre privilège de la donnée » — et le pont vers le sondage bonus (le numéro de sécurité sociale dans un fichier de prospection).

### Questions de réflexion

1. Dans l'affaire Google (2019), aucune faille technique n'a été exploitée. Votre organisation pourrait-elle être sanctionnée demain sans avoir jamais été piratée ? Sur quels traitements ?
2. « Accepter un risque » et « ignorer un risque » produisent le même effet immédiat (on ne fait rien). Qu'est-ce qui les distingue fondamentalement, et pourquoi cette distinction protège-t-elle le dirigeant ?
3. La cyber-assurance encourage-t-elle la négligence (« l'assurance paiera ») ou la vertu (exigences de l'assureur) ? Argumentez les deux positions.
4. Le NIST CSF 2.0 a ajouté la fonction « Gouverner » en 2024. Pourquoi, selon vous, a-t-il fallu une décennie pour reconnaître officiellement que la cybersécurité se pilote en comité de direction ?

## 3. Ressources complémentaires

* **IBM SkillsBuild** : Modules sur les principes de la GRC et le RGPD.
* **[CNIL — Guide de la sécurité des données personnelles](https://www.cnil.fr/fr/guide-de-la-securite-des-donnees-personnelles)** : l'outil indispensable pour auditer sa conformité.
* **[CNIL — Comprendre le RGPD](https://www.cnil.fr/fr/comprendre-le-rgpd)** : les principes expliqués simplement, avec les sanctions publiées.
* **NIST (USA)** : Documentation officielle du Cybersecurity Framework v2.0 (6 fonctions, dont Govern).
* **ANSSI — EBIOS Risk Manager** : la méthode française de référence pour l'analyse de risques.

## 4. Exercice bonus (Débat RGPD - Livestorm)

*   **Objectif :** Responsabilisation sur la collecte de données.
*   **📊 Sondage Livestorm n°10 :** Pour un fichier de prospection commerciale de base, avez-vous le droit de collecter les numéros de sécurité sociale des prospects ?
    *   A) Oui, cela permet une identification unique et sans doublons.
    *   B) Non, cela viole le principe de minimisation des données du RGPD ✅
    *   C) Oui, si les prospects ont coché une case générique d'acceptation.
*   **Guide d'animation (pour le mentor) :** Expliquez le principe de minimisation : on ne doit collecter que les données strictement nécessaires à l'objectif du traitement. La case générique (option C) ne sauve rien : le consentement doit être spécifique et éclairé — c'est exactement le grief retenu contre Google en 2019. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Analyse de risques** | Identifier, évaluer et hiérarchiser les risques ; Criticité = Vraisemblance × Impact ; brute avant traitement, résiduelle après. |
| **BYOD (Bring Your Own Device)** | Usage des équipements personnels des collaborateurs dans le cadre professionnel. |
| **CNIL** | Autorité française de protection des données personnelles (des équivalents existent dans chaque État européen). |
| **Criticité résiduelle** | Risque subsistant après traitement, accepté en connaissance de cause par la direction. |
| **Donnée personnelle** | Toute information se rapportant à une personne physique identifiée ou identifiable (nom, e-mail, adresse IP, données de santé...). |
| **DPO (Data Protection Officer)** | Délégué à la protection des données, garant indépendant de la conformité RGPD. |
| **EBIOS RM** | Méthode ANSSI d'analyse et de management des risques numériques. |
| **GRC (Gouvernance, Risques et Conformité)** | Aligner l'informatique sur les objectifs de l'entreprise, gérer les risques, respecter les obligations réglementaires. |
| **ISO/CEI 27001** | Norme internationale du Système de Management de la Sécurité de l'Information (SMSI), fondée sur le cycle PDCA. |
| **NIST CSF 2.0** | Cadre américain à 6 fonctions : Gouverner, Identifier, Protéger, Détecter, Répondre, Récupérer. |
| **PSSI** | Politique de Sécurité des SI — la « loi interne », signée par la direction, à valeur de règlement intérieur. |
| **RGPD** | Règlement européen sur les données personnelles ; sanctions jusqu'à 20 M€ ou 4 % du CA mondial (le plus élevé retenu) ; notification des violations sous 72 h. |
| **Traitement du risque** | Quatre stratégies : Réduire, Transférer (l'impact financier seulement), Éviter, Accepter (documenté). |

**La règle d'or de la session :** on ne supprime jamais un risque, on le gère — et la conformité ne se délègue pas à la technique : un système parfaitement sécurisé peut être parfaitement illégal.
