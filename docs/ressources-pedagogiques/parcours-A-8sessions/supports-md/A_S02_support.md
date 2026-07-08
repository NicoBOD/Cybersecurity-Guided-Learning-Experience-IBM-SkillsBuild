# Support de cours — Session 02 : Menaces, attaques & ingénierie sociale
Parcours : A 8 sessions  |  Module : Menaces Cyber  |  Niveau : Débutant

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - La typologie des logiciels malveillants (*Malwares*)
    - Les mécanismes de l'ingénierie sociale
    - La Cyber Kill Chain : Comprendre le parcours de l'attaquant
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

Les cyberattaques modernes ciblent de plus en plus le maillon réputé le plus vulnérable de la chaîne de sécurité : l'être humain. Ce support de cours détaille les mécanismes de l'ingénierie sociale, l'art de manipuler les personnes pour contourner les protections technologiques. Vous étudierez les principaux types de logiciels malveillants (*malware*), du rançongiciel destructeur au cheval de Troie discret. Nous décrypterons également les ressorts psychologiques du phishing (hameçonnage), du vishing (par téléphone) et les grandes étapes de la *Cyber Kill Chain*, le modèle théorique qui décrit le déroulement d'une attaque de son ciblage initial jusqu'à sa conclusion logique. L'objectif est de vous donner les clés pour identifier instantanément les signaux d'alerte et adopter des réflexes d'hygiène numérique indispensables.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Psychologie de l'Ingénierie Sociale**
Détaillez les ressorts psychologiques exploités par les attaquants : l'urgence (faux e-mail du PDG demandant un virement sous 2 heures), la peur (fausse amende gouvernementale), ou la cupidité (faux gain à un concours). Insistez sur le fait que l'humain est souvent le maillon faible malgré les meilleurs pare-feux.

**2. Anatomie d'une attaque de Spear-Phishing**
Décomposez une attaque ciblée étape par étape :
- *Reconnaissance* (OSINT) : Collecte d'informations sur l'organigramme via LinkedIn.
- *Fabrication de l'arme* : Création d'un e-mail reprenant la signature exacte du directeur financier.
- *Exploitation* : L'utilisateur clique sur une pièce jointe Excel contenant une macro malveillante.

**3. Ateliers pratiques de détection**
Passez 20 minutes à disséquer des exemples visuels de phishing : montrez comment inspecter les en-têtes d'un e-mail, vérifier le domaine de l'expéditeur (typosquatting comme `amaz0n.com`) et survoler les liens hypertextes sans cliquer.


---

### Glossaire

*   **BEC (Business Email Compromise)** — Fraude par compromission de la messagerie professionnelle, où un pirate usurpe l'identité d'un dirigeant pour ordonner des virements frauduleux.
*   **Cyber Kill Chain** — Cadre conceptuel décrivant les 7 étapes chronologiques d'une cyberattaque réussie, développé par Lockheed Martin.
*   **Ingénierie sociale (Social Engineering)** — Manipulation psychologique visant à extorquer des informations confidentielles ou à faire accomplir des actions dangereuses à une victime.
*   **Malware (Logiciel malveillant)** — Terme générique désignant tout programme conçu pour nuire à un système informatique (virus, ver, rançongiciel, etc.).
*   **Phishing (Hameçonnage)** — Technique frauduleuse par e-mail visant à tromper le destinataire pour lui soutirer des informations confidentielles (mots de passe, numéros de carte bancaire) en usurpant l'identité d'une marque de confiance.
*   **Ransomware (Rançongiciel)** — Malware qui chiffre les fichiers d'un utilisateur ou d'une entreprise et réclame le paiement d'une rançon en échange de la clé de déchiffrement.
*   **Smishing** — Attaque d'ingénierie sociale réalisée par SMS pour pousser la victime à visiter un site malveillant ou à divulguer des données.
*   **Spear-phishing (Hameçonnage ciblé)** — Variante hautement personnalisée du phishing, ciblant un individu ou une organisation spécifique en exploitant des détails personnels collectés à l'avance.
*   **Spear-phishing (Hameçonnage ciblé)** — Technique d'hameçonnage hautement personnalisée visant un individu ou une organisation spécifique à l'aide d'informations ciblées.
*   **Vishing (Hameçonnage vocal)** — Technique de manipulation par téléphone où l'attaquant usurpe l'identité d'un tiers de confiance (ex. conseiller bancaire) pour extorquer des informations.

