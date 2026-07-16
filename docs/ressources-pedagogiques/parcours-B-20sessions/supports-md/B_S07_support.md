# Session B07 — Communications sécurisées
Parcours : B 20 sessions  |  Module : B — Systèmes & réseaux  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Sécuriser le web : Le protocole TLS
    - Les Réseaux Privés Virtuels (VPN)
    - La sécurité des communications sans-fil (Wi-Fi)
    - Deux affaires réelles : Firesheep (2010), l'extension qui a forcé le web à se chiffrer, et DigiNotar (2011), l'autorité de certification piratée
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   **HTTPS/TLS** protège les données applicatives en transit en combinant la cryptographie asymétrique (échange de clés) et symétrique (chiffrement des flux).
*   La validation du **certificat numérique** par le navigateur empêche les attaques par interception *Man-in-the-Middle* (MitM).
*   Le **VPN** sécurise les flux de transport sur des réseaux publics en créant un tunnel chiffré (IPsec pour le site-à-site, WireGuard/OpenVPN pour le nomade).
*   La sécurité Wi-Fi moderne requiert l'abandon de WEP/WPA2-PSK au profit de **WPA3** et de **WPA-Enterprise** pour l'authentification individuelle.

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer les étapes du protocole de négociation (*handshake*) TLS dans la sécurisation des échanges web (HTTPS) et le rôle des autorités de certification.
* Comparer les protocoles et architectures VPN (IPsec, OpenVPN, WireGuard) en fonction de leurs cas d'usage (accès utilisateur distant ou interconnexion de sites).
* Identifier les failles des anciens protocoles de chiffrement Wi-Fi (WEP, WPA2-PSK) et préconiser des solutions modernes (WPA3, WPA-Enterprise).

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** Aujourd'hui, quelle proportion des pages web chargées dans le monde l'est en HTTPS (connexion chiffrée) ?

    - A) Environ 30 %
    - B) Environ 60 %
    - C) Plus de 90 % ✅

    **Débrief mentor :** Réponse C : plus de 90 % selon le rapport de transparence de Google — le cadenas est devenu la norme. Mais au début des années 2010, c'était l'inverse : la plupart des sites, y compris les réseaux sociaux, transmettaient vos sessions **en clair**. Ce qui a fait basculer le web ? Pour une bonne part... une petite extension de navigateur gratuite, créée pour faire un scandale. Son histoire arrive en seconde partie de session. Ce soir : comprendre ce que le cadenas garantit vraiment — et ce qu'il ne garantit pas.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Le handshake TLS, cœur de la session**
Consacrez le temps nécessaire au *handshake* : négociation des algorithmes, authentification du serveur par certificat, échange de la clé de session. Le point subtil à faire passer : l'asymétrique (lent, mais permettant l'échange sans secret préalable) ne sert qu'à démarrer ; tout le trafic est ensuite chiffré en symétrique (rapide). Précision terminologique : **SSL est mort** — les versions SSL 2.0/3.0 sont dépréciées depuis des années ; le protocole actuel est TLS (1.2 minimum, 1.3 recommandé — voir les recommandations TLS de l'ANSSI en ressources). Si on vous dit « certificat SSL », comprenez « certificat TLS » : l'usage commercial a gardé l'ancien nom.

**2. Ce que HTTPS ne cache PAS**
Anticipez la question (elle recoupe la question de réflexion n°1) : même en HTTPS, un observateur du réseau voit les **métadonnées** — adresses IP contactées, noms de domaine (requêtes DNS, indication SNI du handshake), volumes et horaires. Le contenu est illisible, la destination ne l'est pas. C'est précisément ce que le VPN ajoute : il masque tout cela à l'observateur local en déplaçant le point de sortie.

**3. Wi-Fi public : Evil Twin et écoute passive**
Détaillez les deux menaces types du Wi-Fi public : l'**écoute passive** des trames (triviale sur un réseau ouvert non chiffré — c'était tout le propos de Firesheep) et le **jumeau maléfique** (*Evil Twin*) : un point d'accès pirate au nom crédible (« Hotel_WiFi_Gratuit ») auquel les victimes se connectent d'elles-mêmes — l'attaquant devient alors la passerelle et voit tout le trafic non chiffré. Parade en couches : ne pas faire confiance au réseau (VPN), garder le chiffrement applicatif (HTTPS), désactiver les partages locaux (profil « réseau public »).

