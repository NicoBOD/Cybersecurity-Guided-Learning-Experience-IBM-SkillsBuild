# Banque de Quiz — Parcours A (8 sessions)
Parcours : A 8 sessions  |  Module : Validation des connaissances  |  Format : Banque de QCM résolus

> **Usage** : ces questions alimentent les quiz d'auto-évaluation self-paced et servent de réserve au mentor (sondages supplémentaires, séances de révision). Chaque question est autonome : scénario ou fait précis, une seule bonne réponse, explication qui enseigne. Les questions sont alignées sur les supports de cours enrichis (chiffres sourcés et études de cas compris).

---

## Session 01 : Découverte de la cybersécurité & paysage des menaces

### Question 1 : Le pilier de la Confidentialité
Quelle technologie permet de garantir le pilier de la **Confidentialité** au sein de la triade C-I-D ?

* A. La duplication des serveurs de base de données.
* B. Le chiffrement des données de santé stockées.
* C. La signature numérique des e-mails.
* **Réponse correcte : B**
* *Explication* : Le chiffrement transforme l'information en texte illisible pour toute personne ne possédant pas la clé d'accès. Cela garantit le secret (la Confidentialité). La réponse A garantit la Disponibilité et la C garantit l'Intégrité et l'authenticité.

### Question 2 : Profil d'attaquant
Quel groupe d'attaquants est principalement motivé par des gains financiers rapides à travers des campagnes massives de ransomwares ?

* A. Les hacktivistes.
* B. Les États-nations.
* C. Les cybercriminels.
* **Réponse correcte : C**
* *Explication* : Les cybercriminels agissent pour l'argent (rançons, vol de cartes de crédit). Les hacktivistes sont motivés par l'idéologie ou la politique, et les États-nations par l'espionnage, le renseignement ou le sabotage géopolitique.

### Question 3 : L'acronyme CIA
Dans l'acronyme anglais « CIA » de la triade de sécurité, que désigne la lettre **A** ?

* A. *Authentication* — l'authentification des utilisateurs.
* B. *Availability* — la Disponibilité des systèmes et des données.
* C. *Authorization* — l'autorisation d'accès aux ressources.
* **Réponse correcte : B**
* *Explication* : L'acronyme vient de l'anglais *Confidentiality, Integrity, Availability*. En français, le troisième pilier est la Disponibilité — d'où les initiales françaises C-I-D utilisées dans le cours. L'authentification et l'autorisation sont des mécanismes de contrôle d'accès, pas des piliers de la triade.

### Question 4 : Vulnérabilité, menace ou risque ?
Un serveur de votre entreprise n'a reçu aucune mise à jour depuis deux ans. En vocabulaire de sécurité, ce serveur constitue...

* A. Une menace.
* B. Une vulnérabilité.
* C. Un risque.
* **Réponse correcte : B**
* *Explication* : La vulnérabilité est la faiblesse (la « porte ouverte ») ; la menace est l'acteur qui peut l'exploiter (le « cambrioleur ») ; le risque est la combinaison des deux avec l'impact (Risque = Menace × Vulnérabilité × Impact). Le serveur obsolète est donc la porte ouverte.

### Question 5 : La formule du risque
Deux machines présentent la même faille logicielle : un serveur de paie exposé sur Internet et un vieil ordinateur isolé, sans données, dans la salle de pause. Pourquoi leurs niveaux de risque diffèrent-ils ?

* A. Parce que la menace est plus faible sur le serveur de paie.
* B. Parce que l'impact et l'exposition diffèrent : même vulnérabilité, mais conséquences et probabilité d'exploitation sans commune mesure.
* C. Ils ne diffèrent pas : même vulnérabilité, même risque.
* **Réponse correcte : B**
* *Explication* : Le risque se calcule en combinant menace, vulnérabilité ET impact. Le serveur de paie exposé cumule un impact élevé (salaires, données personnelles) et une forte exposition ; l'ordinateur de la salle de pause n'offre presque rien à voler. C'est pourquoi toute démarche de sécurité commence par « qu'est-ce qui est critique pour moi ? ».

### Question 6 : La double extorsion du CHSF
Lors de l'attaque de l'hôpital de Corbeil-Essonnes (LockBit, 2022), les systèmes ont d'abord été chiffrés, puis environ 11 Go de données ont été publiés après le refus de payer. Quels piliers de la triade ont été successivement touchés ?

* A. La Disponibilité, puis la Confidentialité.
* B. L'Intégrité, puis la Disponibilité.
* C. Uniquement la Confidentialité.
* **Réponse correcte : A**
* *Explication* : Le chiffrement a rendu les systèmes inaccessibles (Disponibilité), forçant le retour au papier ; la publication des données volées a ensuite violé la Confidentialité. C'est le mécanisme de la « double extorsion », désormais standard chez les groupes de rançongiciel.

### Question 7 : L'effet différé d'une fuite de données
Lors de la fuite France Travail (2024, potentiellement 43 millions de personnes), ni mots de passe ni données bancaires n'ont été volés. Pourquoi le danger reste-t-il considérable ?

* A. Les données d'identité volées permettent des campagnes d'hameçonnage crédibles et des usurpations d'identité pendant des années.
* B. Il n'y a en réalité aucun danger sans mot de passe volé.
* C. Le seul risque est la revente publicitaire des adresses e-mail.
* **Réponse correcte : A**
* *Explication* : Identité, numéro de sécurité sociale et coordonnées suffisent à fabriquer des messages « officiels » très convaincants. Les données volées aujourd'hui alimentent les attaques de demain — c'est l'effet différé d'une violation de Confidentialité, même « silencieuse ».

### Question 8 : Le facteur humain
Selon le rapport *Data Breach Investigations Report* de Verizon (2025), dans quelle proportion des violations de données le facteur humain (erreur, manipulation, identifiants volés) est-il impliqué ?

* A. Environ 15 %.
* B. Environ 60 %.
* C. Environ 95 %.
* **Réponse correcte : B**
* *Explication* : Environ six violations sur dix impliquent le facteur humain. C'est le chiffre qui justifie la sensibilisation : l'humain est à la fois le premier vecteur d'attaque et la première ligne de défense.

### Question 9 : La découverte d'une faille
Vous découvrez que le serveur de votre PME expose un accès de bureau à distance protégé par un mot de passe faible. Quelle est la bonne posture ?

* A. Tester vous-même le mot de passe pour vérifier la gravité avant d'alerter.
* B. Prévenir immédiatement le responsable informatique ou la direction, sans rien tester.
* C. Ne rien dire : la sécurité n'est pas votre rôle.
* **Réponse correcte : B**
* *Explication* : Signaler, jamais exploiter : tester un accès sans autorisation écrite est un délit (art. 323-1 du Code pénal), même avec de bonnes intentions. Et se taire laisse la porte ouverte — la sécurité est l'affaire de tous.

### Question 10 : Sécurité offensive
Qu'est-ce qui distingue légalement un test d'intrusion (pentest) d'une attaque informatique ?

