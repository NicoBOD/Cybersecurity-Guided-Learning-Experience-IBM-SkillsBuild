# Support de cours — Session 07 : Réponse aux incidents & introduction au forensics
Parcours : A 8 sessions  |  Module : Réponse aux Incidents  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Le cycle de réponse aux incidents (IR) : Les 6 étapes clés
    - Introduction au Forensics et préservation des preuves
    - Cadre légal : Piratage éthique vs Intrusions illégales
    - L'incident en chiffres et deux cas réels : la reconstruction de Maersk (2017) et le retour sur l'hôpital de Corbeil-Essonnes
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

Même avec les meilleures protections logicielles et humaines, le risque zéro n'existe pas : toute entreprise sera confrontée un jour ou l'autre à un incident de sécurité. Ce qui différencie une organisation résiliente d'une organisation qui s'effondre est la qualité de sa préparation et de sa réaction. Ce support de cours vous présente le cycle méthodologique de la réponse aux incidents pour savoir comment réagir étape par étape lors d'une attaque. Nous aborderons les bases du *forensics* (investigation numérique) afin de comprendre comment les analystes collectent et préservent les preuves d'une intrusion en respectant la chaîne de contrôle. Enfin, nous définirons le cadre légal du piratage éthique en France, afin de clarifier les limites juridiques indispensables aux métiers de la cybersécurité. Et parce que rien ne vaut le réel : vous découvrirez comment un géant mondial du transport a reconstruit 45 000 ordinateurs en dix jours — sauvé par une coupure de courant au Ghana.

### Objectifs de la session

À l'issue de cette session, vous serez capable de :

- **Dérouler** les 6 étapes du cycle de réponse aux incidents (modèle SANS) et expliquer pourquoi leur ordre n'est pas négociable.
- **Appliquer** le réflexe de confinement correct (isoler sans éteindre) et justifier l'ordre de volatilité des preuves.
- **Expliquer** la chaîne de contrôle (*chain of custody*) qui rend une preuve numérique recevable.
- **Situer** le cadre légal français du piratage éthique (STAD, ordre de mission) et la doctrine de non-paiement des rançons.

!!! tip "📊 Sondage Livestorm n°1 — Le vote AVANT (à lancer en tout début de session, SANS révéler la réponse)"
    **Question :** Un poste de travail affiche des signes d'infection active (fichiers qui disparaissent, trafic réseau anormal). Votre TOUT premier geste ?

    - A) Éteindre la machine en maintenant le bouton d'alimentation
    - B) Débrancher le câble réseau (ou couper le Wi-Fi) en laissant la machine allumée ✅ *(ne pas révéler maintenant)*
    - C) Lancer un scan antivirus complet
    - D) Envoyer un e-mail à tous les collègues pour les prévenir

    **Consigne mentor :** Notez la répartition des votes et annoncez : « je garde vos réponses au chaud — nous referons EXACTEMENT ce vote en fin de session, et nous comparerons. » Ne donnez ni la bonne réponse ni d'indice. C'est la mesure « avant/après » de la session : la comparaison finale (sondage n°9) est le meilleur débrief possible.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Deux modèles cousins : SANS (6 étapes) et NIST (4 phases) — à ne pas confondre**
Le cycle en 6 étapes enseigné dans ce support (Préparation, Identification, Confinement, Éradication, Restauration, Leçons apprises) est le modèle du **SANS Institute**, dit « PICERL » — le plus pédagogique. Le **NIST SP 800-61** regroupe les mêmes réalités en **4 phases** : Préparation ; Détection & Analyse ; Confinement-Éradication-Recouvrement ; Activité post-incident. Les deux disent la même chose à des granularités différentes — si un apprenant cite « les 4 phases du NIST », il a raison aussi. Point d'actualité pour votre culture : la révision 3 du SP 800-61 (2025) réaligne la réponse aux incidents sur les 6 fonctions du CSF 2.0 vues en session A5 (Gouverner comprise) — la boucle est bouclée.

