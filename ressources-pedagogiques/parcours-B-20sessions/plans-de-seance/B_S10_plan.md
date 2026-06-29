# Plan de séance — Session B10
Parcours : B 20 sessions  |  Module : C — Identités, cloud & données  |  Durée : 1h30 (90 minutes)

## 1. Métadonnées de la session
* **Titre** : Cryptographie essentielle
* **Objectifs pédagogiques opérationnels** :
  * Expliquer la différence de fonctionnement et d'usage entre le chiffrement symétrique (clé unique) et le chiffrement asymétrique (couple clé publique/privée).
  * Utiliser une fonction de hachage (ex. SHA-256) pour valider l'intégrité d'un fichier et expliquer l'effet d'avalanche.
  * Décrire le rôle d'une infrastructure de clés publiques (PKI), des autorités de certification (AC) et le contenu d'un certificat X.509.
* **Prérequis** : B09.
* **Lien de progression** : Fournit le cadre théorique et mathématique permettant d'aborder la sécurisation des infrastructures cloud (B11) et le chiffrement des données au repos et en transit (B12).

---

## 2. Déroulé minuté (90 minutes)

| Minutage | Séquence | Contenu théorique & Activités | Rôle du Mentor | Rôle de l'Apprenant | Méthode pédagogique | Livrable / Jalon |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **00 - 15 min** *(15')* | **Brise-glace & Code** | *Brise-glace : Le code de César.* Décryptage collaboratif en direct d'un court message chiffré par décalage (ROT13) pour comprendre le concept d'algorithme et de clé. | Projette le message codé, explique la logique de décalage et anime le décryptage. | Analyse le message, calcule le décalage et trouve le message en clair. | Interrogative / Active | Jalon : Message en clair déchiffré collectivement. |
| **15 - 35 min** *(20')* | **Apports Théoriques : Chiffrement** | *Chiffrement symétrique vs asymétrique.* Algorithmes AES (symétrique) et RSA/Diffie-Hellman (asymétrique). Cas d'usage (chiffrement de disque vs échange de clés). | Présente les slides théoriques, illustre avec des animations ou des schémas d'envoi de clés. | Apprend à différencier la clé privée (à cacher) et la clé publique (à distribuer). | Explicative / Visuelle | - |
| **35 - 50 min** *(15')* | **Apports Théoriques : Hachage & PKI** | *Hachage (SHA-256) et certificats X.509.* Utilité du hachage, notion d'irréversibilité. Fonctionnement de la PKI (confiance tierce). | Explique le concept de hachage non-réversible et détaille la structure d'un certificat SSL de site web. | Observe comment le navigateur valide l'identité d'un site sécurisé. | Explicative | - |
| **50 - 80 min** *(30')* | **Activité Pratique** | *Activité : Vérification d'intégrité (SHA-256).* Les apprenants calculent à l'aide d'outils en ligne ou de commandes le hash de fichiers textes pour analyser l'impact du moindre changement de caractère. | Propose deux fichiers textes quasi identiques, guide le calcul du hash. | Calcule les hachages, observe l'effet d'avalanche et rédige un rapport de vérification. | Active / Expérimentale | **Livrable** : Tableau comparatif de hachages SHA-256 et validation d'intégrité de fichiers. |
| **80 - 90 min** *(10')* | **Quiz & Devoirs** | *Quiz de session & Devoirs.* Validation des principes cryptographiques de base. | Lance le quiz de session et présente le travail autonome SkillsBuild. | Effectue le quiz en ligne et note les devoirs. | Interrogative | Jalon : Score au quiz individuel. |

---

## 3. Travail en autonomie (Self-paced)
* **Avant la session suivante (B11)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Cryptography Basics"* (durée estimée : 1h30).
  * **Exercice de recherche** : Identifier la différence entre IaaS, PaaS et SaaS et donner un exemple de service connu pour chaque catégorie (ex. AWS EC2, Heroku, Google Workspace).
