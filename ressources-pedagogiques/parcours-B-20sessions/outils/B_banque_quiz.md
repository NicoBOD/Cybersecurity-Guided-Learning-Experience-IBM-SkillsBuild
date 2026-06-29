# Banque de Quiz — Parcours B (20 sessions)
Parcours : B 20 sessions  |  Module : Évaluation continue  |  Format : Banque de QCM résolus

---

## Session B01 : Introduction à la cybersécurité & triade CIA

### Question 1 : Le pilier d'Intégrité
Quelle mesure garantit le pilier de l'**Intégrité** de la triade CIA lorsqu'un fichier est transféré sur un réseau ?
* A. Le chiffrement symétrique AES-256.
* B. L'empreinte cryptographique (hachage) SHA-256.
* C. La redondance des disques durs (RAID 1).
* **Réponse correcte : B**
* *Explication* : L'empreinte ou hachage (ex. SHA-256) permet de vérifier qu'un fichier n'a pas été altéré ou corrompu pendant son transfert. Si le fichier change même d'un bit, son empreinte change complètement. Le chiffrement AES-256 garantit la Confidentialité et le RAID 1 assure la Disponibilité.

### Question 2 : Le concept de Défense en Profondeur
Qu'illustre le principe de la **Défense en Profondeur** ?
* A. Acheter le pare-feu le plus cher du marché pour sécuriser la périphérie.
* B. Installer plusieurs couches de contrôles de sécurité indépendants (physiques, techniques, administratifs).
* C. Conserver tous les serveurs informatiques dans un sous-sol sécurisé à 10 mètres de profondeur.
* **Réponse correcte : B**
* *Explication* : La défense en profondeur consiste à superposer plusieurs barrières de sécurité (ex. pare-feu + antivirus + formation des utilisateurs + MFA). Si une barrière cède, les autres empêchent ou ralentissent la progression de l'attaquant.

---

## Session B02 : Paysage des menaces & acteurs

### Question 1 : Motivation des Advanced Persistent Threats (APT)
Quelle est la principale caractéristique et motivation d'un groupe d'attaquants qualifié d'APT (généralement soutenu par un État) ?
* A. Obtenir des gains financiers immédiats par le vol de cartes bleues.
* B. Réaliser des attaques à des fins de sabotage politique ou d'espionnage industriel à long terme.
* C. Modifier le design d'un site web public par idéologie (défacement).
* **Réponse correcte : B**
* *Explication* : Les APT (États-nations) disposent de ressources financières et techniques illimitées. Leurs campagnes visent l'espionnage, le vol de propriété industrielle ou le sabotage géopolitique à long terme. Le vol de cartes bleues est l'apanage des cybercriminels, et le défacement idéologique est mené par des hacktivistes.

### Question 2 : La notion de "Script Kiddie"
Qu'est-ce qu'un "Script Kiddie" dans le jargon de la cybersécurité ?
* A. Un analyste junior apprenant à coder en Python.
* B. Un attaquant utilisant des scripts et outils automatisés créés par d'autres, sans en comprendre le fonctionnement réel.
* C. Un botnet de serveurs automatisés spammant des e-mails d'hameçonnage.
* **Réponse correcte : B**
* *Explication* : Un Script Kiddie manque de compétences techniques avancées. Il se contente de télécharger et de lancer des outils de piratage publics disponibles sur Internet, souvent par jeu ou par provocation.

---

## Session B03 : Types d'attaques & vecteurs

### Question 1 : L'attaque de l'Homme du Milieu (MitM)
Quelle action illustre une attaque de type "Homme du Milieu" (Man-in-the-Middle) ?
* A. Un attaquant qui usurpe l'adresse IP d'un serveur légitime pour intercepter les flux réseau non chiffrés d'un utilisateur.
* B. Un pirate qui devine le mot de passe d'une session Windows par force brute.
* C. Une clé USB malveillante déposée sur un bureau pour piéger un logisticien.
* **Réponse correcte : A**
* *Explication* : L'attaque MitM consiste à intercepter et éventuellement altérer les communications entre deux parties à leur insu (ex. sur un réseau Wi-Fi public non chiffré).