---

### 1. La typologie des logiciels malveillants (*Malwares*)

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.


Les programmes malveillants revêtent des formes diverses selon l'objectif poursuivi par les attaquants :

#### A. Les Rançongiciels (*Ransomware*)
C'est la menace financière majeure pour les organisations. Le malware s'introduit dans le système, identifie les serveurs et les partages de fichiers critiques, puis applique un chiffrement fort. Les pirates réclament une rançon payable en cryptomonnaie en échange de l'outil de déchiffrement. Souvent, ils menacent également de divulguer publiquement les données volées (double extorsion).

#### B. Les Chevaux de Troie (*Trojan Horse*)
Un programme d'apparence légitime et inoffensive, mais contenant des fonctionnalités malveillantes cachées. Une fois installé par l'utilisateur, il ouvre des portes dérobées (*backdoors*) pour permettre aux pirates de prendre le contrôle de la machine à distance.

#### C. Les Logiciels espions (*Spyware / Keylogger*)
Des outils discrets installés sur le système pour collecter des données à l'insu de l'utilisateur. Un *keylogger* enregistre chaque touche pressée sur le clavier, capturant ainsi les mots de passe lors de leur saisie.

#### D. Les Vers (*Worms*)
Des malwares autonomes capables de se propager d'ordinateur en ordinateur à travers le réseau en exploitant des failles de sécurité, sans nécessiter d'interaction humaine (contrairement aux virus traditionnels qui nécessitent l'exécution d'un fichier hôte).



### 2. Les mécanismes de l'ingénierie sociale

L'ingénierie sociale repose sur l'exploitation de biais psychologiques humains. Les pirates n'attaquent pas les serveurs chiffrés, ils manipulent l'humain pour qu'il leur ouvre la porte.

#### Les 4 leviers de manipulation les plus courants :
1. **L'Urgence** : "Votre compte bancaire sera suspendu dans 2 heures si vous ne validez pas ce lien." L'urgence empêche la victime de réfléchir rationnellement.
2. **L'Autorité** : Le pirate se fait passer pour le directeur général, la police, ou un inspecteur des impôts pour exiger un transfert d'information.
3. **La Confiance** : Usurper l'identité d'un collègue, d'un fournisseur habituel ou d'un service connu (EDF, Netflix, La Poste).
4. **La Curiosité / L'Appât du gain** : "Vous avez gagné un bon d'achat" ou "Découvrez le fichier contenant les salaires de l'entreprise".

#### Les déclinaisons de l'hameçonnage :
* **Phishing** : E-mail générique envoyé à des millions de destinataires.
* **Spear-phishing** : E-mail personnalisé (ex. "Bonjour Julie, suite à notre discussion de ce matin sur le projet X, merci de valider ce document").
* **Smishing** : Hameçonnage par SMS (ex. "Votre colis a rencontré un problème de livraison, visitez...").
* **Vishing** : Hameçonnage par téléphone (ex. le faux conseiller bancaire appelant pour faire annuler de "fausses transactions frauduleuses").



### 3. La Cyber Kill Chain : Comprendre le parcours de l'attaquant

La *Cyber Kill Chain* permet aux défenseurs de comprendre la séquence logique d'une intrusion. Si la chaîne est brisée à n'importe quelle étape, l'attaque échoue.

```
[1. Reconnaissance] ➔ [2. Armement] ➔ [3. Livraison] ➔ [4. Exploitation] ➔ [5. Installation] ➔ [6. Commande & Contrôle (C2)] ➔ [7. Actions sur Objectifs]
```

1. **Reconnaissance** : Recherche d'informations sur la cible (adresses e-mail, outils utilisés, organigramme).
2. **Armement** : Création d'une charge malveillante (ex. un document PDF contenant un code malveillant associé à un message de phishing convaincant).
3. **Livraison** : Envoi de la charge à la victime (par e-mail, clé USB, ou téléchargement web).
4. **Exploitation** : Le code malveillant s'exécute en exploitant une vulnérabilité du système (ex. le lecteur PDF de la victime n'est pas à jour).
5. **Installation** : Le logiciel malveillant s'installe sur la machine cible pour s'y implanter durablement.
6. **Commande & Contrôle (C2)** : Le malware ouvre un canal de communication avec le serveur des pirates pour recevoir des instructions.
7. **Actions sur Objectifs** : Les attaquants atteignent leur but final (exfiltration de données confidentielles ou chiffrement du réseau).