**2. Ordre de volatilité et Forensics**
Expliquez pourquoi on ne doit **jamais** éteindre un ordinateur infecté par un ransomware : l'extinction vide la mémoire RAM qui contient potentiellement les clés de chiffrement et les preuves de l'attaque. L'ordre de collecte exige de d'abord capturer la RAM, puis les connexions et processus actifs, puis les fichiers temporaires, et enfin cloner le disque dur physique.

**3. La communication de crise (souvent oubliée)**
Un point que les exercices révèlent systématiquement : quand la messagerie est chiffrée ou compromise, comment la cellule de crise communique-t-elle ? Réponse à préparer AVANT : un canal de secours hors du SI (téléphonie, messagerie externe pré-convenue), une liste de contacts imprimée (direction, prestataire de réponse à incident, assurance, CNIL le cas échéant), et un porte-parole unique. Chez Maersk (cas étudié plus bas), la coordination mondiale s'est faite un temps par téléphone et messageries personnelles — improvisée, donc coûteuse.

**4. L'exercice, encore l'exercice**
L'ANSSI publie un guide complet pour organiser un exercice de gestion de crise cyber (référencé dans les ressources). Le message aux apprenants : un plan de réponse jamais répété est comme un plan d'évacuation jamais testé — on découvre les portes verrouillées le jour de l'incendie. C'est exactement ce que la session A8 leur fera vivre en conditions réelles sur le cas MedDistri.

---

### Glossaire

*   **CERT / CSIRT** — Équipe spécialisée de réponse aux incidents de sécurité (Computer Emergency Response Team). Le CERT-FR, rattaché à l'ANSSI, est l'équipe nationale française.
*   **Chaîne de contrôle (Chain of Custody)** — Documentation chronologique stricte recensant l'historique des personnes ayant manipulé, transféré et analysé une preuve physique ou numérique, afin de garantir qu'elle n'a subi aucune altération.
*   **Confinement** — Phase de la réponse aux incidents visant à isoler le système d'information ou les hôtes compromis pour empêcher la propagation de l'attaque.
*   **Éradication** — Phase consistant à éliminer définitivement la source de l'incident (ex. supprimer un code malveillant ou fermer un compte piraté).
*   **Forensics (Investigation numérique)** — Discipline scientifique consistant à collecter, analyser et préserver les preuves numériques à la suite d'un incident de sécurité en vue de procédures internes ou judiciaires.
*   **Mémoire volatile (RAM)** — Mémoire temporaire d'un ordinateur contenant les données actives des programmes en cours d'exécution. Elle s'efface dès que la machine est éteinte.
*   **Ordre de volatilité** — Principe de collecte des preuves numériques : capturer d'abord ce qui s'efface le plus vite (RAM, connexions actives), en dernier ce qui persiste (disque dur).
*   **Piratage éthique (Ethical Hacking)** — Pratique consistant à utiliser les mêmes techniques d'intrusion qu'un pirate malveillant, mais de manière légale, encadrée et autorisée, afin d'identifier et de corriger les faiblesses d'un système.
*   **Playbook** — Procédure de réaction pré-écrite pour un type d'incident donné (ex. « ransomware », « compte compromis ») : qui fait quoi, dans quel ordre, avec quels outils.
*   **Réponse aux incidents (Incident Response - IR)** — Processus structuré permettant à une organisation de détecter, de contenir, d'éradiquer et de se relever d'une cyberattaque.
*   **Sauvegarde immuable** — Sauvegarde dont le contenu ne peut être ni modifié ni effacé, même par un administrateur système, protégeant des rançongiciels.

---

### 1. Le cycle de réponse aux incidents (IR) : Les 6 étapes clés

!!! info "À retenir"
    En pleine crise, l'ennemi n°1 n'est pas l'attaquant : c'est la **panique**, qui fait éteindre les machines, écraser les preuves et improviser la communication. Le cycle en 6 étapes existe pour remplacer la panique par une procédure.

