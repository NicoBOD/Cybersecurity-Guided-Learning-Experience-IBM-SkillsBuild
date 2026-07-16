# Session B10 — Cryptographie essentielle
Parcours : B 20 sessions  |  Module : C — Identités, cloud & données  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Chiffrement symétrique vs asymétrique
    - Le Hachage, l'intégrité des données... et le stockage des mots de passe (le sel)
    - PKI et Certificats X.509
    - Deux affaires réelles : Adobe (2013), les mots de passe « chiffrés » lisibles comme des mots croisés, et LinkedIn (2012), les empreintes sans sel
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Le **chiffrement symétrique** utilise une seule clé partagée (ultra-rapide, idéal pour les gros volumes de données au repos).
*   Le **chiffrement asymétrique** utilise un couple clé publique/privée (plus lent, idéal pour l'authentification et l'échange sécurisé de clés sur Internet).
*   La fonction de **hachage** (ex. SHA-256) crée une empreinte unique et irréversible permettant de vérifier l'**intégrité** d'un fichier grâce à l'**effet d'avalanche** — et, avec un **sel**, de stocker les mots de passe correctement.
*   Les **certificats X.509** et les **Autorités de Certification (AC)** constituent la base de confiance asymétrique nécessaire au chiffrement web (HTTPS, vu en B07).

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer la différence de fonctionnement et d'usage entre le chiffrement symétrique (clé unique) et le chiffrement asymétrique (couple de clés).
* Utiliser et analyser une fonction de hachage (comme SHA-256) pour garantir l'intégrité d'une donnée et illustrer l'effet d'avalanche.
* Justifier les règles de stockage sécurisé des mots de passe (hachage salé, fonctions dédiées) et décrire les rôles d'une PKI, des autorités de certification et d'un certificat X.509.

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** Comment un site web doit-il conserver votre mot de passe dans sa base de données ?

    - A) Chiffré avec une clé secrète bien protégée
    - B) Haché avec un sel unique, via une fonction dédiée ✅
    - C) En clair, dans une base elle-même sécurisée

    **Débrief mentor :** Réponse B — et le piège est A : le chiffrement est **réversible** (qui détient la clé peut tout relire, et la clé finit par fuiter), tandis que le hachage est à sens unique — le site peut VÉRIFIER votre mot de passe sans jamais pouvoir le RELIRE. Votre recherche de la semaine sur le « sel » prend tout son sens ce soir : une grande entreprise a choisi la réponse A pour 153 millions de comptes... l'histoire arrive en seconde partie. Ce soir : les trois outils de la cryptographie — chiffrer, hacher, certifier — et surtout QUAND utiliser chacun.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. La cryptographie hybride, déjà rencontrée**
Reliez explicitement à B07 : le handshake TLS EST la cryptographie hybride en action — l'asymétrique (RSA, Diffie-Hellman) résout le problème de l'échange de clés, la symétrique (AES) fait le travail à grande vitesse. Cette session donne les fondations de ce qui a été admis en B07. Pour les curieux : Diffie-Hellman permet même de construire un secret commun sans jamais le transmettre — chacun combine sa part privée avec la part publique de l'autre.

**2. Mots de passe : pourquoi le hachage « rapide » ne suffit pas**
Le point technique central de la session : un mot de passe ne se chiffre pas, il se **hache** — mais pas n'importe comment. (1) Sans **sel**, deux utilisateurs au même mot de passe ont la même empreinte, et les tables précalculées (*rainbow tables*) cassent tout en masse. (2) Même salées, les fonctions généralistes (MD5, SHA-1, SHA-256) sont trop **rapides** : une seule carte graphique moderne teste des milliards de candidats par seconde. D'où les fonctions dédiées **volontairement lentes et coûteuses** : bcrypt, scrypt, **Argon2** (la référence actuelle). MD5 et SHA-1 sont par ailleurs cryptographiquement cassés (collisions démontrées) — à bannir de tout nouvel usage.

**3. La signature numérique : le hachage rencontre l'asymétrique**
Expliquez la mécanique si la question vient : signer un document = hacher le document, puis chiffrer l'empreinte avec sa clé **privée**. Quiconque possède la clé publique peut vérifier : il déchiffre la signature, recalcule le hachage, compare. C'est exactement ainsi qu'une Autorité de Certification signe un certificat X.509 — et ce que le navigateur vérifie à chaque cadenas (B07 : DigiNotar a montré ce qui arrive quand le signataire est compromis).