---

### Glossaire

*   **CA (Certificate Authority)** — Organisme tiers de confiance chargé de générer, valider et révoquer les certificats numériques d'identité des serveurs.
*   **Evil Twin (Jumeau maléfique)** — Point d'accès Wi-Fi pirate imitant le nom d'un réseau légitime pour que les victimes s'y connectent d'elles-mêmes.
*   **Handshake TLS** — Phase de négociation initiale où le client et le serveur s'authentifient et définissent la clé de chiffrement de leur session.
*   **Man-in-the-Middle (MitM)** — Attaque d'interception où un pirate s'interpose secrètement entre deux parties pour lire ou modifier leurs communications.
*   **PKI (Infrastructure de Clés Publiques)** — Système de serveurs, de logiciels et de procédures délivrant et gérant des certificats numériques de confiance (certificats X.509).
*   **RADIUS Server** — Serveur centralisant l'authentification, les autorisations et la traçabilité des accès utilisateurs sur un réseau d'entreprise (802.1X).
*   **TLS (Transport Layer Security)** — Protocole de sécurisation des échanges réseau chiffrant les flux applicatifs (comme HTTPS) et garantissant l'identité du serveur ; successeur du SSL, aujourd'hui déprécié.
*   **VPN (Réseau Privé Virtuel)** — Réseau virtuel sécurisé créant un tunnel chiffré pour le transit de données sur un réseau public.

---

### Concepts clés

!!! info "À retenir"
    Vos murailles (B06) protègent votre réseau — mais vos données, elles, **voyagent** hors les murs : Wi-Fi, Internet, hôtels, clients. La règle : ne jamais faire confiance au réseau traversé. Chiffrer le contenu (TLS), chiffrer le chemin (VPN), authentifier l'interlocuteur (certificats) — et considérer tout réseau public comme hostile par défaut.

### 1. Sécuriser le web : Le protocole TLS
Lorsque vous naviguez sur un site web en HTTP classique, toutes les informations (mots de passe, numéros de carte bancaire) transitent en texte clair sur le réseau — vous l'avez vu de vos yeux dans l'exercice bonus de B05. Le protocole **HTTPS** sécurise ces échanges en encapsulant le trafic HTTP au sein d'un tunnel chiffré par le protocole **TLS** (*Transport Layer Security* — successeur du SSL, aujourd'hui déprécié).

*   *L'analogie* : Naviguer en HTTP équivaut à envoyer une carte postale sans enveloppe (tous les intermédiaires peuvent la lire). Naviguer en HTTPS équivaut à glisser le message dans un coffre-fort blindé portatif dont seul le destinataire possède le code.
*   **Le Handshake TLS (Poignée de main)** :
    1.  *Négociation* : Le navigateur et le serveur s'accordent sur la version de TLS et les algorithmes de chiffrement à utiliser.
    2.  *Authentification* : Le serveur envoie son **certificat numérique**. Le navigateur vérifie sa validité auprès d'une **Autorité de Certification** (CA — *Certificate Authority*) de confiance pour s'assurer que le site est bien celui qu'il prétend être (évitant l'interception *Man-in-the-Middle* — MitM).
    3.  *Échange de clés* : Ils utilisent la cryptographie asymétrique (clé publique/privée) pour s'échanger en toute sécurité une **clé symétrique temporaire** (clé de session).
    4.  *Chiffrement* : Le reste de la communication est chiffré de manière ultra-rapide avec cette clé symétrique de session.

**Pourquoi deux cryptographies ?** L'asymétrique permet de s'échanger un secret sans jamais s'être rencontrés — mais elle est lente. La symétrique est extrêmement rapide — mais il faut partager la clé. Le handshake combine le meilleur des deux : l'asymétrique livre la clé, la symétrique fait le travail.

### 2. Les Réseaux Privés Virtuels (VPN)
Un **VPN** (*Virtual Private Network*) crée un tunnel virtuel chiffré à travers un réseau public non sûr (comme Internet) pour relier de manière sécurisée deux entités distantes.

