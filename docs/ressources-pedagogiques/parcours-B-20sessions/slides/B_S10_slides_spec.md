# Spécifications des slides — Session B10 : Cryptographie essentielle
Parcours : B 20 sessions  |  Module : C — Identités, cloud & données  |  Format : Spécifications Markdown

> **Principe** : le texte affiché reste minimal (mots-clés, chiffres, schémas) ; le contenu riche est dans les notes orateur et le [plan de séance minuté](../plans-de-seance/B_S10_plan.md). Toutes les interactions passent par les sondages et le chat Livestorm.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Cryptographie essentielle
  - Chiffrer · Hacher · Certifier — trois outils, trois usages
  - Parcours B — Session B10
- **Notes orateur** : Accueillir : ce soir on ouvre le coffre à outils mathématique de tout ce qu'on a vu (TLS, BitLocker, certificats). Retour self-paced : « en une phrase dans le chat : à quoi sert le sel cryptographique ? » Lire 2-3 définitions, valider sans tout dévoiler : « dans une heure, vous saurez pourquoi son absence a coûté 117 millions de comptes à LinkedIn. » Rappel B09 : Uber, 23andMe.
- **Visuel suggéré** : Trois objets stylisés côte à côte : un coffre (chiffrer), une empreinte digitale (hacher), un sceau de cire (certifier).
  - **alt-text** : Coffre-fort, empreinte digitale et sceau symbolisant les trois usages de la cryptographie.
- **Élément interactif** : 💬 Chat d'accueil — le sel cryptographique en une phrase.

---

### Slide 2 — Objectifs & agenda
- **Type** : contenu
- **Points clés (bullets)** :
  - Distinguer chiffrement symétrique et asymétrique (et leur combinaison).
  - Maîtriser le hachage : intégrité, effet d'avalanche, mots de passe (sel + fonctions lentes).
  - Décrire PKI, autorités de certification et certificats X.509.
  - Agenda : chiffrement → hachage → PKI → laboratoire du hachage → Adobe & LinkedIn → quiz.
- **Notes orateur** : Le fil rouge : trois outils qui ne sont PAS interchangeables — on chiffre ce qu'on devra relire, on hache ce qu'on doit seulement vérifier, on signe ce dont il faut prouver l'origine. Deux catastrophes d'école (270 millions de comptes à elles deux) montreront le prix de la confusion.
- **Visuel suggéré** : Deux colonnes présentant les objectifs et l'agenda de la séance.
  - **alt-text** : Tableau présentant les objectifs d'apprentissage et les étapes de la session.

---

### Slide 3 — Brise-glace : où va votre mot de passe ?
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **Sondage n°1** : comment un site doit-il conserver votre mot de passe ?
  - A) Chiffré avec une clé protégée — B) Haché avec un sel unique — C) En clair, base sécurisée
- **Notes orateur** : Lancer le sondage n°1 (60-90 s). Réponse B — le piège est A : le chiffrement est réversible (qui a la clé relit tout, et les clés fuitent) ; le hachage permet de VÉRIFIER sans jamais pouvoir RELIRE. Cette distinction est le fil rouge de la soirée — et une grande entreprise a choisi A pour 153 millions de comptes.
- **Visuel suggéré** : Deux coffres côte à côte : l'un avec une clé suspendue à côté (chiffrement), l'autre remplacé par une empreinte gravée (hachage).
  - **alt-text** : Comparaison entre un coffre à clé récupérable et une empreinte irréversible pour le stockage des mots de passe.
- **Élément interactif** : 📊 Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — Le code de César : algorithme + clé
- **Type** : question chat
- **Points clés (bullets)** :
  - 💬 Message chiffré : `FRPHEVGR` (décalage de 13 lettres).
  - Le premier qui tape le mot en clair dans le chat a gagné !
- **Notes orateur** : Laisser 1-2 min, féliciter le premier « SÉCURITÉ ». Débrief : un algorithme (le décalage) + une clé (13) — toute la cryptographie tient dans ce couple depuis Jules César ; seule la solidité mathématique a changé. Transition : aujourd'hui, deux grandes familles d'algorithmes.
- **Visuel suggéré** : Disque de chiffrement de César à deux anneaux de lettres décalées.
  - **alt-text** : Disque de chiffrement par décalage illustrant le code de César.