---

### Glossaire

*   **Argon2 / bcrypt** — Fonctions de hachage dédiées au stockage des mots de passe, volontairement lentes et coûteuses pour résister aux attaques par force brute massives.
*   **Chiffrement asymétrique** — Algorithme utilisant un couple de clés (publique pour chiffrer, privée pour déchiffrer).
*   **Chiffrement symétrique** — Algorithme cryptographique utilisant la même clé secrète pour chiffrer et déchiffrer les données.
*   **Effet d'avalanche** — Propriété d'une fonction de hachage où une infime modification de l'entrée change radicalement l'empreinte finale.
*   **Hachage (Hashing)** — Transformation mathématique irréversible d'une donnée d'entrée en une empreinte de taille fixe garantissant l'intégrité.
*   **PKI (Infrastructure de Clés Publiques)** — Système de délivrance et de gestion de certificats numériques X.509 permettant de certifier l'identité des serveurs et des clés.
*   **Rainbow table (Table arc-en-ciel)** — Table précalculée d'empreintes de mots de passe courants, permettant de casser en masse les hachages non salés.
*   **Sel (Salt)** — Valeur aléatoire unique ajoutée à chaque mot de passe avant hachage, rendant chaque empreinte unique et les tables précalculées inopérantes.
*   **Signature numérique** — Empreinte d'un document chiffrée avec la clé privée du signataire — vérifiable par tous avec sa clé publique (authenticité + intégrité).

---

### Concepts clés

!!! info "À retenir"
    Trois outils, trois usages — et aucun n'est interchangeable : on **chiffre** ce qu'on devra relire (confidentialité, réversible), on **hache** ce qu'on doit seulement vérifier (intégrité, mots de passe — irréversible), on **signe/certifie** ce dont il faut prouver l'origine (authenticité). La plupart des catastrophes cryptographiques viennent d'avoir pris un outil pour l'autre.

### 1. Chiffrement symétrique vs asymétrique
La cryptographie protège la confidentialité des données à l'aide de formules mathématiques. Il existe deux grandes familles d'algorithmes de chiffrement :

*   **Chiffrement symétrique** : Utilise une seule et unique clé secrète partagée pour chiffrer et déchiffrer les données. C'est un protocole extrêmement rapide, idéal pour chiffrer de grands volumes de données (ex. chiffrement de disques durs ou de bases de données avec l'algorithme **AES** — le BitLocker de B08, c'est lui).
    *   *La problématique* : Comment s'échanger la clé secrète initiale avec son destinataire de manière sécurisée sans qu'un espion ne la capture ?
    *   *Analogie* : Un coffre-fort qui s'ouvre et se ferme avec une seule clé physique. Vous devez faire un double de cette clé et la transmettre en main propre à votre destinataire avant de pouvoir lui expédier le coffre.
*   **Chiffrement asymétrique** : Utilise un couple de clés mathématiquement liées mais différentes :
    *   La **clé publique** : Elle est diffusée librement à tout le monde. Elle sert uniquement à **chiffrer** les messages à destination du propriétaire de la clé.
    *   La **clé privée** : Elle doit être gardée strictement confidentielle par son propriétaire. Elle sert uniquement à **déchiffrer** les messages chiffrés avec la clé publique correspondante.
    *   *Usage* : Ce protocole est beaucoup plus lent. On l'utilise principalement pour établir la connexion initiale sécurisée (échange de clé de session symétrique via des algorithmes comme **RSA** ou **Diffie-Hellman**) ou pour signer numériquement des documents.
    *   *Analogie* : Votre correspondant vous envoie un cadenas ouvert (clé publique) dont il garde jalousement la clé physique (clé privée). Vous mettez votre document dans une boîte, vous la fermez avec son cadenas ouvert et lui renvoyez la boîte. Personne d'autre que lui ne pourra ouvrir la boîte, car il est le seul à posséder la clé physique.