* A. Le pentest utilise des outils moins puissants que les attaquants.
* B. Le pentest est réalisé avec une autorisation écrite préalable du propriétaire du système, définissant le périmètre.
* C. Le pentest est réalisé uniquement en dehors des heures de bureau.
* **Réponse correcte : B**
* *Explication* : Les techniques sont les mêmes ; seule l'autorisation écrite (ordre de mission, périmètre, période) rend l'exercice légal. Sans elle, les mêmes gestes constituent une atteinte à un système de traitement automatisé de données.

---

## Session 02 : Menaces, attaques & ingénierie sociale

### Question 1 : Hameçonnage par téléphone
Quel terme désigne une attaque d'ingénierie sociale menée spécifiquement par téléphone ?

* A. Le Spear-phishing.
* B. Le Smishing.
* C. Le Vishing.
* **Réponse correcte : C**
* *Explication* : Le *Vishing* (Hameçonnage vocal / Voice Phishing) utilise le téléphone pour usurper l'identité de conseillers bancaires ou de techniciens. Le *Smishing* utilise les SMS, et le *Spear-phishing* désigne des e-mails d'hameçonnage ultra-ciblés.

### Question 2 : Le Cheval de Troie
Quelle est la caractéristique d'un malware de type "Cheval de Troie" (Trojan) ?

* A. Il se propage de machine en machine de manière totalement autonome.
* B. Il se cache à l'intérieur d'un programme légitime pour infecter la machine.
* C. Il chiffre le disque dur et réclame une rançon sous 48h.
* **Réponse correcte : B**
* *Explication* : Comme dans le mythe grec, le cheval de Troie se fait passer pour un logiciel utile (ex. utilitaire de nettoyage gratuit) mais contient des fonctions cachées malveillantes. Un malware qui chiffre est un ransomware, et un malware autonome est un ver.

### Question 3 : La Cyber Kill Chain
Dans la méthodologie de la Cyber Kill Chain, à quelle étape correspond l'envoi d'un e-mail de phishing à une cible ?

* A. L'Armement.
* B. La Livraison.
* C. L'Exploitation.
* **Réponse correcte : B**
* *Explication* : La Livraison est l'acheminement de la charge malveillante vers la victime (e-mail, clé USB, téléchargement). L'Armement est la fabrication préalable du piège, et l'Exploitation est le déclenchement du code sur la machine. Briser un seul maillon suffit à stopper l'attaque.

### Question 4 : Le levier psychologique n°1
« Votre compte sera suspendu dans 2 heures », « payez avant midi », « répondez immédiatement » : quel levier de manipulation ces formulations exploitent-elles ?

* A. La curiosité.
* B. L'urgence, pour court-circuiter la réflexion rationnelle.
* C. La confiance.
* **Réponse correcte : B**
* *Explication* : L'urgence est le signal d'alarme n°1 de l'ingénierie sociale : elle vise à faire agir avant de faire réfléchir. Une organisation légitime laisse toujours le temps de vérifier — c'est précisément ce temps que l'attaquant veut supprimer.

### Question 5 : Le typosquatting
Un e-mail provient de `service-clients@netf1ix-securite.com`. Quelle technique reconnaissez-vous ?

* A. Le typosquatting : un domaine imitant une marque à un caractère près pour tromper l'œil.
* B. Le SIM swapping : le détournement d'une ligne mobile.
* C. Le déni de service : la saturation d'un serveur.
* **Réponse correcte : A**
* *Explication* : Le « 1 » remplace le « l » de netflix — une substitution presque invisible en lecture rapide. Le réflexe : lire l'adresse de l'expéditeur caractère par caractère et survoler les liens sans cliquer pour voir leur destination réelle.

### Question 6 : L'affaire Pathé
Lors de l'arnaque au président Pathé (2018, ~19,2 M€), la demande de virement exigeait le secret absolu au nom d'une « acquisition confidentielle ». Pourquoi cette exigence de secret est-elle un signal d'alarme majeur ?

* A. Parce que les acquisitions d'entreprises sont toujours publiques.
* B. Parce que le secret neutralise la double validation : il interdit précisément la vérification qui ferait échouer la fraude.
* C. Parce que le secret est illégal en droit des affaires.
* **Réponse correcte : B**
* *Explication* : Autorité + urgence + secret est la combinaison signature de la fraude au président : le secret prive la victime du réflexe salvateur (vérifier par un autre canal). Quand une demande interdit la vérification, c'est le moment d'exiger la vérification.

### Question 7 : Le deepfake d'Arup
En 2024, un employé du cabinet Arup a viré ~25 M$ après une visioconférence où dirigeants et collègues étaient des deepfakes. Quelle parade aurait cassé ce scénario ?

* A. Demander aux participants de la visio de montrer leur badge à la caméra.
* B. Recontacter soi-même le dirigeant via un canal indépendant connu (numéro interne) avant tout virement.
* C. Exiger un e-mail de confirmation en réponse à l'invitation de la visioconférence.
* **Réponse correcte : B**
* *Explication* : « Je l'ai vu et entendu » ne prouve plus l'identité à l'ère des deepfakes, et répondre au canal fourni par l'attaquant (l'e-mail d'invitation) revient à demander confirmation... à l'attaquant. Seule une vérification initiée par soi, sur un canal indépendant, reste fiable.

### Question 8 : La minute fatale
Selon le rapport Verizon DBIR 2024, combien de temps s'écoule en médiane entre l'ouverture d'un e-mail de phishing et la saisie des données par la victime ?

* A. Moins d'une minute.
* B. Environ une heure.
* C. Environ une journée.
* **Réponse correcte : A**
* *Explication* : Environ 21 secondes pour cliquer et 28 secondes de plus pour saisir ses identifiants. La leçon : la réflexion après coup ne sauve pas — c'est le réflexe avant le clic (et le signalement immédiat après une erreur) qui protège.

### Question 9 : Fautes d'orthographe ≠ fraude
Un message interne annonce une maintenance, contient deux fautes d'orthographe, provient du vrai domaine de l'entreprise, sans lien ni demande sensible. Comment le qualifier ?

* A. Phishing certain : les fautes d'orthographe sont une preuve de fraude.
* B. Message légitime mais maladroit : c'est la demande (sensible ou non) qui compte, pas la forme.
* C. Impossible à qualifier sans analyse forensique complète.
* **Réponse correcte : B**
* *Explication* : Les indices de forme (fautes, maladresses) ne suffisent plus dans les deux sens : l'IA générative écrit des fraudes impeccables, et les collègues pressés écrivent des messages légitimes maladroits. Les indices de fond priment : demande-t-on une action sensible ? Le lien mène-t-il au bon domaine ?

### Question 10 : Le réflexe smishing
Vous recevez un SMS frauduleux de « livraison de colis » avec un lien de paiement. Outre ne pas cliquer, quel est le geste citoyen recommandé en France ?

* A. Répondre « STOP » au SMS.
* B. Transférer le SMS au 33700, la plateforme nationale de signalement.
* C. Rappeler le numéro pour vérifier l'identité de l'expéditeur.
* **Réponse correcte : B**
* *Explication* : Le 33700 alimente le blocage des numéros et liens frauduleux pour tous. Répondre « STOP » ou rappeler confirme au contraire à l'attaquant que votre numéro est actif — c'est le signalement, pas le dialogue, qui protège.

---

## Session 03 : Sécurité des systèmes & réseaux