Pour éviter la panique et les erreurs de manipulation lors d'une cyberattaque (ex. un rançongiciel en cours de chiffrement), les équipes de sécurité suivent le cycle standardisé en 6 étapes du SANS Institute (le NIST décrit les mêmes réalités en 4 phases — voir l'encadré mentor) :

```
[1. Préparation] ➔ [2. Identification] ➔ [3. Confinement] ➔ [4. Éradication] ➔ [5. Restauration] ➔ [6. Leçons apprises]
```

1. **Préparation** : Mettre en place les outils de sécurité, former les équipes, rédiger les procédures d'urgence (playbooks) et définir qui appeler en cas de crise — y compris un canal de communication de secours si la messagerie tombe.
2. **Identification** : Détecter l'incident de sécurité (ex. une alerte SOC — la session A6 en action) et en déterminer la nature, la gravité et le périmètre.
3. **Confinement** : Isoler les systèmes touchés pour empêcher l'attaque de se propager (ex. débrancher un serveur infecté du réseau, désactiver des comptes compromis) — **sans les éteindre**, pour préserver les preuves.
4. **Éradication** : Supprimer l'origine de l'incident (ex. supprimer les malwares, effacer les portes dérobées, réinstaller les serveurs à partir d'une image propre).
5. **Restauration** : Remettre en production les systèmes nettoyés et restaurer les données à partir de sauvegardes saines (le 3-2-1 d'A4 trouve ici sa raison d'être), tout en surveillant attentivement l'activité pour s'assurer que le pirate ne revient pas.
6. **Leçons apprises** : Analyser l'incident a posteriori (RETEX) pour comprendre comment il s'est produit, évaluer l'efficacité de la réaction et modifier les défenses pour éviter qu'il ne se reproduise.

L'ordre n'est pas négociable : restaurer avant d'éradiquer, c'est réinstaller la maison pendant que le cambrioleur a encore le double des clés — le dilemme que vous avez voté en session A1 (l'hôpital, sondage final) prend ici tout son sens méthodologique.

### Activité — La Timeline du Détective (Sondages Livestorm n°2 et 3)

**Consignes pour le mentor :** Projetez les 5 événements ci-dessous **dans le désordre** (l'ordre d'affichage conseillé : C, A, E, B, D). Annoncez : « le SOC vous transmet 5 constats en vrac — reconstituez l'histoire. » Lancez les deux sondages, débriefez, puis révélez la chronologie complète.

Les 5 événements (chronologie réelle, à ne pas afficher d'emblée) :

- **B.** Lundi 09:12 — Un commercial reçoit un e-mail « mise à jour du portail RH » et saisit ses identifiants sur un faux site.
- **D.** Mardi 03:14 — Connexion réussie au VPN de l'entreprise depuis une adresse IP inconnue, avec le compte du commercial.
- **E.** Mardi 03:20 — Le compte accède au serveur de fichiers et parcourt les répertoires financiers (déplacement latéral).
- **C.** Mercredi 02:00 — Transfert de 10 Go de données vers un serveur externe.
- **A.** Mercredi 02:05 — Alerte SIEM « volume sortant anormal » ; le SOC ouvre un ticket.

*   **📊 Sondage n°2 :** Parmi ces 5 constats, lequel est le **point de départ** réel de l'attaque ?
    *   A) L'alerte SIEM de mercredi
    *   B) L'e-mail de lundi matin et la saisie des identifiants ✅
    *   C) La connexion VPN de mardi 03:14
    *   D) Le transfert de 10 Go
*   **📊 Sondage n°3 :** Quelle défense unique aurait cassé cette chaîne au meilleur rapport coût/efficacité ?
    *   A) Le MFA sur le VPN : les identifiants volés n'auraient pas suffi à se connecter ✅
    *   B) Interdire les e-mails externes dans l'entreprise
    *   C) Chiffrer le serveur de fichiers
    *   D) Doubler la taille de l'équipe SOC

**Éléments de débriefing (pour le mentor) :**

