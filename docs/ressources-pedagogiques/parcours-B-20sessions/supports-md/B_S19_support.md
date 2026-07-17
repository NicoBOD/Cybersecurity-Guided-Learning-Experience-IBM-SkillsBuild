# Session B19 — Simulation de crise cyber (Tabletop exercise)
Parcours : B 20 sessions  |  Module : E — Opérations, détection & réponse  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30) — session-exercice « la crise en direct »

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Qu'est-ce qu'un Tabletop Exercise (exercice de crise sur table) ?
    - La cellule de crise cyber : qui décide de quoi
    - Les règles d'or de la communication de crise
    - Deux affaires réelles : Norsk Hydro (2019, la crise exemplaire) et Maersk (2017, revisité côté reconstruction)
    - **L'exercice du soir : la crise GigaVolt**, une simulation en temps réel où VOUS prenez chaque décision par sondages
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Un **Tabletop Exercise** est un entraînement théorique, sans impact sur la production, qui teste la capacité décisionnelle d'une organisation face à un scénario d'attaque — le NIST et l'ANSSI recommandent d'en organiser régulièrement.
*   La gestion de crise réunit la **Direction**, l'**IT/Sécurité**, le **Juridique/DPO** et la **Communication** : l'informatique ne décide jamais seule — c'était votre réflexion de la semaine.
*   La communication de crise doit être **factuelle, empathique et centralisée** autour d'un porte-parole unique.
*   Toute fuite de données personnelles impose une notification à la **CNIL sous 72 h** (B15) ; l'indemnisation assurantielle d'une cyberattaque exige une plainte sous **72 h** (LOPMI 2023, B02).

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer le fonctionnement et l'intérêt d'une simulation de crise sur table (rôle du maître du jeu, injects, RETEX).
* Prendre des décisions de crise opérationnelles, juridiques et de communication sous contrainte de temps et d'information incomplète (l'exercice GigaVolt).
* Rédiger un communiqué de crise externe factuel, transparent et conforme aux obligations réglementaires (RGPD).

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** Selon le rapport IBM *Cost of a Data Breach* 2022, combien économise en moyenne une organisation disposant d'une équipe de réponse aux incidents ET d'un plan régulièrement testé, sur le coût d'une violation de données ?

    - A) Environ 250 000 $
    - B) Environ 1 million de $
    - C) Environ 2,66 millions de $ ✅

    **Débrief mentor :** Réponse C : **2,66 M$ d'écart moyen** (IBM, 2022) entre les organisations préparées (équipe + plan testé) et celles qui n'ont ni l'un ni l'autre. Le mot important : **testé**. Un plan jamais exercé est une hypothèse — sous stress, on ne s'élève pas au niveau de ses ambitions, on retombe au niveau de son entraînement. Ce soir, on s'entraîne : dans vingt minutes, vous serez la cellule de crise d'une PME attaquée, et chaque décision passera par vos votes.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Concevoir un exercice de crise : la méthode ANSSI**
Pour les participants qui voudraient organiser leur propre exercice : l'ANSSI publie un guide dédié, *Organiser un exercice de gestion de crise cyber* (2021), qui détaille la démarche — définir des **objectifs** précis (tester la chaîne d'alerte ? la décision de déconnexion ? la communication ?), écrire un **scénario** vraisemblable adossé aux risques réels de l'organisation (le registre de B14 sert de vivier), préparer le **chronogramme du maître du jeu** avec ses injects (chaque inject teste un objectif), prévoir des **observateurs** qui notent sans jouer, et surtout le **RETEX** en deux temps : à chaud (ressentis, blocages immédiats) puis à froid (plan d'action, mise à jour des playbooks et de la PSSI). Fréquence recommandée : au moins un exercice par an, en variant les scénarios. Piège classique : l'exercice-spectacle réussi d'avance — un bon exercice DOIT faire apparaître des failles, c'est sa raison d'être.

