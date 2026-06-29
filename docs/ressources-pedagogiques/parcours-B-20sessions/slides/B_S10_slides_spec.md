# Spécifications des slides — Session B10 : Cryptographie essentielle
Parcours : B 20 sessions  |  Module : C — Sécurité des Systèmes et Applications  |  Format : Spécifications Markdown

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Cryptographie essentielle
  - Chiffrement symétrique, asymétrique, fonctions de hachage et infrastructures de confiance
  - Parcours B — Session B10
- **Notes orateur** : Bonjour et bienvenue dans cette dixième session. Aujourd'hui, nous allons étudier la cryptographie. C'est l'outil mathématique qui rend la cybersécurité possible. Nous allons démystifier le chiffrement symétrique et asymétrique, comprendre comment valider l'intégrité de nos fichiers et étudier le fonctionnement des certificats numériques.
- **Visuel suggéré** : Illustration complexe d'une clé de bronze classique fusionnée à un tableau de chiffres binaires (0 et 1) en 3D avec des faisceaux laser verts.
  - **alt-text** : Graphisme conceptuel illustrant l'art du chiffrement et de la cryptographie numérique.
- **Élément interactif** : Question sondage : "Qui sait expliquer concrètement la différence entre une clé publique et une clé privée ?"

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Comparer le chiffrement symétrique (clé unique) et le chiffrement asymétrique (couple de clés).
  - Utiliser et analyser une fonction de hachage (SHA-256) et son effet d'avalanche.
  - Décrire les infrastructures de clés publiques (PKI) et déchiffrer un certificat X.509.
  - Sommaire : Chiffrement Symétrique vs Asymétrique (25 min), Le Hachage & l'effet d'avalanche (20 min), PKI & Certificats numériques (20 min), Exercice de hachage pratique (15 min), Quiz (10 min).
- **Notes orateur** : Nous commencerons par distinguer les deux familles de chiffrement. Puis, nous verrons le hachage et l'effet d'avalanche. Nous étudierons ensuite la structure des certificats de confiance sur le web avant de réaliser une manipulation pratique et de clôturer par notre traditionnel quiz de validation.
- **Visuel suggéré** : Liste structurée présentant d'un côté les objectifs opérationnels et de l'autre le minutage de la séance synchrone de 90 minutes.
  - **alt-text** : Tableau d'agenda minuté de la session synchrone sur la cryptographie.

---

### Slide 3 — Chiffrement symétrique : La clé unique
- **Type** : contenu
- **Points clés (bullets)** :
  - Utilise **une seule et unique clé secrète** pour chiffrer et déchiffrer.
  - Très rapide, adapté aux gros volumes de données au repos (ex: algorithme AES).
  - *Le défi majeur* : Comment s'échanger la clé initiale de manière sécurisée ?
  - *Analogie* : Un coffre-fort physique s'ouvrant avec une unique clé. Il faut transmettre le double de la clé au destinataire avant de pouvoir expédier le coffre.
- **Notes orateur** : Le chiffrement symétrique utilise la même clé pour verrouiller et déverrouiller. C'est le chiffrement le plus rapide, idéal pour crypter un disque dur. Son point faible est l'échange de la clé : si vous l'envoyez par e-mail, un pirate peut l'intercepter et déchiffrer toutes vos communications. C'est l'analogie du double de clé de coffre-fort qu'il faut transmettre de main en main.
- **Visuel suggéré** : Un coffre-fort métallique classique fermé par une serrure à clé unique dorée.
  - **alt-text** : Coffre-fort à clé unique illustrant le concept de chiffrement symétrique.

---

### Slide 4 — Chiffrement asymétrique : Le couple de clés
- **Type** : schéma
- **Points clés (bullets)** :
  - Utilise un couple de clés mathématiquement liées :
    - **Clé publique** : Diffusée librement à tous. Sert uniquement à **chiffrer**.
    - **Clé privée** : Gardée jalousement par son propriétaire. Sert uniquement à **déchiffrer**.
  - Protocole plus lent, utilisé pour l'authentification et l'échange initial de clés de session (RSA, Diffie-Hellman).
  - *Analogie* : Votre destinataire vous envoie un cadenas ouvert (clé publique). Vous fermez votre boîte avec et lui renvoyez. Lui seul possède la clé physique (clé privée) pour l'ouvrir.
- **Notes orateur** : Le chiffrement asymétrique résout le problème de l'échange de clé. Chaque personne génère une clé publique que tout le monde peut voir, et une clé privée que personne d'autre ne possède. Si je veux envoyer un message chiffré à Bob, je le crypte avec sa clé publique. Seul Bob pourra le décoder, car sa clé privée est la seule à pouvoir déverrouiller ce chiffrement.
- **Visuel suggéré** : Un cadenas ouvert (clé publique) envoyé par un utilisateur à un autre, puis le cadenas fermé à clé sur une boîte métallique dont le destinataire garde la clé privée.
  - **alt-text** : Schéma conceptuel du chiffrement asymétrique à l'aide de la métaphore du cadenas public et de la clé privée.