---

### Focus pratique
Savoir identifier les indices visuels d'un e-mail malveillant est une compétence d'autodéfense numérique cruciale.

```text
De : service-clients@netf1ix-securite.com  <-- [Indice A : Domaine suspect (typosquatting)]
À : destinataire@entreprise.fr
Objet : Action requise : Suspension imminente de votre abonnement ! <-- [Indice B : Urgence artificielle]

Cher Client,
Nous n'avons pas pu valider votre dernier prélèvement mensuel. 
Veuillez cliquer immédiatement sur le lien ci-dessous pour mettre à jour vos coordonnées bancaires et éviter la perte de vos services :

👉 [METTRE A JOUR MON COMPTE] <-- [Indice C : Le lien pointe vers http://193.168.1.45/login.php et non netflix.com]

L'équipe Netflix.
```

* **Indice A** : L'adresse de l'expéditeur semble légitime mais contient des fautes discrètes (un '1' au lieu d'un 'l' dans netflix).
* **Indice B** : votre alarmiste incitant à agir sans réfléchir.
* **Indice C** : Le lien de destination réel (visible en survolant le bouton avec la souris sans cliquer) ne correspond pas au site officiel.

---

### Exercice d'application (Scénario de Crise Interactif - Livestorm)

**Consignes pour le mentor :** Présentez la situation et lancez les votes.

*   **Scénario :** Un employé reçoit un e-mail pressant "de la direction" lui demandant d'acheter des cartes cadeaux d'urgence. De quel type d'attaque s'agit-il ?
    *   A) Ransomware
    *   B) Hameçonnage ciblé / Virement au président (Spear-phishing / BEC) *(Bonne réponse)*
    *   C) Attaque par déni de service (DDoS)
    *   D) Logiciel espion (Spyware)
*   **Sondage :** Quelle est l'action la plus sûre que l'employé doit faire à ce stade ?
    *   A) Répondre à l'e-mail pour demander des clarifications.
    *   B) Acheter les cartes et envoyer les codes pour ne pas mécontenter la direction.
    *   C) Contacter la direction par un canal alternatif (téléphone, en personne) pour vérifier l'authenticité *(Bonne réponse)*.
    *   D) Transférer l'e-mail à tous ses collègues pour les prévenir.

**Éléments de débriefing (pour le mentor) :**
- Le canal de messagerie d'origine ne doit jamais être utilisé pour confirmer une demande suspecte (l'attaquant peut avoir compromis le compte).
- L'utilisation d'un canal alternatif (téléphone) est la règle d'or de la double validation.

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Pour comprendre la manipulation psychologique en cybersécurité, imaginez l'analogie d'un **imposteur habillé en agent du gaz** :
    - L'imposteur ne force pas la serrure (pas de faille technique). Il frappe à la porte, montre un faux badge, et utilise l'urgence ("fuite détectée dans la rue") pour que vous le laissiez entrer de votre plein gré.
    - Le **Phishing** est un e-mail envoyé à 1000 personnes en espérant qu'une seule laisse entrer l'imposteur.
    - Le **Spear-phishing** est un e-mail hautement personnalisé où l'imposteur connaît votre nom, le nom de votre chien, et prétend être envoyé par votre syndic de copropriété.

