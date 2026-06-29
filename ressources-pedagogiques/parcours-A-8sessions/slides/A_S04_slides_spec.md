# Spécifications des slides — Session 04 : Sécurité du cloud, des données & des identités
Parcours : A 8 sessions  |  Module : Données & Identités  |  Format : Spécifications Markdown

---

## Slide 1 : Page de garde
* **Layout** : Titre (Emphase visuelle, fond sombre)
* **Texte affiché sur la slide** :
  * **Sécurité du Cloud, des Données & des Identités**
  * Parcours A — Session 04
  * *Verrouiller l'accès : gestion des identités, modèle de responsabilité partagée et protection du patrimoine de données*
  * Nom du Mentor / IBM SkillsBuild
* **Visuels suggérés** : Représentation d'un nuage (cloud) entouré d'anneaux de sécurité lumineux, avec une clé dorée au centre. Logo officiel dans un angle.
* **Notes du présentateur** :
  * Accueillir les apprenants.
  * Valider la complétion de l'exercice autonome de la session A3 (les e-mails compromis découverts sur Have I Been Pwned).
  * Introduire la session : comment sécuriser nos identifiants de connexion et protéger nos sauvegardes dans un monde de plus en plus basé sur le cloud.

---

## Slide 2 : Objectifs de la séance & Sommaire
* **Layout** : Deux colonnes (Gauche : Objectifs, Droite : Sommaire)
* **Texte affiché sur la slide** :
  * **Nos objectifs aujourd'hui** :
    * Maîtriser le principe du moindre privilège à travers l'IAM.
    * Expliquer l'importance cruciale de l'authentification multifacteur (MFA).
    * Comprendre le modèle de responsabilité partagée dans le cloud.
    * Appliquer la règle de sauvegarde 3-2-1 pour se prémunir des ransomwares.
  * **Sommaire de la séance** :
    * 1. Brise-glace : Le trousseau de clés (10 min)
    * 2. IAM & Moindre Privilège (15 min)
    * 3. Le bouclier MFA (20 min)
    * 4. Modèle cloud de responsabilité partagée (15 min)
    * 5. Règle de sauvegarde 3-2-1 (15 min)
    * 6. Quiz final & Synthèse (15 min)
* **Visuels suggérés** : Icônes cibles pour les objectifs et icône de liste pour le sommaire.
* **Notes du présentateur** :
  * Présenter les objectifs en insistant sur le fait que ces concepts s'appliquent autant au niveau professionnel qu'au niveau personnel (protection des comptes personnels).

---

## Slide 3 : Rappel & Brise-glace interactif
* **Layout** : Plein écran interactif
* **Texte affiché sur la slide** :
  * **Brise-glace : La clé unique de l'immeuble**
  * *Quelle est votre stratégie de clés ?*
    * Si vous étiez gérant d'un grand immeuble de bureaux, donneriez-vous un double de la clé du coffre-fort et des locaux techniques à tous les employés, y compris aux stagiaires d'une semaine ?
    * Pourquoi applique-t-on des restrictions d'accès physiques ? Pourquoi est-ce si différent dans l'informatique ?
* **Visuels suggérés** : Photo d'un énorme trousseau de clés en désordre.
* **Notes du présentateur** :
  * Laisser 3 minutes de débat.
  * Faire le lien : dans le monde physique, restreindre l'accès est naturel. En informatique, on a tendance à donner trop de droits (droits d'administrateur pour tout le monde) par facilité, ce qui est une grave faille.
  * Introduire le concept d'IAM.

---

## Slide 4 : IAM & Le principe du moindre privilège
* **Layout** : Deux colonnes
* **Texte affiché sur la slide** :
  * **IAM : Identity and Access Management**
  * *S'assurer que la bonne personne a le bon accès au bon moment.*
  * **Le principe du moindre privilège** :
    * Un utilisateur ne doit disposer **que** des droits d'accès strictement nécessaires à l'accomplissement de sa mission.
    * *Exemple* : Un comptable n'a pas besoin de droits de modification sur le code source de l'application. Un développeur n'a pas besoin d'accéder aux fiches de paie.
  * **Les avantages** :
    * Limite les erreurs humaines accidentelles.
    * Restreint les mouvements du pirate si un compte est compromis.