---

### Slide 5 — Le Hachage (Hashing) : Garantir l'intégrité
- **Type** : contenu
- **Points clés (bullets)** :
  - Le hachage n'est pas du chiffrement (il est irréversible).
  - Transforme un document de taille quelconque en une empreinte de taille fixe (ex: SHA-256).
  - **Propriétés indispensables** :
    - **Irréversible** : Impossible de retrouver le document d'origine à partir du hash.
    - **Résistant aux collisions** : Deux documents différents ne donnent pas le même hash.
    - **Effet d'avalanche** : La moindre modification change totalement le hash de sortie.
- **Notes orateur** : Le hachage permet de vérifier l'intégrité d'un fichier. Ce n'est pas du chiffrement : on ne peut pas revenir en arrière. Une bonne fonction de hachage comme le SHA-256 génère une empreinte unique. Si un seul caractère ou un espace change dans le document, l'empreinte de sortie est totalement modifiée. C'est l'effet d'avalanche.
- **Visuel suggéré** : Un document texte passant à travers un hachoir virtuel et ressortant sous la forme d'une chaîne hexadécimale fixe de 64 caractères.
  - **alt-text** : Graphique illustrant la transformation d'un fichier en empreinte de hachage SHA-256.

---

### Slide 6 — Focus sur l'effet d'avalanche
- **Type** : schéma
- **Points clés (bullets)** :
  - Entrée A : *"La cybersécurité protège nos données."*
    - Hash : `5ccfec79bdf934f595df7b14ab44a2cbe5321f8a846c483a992bb3b0b8c66e4d`
  - Entrée B : *"La cybersecurite protege nos donnees."*
    - Hash : `8e77a16709f6e1ba0a3203498875567b45ddb17904ce8e7d2bb9b4226f97914a`
  - Différence d'entrée : 4 accents modifiés.
  - Résultat : Empreintes de hachage 100% différentes.
- **Notes orateur** : Regardez cet exemple. Nous avons deux phrases presque identiques. Nous avons juste retiré les accents de la deuxième phrase. Les deux empreintes SHA-256 n'ont aucun caractère similaire à la même position. C'est cet effet d'avalanche qui permet de détecter immédiatement si un pirate a modifié ne serait-ce qu'une seule lettre d'un fichier lors d'un téléchargement.
- **Visuel suggéré** : Comparatif visuel des deux phrases avec les différences de caractères surlignées en rouge, et les deux hashes affichés en dessous dans des cadres colorés distincts.
  - **alt-text** : Schéma comparatif illustrant l'effet d'avalanche avec deux phrases d'entrée similaires.

---

### Slide 7 — Utilité du hachage : L'intégrité logicielle
- **Type** : contenu
- **Points clés (bullets)** :
  - L'éditeur publie le hash SHA-256 officiel de référence sur son site web sécurisé.
  - L'utilisateur télécharge le fichier d'installation (.ISO ou .EXE).
  - L'utilisateur calcule localement le hash du fichier téléchargé.
  - Si les deux hashes correspondent $\rightarrow$ garantie absolue que le fichier n'a été ni corrompu lors du transport, ni modifié par un attaquant pour y ajouter un virus.
- **Notes orateur** : Comment être sûr qu'un système d'exploitation téléchargé n'est pas piégé ? Les éditeurs publient le hash de référence de leurs fichiers. Une fois le fichier téléchargé, vous calculez son hash sur votre machine. S'il correspond exactement au hash publié par l'éditeur, vous avez l'assurance absolue que le fichier est sain et intègre.
- **Visuel suggéré** : Illustration d'une comparaison de hashes : à gauche, le hash du site web, à droite, le hash calculé localement par l'utilisateur, avec un signe égal de validation vert.
  - **alt-text** : Graphique d'explication de la vérification d'intégrité par comparaison de hashes de fichiers.

---

### Slide 8 — Infrastructures de Clés Publiques (PKI) et X.509
- **Type** : contenu
- **Points clés (bullets)** :
  - **Le problème** : Comment être sûr que la clé publique de `google.com` appartient bien à Google et non à un pirate ?
  - **La solution** : L'Infrastructure de Clés Publiques (PKI).
  - **Certificat X.509** : Carte d'identité numérique du serveur.
    - Clé publique du site.
    - Identité du propriétaire (nom de domaine).
    - Identité de l'émetteur (Autorité de Certification).
    - Signature cryptographique de l'AC.
- **Notes orateur** : Sur Internet, pour éviter qu'un pirate n'intercepte vos données en se faisant passer pour un autre site, nous utilisons des certificats d'identité numérique X.509. C'est l'équivalent d'une carte d'identité pour un serveur web. Elle contient la clé publique du site et elle est tamponnée et signée par une Autorité de Certification de confiance.
- **Visuel suggéré** : Un certificat d'identité numérique officiel stylisé avec le symbole d'un cadenas et les champs X.509 (Propriétaire, Émetteur, Dates, Clé publique) lisibles.
  - **alt-text** : Schéma conceptuel d'un certificat d'identité numérique X.509.