- **Élément interactif** : 💬 Chat — décryptage collectif du code de César.

---

### Slide 5 — Symétrique vs asymétrique
- **Type** : schéma
- **Points clés (bullets)** :
  - **Symétrique (AES)** : une seule clé partagée — ultra-rapide (disques, bases)... mais comment livrer la clé ?
  - **Asymétrique (RSA, DH)** : clé publique (chiffrer) + clé privée (déchiffrer) — lent, mais résout l'échange et permet la signature.
  - **Hybride** : l'asymétrique livre la clé, la symétrique fait le travail = le handshake TLS (B07).
- **Notes orateur** : Dérouler les deux analogies : le coffre-fort à clé unique (et le problème du double de clé), le cadenas ouvert distribué à tous (seul le détenteur de la clé privée ouvre). BitLocker (B08) = AES. Question rhétorique : quelle clé ne quitte JAMAIS son propriétaire ? La privée — tout l'édifice repose là-dessus.
- **Visuel suggéré** : Diptyque : coffre à clé unique / boîte aux lettres à fente publique et porte privée.
  - **alt-text** : Comparaison entre le chiffrement symétrique à clé unique et l'asymétrique à double clé.

---

### Slide 6 — Le hachage : l'empreinte digitale des données
- **Type** : contenu
- **Points clés (bullets)** :
  - Ce n'est **pas** du chiffrement : une empreinte de taille fixe, à **sens unique**.
  - 3 propriétés : irréversible · résistant aux collisions · **effet d'avalanche**.
  - Usage n°1 : l'**intégrité** (l'empreinte publiée vs l'empreinte calculée).
- **Notes orateur** : L'analogie de l'empreinte digitale : on ne recrée pas la personne à partir de l'empreinte, mais on vérifie que c'est bien elle. L'effet d'avalanche : une lettre change, tout change — le laboratoire de tout à l'heure le montrera sur de vraies empreintes SHA-256.
- **Visuel suggéré** : Document passant dans un entonnoir et ressortant en empreinte hexadécimale courte, flèche retour barrée.
  - **alt-text** : Document transformé en empreinte de hachage avec impossibilité du chemin inverse.

---

### Slide 7 — Hacher les mots de passe : sel + lenteur
- **Type** : schéma
- **Points clés (bullets)** :
  - Jamais en clair, jamais chiffré : **haché**.
  - **+ Sel** (unique par utilisateur) : empreintes toutes différentes, rainbow tables inopérantes.
  - **+ Fonction lente** (bcrypt, **Argon2**) : la force brute devient non rentable.
  - MD5 et SHA-1 : **cassés** — à bannir.
- **Notes orateur** : La chaîne du raisonnement : sans sel, tous les « linkedin123 » ont la même empreinte → tables précalculées. Même salé, SHA-256 est trop rapide : des milliards de tests/seconde sur une carte graphique → fonctions volontairement lentes. Question rhétorique : pourquoi votre banque ne peut-elle pas vous RENVOYER votre mot de passe oublié ? Elle ne l'a jamais eu — elle n'en garde que l'empreinte. Si un site le peut... méfiance (mini-scénario à venir).
- **Visuel suggéré** : Chaîne de fabrication : mot de passe + grain de sel → moulin lent (Argon2) → empreinte unique.
  - **alt-text** : Chaîne illustrant l'ajout d'un sel unique et le passage par une fonction lente avant stockage de l'empreinte.

---

### Slide 8 — PKI, X.509 & la signature numérique
- **Type** : schéma
- **Points clés (bullets)** :
  - Le problème : cette clé publique est-elle vraiment celle de `banque.com` ?
  - **L'AC** vérifie l'identité puis **signe** le certificat **X.509** (clé publique + domaine + validité + signature — jamais la clé privée).
  - **Signer** = hacher le document + chiffrer l'empreinte avec la clé **privée**.