- N°2 : l'alerte n'est pas l'attaque — elle en est la **découverte**, 41 heures plus tard. Entre le clic de lundi et l'alerte de mercredi : tout le parcours des sessions A2 (phishing), A4 (identifiants) et A3 (déplacement latéral). Faire reconstituer la chronologie B → D → E → C → A à voix haute.
- N°3 : réponse A — rejouer la hiérarchie d'A4 (le MFA bloque l'usage d'identifiants volés). B est disproportionné (on tue l'activité), C ne bloque pas un compte légitime volé, D améliore la détection mais pas la prévention. Leçon transversale : **la réponse aux incidents commence des mois avant l'incident, dans l'architecture.**
- Conclure : « voilà pourquoi la phase 6 — leçons apprises — est la plus rentable du cycle : c'est elle qui transforme 41 heures d'aveuglement en un correctif d'architecture. »

### 2. Introduction au Forensics et préservation des preuves

L'investigation numérique s'apparente à une enquête de police scientifique, transposée au monde virtuel. Les enquêteurs doivent collecter des indices sans modifier la scène de crime.

#### A. L'ordre de volatilité des données
Les données informatiques s'effacent à des vitesses différentes. Les enquêteurs collectent d'abord les données les plus volatiles :

* **Mémoire vive (RAM)** : Contient les mots de passe saisis en clair, les clés de chiffrement temporaires et la liste des connexions réseau actives de l'attaquant. Si on éteint l'ordinateur, toutes ces preuves cruciales disparaissent instantanément.
* **Connexions réseau et processus actifs** : La photographie de ce que fait l'attaquant en ce moment même — perdue dès la déconnexion.
* **Fichiers temporaires & caches système** : Traces d'exécution récentes.
* **Stockage physique (Disque dur)** : Fichiers persistants, logs enregistrés, fichiers supprimés récupérables.

C'est la justification technique du réflexe de confinement : **débrancher le réseau isole l'attaquant ; éteindre la machine détruit les preuves.** Les deux gestes se ressemblent, leurs conséquences sont opposées.

#### B. La Chaîne de contrôle (*Chain of Custody*)
Pour qu'une preuve numérique soit acceptée devant un tribunal, l'enquêteur doit prouver qu'elle n'a pas été modifiée lors de sa collecte ou de son analyse.

* *Comment ?* On réalise une **copie bit-à-bit** (clone exact) du disque dur d'origine. On calcule ensuite l'**empreinte numérique** (hachage SHA-256 — le « cachet de cire » de la session A1) du clone. Si l'empreinte correspond exactement à celle du disque d'origine, on prouve que la copie est identique. Toutes les analyses sont ensuite menées uniquement sur la copie, l'original restant scellé sous clé, chaque manipulation étant consignée (qui, quand, pourquoi).

### 3. Cadre légal : Piratage éthique vs Intrusions illégales

En France, la loi encadre strictement l'accès aux systèmes informatiques. Les articles 323-1 et suivants du Code pénal définissent les délits liés aux "atteintes aux systèmes de traitement automatisé de données" (STAD).