On distingue deux architectures majeures :

*   **Le VPN d'accès distant (Client-to-Site)** : Permet à un utilisateur nomade (télétravailleur) d'installer un logiciel client sur son poste pour se connecter de manière sécurisée au réseau de son entreprise.
*   **Le VPN site-à-site (Site-to-Site)** : Interconnecte de manière permanente les réseaux de deux sites physiques distincts d'une entreprise (ex. relier le siège social et une usine).

#### Comparatif des protocoles VPN :
*   **IPsec (*IP Security*)** : Protocole historique et très robuste opérant au niveau de la couche 3 (Réseau). C'est la norme industrielle pour les tunnels VPN permanents site-à-site.
*   **OpenVPN** : Solution open-source très flexible fonctionnant sur la couche 4 (Transport). Il est sécurisé et largement déployé pour les clients nomades, mais sa configuration peut être complexe et il est gourmand en ressources.
*   **WireGuard** : Le protocole moderne par excellence. Beaucoup plus léger en lignes de code, extrêmement rapide et performant. Il consomme moins de batterie sur les appareils mobiles et se reconnecte instantanément lors d'un changement de réseau.

> 💡 **Bon à savoir : le VPN est aussi... une porte**
> Souvenez-vous de B05 : les passerelles VPN font partie des équipements de bordure les plus ciblés (ANSSI). Un VPN protège vos flux, mais sa passerelle exposée doit être maintenue à jour et protégée par MFA — sinon le tunnel des employés devient celui des attaquants (rappel du mini-scénario CTI de B02).

### 3. La sécurité des communications sans-fil (Wi-Fi)
Les ondes radio du Wi-Fi traversent les murs, ce qui permet à n'importe qui à proximité physique d'intercepter les paquets s'ils ne sont pas chiffrés.

*   **WEP (*Wired Equivalent Privacy*)** : Protocole de première génération. **Totalement obsolète et dangereux**. Ses faiblesses mathématiques permettent de casser sa clé de sécurité en quelques secondes à l'aide d'outils grand public.
*   **WPA2-PSK (*Pre-Shared Key*)** : Le protocole le plus répandu à la maison. Il utilise une clé unique partagée pour tous les utilisateurs. Il est vulnérable aux attaques par dictionnaire (si la clé est trop simple) et à des failles de conception (attaque KRACK).
*   **WPA3** : Le standard moderne. Il corrige les failles de WPA2 en remplaçant l'échange de clés initial par le protocole **SAE** (*Simultaneous Authentication of Equals*), empêchant le piratage de la clé Wi-Fi par interception passive et attaque hors ligne.
*   **WPA-Enterprise (802.1X)** : Destiné aux entreprises. Au lieu d'avoir un mot de passe unique pour tout le monde, chaque salarié se connecte avec son propre identifiant/mot de passe ou son propre certificat de sécurité. Le contrôle d'accès est centralisé par un serveur d'authentification (généralement de type **RADIUS**).

### Activité — Mission : sécuriser les 100 consultants nomades (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Affichez le contexte : vous êtes consultant en cybersécurité pour une société de conseil de 100 consultants mobiles — gares, hôtels, sites clients — qui accèdent aux serveurs internes (rapports d'audit confidentiels) et à des applications cloud. Trois décisions à prendre, trois sondages. Débriefez après chaque vote.

*   **📊 Sondage n°2 — Le Wi-Fi du siège :** Quelle configuration préconisez-vous pour le réseau sans-fil des bureaux ?
    *   A) WPA2-PSK avec un mot de passe robuste affiché en salle de pause
    *   B) WPA3-Enterprise (802.1X) : chaque consultant a ses identifiants nominatifs ✅
    *   C) WEP, suffisant pour un usage de bureau
*   **📊 Sondage n°3 — L'accès nomade :** Quelle technologie installez-vous sur les 100 ordinateurs portables ?
    *   A) Aucune : HTTPS suffit puisque les sites sont chiffrés
    *   B) Un VPN d'accès distant moderne (type WireGuard), activé en mobilité ✅
    *   C) Un simple proxy web configuré dans le navigateur
