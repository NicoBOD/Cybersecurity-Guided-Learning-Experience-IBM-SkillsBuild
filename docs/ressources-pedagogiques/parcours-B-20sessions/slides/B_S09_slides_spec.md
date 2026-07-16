# Spécifications des slides — Session B09 : Gestion des identités et des accès (IAM)
Parcours : B 20 sessions  |  Module : C — Identités, cloud & données  |  Format : Spécifications Markdown

> **Principe** : le texte affiché reste minimal (mots-clés, chiffres, schémas) ; le contenu riche est dans les notes orateur et le [plan de séance minuté](../plans-de-seance/B_S09_plan.md). Toutes les interactions passent par les sondages et le chat Livestorm.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Gestion des identités et des accès (IAM)
  - Qui a les clés ? Identifier, prouver, autoriser, tracer
  - Parcours B — Session B09 · Ouverture du module Identités, cloud & données
- **Notes orateur** : Accueillir : ouverture du module C — les murailles sont construites (module B), reste à gérer qui a les clés. Retour self-paced : « tapez dans le chat un service que vous utilisez avec "Se connecter avec Google/Microsoft" » — « vous utilisez déjà du SSO tous les jours ; ce soir, vous comprendrez la machinerie derrière le bouton. » Rappel B08 : Colonial Pipeline et son compte dormant — il va revenir.
- **Visuel suggéré** : Empreinte digitale numérique entourée de cercles concentriques de clés et de jetons d'accès.
  - **alt-text** : Illustration d'une empreinte digitale numérique entourée de clés symbolisant le contrôle des identités.
- **Élément interactif** : 💬 Chat d'accueil — le SSO dans votre quotidien.

---

### Slide 2 — Objectifs & agenda
- **Type** : contenu
- **Points clés (bullets)** :
  - Distinguer les 4 piliers : Identification, Authentification, Autorisation, Audit.
  - Comparer RBAC (rôles) et ABAC (attributs dynamiques).
  - Concevoir une politique MFA + SSO, avec le cycle de vie des identités (JML).
  - Agenda : 4 piliers → RBAC/ABAC → SSO & JML → matrice MedDistri → Uber & 23andMe → quiz.
- **Notes orateur** : Le fil rouge de la soirée tient en une phrase du rapport Verizon : les attaquants ne piratent pas, ils se connectent. Nous allons apprendre à rendre cette connexion difficile (MFA), limitée (RBAC) et traçable (audit) — puis deux affaires récentes montreront le prix de chaque négligence.
- **Visuel suggéré** : Deux colonnes présentant les objectifs et l'agenda de la séance.
  - **alt-text** : Tableau présentant les objectifs d'apprentissage et les étapes de la session.

---

### Slide 3 — Brise-glace : comment entrent-ils vraiment ?
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **Sondage n°1** : le premier vecteur d'accès initial des attaquants (Verizon DBIR) ?
  - A) Identifiants volés ou réutilisés — B) Failles zero-day — C) Intrusion physique
- **Notes orateur** : Lancer le sondage n°1 (60-90 s). Réponse A : de l'ordre d'une violation sur cinq, en tête année après année (DBIR 2025). Les attaquants achètent, hameçonnent ou rejouent de vrais identifiants — ils SE CONNECTENT. Le périmètre n'est plus la muraille : c'est l'identité.
- **Visuel suggéré** : Porte d'entrée moderne ouverte avec une vraie clé, pendant que des outils de cambriolage restent inutilisés au sol.
  - **alt-text** : Attaquant ouvrant une porte avec une clé légitime plutôt qu'en la forçant, symbolisant les identifiants volés.
