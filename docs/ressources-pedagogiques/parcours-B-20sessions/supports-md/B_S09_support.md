# Session B09 — Gestion des identités et des accès (IAM)
Parcours : B 20 sessions  |  Module : C — Identités, cloud & données  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Les 4 piliers de l'IAM (Identity and Access Management)
    - RBAC vs ABAC : Comment attribuer les droits ?
    - SSO (Single Sign-On) et cycle de vie des identités
    - Deux affaires réelles : Uber (2022), la MFA vaincue par la fatigue, et 23andMe (2023), les mots de passe recyclés
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   L'**Identification** déclare qui vous êtes, l'**Authentification** le prouve, l'**Autorisation** accorde les droits d'accès et l'**Audit** trace vos actions.
*   Le **MFA** combine au moins deux facteurs de natures différentes (ce que je sais, ce que je possède, ce que je suis) pour neutraliser le vol simple de mot de passe.
*   Le modèle **RBAC** structure les droits par rôles métier, tandis que le modèle **ABAC** utilise des variables dynamiques (IP, heure, lieu) pour une plus grande granularité.
*   Le **SSO** simplifie l'expérience utilisateur et renforce la sécurité des accès en centralisant l'authentification — à condition de protéger ce compte unique par MFA.

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Distinguer et expliquer les quatre étapes fondamentales de l'IAM : Identification, Authentification, Autorisation et Audit.
* Comparer le modèle de contrôle d'accès basé sur les rôles (RBAC) avec le modèle basé sur les attributs (ABAC).
* Modéliser et concevoir une politique d'authentification multifacteur (MFA) et d'authentification unique (SSO) pour sécuriser l'accès aux données sensibles d'une entreprise.

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** Selon le rapport Verizon DBIR, quel est le premier moyen utilisé par les attaquants pour obtenir leur accès initial aux systèmes des entreprises ?

    - A) Les identifiants volés ou réutilisés (mots de passe compromis) ✅
    - B) Les failles zero-day inconnues des éditeurs
    - C) L'intrusion physique dans les locaux

    **Débrief mentor :** Réponse A : année après année, l'abus d'identifiants volés reste en tête des vecteurs d'accès initial — de l'ordre d'une violation sur cinq selon le Verizon DBIR 2025. Les attaquants ne « piratent » pas : ils **se connectent**, avec de vrais identifiants achetés, hameçonnés ou rejoués depuis d'anciennes fuites. Tout le module qui s'ouvre ce soir — le module Identités — répond à ce constat : le nouveau périmètre de sécurité, ce ne sont plus les murailles (module B), c'est **qui a les clés**.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Le cycle de vie des identités (JML : Joiner, Mover, Leaver)**
Détaillez les trois moments critiques : l'arrivée (*Joiner* — provisionner selon le rôle, pas plus), la mobilité (*Mover* — LE point faible : les droits s'accumulent au fil des mutations si personne ne retire les anciens, c'est la « dérive des privilèges » ou *privilege creep*), et le départ (*Leaver* — révocation immédiate et totale, rappel de l'offboarding de B02 et du compte dormant de Colonial Pipeline en B08). La revue périodique des droits (recertification) est le filet de sécurité de tout le cycle.

**2. Tous les MFA ne se valent pas**
Hiérarchisez les facteurs pour les questions avancées : le **SMS** est le plus faible (interception via les faiblesses du réseau SS7, et surtout **SIM swapping** — l'attaquant fait transférer la ligne de la victime sur sa propre carte SIM en manipulant l'opérateur) ; les **applications TOTP** (codes à usage unique) sont un bon standard ; les **notifications push** sont confortables mais vulnérables à la **fatigue MFA** (cas Uber de la session — parade : le *number matching*) ; les **clés FIDO2/passkeys** sont le sommet : résistantes à l'hameçonnage par conception, car la preuve cryptographique est liée au site légitime — un faux site ne peut rien en obtenir.

**3. Les protocoles du SSO : SAML et OIDC**
Pour les curieux (et le travail en autonomie) : le SSO d'entreprise repose sur des standards ouverts — **SAML 2.0** (historique, très répandu en entreprise) et **OpenID Connect/OAuth 2.0** (moderne, natif web et mobile). Principe commun : l'application ne voit jamais le mot de passe ; elle reçoit du fournisseur d'identité (IdP) une **assertion signée** (« cet utilisateur est bien authentifié, voici ses attributs »). C'est ce découplage qui permet la révocation centralisée instantanée.

