# Session B09 — Gestion des identités et des accès (IAM)

## Objectifs de la session
À la fin de cette session, vous serez capable de :

* Distinguer et expliquer les quatre étapes fondamentales de l'IAM : Identification, Authentification, Autorisation et Audit.
* Comparer le modèle de contrôle d'accès basé sur les rôles (RBAC) avec le modèle basé sur les attributs (ABAC).
* Modéliser et concevoir une politique d'authentification multifacteur (MFA) et d'authentification unique (SSO) pour sécuriser l'accès aux données sensibles d'une entreprise.

---

## Concepts clés

### 1. Les 4 piliers de l'IAM (Identity and Access Management)
L'IAM regroupe les processus et technologies visant à garantir que les bonnes personnes ont accès aux bonnes ressources, au bon moment et pour les bonnes raisons. Il repose sur quatre étapes distinctes et successives :

*   **Identification** : L'acte de déclarer qui vous êtes. C'est l'identifiant publique de l'utilisateur (nom d'utilisateur, adresse e-mail, matricule).
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
*   *Ce que l'on possède* : Un smartphone (qui reçoit un code par SMS/application), une clé matérielle (ex. YubiKey), un token matériel générant des codes à usage unique (OTP).
*   *Ce que l'on est* : Une caractéristique biométrique (empreinte digitale, reconnaissance faciale ou de l'iris).

> [!IMPORTANT]
> **Authentification Multifacteur (MFA)** : Pour être qualifiée de "multifacteur", une authentification doit utiliser **au moins deux facteurs issus de catégories différentes**. Saisir deux mots de passe différents n'est pas du MFA (deux fois "ce que l'on sait"). Saisir un mot de passe et valider une notification sur son smartphone est du MFA (savoir + posséder).

### 2. RBAC vs ABAC : Comment attribuer les droits ?
Une fois l'utilisateur authentifié, le système doit décider de ses droits d'accès. Deux modèles logiques s'affrontent :

*   **RBAC (*Role-Based Access Control*)** : Les droits d'accès sont liés à des **rôles métier** prédéfinis au sein de l'organisation. L'administrateur attribue des droits aux rôles (ex. le rôle "RH" peut modifier le dossier du personnel), puis affecte les employés à ces rôles. C'est simple à administrer et idéal pour les structures stables.
*   **ABAC (*Attribute-Based Access Control*)** : Les droits d'accès sont évalués de manière dynamique en fonction de règles combinant plusieurs **attributs** :
    *   *Attributs du sujet* : Rôle, département, niveau d'habilitation de l'utilisateur.
    *   *Attributs de la ressource* : Sensibilité du document (Public ou Confidentiel), format.
    *   *Attributs environnementaux* : Heure de connexion, localisation géographique (adresse IP de l'entreprise ou connexion depuis l'étranger).
    *   *Exemple d'accès ABAC* : *"Un utilisateur ayant le rôle Comptable peut modifier les fichiers financiers SEULEMENT pendant les heures de bureau (8h-18h) ET s'il est connecté sur le réseau de l'entreprise (pas en Wi-Fi public à l'étranger)"*.

### 3. SSO (Single Sign-On)
Le **SSO** (ou Authentification Unique) est un mécanisme permettant à un utilisateur de ne saisir ses identifiants qu'une seule fois auprès d'un fournisseur d'identité central (IdP), afin d'accéder automatiquement à l'ensemble de ses applications d'entreprise compatibles (messagerie, CRM, outils RH).