**2. La question de la rançon, en profondeur**
L'exercice fera surgir le débat ; les points d'appui : la position constante de l'**ANSSI** et des autorités françaises — ne pas payer (payer finance l'écosystème criminel, ne garantit ni le déchiffrement ni la non-publication, et signale un payeur pour l'avenir) ; la **LOPMI (2023)** conditionne l'indemnisation assurantielle au dépôt de plainte sous 72 h — le réflexe judiciaire n'est plus optionnel ; certains paiements sont juridiquement risqués (verser des fonds à un groupe sous sanctions internationales peut engager la responsabilité de l'entreprise) ; et dans la réalité, des négociateurs professionnels existent — négocier pour gagner du temps d'investigation n'est pas payer. Rappel utile : l'affaire Colonial Pipeline (B08) a payé et récupéré un déchiffreur… si lent que la restauration sur sauvegardes est restée nécessaire.

**3. Communication hors bande et continuité : les décisions que le PCA prépare**
Deux angles morts classiques que l'exercice révèle : (1) **la messagerie de crise** — si l'AD et la messagerie sont chiffrés, comment la cellule se parle-t-elle ? Les canaux alternatifs se préparent À L'AVANCE : annuaire de crise imprimé (téléphones personnels des membres), messagerie chiffrée grand public convenue, pont téléphonique externe ; improviser un canal en pleine crise fait perdre des heures. (2) **La tenue en mode dégradé** — combien de temps l'activité survit-elle sans informatique ? C'est le PCA/PRA de B12 (RTO/RPO) qui répond, et c'est lui qui arbitre les décisions dures de la cellule (déconnecter tout le SI se décide en minutes si l'on sait qu'on peut produire en manuel — Norsk Hydro l'a prouvé).

---

### Glossaire

*   **Cellule de crise** — Groupe décisionnel restreint (Direction, IT/Sécurité, Juridique/DPO, Communication) constitué pour piloter la réponse à un incident majeur.
*   **Chaîne de contrôle (Chain of custody)** — Documentation de la collecte, du transfert et de l'analyse des preuves numériques, garantissant leur validité devant un tribunal.
*   **Communication hors bande (Out-of-band)** — Canaux de communication indépendants du SI compromis (téléphones personnels, messagerie chiffrée externe, pont téléphonique), préparés à l'avance.
*   **Double extorsion** — Tactique combinant chiffrement des données ET menace de publication des données volées, pour faire pression même sur les victimes disposant de sauvegardes (B02).
*   **Inject (stimulus)** — Information ou rebondissement introduit par l'animateur d'une simulation pour faire évoluer le scénario et tester une capacité précise.
*   **RETEX / REX (Retour d'expérience)** — Analyse post-incident (ou post-exercice) des défaillances et réussites, aboutissant à un plan d'amélioration concret.
*   **Tabletop Exercise (exercice sur table)** — Simulation théorique d'un incident permettant de tester les plans de réponse et la prise de décision, sans aucun impact sur la production.

---

### Concepts clés

!!! info "À retenir"
    Une crise cyber n'est pas un problème informatique : c'est un problème d'entreprise à déclencheur informatique. La technique confine et restaure ; mais décider de déconnecter, de notifier, de communiquer, de ne pas payer — c'est la **cellule de crise** qui le fait, et elle ne le fait bien que si elle s'est **entraînée**.

### 1. Qu'est-ce qu'un Tabletop Exercise ?
Un **exercice sur table** est une simulation de crise théorique : les décisionnaires se réunissent et réagissent en temps réel à un scénario d'attaque fictif, sans toucher à la production.

*   **Le maître du jeu (MJ)** anime la session et introduit régulièrement des **injects** — nouvelles informations perturbatrices : une fuite découverte sur un forum, une demande de rançon, l'appel d'un journaliste, un tweet de salarié…
*   **Ce que l'exercice teste** : la clarté des playbooks (B18), la capacité à décider vite avec des informations incomplètes, la coordination entre techniques et non-techniques — et les angles morts (qui a le numéro personnel du DPO un dimanche ?).
*   **La règle d'or de l'exercice** : un bon exercice fait apparaître des failles. Si tout se passe parfaitement, c'est que le scénario était trop facile.

### 2. La cellule de crise cyber : qui décide de quoi
Face à une attaque d'ampleur, l'informatique ne décide pas seule. La cellule réunit quatre fonctions complémentaires — comparez avec la liste que vous avez préparée cette semaine :

*   **Le directeur de crise (Direction générale)** : valide la stratégie, débloque les moyens d'urgence (experts externes, matériel), assume la responsabilité finale — c'est lui qui « porte » la décision de payer ou non, de déconnecter ou non (le principe de B13 : la direction décide, la direction assume).
*   **Le responsable IT/Sécurité (RSSI/DSI)** : diagnostic technique, pilotage du confinement et de l'investigation, estimation des délais de restauration — il éclaire les décisions, il ne les prend pas seul.
*   **Le juridique / DPO** : qualifie les obligations — notification **CNIL sous 72 h** si données personnelles (B15), information des personnes concernées, dépôt de plainte (**LOPMI : 72 h** pour préserver l'indemnisation, B02), relations avec l'assureur (B14).
*   **La communication** : messages internes (couper court aux rumeurs) et externes (presse, clients, partenaires), préparation du porte-parole unique.

### 3. Les règles d'or de la communication de crise
En crise cyber, une mauvaise communication peut coûter plus cher que l'attaque elle-même :

!!! warning "Règles fondamentales de communication de crise"
    1.  **S'en tenir strictement aux faits** : ne jamais mentir, spéculer, ni désigner un coupable sans preuves techniques solides.
    2.  **Centraliser la parole** : un porte-parole unique ; les salariés ne s'expriment pas sur l'incident — ni aux journalistes, ni sur leurs réseaux personnels.
    3.  **Empathie et responsabilité** : reconnaître la situation, exprimer des regrets pour la gêne, détailler les mesures concrètes engagées.
    4.  **Transparence contrôlée** : expliquer clairement ce qui s'est passé, sans dévoiler de détails techniques exploitables par d'autres attaquants.

### 4. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **2,66 M$ d'économie moyenne** sur le coût d'une violation pour les organisations dotées d'une équipe de réponse ET d'un plan régulièrement testé (IBM, *Cost of a Data Breach*, 2022).
    - **~70 M$** : coût estimé de l'attaque LockerGoga pour Norsk Hydro, qui a refusé de payer (chiffres communiqués par l'entreprise, 2019).
    - **~300 M$** de pertes déclarées par Maersk après NotPetya, et **10 jours** pour reconstruire ~4 000 serveurs et 45 000 postes (déclarations de l'entreprise, 2017).

**Comment lire ces chiffres ?** (1) La préparation se mesure en millions : l'écart IBM est l'argument budgétaire de l'exercice de ce soir. (2) Refuser de payer coûte cher (Hydro) — mais l'entreprise a gardé la maîtrise de sa crise, sa réputation en est sortie renforcée, et l'écosystème criminel n'a rien touché. (3) La reconstruction se compte en jours quand les sauvegardes existent (B12) — et en existence de l'entreprise quand elles n'existent pas.

### 5. Une affaire réelle : Norsk Hydro (2019) — la crise gérée en pleine lumière

Mars 2019, 4 heures du matin. Le géant norvégien de l'aluminium **Norsk Hydro** (35 000 salariés, 40 pays) détecte le rançongiciel **LockerGoga** en train de chiffrer ses systèmes. La cellule de crise prend trois décisions rapides devenues un cas d'école : **isoler massivement** (réseaux déconnectés, 22 000 postes hors ligne), **refuser de payer** — sans même ouvrir la négociation —, et **communiquer en transparence totale** : points presse quotidiens, page d'incident publique, dirigeants face caméra dès le premier jour. Pendant des semaines, les usines tournent en **mode manuel** : les anciens ressortent les classeurs papier, les jeunes apprennent des retraités rappelés en renfort. Coût final : de l'ordre de **70 M$** (chiffres de l'entreprise, 2019) — et, fait rare, une réputation *renforcée* par la crise : Hydro est depuis cité en exemple par les autorités et les assureurs.

**Ce que ce cas illustre :** les trois décisions dures (déconnecter, ne pas payer, tout dire) se prennent en heures — impossibles à improviser sans préparation ni PCA (le mode manuel était possible parce que pensé) ; la transparence a inversé le rapport de force médiatique : pas de fuite à gérer, pas de rumeur à démentir, l'entreprise racontait sa propre histoire ; et le refus de payer, assumé publiquement, a fait de Hydro un contre-modèle pour les attaquants — on ne rackette pas celui qui a prouvé qu'il ne paie pas.

**Le cas revisité — Maersk (2017, vu en B03) côté cellule de crise :** frappé collatéralement par **NotPetya**, le géant du transport maritime perd la quasi-totalité de son informatique en quelques heures — dont ses contrôleurs de domaine. La reconstruction (10 jours, ~4 000 serveurs, 45 000 postes, ~300 M$ de pertes déclarées) n'a été possible que grâce à une copie survivante de l'annuaire… au bureau du **Ghana**, épargné par une coupure de courant. La leçon de crise : l'entreprise a maintenu ~80 % de son activité en mode dégradé (WhatsApp, tableurs, papier) — l'improvisation héroïque a sauvé Maersk, mais une communication hors bande et des sauvegardes hors ligne **préparées** auraient coûté infiniment moins cher que ce coup de chance.

---

### 🧪 L'exercice du soir — La crise GigaVolt (simulation en temps réel)

**Le principe :** le mentor est le maître du jeu ; **vous êtes collectivement la cellule de crise**. Le scénario avance par injects horodatés ; à chaque point de décision, vous votez (sondages) ou proposez (chat). Aucune préparation requise — comme dans la vraie vie.

**Mise en situation :** GigaVolt, PME française de 120 salariés, distribue du matériel électrique. Lundi, 7h55 : l'astreinte informatique appelle — « l'Active Directory ne répond plus, des fichiers changent d'extension en `.lokd`, il y a un écran de rançon sur les serveurs. »

*   **📊 Sondage n°2 — Décision 1 (8h00) : la première heure.** Que faites-vous en premier ?
    *   A) Redémarrer les serveurs pour tenter de récupérer l'Active Directory
    *   B) Confiner : isoler les segments réseau touchés, couper les accès distants, laisser les machines allumées — et activer la cellule de crise ✅
    *   C) Contacter les attaquants pour gagner du temps
*   **📊 Sondage n°3 — Décision 2 (8h30) : qui prévenir dans l'heure ?**
    *   A) Uniquement l'équipe informatique : inutile d'affoler tout le monde
    *   B) La cellule de crise au complet (Direction, IT, juridique/DPO, communication) + l'assureur et un prestataire de réponse à incident ✅
    *   C) Tous les clients immédiatement, par précaution