**La cryptographie hybride** : vous l'avez déjà rencontrée — le handshake TLS de B07 combine les deux : l'asymétrique livre la clé de session, la symétrique chiffre le trafic. Le meilleur des deux mondes.

### 2. Le Hachage et l'intégrité des données
Un **hachage** (ou condensat) n'est **pas** du chiffrement. C'est l'application d'une fonction mathématique à sens unique à un message d'entrée pour produire une empreinte numérique de taille fixe (ex. 256 bits pour le **SHA-256**), peu importe la taille du document d'entrée.

#### Les 3 propriétés fondamentales d'un bon hachage :
*   **Irréversible** : Il est mathématiquement impossible de reconstituer le document d'origine à partir de son empreinte de hachage.
*   **Résistant aux collisions** : Deux documents différents ne doivent pas donner la même empreinte de hachage.
*   **Effet d'avalanche** : La moindre modification infinitésimale de la donnée d'entrée (ex. un simple espace ou une lettre modifiée) produit une empreinte de hachage de sortie totalement différente.

*   *Usage n°1 — l'intégrité* : On utilise le hachage pour valider qu'un fichier n'a pas été corrompu ou modifié par un virus lors du téléchargement (l'empreinte publiée par l'éditeur doit correspondre à celle calculée localement).

#### Le hachage des mots de passe : le sel, et des fonctions volontairement lentes
*   *Usage n°2 — les mots de passe* : un site ne doit jamais pouvoir RELIRE votre mot de passe, seulement le VÉRIFIER — donc : hachage, jamais de chiffrement ni de stockage en clair.
*   **Le sel (*salt*)** : une valeur aléatoire **unique par utilisateur**, ajoutée au mot de passe avant hachage. Sans sel : deux utilisateurs au même mot de passe ont la même empreinte, et les **rainbow tables** (tables d'empreintes précalculées des mots de passe courants) cassent tout en masse. Avec sel : chaque empreinte est unique, les tables précalculées sont inopérantes.
*   **La lenteur volontaire** : même salées, les fonctions généralistes (SHA-256) sont trop rapides face aux cartes graphiques modernes (des milliards de tests par seconde). On utilise des fonctions dédiées, lentes et coûteuses par conception : **bcrypt, scrypt, Argon2**.
*   À retenir : **MD5 et SHA-1 sont cassés** (collisions démontrées) — à bannir de tout nouvel usage.

### 3. PKI et Certificats X.509
Comment être sûr que la clé publique de `banque.com` appartient bien à votre banque et non à un pirate ? C'est le rôle de l'**Infrastructure de Clés Publiques** (PKI) et des **Autorités de Certification** (AC) — les garants du cadenas rencontrés en B07 (souvenez-vous de DigiNotar).

*   **L'Autorité de Certification (AC)** : C'est un tiers de confiance chargé de vérifier l'identité réelle d'une entreprise, puis de signer numériquement son **certificat d'identité numérique (X.509)**.
*   **Le Certificat X.509** : C'est la carte d'identité numérique du serveur web. Il contient :
    1.  La clé publique du serveur.
    2.  Le nom du propriétaire (le domaine `banque.com`).
    3.  Les dates de validité du certificat.
    4.  L'identité de l'AC qui l'a émis (ex. Let's Encrypt).
    5.  La signature cryptographique de l'AC (prouvant que le certificat n'a pas été falsifié).
*   **La signature numérique**, mécanisme sous-jacent : hacher le document, puis chiffrer l'empreinte avec la clé **privée** du signataire. Quiconque détient la clé publique vérifie : déchiffrer la signature, recalculer le hachage, comparer. Hachage + asymétrique = authenticité ET intégrité.

### Activité — Le laboratoire du hachage (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Affichez les deux phrases et leurs empreintes SHA-256, laissez 30 secondes d'observation, puis lancez les sondages. Débriefez après chaque vote.

> **Phrase A** : `La cybersécurité protège nos données.`
> **SHA-256 (A)** : `5ccfec79bdf934f595df7b14ab44a2cbe5321f8a846c483a992bb3b0b8c66e4d`
>
> **Phrase B** : `La cybersecurite protege nos donnees.` *(les mêmes mots, sans accents)*
> **SHA-256 (B)** : `8e77a16709f6e1ba0a3203498875567b45ddb17904ce8e7d2bb9b4226f97914a`