---

### Glossaire

*   **ABAC (Attribute-Based Access Control)** — Contrôle d'accès dynamique fondé sur des règles combinant les attributs de l'utilisateur, de la ressource et du contexte (heure, lieu, réseau).
*   **Credential stuffing (Bourrage d'identifiants)** — Attaque consistant à rejouer en masse des couples identifiant/mot de passe issus d'anciennes fuites sur d'autres services, en pariant sur la réutilisation des mots de passe.
*   **Fatigue MFA (MFA fatigue / push bombing)** — Attaque consistant à bombarder la victime de notifications MFA jusqu'à ce qu'elle accepte, par lassitude ou par erreur.
*   **IAM (Identity and Access Management)** — Système et ensemble de règles gérant les identités numériques et contrôlant les droits d'accès aux ressources.
*   **IdP (Identity Provider)** — Fournisseur d'identité central auprès duquel s'effectue l'authentification unique (SSO) et qui émet les preuves d'identité vers les applications.
*   **MFA (Multi-Factor Authentication)** — Méthode de validation d'identité requérant l'association d'au moins deux preuves de catégories distinctes (savoir, possession, biométrie).
*   **Passkey / FIDO2** — Méthode d'authentification par clé cryptographique (matérielle ou intégrée à l'appareil), résistante à l'hameçonnage par conception.
*   **RBAC (Role-Based Access Control)** — Mécanisme de contrôle d'accès dans lequel les autorisations système sont liées à des rôles professionnels plutôt qu'à des personnes.
*   **SIM swapping** — Fraude consistant à faire transférer la ligne mobile de la victime vers la carte SIM de l'attaquant pour intercepter ses codes SMS.
*   **SSO (Single Sign-On)** — Technologie d'authentification unique permettant à un utilisateur d'accéder à plusieurs applications avec un seul compte d'accès.

---

### Concepts clés

!!! info "À retenir"
    Les attaquants ne piratent plus, ils **se connectent** : le mot de passe volé est leur premier vecteur d'entrée. La riposte tient en trois couches : prouver l'identité fortement (MFA — et tous les MFA ne se valent pas), n'accorder que le nécessaire (RBAC, moindre privilège), et tracer puis réviser en permanence (audit, cycle de vie JML).

### 1. Les 4 piliers de l'IAM (Identity and Access Management)
L'IAM regroupe les processus et technologies visant à garantir que les bonnes personnes ont accès aux bonnes ressources, au bon moment et pour les bonnes raisons. Il repose sur quatre étapes distinctes et successives :

*   **Identification** : L'acte de déclarer qui vous êtes. C'est l'identifiant public de l'utilisateur (nom d'utilisateur, adresse e-mail, matricule).
*   **Authentification (AuthN)** : L'acte de prouver que vous êtes bien la personne identifiée. Cela repose sur la fourniture de facteurs de preuve.
*   **Autorisation (AuthZ)** : L'acte d'accorder ou de refuser des privilèges d'accès à des ressources spécifiques après vérification de l'identité (ex. lire, modifier ou supprimer un fichier).
*   **Audit (ou Responsabilité/Traçabilité)** : L'enregistrement historique des actions de l'utilisateur (logs de connexion, fichiers consultés, modifications effectuées) afin de pouvoir retracer les incidents de sécurité.

*   *L'analogie de l'immeuble sécurisé* :
    *   **Identification** : Vous vous présentez à l'accueil et dites : *"Je suis Alice Martin, consultante externe"*.
    *   **Authentification** : L'agent de sécurité vous demande de présenter votre passeport pour le prouver.
    *   **Autorisation** : L'agent vous remet un badge magnétique programmé uniquement pour ouvrir les portes des salles de réunion du 1er étage (accès aux serveurs du sous-sol refusé).
    *   **Audit** : À chaque fois que vous passez votre badge sur un lecteur, l'heure et la porte franchie sont enregistrées dans le registre de sécurité du bâtiment.

#### Les 3 types de facteurs d'authentification :
*   *Ce que l'on sait* : Un mot de passe, un code PIN, une réponse à une question secrète.
*   *Ce que l'on possède* : Un smartphone (qui reçoit un code par application), une clé matérielle (ex. YubiKey), un token matériel générant des codes à usage unique (OTP).
*   *Ce que l'on est* : Une caractéristique biométrique (empreinte digitale, reconnaissance faciale ou de l'iris).