*   **📊 Sondage n°4 — Au café :** Un consultant doit envoyer un document confidentiel depuis le Wi-Fi public d'un café. Sa PREMIÈRE action ?
    *   A) Vérifier que le site de l'entreprise affiche bien le cadenas
    *   B) Éviter seulement les sites bancaires, le reste peut passer
    *   C) Activer le VPN d'entreprise AVANT d'ouvrir la moindre application ✅

**Éléments de débriefing (pour le mentor) :**

- N°2 : le mot-clé est **nominatif** — avec une clé partagée (A), le départ d'un consultant impose de changer le mot de passe de toute l'entreprise, et personne n'est traçable individuellement. WPA3-Enterprise + RADIUS : accès individuels, révocables un par un. C est disqualifié d'office (WEP se casse en secondes).
- N°3 : le piège est A — HTTPS chiffre le contenu, pas les métadonnées (domaines visités, destinations) et ne protège pas les applications non-web. Le VPN chiffre TOUT le trafic de la machine ; WireGuard excelle en mobilité (léger, reconnexion instantanée aux changements de réseau). Le proxy (C) relaie sans chiffrer globalement — c'est l'exercice bonus.
- N°4 : l'ordre des opérations est LA réponse : le VPN d'abord, tout le reste ensuite — chaque seconde de trafic hors tunnel sur un Wi-Fi public est lisible par le voisin. Compléter avec les deux autres règles du corrigé : exiger le HTTPS partout (double chiffrement), et profil « réseau public » (partages locaux désactivés).

**Fiche de préconisations complète (corrigé de référence) :**

1.  **Wi-Fi du siège : WPA3-Enterprise (802.1X)** — sécurité cryptographique moderne + identifiants nominatifs : si un consultant part, on révoque SON accès sans toucher aux autres.
2.  **Accès nomade : WireGuard** (ou OpenVPN) — léger, économe en batterie, débits optimisés pour les connexions instables, rétablissement instantané du tunnel aux changements de réseau.
3.  **Règles d'usage sur Wi-Fi public** : (1) VPN activé **avant** toute application ; (2) HTTPS exigé partout (cadenas) — double chiffrement ; (3) partage de fichiers désactivé (profil « réseau public » sous Windows/macOS).

### 4. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **Plus de 90 %** des pages web chargées dans le monde le sont désormais en HTTPS (rapport de transparence Google) — au début des années 2010, le chiffrement était l'exception.
    - **Plus de 100 000 téléchargements en 24 heures** pour l'extension Firesheep à sa sortie en octobre 2010 (chiffres rapportés par son auteur) — le scandale qui a précipité le web vers HTTPS.
    - **Environ 300 000 internautes iraniens** espionnés via de faux certificats Google émis après le piratage de l'autorité de certification DigiNotar (rapport d'enquête Fox-IT, 2011).

**Comment lire ces chiffres ?** (1) Le chiffrement généralisé du web est une conquête récente — obtenue en partie par l'électrochoc. (2) Quand la démonstration d'une faille est à la portée de tous, l'industrie bouge en quelques mois. (3) La confiance du web repose sur les autorités de certification : quand l'une d'elles tombe, c'est le cadenas lui-même qui ment.

### 5. Deux affaires réelles : l'extension qui a fait peur au web et la CA qui a menti

#### Cas n°1 — Firesheep (2010) : le scandale qui a généralisé le HTTPS

Octobre 2010. Un développeur américain, lassé de voir l'industrie ignorer un problème connu depuis des années, publie **Firesheep** : une simple extension gratuite pour Firefox. Son fonctionnement : assis dans un café, connecté au Wi-Fi ouvert, l'utilisateur voit apparaître... la liste des comptes Facebook, Twitter et autres des personnes présentes autour de lui — **un double-clic, et il navigue dans leur session**. Aucune compétence requise. Le mécanisme : à l'époque, ces sites ne chiffraient que la page de connexion ; le **cookie de session** — le badge qui vous identifie ensuite — circulait en clair sur le réseau, et n'importe qui pouvait le copier (*session hijacking*).