*   **📊 Sondage n°2 — L'effet d'avalanche :** Les deux phrases ne diffèrent que par quelques accents. Combien de caractères leurs empreintes ont-elles en commun aux mêmes positions ?
    *   A) Presque tous : les phrases sont quasi identiques
    *   B) Environ la moitié
    *   C) Pratiquement aucun : les empreintes sont totalement différentes ✅
*   **📊 Sondage n°3 — L'usage :** Pourquoi les éditeurs (ex. Ubuntu) publient-ils l'empreinte SHA-256 de leurs fichiers d'installation à côté du lien de téléchargement ?
    *   A) Pour permettre de vérifier que le fichier téléchargé est intègre et non modifié ✅
    *   B) Pour chiffrer le fichier pendant le téléchargement
    *   C) Pour accélérer le téléchargement grâce à la compression
*   **📊 Sondage n°4 — Le sens unique :** À partir d'une empreinte SHA-256, peut-on retrouver le document d'origine ?
    *   A) Oui, en inversant le calcul mathématique
    *   B) Non — la fonction est à sens unique ; mais si l'entrée est courte et prévisible, on peut tester des candidats en masse jusqu'à retrouver la bonne ✅
    *   C) Oui, mais uniquement avec un ordinateur quantique

**Éléments de débriefing (pour le mentor) :**

- N°2 : c'est l'**effet d'avalanche** — aucune corrélation visible entre les empreintes, impossible de deviner l'ampleur ou la nature de la modification. C'est ce qui rend l'empreinte fiable : toute altération, même d'un bit, se voit.
- N°3 : le scénario complet : l'éditeur publie le hash de référence depuis son site (protégé par TLS) ; l'utilisateur télécharge le fichier (parfois via un miroir non maîtrisé), calcule localement `sha256sum fichier.iso`, compare. Identique = ni corruption, ni malware injecté en route.
- N°4 : la nuance est LE pont vers les mots de passe : inverser est impossible, mais **tester** est possible — un attaquant hache des millions de candidats (« azerty », « 123456 »...) et compare aux empreintes volées. C'est exactement pourquoi le sel et les fonctions lentes existent... et ce que LinkedIn a appris à ses dépens (l'histoire arrive).

### 4. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **Environ 153 millions de comptes** dans le fichier Adobe diffusé fin 2013 — mots de passe **chiffrés** (et non hachés) avec la même clé, indices de mot de passe stockés **en clair**.
    - **117 millions d'identifiants LinkedIn** mis en vente en 2016, issus de la fuite de 2012 — des empreintes SHA-1 **sans sel**, dont l'écrasante majorité a été cassée en quelques jours.
    - **Plusieurs milliards d'empreintes testées par seconde** : l'ordre de grandeur d'une seule carte graphique moderne face à des hachages rapides, constaté sur les bancs d'essai publics des outils de cassage (ex. Hashcat) — la raison d'être des fonctions dédiées lentes (bcrypt, Argon2).

**Comment lire ces chiffres ?** (1) Le mauvais outil au mauvais endroit (chiffrer au lieu de hacher) transforme une fuite en catastrophe. (2) Un détail d'implémentation (le sel manquant) change tout. (3) La force brute est industrielle : seule la lenteur volontaire des fonctions dédiées la rend non rentable.

### 5. Deux affaires réelles : les mots croisés d'Adobe et le sel manquant de LinkedIn

#### Cas n°1 — Adobe (2013) : 153 millions de mots de passe « chiffrés »... et lisibles comme des mots croisés

Fin 2013, un fichier gigantesque circule sur Internet : la base clients d'**Adobe**, environ **153 millions de comptes**. Le drame n'est pas seulement la fuite — c'est ce qu'elle révèle : Adobe n'avait pas **haché** les mots de passe, mais les avait **chiffrés**, tous avec la même clé et un mode de chiffrement qui produit le même résultat pour la même entrée. Conséquence : sans même casser le chiffrement, on voit quels utilisateurs partagent le même mot de passe — les blocs chiffrés identiques se comptent par millions. Pire : les **indices de mot de passe**, eux, étaient stockés **en clair** à côté (« prénom de ma fille », « 123456 », « pareil que gmail »...). La communauté sécurité l'a surnommée « la plus grande grille de mots croisés du monde » : les indices des uns révélaient le mot de passe chiffré... des millions d'autres.