!!! warning "Authentification Multifacteur (MFA) : la règle des catégories"
    Pour être qualifiée de « multifacteur », une authentification doit utiliser **au moins deux facteurs issus de catégories différentes**. Saisir deux mots de passe différents n'est PAS du MFA (deux fois « ce que l'on sait »). Saisir un mot de passe et valider dans une application sur son smartphone est du MFA (savoir + posséder). Et tous les seconds facteurs ne se valent pas : le SMS est le plus fragile (SIM swapping), l'application d'authentification est un bon standard, la clé FIDO2/passkey résiste même à l'hameçonnage.

### 2. RBAC vs ABAC : Comment attribuer les droits ?
Une fois l'utilisateur authentifié, le système doit décider de ses droits d'accès. Deux modèles logiques s'affrontent :

*   **RBAC (*Role-Based Access Control*)** : Les droits d'accès sont liés à des **rôles métier** prédéfinis au sein de l'organisation. L'administrateur attribue des droits aux rôles (ex. le rôle "RH" peut modifier le dossier du personnel), puis affecte les employés à ces rôles. C'est simple à administrer et idéal pour les structures stables.
*   **ABAC (*Attribute-Based Access Control*)** : Les droits d'accès sont évalués de manière dynamique en fonction de règles combinant plusieurs **attributs** :
    *   *Attributs du sujet* : Rôle, département, niveau d'habilitation de l'utilisateur.
    *   *Attributs de la ressource* : Sensibilité du document (Public ou Confidentiel), format.
    *   *Attributs environnementaux* : Heure de connexion, localisation géographique (adresse IP de l'entreprise ou connexion depuis l'étranger).
    *   *Exemple d'accès ABAC* : *"Un utilisateur ayant le rôle Comptable peut modifier les fichiers financiers SEULEMENT pendant les heures de bureau (8h-18h) ET s'il est connecté sur le réseau de l'entreprise (pas en Wi-Fi public à l'étranger)"*.

### Activité — La matrice RBAC de MedDistri (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Affichez le contexte : MedDistri (notre PME fil rouge, dont vous avez sécurisé le réseau en B08) veut structurer les droits sur 4 ressources — le dossier candidats RH, la base de factures, la console cloud d'administration, le portail d'actualités interne — pour 4 profils : RH_Manager, Comptable, Admin_IT, Stagiaire_Marketing. Droits possibles : **W** (écriture), **R** (lecture seule), **N** (aucun accès). Trois cas votés, puis la matrice complète est reconstituée à l'écran.

*   **📊 Sondage n°2 — Le Stagiaire_Marketing :** Quel profil de droits lui attribuez-vous ?
    *   A) Lecture partout : « il est là pour apprendre »
    *   B) Aucun accès aux ressources sensibles, lecture seule du portail d'actualités ✅
    *   C) Écriture sur le portail d'actualités et lecture du reste
*   **📊 Sondage n°3 — Le Comptable et le dossier candidats RH :** Quel droit ?
    *   A) Lecture : « il doit pouvoir vérifier les prétentions salariales »
    *   B) Aucun accès : les données RH ne relèvent pas de son besoin métier ✅
    *   C) Écriture : la paie et le recrutement, c'est pareil
*   **📊 Sondage n°4 — L'Admin_IT et la base de données des factures :** Quel droit ?
    *   A) Écriture : il administre les serveurs, donc les données qu'ils contiennent
    *   B) Lecture : pour vérifier que la base fonctionne
    *   C) Aucun accès aux données métier : administrer l'infrastructure n'est pas accéder au contenu ✅

**Éléments de débriefing (pour le mentor) :**