**Exemple d'application professionnelle :**
Dans une start-up, un comptable reçoit un SMS urgent (Smishing) prétendument de la banque, lui demandant de cliquer sur un lien pour annuler un débit frauduleux de 15 000 €. En panique (levier d'urgence), il clique et saisit ses codes d'accès. Grâce à la formation à la vigilance, il réalise son erreur 2 minutes après et appelle le service de sécurité informatique qui désactive immédiatement le compte avant que le pirate n'initie de virement.


### Panorama des solutions du marché (Commerciales & Open-Source)

Pour lutter contre l'ingénierie sociale et sécuriser la messagerie d'entreprise (principal vecteur d'attaque), voici les outils recommandés :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **KnowBe4 Security Awareness Training** : Leader incontesté pour la formation à la sensibilisation des employés et les simulations d'hameçonnage automatisées.
    *   **Proofpoint Security Awareness / SEG (Secure Email Gateway)** : Solution haut de gamme de filtrage de messagerie et de sensibilisation des collaborateurs, réputée pour bloquer le Business Email Compromise (BEC).
    *   **SoSafe** : Plateforme européenne (conforme RGPD) de sensibilisation au phishing basée sur la gamification et la psychologie comportementale.
    *   **Mimecast Email Security** : Passerelle de messagerie cloud-native offrant une protection avancée contre le phishing ciblé, les malwares et le vol d'identifiants.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **GoPhish** : Le framework open-source de simulation de phishing le plus populaire. Il permet aux administrateurs réseau de concevoir et lancer leurs propres campagnes de tests internes pour mesurer la vigilance des équipes.
    *   **Phishing-Initiative** : Projet citoyen et collaboratif (soutenu par l'ANSSI) permettant de signaler les adresses de phishing pour qu'elles soient bloquées dans les navigateurs du monde entier.

## 3. Ressources complémentaires

* **IBM SkillsBuild** : Cours sur l'ingénierie sociale et la sensibilisation au phishing.
* **Cybermalveillance.gouv.fr (ou organisme national équivalent)** : Fiches pratiques sur les rançongiciels et l'hameçonnage.
* **MITRE ATT&CK Framework** : Base de connaissances mondiale sur les tactiques et techniques réelles des attaquants (consulter la matrice simplifiée).


---

* [Cybermalveillance - Fiche Phishing](https://www.cybermalveillance.gouv.fr/tous-nos-contenus/fiches-reflexes/hameconnage-phishing)
* [CNIL - Phishing](https://www.cnil.fr/fr/spam-phishing-arnaques-signaler-pour-agir)

## 4. Exercice bonus (Sondage de Vigilance - Livestorm)

*   **Objectif :** Détection de signaux faibles d'hameçonnage.
*   **Sondage Livestorm :** Vous recevez un e-mail d'un fournisseur habituel contenant une facture. Quelle anomalie doit vous alerter en premier ?
    *   A) Le montant de la facture est élevé.
    *   B) L'adresse de l'expéditeur a un domaine légèrement modifié (ex. `support@st0rmshield.fr` au lieu de `stormshield.fr`) *(Bonne réponse)*.
    *   C) L'e-mail a été envoyé à 14h.
*   **Guide d'animation (pour le mentor) :** Montrez l'importance du typosquattage (changement de caractères subtils comme un zéro au lieu d'un 'o') comme vecteur classique pour tromper les utilisateurs.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **BEC (Business Email Compromise)** | Fraude par compromission de la messagerie professionnelle, où un pirate usurpe l'identité d'un dirigeant pour ordonner des virements frauduleux. |
| **Cyber Kill Chain** | Cadre conceptuel décrivant les 7 étapes chronologiques d'une cyberattaque réussie, développé par Lockheed Martin. |
| **Ingénierie sociale (Social Engineering)** | Manipulation psychologique visant à extorquer des informations confidentielles ou à faire accomplir des actions dangereuses à une victime. |
| **Malware (Logiciel malveillant)** | Terme générique désignant tout programme conçu pour nuire à un système informatique (virus, ver, rançongiciel, etc.). |
| **Phishing (Hameçonnage)** | Technique frauduleuse par e-mail visant à tromper le destinataire pour lui soutirer des informations confidentielles (mots de passe, numéros de carte bancaire) en usurpant l'identité d'une marque de confiance. |
| **Ransomware (Rançongiciel)** | Malware qui chiffre les fichiers d'un utilisateur ou d'une entreprise et réclame le paiement d'une rançon en échange de la clé de déchiffrement. |
| **Smishing** | Attaque d'ingénierie sociale réalisée par SMS pour pousser la victime à visiter un site malveillant ou à divulguer des données. |
| **Spear-phishing (Hameçonnage ciblé)** | Variante hautement personnalisée du phishing, ciblant un individu ou une organisation spécifique en exploitant des détails personnels collectés à l'avance. |
| **Vishing (Hameçonnage vocal)** | Technique de manipulation par téléphone où l'attaquant usurpe l'identité d'un tiers de confiance (ex. conseiller bancaire) pour extorquer des informations. |