*   **🕙 Inject 2 (10h30) :** un e-mail arrive sur la boîte personnelle du dirigeant : les attaquants réclament **500 000 €** et menacent de **publier les données clients volées** (double extorsion). Les sauvegardes de la veille sont saines et hors ligne (B12).
*   **📊 Sondage n°4 — Décision 3 : la rançon.**
    *   A) Payer discrètement : c'est moins cher qu'une semaine d'arrêt
    *   B) Ne pas payer : déposer plainte (LOPMI : 72 h), préparer la notification CNIL (données personnelles volées : 72 h), restaurer sur sauvegardes après éradication ✅
    *   C) Ignorer totalement la demande, sans plainte ni notification : moins on en parle, mieux c'est
*   **🕑 Inject 3 (14h00) :** un journaliste appelle le standard — il a repéré des données GigaVolt sur un forum. Au même moment, un salarié tweete : « grosse panique au boulot, on est piratés ! »

!!! question "🤔 Mini-scénario — Que répondez-vous au journaliste ? (Inject 3)"
    **Tapez A, B ou C dans le chat :**

    - A) Nier tout incident, le temps d'y voir clair.
    - B) Reconnaître factuellement un incident en cours d'investigation, annoncer un communiqué à venir, renvoyer vers le porte-parole unique — et rappeler en interne la consigne : personne d'autre ne s'exprime. ✅
    - C) Tout détailler techniquement pour prouver la transparence de l'entreprise.

    **Débrief mentor :** B — nier (A) est la pire option : le journaliste A les données sous les yeux, le mensonge deviendra l'histoire principale ; tout détailler (C) livre des informations exploitables et de la spéculation. La transparence CONTRÔLÉE : des faits, un calendrier, une seule voix. Et le tweet du salarié illustre la règle n°2 : la consigne interne de silence externe se donne dès la première heure, pas après le premier tweet.