* **L'infraction de base** : Le simple fait d'accéder ou de se maintenir frauduleusement dans un système informatique est puni de peines pouvant atteindre **2 ans d'emprisonnement et 60 000 € d'amende** — portées à **3 ans et 100 000 €** lorsqu'il en résulte une altération ou une suppression de données, et jusqu'à **5 ans et 150 000 €** pour l'entrave au fonctionnement d'un système (art. 323-1 et 323-2). Le fait que le système ait été mal sécurisé n'est pas une excuse légale — la porte ouverte n'autorise pas le cambriolage.
* **Le cadre du piratage éthique** : Un testeur d'intrusion (*pentester*) ne peut agir qu'après la signature d'un **contrat écrit explicite** (ordre de mission) définissant précisément le périmètre d'attaque autorisé, la période de test et les outils utilisés. Dépasser ce périmètre contractuel (ex. attaquer le site d'un sous-traitant de son client) constitue un délit pénal.
* **La doctrine française face aux rançons** : les autorités (ANSSI en tête) recommandent de **ne pas payer** — payer n'offre aucune garantie de récupération, finance l'écosystème criminel et désigne l'organisation comme un payeur récidivable. C'est le choix qu'a assumé l'hôpital de Corbeil-Essonnes (revu plus bas). À noter : le dépôt de plainte est désormais une condition d'indemnisation par les cyber-assurances en France.

---

### Focus pratique
Lors d'un incident sur un poste de travail, voici l'ordre dans lequel les éléments techniques doivent être capturés par l'équipe de réponse à incident :

| Niveau de volatilité | Élément technique | Méthode d'acquisition | Risque de perte |
| :--- | :--- | :--- | :--- |
| **Très Élevé** | Données de la mémoire vive (RAM). | Extraction via outil de dump mémoire (ex. FTK Imager). | Perte immédiate si arrêt de la machine ou redémarrage. |
| **Élevé** | Connexions réseau et processus actifs. | Commandes système d'observation en direct. | Perte dès la déconnexion réseau ou arrêt du processus. |
| **Moyen** | Fichiers temporaires et fichiers système. | Copie logique des répertoires temporaires. | Écriture de nouveaux logs écrasant les anciens. |
| **Bas** | Données du disque dur (fichiers stockés). | Copie bit-à-bit (clonage physique du disque). | Persistant sur le support physique hors tension. |

### 4. L'incident en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **Plusieurs mois** : le délai moyen entre une intrusion et son confinement complet (IBM, *Cost of a Data Breach*, 2025 — rappel de la session A1). La réponse aux incidents vise à transformer ces mois en heures.
    - **72 heures** : le délai de notification d'une violation de données à la CNIL (RGPD, rappel A5) — le chrono démarre à la **découverte**, d'où le lien direct entre détection (A6) et obligation légale.
    - **~300 millions de dollars** : les pertes déclarées par le transporteur Maersk après NotPetya (2017) — et **10 jours** pour reconstruire l'intégralité de son informatique mondiale (cas détaillé ci-dessous).
    - **Ne pas payer** : la doctrine constante des autorités françaises face aux rançons (ANSSI) — et la ligne tenue par l'hôpital de Corbeil-Essonnes en 2022.

**Comment lire ces chiffres ?** (1) La réponse aux incidents est une course contre deux chronomètres : celui de l'attaquant et celui du régulateur. (2) Le coût d'un incident dépend moins de l'attaque que de la **préparation** de la victime — Maersk va le prouver. (3) La décision de payer ou non se prend à froid, dans la phase de préparation — jamais à chaud, à 3 heures du matin.

### 5. Deux cas réels : la reconstruction héroïque et le retour à Corbeil-Essonnes

#### Cas n°1 — Maersk et NotPetya (2017) : reconstruire un géant en dix jours

Le 27 juin 2017, NotPetya (croisé en session A1) frappe le géant danois du transport maritime **Maersk** — 20 % du fret conteneurisé mondial. En quelques minutes, l'infection se propage : environ **4 000 serveurs et 45 000 postes de travail** sont irrécupérables, les terminaux portuaires s'arrêtent, les réservations se font au téléphone et sur papier. Pire : les sauvegardes de l'annuaire central (le « cerveau » du réseau, qui gère tous les comptes) ont été détruites avec le reste... sauf une. Par miracle logistique, le contrôleur de domaine de la filiale du **Ghana** était hors ligne au moment de l'attaque — une **coupure de courant** l'avait déconnecté. Ce serveur africain, transporté par relais humain, devient la graine de la reconstruction. Bilan : l'informatique mondiale de Maersk réinstallée en **dix jours** — un exploit salué par toute la profession — pour environ **300 millions de dollars** de pertes tout de même.

**Ce que ce cas illustre :** les phases 3 à 5 du cycle en conditions extrêmes (confinement mondial, éradication par reconstruction totale, restauration depuis LA sauvegarde survivante) ; la valeur littéralement vitale d'une copie **hors ligne** (le 3-2-1 d'A4 : ici, le « hors site » était involontaire — ne comptez pas sur une coupure de courant au Ghana) ; et la communication de crise improvisée (téléphones personnels, messageries grand public) qui a fonctionné mais a coûté cher en coordination. La phase 1 — Préparation — est celle qui aurait transformé l'exploit en simple procédure.