### Question 2 : Attaque par Déni de Service Distribué (DDoS)
Quel est l'objectif premier d'une attaque DDoS ?
* A. Voler la base de données de facturation d'un site e-commerce.
* B. Rendre un site web ou un serveur indisponible en saturant ses ressources de requêtes simultanées.
* C. Installer un logiciel espion de type Keylogger sur les ordinateurs des dirigeants.
* **Réponse correcte : B**
* *Explication* : Le DDoS vise la Disponibilité. En mobilisant des milliers de machines compromises (botnet) pour envoyer simultanément des requêtes à une cible, le serveur est débordé et ne peut plus répondre aux clients légitimes.

---

## Session B04 : Ingénierie sociale & facteur humain

### Question 1 : Le spear-phishing (harponnage)
Quelle est la différence entre un e-mail de phishing classique et un e-mail de spear-phishing ?
* A. Le spear-phishing contient obligatoirement une pièce jointe de type exécutable (.exe).
* B. Le spear-phishing est ultra-ciblé, rédigé sur mesure pour une victime précise en exploitant des détails professionnels réels.
* C. Le phishing classique est envoyé uniquement par SMS (Smishing).
* **Réponse correcte : B**
* *Explication* : Le spear-phishing (harponnage) est une attaque ciblée. Le pirate se renseigne sur sa victime (ex. via LinkedIn) pour usurper l'identité d'un client réel ou d'un fournisseur et rendre l'email extrêmement crédible.

### Question 2 : Le concept de Tailgating (Talonnage)
En sécurité physique, qu'est-ce que le "Tailgating" ?
* A. Espionner l'écran d'un salarié à son insu par-dessus son épaule.
* B. Suivre de près un employé habilité pour franchir une porte sécurisée sans présenter de badge.
* C. Fouiller les poubelles d'une entreprise pour y trouver des mots de passe jetés.
* **Réponse correcte : B**
* *Explication* : Le tailgating (talonnage) exploite la politesse ou l'inattention. Le pirate profite du fait qu'un employé ouvre une porte avec son badge pour entrer juste derrière lui avant que la porte ne se referme.

---

## Session B05 : Fondations réseau pour la sécurité

### Question 1 : Rôle du protocole ARP
Quel est le rôle du protocole ARP (Address Resolution Protocol) sur un réseau local ?
* A. Traduire une adresse IP logique en adresse MAC physique.
* B. Assurer la distribution dynamique d'adresses IP aux hôtes.
* C. Résoudre un nom de domaine en adresse IP.
* **Réponse correcte : A**
* *Explication* : ARP fait le lien entre la couche 2 (liaison - adresse MAC) et la couche 3 (réseau - adresse IP). DHCP distribue les IP, et DNS résout les noms de domaines.

### Question 2 : Le protocole DNS (Domain Name System)
Pourquoi le protocole DNS représente-t-il une cible et un vecteur d'attaque de choix en sécurité ?
* A. Parce qu'il est responsable du chiffrement des fichiers locaux.
* B. Parce qu'un attaquant peut falsifier les réponses DNS (DNS Spoofing) pour rediriger les salariés vers de faux sites web.
* C. Parce qu'il fonctionne uniquement sans connexion Internet.
* **Réponse correcte : B**
* *Explication* : Si un pirate falsifie la réponse DNS (ex. empoisonnement du cache), taper "mabanque.fr" redirigera l'utilisateur vers le serveur du pirate, permettant de voler ses identifiants.

---

## Session B06 : Défenses réseau

