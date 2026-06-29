# Session B05 — Fondamentaux réseau pour la sécurité

## Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer les couches clés des modèles OSI et TCP/IP à travers le prisme de la sécurité en identifiant où se situent les principales attaques et défenses.
* Décrire le rôle des protocoles réseaux majeurs (DNS, DHCP, ARP, ICMP) et identifier les ports de communication standards les plus exposés (22, 53, 80, 443, 3389).
* Lire et analyser la structure d'une adresse IP (partie réseau vs partie hôte) et interpréter les éléments clés d'un en-tête de paquet réseau simple (IP source/dest, ports, TTL).

---

## Concepts clés

### 1. Les Modèles OSI et TCP/IP sous l'angle de la sécurité
Pour faire communiquer des ordinateurs, les données doivent être formatées et transmises selon des règles strictes. Le modèle théorique **OSI** (en 7 couches) et le modèle pratique **TCP/IP** (en 4 couches) décrivent ce processus. En cybersécurité, chaque couche représente une surface d'attaque spécifique et nécessite des défenses adaptées.

*   **Couche 2 : Liaison (*Data Link*)** — Gère la communication physique locale entre cartes réseau via les adresses **MAC** (*Media Access Control*).
    *   *Attaque* : L'usurpation ARP (*ARP spoofing*) permettant d'intercepter le trafic local.
    *   *Défense* : Sécurisation des ports de commutateurs (*Port Security*) et inspection ARP dynamique.
*   **Couche 3 : Réseau (*Network*)** — Assure le routage des paquets à travers Internet via les adresses **IP** (*Internet Protocol*).
    *   *Attaque* : L'usurpation d'adresse IP (*IP spoofing*) pour masquer l'identité de l'attaquant.
    *   *Défense* : Filtrage par pare-feu (*firewall*) et listes de contrôle d'accès (ACL).