- N°2 : le réflexe « lecture partout pour apprendre » est la première cause de sur-attribution. Le besoin métier du stagiaire : s'informer (R sur le portail). Rien d'autre. C'est le moindre privilège appliqué aux personnes (rappel B08).
- N°3 : le piège est la justification plausible (A) — presque tous les accès excessifs ont une bonne excuse. Le critère n'est pas « ça pourrait servir » mais « le rôle l'exige-t-il ? ».
- N°4 : LE piège classique de l'IAM — confondre administration technique et accès aux données. L'Admin_IT gère la console (W sur l'infrastructure), pas le contenu métier : c'est la **séparation des privilèges**. Si son compte est compromis, les factures ne le sont pas automatiquement.
- **Reconstituer la matrice complète à l'écran :**

| Rôle / Ressource | Dossier Candidats RH | Base de données Factures | Console cloud | Portail Actualités |
|---|---|---|---|---|
| **RH_Manager** | **W** | **N** | **N** | **R** |
| **Comptable** | **N** | **W** | **N** | **R** |
| **Admin_IT** | **N** | **N** | **W** | **R** |
| **Stagiaire_Marketing** | **N** | **N** | **N** | **R** |

### 3. SSO (Single Sign-On) et cycle de vie des identités
Le **SSO** (ou Authentification Unique) est un mécanisme permettant à un utilisateur de ne saisir ses identifiants qu'une seule fois auprès d'un fournisseur d'identité central (IdP), afin d'accéder automatiquement à l'ensemble de ses applications d'entreprise compatibles (messagerie, CRM, outils RH).

*   *Avantage cyber* : Réduit la "lassitude des mots de passe" des employés (qui ont tendance à réutiliser le même mot de passe partout s'ils doivent en retenir cinquante différents — la matière première du *credential stuffing*).
*   *Avantage administration* : Permet de désactiver instantanément tous les accès d'un salarié qui quitte l'entreprise en bloquant son compte unique auprès du fournisseur d'identité.
*   *Le revers de la médaille* : le compte SSO devient un **point de défaillance unique** — s'il est compromis, TOUTES les applications le sont. Conséquence non négociable : MFA robuste obligatoire sur ce compte, et surveillance renforcée de ses connexions.

**Le cycle de vie des identités (JML)** : une politique d'accès ne vaut que si elle vit — à l'arrivée (*Joiner*), on provisionne selon le rôle ; à chaque mobilité (*Mover*), on retire les anciens droits AVANT d'accorder les nouveaux (sinon les privilèges s'accumulent — la « dérive des privilèges ») ; au départ (*Leaver*), on révoque tout, immédiatement. La revue périodique des droits est le filet de sécurité de l'ensemble.

### 4. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **De l'ordre d'une violation sur cinq** commence par l'abus d'identifiants volés — le premier vecteur d'accès initial, année après année (Verizon DBIR 2025).
    - **Environ 6,9 millions de personnes** touchées par la fuite 23andMe en 2023... à partir de ~14 000 comptes seulement, compromis par simple réutilisation de mots de passe (chiffres communiqués par l'entreprise).
    - **2022** : Uber, géant mondial de la technologie, compromis en profondeur par un attaquant présenté comme âgé de 17-18 ans — sans exploit, en fatiguant la MFA d'un prestataire.

**Comment lire ces chiffres ?** (1) Le mot de passe seul est mort : il se vole, se rejoue, se revend. (2) La MFA est indispensable mais pas invincible — sa mise en œuvre compte (push simple < number matching < FIDO2). (3) Quelques milliers de mots de passe recyclés peuvent exposer des millions de personnes : votre hygiène protège aussi les autres.

### 5. Deux affaires réelles : la MFA fatiguée et les mots de passe recyclés

#### Cas n°1 — Uber (2022) : quand l'attaquant sonne jusqu'à ce qu'on ouvre

Septembre 2022. Un attaquant — présenté par la presse et la justice comme un adolescent lié au groupe Lapsus$ — achète sur le marché noir les identifiants d'un **prestataire** d'Uber (rappel : Target, TV5... le prestataire, encore). Le mot de passe est bon, mais la MFA bloque : chaque tentative de connexion envoie une notification push sur le téléphone du prestataire. L'attaquant applique alors la **fatigue MFA** : il enchaîne les tentatives, déclenchant des notifications en rafale — puis contacte sa victime sur WhatsApp en se faisant passer pour le support informatique d'Uber : *« Pour faire cesser les notifications, acceptez la demande. »* La victime accepte. L'attaquant est dans le VPN. Il y découvre un script contenant des identifiants d'administration codés en dur... et accède à une large partie des systèmes internes de l'entreprise, jusqu'à interpeller les employés sur leur propre messagerie Slack.

**Ce que ce cas illustre :** la MFA par notification push a une faille **comportementale**, pas cryptographique — l'humain finit par accepter (parade : le *number matching*, qui exige de saisir un code affiché à l'écran de connexion — l'objet de l'exercice bonus) ; l'ingénierie sociale (B04) et l'IAM se combinent : la technique bloque, l'attaquant manipule ; et les secrets codés en dur dans des scripts transforment un accès limité en compromission générale.

#### Cas n°2 — 23andMe (2023) : 14 000 mots de passe recyclés, 6,9 millions de victimes

Fin 2023, la société d'analyse génétique **23andMe** révèle une fuite massive. Le mode opératoire n'a rien d'exotique : du ***credential stuffing*** — les attaquants ont rejoué sur le site des couples e-mail/mot de passe issus d'anciennes fuites d'autres services. Environ **14 000 comptes** ont cédé, ceux dont les propriétaires réutilisaient leur mot de passe. Mais l'effet s'est démultiplié : via la fonction de mise en relation généalogique (« DNA Relatives »), chaque compte compromis exposait les données de ses apparentés — au total, les informations d'environ **6,9 millions de personnes**. L'entreprise a ensuite rendu la MFA obligatoire... après coup.

**Ce que ce cas illustre :** la réutilisation de mots de passe transforme la fuite d'hier chez X en intrusion de demain chez Y (d'où : un mot de passe unique par service + gestionnaire) ; l'absence de MFA par défaut a laissé le champ libre à une attaque triviale ; et dans les systèmes interconnectés, VOTRE négligence expose les AUTRES — une leçon qui dépasse la génétique.