---

### Slide 9 — PKI : La chaîne de confiance
- **Type** : schéma
- **Points clés (bullets)** :
  - Votre navigateur web intègre par défaut une liste d'Autorités de Certification racines de confiance.
  - Le serveur web envoie son certificat signé.
  - Le navigateur vérifie mathématiquement la signature du serveur à l'aide de la clé publique de la CA.
  - Si la signature est valide $\rightarrow$ le cadenas vert s'affiche.
  - Si elle est invalide $\rightarrow$ affichage d'un avertissement de sécurité rouge.
- **Notes orateur** : Comment votre navigateur vérifie-t-il le certificat ? Il contient en mémoire les signatures des grandes Autorités de Certification mondiales. Lorsqu'il se connecte à un site, il vérifie mathématiquement que la signature du certificat provient bien d'une de ces autorités. Si c'est le cas, la confiance est établie. Sinon, une alerte de sécurité s'affiche à l'écran.
- **Visuel suggéré** : Représentation d'une chaîne de maillons reliant l'Autorité Racine, l'Autorité Intermédiaire, le Certificat du site web et enfin le navigateur de l'utilisateur.
  - **alt-text** : Schéma de la chaîne de confiance cryptographique liant le navigateur à l'autorité racine de certification.

---

### Slide 10 — Activité pratique : Analyse d'intégrité logicielle
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **Scénario** : L'administrateur système télécharge un logiciel de sécurité.
  - **Hash de référence de l'éditeur** : `8e77a167...2bb9b4226f97914a`.
  - **Hash calculé sur le fichier reçu** : `8e77a167...2bb9b4226f97914a` (Cas 1) ou `f72a816b...d2bb9b4226f97915b` (Cas 2).
  - **Objectifs** :
    - Interpréter les deux cas.
    - Expliquer quelle action doit être menée dans le Cas 2.
    - Proposer une commande de calcul de hash sur Linux ou Windows.
- **Notes orateur** : Dans cet atelier, vous allez comparer des hashes d'installation reçus avec les hashes officiels de l'éditeur. Dans le premier cas, ils concordent. Dans le second, ils diffèrent radicalement. Que devez-vous faire du fichier dans le second cas ? Et comment auriez-vous pu calculer ce hash en console sur vos propres machines ?
- **Visuel suggéré** : Capture d'un terminal de commande exécutant un calcul de hash sur un fichier d'installation logicielle, avec des lignes de comparaison de hachage.
  - **alt-text** : Console de commande système affichant les résultats d'un calcul de somme de contrôle SHA-256.
- **Élément interactif** : Manipulation et analyse de la trame de hashes en sous-salles virtuelles.

---

### Slide 11 — Quiz de validation
- **Type** : quiz
- **Points clés (bullets)** :
  - 1. Quel algorithme de chiffrement (AES ou RSA) est le plus performant pour crypter une base de données de 1 To ?
  - 2. Quelle propriété d'une fonction de hachage fait qu'un seul caractère changé modifie totalement le hash de sortie ?
  - 3. Un certificat X.509 contient-il la clé privée du serveur web ?
- **Notes orateur** : Passons au quiz final pour valider vos compétences cryptographiques. N'oubliez pas qu'un certificat d'identité est public et ne doit donc jamais dévoiler d'informations confidentielles comme les clés privées.
- **Visuel suggéré** : QR Code d'accès au questionnaire en ligne à gauche, questions à choix multiples à droite.
  - **alt-text** : QR Code vert pour la validation des acquis en cryptographie.
- **Élément interactif** : Quiz interactif avec statistiques de réponses affichées en direct.

---

### Slide 12 — Conclusion & Travail autonome
- **Type** : récap
- **Points clés (bullets)** :
  - **Résumé** : Chiffrement symétrique (clé unique/AES), asymétrique (couple clés/RSA), hachage (intégrité/effet d'avalanche), et PKI (chaîne de confiance/X.509).
  - **Devoirs** : Compléter le module de cours *"Cryptography Basics"* sur IBM SkillsBuild (~1h30).
  - **Action pratique** : Ouvrir la console de sa machine personnelle, créer un petit fichier texte et s'entraîner à calculer et modifier son empreinte de hachage.
  - Prochaine session : *Sécurité des infrastructures Cloud (B11)*.
- **Notes orateur** : Bravo pour votre participation ! Vous connaissez maintenant les bases de la cryptographie qui sécurisent nos disques durs et notre navigation web au quotidien. Complétez le cours IBM SkillsBuild et testez le calcul de hachage en console chez vous. La semaine prochaine, nous verrons comment ces briques s'assemblent pour sécuriser les infrastructures Cloud. À bientôt !
- **Visuel suggéré** : Capture d'un terminal montrant les commandes `sha256sum` et les différences de hash après édition du fichier.
  - **alt-text** : Illustration des étapes de calcul pratique de hachage en console de commande.