### Question 1 : HTTP vs HTTPS
Vous saisissez un mot de passe sur un site web en HTTP (sans le cadenas). Quel est le risque immédiat ?

* A. Aucun : le mot de passe est toujours chiffré par le navigateur.
* B. Toute personne en position d'écoute sur le réseau (Wi-Fi public par exemple) peut lire le mot de passe en clair.
* C. Le site sera plus lent à charger.
* **Réponse correcte : B**
* *Explication* : HTTP transmet tout en clair, comme une carte postale lisible par tous les intermédiaires. HTTPS (TLS) chiffre les échanges : même interceptées, les données sont illisibles. C'est le sniffing (écoute passive) que le chiffrement neutralise.

### Question 2 : Le principe fondateur du pare-feu
Quelle règle de base applique un pare-feu correctement configuré ?

* A. Tout autoriser par défaut et bloquer les adresses IP malveillantes connues.
* B. Tout interdire par défaut et n'autoriser que les flux explicitement nécessaires (*Default Deny*).
* C. Autoriser tout le trafic des employés et bloquer tout le trafic externe.
* **Réponse correcte : B**
* *Explication* : On ne peut pas énumérer le mal (la liste des menaces est infinie et change chaque jour) ; on autorise donc le nécessaire et on bloque tout le reste. La dernière règle d'une table de filtrage bien conçue est toujours « tout bloquer ».

### Question 3 : L'emplacement du serveur web public
Où doit être placé le serveur web public d'une entreprise ?

* A. Sur le réseau local interne (LAN), avec les postes de travail.
* B. Dans une zone démilitarisée (DMZ), séparée du réseau interne par un pare-feu.
* C. Directement sur Internet, sans protection, pour de meilleures performances.
* **Réponse correcte : B**
* *Explication* : La DMZ est un sas : accessible depuis Internet, mais interdite d'initier des connexions vers le réseau interne. Si le serveur web est compromis, l'attaquant reste confiné dans le sas au lieu d'atteindre les données de l'entreprise.

### Question 4 : L'ordre des règles
Dans une table de filtrage, la règle « Internet → TOUT : BLOQUER » est déplacée par erreur AU-DESSUS de la règle « Internet → Serveur Web : AUTORISER (443) ». Que se passe-t-il ?

* A. Rien : l'ordre des règles n'a pas d'importance.
* B. Le site web public devient inaccessible : la règle de blocage, lue en premier, capte tout le trafic entrant.
* C. Le serveur web devient accessible sur tous les ports.
* **Réponse correcte : B**
* *Explication* : Un pare-feu lit ses règles de haut en bas et applique la première qui correspond. L'ordre des règles est donc aussi important que leur contenu — une simple inversion peut paralyser un service ou, à l'inverse, ouvrir une brèche.

### Question 5 : Le déplacement latéral
Que désigne le « déplacement latéral » (*lateral movement*) dans une intrusion ?

* A. La progression de l'attaquant, de machine en machine, à l'intérieur du réseau compromis.
* B. Le transfert de l'attaque d'une entreprise vers sa concurrente.
* C. Le changement d'adresse IP de l'attaquant pour échapper à la détection.
* **Réponse correcte : A**
* *Explication* : Une fois entré (souvent par un poste peu sensible), l'attaquant « rebondit » vers les actifs de valeur. La segmentation réseau (VLAN, DMZ, pare-feu internes) vise précisément à bloquer cette progression — un réseau plat est une maison sans portes intérieures.

### Question 6 : La leçon de Target
Lors de la violation Target (2013, ~40 millions de cartes bancaires), les attaquants sont entrés avec les identifiants d'un prestataire de chauffage-climatisation, puis ont atteint les caisses des magasins. Quelle défense a fait défaut ?

* A. L'antivirus des postes de travail.
* B. La segmentation réseau : rien ne cloisonnait l'accès du prestataire des systèmes de paiement.
* C. Le chiffrement du site web de Target.
* **Réponse correcte : B**
* *Explication* : L'accès tiers mal cloisonné a permis un déplacement latéral jusqu'aux systèmes d'encaissement. Avec un pare-feu interne interdisant à la zone « prestataires » d'atteindre la zone « paiement », l'intrusion serait restée confinée — la technologie existait, l'architecture a manqué.

### Question 7 : Le botnet Mirai
Comment le botnet Mirai (2016) a-t-il enrôlé des centaines de milliers d'objets connectés pour ses attaques DDoS record (~1 Tbit/s) ?

* A. En exploitant une faille inconnue des processeurs.
* B. En testant simplement les mots de passe d'usine (admin/admin, root/12345) sur les équipements exposés à Internet.
* C. En infectant les mises à jour officielles des fabricants.
* **Réponse correcte : B**
* *Explication* : Aucune prouesse technique : des caméras et routeurs exposés avec leurs mots de passe par défaut jamais changés. Leçon double : tout équipement branché est scanné en quelques minutes, et le changement des mots de passe d'usine est un geste de sécurité fondamental.

### Question 8 : Les limites du VPN
Le VPN de votre entreprise empêche-t-il votre ordinateur de télécharger un malware ?

* A. Oui : le tunnel chiffré bloque les logiciels malveillants.
* B. Non : le VPN protège le transport des données, pas leur contenu — un malware voyage très bien chiffré.
* C. Oui, mais uniquement les malwares connus des antivirus.
* **Réponse correcte : B**
* *Explication* : Le tunnel livre ce qu'on y fait passer, de façon confidentielle — y compris un fichier piégé. Le VPN complète l'antivirus et la vigilance, il ne les remplace pas. Autre limite : la passerelle VPN elle-même doit être maintenue à jour.

### Question 9 : Le cadenas trompeur
Un site affiche le cadenas HTTPS dans la barre d'adresse. Peut-on en conclure qu'il est digne de confiance ?

* A. Oui : le cadenas certifie l'honnêteté du site.
* B. Non : le cadenas garantit que la connexion est chiffrée, pas que le site est légitime — un site de phishing obtient un certificat gratuit en quelques minutes.
* C. Oui, si le cadenas est vert.
* **Réponse correcte : B**
* *Explication* : Le cadenas signifie « conversation privée », pas « interlocuteur honnête ». Un faux site bancaire en HTTPS chiffre parfaitement... les identifiants que vous lui donnez. La légitimité se vérifie sur le nom de domaine, pas sur le cadenas.

### Question 10 : SSL ou TLS ?
Un prestataire vous propose de « sécuriser votre site avec un certificat SSL ». Quelle précision technique s'impose ?

* A. Aucune : SSL est le protocole de chiffrement actuel du web.
* B. Le protocole moderne est TLS ; SSL est son prédécesseur, déprécié car vulnérable — on garde le mot « SSL » par habitude commerciale.
* C. SSL et TLS sont deux protocoles concurrents au choix du client.
* **Réponse correcte : B**
* *Explication* : SSLv3 est cassé depuis 2014 ; les navigateurs et serveurs modernes utilisent TLS. L'expression « certificat SSL » survit dans le langage courant, mais un professionnel configure du TLS à jour — et désactive les anciennes versions.

---

## Session 04 : Sécurité du cloud, des données & des identités

### Question 1 : Le moindre privilège
Quel principe de sécurité consiste à n'accorder à chaque utilisateur que les droits strictement nécessaires à sa mission ?