L'extension est téléchargée **plus de 100 000 fois en 24 heures**. Le scandale est mondial — et c'était le but : forcer les géants du web à agir. En quelques mois, Facebook, Twitter puis l'essentiel du web basculent vers le **HTTPS intégral**. Quelques années plus tard, l'initiative Let's Encrypt (certificats gratuits et automatisés) achève la généralisation : plus de 90 % du web est aujourd'hui chiffré.

**Ce que ce cas illustre :** sur un réseau non chiffré, l'écoute est **passive et indétectable** — la victime ne saura jamais ; le chiffrement partiel (seulement la page de connexion) est une illusion de sécurité ; et la divulgation responsable version « électrochoc » a parfois changé le web plus vite que dix ans d'avertissements d'experts.

#### Cas n°2 — DigiNotar (2011) : quand le cadenas lui-même ment

Été 2011. Un internaute iranien remarque un avertissement étrange de son navigateur en se connectant à Gmail. L'enquête révèle l'impensable : **DigiNotar**, une autorité de certification néerlandaise — l'un de ces organismes dont le métier est de garantir l'identité des sites web —, a été piratée. Les attaquants ont émis **plus de 500 faux certificats**, dont un pour `*.google.com`, reconnus comme parfaitement valides par tous les navigateurs. Utilisés en Iran avec une interception du trafic, ces certificats ont permis d'espionner les comptes Gmail d'environ **300 000 internautes** — cadenas affiché, session « sécurisée », surveillance totale (rapport d'enquête Fox-IT).

La sanction du marché est immédiate : les navigateurs retirent DigiNotar de leurs listes de confiance, invalidant tous ses certificats — y compris ceux de l'État néerlandais, son principal client. **L'entreprise fait faillite en quelques semaines.**

**Ce que ce cas illustre :** toute la confiance du web repose sur quelques centaines d'autorités de certification — la compromission d'une seule casse la promesse du cadenas pour tout le monde ; le MitM « parfait » existe quand l'attaquant possède un certificat valide ; et pour une CA, la confiance EST le capital : perdue, l'entreprise meurt en un mois (écho au talon d'Achille « réputation » du RaaS vu en B02).

!!! tip "📊 Sondage Livestorm n°5 — Et vous ? (sondage d'opinion, pas de bonne réponse)"
    **Question :** Sur un Wi-Fi public (gare, hôtel, café), quelle est votre pratique actuelle ?

    - A) VPN systématique avant toute connexion
    - B) Je fais attention aux sites que je visite (cadenas HTTPS)
    - C) Je ne me suis jamais vraiment posé la question

    **Débrief mentor :** Sondage d'opinion — sans jugement : avant cette session, la réponse C est la plus courante. La bonne nouvelle : B est déjà une vraie protection du **contenu** (merci Firesheep) — il manque les métadonnées et les applications non-web, ce que le VPN ajoute. Après ce soir, l'objectif est que le réflexe A devienne naturel en déplacement professionnel — c'est la règle n°1 de la fiche de préconisations que vous venez de construire.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Vous arrivez à l'hôtel Bellevue. Votre téléphone détecte deux réseaux Wi-Fi ouverts : `Hotel_Bellevue` et `Hotel Bellevue - WiFi Gratuit`. **Tapez A, B ou C dans le chat :**

    - A) Je me connecte à celui qui a le meilleur signal.
    - B) Je demande à la réception le nom exact du réseau officiel, et j'active mon VPN dans tous les cas. ✅
    - C) Je me connecte aux deux pour comparer la vitesse.

    **Débrief mentor :** B — l'un des deux est peut-être un **jumeau maléfique** (*Evil Twin*) : un point d'accès pirate au nom crédible, dont l'opérateur voit transiter tout le trafic non chiffré de ses victimes. Le signal le plus fort (A) peut justement être le pirate (il est peut-être dans la chambre d'à côté). Le réflexe en deux temps : vérifier le nom officiel À la source humaine, et ne faire confiance à AUCUN Wi-Fi public — le VPN protège même si vous vous êtes trompé de réseau.

---