- **Élément interactif** : 📊 Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — Les 4 piliers de l'IAM
- **Type** : schéma
- **Points clés (bullets)** :
  - **Identification** : « Je suis Alice Martin » (l'identifiant).
  - **Authentification** : le prouver (facteurs de preuve).
  - **Autorisation** : le badge limité au 1er étage.
  - **Audit** : chaque passage enregistré.
- **Notes orateur** : Dérouler l'analogie de l'immeuble sécurisé : l'accueil, le passeport, le badge programmé, le registre. Vocabulaire pro : AuthN (prouver qui l'on est) vs AuthZ (décider ce que l'on peut faire) — deux questions différentes, souvent confondues. Relance chat : « le badge limité au 1er étage, c'est quel pilier ? » (l'Autorisation).
- **Visuel suggéré** : Parcours en quatre étapes dans un hall d'immeuble : accueil, contrôle du passeport, badge remis, registre de passage.
  - **alt-text** : Parcours d'un visiteur dans un immeuble sécurisé illustrant les quatre piliers de l'IAM.
- **Élément interactif** : 💬 Chat — quiz éclair sur l'analogie.

---

### Slide 5 — MFA : la règle des catégories
- **Type** : contenu
- **Points clés (bullets)** :
  - Ce que l'on **sait** · ce que l'on **possède** · ce que l'on **est**.
  - MFA = **deux catégories différentes** minimum (2 mots de passe ≠ MFA).
  - Tous les MFA ne se valent pas : SMS < application TOTP < push + number matching < **FIDO2/passkey**.
- **Notes orateur** : La règle des catégories est la question n°6 du quiz. Hiérarchiser : le SMS est fragile (SIM swapping — l'attaquant fait transférer votre ligne sur sa carte SIM) ; l'application TOTP est un bon standard ; le push est confortable mais vulnérable à la fatigue MFA (l'histoire d'Uber arrive) ; la clé FIDO2/passkey résiste à l'hameçonnage par conception. Rappel B04 : la MFA bloque >99,9 % des attaques automatisées — encore faut-il bien la choisir.
- **Visuel suggéré** : Podium à quatre marches classant les méthodes MFA du SMS à la clé FIDO2.
  - **alt-text** : Podium hiérarchisant les méthodes d'authentification multifacteur de la plus faible à la plus robuste.

---

### Slide 6 — RBAC vs ABAC
- **Type** : schéma
- **Points clés (bullets)** :
  - **RBAC** : les droits suivent les **rôles métier** — simple, auditable.
  - **ABAC** : la décision dépend des **attributs** — sujet, ressource, contexte (heure, lieu, réseau).
  - Exemple ABAC : « le Comptable modifie les factures SEULEMENT aux heures de bureau ET depuis le réseau de l'entreprise ».
- **Notes orateur** : RBAC répond à « qui peut quoi », ABAC ajoute « dans quelles conditions ». Question rhétorique : pourquoi ne pas tout faire en ABAC ? Complexité — chaque règle dynamique s'écrit, se teste, se maintient. En pratique : RBAC pour la structure, ABAC pour les ressources les plus sensibles. C'est la question n°7 du quiz.
- **Visuel suggéré** : Deux panneaux : un organigramme avec des rôles colorés (RBAC) et un tableau de bord de conditions contextuelles (ABAC).
  - **alt-text** : Comparaison visuelle entre l'attribution de droits par rôles et l'évaluation dynamique par attributs.

---

### Slide 7 — SSO & le cycle de vie des identités
- **Type** : schéma
- **Points clés (bullets)** :
  - **SSO** : un compte unique (IdP) → toutes les applications ; le mot de passe n'est jamais vu des applications.
  - Révocation **instantanée et centralisée** au départ — mais point de défaillance unique → **MFA obligatoire**.
  - **JML** : Joiner (provisionner) · **Mover (retirer AVANT d'ajouter !)** · Leaver (tout révoquer).
- **Notes orateur** : Les protocoles derrière le bouton : SAML 2.0 et OpenID Connect — l'application reçoit une assertion signée, jamais le mot de passe. Le « M » de JML est le maillon faible : les droits s'accumulent au fil des mutations (dérive des privilèges) — la revue périodique est le filet de sécurité. Question rhétorique : qui connaît TOUS les accès d'un salarié muté deux fois ? Sans IAM centralisé : personne.
- **Visuel suggéré** : Portail central (IdP) ouvrant sur plusieurs applications, avec une frise Joiner → Mover → Leaver en dessous.
  - **alt-text** : Portail d'authentification unique desservant plusieurs applications avec la frise du cycle de vie des identités.

---

### Slide 8 — Activité : la matrice RBAC de MedDistri
- **Type** : activité (sondages)
- **Points clés (bullets)** :
  - 4 ressources × 4 profils · droits **W / R / N**.
  - 📊 **Sondage n°2** : le Stagiaire_Marketing ? · 📊 **n°3** : le Comptable et le dossier RH ? · 📊 **n°4** : l'Admin_IT et les factures ?
  - La matrice complète se remplit à l'écran au fil des votes.
- **Notes orateur** : Lancer les trois sondages avec débrief entre chaque : n°2 — « lecture partout pour apprendre » est la première cause de sur-attribution ; n°3 — presque tous les accès excessifs ont une bonne excuse, le critère est « le rôle l'exige-t-il ? » ; n°4 — LE piège : administrer l'infrastructure ≠ accéder aux données (séparation des privilèges). Reconstituer la matrice complète (support) en verbalisant chaque justification.
- **Visuel suggéré** : Matrice 4×4 vide projetée, remplie case par case avec un code couleur W/R/N.
  - **alt-text** : Matrice de droits d'accès à compléter progressivement pendant l'activité collective.
- **Élément interactif** : 📊 Sondages Livestorm n°2 à 4 — construction collective de la matrice.

---

### Slide 9 — Le paysage en chiffres
- **Type** : chiffres clés
- **Points clés (bullets)** :
  - **~1 violation sur 5** commence par des identifiants volés (Verizon DBIR 2025).
  - **~14 000 comptes** compromis → **6,9 millions de personnes** exposées (23andMe, 2023).
  - **2022** : Uber compromis par un attaquant de 17-18 ans — sans le moindre exploit.
- **Notes orateur** : Trois lectures : le mot de passe seul est mort — il se vole, se rejoue, se revend ; la MFA est indispensable mais sa mise en œuvre compte ; et quelques milliers de mots de passe recyclés peuvent exposer des millions de personnes — votre hygiène protège aussi les autres. Transition : les deux histoires.
- **Visuel suggéré** : Trois grands chiffres en typographie XXL avec leurs sources et années en petit.
  - **alt-text** : Trois statistiques géantes sur les compromissions d'identités avec leurs sources.

---

### Slide 10 — Affaire n°1 : Uber (2022)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Identifiants d'un **prestataire** achetés au marché noir.
  - La MFA bloque... alors l'attaquant **bombarde de notifications**.
  - Un message WhatsApp du « support » : « acceptez pour faire cesser ».
  - Un script aux identifiants codés en dur → accès généralisé.
- **Notes orateur** : Dérouler la chaîne : la fatigue MFA (notifications en rafale la nuit) + l'ingénierie sociale (le faux support — B04) → l'acceptation → le VPN → le script PowerShell aux secrets codés en dur → les systèmes internes, jusqu'au Slack de l'entreprise. L'attaquant : présenté comme un adolescent lié à Lapsus$. Leçons : la faille du push est comportementale (parade : number matching — l'exercice bonus) ; les secrets codés en dur transforment un accès limité en compromission totale. Et le prestataire, encore (Target, TV5...).
- **Visuel suggéré** : Smartphone submergé de notifications push identiques, avec une bulle de message « acceptez pour faire cesser » en surimpression.
  - **alt-text** : Téléphone recevant une rafale de notifications d'authentification illustrant l'attaque par fatigue MFA.

---

### Slide 11 — Affaire n°2 : 23andMe (2023)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **Credential stuffing** : d'anciennes fuites rejouées en masse.
  - ~14 000 comptes cèdent — ceux aux **mots de passe recyclés**.
  - La mise en relation généalogique expose **6,9 millions de personnes**.
  - La MFA rendue obligatoire... après coup.
- **Notes orateur** : Aucune prouesse technique : les attaquants ont essayé des couples e-mail/mot de passe déjà fuités ailleurs. L'amplification : chaque compte compromis exposait ses « apparentés » via la fonction DNA Relatives. Leçons : la fuite d'hier chez X est l'intrusion de demain chez Y (mot de passe unique + gestionnaire) ; dans un système interconnecté, votre négligence expose les autres. Relance chat : « quel détail vous marque le plus ? »
- **Visuel suggéré** : Arbre généalogique stylisé dont un seul nœud compromis illumine en rouge toutes ses branches.
  - **alt-text** : Arbre généalogique dont la compromission d'un seul profil expose en cascade tous les profils liés.
- **Élément interactif** : 💬 Chat — réactions aux deux affaires.

---

### Slide 12 — Et vous ? Les mots de passe
- **Type** : sondage (opinion)
- **Points clés (bullets)** :
  - 📊 **Sondage n°5** : votre pratique actuelle, en toute honnêteté ?
  - A) Gestionnaire + uniques — B) Quelques « socles » déclinés — C) Le même presque partout.