*   *Avantage cyber* : Réduit la "lassitude des mots de passe" des employés (qui ont tendance à réutiliser le même mot de passe partout s'ils doivent en retenir cinquante différents).
*   *Avantage administration* : Permet de désactiver instantanément tous les accès d'un salarié qui quitte l'entreprise en bloquant son compte unique auprès du fournisseur d'identité.

---

## Activités / exercices

### Exercice 1 — La Matrice RBAC de l'entreprise "MediDistri"
**Objectif :** Concevoir une matrice de contrôle d'accès logique basée sur les rôles (RBAC) pour respecter le principe du moindre privilège.

**Consignes :**
L'entreprise "MediDistri" distribue des produits médicaux et souhaite structurer les droits d'accès à ses 4 ressources clés :

1.  **Dossier Candidats RH** : Contient les CV et salaires des candidats.
2.  **Base de données Factures** : Contient les informations de paiement des clients.
3.  **Console Administrative AWS** : Console cloud gérant les serveurs de production.
4.  **Portail Actualités** : L'intranet d'information interne de l'entreprise.

Vous devez définir les droits d'accès de 4 profils d'utilisateurs distincts :

*   **RH_Manager** : Responsable du recrutement.
*   **Comptable** : Responsable des factures clients.
*   **Admin_IT** : Responsable technique de l'infrastructure cloud.
*   **Stagiaire_Marketing** : Stagiaire en charge de la communication.

Pour chaque intersection, attribuez l'un des droits suivants :

*   **W** : Écriture, modification, suppression (*Write*).
*   **R** : Lecture seule (*Read*).
*   **N** : Aucun accès (*No access*).

**Tableau à remplir :**

| Rôle / Ressource | Dossier Candidats RH | Base de données Factures | Console AWS | Portail Actualités |
|---|---|---|---|---|
| **RH_Manager** | ... | ... | ... | ... |
| **Comptable** | ... | ... | ... | ... |
| **Admin_IT** | ... | ... | ... | ... |
| **Stagiaire_Marketing** | ... | ... | ... | ... |

**Corrigé / Éléments de réponse :**

| Rôle / Ressource | Dossier Candidats RH | Base de données Factures | Console AWS | Portail Actualités | Justifications pédagogiques |
|---|---|---|---|---|---|
| **RH_Manager** | **W** | **N** | **N** | **R** | A besoin d'écrire sur les dossiers RH. N'a aucun besoin lié aux factures ou aux serveurs AWS. Lit l'intranet. |
| **Comptable** | **N** | **W** | **N** | **R** | Modifie les factures clients. Pas d'accès aux RH ni à l'administration AWS. |
| **Admin_IT** | **N** | **N** | **W** | **R** | Gère techniquement l'infrastructure cloud. N'a aucun droit de lecture/écriture sur les données RH ou financières. |
| **Stagiaire_Marketing** | **N** | **N** | **N** | **R** | N'a aucun besoin métier d'accès aux serveurs, factures ou RH. Ne peut que lire les actualités internes. |

---

## Questions de réflexion
1. Si un attaquant parvient à voler le mot de passe d'un utilisateur sur un site web non protégé par MFA, comment le MFA l'empêcherait-il de compromettre le compte ? Quel facteur d'authentification bloquerait l'attaquant ?
2. Imaginez qu'une entreprise adopte le Single Sign-On (SSO). Si le compte SSO unique d'un utilisateur est piraté, quelles en sont les conséquences ? Quelles mesures de sécurité compensatoires doit-on obligatoirement mettre en place sur ce compte unique ?

---

## Résumé / points à retenir
*   L'**Identification** déclare qui vous êtes, l'**Authentification** le prouve, l'**Autorisation** accorde les droits d'accès et l'**Audit** trace vos actions.
*   Le **MFA** combine au moins deux facteurs de natures différentes (ce que je sais, ce que je possède, ce que je suis) pour neutraliser le vol simple de mot de passe.
*   Le modèle **RBAC** structure les droits par rôles métier, tandis que le modèle **ABAC** utilise des variables dynamiques (IP, heure, lieu) pour une plus grande granularité.
*   Le **SSO** simplifie l'expérience utilisateur et renforce la sécurité des accès en centralisant l'authentification.

---

## Glossaire de la session
*   **IAM (Identity and Access Management)** — Système et ensemble de règles gérant les identités numériques et contrôlant les droits d'accès aux ressources.
*   **MFA (Multi-Factor Authentication)** — Méthode de validation d'identité requérant l'association de plusieurs preuves de catégories distinctes.
*   **RBAC (Role-Based Access Control)** — Mécanisme de contrôle d'accès dans lequel les autorisations système sont liées à des rôles professionnels plutôt qu'à des personnes.
*   **SSO (Single Sign-On)** — Technologie d'authentification unique permettant à un utilisateur d'accéder à plusieurs applications avec un seul compte d'accès.

---

## Pour aller plus loin (self-paced)
*   **Sur IBM SkillsBuild** : Suivre le cours *"Identity and Access Management Fundamentals"* (durée estimée : 1h30).
*   **Recherche complémentaire** : Renseignez-vous sur le protocole standard ouvert **SAML 2.0** et sur le protocole **OIDC (OpenID Connect)**. Découvrez comment ils permettent au SSO d'échanger des preuves d'identité sécurisées entre applications.