*   **💬 Le communiqué collectif (chat) :** construisez ensemble le squelette du communiqué de presse — le mentor l'assemble en direct : ① reconnaissance factuelle de l'incident ② mesures engagées (isolement, experts, autorités) ③ ce qui est touché ET ce qui ne l'est pas ④ notification CNIL et information des clients concernés ⑤ regrets et engagement ⑥ contact presse unique. *(Le corrigé modèle ci-dessous sert de référence après l'exercice.)*

**Corrigé / Communiqué modèle (rédigé sur le cas EcoLog, transposable) :**

```text
COMMUNIQUÉ DE PRESSE — ECOLOG
Pour diffusion immédiate — Paris, le 29 juin 2026

EcoLog informe avoir été la cible d'un incident de sécurité informatique ayant
partiellement perturbé certains de ses systèmes de gestion des livraisons.

Dès la détection de l'événement, nos équipes techniques ont immédiatement isolé
les serveurs affectés afin de contenir la propagation. Nous collaborons avec des
experts externes en cybersécurité pour mener des investigations approfondies et
assurer un retour sécurisé à la normale de nos opérations.

Nos premières analyses indiquent que des données de facturation (noms, adresses
postales et historiques de commandes) relatives à un nombre limité de clients ont
pu être consultées sans autorisation. Aucune coordonnée bancaire ni mot de passe
n'a été compromis lors de cet incident.

Conformément à la réglementation en vigueur (RGPD), nous avons procédé à la
notification de cet incident auprès de la CNIL. Les clients concernés sont en
cours d'information individuelle afin de leur apporter les recommandations
nécessaires.

EcoLog regrette sincèrement les désagréments causés par cet acte malveillant et
réaffirme son engagement total envers la protection et la sécurité des données de
ses clients et partenaires.

Contact presse unique : service.presse@ecolog.fr
```