- **Notes orateur** : Anonyme et sans jugement — B et C sont majoritaires partout. Le message est mécanique, pas moral : un mot de passe recyclé déjà fuité suffit (23andMe). La sortie par le haut : un gestionnaire, des mots de passe uniques, la MFA partout — en commençant par la messagerie, clé de récupération de tout le reste. Enchaîner sur le mini-scénario de la mutation interne : « tapez A, B ou C » (réponse B — retirer les anciens droits en accordant les nouveaux ; c'est le « M » de JML, le maillon faible).
- **Visuel suggéré** : Trois trousseaux : un coffre numérique ordonné, un trousseau de clés similaires, une clé unique usée.
  - **alt-text** : Trois trousseaux de clés illustrant les niveaux d'hygiène de gestion des mots de passe.
- **Élément interactif** : 📊 Sondage Livestorm n°5 (opinion) puis 🤔 mini-scénario en chat (A/B/C).

---

### Slide 13 — Quiz de validation
- **Type** : quiz (sondages)
- **Points clés (bullets)** :
  - 📊 **Sondage n°6** : mot de passe + question secrète = MFA ?
  - 📊 **Sondage n°7** : quelle règle relève de l'ABAC ?
  - 📊 **Sondage n°8** : l'avantage du SSO au départ d'un salarié ?
- **Notes orateur** : Lancer les trois sondages à la suite (~2 min chacun), débriefs scriptés dans le support : le critère du MFA est la CATÉGORIE, pas le nombre ; dès que la décision dépend du contexte, c'est de l'ABAC ; le SSO au départ = révocation instantanée centralisée — le « L » de JML, exactement ce qui a manqué à Colonial Pipeline. Si le temps le permet, enchaîner sur le bonus n°9 (la fatigue MFA et le number matching).
- **Visuel suggéré** : Trois cartes de quiz numérotées 6, 7, 8 avec l'icône de sondage Livestorm.
  - **alt-text** : Trois cartes de questions de quiz numérotées, associées à des sondages en direct.
- **Élément interactif** : 📊 Sondages Livestorm n°6 à 8 (+ n°9 en tampon).

---

### Slide 14 — Synthèse & prochaine session
- **Type** : récap
- **Points clés (bullets)** :
  - Les attaquants ne piratent pas : ils **se connectent**.
  - MFA (la plus robuste possible) · besoin métier, rien que le besoin (RBAC) · retirer ce qui n'est plus exigé (JML) · tout tracer.
  - Self-paced : SkillsBuild *« Identity and Access Management Fundamentals »* + recherche « sel cryptographique ».
  - Prochaine session — B10 : Cryptographie essentielle.
- **Notes orateur** : Faire écrire dans le chat UN mot retenu, en lire 4-5. Rappeler le devoir : la recherche sur le « sel » prépare directement B10. Teaser B10 : « chiffrer, hacher, signer — et l'histoire d'école : une grande entreprise a "chiffré" 153 millions de mots de passe au lieu de les hacher... et le monde entier a pu les lire comme une grille de mots croisés. » Terminer à l'heure exacte.
- **Visuel suggéré** : Récapitulatif en quatre vignettes (MFA, matrice, JML, audit) et un panneau « B10 » fléché.
  - **alt-text** : Synthèse en quatre vignettes des thèmes IAM avec un panneau indiquant la prochaine session B10.
- **Élément interactif** : Chat de clôture — « un mot que vous retenez ».
