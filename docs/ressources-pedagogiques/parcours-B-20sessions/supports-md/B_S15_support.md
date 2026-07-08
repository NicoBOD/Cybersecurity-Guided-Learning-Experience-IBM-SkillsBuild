# Session B15 — Conformité & réglementations vie privée

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Les Fondamentaux du RGPD
    - Le rôle de la CNIL et les sanctions
    - Le Délégué à la Protection des Données (DPO — Data Protection Officer)
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Le **RGPD** impose des principes stricts (minimisation, limitation de conservation, consentement libre) pour protéger la vie privée des résidents européens.
*   En cas d'incident de sécurité sur des données personnelles, l'entreprise doit notifier la **CNIL sous 72 heures maximum**.
*   Les sanctions de la **CNIL** peuvent être financières (jusqu'à 4 % du CA mondial) et porter une atteinte grave à la réputation de l'entreprise.
*   Le **DPO** orchestre la conformité interne, tient le registre des traitements obligatoires et fait l'interface avec l'autorité de contrôle.

---

## 2. Développement

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer les obligations réglementaires majeures d'un organisme au titre du RGPD (Registre, consentement, sécurité, notification sous 72h).
* Identifier le rôle d'autorité de la CNIL et mesurer les risques financiers et d'image associés aux sanctions pour non-conformité.
* Auditer une politique de confidentialité d'entreprise pour en extraire les clauses non conformes et proposer des corrections adaptées.
* Soutenir et évaluer le livrable du **Mini-projet 3 (Évaluation des risques & charte PSSI)**.

---

### Glossaire
*   **Donnée personnelle** — Toute information se rapportant à une personne physique identifiée ou identifiable de manière directe ou indirecte.
*   **Traitement de données** — Toute opération ou ensemble d'opérations portant sur des données personnelles (collecte, hébergement, modification, transfert).
*   **CNIL** — Commission Nationale de l'Informatique et des Libertés. Autorité administrative publique française de régulation des données personnelles.
*   **DPO (Data Protection Officer)** — Délégué à la Protection des Données. Expert interne ou externe chargé de veiller à l'application du RGPD au sein de l'organisme.

---

### Concepts clés

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

### 1. Les Fondamentaux du RGPD
Entré en vigueur en mai 2018, le **RGPD** (Règlement Général sur la Protection des Données) est le cadre juridique européen régissant la collecte et le traitement des données à caractère personnel.

*   **Donnée à caractère personnel** : Toute information se rapportant à une personne physique identifiée ou identifiable directement ou indirectement (ex. un nom, une adresse email, un numéro de téléphone, une adresse IP, des données de localisation, ou un numéro de sécurité sociale).
*   **Traitement** : Toute opération appliquée à des données personnelles (la collecte, l'enregistrement, l'organisation, la conservation, la modification, la consultation, l'utilisation ou la suppression).

#### Les 5 devoirs clés des entreprises sous le RGPD :
1.  **Transparence et Consentement** : L'utilisateur doit être informé clairement de l'usage de ses données (but ou *finalité*). Le consentement doit être un acte positif clair, libre, spécifique et éclairé (ex. pas de cases pré-cochées pour l'envoi de publicités).
2.  **Minimisation des données** : Collecter uniquement les données strictement nécessaires au traitement (ex. un site e-commerce n'a pas besoin de collecter la profession de l'acheteur pour livrer un colis).
3.  **Limitation de la conservation** : Les données ne peuvent pas être stockées indéfiniment. Une durée de conservation précise doit être définie (ex. 3 ans maximum pour des données de prospects inactifs).
4.  **Registre des traitements** : Document interne obligatoire listant tous les traitements de données personnelles effectués au sein de l'entreprise (qui, quoi, pourquoi, combien de temps, quelles mesures de sécurité).
5.  **Notification des violations sous 72 heures** : En cas d'incident de sécurité (piratage, fuite de données), l'entreprise a l'obligation légale de notifier l'autorité de contrôle (**la CNIL** en France) dans un délai maximal de **72 heures** après en avoir pris connaissance. Si la fuite présente un risque élevé pour les citoyens concernés, l'entreprise doit également les informer individuellement.

### 2. Le rôle de la CNIL et les sanctions
La **CNIL** (*Commission Nationale de l'Informatique et des Libertés*) est le gendarme des données personnelles en France.

*   *Missions* : Conseiller les entreprises, informer les citoyens sur leurs droits (droits d'accès, de rectification, de suppression ou "droit à l'oubli") et contrôler les systèmes d'information (audits en ligne ou sur site physique).
*   *Sanctions* : En cas de manquement grave aux règles du RGPD, la CNIL peut prononcer des amendes administratives pouvant s'élever jusqu'à **20 millions d'euros** ou **4 % du chiffre d'affaires annuel mondial** de l'entreprise délinquante, sans compter le préjudice d'image catastrophique lié à la publication publique de la sanction.

### 3. Le Délégué à la Protection des Données (DPO — Data Protection Officer)
Le **DPO** est le pilote de la conformité au sein de l'entreprise.

*   *Rôle* : Il conseille la direction sur la protection de la vie privée, s'assure de la tenue à jour du registre des traitements, mène des Analyses d'Impact sur la Protection des Données (AIPD) pour les projets à risque élevé, et sert de point de contact unique pour les demandes des citoyens ainsi que pour la CNIL en cas de contrôle ou d'incident.

---

### Activités / exercices
### Exercice 1 — Audit d'une politique de confidentialité de site web
**Objectif :** Analyser des clauses de confidentialité réelles, identifier les infractions au RGPD et rédiger des clauses de correction conformes.

**Consignes :**
L'entreprise EcoLog lance une plateforme e-commerce. Le service marketing a ébauché la charte de confidentialité ci-dessous. Identifiez les 3 infractions majeures au RGPD présentes dans ce texte, expliquez pourquoi elles enfreignent la loi, et rédigez les clauses correctives correspondantes.

#### Extrait de la Charte d'EcoLog proposé par le marketing :
> *« [...] EcoLog collecte vos informations lors de votre commande. (Clause A) Nous conservons vos données de carte bancaire de manière définitive afin de faciliter le paiement de vos futurs achats. (Clause B) En créant votre compte, vous acceptez sans réserve que vos données personnelles soient revendues à nos partenaires commerciaux sans possibilité d'opposition de votre part. (Clause C) Si vous souhaitez modifier ou supprimer vos données personnelles de notre base de données, vous devez formuler votre demande en adressant un courrier recommandé avec accusé de réception à l'attention de la direction au siège social de l'entreprise. »*

**Corrigé / Éléments de réponse :**

1.  **Analyse de la Clause A (Données bancaires)** :
    *   *Infraction* : Stockage définitif des coordonnées bancaires sans consentement explicite. Le RGPD interdit la conservation de données bancaires après la transaction, sauf si l'utilisateur y a expressément consenti pour de futurs achats, et dans ce cas, elles doivent être stockées de manière sécurisée (tokenisation).
    *   *Correction conforme* : *"Vos données de carte bancaire sont supprimées une fois la transaction finalisée. Vous pouvez choisir de les enregistrer pour de futurs achats en cochant la case d'option dédiée. Dans ce cas, elles seront chiffrées et conservées conformément aux standards bancaires de sécurité."*
2.  **Analyse de la Clause B (Vente de données & Droit d'opposition)** :
    *   *Infraction* : Consentement forcé et suppression du droit d'opposition. L'inscription au site ne doit pas être conditionnée à l'acceptation de revente de données. De plus, l'utilisateur possède un droit d'opposition absolu à la retransmission de ses données à des tiers.
    *   *Correction conforme* : *"Vos données personnelles ne seront transmises à des tiers partenaires que si vous y consentez expressément en cochant l'option facultative d'opt-in lors de la création de votre compte. Vous pouvez retirer ce consentement ou vous opposer à tout moment à cette transmission en nous écrivant."*
3.  **Analyse de la Clause C (Exercice des droits complexe)** :
    *   *Infraction* : L'exercice des droits de l'utilisateur (rectification, suppression) est rendu inutilement complexe par l'obligation d'un courrier recommandé. Le RGPD stipule que l'exercice des droits doit être aussi simple à réaliser que la collecte initiale des données (ex. par simple clic ou e-mail).
    *   *Correction conforme* : *"Vous pouvez exercer vos droits d'accès, de rectification et d'effacement de vos données personnelles à tout moment et sans frais en envoyant un e-mail à l'adresse dpo@ecolog.fr ou via notre formulaire de contact en ligne."*

---

### Questions de réflexion
1. Si une entreprise sous-traite le stockage de ses fichiers clients à un hébergeur cloud américain, qui est responsable de la conformité des données personnelles au titre du RGPD : l'entreprise (responsable de traitement) ou l'hébergeur cloud (sous-traitant) ?
2. Quelle est la différence fondamentale entre la "sécurité informatique" classique (gérée par le RSSI) et la "conformité RGPD" (supervisée par le DPO) ? Comment ces deux fonctions doivent-elles collaborer lors d'une fuite de données ?

**Corrigé / Éléments de réponse :**
1. Les deux sont responsables. L'entreprise doit s'assurer que le sous-traitant est conforme, et le sous-traitant doit garantir la sécurité des données hébergées.
2. Le RSSI protège le patrimoine de l'entreprise. Le DPO s'assure du respect des droits des personnes. En cas de fuite, ils coordonnent l'enquête technique (RSSI) et les notifications légales (DPO).

---


### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Pour bien comprendre ces concepts techniques, imaginez l'analogie suivante : la cybersécurité de votre entreprise est comme la sécurité d'une maison physique.
    - **Le Pare-feu (Firewall)** agit comme la porte d'entrée blindée : il filtre qui entre et qui sort.
    - **L'Antivirus / EDR** est comme le système d'alarme intérieur : s'il détecte un mouvement suspect, il bloque l'intrus.
    - **La Politique de mots de passe et le MFA** correspondent aux serrures multipoints et au digicode : posséder la clé ne suffit pas toujours, il faut aussi connaître le code secret.

**Exemple d'application professionnelle :**
Dans une PME, un attaquant tentera rarement de forcer les serveurs directement. Il enverra un e-mail frauduleux (Phishing) à un employé des ressources humaines. Si l'employé clique, le logiciel malveillant tente de s'installer. C'est ici que la *défense en profondeur* intervient : le filtre anti-spam aurait dû bloquer l'e-mail, l'antivirus aurait dû bloquer l'exécution, et l'absence de droits administrateurs de l'employé aurait empêché l'installation. Chaque couche est vitale.


## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Introduction to Data Privacy and GDPR"* (durée estimée : 1h30).
*   **Activité pratique** : Rendez-vous sur le site de la CNIL (cnil.fr) et lisez le résumé d'une sanction récente prononcée à l'encontre d'une entreprise pour comprendre quels manquements techniques (mots de passe trop faibles, absence de chiffrement) ont été sanctionnés.

* [ANSSI - Agence Nationale de la Sécurité des Systèmes d'Information](https://www.ssi.gouv.fr/)
* [Cybermalveillance.gouv.fr](https://www.cybermalveillance.gouv.fr/)
* [OWASP - Open Worldwide Application Security Project](https://owasp.org/)

---

## 4. Exercice bonus

- **Objectif :** Mise en pratique autonome.
- **Consignes :** Réfléchissez à un exemple réel ou une actualité récente liée au sujet de cette session. Discutez en groupe de la manière dont les concepts vus s'appliquent à cet exemple.
- **Correction :** Le mentor validera les réflexions et apportera son expertise.

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Donnée personnelle** | Toute information se rapportant à une personne physique identifiée ou identifiable de manière directe ou indirecte. |
| **Traitement de données** | Toute opération ou ensemble d'opérations portant sur des données personnelles (collecte, hébergement, modification, transfert). |
| **CNIL** | Commission Nationale de l'Informatique et des Libertés. Autorité administrative publique française de régulation des données personnelles. |
| **DPO (Data Protection Officer)** | Délégué à la Protection des Données. Expert interne ou externe chargé de veiller à l'application du RGPD au sein de l'organisme. |