* A. La responsabilité partagée.
* B. Le moindre privilège.
* C. La défense en profondeur.
* **Réponse correcte : B**
* *Explication* : Minimal, nominatif, temporaire : si le compte est compromis, les dégâts restent limités à ses droits ; et l'escalade de privilèges de l'attaquant devient un parcours du combattant. Même le dirigeant n'a pas besoin d'écriture partout — son compte est justement une cible prioritaire.

### Question 2 : Une configuration MFA valide
Laquelle de ces combinaisons constitue une authentification multifacteur (MFA) valide ?

* A. Deux mots de passe différents saisis successivement.
* B. Un mot de passe (ce que je sais) + un code généré par une application sur mon téléphone (ce que je possède).
* C. Un mot de passe et une question secrète.
* **Réponse correcte : B**
* *Explication* : Le MFA exige au moins deux facteurs de **natures différentes** : savoir (mot de passe, PIN), posséder (téléphone, clé physique), être (biométrie). Deux mots de passe ou un mot de passe plus une question secrète relèvent du même facteur (le savoir) — ce n'est pas du MFA.

### Question 3 : La règle 3-2-1
Dans la règle de sauvegarde 3-2-1, que signifie le « 1 » ?

* A. Une seule sauvegarde suffit.
* B. Une copie conservée hors site (autre bâtiment ou cloud), idéalement déconnectée ou immuable.
* C. Une sauvegarde par an.
* **Réponse correcte : B**
* *Explication* : 3 copies, sur 2 supports différents, dont 1 vraiment hors site : c'est cette dernière copie qui survit à l'incendie, au vol ou au ransomware qui chiffre tout le réseau local. Et une sauvegarde jamais testée en restauration n'est qu'un espoir.

### Question 4 : L'efficacité du MFA
Selon Microsoft, quelle proportion des attaques automatisées de compromission de comptes l'activation du MFA bloque-t-elle ?

* A. Environ 50 %.
* B. Environ 80 %.
* C. Plus de 99,9 %.
* **Réponse correcte : C**
* *Explication* : Plus de 99,9 % des attaques automatisées (robots testant des identifiants volés), selon l'étude Microsoft de 2019 régulièrement confirmée depuis. Attention au périmètre : les attaques ciblées savent parfois contourner le MFA classique — d'où l'intérêt des facteurs résistants au phishing.

### Question 5 : Le SIM swapping
Pourquoi recommande-t-on une application d'authentification plutôt que le SMS pour le second facteur ?

* A. Parce que les SMS sont payants.
* B. Parce que le SIM swapping permet à un attaquant de faire transférer votre ligne mobile et de recevoir vos codes SMS ; le code généré localement par l'application, lui, ne transite pas.
* C. Parce que les applications fonctionnent sans batterie.
* **Réponse correcte : B**
* *Explication* : En convainquant l'opérateur de transférer la ligne de la victime, l'attaquant intercepte ses SMS de validation. Le code TOTP est généré sur l'appareil, rien à intercepter. Hiérarchie pratique : clé physique/passkey > application > SMS — mais même le SMS vaut mille fois mieux que rien.