### Question 1 : IDS vs IPS
Quelle est la différence de réaction fondamentale entre un IDS (Intrusion Detection System) et un IPS (Intrusion Prevention System) ?
* A. L'IDS bloque l'attaque tandis que l'IPS génère uniquement une alerte de sécurité.
* B. L'IDS génère une alerte sans bloquer le trafic, tandis que l'IPS bloque activement le trafic jugé malveillant.
* C. L'IDS analyse uniquement les disques durs locaux et l'IPS analyse les réseaux.
* **Réponse correcte : B**
* *Explication* : L'IDS est passif (écoute et alerte). L'IPS est actif (placé en coupure sur le réseau, il bloque la connexion suspecte en direct).

### Question 2 : L'architecture DMZ (Zone Démilitarisée)
Qu'est-ce qui caractérise l'isolement d'une DMZ réseau ?
* A. La DMZ n'a aucun contact avec Internet pour être totalement étanche.
* B. Elle contient les serveurs accessibles depuis Internet et est configurée pour empêcher toute connexion initiée depuis la DMZ vers le réseau interne (LAN).
* C. Elle est réservée aux ordinateurs personnels des salariés se connectant en Wi-Fi.
* **Réponse correcte : B**
* *Explication* : La DMZ héberge les serveurs exposés (ex. serveur web). La règle d'or est que si un serveur web en DMZ est piraté, le pare-feu doit bloquer les flux initiés par ce serveur vers les machines internes du LAN.

---

## Session B07 : Communications sécurisées

### Question 1 : Le rôle du protocole TLS (Transport Layer Security)
Quel pilier de la sécurité TLS garantit-il lors d'une connexion bancaire en HTTPS ?
* A. La disponibilité permanente du site web de la banque.
* B. La confidentialité par chiffrement et l'authenticité du serveur via son certificat numérique.
* C. Le stockage sécurisé des données sur le serveur de la banque.
* **Réponse correcte : B**
* *Explication* : TLS assure le chiffrement des données de transport (Confidentialité) et valide l'identité du serveur web grâce à un certificat émis par une Autorité de Certification (Authenticité).