**Ce que ce cas illustre :** chiffrer n'est PAS hacher — le chiffrement est réversible et la clé devient un point de défaillance unique ; le bon réflexe était connu (hachage salé, fonction lente) ; et les métadonnées « anodines » (les indices) peuvent annuler toute la protection. Le sondage n°1 de ce soir, c'était exactement ce choix — et 153 millions de personnes ont payé la mauvaise réponse.

#### Cas n°2 — LinkedIn (2012) : le sel qui manquait

En 2012, LinkedIn subit une intrusion ; 6,5 millions d'empreintes de mots de passe apparaissent d'abord sur un forum russe. En 2016, la vérité s'avère bien pire : ce sont **117 millions d'identifiants** qui sont mis en vente. Le problème technique : les mots de passe étaient hachés en **SHA-1 sans sel**. Sans sel, tous les utilisateurs de « linkedin123 » partagent la même empreinte : les attaquants comparent la base aux tables précalculées et aux dictionnaires à la vitesse des cartes graphiques — l'écrasante majorité des mots de passe tombe en quelques jours. Ces 117 millions de couples e-mail/mot de passe alimentent depuis des années le **credential stuffing** (rappel : 23andMe, la semaine dernière — la boucle est bouclée).

**Ce que ce cas illustre :** le hachage seul ne suffit pas — le **sel** rend chaque empreinte unique et les tables précalculées inutiles ; la vitesse de la fonction compte autant que sa solidité (SHA-1 rapide → force brute rentable ; bcrypt/Argon2 lents → non rentable) ; et une fuite mal protégée en 2012 nourrit encore les attaques d'aujourd'hui.

!!! tip "📊 Sondage Livestorm n°5 — Et vous ? (sondage d'opinion, pas de bonne réponse)"
    **Question :** Avez-vous déjà vérifié l'empreinte (checksum SHA-256) d'un fichier téléchargé ?

    - A) Oui, régulièrement pour les logiciels sensibles
    - B) Rarement — je sais que ça existe, sans en avoir le réflexe
    - C) Jamais / Je découvre cette pratique ce soir

    **Débrief mentor :** Sondage d'opinion — C est la réponse la plus fréquente et c'est normal : le réflexe est surtout attendu des professionnels IT (déploiement de systèmes, outils d'administration). Le message à retenir : la vérification prend dix secondes (`sha256sum fichier` — c'est le travail en autonomie de la semaine) et elle est le SEUL moyen de détecter un installeur piégé en chemin. À défaut, téléchargez toujours depuis le site officiel, en HTTPS.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Votre prestataire livre le nouveau site client de MedDistri. En phase de test, vous cliquez sur « Mot de passe oublié »... et recevez par e-mail **votre mot de passe actuel, en clair**. **Tapez A, B ou C dans le chat :**

    - A) Pratique ! Le support client gagnera du temps.
    - B) Alerte majeure : le site stocke les mots de passe en clair ou en chiffrement réversible — exiger un stockage en hachage salé (fonction dédiée) et une procédure de réinitialisation. ✅
    - C) Acceptable, à condition que l'e-mail soit envoyé de façon chiffrée.

    **Débrief mentor :** B — si le site peut vous RENVOYER votre mot de passe, c'est qu'il peut le RELIRE : stockage en clair ou chiffrement réversible, l'anti-modèle d'Adobe. Un site correctement conçu ne connaît jamais votre mot de passe (il n'en garde que l'empreinte salée) — c'est pourquoi la seule procédure légitime est la **réinitialisation** par lien temporaire. C déplace le problème sans le résoudre : le chiffrement du transport (TLS) ne change rien au stockage. Ce test à dix secondes est un excellent révélateur du sérieux d'un prestataire.

---