### Questions de réflexion
1. Si vous utilisez un site web HTTPS (chiffré) tout en étant connecté au Wi-Fi public gratuit d'un aéroport sans activer de VPN, quelles informations un attaquant espionnant le réseau peut-il tout de même intercepter ? (Indice : pensez aux requêtes de résolution de nom DNS et à la couche IP.)
2. Pourquoi une Autorité de Certification (CA) est-elle considérée comme la clé de voûte de la confiance sur Internet ? Que s'est-il passé quand DigiNotar a été compromise, et pourquoi la sanction a-t-elle été si radicale ?

**Corrigé / Éléments de réponse :**

1. L'attaquant peut voir le domaine visité (requêtes DNS, indication SNI du handshake) et les adresses IP source/destination, révélant ainsi les sites fréquentés, les horaires et les volumes — même si le contenu des pages est illisible. Le VPN masque ces métadonnées à l'observateur local.
2. Une CA piratée permet d'émettre de faux certificats (ex. pour votre banque ou votre messagerie) reconnus comme valides par tous les navigateurs : le MitM devient invisible, cadenas affiché. Pour DigiNotar : plus de 500 faux certificats, ~300 000 internautes espionnés, retrait immédiat de la confiance par les navigateurs et faillite en quelques semaines — quand on vend de la confiance, on ne survit pas à sa perte.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez la sécurité des communications sur Internet à l'aide de l'analogie d'une **valise diplomatique verrouillée** :
    - Envoyer un message en HTTP simple, c'est comme écrire une carte postale sans enveloppe. Le facteur, le trieur et le destinataire peuvent lire le texte écrit (vol de mot de passe en clair).
    - Envoyer un message en HTTPS (avec chiffrement TLS), c'est glisser la lettre dans une boîte métallique fermée par un cadenas à combinaison dont seuls vous et le destinataire possédez le code. Le facteur voit la boîte passer, mais ne peut pas lire le contenu.
    - Le **VPN (Virtual Private Network)** est comparable à une autoroute souterraine privée et blindée reliant votre domicile directement aux locaux de votre entreprise. Personne dans la rue ne peut voir qui y circule ni ce que transportent les camions.

**Exemple d'application professionnelle :**
Un consultant travaille depuis le réseau Wi-Fi public d'un hôtel. Pour sécuriser sa session, il active son VPN d'entreprise. Même si un attaquant à proximité intercepte les ondes radio du Wi-Fi de l'hôtel (ou opère un point d'accès jumeau maléfique), toutes les données transmises (identifiants, documents de travail) sont encapsulées dans le tunnel chiffré du VPN et restent totalement illisibles.

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour sécuriser et chiffrer les flux réseau d'entreprise via des solutions VPN et des certificats de confiance :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Cisco Secure Client (anciennement AnyConnect)** : L'un des clients VPN TLS/IPsec d'entreprise les plus déployés dans le monde, offrant un accès à distance sécurisé.
    *   **F5 BIG-IP Access Policy Manager (APM)** : Passerelle d'accès réseau sécurisée haut de gamme, gérant le chiffrement TLS à très grande échelle.
    *   **DigiCert / Sectigo Enterprise PKI** : Autorités de certification commerciales pour la gestion du cycle de vie des certificats TLS d'entreprise.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **OpenVPN** : Solution open-source classique de VPN TLS permettant de connecter de manière chiffrée des clients distants ou des réseaux entiers.
    *   **WireGuard** : Protocole VPN open-source moderne et extrêmement rapide, intégré directement au noyau Linux, offrant d'excellentes performances par rapport aux protocoles plus anciens.
    *   **StrongSwan** : Implémentation VPN IPsec open-source, idéale pour établir des liaisons directes sécurisées site-à-site entre serveurs.
    *   **Let's Encrypt** : Autorité de certification gratuite et automatisée fournissant des certificats TLS X.509 valides pour sécuriser les sites Web — l'un des artisans de la généralisation du HTTPS.

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après le mini-scénario.

*   **📊 Sondage n°6 :** Lors du handshake TLS, à quoi sert le certificat numérique envoyé par le serveur ?
    *   A) À chiffrer l'ensemble du trafic de la session
    *   B) À prouver l'identité du serveur, grâce à la garantie d'une autorité de certification ✅
    *   C) À accélérer le chargement des pages