#### Cas n°2 — Retour à Corbeil-Essonnes (2022) : le cycle IR vu de l'intérieur

Vous connaissez ce cas depuis la session A1 — relisons-le avec vos outils de la session 7. **Identification** : l'attaque LockBit est détectée dans la nuit du 20 au 21 août 2022 ; les équipes de garde donnent l'alerte. **Confinement** : les systèmes sont isolés, l'hôpital bascule en mode dégradé — retour au papier, transferts de patients critiques. **Décision de crise** : la rançon de 10 M$ est refusée, conformément à la doctrine française ; l'ANSSI est mobilisée en appui. **Éradication et restauration** : des mois de reconstruction méthodique, service par service, avec l'exigence de ne rien remettre en production qui ne soit assaini. **Leçons apprises** : l'incident a accéléré, au niveau national, les programmes de renforcement de la cybersécurité des hôpitaux. Ce qui n'a PAS manqué : des équipes formées au mode dégradé (les soignants savent travailler au papier) — une forme de « préparation » héritée des exercices de continuité.

**Ce que ce cas illustre :** le cycle complet sur un cas français que vous connaissez déjà — la preuve que la grille de lecture fonctionne ; et le poids des décisions non techniques (payer ou non, communiquer ou non, transférer les patients ou non) : la réponse aux incidents est un sport de direction générale autant que d'ingénieurs.

!!! question "💬 Question chat — Transition"
    Chez Maersk, la sauvegarde qui a tout sauvé était hors ligne **par accident**. **Dans le chat : dans votre organisation (ou chez vous !), existe-t-il une copie de données qui survivrait à un incident détruisant TOUT ce qui est connecté ? Répondez par oui / non / je ne sais pas.** Le mentor commente la répartition : « les "je ne sais pas" sont la vraie réponse majoritaire — et c'est exactement ce qu'un exercice de crise révèle avant que la réalité ne s'en charge. »

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez la réponse sur incident de cybersécurité comme l'intervention des **pompiers après un départ de feu** :
    - **La Détection** : L'alarme incendie se déclenche (l'alerte remonte au SOC).
    - **Le Confinement (Containment)** : Fermer les portes coupe-feu pour éviter que les flammes ne se propagent au reste du bâtiment (ex. débrancher la machine infectée du réseau local).
    - **L'Éradication** : Éteindre le foyer du feu avec de l'eau et s'assurer qu'il ne reste plus de braises chaudes (ex. nettoyer le malware et supprimer le script malveillant).
    - **La Reconstruction (Recovery)** : Aérer les pièces, nettoyer la suie et rouvrir les bureaux (ex. réinstaller le système propre et restaurer les fichiers depuis la dernière sauvegarde saine).
    - **Le Forensics** : L'enquêteur de police cherche l'origine du départ de feu pour savoir s'il est criminel ou accidentel (ex. analyser les logs systèmes pour trouver l'adresse IP d'origine de l'intrus).
    - **Les Leçons apprises** : la commission de sécurité met à jour les consignes et re-planifie l'exercice d'évacuation.

**Exemple d'application professionnelle :**
Une PME subit une attaque par Ransomware. Le serveur de comptabilité commence à chiffrer ses fichiers. La procédure d'incident est immédiatement déclenchée : le serveur est isolé du réseau en moins de 15 minutes, limitant l'infection. Les logs de pare-feu et les journaux systèmes sont copiés de façon intègre (forensics) avant de restaurer le serveur à partir des sauvegardes de la veille. Quinze minutes de confinement contre quarante et une heures dans la Timeline du Détective : toute la différence entre une PME préparée et une PME qui découvre le cycle IR le jour J.

### Panorama des solutions du marché (Commerciales & Open-Source)