### Questions de réflexion
1. Pourquoi utilise-t-on le chiffrement symétrique (rapide) pour chiffrer l'ensemble d'un disque dur plutôt que le chiffrement asymétrique ?
2. Si un pirate réussit à modifier le contenu d'un fichier téléchargé ainsi que la page web qui affiche le hachage SHA-256 de ce fichier, comment l'utilisateur peut-il s'apercevoir de l'attaque ? Quel mécanisme cryptographique (lié aux certificats de sites) protège la page web affichant le hash ?
3. Dans l'affaire Adobe, les mots de passe étaient « protégés » par chiffrement. Expliquez pourquoi un hachage salé aurait radicalement limité les dégâts, même après le vol de la base.

**Corrigé / Éléments de réponse :**

1. Le chiffrement symétrique est beaucoup plus rapide et moins gourmand en ressources CPU, ce qui est indispensable pour chiffrer/déchiffrer des volumes de données en temps réel (un disque dur entier).
2. La page web avec le hash est protégée par un certificat TLS (HTTPS), garantissant son intégrité si le site est bien authentique — modifier le fichier ET la page de référence supposerait de compromettre aussi le serveur légitime ou sa chaîne de certification.
3. Avec un hachage salé (fonction lente type bcrypt/Argon2) : aucune clé à voler (rien à déchiffrer), aucune empreinte identique entre utilisateurs (le sel), et une force brute non rentable (la lenteur). Le vol de la base n'aurait livré que des empreintes inexploitables en masse — au lieu de 153 millions de mots de passe exposés d'un coup par une seule clé et des indices en clair.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez les différents concepts de la cryptographie moderne avec les analogies suivantes :
    - **Le Chiffrement Symétrique** : C'est comme un **coffre-fort à clé unique**. Vous verrouillez le coffre avec la clé physique, puis vous devez donner cette *exacte même clé* au destinataire pour qu'il puisse l'ouvrir. C'est rapide, mais l'envoi de la clé pose un défi de sécurité.
    - **Le Chiffrement Asymétrique** : C'est comme une **boîte aux lettres dotée de deux clés**. La fente de la boîte est ouverte à tous : n'importe qui peut y déposer une lettre (clé publique de chiffrement disponible pour le monde entier). En revanche, seul le propriétaire possède la clé pour ouvrir la porte et lire le courrier (clé privée de déchiffrement).
    - **Le Hachage** : C'est comme une **empreinte digitale**. Si vous modifiez un seul cheveu de la personne, l'empreinte change totalement (effet d'avalanche). On ne peut pas recréer la personne à partir de son empreinte, mais on peut vérifier si c'est bien elle (intégrité).
    - **Le Sel** : c'est comme ajouter un **grain unique** à chaque empreinte : même deux jumeaux parfaits (deux mots de passe identiques) laissent alors des empreintes différentes.

**Exemple d'application professionnelle :**
Une entreprise utilise le chiffrement asymétrique pour établir une connexion TLS sécurisée avec ses clients. Les clés publiques et privées servent uniquement à s'authentifier et à échanger une clé temporaire unique. La suite des communications chiffrées s'effectue en chiffrement symétrique pour garantir un débit rapide des données.

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour déployer des PKI d'entreprise, gérer des clés cryptographiques et stocker des secrets de manière sécurisée :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Thales Luna HSM (Hardware Security Module)** : Équipements physiques ultra-sécurisés pour la génération et le stockage physique de clés cryptographiques de niveau militaire.
    *   **DigiCert Enterprise PKI** : Solution commerciale leader pour la gestion automatisée des certificats numériques et des clés à grande échelle.
    *   **Entrust PKI** : Plateforme robuste pour gérer l'infrastructure de clés publiques d'entreprises financières et gouvernementales.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **HashiCorp Vault** : L'outil open-source leader mondial pour la gestion des secrets, le stockage des clés cryptographiques d'API, de bases de données et la génération dynamique de certificats — l'antidote aux identifiants codés en dur du cas Uber (B09).
    *   **EJBCA Community Edition** : Plateforme de PKI open-source de niveau entreprise, permettant de construire sa propre Autorité de Certification (CA) interne de manière robuste.
    *   **OpenSSL** : Boîte à outils cryptographique en ligne de commande open-source universelle, utilisée pour générer des clés, des demandes de signature de certificat (CSR) et chiffrer des fichiers.

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après le mini-scénario.

*   **📊 Sondage n°6 :** Pourquoi combine-t-on chiffrement symétrique et asymétrique (cryptographie hybride, comme dans TLS) ?
    *   A) L'asymétrique résout l'échange de clés, la symétrique chiffre ensuite à grande vitesse ✅
    *   B) Pour chiffrer deux fois et doubler la sécurité
    *   C) Parce que certains pays interdisent l'un des deux
