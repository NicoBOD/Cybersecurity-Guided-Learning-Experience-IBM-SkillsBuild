# Session B04 — Ingénierie sociale & facteur humain

## Objectifs de la session
À la fin de cette session, vous serez capable de :

* Décoder les 5 principaux leviers psychologiques (urgence, autorité, sympathie, peur, preuve sociale) exploités par les attaquants lors d'une manipulation.
* Distinguer techniquement et fonctionnellement les différents vecteurs d'ingénierie sociale : *Phishing* (email), *Spear-phishing* (ciblé), *Smishing* (SMS) et *Vishing* (téléphone).
* Rédiger et structurer des règles d'hygiène numérique simples et applicables pour sensibiliser efficacement des collaborateurs en entreprise.

---

## Concepts clés

### 1. La psychologie de la manipulation (Ingénierie sociale)

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

L'ingénierie sociale (*Social Engineering*) regroupe l'ensemble des techniques de manipulation psychologique visant à inciter une personne à contourner les règles de sécurité ou à divulguer des informations confidentielles. Les pirates ciblent les failles cognitives humaines plutôt que les failles logicielles. Ils exploitent des leviers psychologiques précis :

*   **L'autorité** : Se faire passer pour une figure hiérarchique supérieure (le directeur général, un avocat de l'entreprise, un policier). La victime obéit par respect ou crainte de la hiérarchie.
    *   *Exemple* : L'arnaque au président, où un comptable reçoit l'ordre direct (présumé) du PDG d'effectuer un virement confidentiel et urgent pour un rachat d'entreprise.
*   **L'urgence** : Créer un sentiment de panique temporelle pour empêcher la victime de réfléchir rationnellement ou de vérifier l'information.
    *   *Exemple* : "Votre compte bancaire va être suspendu dans 2 heures si vous ne validez pas ce lien."
*   **La sympathie ou la réciprocité** : Instaurer une relation cordiale ou feindre de rendre service pour endormir la méfiance.
    *   *Exemple* : Un faux support technique qui appelle pour aider à résoudre un "problème réseau détecté" sur votre poste.
*   **La peur ou l'intimidation** : Utiliser la menace pour forcer l'action.
    *   *Exemple* : "Si vous ne payez pas l'amende pour téléchargement illégal immédiatement, des poursuites judiciaires seront engagées."
*   **La preuve sociale** : Faire croire que tout le monde réalise déjà l'action demandée pour rassurer la victime.
    *   *Exemple* : "Tous vos collègues ont déjà signé cette nouvelle charte RH en ligne, veuillez cliquer ici pour faire de même."

### 2. Canaux et vecteurs d'attaque
L'ingénierie sociale emprunte différents canaux technologiques et de communication :

*   **Le Phishing (Hameçonnage)** : Envoi d'un email massif et impersonnel imitant un tiers de confiance (banque, impôts, service de livraison) pour collecter des identifiants ou propager un malware.
*   **Le Spear-phishing (Hameçonnage ciblé)** : Attaque hautement personnalisée visant une personne précise. L'attaquant utilise des informations glanées au préalable (sur les réseaux sociaux professionnels, le site de l'entreprise) pour rendre l'email extrêmement crédible.
*   **Le Smishing (SMS phishing)** : Hameçonnage par SMS. Le message contient généralement un lien raccourci vers une fausse interface mobile (ex. fausse amende de stationnement ANTAI, colis bloqué).
*   **Le Vishing (Voice phishing)** : Hameçonnage vocal par téléphone. L'attaquant appelle la victime en usurpant l'identité d'un conseiller bancaire, d'un technicien informatique ou d'un auditeur de sécurité pour lui extorquer des codes de double authentification (MFA).

### 3. L'hygiène numérique d'entreprise
La sécurité humaine repose sur des réflexes simples mais rigoureux, que l'on qualifie d'**hygiène numérique** (*cyber hygiene*). Elle comprend :