*   **Couche 4 : Transport** — Assure la connexion de bout en bout (TCP pour les connexions fiables avec maintien d'état, UDP pour la rapidité sans garantie).
    *   *Attaque* : Inondation de paquets SYN (*SYN Flood*) pour saturer la mémoire d'un serveur et le rendre indisponible.
    *   *Défense* : Pare-feux à états (*stateful firewalls*) et limites de connexions par IP.
*   **Couche 7 : Application** — Les protocoles utilisés par les logiciels finaux (HTTP, DNS, SMTP, RDP).
    *   *Attaque* : Injections de code (SQL, XSS), usurpation de services.
    *   *Défense* : Pare-feu applicatif (WAF — *Web Application Firewall*), chiffrement SSL/TLS.

*   *Analogie postale* :
    *   Couche 2 (Liaison) = Le coursier qui transporte les enveloppes dans un même bâtiment.
    *   Couche 3 (Réseau) = L'adresse écrite sur l'enveloppe lue par le centre de tri national.
    *   Couche 4 (Transport) = Le choix d'envoyer la lettre en recommandé avec accusé de réception (TCP) ou en courrier simple (UDP).
    *   Couche 7 (Application) = La langue (français, anglais) et le contenu du message écrit à l'intérieur.

### 2. Protocoles et ports de communication majeurs
Les données circulent sur le réseau via des protocoles (langages) spécifiques, et arrivent à destination sur des **ports de communication** (portes d'entrée logiques sur une machine).

*   **DNS (*Domain Name System*) — Port 53** : L'annuaire d'Internet. Il traduit les noms de domaine lisibles (ex: `google.com`) en adresses IP compréhensibles par les machines (ex: `142.250.179.78`).
    *   *Risque* : Le tunneling DNS (*DNS tunneling*), utilisé par les attaquants pour exfiltrer discrètement des données dans des requêtes DNS légitimes.
*   **DHCP (*Dynamic Host Configuration Protocol*)** : Attribue automatiquement une configuration IP aux machines qui se connectent au réseau local.
    *   *Risque* : Un serveur DHCP pirate (*Rogue DHCP*) qui distribue de fausses configurations pour détourner le trafic.
*   **ARP (*Address Resolution Protocol*)** : Traduit une adresse IP connue en adresse MAC physique sur le réseau local.
*   **ICMP (*Internet Control Message Protocol*)** : Utilisé pour les diagnostics réseau (comme la commande `ping`).
    *   *Risque* : Blocage systématique de l'ICMP sortant par les entreprises pour éviter la reconnaissance réseau par les attaquants (ping sweeps).

#### Les ports courants à surveiller :
*   **Port 22 — SSH (*Secure Shell*)** : Connexion d'administration à distance sécurisée (souvent ciblé par attaques par force brute).
*   **Port 80 — HTTP** : Trafic web non chiffré (à proscrire pour les données sensibles).
*   **Port 443 — HTTPS** : Trafic web chiffré via SSL/TLS.
*   **Port 3389 — RDP (*Remote Desktop Protocol*)** : Prise de contrôle à distance graphique Windows (extrêmement recherché par les rançongiciels).

> 💡 **Bon à savoir : Les ports bien connus (*Well-Known Ports*)**
> Les ports de 0 à 1023 sont réservés par l'IANA (*Internet Assigned Numbers Authority*) pour les services système standard (comme HTTP sur le port 80). Les fermer s'ils ne sont pas activement utilisés est la première règle de réduction de surface d'attaque.

### 3. Adressage IP et En-têtes de paquets
Une adresse IPv4 est composée de 32 bits (ex. `192.168.1.50`). Elle est divisée en deux parties grâce au **masque de sous-réseau** (ex. `255.255.255.0`) :

1.  **L'adresse réseau** : identifie le réseau sur lequel se trouve la machine (la rue).
2.  **L'adresse hôte** : identifie la machine spécifique sur ce réseau (le numéro de maison).

Lorsqu'un paquet est envoyé, il contient un **en-tête IP** contenant les métadonnées de transmission :

*   **IP Source & IP Destination** : Qui envoie et qui reçoit.
*   **TTL (*Time To Live*)** : Une durée de vie sous forme de compteur de routeurs traversés. À chaque routeur, le TTL baisse de 1. S'il atteint 0, le paquet est détruit pour éviter qu'il ne tourne en boucle infinie sur Internet.
*   **Protocol** : Indique si le paquet de transport encapsulé est du TCP ou de l'UDP.

---

## Activités / exercices

### Exercice 1 — Analyse d'un paquet réseau tracé (Wireshark simplifié)
**Objectif :** Analyser des captures de trames réseau simplifiées au format texte afin d'identifier les flux d'informations et repérer une activité suspecte.

**Consignes :**
Analysez les deux extraits de paquets ci-dessous et répondez aux questions :

1. Quelle est l'adresse IP source et destination ?
2. Quels sont les ports source et destination ? Quel protocole applicatif est ciblé ?
3. L'un de ces paquets présente-t-il une anomalie de sécurité ? Si oui, laquelle ?

#### Capture A
```text
[ FRAME LAYER 2 ] Source MAC: 00:1A:2B:3C:4D:5E -> Dest MAC: 00:1A:2B:99:88:77
[ IP LAYER 3 ] Source IP: 192.168.1.15 -> Dest IP: 8.8.8.8 | TTL: 64 | Proto: UDP
[ TRANSPORT LAYER 4 ] Source Port: 53120 -> Dest Port: 53
[ APPLICATION LAYER 7 ] DNS Query: secure-login.bank-online-security-update.com
```

#### Capture B
```text
[ FRAME LAYER 2 ] Source MAC: 00:1A:2B:3C:4D:5E -> Dest MAC: 00:1A:2B:99:88:77
[ IP LAYER 3 ] Source IP: 192.168.1.102 -> Dest IP: 192.168.1.200 | TTL: 128 | Proto: TCP
[ TRANSPORT LAYER 4 ] Source Port: 49215 -> Dest Port: 3389
[ APPLICATION LAYER 7 ] RDP Connection Request | Connection Attempt: 45th in the last 10 seconds
```

**Corrigé / Éléments de réponse :**

*   **Analyse de la Capture A** :
    1.  *IP Source* : `192.168.1.15` (machine locale) | *IP Dest* : `8.8.8.8` (serveur DNS public de Google).
    2.  *Ports* : Port source `53120` (port dynamique éphémère), Port dest `53` (DNS). Le protocole de transport est UDP.
    3.  *Anomalie* : La requête DNS demande la résolution de `secure-login.bank-online-security-update.com`. Le nom de domaine ressemble fortement à une tentative d'hameçonnage (*phishing*) usurpant une banque avec un nom de domaine trompeur.
*   **Analyse de la Capture B** :
    1.  *IP Source* : `192.168.1.102` | *IP Dest* : `192.168.1.200` (les deux sont sur le même réseau local `192.168.1.0/24`).
    2.  *Ports* : Port source `49215` (port éphémère), Port dest `3389` (RDP — bureau à distance Windows). Le protocole de transport est TCP.
    3.  *Anomalie* : Il est indiqué "45ème tentative de connexion en 10 secondes". Il s'agit d'une attaque par force brute réseau (*brute force attack*) sur le service d'administration RDP de la machine `192.168.1.200`.

---

## Questions de réflexion
1. Pourquoi est-il dangereux de laisser le protocole RDP (port 3389) directement ouvert et accessible depuis Internet sur un serveur d'entreprise ? Quelle solution réseau intermédiaire permettrait de sécuriser cet accès ?
2. Si un pare-feu bloque le trafic sur le port 80 (HTTP) mais laisse passer le trafic sur le port 53 (DNS), comment un attaquant peut-il utiliser cette configuration pour exfiltrer des fichiers ?

---

## Résumé / points à retenir
*   Les couches réseau (Liaison, Réseau, Transport, Application) structurent la façon dont les données transitent et définissent les différents types d'attaques cyber.
*   Chaque service réseau standard écoute sur un **port de communication** spécifique (22 pour SSH, 53 pour DNS, 80/443 pour HTTP/S, 3389 pour RDP).
*   Une capture de paquets (trame réseau) révèle l'origine (IP/MAC source), la destination (IP/MAC destination), le protocole et le contenu applicatif du flux.
*   Bloquer les ports inutilisés et analyser le trafic anormal sont des réflexes indispensables pour assurer la sécurité réseau.

---

## Glossaire de la session
*   **MAC Address (Adresse MAC)** — Identifiant physique unique gravé en usine sur chaque carte réseau.
*   **IP Address (Adresse IP)** — Identifiant logique attribué à chaque machine connectée à un réseau, permettant son routage.
*   **DNS Tunneling (Tunneling DNS)** — Technique de détournement consistant à encapsuler du trafic non-DNS dans des requêtes DNS pour contourner les pare-feux.
*   **TTL (Time To Live)** — Valeur dans l'en-tête IP indiquant le nombre maximal de sauts de routeurs autorisés avant la destruction du paquet.

---

## Pour aller plus loin (self-paced)
*   **Sur IBM SkillsBuild** : Suivre le cours *"Network Security - Part 1"* (durée estimée : 1h30).
*   **Action pratique** : Ouvrez un terminal sur votre machine et tapez la commande `ping -c 4 cyber.gouv.fr`. Observez le temps de réponse et la valeur de TTL renvoyée par le serveur.