*   **📊 Sondage n°7 :** À quoi sert le sel (*salt*) dans le stockage des mots de passe ?
    *   A) À rendre le mot de passe plus long, donc plus difficile à deviner
    *   B) À rendre chaque empreinte unique et les tables précalculées (rainbow tables) inopérantes ✅
    *   C) À chiffrer l'empreinte après le hachage
*   **📊 Sondage n°8 :** Que contient un certificat X.509 présenté par un site web ?
    *   A) La clé privée du serveur, pour permettre le déchiffrement
    *   B) La liste des utilisateurs autorisés à visiter le site
    *   C) La clé publique du serveur, l'identité du domaine et la signature de l'autorité de certification ✅

**Éléments de débriefing (pour le mentor) :**

- N°6 : c'est le handshake TLS de B07, désormais compris de l'intérieur — l'asymétrique livre la clé, la symétrique fait le travail.
- N°7 : le sel n'est pas secret ni destiné à « allonger » le mot de passe — il est unique par utilisateur et casse la mutualisation des attaques (LinkedIn : son absence a coûté 117 millions de comptes).
- N°8 : la clé PRIVÉE ne quitte JAMAIS le serveur (le piège A) — le certificat ne transporte que la clé publique, l'identité et la garantie signée de l'AC.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Cryptography Basics"* (durée estimée : 1h30).
*   **Activité pratique** : Ouvrez un terminal sur votre ordinateur de test et tapez la commande de hachage sur un court texte pour observer le résultat (ex. sous Linux/macOS : `echo -n "Bonjour" | sha256sum`). Modifiez une lettre et observez la différence.
*   [ANSSI — Mécanismes cryptographiques](https://cyber.gouv.fr/publications/mecanismes-cryptographiques)
*   [CNIL — Comprendre le chiffrement](https://www.cnil.fr)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Rôle des autorités de certification.
*   **📊 Sondage Livestorm n°9 :** Lorsque votre navigateur affiche une alerte "Connexion non sécurisée" sur un site web HTTPS, quelle en est la cause la plus courante ?
    *   A) Le site web a été piraté.
    *   B) Le certificat TLS du site est expiré ou a été signé par une autorité non reconnue par le système ✅
    *   C) Votre ordinateur manque de mémoire vive.
*   **Guide d'animation (pour le mentor) :** Expliquez le rôle de la chaîne de confiance (PKI) : un certificat doit être signé par une Autorité de Certification reconnue pour valider l'identité du site — et la signature, vous savez désormais comment elle fonctionne (hachage + clé privée de l'AC). Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Chiffrement symétrique (AES)** | Une seule clé partagée — rapide, pour les gros volumes (disques, bases). |
| **Chiffrement asymétrique (RSA, DH)** | Couple publique/privée — lent, pour l'échange de clés et les signatures. |
| **Cryptographie hybride** | L'asymétrique livre la clé, la symétrique fait le travail — le handshake TLS (B07). |
| **Hachage (SHA-256)** | Empreinte irréversible de taille fixe — l'outil de l'intégrité (effet d'avalanche). |
| **Sel + fonction lente (Argon2, bcrypt)** | Le stockage correct des mots de passe : empreintes uniques, force brute non rentable. |
| **Rainbow table** | Table d'empreintes précalculées — neutralisée par le sel. |
| **Signature numérique** | Hachage chiffré à la clé privée — authenticité + intégrité, vérifiable par tous. |
| **PKI / X.509** | La chaîne de confiance du web : l'AC signe la carte d'identité du serveur. |

**La règle d'or de la session :** trois outils, trois usages — chiffrez ce que vous devrez relire, hachez (avec sel et fonction lente) ce que vous devez seulement vérifier, signez ce dont il faut prouver l'origine. Adobe et LinkedIn rappellent qu'un seul choix d'outil erroné se paie en centaines de millions de comptes.