*   **📊 Sondage n°7 :** Pourquoi TLS utilise-t-il la cryptographie asymétrique PUIS symétrique ?
    *   A) L'asymétrique permet d'échanger la clé sans secret préalable ; la symétrique chiffre ensuite rapidement le trafic ✅
    *   B) Par tradition : les deux font exactement la même chose
    *   C) L'asymétrique chiffre les images, la symétrique chiffre le texte
*   **📊 Sondage n°8 :** Quel avantage décisif le WPA-Enterprise (802.1X) apporte-t-il à une entreprise par rapport au WPA2-PSK ?
    *   A) Il augmente la portée du signal Wi-Fi
    *   B) Il supprime le besoin de mot de passe
    *   C) Des identifiants individuels et révocables par salarié, contrôlés par un serveur central (RADIUS) ✅

**Éléments de débriefing (pour le mentor) :**

- N°6 : le certificat ne chiffre pas — il **authentifie**. Sans lui, vous chiffreriez peut-être... vers l'attaquant (MitM). Et DigiNotar a montré ce qui arrive quand cette garantie ment.
- N°7 : le meilleur des deux mondes — l'asymétrique (lente) ne sert qu'à livrer la clé de session ; la symétrique (rapide) fait tout le reste.
- N°8 : le mot-clé est **nominatif** : un départ = une révocation individuelle, sans changer le Wi-Fi de toute l'entreprise ; et chaque connexion est traçable (RADIUS).

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Secure Protocols & Cryptography Basics"* (durée estimée : 1h30).
*   **Recherche complémentaire** : Rechercher l'affaire *DigiNotar* (2011) et le rapport « Operation Black Tulip » pour comprendre les enjeux géopolitiques de la confiance numérique.
*   [ANSSI — Recommandations de sécurité relatives à TLS](https://cyber.gouv.fr/publications/recommandations-de-securite-relatives-tls)
*   [ANSSI — Recommandations Wi-Fi](https://cyber.gouv.fr)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Analyse de la sécurité des accès nomades.
*   **📊 Sondage Livestorm n°9 :** Quelle est la différence majeure entre un VPN et un proxy web simple ?
    *   A) Le proxy est payant, pas le VPN.
    *   B) Le VPN chiffre la totalité du trafic réseau de la machine, tandis que le proxy ne fait que relayer le trafic applicatif (souvent web) sans chiffrement global ✅
    *   C) Il n'y a aucune différence technique.
*   **Guide d'animation (pour le mentor) :** Montrez pourquoi le VPN d'entreprise est indispensable pour les connexions distantes : il protège l'ensemble des protocoles de la machine (messagerie, applications métier, DNS), pas seulement le navigateur. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **CA (Certificate Authority)** | Tiers de confiance qui garantit l'identité des serveurs via les certificats — la clé de voûte du cadenas (cf. DigiNotar). |
| **Evil Twin (Jumeau maléfique)** | Faux point d'accès Wi-Fi au nom crédible — la victime s'y connecte d'elle-même. |
| **Handshake TLS** | Négociation initiale : algorithmes, authentification du serveur (certificat), échange de la clé de session. |
| **Man-in-the-Middle (MitM)** | Interception active : l'attaquant s'interpose entre deux parties pour lire ou modifier les échanges. |
| **PKI** | Infrastructure délivrant et gérant les certificats numériques de confiance (X.509). |
| **RADIUS** | Serveur central d'authentification des accès réseau (802.1X) — le cœur du WPA-Enterprise. |
| **TLS** | Le protocole du HTTPS : chiffre les flux applicatifs et authentifie le serveur (successeur du SSL, déprécié). |
| **VPN** | Tunnel chiffré à travers un réseau public — chiffre TOUT le trafic de la machine (vs proxy). |
| **WPA3 / WPA-Enterprise** | Les standards Wi-Fi modernes : SAE contre l'écoute passive ; 802.1X pour des accès nominatifs révocables. |

**La règle d'or de la session :** ne faites jamais confiance au réseau traversé — chiffrez le contenu (HTTPS partout), chiffrez le chemin en mobilité (VPN d'abord, tout le reste ensuite), et souvenez-vous que le cadenas authentifie le serveur... tant que les autorités de certification tiennent leur promesse.