*Pourquoi ce communiqué fonctionne :* **factuel** (l'incident et la fuite sont admis, sans minimisation) ; **rassurant** (il précise ce qui n'a PAS été volé — coordonnées bancaires, mots de passe) ; **légal et responsable** (notification CNIL et information individuelle explicites) ; **une seule voix** (contact presse unique).

!!! tip "📊 Sondage Livestorm n°5 — La vraie question (sondage d'opinion, pas de bonne réponse)"
    **Question :** Honnêtement : sous la pression réelle — production arrêtée, clients qui appellent, données dans la nature — pensez-vous que votre organisation paierait la rançon ?

    - A) Oui, probablement
    - B) Non, je pense qu'elle tiendrait
    - C) Aucune idée — et c'est bien le problème

    **Débrief mentor :** Pas de bonne réponse — et C est une excellente réponse : si vous ne savez pas ce que votre organisation déciderait, c'est que la décision n'a jamais été **préparée**, et elle se prendra donc dans la panique. Dans la réalité, beaucoup d'organisations paient, les rapports du secteur le confirment année après année — c'est précisément pourquoi la position se décide À FROID, en exercice, avec le juridique et l'assureur autour de la table (rappel Hydro : le refus assumé est aussi une protection pour l'avenir).

### 💬 Le RETEX à chaud (chat)

