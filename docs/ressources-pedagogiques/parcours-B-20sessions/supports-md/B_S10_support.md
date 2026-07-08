# Session B10 — Cryptographie essentielle

## Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer la différence de fonctionnement et d'usage entre le chiffrement symétrique (clé unique) et le chiffrement asymétrique (couple de clés).
* Utiliser et analyser une fonction de hachage (comme SHA-256) pour garantir l'intégrité d'une donnée et illustrer l'effet d'avalanche.
* Décrire les rôles d'une infrastructure de clés publiques (PKI), des autorités de certification (AC) et déchiffrer la structure d'un certificat X.509.

---

## Concepts clés

### 1. Chiffrement symétrique vs asymétrique

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

La cryptographie protège la confidentialité des données à l'aide de formules mathématiques. Il existe deux grandes familles d'algorithmes de chiffrement :

*   **Chiffrement symétrique** : Utilise une seule et unique clé secrète partagée pour chiffrer et déchiffrer les données. C'est un protocole extrêmement rapide, idéal pour chiffrer de grands volumes de données (ex. chiffrement de disques durs ou de bases de données avec l'algorithme **AES**).
    *   *La problématique* : Comment s'échanger la clé secrète initiale avec son destinataire de manière sécurisée sans qu'un espion ne la capture ?
    *   *Analogie* : Un coffre-fort qui s'ouvre et se ferme avec une seule clé physique. Vous devez faire un double de cette clé et la transmettre en main propre à votre destinataire avant de pouvoir lui expédier le coffre.
*   **Chiffrement asymétrique** : Utilise un couple de clés mathématiquement liées mais différentes :
    *   La **clé publique** : Elle est diffusée librement à tout le monde. Elle sert uniquement à **chiffrer** les messages à destination du propriétaire de la clé.
    *   La **clé privée** : Elle doit être gardée strictement confidentielle par son propriétaire. Elle sert uniquement à **déchiffrer** les messages chiffrés avec la clé publique correspondante.
    *   *Usage* : Ce protocole est beaucoup plus lent. On l'utilise principalement pour établir la connexion initiale sécurisée (échange de clé de session symétrique via des algorithmes comme **RSA** ou **Diffie-Hellman**) ou pour signer numériquement des documents.
    *   *Analogie* : Votre correspondant vous envoie un cadenas ouvert (clé publique) dont il garde jalousement la clé physique (clé privée). Vous mettez votre document dans une boîte, vous la fermez avec son cadenas ouvert et lui renvoyez la boîte. Personne d'autre que lui ne pourra ouvrir la boîte, car il est le seul à posséder la clé physique.

### 2. Le Hachage et l'intégrité des données
Un **hachage** (ou condensat) n'est pas du chiffrement. C'est l'application d'une fonction mathématique à sens unique à un message d'entrée pour produire une empreinte numérique de taille fixe (ex. 256 bits pour le **SHA-256**), peu importe la taille du document d'entrée.

#### Les 3 propriétés fondamentales d'un bon hachage :
*   **Irréversible** : Il est mathématiquement impossible de reconstituer le document d'origine à partir de son empreinte de hachage.
*   **Résistant aux collisions** : Deux documents différents ne doivent pas donner la même empreinte de hachage.
*   **Effet d'avalanche** : La moindre modification infinitésimale de la donnée d'entrée (ex. un simple espace ou une lettre modifiée) produit une empreinte de hachage de sortie totalement différente.

*   *Usage* : On utilise le hachage pour valider l'**intégrité** d'un fichier (vérifier qu'il n'a pas été corrompu ou modifié par un virus lors du téléchargement).

### 3. PKI et Certificats X.509
Comment être sûr que la clé publique de `banque.com` appartient bien à votre banque et non à un pirate ? C'est le rôle de l'**Infrastructure de Clés Publiques** (PKI) et des **Autorités de Certification** (AC).

*   **L'Autorité de Certification (AC)** : C'est un tiers de confiance chargé de vérifier l'identité réelle d'une entreprise, puis de signer numériquement son **certificat d'identité numérique (X.509)**.
*   **Le Certificat X.509** : C'est la carte d'identité numérique du serveur web. Il contient :
    1.  La clé publique du serveur.
    2.  Le nom du propriétaire (le domaine `banque.com`).
    3.  Les dates de validité du certificat.
    4.  L'identité de l'AC qui l'a émis (ex. Let's Encrypt).
    5.  La signature cryptographique de l'AC (prouvant que le certificat n'a pas été falsifié).

---

## Activités / exercices

