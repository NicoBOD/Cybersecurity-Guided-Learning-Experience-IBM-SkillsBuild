# Session B07 — Communications sécurisées

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Sécuriser le web : Le protocole TLS/SSL
    - Les Réseaux Privés Virtuels (VPN)
    - La sécurité des communications sans-fil (Wi-Fi)
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   **HTTPS/TLS** protège les données applicatives en transit en combinant la cryptographie asymétrique (échange de clés) et symétrique (chiffrement des flux).
*   La validation du **certificat numérique** par le navigateur empêche les attaques par interception *Man-in-the-Middle* (MitM).
*   Le **VPN** sécurise les flux de transport sur des réseaux publics en créant un tunnel chiffré (IPsec pour le site-à-site, WireGuard/OpenVPN pour le nomade).
*   La sécurité Wi-Fi moderne requiert l'abandon de WEP/WPA2-PSK au profit de **WPA3** et de **WPA-Enterprise** pour l'authentification individuelle.

---

## 2. Développement
Passez 30 minutes sur la cryptographie de transport. Expliquez le fonctionnement du Handshake TLS : négociation des algorithmes, authentification du serveur par un certificat numérique, et génération de la clé de session symétrique. Abordez les risques liés à l'utilisation des Wi-Fi publics (Evil Twin, écoute de trames).

---

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer les étapes du protocole de négociation (*handshake*) TLS/SSL dans la sécurisation des échanges web (HTTPS) et le rôle des autorités de certification.
* Comparer les protocoles et architectures VPN (IPsec, OpenVPN, WireGuard) en fonction de leurs cas d'usage (accès utilisateur distant ou interconnexion de sites).
* Identifier les failles des anciens protocoles de chiffrement Wi-Fi (WEP, WPA2-PSK) et préconiser des solutions modernes (WPA3, WPA-Enterprise).

---

### Glossaire

*   **CA (Certificate Authority)** — Organisme tiers de confiance chargé de générer, valider et révoquer les certificats numériques d'identité des serveurs.
*   **Handshake TLS** — Phase de négociation initiale où le client et le serveur s'authentifient et définissent la clé de chiffrement de leur session.
*   **Man-in-the-Middle (MitM)** — Attaque d'interception où un pirate s'interpose secrètement entre deux parties pour lire ou modifier leurs communications.
*   **Man-in-the-Middle (MitM)** — Attaque consistant pour un pirate à intercepter et éventuellement altérer les communications secrètes entre deux cibles légitimes.
*   **PKI (Infrastructure de Clés Publiques)** — Système de serveurs, de logiciels et de procédures délivrant et gérant des certificats numériques de confiance (certificats X.509).
*   **RADIUS Server** — Serveur centralisant l'authentification, les autorisations et la traçabilité des accès utilisateurs sur un réseau d'entreprise (802.1X).
*   **TLS/SSL** — Protocole de sécurisation des échanges réseau chiffrant les flux applicatifs (comme HTTPS) et garantissant l'identité du serveur.
*   **VPN (Réseau Privé Virtuel)** — Réseau virtuel sécurisé créant un tunnel chiffré pour le transit de données sur un réseau public.

---

### Concepts clés

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

### 1. Sécuriser le web : Le protocole TLS/SSL
Lorsque vous naviguez sur un site web en HTTP classique, toutes les informations (mots de passe, numéros de carte bancaire) transitent en texte clair sur le réseau. Le protocole **HTTPS** sécurise ces échanges en encapsulant le trafic HTTP au sein d'un tunnel chiffré par le protocole **TLS** (*Transport Layer Security* — successeur du SSL).