### Question 2 : VPN SSL vs VPN IPsec
Dans quel cas privilégie-t-on le déploiement d'un VPN IPsec ?
* A. Pour permettre à un commercial de se connecter à Microsoft 365 depuis un simple navigateur web sans logiciel.
* B. Pour interconnecter de manière permanente et chiffrée deux réseaux locaux de sites géographiques distincts (site-à-site).
* C. Pour scanner les virus présents sur une clé USB distante.
* **Réponse correcte : B**
* *Explication* : IPsec fonctionne au niveau de la couche réseau et convient parfaitement pour créer des tunnels permanents de routeur à routeur (site-à-site). Le VPN SSL (ou portails d'accès) est souvent préféré pour des connexions utilisateurs ponctuelles depuis des postes tiers via un navigateur.

---

## Session B08 : Durcissement des systèmes & endpoints

### Question 1 : La gestion des ports réseau
Pourquoi est-il crucial de fermer systématiquement les ports réseau inutilisés (ex. RDP 3389, SSH 22, SMB 445) sur un serveur ?
* A. Pour réduire la consommation électrique de la carte réseau.
* B. Pour minimiser la surface d'attaque en fermant les points d'entrée potentiels exploitables par un malware ou un pirate.
* C. Pour accélérer la vitesse de connexion internet des ordinateurs du réseau.
* **Réponse correcte : B**
* *Explication* : Chaque port ouvert est un service à l'écoute. Si le service a une vulnérabilité ou des identifiants faibles, il devient une porte d'entrée pour les pirates. Fermer les ports non indispensables réduit la surface d'attaque.

### Question 2 : Le rôle d'un pare-feu local (Host-based Firewall)
Quelle est l'utilité d'activer le pare-feu Windows ou iptables sur chaque poste de travail, en plus du pare-feu physique à la frontière d'Internet ?
* A. Bloquer les virus présents sur les clés USB insérées localement.
* B. Empêcher la propagation latérale d'un attaquant ou d'un ver informatique au sein du même réseau local.
* C. Rendre obligatoire la double authentification de l'utilisateur.
* **Réponse correcte : B**
* *Explication* : Si le pare-feu périmétrique protège de l'extérieur, il n'empêche pas une machine compromise d'attaquer ses voisines sur le LAN. Les pare-feux locaux bloquent les flux illégitimes entre machines internes (mouvements latéraux).

---

## Session B09 : Gestion des identités et des accès (IAM)

### Question 1 : Le contrôle d'accès basé sur les rôles (RBAC)
Quelle règle illustre la mise en œuvre d'un modèle RBAC ?
* A. Donner les accès d'un dossier confidentiel à un salarié sur décision individuelle du responsable.
* B. Assigner des droits d'accès à des rôles (ex. "Comptable", "RH") et affecter les salariés à ces rôles selon leur fonction officielle.
* C. Exiger un mot de passe de 18 caractères pour tous les collaborateurs de l'entreprise.
* **Réponse correcte : B**
* *Explication* : Le RBAC (Role-Based Access Control) facilite la gestion des privilèges en associant les accès aux fonctions métier (rôles) plutôt qu'aux individus, garantissant la cohérence et simplifiant les arrivées/départs de salariés.

### Question 2 : La compromission d'un compte de facturation
Quelle mesure technique immédiate et efficace permet de neutraliser la compromission par hameçonnage d'un compte cloud de messagerie commerciale ?
* A. Désinstaller le logiciel de messagerie de l'ordinateur portable du commercial.
* B. Révoquer toutes les sessions actives du compte et activer l'authentification multifacteur (MFA).
* C. Installer un nouveau pare-feu réseau à la périphérie du siège social.
* **Réponse correcte : B**
* *Explication* : Si le mot de passe est volé par phishing, le pirate peut se connecter de n'importe où. Fermer les sessions actives et forcer le MFA bloque l'accès car le pirate ne dispose pas du second facteur de possession (le smartphone de la victime).

---

## Session B10 : Cryptographie essentielle

### Question 1 : Chiffrement symétrique vs asymétrique
Quelle est la contrainte logistique majeure du chiffrement symétrique (comme AES-256) lors de transferts d'informations entre plusieurs partenaires distants ?
* A. Il exige des serveurs surpuissants en raison de sa lenteur de calcul.
* B. Il nécessite que les deux correspondants partagent la même clé secrète en toute sécurité avant d'échanger des messages.
* C. Il ne permet pas de chiffrer des fichiers volumineux.
* **Réponse correcte : B**
* *Explication* : En chiffrement symétrique, la même clé sert à chiffrer et déchiffrer. Le défi est donc de transmettre cette clé secrète au destinataire de manière sécurisée (problème du canal d'échange des clés), ce que résout le chiffrement asymétrique.

### Question 2 : Le rôle du hachage dans le stockage des mots de passe
Pourquoi stocke-t-on les mots de passe des utilisateurs sous forme de empreintes de hachage (ex. bcrypt, Argon2) avec du "sel" (salt) en base de données ?
* A. Pour que l'application puisse décrypter les mots de passe et les envoyer par e-mail en cas de perte.
* B. Pour empêcher un administrateur malveillant ou un pirate ayant volé la base de données de lire les mots de passe en clair.
* C. Pour accélérer la vitesse de connexion lors de la saisie des identifiants.
* **Réponse correcte : B**
* *Explication* : Le hachage est une fonction à sens unique : on ne peut pas retrouver le mot de passe d'origine à partir du hash. Le "sel" évite que deux utilisateurs avec le même mot de passe aient le même hash et bloque les attaques par tables de correspondance (Rainbow tables).

---

## Session B11 : Sécurité du cloud

### Question 1 : Le modèle de Responsabilité Partagée en SaaS
Dans un modèle d'hébergement SaaS (Software as a Service) comme Microsoft 365, quelle responsabilité incombe **au client** (l'entreprise utilisatrice) ?
* A. Assurer la sécurité physique des centres de données accueillant les serveurs.
* B. Mettre à jour les serveurs d'infrastructure sous-jacents contre les vulnérabilités de l'OS.
* C. Gérer les identités des utilisateurs, les accès et configurer la sécurité des données stockées.
* **Réponse correcte : C**
* *Explication* : En SaaS, le fournisseur cloud gère l'infrastructure, le réseau et l'application. Le client reste entièrement responsable de la configuration de ses utilisateurs (identités, MFA) et des droits d'accès à ses fichiers.

### Question 2 : La menace du "Shadow IT"
Pourquoi le "Shadow IT" (utilisation d'applications cloud personnelles non validées par l'informatique) représente-t-il un danger pour l'entreprise ?
* A. Parce qu'il augmente la facture énergétique du réseau local de l'entreprise.
* B. Parce que des données confidentielles de l'entreprise peuvent se retrouver stockées sur des plateformes externes non sécurisées et non conformes au RGPD.
* C. Parce qu'il ralentit le fonctionnement général de la suite bureautique officielle.
* **Réponse correcte : B**
* *Explication* : Si les employés stockent des fichiers sur leurs comptes Dropbox ou Google Drive personnels pour travailler à distance, l'entreprise perd la visibilité et le contrôle sur ses données, augmentant massivement les risques de fuites ou de non-conformité légale.

---

## Session B12 : Sécurité & confidentialité des données

### Question 1 : Chiffrement des données "At rest" (au repos)
Quel outil permet de protéger la confidentialité des données stockées sur le disque dur d'un ordinateur portable professionnel si celui-ci est volé dans un train ?
* A. Un antivirus de nouvelle génération (EDR).
* B. Un logiciel de chiffrement complet du disque (ex. BitLocker ou FileVault).
* C. Un filtre de confidentialité posé sur l'écran physique de l'ordinateur.
* **Réponse correcte : B**
* *Explication* : Si l'ordinateur est éteint et volé, le pirate peut extraire le disque dur et le brancher sur une autre machine pour lire les données. BitLocker chiffre l'intégralité du volume : sans la clé d'accès ou la puce TPM, les fichiers restent illisibles.

### Question 2 : Anonymisation vs Pseudonymisation
Quelle est la différence légale et technique fondamentale entre l'anonymisation et la pseudonymisation selon le RGPD ?
* A. L'anonymisation est réversible tandis que la pseudonymisation est définitive.
* B. L'anonymisation est irréversible (on ne peut plus remonter à l'individu), alors que la pseudonymisation permet de réidentifier l'individu en utilisant des informations complémentaires protégées.
* C. Seule la pseudonymisation est reconnue comme une mesure de protection valide par les tribunaux.
* **Réponse correcte : B**
* *Explication* : La pseudonymisation (ex. remplacer les noms par un identifiant aléatoire dans une base, avec une table de correspondance isolée) reste une donnée personnelle. L'anonymisation brise définitivement le lien (ex. agrégation statistique) et exclut les données du champ d'application du RGPD.