### Exercice 1 — Vérification d'intégrité et effet d'avalanche
**Objectif :** Analyser le rôle d'une fonction de hachage (SHA-256) pour détecter une modification de texte et comprendre le concept d'effet d'avalanche.

**Consignes :**
Considérez les deux phrases suivantes, quasiment identiques à l'exception des accents :

*   **Phrase A** : `La cybersécurité protège nos données.`
*   **Phrase B** : `La cybersecurite protege nos donnees.`

1.  Voici les empreintes de hachage SHA-256 générées pour chacune de ces deux phrases :
    *   **SHA-256 de la Phrase A** : `5ccfec79bdf934f595df7b14ab44a2cbe5321f8a846c483a992bb3b0b8c66e4d`
    *   **SHA-256 de la Phrase B** : `8e77a16709f6e1ba0a3203498875567b45ddb17904ce8e7d2bb9b4226f97914a`
    Comparez les deux empreintes. Combien de caractères ont-ils en commun ? Expliquez ce phénomène.

2.  Pourquoi les éditeurs de logiciels (ex. distribution Linux Ubuntu) publient-ils l'empreinte SHA-256 de leurs fichiers d'installation (.ISO) sur leur site officiel à côté du lien de téléchargement ? Expliquez comment un utilisateur utilise cette information.

**Corrigé / Éléments de réponse :**

1.  **Comparaison des hachages (Effet d'avalanche)** :
    *   Bien que les deux phrases d'entrée ne diffèrent que de 4 accents, les deux empreintes de hachage SHA-256 générées n'ont aucun caractère similaire à la même position. C'est l'**effet d'avalanche**.
    *   Cette propriété garantit qu'il est impossible de deviner quelle était la modification apportée à l'entrée en comparant les deux hachages.
2.  **Utilité pratique de l'empreinte logicielle** :
    *   L'éditeur publie le hash de référence calculé directement sur ses serveurs sécurisés.
    *   Après avoir téléchargé l'installateur sur sa machine (via un serveur miroir parfois non sécurisé), l'utilisateur calcule localement le hash du fichier téléchargé à l'aide d'une commande (ex. `sha256sum ubuntu.iso` sous Linux).
    *   Si le hash obtenu localement correspond exactement au hash publié par l'éditeur, l'utilisateur a la certitude absolue que le fichier n'a été ni corrompu lors du transfert, ni modifié par un hacker pour y injecter un virus ou un cheval de Troie.

---

## Questions de réflexion
1. Pourquoi utilise-t-on le chiffrement symétrique (rapide) pour chiffrer l'ensemble d'un disque dur plutôt que le chiffrement asymétrique ?
2. Si un pirate réussit à modifier le contenu d'un fichier téléchargé ainsi que la page web qui affiche le hachage SHA-256 de ce fichier, comment l'utilisateur peut-il s'apercevoir de l'attaque ? Quel mécanisme cryptographique (lié aux certificats de sites) protège la page web affichant le hash ?

---

!!! abstract "Résumé"
    / points à retenir
    *   Le **chiffrement symétrique** utilise une seule clé partagée (ultra-rapide, idéal pour les gros volumes de données au repos).
    *   Le **chiffrement asymétrique** utilise un couple clé publique/privée (plus lent, idéal pour l'authentification et l'échange sécurisé de clés sur Internet).
    *   La fonction de **hachage** (ex. SHA-256) crée une empreinte unique et irréversible permettant de vérifier l'**intégrité** d'un fichier grâce à l'**effet d'avalanche**.
    *   Les **certificats X.509** et les **Autorités de Certification (AC)** constituent la base de confiance asymétrique nécessaire au chiffrement web (HTTPS).

---

## Glossaire de la session
*   **Chiffrement symétrique** — Algorithme cryptographique utilisant la même clé secrète pour chiffrer et déchiffrer les données.
*   **Chiffrement asymétrique** — Algorithme utilisant un couple de clés (publique pour chiffrer, privée pour déchiffrer).
*   **Hachage (Hashing)** — Transformation mathématique irréversible d'une donnée d'entrée en une empreinte de taille fixe garantissant l'intégrité.
*   **Effet d'avalanche** — Propriété d'une fonction de hachage où une infime modification de l'entrée change radicalement l'empreinte finale.

---

## Pour aller plus loin (self-paced)
*   **Sur IBM SkillsBuild** : Suivre le cours *"Cryptography Basics"* (durée estimée : 1h30).
*   **Activité pratique** : Ouvrez un terminal sur votre ordinateur de test et tapez la commande de hachage sur un court texte pour observer le résultat (ex. sous Linux/macOS : `echo -n "Bonjour" | sha256sum`). Modifiez une lettre et observez la différence.


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