*   *L'analogie* : Naviguer en HTTP équivaut à envoyer une carte postale sans enveloppe (tous les intermédiaires peuvent la lire). Naviguer en HTTPS équivaut à glisser le message dans un coffre-fort blindé portatif dont seul le destinataire possède le code.
*   **Le Handshake TLS (Poignée de main)** :
    1.  *Négociation* : Le navigateur et le serveur s'accordent sur la version de TLS et les algorithmes de chiffrement à utiliser.
    2.  *Authentification* : Le serveur envoie son **certificat numérique**. Le navigateur vérifie sa validité auprès d'une **Autorité de Certification** (CA — *Certificate Authority*) de confiance pour s'assurer que le site est bien celui qu'il prétend être (évitant l'interception *Man-in-the-Middle* — MitM).
    3.  *Échange de clés* : Ils utilisent la cryptographie asymétrique (clé publique/privée) pour s'échanger en toute sécurité une **clé symétrique temporaire** (clé de session).
    4.  *Chiffrement* : Le reste de la communication est chiffré de manière ultra-rapide avec cette clé symétrique de session.

### 2. Les Réseaux Privés Virtuels (VPN)
Un **VPN** (*Virtual Private Network*) crée un tunnel virtuel chiffré à travers un réseau public non sûr (comme Internet) pour relier de manière sécurisée deux entités distantes.

On distingue deux architectures majeures :

*   **Le VPN d'accès distant (Client-to-Site)** : Permet à un utilisateur nomade (télétravailleur) d'installer un logiciel client sur son poste pour se connecter de manière sécurisée au réseau de son entreprise.
*   **Le VPN site-à-site (Site-to-Site)** : Interconnecte de manière permanente les réseaux de deux sites physiques distincts d'une entreprise (ex. relier le siège social et une usine).

#### Comparatif des protocoles VPN :
*   **IPsec (*IP Security*)** : Protocole historique et très robuste opérant au niveau de la couche 3 (Réseau). C'est la norme industrielle pour les tunnels VPN permanents site-à-site.
*   **OpenVPN** : Solution open-source très flexible fonctionnant sur la couche 4 (Transport). Il est sécurisé et largement déployé pour les clients nomades, mais sa configuration peut être complexe et il est gourmand en ressources.
*   **WireGuard** : Le protocole moderne par excellence. Beaucoup plus léger en lignes de code, extrêmement rapide et performant. Il consomme moins de batterie sur les appareils mobiles et se reconnecte instantanément lors d'un changement de réseau.

### 3. La sécurité des communications sans-fil (Wi-Fi)
Les ondes radio du Wi-Fi traversent les murs, ce qui permet à n'importe qui à proximité physique d'intercepter les paquets s'ils ne sont pas chiffrés.

*   **WEP (*Wired Equivalent Privacy*)** : Protocole de première génération. **Totalement obsolète et dangereux**. Ses faiblesses mathématiques permettent de casser sa clé de sécurité en quelques secondes à l'aide d'outils grand public.
*   **WPA2-PSK (*Pre-Shared Key*)** : Le protocole le plus répandu à la maison. Il utilise une clé unique partagée pour tous les utilisateurs. Il est vulnérable aux attaques par dictionnaire (si la clé est trop simple) et à des failles de conception (attaque KRACK).
*   **WPA3** : Le standard moderne. Il corrige les failles de WPA2 en remplaçant l'échange de clés initial par le protocole **SAE** (*Simultaneous Authentication of Equals*), empêchant le piratage de la clé Wi-Fi par interception passive et attaque hors ligne.
*   **WPA-Enterprise (802.1X)** : Destiné aux entreprises. Au lieu d'avoir un mot de passe unique pour tout le monde, chaque salarié se connecte avec son propre identifiant/mot de passe ou son propre certificat de sécurité. Le contrôle d'accès est centralisé par un serveur d'authentification (généralement de type **RADIUS**).

---

### Activités / exercices
### Exercice 1 — Scénarisation de connexions distantes sécurisées
**Objectif :** Analyser le besoin d'une entreprise nomade et rédiger des préconisations de sécurité réseau adaptées pour protéger les flux de données.