---

## Session B13 : Gouvernance & cadres de sécurité

### Question 1 : Le rôle de l'ISO 27001
Quelle est la finalité principale de la norme internationale ISO/IEC 27001 ?
* A. Proposer des configurations techniques précises pour les pare-feu de marque Cisco.
* B. Définir les exigences pour mettre en place, maintenir et améliorer un Système de Gestion de la Sécurité de l'Information (SMSI).
* C. Rendre obligatoire le licenciement des administrateurs système en cas d'attaque réussie.
* **Réponse correcte : B**
* *Explication* : L'ISO 27001 est une norme organisationnelle. Elle aide les structures à concevoir un cadre de gouvernance de la sécurité (SMSI) basé sur une démarche d'amélioration continue (Roue de Deming).

### Question 2 : Le concept d'hygiène informatique selon l'ANSSI
Dans le cadre de l'hygiène informatique définie par l'ANSSI, quelle mesure organisationnelle est jugée prioritaire ?
* A. Publier régulièrement des vidéos humoristiques sur les failles logicielles.
* B. Établir et maintenir un inventaire complet et à jour de tous les matériels et logiciels connectés au réseau de l'entreprise.
* C. Acheter uniquement du matériel informatique fabriqué en France.
* **Réponse correcte : B**
* *Explication* : On ne peut pas protéger ce que l'on ignore posséder. L'inventaire de parc (matériel et logiciel) est la règle numéro 1 de l'hygiène cyber de l'ANSSI pour savoir quels systèmes corriger et surveiller.