* **Visuels suggérés** : Schéma montrant un utilisateur avec seulement deux dossiers accessibles sur un groupe de dix dossiers. Icône de badge d'identité.
* **Notes du présentateur** :
  * Expliquer qu'un attaquant cherche à usurper un compte simple puis à réaliser une "escalade de privilèges" pour devenir administrateur. Le moindre privilège rend cette tâche beaucoup plus difficile.

---

## Slide 5 : L'arme absolue : Le MFA (Authentification Multifacteur)
* **Layout** : Trois colonnes de facteurs
* **Texte affiché sur la slide** :
  * **MFA : Bloquer 99% des attaques d'identifiants**
  * *Associer au moins deux facteurs de natures différentes :*
    * **1. Ce que je sais** : Un mot de passe ou un code PIN (Facteur de connaissance).
    * **2. Ce que j'ai** : Un smartphone, une clé de sécurité physique Yubikey (Facteur de possession).
    * **3. Ce que je suis** : Une empreinte digitale, reconnaissance faciale (Facteur d'inhérence).
  * **Pourquoi le mot de passe seul est mort ?**
    * Un mot de passe peut être deviné, volé (phishing) ou acheté sur le Darknet.
    * Le MFA protège le compte même si le pirate connaît le mot de passe.
* **Visuels suggérés** : Graphique simple montrant 99% de réduction des piratages de comptes avec le MFA activé. Icônes de cerveau (savoir), smartphone (avoir) et empreinte (être).
* **Notes du présentateur** :
  * Insister sur le fait que le MFA doit être activé en priorité sur la messagerie professionnelle et les outils d'administration cloud.
  * Expliquer pourquoi le MFA par application (Google/Microsoft Authenticator) est plus sécurisé que par SMS (vulnérable au SIM swapping).

---

## Slide 6 : Qui fait quoi dans le cloud ? Responsabilité partagée
* **Layout** : Schéma à couches empilées
* **Texte affiché sur la slide** :
  * **Modèle de responsabilité partagée dans le cloud**
  * *Le fournisseur de cloud (ex. AWS, Azure, Google Cloud) ne sécurise pas tout !*
  * **Responsabilité du Client (VOUS)** :
    * Les données stockées.
    * La configuration des comptes et accès (IAM, MFA).
    * La sécurité des applications déployées.
  * **Responsabilité du Fournisseur (EUX)** :
    * La sécurité physique des centres de données.
    * Le réseau physique, l'électricité, la climatisation.
    * L'infrastructure virtuelle globale.
* **Visuels suggérés** : Diagramme en barres horizontales superposées montrant la frontière de responsabilité entre le client (haut) et le fournisseur de cloud (bas) selon les types de services (IaaS, PaaS, SaaS).
* **Notes du présentateur** :
  * Utiliser la métaphore du locataire d'un appartement : le propriétaire (fournisseur de cloud) assure la solidité des murs et de la porte d'entrée, mais si le locataire (le client) laisse la clé sous le paillasson ou la fenêtre ouverte, c'est sa responsabilité s'il est cambriolé.

---

## Slide 7 : Règle de sauvegarde 3-2-1
* **Layout** : Infographie étape par étape
* **Texte affiché sur la slide** :
  * **La Règle de sauvegarde 3-2-1 : Contrer les rançongiciels**
  * *Pour ne jamais perdre vos données précieuses :*
    * **3** : Conserver au moins **3 copies** de vos données (la copie de travail + deux sauvegardes).
    * **2** : Stocker ces copies sur **2 supports différents** (ex. Disque dur externe ET serveur local).
    * **1** : Placer **1 copie hors site** (ex. dans le Cloud ou dans un bâtiment distant).
  * **Règle d'or (Le "0")** : Tester régulièrement la restauration des sauvegardes pour vérifier qu'elles fonctionnent réellement.
* **Visuels suggérés** : Graphisme interactif représentant le chiffre 3 (trois disques empilés), le 2 (un ordinateur et un disque externe) et le 1 (un nuage cloud distant).
* **Notes du présentateur** :
  * Expliquer le cas d'un ransomware : il chiffre l'ordinateur principal ET les clés USB restées branchées dessus. C'est pourquoi la copie hors site (ou déconnectée/immuable) est indispensable pour restaurer le système sans payer la rançon.

---

## Slide 8 : Activité 1 — Audit de politique de sauvegarde
* **Layout** : Consignes de travail (Activité pratique)
* **Texte affiché sur la slide** :
  * **Activité 1 : Auditer une politique de sauvegarde**
  * *Une entreprise stocke sa base de données sur son serveur principal et effectue une sauvegarde toutes les nuits sur un disque dur externe branché en permanence au serveur.*
  * **Questions à analyser en groupe :**
    * 1. Cette politique respecte-t-elle la règle 3-2-1 ? Pourquoi ?
    * 2. Que se passe-t-il si un rançongiciel infecte le serveur ?
    * 3. Que se passe-t-il si le bâtiment subit un incendie ?
  * **Consignes** : 15 min de travail collectif en sous-salle virtuelle. Proposez une solution améliorée.
* **Visuels suggérés** : Icône d'alerte ou de feu. Minuteur visuel de 15 minutes.
* **Notes du présentateur** :
  * Répartir les apprenants. Passer dans les groupes.
  * Lors du débriefing, faire émerger les faiblesses du disque branché en permanence (il sera chiffré par le ransomware en même temps que le reste) et du stockage uniquement sur un seul site physique (vulnérable au feu/vol).

---

## Slide 9 : Quiz de session
* **Layout** : Contenu interactif (Quiz)
* **Texte affiché sur la slide** :
  * **Quiz final : Validez vos connaissances !**
  * 1. *Quel principe consiste à donner aux utilisateurs uniquement les accès nécessaires à leur travail ?* ➔ **[Moindre privilège / Accès illimité / Règle 3-2-1 ?]**
  * 2. *Quels sont les facteurs utilisés pour l'authentification MFA ?* ➔ **[Savoir, Avoir, Être / Écrire, Parler, Penser ?]**
  * 3. *Dans la règle 3-2-1, que signifie le "1" ?* ➔ **[1 seule copie / 1 copie stockée hors site / 1 fois par an ?]**
* **Visuels suggérés** : QR code Wooclap/Kahoot.
* **Notes du présentateur** :
  * Lancer le quiz. Analyser les statistiques de réponse des élèves pour s'assurer que les notions clés sont assimilées avant la clôture.
  * *Réponses* : 1. Moindre privilège ; 2. Savoir, Avoir, Être ; 3. 1 copie stockée hors site.

---

## Slide 10 : Clôture & Devoirs
* **Layout** : Fin de session / Devoirs
* **Texte affiché sur la slide** :
  * **Vos devoirs avant la prochaine séance (Self-paced)** :
    * Suivre le module IBM SkillsBuild : *Introduction à la GRC et à la conformité réglementaire*.
    * Durée estimée : ~60 min.
    * Télécharger et explorer l'application d'authentification recommandée sur votre smartphone personnel.
  * **Prochaine séance** : *Gouvernance, risque, conformité & vie privée (A5)*.
  * Félicitations pour cette première moitié de parcours validée !
* **Visuels suggérés** : Icône de jalon (50% achevé). Logo IBM SkillsBuild.
* **Notes du présentateur** :
  * Féliciter le groupe pour l'assiduité.
  * Rappeler l'importance de faire les devoirs en autonomie pour aborder sereinement la partie GRC lors de la prochaine session.
  * Clôturer.