- **Notes orateur** : La signature, mécanique dévoilée : quiconque a la clé publique vérifie (déchiffre la signature, recalcule le hachage, compare) — hachage + asymétrique = authenticité + intégrité. Boucler avec B07 : c'est ce que le navigateur vérifie à chaque cadenas, et DigiNotar a montré ce qui arrive quand le signataire ment. C'est la question n°8 du quiz.
- **Visuel suggéré** : Chaîne de confiance : AC (sceau) → certificat X.509 (carte d'identité) → navigateur (cadenas vérifié).
  - **alt-text** : Chaîne de confiance reliant l'autorité de certification au cadenas affiché par le navigateur.

---

### Slide 9 — Activité : le laboratoire du hachage
- **Type** : activité (sondages)
- **Points clés (bullets)** :
  - Deux phrases — seuls les accents diffèrent — et leurs empreintes SHA-256 affichées.
  - 📊 **Sondage n°2** : caractères communs ? · 📊 **n°3** : pourquoi publier le SHA-256 d'un .ISO ? · 📊 **n°4** : peut-on inverser une empreinte ?
- **Notes orateur** : 30 s d'observation, puis les trois sondages avec débrief : n°2 — l'effet d'avalanche, aucune corrélation visible ; n°3 — le scénario complet de la vérification d'intégrité (`sha256sum`) ; n°4 — LA nuance : inverser est impossible, TESTER est possible (hacher des millions de candidats et comparer) — le pont exact vers le sel, les fonctions lentes... et LinkedIn.
- **Visuel suggéré** : Les deux phrases et leurs empreintes en police à chasse fixe, différences de caractères surlignées.
  - **alt-text** : Comparaison de deux phrases quasi identiques et de leurs empreintes SHA-256 radicalement différentes.
- **Élément interactif** : 📊 Sondages Livestorm n°2 à 4 — analyse collective.

---

### Slide 10 — Le paysage en chiffres
- **Type** : chiffres clés
- **Points clés (bullets)** :
  - **~153 M de comptes** : le fichier Adobe (2013) — chiffrés, pas hachés, indices en clair.
  - **117 M d'identifiants LinkedIn** en vente (2016, fuite 2012) — SHA-1 **sans sel**.
  - **Des milliards d'empreintes/seconde** : une seule carte graphique moderne face aux hachages rapides.
- **Notes orateur** : Trois lectures : le mauvais outil au mauvais endroit transforme une fuite en catastrophe ; un détail d'implémentation (le sel) change tout ; la force brute est industrielle — seule la lenteur volontaire la rend non rentable. Transition : les deux histoires.
- **Visuel suggéré** : Trois grands chiffres en typographie XXL avec leurs sources et années en petit.
  - **alt-text** : Trois statistiques géantes sur les fuites de mots de passe avec leurs sources.

---

### Slide 11 — Affaire n°1 : Adobe (2013)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - ~153 millions de comptes diffusés.
  - Mots de passe **chiffrés** (même clé) au lieu d'être hachés.
  - Les **indices** stockés en clair à côté.
  - « La plus grande grille de mots croisés du monde. »
- **Notes orateur** : Raconter : le mode de chiffrement produisant le même bloc pour la même entrée — les mots de passe identiques se voient sans rien casser ; les indices (« prénom de ma fille », « pareil que gmail ») révèlent le mot de passe chiffré... de millions d'autres comptes partageant le même bloc. Leçon : chiffrer n'est PAS hacher — le sondage n°1 de ce soir, exactement.
- **Visuel suggéré** : Grille de mots croisés géante dont les définitions sont des indices de mots de passe.
  - **alt-text** : Grille de mots croisés symbolisant la fuite Adobe où les indices en clair révélaient les mots de passe.

---

### Slide 12 — Affaire n°2 : LinkedIn (2012)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - 2012 : 6,5 M d'empreintes fuitées... 2016 : **117 millions en vente**.
  - SHA-1 **sans sel** : tous les « linkedin123 » ont la même empreinte.
  - L'écrasante majorité cassée **en quelques jours**.
  - Ces identifiants alimentent le *credential stuffing* depuis dix ans.
- **Notes orateur** : Dérouler : tables précalculées + cartes graphiques = carnage ; et la boucle avec B09 : c'est ce stock de fuites qui a frappé 23andMe. Leçons : le sel rend chaque empreinte unique ; la lenteur (bcrypt/Argon2) rend la force brute non rentable ; une fuite mal protégée nourrit les attaques pendant une décennie. Relance chat : « quel détail vous marque le plus ? »
- **Visuel suggéré** : Rangée d'empreintes identiques surlignées dans une base de données, reliées à un dictionnaire de mots de passe.
  - **alt-text** : Base de données montrant des empreintes identiques dues à l'absence de sel, reliées à un dictionnaire d'attaque.
- **Élément interactif** : 💬 Chat — réactions aux deux affaires.

---

### Slide 13 — Et vous ? Les checksums + le scénario
- **Type** : sondage (opinion) + scénario
- **Points clés (bullets)** :
  - 📊 **Sondage n°5** : vérifiez-vous l'empreinte de vos téléchargements ? (A souvent / B rarement / C jamais)
  - 🤔 Puis : le site qui vous RENVOIE votre mot de passe par e-mail — A, B ou C dans le chat.
- **Notes orateur** : Sondage n°5 : C est majoritaire et c'est normal — le réflexe est attendu des pros IT ; dix secondes (`sha256sum`), seul moyen de détecter un installeur piégé. Puis le mini-scénario (support) : réponse B — s'il peut le renvoyer, il peut le relire (l'anti-modèle Adobe) ; la seule procédure légitime est la réinitialisation par lien temporaire ; chiffrer l'e-mail (C) déplace le problème. Un test à dix secondes qui révèle le sérieux d'un prestataire.
- **Visuel suggéré** : E-mail affichant un mot de passe en clair avec un tampon « ALERTE » en surimpression.
  - **alt-text** : Message électronique contenant un mot de passe en clair marqué d'une alerte de sécurité.
- **Élément interactif** : 📊 Sondage Livestorm n°5 (opinion) puis 🤔 mini-scénario en chat (A/B/C).

---

### Slide 14 — Quiz de validation
- **Type** : quiz (sondages)
- **Points clés (bullets)** :
  - 📊 **Sondage n°6** : pourquoi la cryptographie hybride (TLS) ?
  - 📊 **Sondage n°7** : à quoi sert le sel ?
  - 📊 **Sondage n°8** : que contient un certificat X.509 ?
- **Notes orateur** : Lancer les trois sondages à la suite (~2 min chacun), débriefs scriptés dans le support : l'asymétrique livre la clé, la symétrique fait le travail (le handshake de B07, compris de l'intérieur) ; le sel casse la mutualisation des attaques (LinkedIn) ; la clé privée ne quitte JAMAIS le serveur. Si le temps le permet, enchaîner sur le bonus n°9 (l'alerte « Connexion non sécurisée »).
- **Visuel suggéré** : Trois cartes de quiz numérotées 6, 7, 8 avec l'icône de sondage Livestorm.
  - **alt-text** : Trois cartes de questions de quiz numérotées, associées à des sondages en direct.
- **Élément interactif** : 📊 Sondages Livestorm n°6 à 8 (+ n°9 en tampon).

---

### Slide 15 — Synthèse & prochaine session
- **Type** : récap
- **Points clés (bullets)** :
  - **Chiffrer** ce qu'on devra relire · **hacher** (sel + lenteur) ce qu'on doit vérifier · **signer** ce qu'il faut authentifier.
  - Adobe & LinkedIn : 270 millions de comptes pour un choix d'outil erroné.
  - Self-paced : SkillsBuild *« Cryptography Basics »* + expérience `sha256sum` + recherche IaaS/PaaS/SaaS.
  - Prochaine session — B11 : Sécurité du Cloud.
- **Notes orateur** : Faire écrire dans le chat UN mot retenu, en lire 4-5. Rappeler le triple devoir (cours, expérience terminal, recherche IaaS/PaaS/SaaS — préparation directe de B11). Teaser B11 : « vos données déménagent chez quelqu'un d'autre : qui est responsable de quoi ? Et l'histoire d'une seule configuration erronée qui a exposé 106 millions de dossiers bancaires. » Terminer à l'heure exacte.
- **Visuel suggéré** : Récapitulatif en trois vignettes (coffre, empreinte salée, sceau) et un panneau « B11 » fléché.
  - **alt-text** : Synthèse en trois vignettes des usages cryptographiques avec un panneau indiquant la prochaine session B11.
- **Élément interactif** : Chat de clôture — « un mot que vous retenez ».