Lors d'un incident de sécurité ou pour mener une investigation numérique (forensics), des outils spécialisés sont indispensables :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **EnCase Forensic / FTK (Forensic Toolkit)** : Standards industriels reconnus par la justice et les experts cyber pour l'acquisition intègre de disques durs et l'investigation numérique approfondie.
    *   **CrowdStrike Falcon Forensics** : Outil d'investigation cloud permettant aux analystes de collecter rapidement des artefacts système à distance lors d'un incident actif.
    *   **Veeam Incident Recovery** : Solution de restauration d'urgence après ransomware, garantissant que les données réinjectées sont exemptes de malwares.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **Autopsy (The Sleuth Kit)** : Plateforme d'investigation numérique open-source la plus connue. Elle permet d'analyser des images de disques durs, de récupérer des fichiers supprimés et d'explorer l'historique d'un système.
    *   **Volatility** : Outil open-source leader pour l'analyse judiciaire de la mémoire vive (RAM forensics), permettant d'extraire des connexions réseau actives et des clés de chiffrement en mémoire.
    *   **Velociraptor** : Outil open-source d'investigation rapide d'endpoints et de réponse active à grande échelle.

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer après les études de cas — et AVANT le re-vote final.

*   **📊 Sondage n°6 :** Lors de la collecte de preuves, que capture-t-on en PREMIER ?
    *   A) Le disque dur (copie bit-à-bit)
    *   B) La mémoire vive (RAM) et les connexions actives ✅
    *   C) Les e-mails de l'utilisateur
    *   D) Les sauvegardes de la semaine passée
*   **📊 Sondage n°7 :** À quoi sert le calcul d'empreinte (hachage) dans la chaîne de contrôle ?
    *   A) À chiffrer le disque pour le protéger
    *   B) À prouver que la copie analysée est strictement identique à l'original ✅
    *   C) À accélérer l'analyse du disque
*   **📊 Sondage n°8 :** Un pentester découvre pendant sa mission que le sous-traitant de son client semble vulnérable. Peut-il le tester « pour être complet » ?
    *   A) Oui, c'est dans l'intérêt du client
    *   B) Non : hors du périmètre écrit de l'ordre de mission, c'est un délit pénal ✅
    *   C) Oui, s'il prévient par e-mail après coup

**Éléments de débriefing (pour le mentor) :**

- N°6 : re-projeter l'ordre de volatilité — on capture d'abord ce qui s'évapore.
- N°7 : le hachage est le « cachet de cire » d'A1 appliqué à la justice : il ne cache rien, il prouve l'intégrité.
- N°8 : le périmètre écrit est la frontière entre le métier et le délit — rappel des sessions A1 et A6.

### 📊 Sondage Livestorm n°9 — Le vote APRÈS (re-vote du sondage n°1)

**Consignes pour le mentor :** Relancez EXACTEMENT le sondage du début de session (le poste infecté : votre premier geste ?). Affichez les deux résultats côte à côte.

**Débrief scripté :** La bonne réponse — désormais massivement votée, en principe — est **B : débrancher le réseau sans éteindre**. Éteindre (A) détruit la RAM, donc les clés de chiffrement et les preuves ; le scan antivirus (C) laisse l'attaquant connecté pendant 3 heures ; l'e-mail collectif (D) alerte tout le monde sauf les bonnes personnes — et peut alerter l'attaquant. Commentez la progression entre les deux votes : c'est la photographie de ce que le groupe a appris en 90 minutes.

### Questions de réflexion