!!! tip "📊 Sondage Livestorm n°5 — Et vous ? (sondage d'opinion, pas de bonne réponse)"
    **Question :** En toute honnêteté, quelle est votre pratique actuelle des mots de passe ?

    - A) Un gestionnaire de mots de passe, tous uniques
    - B) Quelques mots de passe « socles » que je décline selon les sites
    - C) Le même (ou presque) un peu partout

    **Débrief mentor :** Sondage anonyme et sans jugement — B et C sont majoritaires dans toute population non sensibilisée. Le message n'est pas la culpabilité mais la mécanique : 23andMe vient de montrer que le recyclage d'un mot de passe déjà fuité ailleurs suffit — pas besoin de vous « pirater ». La sortie par le haut : un gestionnaire (il retient à votre place), des mots de passe uniques, et la MFA partout où elle existe — en commençant par votre messagerie, la clé de récupération de tous vos autres comptes.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Une collaboratrice de MedDistri est mutée de la comptabilité au service marketing. Son responsable demande « qu'on lui ouvre les accès marketing ». **Tapez A, B ou C dans le chat :**

    - A) Ajouter les accès marketing à son compte : elle garde les accès comptables « au cas où, pour la passation ».
    - B) Accorder les accès marketing ET retirer les accès comptables (avec une période de passation courte, datée et tracée si nécessaire). ✅
    - C) Supprimer son compte et en créer un nouveau de zéro, quitte à la bloquer quelques jours.

    **Débrief mentor :** B — c'est le « M » du cycle JML (*Mover*), le moment le plus négligé : les droits s'ajoutent, ne se retirent jamais, et après trois mutations un salarié cumule les accès de trois métiers — la « dérive des privilèges ». Si une passation est réellement nécessaire, elle se borne dans le temps et se trace. A crée exactement le profil sur-privilégié dont rêvent les attaquants ; C punit l'activité (et sera contourné). La revue périodique des droits attrape ce que le quotidien laisse passer.

---

### Questions de réflexion
1. Si un attaquant parvient à voler le mot de passe d'un utilisateur sur un site web non protégé par MFA, comment le MFA l'empêcherait-il de compromettre le compte ? Quel facteur d'authentification bloquerait l'attaquant ?
2. Imaginez qu'une entreprise adopte le Single Sign-On (SSO). Si le compte SSO unique d'un utilisateur est piraté, quelles en sont les conséquences ? Quelles mesures de sécurité compensatoires doit-on obligatoirement mettre en place sur ce compte unique ?
3. Dans l'affaire Uber, la victime disposait pourtant du MFA. Pourquoi l'attaque a-t-elle réussi malgré tout, et en quoi le « number matching » ou une clé FIDO2 auraient-ils changé l'issue ?