---

## Session B14 : Gestion des risques

### Question 1 : Le calcul de la criticité du risque
Dans une méthode d'analyse de risques (comme EBIOS RM), comment calcule-t-on le niveau de criticité brute d'un scénario de risque ?
* A. Criticité = Nombre de serveurs concernés + Coût de la licence antivirus.
* B. Criticité = Vraisemblance (Probabilité d'occurrence) x Gravité (Intensité de l'impact).
* C. Criticité = Durée de la formation des salariés / Nombre d'attaques subies par an.
* **Réponse correcte : B**
* *Explication* : La formule universelle d'évaluation du risque croise la vraisemblance (chance que la menace se réalise) et l'impact (dégâts financiers, légaux, réputationnels subis).

### Question 2 : Le transfert du risque cyber
Quelle action correspond à une stratégie de **Transfert** du risque cyber ?
* A. Souscrire un contrat d'assurance cyber spécifique auprès d'une compagnie d'assurance.
* B. Former l'ensemble des logisticiens à ne pas ouvrir les pièces jointes douteuses.
* C. Migrer tous les serveurs locaux vers un hébergeur Cloud public.
* **Réponse correcte : A**
* *Explication* : Transférer le risque consiste à en faire porter l'impact financier ou opérationnel à un tiers (une assurance cyber ou un sous-traitant engagé contractuellement). Former réduit le risque, et migrer modifie la nature du risque mais ne le transfère pas entièrement.

---

## Session B15 : Conformité & réglementations vie privée

### Question 1 : Délai de notification CNIL
Sous quel délai légal maximal une entreprise doit-elle notifier la CNIL après avoir constaté une violation de données personnelles (fuite d'informations clients) ?
* A. 24 heures.
* B. 72 heures.
* C. 30 jours.
* **Réponse correcte : B**
* *Explication* : Le RGPD impose une obligation de notification à l'autorité de contrôle (la CNIL en France) sans retard injustifié et, si possible, dans les **72 heures** au plus tard après avoir pris connaissance de la violation.

### Question 2 : L'obligation d'information des personnes concernées
Dans quel cas une violation de données personnelles impose-t-elle de notifier individuellement les clients affectés, en plus de la CNIL ?
* A. Lorsque la fuite est susceptible d'engendrer un risque élevé pour les droits et libertés des personnes physiques (ex. vol de données bancaires ou médicales).
* B. Uniquement si l'entreprise dispose du budget nécessaire pour envoyer des courriers postaux.
* C. Si la violation concerne moins de 10 personnes.
* **Réponse correcte : A**
* *Explication* : La notification individuelle aux victimes est obligatoire si l'incident présente un risque élevé (ex. usurpation d'identité, discrimination, préjudice financier). Si les données volées étaient chiffrées de manière forte (BitLocker, AES-256) et illisibles pour l'attaquant, la notification individuelle peut ne pas être requise.

---

## Session B16 : Centre des opérations de sécurité (SOC) & supervision