1. Chez Maersk, la sauvegarde salvatrice était accidentelle. Que faudrait-il institutionnaliser pour que la survie ne dépende plus de la chance ? (Reliez au 3-2-1 immuable d'A4.)
2. La phase « Leçons apprises » est unanimement décrite comme la plus rentable... et la plus souvent sautée. Pourquoi, à votre avis ? Comment une direction peut-elle la rendre incontournable ?
3. Votre messagerie est chiffrée par un ransomware un lundi matin. Par quel canal la cellule de crise communique-t-elle ? Qui décide de ce canal, et quand aurait-il fallu le décider ?
4. Le forensics ralentit la remise en production (on clone avant de réinstaller). Comment arbitrer entre « comprendre l'attaque » et « redémarrer l'activité » ? Qui doit trancher ?

## 3. Ressources complémentaires

* **IBM SkillsBuild** : Cours sur l'investigation numérique (Digital Forensics) et la réponse à incident.
* **[ANSSI — Organiser un exercice de gestion de crise cyber](https://cyber.gouv.fr/publications/organiser-un-exercice-de-gestion-de-crise-cyber)** : le guide de référence — la lecture qui prépare directement l'atelier final A8.
* **[Cybermalveillance.gouv.fr — Que faire en cas de cyberattaque](https://www.cybermalveillance.gouv.fr)** : les fiches réflexes par type d'incident.
* **SANS Institute** : Fiches de référence sur la réponse aux incidents (Incident Handler's Handbook — le modèle PICERL de cette session).
* **Légifrance** : Code pénal, articles 323-1 à 323-7 (atteintes aux systèmes de traitement automatisé de données).

## 4. Exercice bonus (Sondage Forensics - Livestorm)

*   **Objectif :** Compréhension de la préservation des preuves.
*   **📊 Sondage Livestorm n°10 :** Un employé a cliqué sur un lien suspect et a entré ses identifiants. Vous suspectez une intrusion. Pourquoi ne devez-vous pas réinstaller immédiatement le système ?
    *   A) Parce que cela coûte trop cher.
    *   B) Pour préserver les traces de l'attaque afin d'analyser comment le pirate est entré et ce qu'il a volé ✅
    *   C) Parce que la réinstallation va propager le virus.
*   **Guide d'animation (pour le mentor) :** Expliquez le but du forensics : comprendre l'origine et l'étendue de l'attaque pour éviter qu'elle ne se reproduise le lendemain de la réinstallation. Reboucler avec la Timeline du Détective : réinstaller le poste du commercial lundi soir n'aurait pas fermé le VPN sans MFA. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **CERT / CSIRT** | Équipe spécialisée de réponse aux incidents ; le CERT-FR (ANSSI) est l'équipe nationale française. |
| **Chaîne de contrôle (Chain of Custody)** | Documentation stricte de qui a manipulé chaque preuve, garantissant qu'elle n'a subi aucune altération (copie bit-à-bit + hachage). |
| **Confinement** | Isoler les systèmes compromis pour stopper la propagation — sans les éteindre. |
| **Cycle IR (SANS, 6 étapes)** | Préparation → Identification → Confinement → Éradication → Restauration → Leçons apprises (le NIST regroupe en 4 phases). |
| **Éradication** | Éliminer définitivement la source de l'incident (malware, portes dérobées, comptes piratés). |
| **Forensics (Investigation numérique)** | Collecter, analyser et préserver les preuves numériques en vue de procédures internes ou judiciaires. |
| **Mémoire volatile (RAM)** | Contient les données actives (clés, connexions) ; s'efface à l'extinction — d'où « isoler sans éteindre ». |
| **Ordre de volatilité** | Capturer d'abord ce qui s'efface le plus vite : RAM → connexions/processus → fichiers temporaires → disque. |
| **Piratage éthique (Ethical Hacking)** | Techniques d'intrusion utilisées légalement, dans le strict périmètre d'un ordre de mission écrit. |
| **Playbook** | Procédure de réaction pré-écrite par type d'incident : qui fait quoi, dans quel ordre. |
| **Réponse aux incidents (IR)** | Processus structuré pour détecter, contenir, éradiquer un incident et s'en relever. |
| **Sauvegarde immuable** | Sauvegarde que ni un administrateur ni un ransomware ne peuvent modifier ou effacer. |

**La règle d'or de la session :** en cas d'infection : **isoler, jamais éteindre** — et souvenez-vous que la réponse aux incidents se gagne avant l'incident : préparation, sauvegardes hors ligne, canal de crise, exercice.