**Consignes :**
Vous êtes consultant en cybersécurité pour une société de conseil comprenant 100 consultants mobiles. Ils se déplacent fréquemment chez des clients, travaillent dans des gares ou des hôtels, et doivent accéder en toute sécurité aux serveurs internes de l'entreprise (contenant des rapports d'audit confidentiels) ainsi qu'à des applications Cloud.

Rédigez une fiche de préconisations techniques et d'usages en répondant aux 3 questions suivantes :

1.  **Vecteur réseau** : Quel protocole Wi-Fi et quelle méthode d'authentification préconisez-vous pour le réseau sans-fil des bureaux du siège de l'entreprise ? Justifiez votre choix.
2.  **Accès nomade** : Quelle technologie de VPN recommandez-vous d'installer sur les ordinateurs des consultants pour leurs déplacements ? Pourquoi ?
3.  **Comportement sur le terrain** : Un consultant travaille dans un café et doit utiliser le réseau Wi-Fi public gratuit du café pour envoyer un document confidentiel. Listez les 3 règles de sécurité absolues qu'il doit appliquer sur-le-champ.

**Corrigé / Éléments de réponse :**

1.  **Préconisation Réseau Wi-Fi au Siège** :
    *   *Choix* : **WPA3-Enterprise** (s'appuyant sur le protocole 802.1X).
    *   *Justification* : WPA3 apporte une sécurité cryptographique robuste contre les attaques de déchiffrement passif, tandis que la version "Enterprise" garantit que chaque consultant dispose de ses propres identifiants nominatifs. Si un consultant quitte l'entreprise, on peut révoquer son accès individuellement sans devoir changer le mot de passe Wi-Fi de toute l'entreprise.
2.  **Préconisation VPN Nomade** :
    *   *Choix* : **WireGuard** (ou OpenVPN sous forme de client d'accès distant).
    *   *Justification* : WireGuard est idéal pour les travailleurs mobiles. Sa légèreté limite la consommation de batterie de l'ordinateur portable, ses débits sont optimisés pour les connexions parfois instables (3G/4G, Wi-Fi d'hôtel), et il rétablit le tunnel chiffré instantanément sans coupure ressentie par l'utilisateur lors des changements de réseau.
3.  **Règles d'usage sur Wi-Fi public** :
    *   *Règle 1* : Activer le **VPN** d'entreprise *avant* d'ouvrir toute application ou navigateur web. Le VPN chiffrera l'intégralité du trafic, empêchant un pirate connecté sur le même Wi-Fi public d'intercepter les données.
    *   *Règle 2* : S'assurer que tous les sites consultés affichent le protocole **HTTPS** (cadenas fermé) dans la barre d'adresse pour garantir un double chiffrement (chiffrement applicatif HTTPS + chiffrement réseau VPN).
    *   *Règle 3* : Désactiver le partage de fichiers réseau local sur l'ordinateur portable (profil réseau configuré en "Public" sous Windows/macOS) pour éviter que d'autres utilisateurs du café ne scannent le poste de travail.

---

### Questions de réflexion
1. Si vous utilisez un site web HTTPS (chiffré) tout en étant connecté au Wi-Fi public gratuit d'un aéroport sans activer de VPN, quelles informations un attaquant espionnant le réseau peut-il tout de même intercepter ? (Indice : Pensez aux requêtes de résolution de nom DNS et à la couche IP).
2. Pourquoi une Autorité de Certification (CA) est-elle considérée comme la clé de voûte de la confiance sur Internet ? Que se passerait-il si un attaquant parvenait à pirater une CA et à émettre de faux certificats ?

**Corrigé / Éléments de réponse :**
1. L'attaquant peut voir le domaine visité (DNS) et les adresses IP source/destination, révélant ainsi les sites fréquentés, même si le contenu des pages est illisible.
2. Une CA piratée permettrait à l'attaquant de créer de faux certificats (ex: pour votre banque) reconnus comme valides par les navigateurs, rendant les attaques de type Man-In-The-Middle transparentes.

---


### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez la sécurité des communications sur Internet à l'aide de l'analogie d'une **valise diplomatique verrouillée** :
    - Envoyer un message en HTTP simple, c'est comme écrire une carte postale sans enveloppe. Le facteur, le trieur et le destinataire peuvent lire le texte écrit (vol de mot de passe en clair).
    - Envoyer un message en HTTPS (avec chiffrement TLS), c'est glisser la lettre dans une boîte métallique fermée par un cadenas à combinaison dont seuls vous et le destinataire possédez le code. Le facteur voit la boîte passer, mais ne peut pas lire le contenu.
    - Le **VPN (Virtual Private Network)** est comparable à une autoroute souterraine privée et blindée reliant votre domicile directement aux locaux de votre entreprise. Personne dans la rue ne peut voir qui y circule ni ce que transportent les camions.

**Exemple d'application professionnelle :**
Un consultant travaille depuis le réseau Wi-Fi public d'un hôtel. Pour sécuriser sa session, il active son VPN d'entreprise (IPsec). Même si un attaquant à proximité intercepte les ondes radio du Wi-Fi de l'hôtel (attaque de l'homme du milieu), toutes les données transmises (identifiants, documents de travail) sont encapsulées dans le tunnel chiffré du VPN et restent totalement illisibles.


## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Secure Protocols & Cryptography Basics"* (durée estimée : 1h30).
*   **Recherche complémentaire** : Ouvrez un site d'actualité cyber et recherchez des cas d'attaques historiques de type "MitM" ou des compromissions d'Autorités de Certification (comme l'affaire *DigiNotar* en 2011) pour comprendre les enjeux géopolitiques de la confiance numérique.


---

* [ANSSI - Recommandations TLS](https://cyber.gouv.fr/publications/recommandations-de-securite-relatives-tls)
* [ANSSI - WiFi Sécurisé](https://cyber.gouv.fr)

## 4. Exercice bonus

- **Objectif :** Analyse du chiffrement lors d'une session Web sécurisée.
- **Consignes :**
    1. Expliquez brièvement comment le navigateur de l'utilisateur vérifie l'identité d'un site web bancaire lors de la phase initiale de connexion HTTPS. (Quel est le rôle du certificat X.509 et des Autorités de Certification ?).
    2. Pourquoi utilise-t-on le chiffrement asymétrique au début de la connexion, puis le chiffrement symétrique pour le transfert des données ?
- **Correction pour le mentor :** Le navigateur vérifie le certificat X.509 fourni par le serveur bancaire en vérifiant s'il est signé par une Autorité de Certification (CA) de confiance pré-enregistrée dans le système. Le chiffrement asymétrique (lent mais sûr sans clé partagée au départ) sert uniquement à échanger de manière sécurisée une clé de session temporaire. Le chiffrement symétrique (très rapide) prend le relais pour chiffrer l'ensemble des données échangées avec cette clé commune.

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **CA (Certificate Authority)** | Organisme tiers de confiance chargé de générer, valider et révoquer les certificats numériques d'identité des serveurs. |
| **Handshake TLS** | Phase de négociation initiale où le client et le serveur s'authentifient et définissent la clé de chiffrement de leur session. |
| **Man-in-the-Middle (MitM)** | Attaque d'interception où un pirate s'interpose secrètement entre deux parties pour lire ou modifier leurs communications. |
| **PKI (Infrastructure de Clés Publiques)** | Système de serveurs, de logiciels et de procédures délivrant et gérant des certificats numériques de confiance (certificats X.509). |
| **RADIUS Server** | Serveur centralisant l'authentification, les autorisations et la traçabilité des accès utilisateurs sur un réseau d'entreprise (802.1X). |
| **TLS/SSL** | Protocole de sécurisation des échanges réseau chiffrant les flux applicatifs (comme HTTPS) et garantissant l'identité du serveur. |
| **VPN (Réseau Privé Virtuel)** | Réseau virtuel sécurisé créant un tunnel chiffré pour le transit de données sur un réseau public. |