**Corrigé / Éléments de réponse :**

1. Le MFA bloque l'attaquant car il ne possède pas le deuxième facteur (téléphone, clé FIDO), même s'il a le bon mot de passe. Le facteur « ce que l'on possède » (ou la biométrie) fait barrage.
2. Si le compte SSO est compromis, l'attaquant a accès à toutes les applications de l'utilisateur (point de défaillance unique). Le MFA robuste est donc une obligation absolue sur ce compte, complété par la surveillance des connexions (géolocalisation, horaires) et une procédure de révocation rapide.
3. La faille exploitée était comportementale : la notification push permet d'accepter par lassitude ou par erreur, et l'attaquant a ajouté une couche d'ingénierie sociale (le faux support). Le *number matching* casse ce schéma (il faut recopier un code affiché sur l'écran de connexion de l'attaquant — que la victime ne voit pas) ; une clé FIDO2 l'élimine par conception (la preuve est liée au site légitime, rien à accepter à distance).

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez le fonctionnement de la gestion des identités et des accès (IAM) comme la sécurité d'un **laboratoire de recherche secret** :
    - **L'Identification** : Vous vous présentez à l'accueil et donnez votre nom (votre identifiant/login).
    - **L'Authentification** : Vous devez prouver qui vous êtes en glissant votre badge et en scannant votre empreinte digitale (Authentification Multifacteur - MFA).
    - **L'Autorisation (RBAC)** : Les portes d'accès aux salles ne s'ouvrent que si votre rôle de "Chercheur en chimie" est enregistré dans le système informatique central. Un employé administratif (rôle différent) ne verra pas la porte s'ouvrir.
    - **L'Audit** : Le journal du système enregistre précisément l'heure d'entrée et de sortie de chaque pièce pour assurer la traçabilité.
    - **Le SSO (Single Sign-On)** : Vous passez le grand portail principal sécurisé une fois, ce qui déverrouille automatiquement toutes les portes intérieures auxquelles vous avez droit pour la journée.

**Exemple d'application professionnelle :**
Une entreprise déploie une solution IAM centralisée. Suite au départ soudain d'un collaborateur, le service RH désactive son compte dans l'annuaire d'entreprise unique. Instantanément, tous ses accès VPN, courriels et logiciels Cloud (SaaS) sont révoqués via le SSO, éliminant tout risque de sabotage post-départ.

### Panorama des solutions du marché (Commerciales & Open-Source)

La gestion des identités et des accès (IAM) et l'authentification forte (MFA/SSO) sont indispensables pour contrôler les comptes d'accès :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Microsoft Entra ID (anciennement Azure Active Directory)** : Le leader absolu de la gestion d'identités d'entreprise et du SSO, particulièrement optimisé pour l'écosystème Office 365.
    *   **Okta Workforce Identity Cloud** : Plateforme IAM neutre et indépendante leader sur le marché, facilitant l'authentification unique (SSO) multi-cloud.
    *   **Duo Security (Cisco)** : Solution de référence pour la mise en place d'authentification multifacteur (MFA) ergonomique et de contrôle des accès Zero Trust.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **Keycloak** : Solution d'IAM et de Single Sign-On (SSO) open-source développée par Red Hat. Elle prend en charge les protocoles standards comme SAML 2.0, OpenID Connect et OAuth 2.0.
    *   **Authentik** : Fournisseur d'identité open-source moderne et flexible, intégrant nativement la gestion des accès applicatifs, du MFA et des portails de connexion.
    *   **Authelia** : Portail d'authentification unique léger et open-source, parfait pour sécuriser des applications web auto-hébergées avec du MFA (TOTP / clés de sécurité physiques YubiKey).

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après le mini-scénario.

*   **📊 Sondage n°6 :** Un site vous demande votre mot de passe PUIS la réponse à une question secrète. Est-ce du MFA ?
    *   A) Oui : il y a bien deux vérifications successives
    *   B) Non : ce sont deux facteurs de la même catégorie (« ce que l'on sait ») ✅
    *   C) Oui, si la question secrète est difficile