### Question 1 : Le rôle des analystes SOC Niveaux 1 et 2
Dans l'organisation d'un SOC, quelle est la mission principale d'un analyste de Niveau 1 ?
* A. Négocier les tarifs de rançon avec les pirates lors d'une crise.
* B. Effectuer le tri initial des alertes de sécurité générées par le SIEM, écarter les faux positifs et escalader les menaces réelles au Niveau 2.
* C. Réécrire le code source des applications web compromises de l'entreprise.
* **Réponse correcte : B**
* *Explication* : L'analyste de Niveau 1 surveille la console d'alertes en temps réel, qualifie les alertes et passe le relais (escalade) aux analystes de Niveau 2 pour une investigation plus poussée et la remédiation en cas d'attaque confirmée.

### Question 2 : Le concept de faux positif
Qu'est-ce qu'un "faux positif" en supervision de sécurité ?
* A. Une alerte déclenchée par un comportement légitime mais identifié à tort comme suspect par l'outil de détection.
* B. Une cyberattaque réussie qui n'a généré aucune alerte dans le SIEM.
* C. Un virus détecté et supprimé sans intervention humaine.
* **Réponse correcte : A**
* *Explication* : Un faux positif est une fausse alarme (ex. un administrateur légitime qui lance un outil de test sur le réseau, détecté comme une intrusion). Les faux négatifs (réponse B) représentent le cas inverse où une attaque passe inaperçue.

---

## Session B17 : Outils SIEM & Analyse de logs

### Question 1 : Les 3 composants fondamentaux d'une log
Quelles sont les trois informations minimales et indispensables que doit contenir une ligne de log pour être exploitable lors d'une investigation de sécurité ?
* A. L'adresse e-mail de l'utilisateur, son pays d'origine et son navigateur internet.
* B. Un horodatage précis (Timestamp), la source de l'événement (IP ou nom de machine) et l'action ou événement réalisé.
* C. Le nom de l'éditeur du logiciel, la taille du fichier log et le type de processeur du serveur.
* **Réponse correcte : B**
* *Explication* : Pour reconstituer une attaque, un analyste a impérativement besoin de savoir **quand** l'événement s'est produit (Timestamp), **qui** ou d'où cela provient (Source) et **ce qui** s'est passé (Action/Événement).

### Question 2 : Détection d'une injection SQL
Quelle requête HTTP suspecte dans un fichier de logs Apache révèle une tentative d'injection SQL ?
* A. `GET /index.php?id=12`
* B. `GET /images/logo.png`
* C. `GET /product.php?id=1%20OR%201=1`
* **Réponse correcte : C**
* *Explication* : La chaîne `%20OR%201=1` (décodée en `OR 1=1`) est une signature classique d'injection SQL visant à forcer la base de données à renvoyer des informations confidentielles en rendant la condition toujours vraie.

---

## Session B18 : Introduction à la réponse aux incidents

### Question 1 : Confinement vs Éradication
Dans les phases du NIST SP 800-61 r2, quelle action correspond à la phase de **Confinement** ?
* A. Supprimer les clés de registre créées par un malware.
* B. Isoler du réseau la machine compromise en débranchant son câble Ethernet ou en la plaçant dans un VLAN d'isolation.
* C. Restaurer la dernière sauvegarde propre de la base de données.
* **Réponse correcte : B**
* *Explication* : Le confinement vise à limiter la propagation (ex. débrancher la machine). L'éradication consiste à nettoyer la menace (supprimer le malware, réponse A). La restauration de la sauvegarde (réponse C) correspond à la phase de Recouvrement (Recovery).

### Question 2 : Règle d'or face à un ransomware en cours d'exécution
Quelle est la consigne critique à donner à un utilisateur découvrant un message de ransomware sur son écran de travail ?
* A. Éteindre immédiatement l'ordinateur en restant appuyé sur le bouton d'alimentation.
* B. Ne pas éteindre l'ordinateur, mais débrancher immédiatement le câble réseau ou couper le Wi-Fi, puis alerter l'équipe de sécurité.
* C. Payer immédiatement la rançon demandée avec sa carte de crédit personnelle.
* **Réponse correcte : B**
* *Explication* : Éteindre la machine détruit les preuves volatiles dans la RAM (clés de chiffrement du ransomware en cours, processus actifs). La consigne est d'isoler la machine (couper le réseau) pour bloquer la propagation et préserver la mémoire vive (RAM) pour les enquêteurs.