*   **La gestion des mots de passe** : Utiliser des mots de passe longs (au moins 12 à 15 caractères), uniques pour chaque service, et stockés dans un gestionnaire de mots de passe sécurisé.
*   **Le Double Facteur (MFA — *Multi-Factor Authentication*)** : Activer systématiquement la double validation (code SMS, application d'authentification) pour toutes les connexions.
*   **La culture de la vérification** : Mettre en place des procédures de double validation hors canal (ex. rappeler un fournisseur sur son numéro officiel connu en cas de changement de RIB reçu par email).

> 💡 **Bon à savoir : L'erreur humaine n'est pas une fatalité**
> Punir ou humilier un employé qui s'est fait piéger par une simulation de phishing est contre-productif. Les meilleures politiques de sensibilisation valorisent le signalement rapide de l'erreur au département de sécurité afin de circonscrire l'incident au plus vite.

---

## Activités / exercices

### Exercice 1 — Création d'une fiche d'onboarding "5 règles d'hygiène cyber"
**Objectif :** Rédiger une fiche mémo synthétique, positive et accessible (sans jargon technique) destinée aux nouveaux salariés d'une PME pour leur donner les clés de l'hygiène cyber dès leur arrivée.

**Consignes :**

1. Formulez 5 règles d'or courtes et concrètes.
2. Pour chaque règle, expliquez brièvement le risque évité et le comportement attendu.
3. Présentez le livrable sous forme de guide de poche attractif.

**Corrigé / Éléments de réponse (Exemple de Kit d'onboarding) :**

#### Bienvenue chez EcoLog ! Vos 5 réflexes de sécurité au quotidien

1.  **Vos clés d'accès : Longues et uniques !**
    *   *Le comportement* : Utilisez des phrases de passe (mots de passe de plus de 12 caractères faciles à retenir) et stockez-les dans le gestionnaire de mots de passe de l'entreprise. Ne réutilisez jamais votre mot de passe professionnel sur un site personnel (loisirs, e-commerce).
    *   *Le risque évité* : Le piratage en cascade de tous vos comptes si l'un d'eux venait à fuiter sur Internet.
2.  **La double clé (MFA) : Activée partout !**
    *   *Le comportement* : Configurez l'application d'authentification sur votre téléphone professionnel pour valider vos accès à la messagerie et aux outils cloud.
    *   *Le risque évité* : Même si un attaquant devine ou vole votre mot de passe, il ne pourra pas se connecter à votre compte sans le code de votre téléphone.
3.  **Au bureau comme en déplacement : Verrouillez !**
    *   *Le comportement* : Prenez le réflexe de verrouiller votre session (touche `Windows + L` ou `Cmd + Ctrl + Q` sur Mac) dès que vous quittez votre bureau, même pour une minute.
    *   *Le risque évité* : La consultation ou modification de données sensibles par une personne de passage ou un prestataire externe.
4.  **Emails et SMS : Doutez d'abord !**
    *   *Le comportement* : Si un message vous demande une action urgente, suspecte (changement de RIB, mot de passe à renouveler) ou inhabituelle, ne cliquez sur aucun lien. Contactez l'expéditeur via son numéro de téléphone habituel pour vérifier.
    *   *Le risque évité* : Le vol d'identifiants ou l'installation d'un rançongiciel sur le réseau de l'entreprise.
5.  **En cas d'erreur : Alertez immédiatement !**
    *   *Le comportement* : Vous avez cliqué sur un lien suspect ou saisi vos identifiants sur une page douteuse ? Ne paniquez pas et prévenez tout de suite le support informatique. Aucun blâme ne vous sera fait.
    *   *Le risque évité* : Permettre à une infection de se propager en silence sur l'ensemble des serveurs de l'entreprise pendant des heures.

---

## Questions de réflexion
1. Pourquoi le Spear-phishing (hameçonnage ciblé) a-t-il un taux de réussite beaucoup plus élevé que le phishing de masse ? Quelles traces publiques un attaquant recherche-t-il sur LinkedIn pour monter son scénario ?
2. Face à un appel téléphonique d'un interlocuteur affirmant être de votre banque et vous demandant de "valider des transactions de test" sur votre application mobile pour annuler une fraude en cours (Vishing), quelle est la seule réaction sécurisée ?

---

!!! abstract "Résumé"
    / points à retenir
    *   L'ingénierie sociale repose sur l'exploitation de faiblesses psychologiques (urgence, peur, autorité) et non sur des failles logicielles.
    *   Les attaques se déclinent sur tous les canaux : e-mail (phishing), SMS (smishing), téléphone (vishing).
    *   L'hameçonnage ciblé (spear-phishing) utilise des informations publiques et personnelles pour piéger précisément sa victime.
    *   L'hygiène cyber (mots de passe forts, MFA, verrouillage, doute systématique et culture du signalement) est le premier bouclier de l'entreprise.

---

## Glossaire de la session
*   **Phishing (Hameçonnage)** — Envoi massif d'e-mails frauduleux pour dérober des données confidentielles.
*   **Spear-phishing (Hameçonnage ciblé)** — Variante d'hameçonnage hautement personnalisée visant un individu ou une organisation spécifique.
*   **Smishing** — Hameçonnage réalisé par le biais de messages textes (SMS).
*   **Vishing (Hameçonnage vocal)** — Technique d'ingénierie sociale par téléphone visant à extorquer des informations confidentielles.

---

## Pour aller plus loin (self-paced)
*   **Sur IBM SkillsBuild** : Suivre le cours *"Introduction to Cybersecurity Tools & Cyber Attacks - Social Engineering"* (~1h00).
*   **Recherche autonome** : Se renseigner sur le concept d'OSINT (*Open Source Intelligence*) pour comprendre comment les attaquants collectent légalement des informations publiques sur les entreprises.


## Exercice Bonus (Temps additionnel)
**Si vous avez terminé en avance (avant les 1h30 de session) :**
- **Objectif :** Mise en pratique autonome.
- **Consignes :** Réfléchissez à un exemple réel ou une actualité récente liée au sujet de cette session. Discutez en groupe de la manière dont les concepts vus s'appliquent à cet exemple.
- **Correction :** Le mentor validera les réflexions et apportera son expertise.

## Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Concept clé** | À compléter selon la session |

## Ressources pour aller plus loin

* [ANSSI - Agence Nationale de la Sécurité des Systèmes d'Information](https://www.ssi.gouv.fr/)
* [Cybermalveillance.gouv.fr](https://www.cybermalveillance.gouv.fr/)
* [OWASP - Open Worldwide Application Security Project](https://owasp.org/)