**Consignes pour le mentor :** « L'exercice est terminé — place au retour d'expérience, comme après une vraie crise. **Dans le chat : la décision qui vous a semblé la plus difficile, et une chose que GigaVolt aurait dû préparer à l'avance.** » Récolter, regrouper (canaux hors bande, annuaire de crise, position rançon écrite, sauvegardes testées, porte-parole désigné), et conclure : la liste que vous venez de faire EST un plan d'action RETEX — c'est exactement le livrable d'un vrai exercice.

---

### Questions de réflexion
1. Pourquoi est-il déconseillé d'annoncer publiquement le montant d'une rançon exigée, ou même le fait que l'on négocie avec les attaquants ?
2. La messagerie interne est chiffrée par le rançongiciel. Comment la cellule de crise communique-t-elle de manière sécurisée ? (Pensez aux canaux « hors bande ».)
3. Norsk Hydro a refusé de payer et l'a dit publiquement ; Colonial Pipeline (B08) a payé. Au-delà de la morale, quels arguments *économiques et stratégiques* plaident pour la position de Hydro ?

**Corrigé / Éléments de réponse :**

1. Cela renseigne les attaquants (et les suivants) sur la capacité et la disposition à payer, complique la position de négociation, et peut créer un précédent réputationnel ; certains paiements exposent en outre à un risque juridique (groupes sous sanctions).
2. Canaux préparés à l'avance et indépendants du SI : annuaire de crise imprimé avec téléphones personnels, messagerie chiffrée grand public convenue, pont téléphonique externe. L'improvisation d'un canal en pleine crise fait perdre des heures critiques.
3. Payer ne garantit rien (déchiffreur lent ou défaillant — Colonial a restauré sur sauvegardes malgré le paiement), finance et encourage l'écosystème, et signale un payeur ; refuser en s'appuyant sur des sauvegardes saines et un PCA rend l'extorsion inopérante et décourage les attaques futures — la réputation de Hydro en est sortie renforcée.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Un exercice de crise cyber, c'est **l'exercice d'évacuation incendie** de l'entreprise :
    - On ne met pas le feu au bâtiment (aucun impact sur la production) — on teste les réflexes, les rôles et les circuits.
    - **Le maître du jeu** est le responsable sécurité qui déclenche l'alarme et corse l'exercice (« l'escalier B est bloqué ! » = un inject).
    - **Le RETEX** est le débriefing : qui n'a pas entendu l'alarme ? quelle porte était verrouillée ? — et on corrige AVANT le vrai feu.
    - Et comme pour l'incendie : le jour J, personne n'improvise bien. On retombe au niveau de son entraînement.

**Exemple d'application professionnelle :**
Une PME organise un exercice annuel d'une demi-journée : scénario rançongiciel écrit à partir de son registre des risques (B14), cellule de crise au complet, trois injects (chiffrement, double extorsion, appel presse), un observateur qui note. Le RETEX produit quatre actions : annuaire de crise imprimé, position rançon validée par la direction et l'assureur, test de restauration trimestriel, désignation d'un porte-parole suppléant. Coût : une demi-journée. Économie potentielle : des millions (IBM, 2022).

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour outiller la gestion de crise et l'investigation qui l'accompagne :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **EnCase Forensic / FTK (Forensic Toolkit)** : standards reconnus par la justice pour l'acquisition intègre des supports et l'investigation numérique (la chaîne de contrôle outillée).
    *   **CrowdStrike Falcon Forensics** : collecte d'artefacts à distance pendant un incident actif.
    *   **Everbridge / FACT24** : plateformes de notification de crise (alerter la cellule et les collaborateurs hors bande).
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **Autopsy (The Sleuth Kit)** : la plateforme d'investigation numérique open-source la plus connue (analyse de disques, récupération de fichiers).
    *   **Volatility** : l'outil de référence pour l'analyse de la mémoire vive (la RAM préservée grâce à B18).
    *   **Velociraptor** : collecte d'artefacts en quelques secondes sur des parcs entiers — précieux pour qualifier l'étendue d'une compromission.

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer après le RETEX à chaud.

*   **📊 Sondage n°6 :** Dans un exercice de crise, qu'est-ce qu'un « inject » ?
    *   A) Le rapport final de l'exercice
    *   B) Une information ou un rebondissement introduit par l'animateur pour faire évoluer le scénario ✅
    *   C) Un logiciel d'injection SQL