---

## Session B19 : Simulation de crise cyber (Tabletop exercise)

### Question 1 : Le rôle du DPO/Juriste en cellule de crise
Pourquoi le responsable juridique ou DPO (Data Protection Officer) doit-il faire partie de la cellule de crise cyber dès les premières heures de l'attaque ?
* A. Pour configurer les règles de filtrage sur le pare-feu de l'entreprise.
* B. Pour piloter la stratégie légale, anticiper les sanctions financières et préparer la déclaration CNIL obligatoire sous 72h.
* C. Pour rédiger les messages internes destinés à rassurer techniquement les administrateurs système.
* **Réponse correcte : B**
* *Explication* : Le DPO ou juriste veille au respect de la loi. En cas de vol de données personnelles, il valide le timing et le texte de la déclaration légale obligatoire à la CNIL sous 72h afin d'éviter de lourdes sanctions de non-conformité.

### Question 2 : La communication de crise externe
Quelle est l'attitude recommandée pour la communication externe d'une entreprise victime d'une cyberattaque par ransomware ?
* A. Nier l'attaque auprès de la presse pour ne pas abîmer l'image de l'entreprise.
* B. Publier un communiqué factuel confirmant l'attaque, indiquant l'absence de fuite bancaire (si vérifié), expliquant les mesures de sécurité déployées et s'excusant pour les perturbations.
* C. Divulguer publiquement les adresses IP et les vulnérabilités exploitées par les pirates pour prouver sa bonne foi.
* **Réponse correcte : B**
* *Explication* : La transparence contrôlée rassure les clients et partenaires. Mentir ou cacher l'incident (réponse A) aggrave le scandale réputationnel en cas de fuite ultérieure. Donner des détails techniques sensibles (réponse C) fragilise l'entreprise face à d'autres attaquants.

---

## Session B20 : Soutenance finale & Clôture

### Question 1 : Traduire un risque cyber pour la Direction
Comment devez-vous présenter un risque lié à l'absence de mot de passe complexe sur un serveur de fichiers à la Directrice Générale de MedDistri ?
* A. *"Le port RDP 3389 ouvert sur Internet risque de subir des attaques par dictionnaire exploitant le protocole TLS 1.2."*
* B. *"L'absence de mots de passe robustes expose l'entreprise au chiffrement de ses contrats commerciaux par un pirate, menaçant l'activité de l'entrepôt et risquant d'entraîner une perte de chiffre d'affaires importante."*
* C. *"L'absence de stratégie de complexité empêche le processeur du serveur de fonctionner à son niveau de performance maximal."*
* **Réponse correcte : B**
* *Explication* : Pour convaincre un décisionnaire non technique, il faut traduire les termes réseau ou logiciels complexes en impacts concrets pour l'activité (perte d'exploitation, interruption logistique, coûts).

### Question 2 : Le maintien de la sécurité post-formation
Qu'implique une démarche de veille technologique régulière en cybersécurité ?
* A. Racheter de nouveaux ordinateurs portables tous les six mois.
* B. Consulter régulièrement les alertes de sécurité des éditeurs de logiciels et les bulletins du CERT-FR pour appliquer les correctifs sur les vulnérabilités nouvellement découvertes (CVE).
* C. Interdire définitivement l'accès à Internet à tous les salariés de l'entreprise.
* **Réponse correcte : B**
* *Explication* : La sécurité n'est pas un état figé mais un processus continu. Consulter les CVE et les alertes du CERT-FR permet de patcher les failles critiques avant qu'elles ne soient exploitées par des pirates de manière automatisée.