### Question 6 : Les passkeys
Pourquoi les passkeys (clés d'accès FIDO2) sont-elles dites « résistantes au phishing » ?

* A. Parce qu'elles utilisent des mots de passe plus longs.
* B. Parce que la clé cryptographique est liée au site légitime : un faux site n'obtient rien, même si l'utilisateur se laisse prendre.
* C. Parce qu'elles bloquent l'affichage des e-mails frauduleux.
* **Réponse correcte : B**
* *Explication* : Contrairement à un code à 6 chiffres qu'une victime peut dicter ou saisir sur un faux site, la passkey ne « répond » qu'au domaine légitime auprès duquel elle a été enregistrée. L'hameçonnage du facteur devient techniquement inopérant.

### Question 7 : Au repos ou en transit ?
Un ordinateur portable professionnel chiffré (BitLocker/FileVault) est volé dans un train. Quel mécanisme protège les données, et de quel type de chiffrement s'agit-il ?

* A. Le chiffrement en transit (TLS) : les données voyageaient avec l'utilisateur.
* B. Le chiffrement au repos : les données stockées sur le disque sont illisibles sans la clé, le vol devient un simple incident matériel.
* C. Aucun : un vol physique donne toujours accès aux données.
* **Réponse correcte : B**
* *Explication* : Le chiffrement au repos protège les données stockées (disque, base, sauvegarde) ; le chiffrement en transit (TLS) protège les données qui circulent sur le réseau. Une protection complète exige les deux — l'enveloppe pendant le voyage, le coffre-fort à l'arrivée.

### Question 8 : La leçon de Capital One
La violation Capital One (2019, ~106 millions de clients) a exploité un pare-feu applicatif mal configuré et un rôle technique trop privilégié — le tout hébergé dans le cloud. Qui était responsable de ces défauts ?

* A. Le fournisseur cloud : l'infrastructure lui appartient.
* B. Le client : la configuration des services et la gestion des droits relèvent de la « sécurité DANS le cloud ».
* C. Personne : c'est un aléa technique inévitable.
* **Réponse correcte : B**
* *Explication* : Le modèle de responsabilité partagée est sans ambiguïté : le fournisseur sécurise LE cloud (bâtiments, matériel, hyperviseurs), le client sécurise DANS le cloud (identités, configurations, données) — quel que soit le modèle IaaS/PaaS/SaaS. « C'est dans le cloud » ne signifie pas « c'est sécurisé ».

### Question 9 : La sauvegarde piégée
Une entreprise sauvegarde chaque nuit sur un NAS connecté en permanence au réseau. Un ransomware s'exécute avec des privilèges élevés. Que deviennent les sauvegardes ?

* A. Elles sont protégées : le NAS est un équipement distinct du serveur.
* B. Elles sont chiffrées avec le reste : les ransomwares ciblent en priorité les sauvegardes joignables sur le réseau.
* C. Elles sont automatiquement répliquées vers un site de secours.
* **Réponse correcte : B**
* *Explication* : Un NAS joignable depuis le réseau compromis fait partie du réseau compromis. La parade : une copie immuable (non modifiable même par un administrateur) ou physiquement déconnectée — c'est le complément moderne indispensable de la règle 3-2-1.

### Question 10 : Le « Leaver » oublié
Dans le cycle de vie des identités (Joiner-Mover-Leaver), quel est le risque classique associé au « Leaver » ?

* A. Le nouvel arrivant reçoit trop de formations.
* B. Le compte d'un salarié parti reste actif, offrant une porte d'entrée dormante avec des droits légitimes.
* C. Le salarié muté perd l'accès à sa messagerie.
* **Réponse correcte : B**
* *Explication* : Le compte de l'ex-salarié jamais désactivé est un grand classique des audits : il conserve des accès légitimes que plus personne ne surveille. La désactivation immédiate au départ (et la revue périodique des comptes) relève de l'hygiène IAM de base.

---

## Session 05 : Gouvernance, risque, conformité & vie privée

### Question 1 : La valeur de la PSSI
Quel statut juridique interne possède la Politique de Sécurité des Systèmes d'Information (PSSI) signée par la direction ?

* A. C'est un document consultatif sans portée.
* B. Elle a valeur de règlement intérieur : ses règles s'imposent aux collaborateurs.
* C. C'est un contrat commercial avec les clients.
* **Réponse correcte : B**
* *Explication* : Rédigée par le RSSI et signée par la Direction Générale, la PSSI formalise les règles obligatoires (mots de passe, usages, accès). Sa force vient précisément de cette signature : la sécurité y devient un engagement d'entreprise, pas une préférence technique.

### Question 2 : La stratégie « Éviter »
Une entreprise renonce à héberger un fichier de données hautement sensibles dont elle n'a pas un besoin vital. Quelle stratégie de traitement du risque applique-t-elle ?

* A. Réduire.
* B. Transférer.
* C. Éviter.
* **Réponse correcte : C**
* *Explication* : Éviter consiste à supprimer l'activité qui génère le risque. Réduire aurait consisté à protéger le fichier (chiffrement, accès), transférer à s'assurer contre ses conséquences. Le meilleur risque reste parfois celui qu'on ne prend pas.

### Question 3 : La minimisation
Pour l'inscription à une simple newsletter, un formulaire exige le numéro de sécurité sociale. Quel principe du RGPD est violé ?

* A. Le principe de minimisation : on ne collecte que les données strictement nécessaires à la finalité.
* B. Le droit à la portabilité.
* C. L'obligation de notification sous 72 heures.
* **Réponse correcte : A**
* *Explication* : La minimisation est le « moindre privilège de la donnée » : chaque donnée collectée doit être nécessaire au but déclaré. Un NIR pour une newsletter est indéfendable — et chaque donnée superflue collectée est une donnée de plus à protéger et à assumer en cas de fuite.

### Question 4 : Le NIST CSF 2.0
Combien de fonctions structure le NIST Cybersecurity Framework dans sa version 2.0 (2024), et laquelle a été ajoutée ?

* A. Cinq fonctions, dont « Identifier » est la nouveauté.
* B. Six fonctions : « Gouverner » a été ajoutée en socle des cinq historiques (Identifier, Protéger, Détecter, Répondre, Récupérer).
* C. Quatre fonctions, alignées sur le cycle PDCA.
* **Réponse correcte : B**
* *Explication* : La v2.0 (février 2024) consacre la gouvernance comme fonction à part entière : stratégie, rôles et supervision des risques irriguent les cinq autres. Il aura fallu une décennie pour graver officiellement que la cybersécurité se pilote en comité de direction.

### Question 5 : Le calcul de criticité
Un scénario de risque est coté Vraisemblance 3 × Impact 4. Quelle est sa criticité brute et sa zone dans la matrice (seuils : 1-3 faible, 4-9 moyen, 12-16 élevé) ?

* A. Criticité 7, zone moyenne.
* B. Criticité 12, zone élevée : traitement obligatoire et immédiat.
* C. Criticité 12, zone faible.
* **Réponse correcte : B**
* *Explication* : Criticité = Vraisemblance × Impact = 12, en zone rouge. Après traitement (réduction), on réévalue : c'est la criticité résiduelle, celle que la direction accepte en connaissance de cause. La matrice n'est pas un exercice d'école : c'est un outil d'allocation de budget.

### Question 6 : Ce que transfère la cyber-assurance
Souscrire une cyber-assurance « transfère » le risque. Qu'est-ce qui est réellement transféré ?

* A. Le risque entier : l'attaque ne peut plus se produire.
* B. Une partie de l'impact financier — l'interruption d'activité, les données perdues et la responsabilité légale demeurent.
* C. La responsabilité pénale du dirigeant.
* **Réponse correcte : B**
* *Explication* : L'assureur rembourse des frais, il ne restaure ni la production, ni les données, ni la réputation. Les assureurs exigent d'ailleurs désormais des mesures de réduction (MFA, sauvegardes) avant de couvrir — transférer ne dispense jamais de réduire.

### Question 7 : Le chrono des 72 heures
En cas de violation de données personnelles présentant un risque, quand démarre le délai de 72 heures pour notifier la CNIL ?

* A. À la date de l'intrusion initiale de l'attaquant.
* B. À la découverte de la violation par l'organisme.
* C. À la publication des données par l'attaquant.
* **Réponse correcte : B**
* *Explication* : Le chrono court dès que l'organisme a connaissance de la violation — d'où le lien direct entre capacité de détection et conformité. Si le risque pour les personnes est élevé, il faut aussi informer les personnes concernées elles-mêmes.

### Question 8 : Les plafonds de sanction
Quel est le plafond des amendes RGPD pour les manquements les plus graves ?

* A. 20 millions d'euros ou 4 % du chiffre d'affaires mondial annuel — le montant le plus élevé étant retenu.
* B. 500 000 euros dans tous les cas.
* C. 4 % du chiffre d'affaires français uniquement.
* **Réponse correcte : A**
* *Explication* : Le RGPD prévoit deux paliers (jusqu'à 10 M€/2 % pour certains manquements, jusqu'à 20 M€/4 % pour les plus graves), le montant le plus élevé servant de plafond. Le record européen — 1,2 milliard d'euros contre Meta en 2023 — prouve que ces plafonds ne sont pas théoriques.

### Question 9 : Sanctionné sans être piraté
En 2019, la CNIL a infligé 50 M€ à Google sans qu'aucun piratage ni fuite ne soit en cause. Sur quel fondement ?

* A. Un défaut de transparence et un consentement ni éclairé ni spécifique — des manquements de principes.
* B. L'absence d'antivirus sur les serveurs de Google.
* C. Le refus de Google de payer une rançon.
* **Réponse correcte : A**
* *Explication* : L'information était diluée dans une arborescence de menus et le consentement recueilli via une case globale. La leçon fondatrice : un système parfaitement sécurisé peut être parfaitement illégal — la conformité ne se réduit pas à la sécurité technique.

### Question 10 : Accepter n'est pas ignorer
Quelle est la différence entre « accepter un risque » et « ignorer un risque » ?

* A. Aucune : dans les deux cas, on ne fait rien.
* B. L'acceptation est une décision documentée, datée, signée par la direction et réévaluée périodiquement ; l'ignorance est une négligence sans trace.
* C. L'acceptation ne concerne que les risques de criticité maximale.
* **Réponse correcte : B**
* *Explication* : L'effet immédiat est le même (aucune mesure), mais l'acceptation documentée prouve que l'arbitrage a été fait en connaissance de cause — elle protège l'organisation et le dirigeant. C'est toute la différence entre une gouvernance mature et une exposition inconsciente.

---

## Session 06 : Opérations de sécurité & gestion des vulnérabilités

### Question 1 : Le rôle du SIEM
Quel est le rôle principal d'un SIEM dans un dispositif de détection ?

* A. Bloquer les malwares sur les postes de travail.
* B. Centraliser les journaux d'événements de toutes les machines et détecter les combinaisons suspectes par corrélation.
* C. Remplacer les analystes du SOC.
* **Réponse correcte : B**
* *Explication* : Chaque événement isolé est anodin (un échec de connexion, un transfert de fichier) ; c'est la combinaison qui fait l'attaque (50 échecs + 1 succès + 10 Go sortants). Le SIEM lit les combinaisons ; l'analyste du SOC qualifie ensuite l'alerte.

### Question 2 : Le faux positif
L'antivirus alerte sur le fichier de test standard (EICAR) utilisé volontairement par un technicien. Que doit faire l'analyste SOC ?

* A. Ignorer l'alerte sans rien consigner : le technicien est connu.
* B. Qualifier le faux positif, le documenter et ajuster la règle pour ce cas d'usage encadré.
* C. Isoler le poste et lancer une investigation complète.
* **Réponse correcte : B**
* *Explication* : Un faux positif se documente toujours : c'est ainsi qu'on affine les règles (tuning) et qu'on combat la fatigue des alertes. Ignorer sans consigner dégrade le système de détection — et un jour, le vrai loup passe au milieu des faux.

### Question 3 : Scan ou pentest ?
Quelle est la différence fondamentale entre un scan de vulnérabilités et un test d'intrusion ?

* A. Aucune : ce sont deux noms pour la même prestation.
* B. Le scan est un outil automatisé qui compare le parc aux failles connues ; le pentest est mené par un expert humain qui exploite et combine les failles en conditions réelles, avec autorisation écrite.
* C. Le scan est réservé aux grandes entreprises, le pentest aux PME.
* **Réponse correcte : B**
* *Explication* : Le scan est le radar automatique (fréquent, systématique, faux positifs possibles) ; le pentester est le pilote d'essai (il improvise et contourne). Une bonne stratégie combine scans fréquents et pentest périodique — jamais l'un sans l'autre.

### Question 4 : Les niveaux du SOC
Dans un SOC organisé en trois niveaux, quelle est la répartition des rôles ?

* A. T1 trie les alertes et gère les faux positifs ; T2 investigue les incidents confirmés ; T3 chasse proactivement les menaces invisibles (*threat hunting*).
* B. T1 dirige le SOC ; T2 gère le budget ; T3 rédige les rapports.
* C. Les trois niveaux font le même travail en rotation horaire.
* **Réponse correcte : A**
* *Explication* : Le tri (T1) absorbe le volume, l'investigation (T2) traite le confirmé, la chasse (T3) cherche ce qui n'a déclenché aucune alerte. Cette pyramide protège les experts rares de la noyade sous les alertes de routine.

### Question 5 : Score et exposition
Deux failles attendent un correctif : une 8.5 sur un serveur interne non exposé, une 7.5 sur le serveur web public. Laquelle traiter en premier, et pourquoi ?

* A. La 8.5 : le score CVSS brut prime toujours.
* B. La 7.5 : l'exposition sur Internet augmente drastiquement la probabilité d'exploitation réelle — le score dit la gravité, l'exposition dit l'urgence.
* C. Aucune : on attend l'audit annuel.
* **Réponse correcte : B**
* *Explication* : Le score CVSS mesure la gravité intrinsèque de la faille ; le contexte d'exposition détermine l'urgence opérationnelle. Une faille moyenne exposée au balayage permanent d'Internet est souvent plus urgente qu'une faille sévère enfouie derrière trois pare-feux.

### Question 6 : L'échelle CVSS
Un scan remonte une faille CVSS 9.8 sur un serveur de production exposé. Comment la qualifier et réagir ?

* A. Critique (9.0-10.0) : correctif ou mesure de contournement en urgence, sous 24 heures, avec surveillance renforcée.
* B. Élevée (7.0-8.9) : à traiter dans le mois.
* C. Moyenne (4.0-6.9) : cycle normal de maintenance.
* **Réponse correcte : A**
* *Explication* : L'échelle CVSS (v4.0 actuelle, échelle commune avec la v3.1) classe 9.0-10.0 en Critique — typiquement exploitable à distance sans authentification. Sur un actif exposé, la fenêtre correctif-attaque se compte en heures ou en jours, pas en trimestres.

### Question 7 : Le déluge de CVE
Environ 40 000 CVE ont été publiées en 2024 (plus de 100 par jour, un record). Quelle conséquence opérationnelle ce volume impose-t-il ?

* A. Corriger toutes les failles immédiatement, sans exception.
* B. Prioriser : personne ne peut tout corriger — on traite d'abord ce qui est critique ET exposé.
* C. Ignorer les CVE et se fier uniquement à l'antivirus.
* **Réponse correcte : B**
* *Explication* : La gestion des vulnérabilités n'est pas une affaire de perfection mais de priorisation, outillée par le CVSS pondéré par l'exposition. C'est tout l'objet de la feuille de route de remédiation : immédiat / sous 7 jours / cycle mensuel.

### Question 8 : La leçon d'Equifax
Chez Equifax (2017, ~147 millions de personnes, ~700 M$), le correctif de la faille exploitée était disponible deux mois avant l'intrusion. Qu'est-ce qui a réellement failli ?

* A. La technologie : aucun correctif n'existait.
* B. Le processus et l'organisation : inventaire incomplet, correctif non appliqué, outil de surveillance lui-même mal configuré (76 jours sans détection).
* C. La loi : aucune obligation de correctif n'existait à l'époque.
* **Réponse correcte : B**
* *Explication* : Le correctif existait du premier au dernier jour ; c'est la chaîne organisationnelle qui a rompu, deux fois (patch management puis détection). La question d'audit qui en découle : « combien de temps entre la publication d'un correctif critique et son application chez vous ? »

### Question 9 : Log4Shell
Pourquoi la faille Log4Shell (décembre 2021, CVSS 10.0) a-t-elle été si difficile à corriger rapidement dans le monde entier ?

* A. Le correctif était payant.
* B. La bibliothèque Log4j était enfouie partout, souvent dans des produits tiers : il fallait d'abord savoir OÙ l'on était vulnérable — l'inventaire avant le correctif.
* C. La faille ne concernait que les superordinateurs.
* **Réponse correcte : B**
* *Explication* : Face à une faille ubiquitaire exploitée en quelques heures, la vitesse de réaction dépend de trois choses préparées avant la crise : un inventaire à jour, des scans capables de confirmer, un processus de patch d'urgence rodé. Les organisations préparées ont corrigé en 48 heures ; les autres ont subi des mois.

### Question 10 : Le SOAR et la fatigue des alertes
Quel problème la technologie SOAR (orchestration et automatisation de la réponse) vise-t-elle à résoudre ?

* A. Le coût des licences antivirus.
* B. La fatigue des alertes : automatiser les réponses répétitives (playbooks) pour que les analystes se concentrent sur les cas complexes.
* C. La lenteur des connexions VPN.
* **Réponse correcte : B**
* *Explication* : Submergé d'alertes dont beaucoup de faux positifs, l'analyste finit par « crier au loup » intérieurement. Le SOAR exécute automatiquement les réactions codifiées (ex. isoler un poste qui contacte une IP malveillante connue), en gardant l'humain pour le jugement.

---

## Session 07 : Réponse aux incidents & introduction au forensics

### Question 1 : L'ordre de volatilité
Lors de la collecte de preuves sur une machine compromise, quel élément doit être capturé en premier ?

* A. Le disque dur, par copie bit-à-bit.
* B. La mémoire vive (RAM) et les connexions actives : elles s'effacent à l'extinction ou à la déconnexion.
* C. Les e-mails archivés de l'utilisateur.
* **Réponse correcte : B**
* *Explication* : L'ordre de volatilité impose de capturer d'abord ce qui s'évapore : la RAM contient les mots de passe en clair, les clés de chiffrement et les connexions de l'attaquant. Le disque, persistant, se clone en dernier.

### Question 2 : La chaîne de contrôle
À quoi sert le calcul d'empreinte (hachage SHA-256) dans la chaîne de contrôle d'une preuve numérique ?

* A. À chiffrer le disque pour le protéger des regards.
* B. À prouver que la copie analysée est strictement identique à l'original, resté scellé.
* C. À accélérer l'analyse du disque par l'enquêteur.
* **Réponse correcte : B**
* *Explication* : Empreintes identiques = contenus identiques : le hachage prouve l'intégrité de la copie de travail, l'original restant sous scellés. Toute manipulation est consignée (qui, quand, pourquoi) — sans cette chaîne, la meilleure preuve est irrecevable au tribunal.

### Question 3 : Le cadre pénal
En France, que risque l'auteur d'un simple accès frauduleux à un système informatique (art. 323-1 du Code pénal), même « pour prouver une faille » ?

* A. Rien, si le système était mal sécurisé.
* B. Jusqu'à 2 ans d'emprisonnement et 60 000 € d'amende — davantage en cas d'altération de données (3 ans / 100 000 €) ou d'entrave (5 ans / 150 000 €).
* C. Une simple amende administrative de 135 €.
* **Réponse correcte : B**
* *Explication* : Le défaut de sécurisation du système n'est pas une excuse légale — la porte ouverte n'autorise pas le cambriolage. La bonne intention ne change rien au délit : la voie légale est le signalement responsable, sans exploitation.

### Question 4 : L'ordre du cycle
Pourquoi l'Éradication doit-elle impérativement précéder la Restauration dans le cycle de réponse aux incidents ?

* A. Pour des raisons purement administratives.
* B. Parce que restaurer sur un système encore compromis (porte dérobée en place) garantit la re-compromission — on réinstalle la maison pendant que le cambrioleur a le double des clés.
* C. Parce que la restauration est plus coûteuse que l'éradication.
* **Réponse correcte : B**
* *Explication* : Les six étapes (Préparation, Identification, Confinement, Éradication, Restauration, Leçons apprises) s'enchaînent dans un ordre non négociable. Restaurer trop tôt fait repartir la production... avec l'attaquant à l'intérieur.

### Question 5 : Le premier geste
Un poste montre une infection active. Pourquoi débrancher le câble réseau plutôt qu'éteindre la machine ?

* A. Parce qu'éteindre abîme le disque dur.
* B. Parce que débrancher isole l'attaquant et stoppe la propagation, tandis qu'éteindre détruit la mémoire vive — donc les clés de chiffrement et les preuves.
* C. Parce que le câble réseau est plus facile d'accès que le bouton d'alimentation.
* **Réponse correcte : B**
* *Explication* : Deux gestes qui se ressemblent, deux conséquences opposées : l'isolement réseau confine sans rien détruire ; l'extinction vide la RAM et peut anéantir la seule chance de déchiffrer sans payer. Isoler, jamais éteindre.

### Question 6 : SANS ou NIST ?
Le cycle en 6 étapes (Préparation, Identification, Confinement, Éradication, Restauration, Leçons apprises) et le modèle en 4 phases du NIST SP 800-61 sont-ils contradictoires ?

* A. Oui : il faut choisir son camp méthodologique.
* B. Non : le cycle en 6 étapes est le modèle SANS (PICERL) ; le NIST regroupe les mêmes réalités en 4 phases — granularités différentes, même logique.
* C. Oui : le NIST interdit la phase de confinement.
* **Réponse correcte : B**
* *Explication* : Le NIST fusionne Confinement-Éradication-Recouvrement en une seule phase et parle d'« activité post-incident » pour les leçons apprises. Citer l'un ou l'autre est correct — l'essentiel est l'ordre des opérations, identique dans les deux modèles.

### Question 7 : La doctrine face aux rançons
Quelle est la position constante des autorités françaises (ANSSI) sur le paiement des rançons ?

* A. Payer rapidement pour récupérer les données au plus vite.
* B. Ne pas payer : aucune garantie de récupération, financement de l'écosystème criminel, désignation comme « payeur » récidivable — et porter plainte, condition d'indemnisation par les cyber-assurances.
* C. Payer uniquement si la rançon est inférieure à 10 000 €.
* **Réponse correcte : B**
* *Explication* : C'est la ligne tenue par l'hôpital de Corbeil-Essonnes en 2022 malgré 10 M$ exigés. La décision de payer ou non se prépare à froid, en phase de Préparation — jamais à chaud, à 3 heures du matin.

### Question 8 : Le miracle de Maersk
Après NotPetya (2017), Maersk a reconstruit ~4 000 serveurs et 45 000 postes en dix jours grâce à un unique contrôleur de domaine survivant au Ghana. Pourquoi ce serveur avait-il survécu ?

* A. Il était protégé par un antivirus de nouvelle génération.
* B. Une coupure de courant l'avait mis hors ligne au moment de l'attaque : déconnecté, il n'a pas été infecté.
* C. Il utilisait un système d'exploitation inconnu des attaquants.
* **Réponse correcte : B**
* *Explication* : La survie de l'informatique mondiale de Maersk a tenu à une panne d'électricité — une copie hors ligne accidentelle. La leçon : institutionnaliser ce hasard avec des sauvegardes volontairement déconnectées ou immuables (le 3-2-1 moderne), plutôt que compter sur la chance.

### Question 9 : La phase la plus rentable
Pourquoi la phase « Leçons apprises » est-elle décrite comme la plus rentable du cycle — et pourtant la plus souvent sautée ?

* A. Elle permet de facturer l'incident au client.
* B. Elle transforme l'incident subi en correctifs durables (architecture, procédures, formation) ; on la saute parce que l'urgence est retombée et que chacun veut passer à autre chose.
* C. Elle est obligatoire pour obtenir un remboursement d'assurance.
* **Réponse correcte : B**
* *Explication* : Sans RETEX, la même attaque réussira le mois suivant par la même porte. C'est cette phase qui transforme « 41 heures d'aveuglement » en MFA sur le VPN — un correctif d'architecture qui vaut tous les rapports.

### Question 10 : Le périmètre du pentest
En mission, un pentester découvre que le sous-traitant de son client semble vulnérable. Peut-il le tester « pour être complet » ?

* A. Oui : c'est dans l'intérêt de son client.
* B. Non : hors du périmètre écrit de l'ordre de mission, ces tests constituent un délit pénal — même avec de bonnes intentions.
* C. Oui, à condition de prévenir le sous-traitant par e-mail après coup.
* **Réponse correcte : B**
* *Explication* : L'ordre de mission écrit (périmètre, période, outils) est la frontière exacte entre le métier et le délit. Le sous-traitant n'a rien signé : le tester relève de l'article 323-1, pas de la conscience professionnelle.

---

## Session 08 : Grand Atelier d'Audit & Synthèse

### Question 1 : L'objet d'un audit de sécurité
Qu'est-ce qu'un audit de sécurité ?

* A. Une attaque informatique menée par un concurrent.
* B. Une évaluation méthodique de l'état de sécurité d'une organisation par rapport à des normes ou des règles de l'art, débouchant sur un plan d'action priorisé.
* C. L'installation d'un antivirus sur tous les postes.
* **Réponse correcte : B**
* *Explication* : L'audit constate l'existant (technique, organisationnel, humain), le compare à un référentiel et hiérarchise les écarts. Son livrable utile n'est pas la liste des problèmes mais la feuille de route de remédiation — priorisée et budgétée.

### Question 2 : Le court terme à budget nul
Dans la feuille de route de MedDistri, quelles mesures relèvent du court terme à budget quasi nul ?

* A. L'achat d'un pare-feu de nouvelle génération et d'un SIEM.
* B. La fermeture des accès exposés sur Internet, l'activation du MFA et le changement des mots de passe prévisibles.
* C. La certification ISO 27001 de l'entreprise.
* **Réponse correcte : B**
* *Explication* : Les mesures les plus urgentes sont souvent les moins chères : fermer, activer, changer. Les investissements (VPN, sauvegarde externalisée) viennent au moyen terme, et la consolidation (PSSI, scans, exercices) au long terme — l'ordre inverse serait un contresens budgétaire.

### Question 3 : Les portes ouvertes de MedDistri
Les ports SSH (22) et RDP (3389) de MedDistri sont exposés à tout Internet. Pourquoi est-ce la priorité absolue de l'audit ?

* A. Parce que ces ports ralentissent la connexion Internet de l'entreprise.
* B. Parce que les accès d'administration exposés sont l'un des tout premiers vecteurs d'infection par ransomware : scannés en continu, ils subissent la force brute en quelques minutes.
* C. Parce que ces ports sont payants chez les fournisseurs d'accès.
* **Réponse correcte : B**
* *Explication* : Internet est balayé en permanence par des robots ; un accès d'administration exposé avec mot de passe devinable est une invitation. La remédiation type : fermer les ports, passer par un VPN et exiger le MFA sur cet accès.

### Question 4 : Parler à la direction
Comment présenter efficacement une vulnérabilité technique à une direction non technicienne ?

* A. Détailler le fonctionnement du protocole et le numéro de CVE.
* B. Traduire en risque business : impact financier, juridique et réputationnel (« vol du fichier client → sanction CNIL et une de la presse » plutôt que « injection SQL »).
* C. Envoyer le rapport de scan brut de 200 pages.
* **Réponse correcte : B**
* *Explication* : Un comité de direction décide sur des risques d'entreprise, pas sur du jargon. La vulgarisation managériale est une compétence d'auditeur à part entière : « 3 secondes de MFA par jour contre 3 semaines d'arrêt » convainc plus qu'un acronyme.

### Question 5 : Le meilleur retour sur investissement
Pour une TPE/PME, quelle démarche offre le meilleur retour sur investissement en sécurité ?

* A. Un pare-feu haut de gamme à 5 000 €.
* B. L'hygiène de base : mots de passe robustes, MFA, sauvegardes saines et sensibilisation des collaborateurs.
* C. Une charte informatique de 80 pages.
* **Réponse correcte : B**
* *Explication* : L'hygiène de base bloque la majorité des attaques opportunistes pour un coût minime. L'outil coûteux isolé protège un point pendant que tout le reste est ouvert, et la charte que personne ne lit est l'anti-modèle de la PSSI utile.

### Question 6 : Le pentest prématuré
MedDistri dispose de 2 000 € de budget annuel. Pourquoi un test d'intrusion complet à 2 000 € serait-il un mauvais premier investissement ?

* A. Parce que les pentests sont interdits aux PME.
* B. Parce qu'auditer un système dont les failles béantes sont déjà connues revient à payer pour apprendre ce que l'on sait : le pentest prend sa valeur une fois l'hygiène de base en place.
* C. Parce qu'un pentest ne peut être réalisé qu'en interne.
* **Réponse correcte : B**
* *Explication* : Le pentest n'est pas inutile, il est prématuré : avec des ports exposés, sans MFA ni sauvegarde saine, son rapport ne ferait que confirmer l'évidence. Le budget se dépense d'abord sur les remédiations connues, le pentest vient valider ensuite.

### Question 7 : La sauvegarde de MedDistri
La sauvegarde hebdomadaire de MedDistri sur disque USB branché en permanence est jugée critique par l'audit. Quelle remédiation la feuille de route doit-elle prévoir ?

* A. Passer à deux disques USB branchés en alternance sur le même serveur.
* B. Une sauvegarde respectant la règle 3-2-1 avec une copie déconnectée ou immuable, et des tests de restauration réguliers.
* C. Supprimer les sauvegardes pour éviter qu'elles soient volées.
* **Réponse correcte : B**
* *Explication* : Le disque branché en permanence sera chiffré avec le serveur lors d'une attaque par ransomware. La copie hors d'atteinte (déconnectée ou immuable) et testée est ce qui permet de restaurer sans payer — c'est la différence entre un incident et une catastrophe.

### Question 8 : La synthèse managériale
Qu'est-ce qu'une bonne synthèse managériale (*executive summary*) de rapport d'audit ?

* A. La liste exhaustive des 200 vulnérabilités détectées, classées par CVE.
* B. Une page maximum, sans jargon : les menaces majeures, leur impact business et le budget des remédiations prioritaires.
* C. Un glossaire technique complet à destination des dirigeants.
* **Réponse correcte : B**
* *Explication* : La synthèse managériale est la seule page que la direction lira intégralement : elle doit permettre une décision (arbitrer, budgéter) en cinq minutes. Le détail technique vit dans le corps du rapport, pour les équipes qui remédient.

### Question 9 : Le Score de Résilience
Dans l'Atelier MedDistri, que mesure le « Score de Résilience Cyber » qui passe de 10 % à (idéalement) plus de 80 % ?

* A. La vitesse de connexion Internet de l'entreprise.
* B. La capacité estimée de la PME à résister à une attaque et à s'en relever, améliorée à chaque décision d'audit correcte.
* C. Le pourcentage d'employés ayant suivi la formation.
* **Réponse correcte : B**
* *Explication* : La jauge matérialise l'effet cumulé des bonnes décisions : fermer les accès (+25 %), activer le MFA (+20 %), assainir les sauvegardes (+25 %), allouer le budget à l'hygiène (+20 %). Quatre décisions à moins de 2 000 € — la preuve que le risque PME est d'abord une affaire de réflexes.

### Question 10 : Le mot de passe prévisible
Le mot de passe administrateur de MedDistri est `Admin@MedDistri2025`. Pourquoi est-il faible malgré sa longueur, ses majuscules et son caractère spécial ?

* A. Il ne contient pas assez de chiffres.
* B. Il suit un schéma prévisible (rôle + nom de l'entreprise + année) que les attaques par dictionnaire testent en priorité.
* C. Il est trop long pour être mémorisé.
* **Réponse correcte : B**
* *Explication* : Les outils de force brute ne testent pas au hasard : ils combinent nom de l'entreprise, années et mots usuels. La robustesse vient de l'imprévisibilité (phrases de passe longues ou générateur aléatoire d'un gestionnaire), pas du simple respect formel des règles de complexité.