*   **📊 Sondage n°7 :** Les sauvegardes sont saines. Dans quel ordre remet-on le système en service ?
    *   A) Restaurer immédiatement, puis chercher la faille quand la production tourne
    *   B) Éradiquer d'abord (fermer la faille, supprimer les portes dérobées), puis restaurer et surveiller ✅
    *   C) Reformater tous les postes sans investigation pour aller plus vite
*   **📊 Sondage n°8 :** Pendant la crise, qui s'exprime publiquement sur l'incident ?
    *   A) Chaque manager pour son périmètre : c'est plus rapide
    *   B) Personne, jamais : silence complet jusqu'à la fin de l'enquête
    *   C) Le porte-parole unique, avec des faits vérifiés — et personne d'autre ✅

**Éléments de débriefing (pour le mentor) :**

- N°6 : l'inject teste UNE capacité à la fois (chaîne d'alerte, décision rançon, communication) — c'est l'outil du maître du jeu.
- N°7 : restaurer avant d'éradiquer = restaurer dans un environnement piégé (la question de réflexion de B18) ; reformater sans investiguer (C) détruit les preuves ET laisse la faille ouverte.
- N°8 : le silence total (B) laisse la place aux rumeurs et aux fuites ; la cacophonie (A) fabrique des contradictions. Une voix, des faits, un calendrier.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Terminer le cursus du parcours et récupérer les badges de complétion.
*   **Guide pratique** : Lire *Organiser un exercice de gestion de crise cyber* (ANSSI, 2021) — la méthode complète, du scénario au RETEX.
*   [ANSSI — Organiser un exercice de gestion de crise cyber](https://cyber.gouv.fr/publications/organiser-un-exercice-de-gestion-de-crise-cyber)
*   [CNIL — Notifier une violation de données personnelles](https://www.cnil.fr/fr/notifier-une-violation-de-donnees-personnelles)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Préservation des preuves après compromission.
*   **📊 Sondage Livestorm n°9 :** Un employé a cliqué sur un lien suspect et saisi ses identifiants ; vous suspectez une intrusion. Pourquoi ne pas réinstaller immédiatement son poste ?
    *   A) Parce que cela coûte trop cher
    *   B) Pour préserver les traces de l'attaque : comprendre comment le pirate est entré, ce qu'il a fait et ce qu'il a volé ✅
    *   C) Parce que la réinstallation propagerait le virus
*   **Guide d'animation (pour le mentor) :** réinstaller efface la scène de crime : sans investigation, on ignore l'étendue de la compromission (autres comptes ? persistance ?) et l'attaque se reproduit le lendemain de la réinstallation. D'abord isoler, préserver (RAM, disque en copie — B18), investiguer ; réinstaller vient après. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Tabletop** | La crise sans les dégâts : tester les décisions, les rôles et les playbooks — un bon exercice révèle des failles. |
| **Cellule de crise** | Direction (décide et assume) + IT (éclaire) + juridique/DPO (72 h CNIL, plainte LOPMI) + communication. |
| **Inject** | Le rebondissement du maître du jeu — chaque inject teste une capacité précise. |
| **Rançon** | Position ANSSI : ne pas payer ; se décide À FROID, avec juridique et assureur — Hydro en modèle. |
| **Communication de crise** | Des faits, une voix (porte-parole unique), de l'empathie, une transparence contrôlée. |
| **Hors bande** | Les canaux de secours se préparent AVANT : annuaire de crise imprimé, messagerie externe convenue. |
| **RETEX** | À chaud puis à froid : la liste des manques devient le plan d'action — c'est le livrable de l'exercice. |

**La règle d'or de la session :** sous stress, on ne s'élève pas au niveau de ses ambitions — on retombe au niveau de son entraînement. Exercez la crise avant qu'elle n'arrive : Hydro a pu déconnecter, refuser de payer et parler en confiance parce que rien de tout cela ne s'improvisait ce matin-là.