*   **📊 Sondage n°7 :** Quelle règle relève du modèle ABAC (et non du RBAC) ?
    *   A) « Le rôle Comptable peut modifier les factures »
    *   B) « Le rôle RH peut lire les dossiers du personnel »
    *   C) « Le Comptable peut modifier les factures uniquement aux heures de bureau et depuis le réseau de l'entreprise » ✅
*   **📊 Sondage n°8 :** Un salarié quitte l'entreprise. Quel avantage décisif le SSO apporte-t-il à ce moment précis ?
    *   A) Il permet de récupérer les mots de passe du salarié
    *   B) La désactivation du compte unique révoque instantanément TOUS ses accès applicatifs ✅
    *   C) Il transfère automatiquement ses accès à son remplaçant

**Éléments de débriefing (pour le mentor) :**

- N°6 : le critère est la **catégorie** (savoir / posséder / être), pas le nombre de questions. Deux « savoirs » se volent de la même façon (fuite, hameçonnage).
- N°7 : dès que la décision dépend du **contexte** (heure, lieu, réseau), on est dans l'ABAC. Le RBAC répond à « qui peut quoi », l'ABAC ajoute « dans quelles conditions ».
- N°8 : c'est le « L » du cycle JML — la révocation centralisée instantanée. Rappel de la chaîne : Colonial Pipeline (B08), c'est précisément le compte qui n'a jamais été révoqué.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Identity and Access Management Fundamentals"* (durée estimée : 1h30).
*   **Recherche complémentaire** : Renseignez-vous sur le protocole standard ouvert **SAML 2.0** et sur le protocole **OIDC (OpenID Connect)**. Découvrez comment ils permettent au SSO d'échanger des preuves d'identité sécurisées entre applications.
*   [CNIL — Sécuriser vos mots de passe](https://www.cnil.fr/fr/mots-de-passe-une-nouvelle-recommandation-pour-maitriser-sa-securite)
*   [ANSSI — Recommandations relatives à l'authentification multifacteur et aux mots de passe](https://cyber.gouv.fr/publications/recommandations-relatives-lauthentification-multifacteur-et-aux-mots-de-passe)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Compréhension des attaques par fatigue d'authentification.
*   **📊 Sondage Livestorm n°9 :** Un attaquant possède le mot de passe d'un utilisateur et envoie des dizaines de notifications push MFA sur son smartphone au milieu de la nuit jusqu'à ce que l'utilisateur clique sur "Accepter" par exaspération. Comment contrer cette attaque ?
    *   A) Désactiver complètement le MFA.
    *   B) Activer le "Number Matching" (l'utilisateur doit saisir sur son téléphone un numéro affiché à l'écran de connexion) ✅
    *   C) Rendre le mot de passe encore plus complexe.
*   **Guide d'animation (pour le mentor) :** C'est exactement l'attaque qui a fait tomber Uber en 2022. Le Number Matching élimine la vulnérabilité comportementale : impossible d'accepter « par réflexe », il faut recopier un code que seul l'écran de connexion légitime affiche — l'attaquant, lui, ne peut pas le transmettre à sa victime. La clé FIDO2 va encore plus loin en supprimant toute action à distance. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **ABAC** | Droits évalués dynamiquement selon les attributs et le contexte (heure, lieu, réseau). |
| **Credential stuffing** | Rejouer des identifiants issus d'anciennes fuites — l'arme contre les mots de passe recyclés (23andMe). |
| **Fatigue MFA** | Bombarder de notifications push jusqu'à l'acceptation — parade : number matching, FIDO2 (cas Uber). |
| **IAM — les 4 piliers** | Identification (qui ?), Authentification (preuve), Autorisation (droits), Audit (traçabilité). |
| **JML (Joiner, Mover, Leaver)** | Le cycle de vie des identités — le « M » est le maillon faible (dérive des privilèges). |
| **MFA** | Au moins deux facteurs de catégories différentes ; hiérarchie : SMS < application TOTP < push avec number matching < FIDO2/passkey. |
| **RBAC** | Les droits suivent les rôles métier — la matrice de MedDistri. |
| **SSO** | Un compte unique pour toutes les applications : confort + révocation instantanée... et point de défaillance unique → MFA obligatoire. |

**La règle d'or de la session :** les attaquants se connectent avec de vrais identifiants — imposez la MFA (la plus robuste possible), n'accordez que ce que le rôle exige, retirez ce qu'il n'exige plus, et tracez tout : l'identité est le nouveau périmètre.
