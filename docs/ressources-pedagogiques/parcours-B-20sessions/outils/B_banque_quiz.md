# Banque de Quiz — Parcours B (20 sessions)
Parcours : B 20 sessions  |  Module : Évaluation continue  |  Format : Banque de QCM résolus

> **Usage** : ces questions alimentent les quiz d'auto-évaluation self-paced et servent de réserve au mentor (sondages supplémentaires, séances de révision). Chaque question est autonome : scénario ou fait précis, une seule bonne réponse, explication qui enseigne. Les questions sont alignées sur les supports de cours enrichis (chiffres sourcés et études de cas compris).

---

## Session B01 : Introduction à la cybersécurité & triade CIA

### Question 1 : Le pilier d'Intégrité
Quelle mesure garantit le pilier de l'**Intégrité** de la triade CIA lorsqu'un fichier est transféré sur un réseau ?

* A. Le chiffrement symétrique AES-256.
* B. L'empreinte cryptographique (hachage) SHA-256.
* C. La redondance des disques durs (RAID 1).
* **Réponse correcte : B**
* *Explication* : L'empreinte (hachage) permet de vérifier qu'un fichier n'a pas été altéré pendant son transfert : si le fichier change d'un seul bit, son empreinte change complètement. Le chiffrement AES-256 garantit la Confidentialité et le RAID 1 la Disponibilité.

### Question 2 : Le concept de Défense en Profondeur
Qu'illustre le principe de la **Défense en Profondeur** ?

* A. Acheter le pare-feu le plus cher du marché pour sécuriser la périphérie.
* B. Installer plusieurs couches de contrôles de sécurité indépendants (physiques, techniques, administratifs).
* C. Conserver tous les serveurs informatiques dans un sous-sol sécurisé à 10 mètres de profondeur.
* **Réponse correcte : B**
* *Explication* : La défense en profondeur superpose plusieurs barrières (pare-feu + antivirus + formation + MFA). Si une barrière cède, les autres empêchent ou ralentissent la progression de l'attaquant.

### Question 3 : L'acronyme CIA
Dans l'acronyme anglais « CIA » de la triade de sécurité, que désigne la lettre **A** ?

* A. *Authentication* — l'authentification des utilisateurs.
* B. *Availability* — la Disponibilité des systèmes et des données.
* C. *Authorization* — l'autorisation d'accès aux ressources.
* **Réponse correcte : B**
* *Explication* : L'acronyme vient de *Confidentiality, Integrity, Availability*. L'authentification et l'autorisation sont des mécanismes de contrôle d'accès, pas des piliers de la triade.

### Question 4 : Vulnérabilité, menace ou risque ?
Un serveur de votre entreprise n'a reçu aucune mise à jour depuis deux ans. En vocabulaire de sécurité, ce serveur constitue…

* A. Une menace.
* B. Une vulnérabilité.
* C. Un risque.
* **Réponse correcte : B**
* *Explication* : La vulnérabilité est la faiblesse (la porte ouverte) ; la menace est l'acteur qui peut l'exploiter ; le risque est leur combinaison avec l'impact. Le serveur obsolète est la porte ouverte.

### Question 5 : L'attaque du CHSF (Corbeil-Essonnes, 2022)
Lors de l'attaque du Centre Hospitalier Sud-Francilien (LockBit, août 2022), les systèmes ont d'abord été chiffrés, puis des données ont été publiées après le refus de payer. Quels piliers de la triade ont été successivement touchés ?

* A. La Disponibilité, puis la Confidentialité.
* B. L'Intégrité, puis la Disponibilité.
* C. Uniquement la Confidentialité.
* **Réponse correcte : A**
* *Explication* : Le chiffrement des systèmes a rendu l'hôpital indisponible (retour au papier) ; la publication des données volées a ensuite violé la Confidentialité. C'est le schéma de la double extorsion.

### Question 6 : France Travail (2024)
La violation de données de France Travail (mars 2024) a potentiellement exposé les informations d'environ 43 millions de personnes. Quel pilier de la triade cet incident illustre-t-il avant tout ?

* A. La Disponibilité : le site de France Travail est resté inaccessible plusieurs semaines.
* B. La Confidentialité : des données personnelles ont été consultées et exfiltrées à très grande échelle.
* C. L'Intégrité : les dossiers des demandeurs d'emploi ont été falsifiés.
* **Réponse correcte : B**
* *Explication* : Il s'agit d'une fuite massive de données personnelles — une atteinte à la Confidentialité, l'une des plus importantes jamais enregistrées en France par son ampleur.

### Question 7 : Le retour au papier
Quand un hôpital attaqué par un rançongiciel repasse aux formulaires papier et reporte des opérations, quel pilier de la triade est directement en défaut ?

* A. La Confidentialité.
* B. L'Intégrité.
* C. La Disponibilité.
* **Réponse correcte : C**
* *Explication* : Les données et systèmes existent toujours mais sont inaccessibles : c'est la Disponibilité qui est rompue — avec, dans la santé, des conséquences potentiellement vitales.

### Question 8 : Le rançongiciel
Quel terme désigne un logiciel malveillant qui chiffre les données d'une victime et exige un paiement pour les déchiffrer ?

* A. Un APT (Advanced Persistent Threat).
* B. Un serveur de Command & Control (C2).
* C. Un ransomware (rançongiciel).
* **Réponse correcte : C**
* *Explication* : Le rançongiciel prend les données en otage par chiffrement. L'APT désigne un groupe d'attaquants sophistiqué et persistant ; le C2 est le serveur depuis lequel un attaquant pilote ses machines compromises.

### Question 9 : Le déni de service distribué
Quel terme désigne une attaque visant à rendre un service indisponible en le submergeant de requêtes envoyées depuis de nombreuses sources ?

* A. Un ver (worm).
* B. La Cyber Kill Chain.
* C. Un DDoS (déni de service distribué).
* **Réponse correcte : C**
* *Explication* : Le DDoS mobilise des milliers de machines compromises (botnet) pour saturer une cible : il attaque la Disponibilité, sans voler ni modifier de données.

### Question 10 : Red Team et Blue Team
Quelle équipe simule des attaques pour évaluer les défenses d'une organisation, et laquelle les repousse au quotidien ?

* A. La Red Team attaque en simulation ; la Blue Team défend au quotidien.
* B. La Blue Team attaque en simulation ; la Red Team défend au quotidien.
* C. Les deux termes désignent la même équipe à des horaires différents.
* **Réponse correcte : A**
* *Explication* : La Red Team joue l'attaquant (tests d'intrusion, simulations) pour révéler les faiblesses ; la Blue Team surveille, détecte et répond aux attaques réelles. Leur confrontation améliore la défense.

---

## Session B02 : Paysage des menaces & acteurs

### Question 1 : Motivation des Advanced Persistent Threats (APT)
Quelle est la principale caractéristique et motivation d'un groupe d'attaquants qualifié d'APT (généralement soutenu par un État) ?

* A. Obtenir des gains financiers immédiats par le vol de cartes bleues.
* B. Réaliser des attaques à des fins de sabotage politique ou d'espionnage industriel à long terme.
* C. Modifier le design d'un site web public par idéologie (défacement).
* **Réponse correcte : B**
* *Explication* : Les APT disposent de ressources importantes et visent l'espionnage, le vol de propriété intellectuelle ou le sabotage à long terme. Le vol financier de masse est l'apanage des cybercriminels, le défacement idéologique celui des hacktivistes.

### Question 2 : La notion de « Script Kiddie »
Qu'est-ce qu'un « script kiddie » dans le jargon de la cybersécurité ?

* A. Un analyste junior apprenant à coder en Python.
* B. Un attaquant utilisant des scripts et outils automatisés créés par d'autres, sans en comprendre le fonctionnement réel.
* C. Un botnet de serveurs automatisés spammant des e-mails d'hameçonnage.
* **Réponse correcte : B**
* *Explication* : Le script kiddie manque de compétences avancées : il télécharge et lance des outils publics, souvent par jeu ou provocation — dangereux malgré tout, car l'outil, lui, est réel.

### Question 3 : Le Ransomware-as-a-Service (RaaS)
Que désigne le modèle « RaaS » dans l'économie cybercriminelle ?

* A. La location d'un rançongiciel clé en main à des « affiliés », contre un pourcentage des rançons extorquées.
* B. Un service public de déchiffrement gratuit des rançongiciels.
* C. Une assurance couvrant le paiement des rançons.
* **Réponse correcte : A**
* *Explication* : Le RaaS industrialise le crime : les développeurs louent l'outil et l'infrastructure, les affiliés mènent les attaques. C'est le modèle qui a fait la « réussite » de LockBit — et qui explique le volume des attaques sur les PME.

### Question 4 : Les indicateurs de compromission (IoC)
À quoi servent les IoC (*Indicators of Compromise*) partagés entre organisations ?

* A. À mesurer la performance financière des équipes de sécurité.
* B. À reconnaître les signes techniques d'une compromission (adresses IP malveillantes, empreintes de fichiers) observés ailleurs, pour les détecter chez soi.
* C. À certifier la conformité RGPD d'un traitement.
* **Réponse correcte : B**
* *Explication* : Les IoC sont la matière première du renseignement sur les menaces (CTI) : ce qu'une victime a observé (IP, condensats, noms de domaine) permet à toutes les autres de détecter et bloquer la même campagne.

### Question 5 : La menace interne
Quel terme désigne le risque provenant d'un employé, prestataire ou partenaire disposant d'accès légitimes au réseau ?

* A. La menace interne (*insider threat*).
* B. Le smishing.
* C. Le risque résiduel.
* **Réponse correcte : A**
* *Explication* : L'initié — malveillant ou simplement négligent — franchit toutes les défenses périmétriques puisqu'il est déjà à l'intérieur : sa détection repose sur la surveillance des comportements (journaux, DLP) et la limitation des privilèges.

### Question 6 : La Banque du Bangladesh (2016)
Le casse de la Banque du Bangladesh (2016, ~81 M$ détournés via le réseau SWIFT) est attribué au groupe Lazarus, lié à un État. Qu'enseigne ce cas sur la classification des attaquants ?

* A. Les États n'attaquent jamais pour de l'argent.
* B. Les frontières entre catégories se brouillent : un groupe étatique peut mener des opérations à motivation financière.
* C. Les banques ne sont attaquées que par des script kiddies.
* **Réponse correcte : B**
* *Explication* : Lazarus combine espionnage étatique et braquages financiers. Les catégories d'attaquants décrivent des motivations dominantes, pas des cases étanches — d'où l'importance de se défendre contre les techniques, pas contre les étiquettes.

### Question 7 : L'opération Cronos (2024)
Que retenir du démantèlement partiel de LockBit par l'opération internationale Cronos (février 2024) ?

* A. Le rançongiciel a définitivement disparu depuis.
* B. La coopération policière internationale peut frapper l'écosystème criminel — et récupérer des clés de déchiffrement pour les victimes qui ont porté plainte.
* C. Les autorités ont racheté LockBit pour l'étudier.
* **Réponse correcte : B**
* *Explication* : Cronos a saisi l'infrastructure de LockBit et récupéré des clés remises à des victimes. Leçon pratique : signaler et porter plainte n'est jamais inutile — cela alimente les enquêtes et peut permettre de récupérer ses données.

### Question 8 : L'hacktiviste
Quelle est la motivation première d'un hacktiviste ?

* A. Le gain financier par l'extorsion.
* B. L'idéologie : porter une cause politique ou sociale par des actions numériques (défacement, fuites, DDoS).
* C. L'espionnage industriel au profit d'un concurrent.
* **Réponse correcte : B**
* *Explication* : L'hacktiviste cherche la visibilité de sa cause, pas l'argent. Ses attaques privilégient l'impact symbolique et médiatique — défacements, dénis de service, publications de documents.

### Question 9 : La LOPMI et l'assurance cyber
Depuis la loi LOPMI (2023), à quelle condition une entreprise française peut-elle être indemnisée par son assurance après une cyberattaque ?

* A. Avoir payé la rançon rapidement.
* B. Avoir déposé plainte dans les 72 heures suivant la connaissance de l'attaque.
* C. Avoir informé la presse dans les 24 heures.
* **Réponse correcte : B**
* *Explication* : La LOPMI conditionne l'indemnisation assurantielle au dépôt de plainte sous 72 h. Le réflexe judiciaire n'est plus optionnel — et il alimente les enquêtes (voir l'opération Cronos).

### Question 10 : La veille CERT-FR
À quoi sert concrètement l'abonnement aux bulletins du CERT-FR pour une PME ?

* A. À obtenir une certification officielle de l'ANSSI.
* B. À être alerté des vulnérabilités critiques et campagnes d'attaques en cours, pour corriger avant d'être frappé.
* C. À remplacer l'antivirus par une veille documentaire.
* **Réponse correcte : B**
* *Explication* : Le CERT-FR publie alertes et avis sur les vulnérabilités activement exploitées. Cette veille gratuite permet de prioriser ses correctifs sur ce qui est réellement attaqué — le premier étage d'une défense informée.

---

## Session B03 : Types d'attaques & vecteurs

### Question 1 : L'attaque de l'Homme du Milieu (MitM)
Quelle action illustre une attaque de type « Homme du Milieu » (*Man-in-the-Middle*) ?

* A. Un attaquant qui usurpe l'adresse IP d'un serveur légitime pour intercepter les flux réseau non chiffrés d'un utilisateur.
* B. Un pirate qui devine le mot de passe d'une session Windows par force brute.
* C. Une clé USB malveillante déposée sur un bureau pour piéger un logisticien.
* **Réponse correcte : A**
* *Explication* : Le MitM consiste à s'interposer dans les communications entre deux parties à leur insu (typiquement sur un réseau non chiffré) pour lire ou altérer les échanges.

### Question 2 : Attaque par Déni de Service Distribué (DDoS)
Quel est l'objectif premier d'une attaque DDoS ?

* A. Voler la base de données de facturation d'un site e-commerce.
* B. Rendre un site web ou un serveur indisponible en saturant ses ressources de requêtes simultanées.
* C. Installer un logiciel espion de type keylogger sur les ordinateurs des dirigeants.
* **Réponse correcte : B**
* *Explication* : Le DDoS vise la Disponibilité : des milliers de machines compromises (botnet) submergent la cible, qui ne peut plus répondre aux clients légitimes.

### Question 3 : Le ver informatique
Qu'est-ce qui distingue un **ver** (*worm*) des autres logiciels malveillants ?

* A. Il se propage de manière autonome de machine en machine, sans intervention humaine.
* B. Il ne fonctionne que sur les téléphones mobiles.
* C. Il nécessite qu'un utilisateur l'exécute manuellement sur chaque machine.
* **Réponse correcte : A**
* *Explication* : Le ver exploite des vulnérabilités réseau pour se répliquer seul — c'est ce qui a permis à WannaCry d'infecter des centaines de milliers de machines dans le monde en quelques jours.

### Question 4 : Le cheval de Troie
Quel terme désigne un programme nuisible camouflé sous l'apparence d'un logiciel légitime ?

* A. Un cheval de Troie (*trojan*).
* B. Un hameçonnage (*phishing*).
* C. Un chiffrement en transit.
* **Réponse correcte : A**
* *Explication* : Comme dans le mythe, le danger est à l'intérieur du cadeau : l'utilisateur installe lui-même le programme (faux utilitaire, pièce jointe piégée), qui ouvre ensuite l'accès à l'attaquant.

### Question 5 : La Cyber Kill Chain
Que décrit le modèle « Cyber Kill Chain » (Lockheed Martin) ?

* A. Les 7 étapes types du déroulement d'une attaque ciblée, de la reconnaissance à l'action finale.
* B. La procédure de licenciement d'un administrateur négligent.
* C. Le classement mondial des groupes de rançongiciels.
* **Réponse correcte : A**
* *Explication* : Ce modèle découpe l'attaque en phases (reconnaissance, armement, livraison, exploitation, installation, commande et contrôle, action). Chaque phase est une occasion de détection : briser UN maillon suffit à casser la chaîne.

### Question 6 : Le serveur de Command & Control
À quoi sert un serveur de « Command & Control » (C2) pour un attaquant ?

* A. À héberger le site vitrine officiel de l'entreprise ciblée.
* B. À piloter à distance les machines compromises et à recevoir les données exfiltrées.
* C. À certifier les mises à jour logicielles légitimes.
* **Réponse correcte : B**
* *Explication* : Le C2 est le poste de commandement externe de l'attaquant. C'est pourquoi la détection surveille les connexions sortantes inhabituelles : une machine interne qui « téléphone » régulièrement à un serveur inconnu est un signal majeur.

### Question 7 : La leçon de WannaCry (2017)
Le ver-rançongiciel WannaCry a frappé en mai 2017 en exploitant la faille EternalBlue. Quel fait rend ce cas si instructif ?

* A. La faille était inconnue de tous : aucune défense n'était possible.
* B. Le correctif Microsoft (MS17-010) était disponible depuis près de deux mois : les victimes étaient celles qui n'avaient pas patché.
* C. L'attaque ne visait que des particuliers.
* **Réponse correcte : B**
* *Explication* : WannaCry est la démonstration mondiale du coût du non-patching : hôpitaux britanniques (NHS), usines et entreprises paralysés par une faille corrigée des semaines plus tôt. La gestion des correctifs est une défense de premier plan.

### Question 8 : La leçon de NotPetya (2017)
NotPetya s'est propagé via la mise à jour piégée d'un logiciel de comptabilité ukrainien (MeDoc) et a causé des milliards de dollars de dégâts mondiaux (dont ~250 M€ pour Saint-Gobain). Quelles caractéristiques le distinguent ?

* A. C'était un rançongiciel classique dont les victimes ont récupéré leurs données en payant.
* B. C'était un destructeur déguisé en rançongiciel, diffusé par la chaîne d'approvisionnement logicielle.
* C. Il ne s'est jamais propagé hors d'Ukraine.
* **Réponse correcte : B**
* *Explication* : Payer ne servait à rien : NotPetya détruisait sans possibilité de déchiffrement. Et son vecteur — la mise à jour d'un logiciel légitime — annonce les attaques par chaîne d'approvisionnement (SolarWinds en B16).

### Question 9 : Reconnaître une injection SQL
Quel élément dans une requête web trahit une tentative d'injection SQL ?

* A. `GET /images/logo.png`
* B. `GET /product.php?id=1' OR 1=1--`
* C. `GET /contact.html`
* **Réponse correcte : B**
* *Explication* : L'apostrophe qui casse la syntaxe, la condition toujours vraie `OR 1=1` et le commentaire `--` sont la signature classique : l'attaquant injecte du code SQL dans un paramètre pour manipuler la base de données.

### Question 10 : Le vecteur d'attaque n°1
Selon les rapports d'activité de Cybermalveillance.gouv.fr, quel vecteur reste, année après année, la première cause d'attaque signalée ?

* A. L'hameçonnage (phishing) et ses variantes.
* B. Le piratage des objets connectés domestiques.
* C. Les attaques par satellite.
* **Réponse correcte : A**
* *Explication* : L'hameçonnage domine les signalements car il exploite le maillon humain, présent dans toutes les organisations. C'est pourquoi la sensibilisation (B04) est un contrôle de sécurité à part entière.

---

## Session B04 : Ingénierie sociale & facteur humain

### Question 1 : Le spear-phishing (harponnage)
Quelle est la différence entre un e-mail de phishing classique et un e-mail de spear-phishing ?

* A. Le spear-phishing contient obligatoirement une pièce jointe de type exécutable (.exe).
* B. Le spear-phishing est ultra-ciblé, rédigé sur mesure pour une victime précise en exploitant des détails professionnels réels.
* C. Le phishing classique est envoyé uniquement par SMS (smishing).
* **Réponse correcte : B**
* *Explication* : Le harponneur se renseigne sur sa victime (LinkedIn, site de l'entreprise) pour usurper l'identité d'un contact réel et rendre son message extrêmement crédible — d'où un taux de réussite bien supérieur au phishing de masse.

### Question 2 : Le concept de Tailgating (talonnage)
En sécurité physique, qu'est-ce que le « tailgating » ?

* A. Espionner l'écran d'un salarié à son insu par-dessus son épaule.
* B. Suivre de près un employé habilité pour franchir une porte sécurisée sans présenter de badge.
* C. Fouiller les poubelles d'une entreprise pour y trouver des mots de passe jetés.
* **Réponse correcte : B**
* *Explication* : Le talonnage exploite la politesse ou l'inattention : l'intrus profite de la porte ouverte par un badge légitime. La parade est autant culturelle (oser demander le badge) que technique (sas unipersonnel).

### Question 3 : Le smishing
Quel terme désigne l'hameçonnage réalisé par SMS ?

* A. Le vishing.
* B. Le smishing.
* C. Le spoofing.
* **Réponse correcte : B**
* *Explication* : SMS + phishing = smishing (faux avis de livraison, fausse alerte bancaire). Le canal change, les réflexes restent : ne jamais cliquer, passer par l'application ou le site officiel.

### Question 4 : Le vishing
Quel terme désigne l'ingénierie sociale menée par téléphone pour extorquer informations ou actions ?

* A. Le vishing (hameçonnage vocal).
* B. Le pharming.
* C. Le talonnage.
* **Réponse correcte : A**
* *Explication* : Le vishing (voice + phishing) usurpe souvent un support informatique, une banque ou un dirigeant. La voix crée une pression d'urgence que l'e-mail n'a pas — et les outils de clonage vocal aggravent la menace.

### Question 5 : La fraude au président — le cas Pathé (2018)
La filiale néerlandaise de Pathé a viré environ 19 M€ à des escrocs se faisant passer pour la direction du groupe. Quel contrôle organisationnel aurait bloqué cette fraude ?

* A. Un antivirus plus récent sur les postes de la direction financière.
* B. Une procédure incontournable de double validation et de contre-vérification par un canal indépendant pour tout virement inhabituel.
* C. Un pare-feu de nouvelle génération.
* **Réponse correcte : B**
* *Explication* : La fraude au président n'exploite aucune faille technique — uniquement l'autorité et l'urgence. Seule une procédure que PERSONNE ne peut court-circuiter (rappel du donneur d'ordre à un numéro connu, double signature) la neutralise.

### Question 6 : Le deepfake — le cas Arup (2024)
Un employé du cabinet Arup a viré ~25 M$ après une visioconférence où dirigeants et collègues étaient en réalité des deepfakes. Qu'est-ce que ce cas change aux règles de vérification ?

* A. Rien : les visioconférences restent une preuve d'identité fiable.
* B. Voir et entendre ne suffit plus : la vérification doit passer par un canal indépendant (rappel à un numéro connu, code convenu).
* C. Il faut interdire toutes les visioconférences.
* **Réponse correcte : B**
* *Explication* : L'IA générative fabrique des visages et des voix crédibles en direct. Le contre-appel sur un canal séparé, établi à l'avance, redevient LA vérification de référence — l'image ne prouve plus rien.

### Question 7 : Les leviers psychologiques
Quels sont les deux leviers psychologiques les plus exploités par l'ingénierie sociale ?

* A. L'humour et la curiosité scientifique.
* B. L'autorité (un « supérieur » ordonne) et l'urgence (agir vite, sans réfléchir ni vérifier).
* C. La flatterie et la nostalgie.
* **Réponse correcte : B**
* *Explication* : « C'est le PDG, c'est urgent, c'est confidentiel » : autorité + urgence + secret court-circuitent la réflexion et isolent la victime. Reconnaître ce cocktail est le premier réflexe défensif.

### Question 8 : La culture du signalement
Pourquoi une politique de signalement « sans blâme » des clics suspects renforce-t-elle la sécurité ?

* A. Parce qu'elle permet de licencier plus facilement les salariés imprudents.
* B. Parce qu'un salarié qui n'a pas peur d'être sanctionné signale immédiatement — et transforme une compromission silencieuse en alerte précoce.
* C. Parce qu'elle dispense de former les équipes.
* **Réponse correcte : B**
* *Explication* : La honte et la peur retardent le signalement, offrant des heures précieuses à l'attaquant. Le salarié qui a cliqué et alerte en 5 minutes est un capteur de sécurité, pas un coupable.

### Question 9 : Le renseignement en sources ouvertes
Que désigne l'OSINT (terme officiel français : renseignement d'origine sources ouvertes, ROSO) dans la préparation d'une attaque ?

* A. La collecte d'informations publiques (réseaux sociaux, site web, annuaires) pour personnaliser l'attaque.
* B. L'achat de données volées sur le dark web.
* C. L'interception des communications téléphoniques.
* **Réponse correcte : A**
* *Explication* : Organigramme sur le site web, poste et vacances sur LinkedIn : tout est légal et public. C'est la matière première du spear-phishing — d'où l'intérêt de maîtriser son empreinte publique.

### Question 10 : Le contre-appel
En quoi consiste le réflexe du « contre-appel » face à une demande sensible inattendue ?

* A. Répondre à l'e-mail reçu pour demander confirmation.
* B. Rappeler le demandeur supposé sur un numéro déjà connu et vérifié (annuaire interne), jamais sur les coordonnées fournies dans le message.
* C. Attendre 24 heures avant d'exécuter la demande.
* **Réponse correcte : B**
* *Explication* : Répondre au message ou appeler le numéro qu'il contient revient à demander à l'escroc s'il est honnête. Le canal de vérification doit être indépendant du canal de la demande.

---

## Session B05 : Fondations réseau pour la sécurité

### Question 1 : Rôle du protocole ARP
Quel est le rôle du protocole ARP (Address Resolution Protocol) sur un réseau local ?

* A. Traduire une adresse IP logique en adresse MAC physique.
* B. Assurer la distribution dynamique d'adresses IP aux hôtes.
* C. Résoudre un nom de domaine en adresse IP.
* **Réponse correcte : A**
* *Explication* : ARP fait le lien entre la couche 3 (adresse IP) et la couche 2 (adresse MAC). DHCP distribue les IP, DNS résout les noms de domaine.

### Question 2 : Le protocole DNS
Pourquoi le protocole DNS représente-t-il une cible et un vecteur d'attaque de choix ?

* A. Parce qu'il est responsable du chiffrement des fichiers locaux.
* B. Parce qu'un attaquant peut falsifier les réponses DNS (DNS spoofing) pour rediriger les utilisateurs vers de faux sites.
* C. Parce qu'il fonctionne uniquement sans connexion Internet.
* **Réponse correcte : B**
* *Explication* : Si un pirate falsifie la réponse DNS (empoisonnement de cache), taper « mabanque.fr » mène au serveur du pirate — qui n'a plus qu'à recueillir les identifiants saisis.

### Question 3 : L'adresse MAC
Qu'est-ce qu'une adresse MAC ?

* A. L'identifiant physique unique gravé en usine sur chaque carte réseau.
* B. L'adresse postale du siège social d'une entreprise.
* C. Un identifiant attribué dynamiquement par le fournisseur d'accès.
* **Réponse correcte : A**
* *Explication* : L'adresse MAC identifie le matériel sur le réseau local (couche 2), quand l'adresse IP identifie la machine logiquement (couche 3) — deux étages complémentaires du dialogue réseau.

### Question 4 : L'adresse IP
Quel rôle joue l'adresse IP dans un réseau ?

* A. Elle chiffre les communications entre deux machines.
* B. Elle identifie logiquement chaque machine et permet le routage des paquets jusqu'à elle.
* C. Elle stocke les mots de passe de la machine.
* **Réponse correcte : B**
* *Explication* : L'adresse IP est l'adresse postale logique de la machine : c'est elle que les routeurs lisent pour acheminer chaque paquet — et elle que l'analyste retrouve dans les journaux (B17).

### Question 5 : Le champ TTL
À quoi sert la valeur TTL (Time To Live) dans l'en-tête d'un paquet IP ?

* A. À indiquer la durée de validité du certificat TLS.
* B. À limiter le nombre de sauts de routeurs avant destruction du paquet, évitant qu'il ne circule indéfiniment.
* C. À mesurer le temps de connexion d'un utilisateur.
* **Réponse correcte : B**
* *Explication* : Chaque routeur traversé décrémente le TTL ; à zéro, le paquet est détruit. Ce mécanisme évite les boucles infinies — et sert d'indice aux outils de diagnostic comme traceroute.

### Question 6 : Le tunneling DNS
Pourquoi le « DNS tunneling » est-il une technique d'exfiltration discrète ?

* A. Parce que le trafic DNS est rarement bloqué et peu inspecté : y encapsuler des données permet de contourner les pare-feux.
* B. Parce que le DNS chiffre nativement toutes les données.
* C. Parce que le DNS ne laisse aucune trace dans les journaux.
* **Réponse correcte : A**
* *Explication* : Presque tous les réseaux laissent sortir le DNS, indispensable au fonctionnement d'Internet. Un attaquant peut y cacher des données volées, requête après requête — d'où la surveillance des requêtes DNS anormales (volume, longueur, fréquence).

### Question 7 : Les ports exposés
Pourquoi laisser les ports 22 (SSH) et 3389 (RDP) ouverts sur l'adresse IP publique d'une PME est-il si dangereux ?

* A. Cela ralentit fortement la connexion Internet.
* B. Ce sont des portes d'administration directe : des robots les scannent en permanence et testent des mots de passe en continu.
* C. Ces ports sont réservés par la loi aux administrations publiques.
* **Réponse correcte : B**
* *Explication* : L'accès distant exposé avec mot de passe faible est un vecteur d'intrusion majeur constaté par l'ANSSI sur les PME. La parade : fermer ces ports et passer par un VPN avec MFA.

### Question 8 : TV5 Monde (2015)
Lors de l'attaque de TV5 Monde (2015), qu'est-ce qui a permis de sauver la chaîne de la destruction complète ?

* A. Le paiement rapide d'une rançon.
* B. La déconnexion d'urgence des systèmes et l'isolement du réseau, suivis d'une reconstruction avec segmentation stricte.
* C. Le redémarrage simple de tous les serveurs.
* **Réponse correcte : B**
* *Explication* : La diffusion a été coupée mais la déconnexion d'urgence a stoppé la destruction. La reconstruction a imposé la segmentation et la séparation des réseaux (bureautique vs diffusion) — l'architecture comme défense.

### Question 9 : Les couches réseau
À quelle « couche » du dialogue réseau opère un routeur ?

* A. La couche physique : il régénère le signal électrique.
* B. La couche réseau (couche 3) : il lit les adresses IP pour acheminer les paquets entre réseaux.
* C. La couche application : il interprète les pages web.
* **Réponse correcte : B**
* *Explication* : Le commutateur travaille en couche 2 (adresses MAC, réseau local), le routeur en couche 3 (adresses IP, interconnexion des réseaux) : savoir qui lit quoi aide à comprendre où placer les défenses.

### Question 10 : Le Wi-Fi public
Quel est le risque principal d'utiliser le Wi-Fi ouvert d'un aéroport pour consulter des données professionnelles, et quelle parade s'impose ?

* A. Aucun risque : le Wi-Fi public est surveillé par les autorités.
* B. L'interception des communications par un tiers (réseau non chiffré ou point d'accès piégé) ; la parade est le VPN d'entreprise qui chiffre tout le trafic.
* C. La surchauffe de l'ordinateur portable ; la parade est un support ventilé.
* **Réponse correcte : B**
* *Explication* : Sur un réseau ouvert, un attaquant peut écouter le trafic non chiffré ou monter un faux point d'accès jumeau. Le tunnel VPN chiffre l'intégralité des échanges, rendant l'écoute inutile.

---

## Session B06 : Défenses réseau

### Question 1 : IDS vs IPS
Quelle est la différence de réaction fondamentale entre un IDS (Intrusion Detection System) et un IPS (Intrusion Prevention System) ?

* A. L'IDS bloque l'attaque tandis que l'IPS génère uniquement une alerte de sécurité.
* B. L'IDS génère une alerte sans bloquer le trafic, tandis que l'IPS bloque activement le trafic jugé malveillant.
* C. L'IDS analyse uniquement les disques durs locaux et l'IPS analyse les réseaux.
* **Réponse correcte : B**
* *Explication* : L'IDS est passif (il écoute une copie du trafic et alerte) ; l'IPS est actif (placé en coupure, il bloque en direct) — avec le risque du faux positif qui coupe un flux légitime.

### Question 2 : L'architecture DMZ
Qu'est-ce qui caractérise l'isolement d'une DMZ réseau ?

* A. La DMZ n'a aucun contact avec Internet pour être totalement étanche.
* B. Elle contient les serveurs accessibles depuis Internet et le pare-feu interdit toute connexion initiée depuis la DMZ vers le réseau interne.
* C. Elle est réservée aux ordinateurs personnels des salariés en Wi-Fi.
* **Réponse correcte : B**
* *Explication* : La DMZ est la zone tampon : si un serveur exposé y est compromis, l'attaquant ne doit pas pouvoir rebondir vers le LAN — d'où la règle d'or d'interdiction des flux initiés DMZ → interne.

### Question 3 : Le rejet par défaut
Que signifie la politique « default deny » sur un pare-feu ?

* A. Refuser par défaut toutes les communications, puis n'autoriser explicitement que les flux nécessaires.
* B. Autoriser tout le trafic par défaut et bloquer au cas par cas.
* C. Refuser les mises à jour du pare-feu.
* **Réponse correcte : A**
* *Explication* : On liste ce qui est permis, tout le reste est interdit. L'approche inverse laisse mécaniquement passer ce qu'on n'a pas prévu — c'est-à-dire précisément l'imprévu qu'exploite l'attaquant.

### Question 4 : La leçon de Target (2013)
Chez Target, des attaquants entrés via un prestataire de climatisation ont atteint les systèmes d'encaissement (40 millions de cartes volées). Quelle défense réseau aurait cassé cette attaque ?

* A. Un antivirus plus récent sur les caisses enregistreuses.
* B. La segmentation : le réseau des prestataires ne devait avoir aucun chemin vers les systèmes de paiement.
* C. Des mots de passe plus longs pour les employés du siège.
* **Réponse correcte : B**
* *Explication* : Le problème n'était pas l'entrée (un prestataire se fera toujours piéger un jour) mais la circulation : dans un réseau segmenté, l'accès « climatisation » ne mène pas aux caisses. Cloisonner limite l'explosion.

### Question 5 : Le thermomètre du casino (2017)
Dans l'affaire rapportée par Darktrace (2018), des attaquants ont exfiltré des données d'un casino via le thermomètre connecté d'un aquarium (incident de 2017). Quelle leçon d'architecture ce cas illustre-t-il ?

* A. Il faut interdire les aquariums dans les entreprises.
* B. Tout objet connecté est un point d'entrée : l'IoT doit vivre dans un segment réseau isolé, sans chemin vers les données sensibles.
* C. Les thermomètres doivent être mis à jour toutes les heures.
* **Réponse correcte : B**
* *Explication* : L'IoT (capteurs, caméras, badgeuses) est rarement patché et souvent oublié de l'inventaire. Le placer dans son propre segment, cloisonné, transforme un point d'entrée en cul-de-sac.

### Question 6 : Le rôle des VLANs
À quoi servent les VLANs dans une architecture de sécurité ?

* A. À augmenter le débit Internet de l'entreprise.
* B. À découper logiquement un réseau physique en zones étanches (compta, entrepôt, invités) dont les échanges passent par un point de contrôle.
* C. À remplacer le câblage par du sans-fil.
* **Réponse correcte : B**
* *Explication* : Le VLAN cloisonne sans multiplier le matériel : chaque population vit dans sa zone, et les flux inter-zones traversent le pare-feu qui applique la politique — la segmentation à coût maîtrisé.

### Question 7 : Le pare-feu applicatif web (WAF)
Contre quoi un WAF protège-t-il spécifiquement ?

* A. Contre le vol physique des serveurs web.
* B. Contre les attaques applicatives visant les sites web : injections SQL, traversées de répertoires, scripts malveillants.
* C. Contre les coupures d'électricité du centre de données.
* **Réponse correcte : B**
* *Explication* : Le pare-feu réseau filtre par ports et adresses ; le WAF inspecte le CONTENU des requêtes HTTP et bloque les motifs d'attaque applicative — la défense dédiée du serveur web (revoyez l'Atelier 4 de B17).

### Question 8 : Le déploiement prudent d'un IPS
Pourquoi active-t-on souvent un IPS d'abord en mode détection avant le mode blocage sur un système critique ?

* A. Parce que le mode blocage est plus cher en licence.
* B. Parce qu'un faux positif en mode blocage couperait du trafic légitime — sur un système critique (hôpital, industrie), le remède peut faire plus de dégâts que l'attaque.
* C. Parce que le mode détection consomme moins d'électricité.
* **Réponse correcte : B**
* *Explication* : On observe d'abord ce que les règles déclencheraient, on ajuste, puis on active le blocage règle par règle. Prudence opérationnelle : la disponibilité est aussi un pilier de la sécurité.

### Question 9 : Le modèle Zero Trust
Quel principe résume le modèle « Zero Trust » ?

* A. Ne jamais faire confiance par défaut, vérifier en continu chaque utilisateur et chaque appareil (« never trust, always verify »).
* B. Faire confiance à tout ce qui se trouve à l'intérieur du réseau de l'entreprise.
* C. Interdire tout accès distant aux salariés.
* **Réponse correcte : A**
* *Explication* : Le Zero Trust abandonne l'idée d'un « intérieur sûr » : chaque accès est authentifié, autorisé et évalué en contexte, qu'il vienne du bureau ou d'ailleurs — la réponse à des périmètres devenus poreux.

### Question 10 : Le pare-feu local
Pourquoi activer le pare-feu local de chaque poste alors qu'un pare-feu périmétrique protège déjà l'entreprise ?

* A. Pour ralentir volontairement le réseau local.
* B. Parce que le pare-feu périmétrique ne voit pas le trafic ENTRE machines internes : le pare-feu local bloque les mouvements latéraux d'un attaquant déjà entré.
* C. Pour remplacer l'antivirus, devenu inutile.
* **Réponse correcte : B**
* *Explication* : Une fois une machine compromise, l'attaquant se propage de poste en poste (~62 minutes en moyenne avant le mouvement latéral — CrowdStrike 2024). Les pare-feux locaux transforment chaque poste en compartiment étanche.

---

## Session B07 : Communications sécurisées

### Question 1 : Le rôle du protocole TLS
Quel pilier de la sécurité TLS garantit-il lors d'une connexion bancaire en HTTPS ?

* A. La disponibilité permanente du site web de la banque.
* B. La confidentialité par chiffrement et l'authenticité du serveur via son certificat numérique.
* C. Le stockage sécurisé des données sur le serveur de la banque.
* **Réponse correcte : B**
* *Explication* : TLS chiffre les échanges (Confidentialité) et prouve l'identité du serveur grâce à un certificat émis par une Autorité de Certification (Authenticité). Il ne protège pas ce qui se passe sur le serveur lui-même.

### Question 2 : VPN SSL vs VPN IPsec
Dans quel cas privilégie-t-on le déploiement d'un VPN IPsec ?

* A. Pour permettre à un commercial de se connecter à Microsoft 365 depuis un simple navigateur web sans logiciel.
* B. Pour interconnecter de manière permanente et chiffrée deux réseaux locaux de sites géographiques distincts (site-à-site).
* C. Pour scanner les virus présents sur une clé USB distante.
* **Réponse correcte : B**
* *Explication* : IPsec opère au niveau de la couche réseau et convient aux tunnels permanents routeur-à-routeur. Le VPN SSL est souvent préféré pour les connexions ponctuelles d'utilisateurs nomades.

### Question 3 : Le handshake TLS
Que se passe-t-il durant le « handshake » TLS ?

* A. Le client et le serveur négocient les paramètres de chiffrement, le serveur prouve son identité, et une clé de session est établie.
* B. Le serveur envoie son mot de passe administrateur au client.
* C. Les deux machines échangent leurs adresses MAC.
* **Réponse correcte : A**
* *Explication* : Cette poignée de main initiale combine chiffrement asymétrique (authentification, échange de clés) puis symétrique (rapidité pour la session) — le meilleur des deux mondes vus en B10.

### Question 4 : L'Autorité de Certification
Quel est le rôle d'une CA (Certificate Authority) ?

* A. Générer, valider et révoquer les certificats numériques qui prouvent l'identité des serveurs.
* B. Héberger les sites web des grandes entreprises.
* C. Distribuer les adresses IP publiques.
* **Réponse correcte : A**
* *Explication* : La CA est le tiers de confiance : votre navigateur croit le certificat de « mabanque.fr » parce qu'une CA reconnue l'a signé. Toute la confiance du web repose sur ce mécanisme — d'où la gravité d'une CA compromise.

### Question 5 : Ce que dit (et ne dit pas) le cadenas HTTPS
Que garantit le cadenas HTTPS affiché par le navigateur ?

* A. Que le site est honnête et sans danger.
* B. Que la connexion est chiffrée et que le serveur correspond bien au nom de domaine affiché — rien de plus.
* C. Que le site est hébergé en France.
* **Réponse correcte : B**
* *Explication* : Un site d'hameçonnage peut parfaitement avoir son cadenas : la connexion vers l'escroc est alors… chiffrée. Le cadenas dit « personne n'écoute entre vous et CE site », pas « ce site est digne de confiance ».

### Question 6 : Le serveur RADIUS
À quoi sert un serveur RADIUS dans un réseau d'entreprise ?

* A. À centraliser l'authentification, les autorisations et la traçabilité des accès (par exemple pour le Wi-Fi d'entreprise en 802.1X).
* B. À diffuser la radio d'entreprise sur les postes de travail.
* C. À mesurer le rayon de couverture des bornes Wi-Fi.
* **Réponse correcte : A**
* *Explication* : RADIUS vérifie l'identité (comptes d'annuaire, certificats) avant d'ouvrir l'accès réseau et trace qui s'est connecté où — l'entrée du réseau sous contrôle d'identité, plutôt qu'un mot de passe Wi-Fi partagé.

### Question 7 : La leçon de Firesheep (2010)
L'extension Firesheep (2010) permettait à n'importe qui, sur un Wi-Fi ouvert, de voler les sessions Facebook ou Twitter des voisins. Qu'a provoqué cette démonstration ?

* A. L'interdiction mondiale des réseaux Wi-Fi publics.
* B. L'accélération de la généralisation du HTTPS sur l'ensemble des grands sites web.
* C. La fin des cookies de session.
* **Réponse correcte : B**
* *Explication* : Firesheep a rendu visible au grand public ce que les experts savaient : sans chiffrement de bout en bout de la session, le vol est trivial. En rendant l'attaque facile, elle a forcé l'industrie à chiffrer par défaut.

### Question 8 : La leçon de DigiNotar (2011)
L'autorité de certification néerlandaise DigiNotar a été piratée en 2011 ; de faux certificats (dont un pour Google) ont servi à espionner des utilisateurs. Qu'illustre cette affaire ?

* A. Que les certificats numériques sont inutiles.
* B. Que la compromission d'un tiers de confiance fait s'effondrer toute la chaîne : DigiNotar a été retirée des navigateurs et a fait faillite.
* C. Que seuls les petits sites ont besoin de certificats.
* **Réponse correcte : B**
* *Explication* : La confiance du web est déléguée aux CA : quand l'une d'elles est compromise, les navigateurs n'ont d'autre choix que de la bannir — mort commerciale immédiate, et rappel que la confiance se gagne en la protégeant.

### Question 9 : SSL et TLS
Quelle est la relation entre SSL et TLS ?

* A. SSL est la version moderne et recommandée de TLS.
* B. TLS succède à SSL, un protocole plus ancien aujourd'hui obsolète et à proscrire.
* C. Ce sont deux protocoles concurrents toujours utilisés à parts égales.
* **Réponse correcte : B**
* *Explication* : Les versions de SSL sont cassées et dépréciées de longue date : les configurations modernes n'acceptent que TLS (1.2 et 1.3). Le terme « certificat SSL » survit dans le langage courant, mais le protocole en service est TLS.

### Question 10 : Ce qu'un VPN ne protège pas
Un salarié se connecte au VPN d'entreprise depuis un ordinateur déjà infecté par un logiciel espion. Que protège le VPN dans cette situation ?

* A. Tout : le VPN neutralise le logiciel espion.
* B. Seulement le transport : le tunnel est chiffré, mais l'espion voit tout ce que fait le poste — le VPN peut même lui ouvrir la porte du réseau interne.
* C. Rien : le VPN ne sert à rien dans tous les cas.
* **Réponse correcte : B**
* *Explication* : Le VPN chiffre le trajet, pas les extrémités. Un poste compromis reste compromis — c'est pourquoi l'accès distant se conjugue avec la santé du poste (EDR, mises à jour) et le MFA.

---

## Session B08 : Durcissement des systèmes & endpoints

### Question 1 : La gestion des ports réseau
Pourquoi est-il crucial de fermer systématiquement les ports réseau inutilisés (ex. RDP 3389, SSH 22, SMB 445) sur un serveur ?

* A. Pour réduire la consommation électrique de la carte réseau.
* B. Pour minimiser la surface d'attaque en fermant les points d'entrée potentiels exploitables par un malware ou un pirate.
* C. Pour accélérer la vitesse de connexion Internet des ordinateurs du réseau.
* **Réponse correcte : B**
* *Explication* : Chaque port ouvert est un service à l'écoute ; s'il a une vulnérabilité ou des identifiants faibles, c'est une porte d'entrée. Fermer les ports non indispensables réduit la surface d'attaque.

### Question 2 : Le rôle d'un pare-feu local
Quelle est l'utilité d'activer le pare-feu local sur chaque poste, en plus du pare-feu physique à la frontière d'Internet ?

* A. Bloquer les virus présents sur les clés USB insérées localement.
* B. Empêcher la propagation latérale d'un attaquant ou d'un ver informatique au sein du même réseau local.
* C. Rendre obligatoire la double authentification de l'utilisateur.
* **Réponse correcte : B**
* *Explication* : Le pare-feu périmétrique protège de l'extérieur, mais n'empêche pas une machine compromise d'attaquer ses voisines. Les pare-feux locaux bloquent ces mouvements latéraux internes.

### Question 3 : Les stratégies de groupe (GPO)
À quoi servent les GPO (Group Policy Objects) dans un environnement Active Directory ?

* A. À configurer de manière centralisée les règles de sécurité d'un parc de machines Windows (mots de passe, verrouillage, restrictions logicielles).
* B. À grouper les employés par service dans l'organigramme RH.
* C. À optimiser la vitesse des disques durs des serveurs.
* **Réponse correcte : A**
* *Explication* : La GPO applique une politique uniforme à des centaines de machines d'un coup : c'est l'outil du durcissement à l'échelle — une règle décidée une fois, appliquée partout, sans dépendre de la discipline individuelle.

### Question 4 : Le durcissement (hardening)
Que recouvre le « durcissement » d'un système d'exploitation ?

* A. L'installation d'un boîtier antichoc sur les serveurs.
* B. La réduction de la surface d'attaque : désactiver les services inutiles, fermer les ports, retirer les comptes par défaut, appliquer les configurations sécurisées.
* C. L'augmentation de la puissance du processeur.
* **Réponse correcte : B**
* *Explication* : Un système sorti de boîte est configuré pour la commodité, pas pour la sécurité. Durcir, c'est enlever tout ce qui n'est pas nécessaire — chaque service désactivé est une porte de moins à surveiller.

### Question 5 : EDR vs antivirus classique
Qu'apporte un EDR (Endpoint Detection and Response) par rapport à un antivirus à signatures ?

* A. Il est simplement moins cher.
* B. Il détecte les comportements suspects (chaînes de processus, actions anormales) même sans signature connue, et permet d'isoler la machine à distance.
* C. Il supprime le besoin de mises à jour.
* **Réponse correcte : B**
* *Explication* : L'antivirus reconnaît des empreintes connues ; l'EDR observe les comportements (Word qui lance PowerShell, chiffrement massif de fichiers) — indispensable contre les attaques inédites et les malwares sans fichier.

### Question 6 : Le moindre privilège
Que signifie le principe du moindre privilège ?

* A. Donner à chaque utilisateur et processus uniquement les droits strictement nécessaires à sa fonction, rien de plus.
* B. Réserver tous les droits d'administration au PDG.
* C. Supprimer tous les comptes administrateurs de l'entreprise.
* **Réponse correcte : A**
* *Explication* : Un compte compromis ne donne à l'attaquant que ce que ce compte possède : moins il possède, moins l'attaque rapporte. Corollaire pratique : les administrateurs utilisent un compte bureautique séparé au quotidien.

### Question 7 : Colonial Pipeline (2021)
L'attaque de Colonial Pipeline (mai 2021), qui a paralysé l'approvisionnement en carburant de la côte Est américaine, a commencé par un accès VPN. Quelles défenses élémentaires manquaient ?

* A. Un antivirus sur les serveurs de facturation.
* B. Le MFA sur l'accès VPN et l'hygiène des comptes : le mot de passe d'un compte VPN dormant, réutilisé ailleurs, a suffi.
* C. Un pare-feu physique plus récent.
* **Réponse correcte : B**
* *Explication* : Un identifiant retrouvé dans une fuite, un VPN sans second facteur, un compte jamais désactivé : trois négligences d'hygiène élémentaire. Le MFA seul aurait probablement stoppé l'intrusion.

### Question 8 : Atlanta (2018)
La ville d'Atlanta, frappée par le rançongiciel SamSam (2018) après des intrusions par force brute, a refusé de payer ~51 000 $ de rançon… et dépensé des millions en reconstruction. Que retenir ?

* A. Il aurait fallu payer : c'était plus économique.
* B. La dette technique se paie au centuple en crise : systèmes obsolètes et non durcis ont transformé un incident en reconstruction complète — la prévention coûte toujours moins cher.
* C. Les administrations ne sont jamais des cibles.
* **Réponse correcte : B**
* *Explication* : Les audits préalables avaient signalé les faiblesses (systèmes non patchés, mots de passe faibles). L'écart entre la rançon et la facture finale mesure le coût de l'impréparation — pas celui du refus de payer, qui reste la position recommandée.

### Question 9 : Le premier contrôle de l'hygiène
Selon les guides d'hygiène informatique de l'ANSSI, quelle mesure vient en tout premier ?

* A. L'achat d'un SIEM performant.
* B. L'inventaire complet et à jour des matériels et logiciels : on ne protège que ce qu'on sait posséder.
* C. Le chiffrement de tous les disques durs.
* **Réponse correcte : B**
* *Explication* : Sans inventaire, impossible de savoir quoi patcher, quoi surveiller, quoi durcir. Log4Shell (B18) l'a démontré mondialement : la première question de crise fut partout « où utilise-t-on cette bibliothèque ? ».

### Question 10 : Le contrôle de compte utilisateur (UAC)
À quoi sert l'UAC (User Account Control) de Windows ?

* A. À compter le nombre d'utilisateurs connectés simultanément.
* B. À demander une confirmation (ou un mot de passe administrateur) avant toute action nécessitant une élévation de privilèges.
* C. À contrôler les horaires de connexion des salariés.
* **Réponse correcte : B**
* *Explication* : L'UAC matérialise le moindre privilège au quotidien : même connecté, on ne modifie pas le système sans élévation explicite — un malware exécuté par l'utilisateur se heurte à cette barrière supplémentaire.

---

## Session B09 : Gestion des identités et des accès (IAM)

### Question 1 : Le contrôle d'accès basé sur les rôles (RBAC)
Quelle règle illustre la mise en œuvre d'un modèle RBAC ?

* A. Donner les accès d'un dossier confidentiel à un salarié sur décision individuelle du responsable.
* B. Assigner des droits d'accès à des rôles (ex. « Comptable », « RH ») et affecter les salariés à ces rôles selon leur fonction officielle.
* C. Exiger un mot de passe de 18 caractères pour tous les collaborateurs de l'entreprise.
* **Réponse correcte : B**
* *Explication* : Le RBAC associe les droits aux fonctions métier plutôt qu'aux individus : cohérence garantie, et gestion des arrivées, mobilités et départs considérablement simplifiée.

### Question 2 : La compromission d'un compte de facturation
Quelle mesure technique immédiate permet de neutraliser la compromission par hameçonnage d'un compte cloud de messagerie ?

* A. Désinstaller le logiciel de messagerie de l'ordinateur portable du commercial.
* B. Révoquer toutes les sessions actives du compte et activer l'authentification multifacteur (MFA).
* C. Installer un nouveau pare-feu réseau à la périphérie du siège social.
* **Réponse correcte : B**
* *Explication* : Le mot de passe volé permet de se connecter de n'importe où : fermer les sessions actives coupe l'accès en cours, et le MFA bloque les reconnexions — le pirate ne possède pas le second facteur.

### Question 3 : La hiérarchie des facteurs MFA
Parmi ces méthodes de MFA, laquelle résiste le mieux à l'hameçonnage ?

* A. Le code reçu par SMS.
* B. La notification push simple sur smartphone.
* C. La clé de sécurité physique FIDO2 (ou passkey).
* **Réponse correcte : C**
* *Explication* : Le SMS peut être intercepté (échange de carte SIM), la notification push peut être approuvée par lassitude — la clé FIDO2, elle, vérifie cryptographiquement le site et ne peut pas être « donnée » à un faux site : elle est résistante au phishing par conception.

### Question 4 : La fatigue MFA — le cas Uber (2022)
En 2022, un attaquant a pénétré Uber en bombardant un employé de notifications MFA puis en le contactant sur WhatsApp en se faisant passer pour le support. Quelle parade cible précisément cette technique ?

* A. Supprimer complètement le MFA, devenu contre-productif.
* B. Le « number matching » (saisir un code affiché à l'écran) et la sensibilisation : on n'approuve JAMAIS une notification qu'on n'a pas soi-même déclenchée.
* C. Changer de mot de passe chaque semaine.
* **Réponse correcte : B**
* *Explication* : La fatigue MFA exploite la lassitude, pas la technologie. Exiger une correspondance de code lie l'approbation à une connexion précise ; et la règle humaine reste : une notification non sollicitée = une alerte à signaler, pas une gêne à faire taire.

### Question 5 : Le credential stuffing — le cas 23andMe (2023)
La violation de 23andMe (2023) a commencé par du « credential stuffing ». En quoi consiste cette technique ?

* A. Tester sur un site des couples identifiant/mot de passe volés ailleurs, en pariant sur la réutilisation des mots de passe.
* B. Saturer le formulaire de connexion pour le faire tomber en panne.
* C. Voler physiquement les serveurs d'authentification.
* **Réponse correcte : A**
* *Explication* : Les comptes compromis étaient protégés par des mots de passe réutilisés et déjà fuités ailleurs. Parades : mot de passe unique par service (gestionnaire), MFA — et côté site, détection des vagues de connexions.

### Question 6 : Le SSO, bénéfice et contrepartie
Quel est le principal bénéfice ET la principale contrepartie du SSO (Single Sign-On) ?

* A. Bénéfice : moins de mots de passe à retenir et une gestion centralisée ; contrepartie : le compte SSO devient une clé maîtresse à protéger très fort (MFA obligatoire).
* B. Bénéfice : la gratuité ; contrepartie : la lenteur des connexions.
* C. Bénéfice : l'anonymat complet ; contrepartie : l'incompatibilité avec le cloud.
* **Réponse correcte : A**
* *Explication* : Une seule authentification ouvre tous les services : moins de mots de passe faibles et un point de contrôle unique — mais ce point unique concentre le risque : sa compromission ouvre tout, d'où MFA fort et surveillance renforcée.

### Question 7 : Les comptes d'administration
Pourquoi un administrateur doit-il disposer de deux comptes distincts (un compte bureautique et un compte d'administration) ?

* A. Pour recevoir deux fois plus d'e-mails.
* B. Pour que la navigation web et la messagerie — les activités les plus exposées — ne s'exécutent jamais avec des privilèges élevés.
* C. Parce que les licences logicielles l'imposent.
* **Réponse correcte : B**
* *Explication* : Un clic malheureux sur un compte administrateur donne à l'attaquant les clés du royaume. La séparation garantit qu'un hameçonnage réussi ne compromet « que » un compte standard — moindre privilège appliqué aux plus privilégiés.

### Question 8 : Le départ d'un salarié
Un administrateur système quitte l'entreprise vendredi. Que doit prévoir le processus de départ (offboarding) ?

* A. La désactivation immédiate de ses comptes et accès (VPN, cloud, badges), et la rotation des secrets partagés qu'il connaissait.
* B. Le maintien de ses accès un mois, par courtoisie.
* C. Un simple e-mail de remerciement.
* **Réponse correcte : A**
* *Explication* : Les comptes orphelins actifs sont une porte d'entrée classique (rappelez-vous le compte VPN dormant de Colonial Pipeline). L'offboarding est un processus de sécurité, pas une formalité RH.

### Question 9 : Le gestionnaire de mots de passe
Pourquoi recommander un gestionnaire de mots de passe aux équipes ?

* A. Parce qu'il permet d'utiliser le même mot de passe partout en toute sécurité.
* B. Parce qu'il rend praticable la seule politique robuste : un mot de passe long, aléatoire et UNIQUE par service — l'humain ne retient que la phrase maîtresse.
* C. Parce qu'il supprime le besoin de MFA.
* **Réponse correcte : B**
* *Explication* : Sans gestionnaire, l'unicité est humainement impossible et la réutilisation devient la norme — le terreau du credential stuffing (23andMe). Le gestionnaire industrialise l'unicité.

### Question 10 : Les trois familles de facteurs
Quelles sont les trois familles de facteurs d'authentification combinées par le MFA ?

* A. Ce que je sais (mot de passe), ce que je possède (téléphone, clé), ce que je suis (biométrie).
* B. Mon nom, mon prénom, ma date de naissance.
* C. Mon adresse IP, mon navigateur, mon fuseau horaire.
* **Réponse correcte : A**
* *Explication* : Le MFA exige au moins deux familles DIFFÉRENTES : voler le mot de passe (savoir) ne suffit plus s'il faut aussi le téléphone (possession). Deux mots de passe ne font pas un MFA — c'est deux fois la même famille.

---

## Session B10 : Cryptographie essentielle

### Question 1 : Chiffrement symétrique vs asymétrique
Quelle est la contrainte logistique majeure du chiffrement symétrique (comme AES-256) lors d'échanges entre plusieurs partenaires distants ?

* A. Il exige des serveurs surpuissants en raison de sa lenteur de calcul.
* B. Il nécessite que les deux correspondants partagent la même clé secrète en toute sécurité avant d'échanger des messages.
* C. Il ne permet pas de chiffrer des fichiers volumineux.
* **Réponse correcte : B**
* *Explication* : La même clé chiffre et déchiffre : il faut donc la transmettre sans qu'elle soit interceptée — le problème de l'échange des clés, que résout le chiffrement asymétrique (et qu'exploite le handshake TLS de B07).

### Question 2 : Le hachage des mots de passe
Pourquoi stocke-t-on les mots de passe sous forme d'empreintes de hachage (bcrypt, Argon2) avec du « sel » ?

* A. Pour que l'application puisse déchiffrer les mots de passe et les renvoyer par e-mail en cas d'oubli.
* B. Pour qu'un pirate ayant volé la base de données ne puisse pas lire les mots de passe en clair.
* C. Pour accélérer la vitesse de connexion lors de la saisie des identifiants.
* **Réponse correcte : B**
* *Explication* : Le hachage est à sens unique : on ne remonte pas au mot de passe depuis l'empreinte. Le sel rend chaque empreinte unique (même pour deux mots de passe identiques) et neutralise les tables précalculées.

### Question 3 : L'apport du chiffrement asymétrique
Quel problème le chiffrement asymétrique (paire clé publique / clé privée) résout-il ?

* A. La lenteur des connexions Internet.
* B. L'échange sécurisé : on peut publier sa clé publique à tous — seul le détenteur de la clé privée déchiffre ce qui est chiffré avec elle.
* C. La sauvegarde automatique des fichiers.
* **Réponse correcte : B**
* *Explication* : Plus besoin de canal secret pour échanger la clé : la clé publique se diffuse librement, la clé privée ne quitte jamais son propriétaire. En pratique, l'asymétrique établit la confiance, puis passe le relais au symétrique, plus rapide.

### Question 4 : La signature numérique
Que garantit la signature numérique d'un document (chiffrement de l'empreinte avec la clé privée de l'émetteur) ?

* A. La confidentialité du document.
* B. L'authenticité (l'émetteur est bien le détenteur de la clé privée) et l'intégrité (le document n'a pas été modifié depuis la signature).
* C. La disponibilité permanente du document.
* **Réponse correcte : B**
* *Explication* : Quiconque possède la clé publique peut vérifier la signature : si l'empreinte correspond, le document est intact et provient bien du signataire. La signature ne cache rien — elle prouve.

### Question 5 : La leçon d'Adobe (2013)
Lors de la fuite Adobe (2013, ~153 millions de comptes), les mots de passe étaient chiffrés (3DES en mode ECB) au lieu d'être hachés, avec les indices de mot de passe stockés en clair. Pourquoi est-ce une faute de conception ?

* A. Le chiffrement est réversible (une seule clé déchiffre tout) et le mode utilisé laissait apparaître les motifs identiques — les indices en clair ont fait le reste.
* B. 3DES est trop lent pour les connexions.
* C. Il aurait fallu stocker les mots de passe en clair, c'est plus simple.
* **Réponse correcte : A**
* *Explication* : Pour des mots de passe, on hache (irréversible, avec sel), on ne chiffre pas : le chiffrement crée un point de défaillance unique (la clé) et le mode ECB révélait quels comptes partageaient le même mot de passe — un cas d'école mondial.

### Question 6 : La leçon de LinkedIn (2012)
La fuite LinkedIn (2012) a exposé des millions d'empreintes SHA-1 **sans sel**, massivement cassées ensuite. Quelle règle moderne ce cas impose-t-il ?

* A. Ne plus utiliser de mots de passe du tout.
* B. Utiliser des fonctions dédiées aux mots de passe (bcrypt, Argon2), lentes par conception, TOUJOURS avec un sel unique par compte.
* C. Limiter les mots de passe à 8 caractères pour faciliter les vérifications.
* **Réponse correcte : B**
* *Explication* : SHA-1 est rapide — donc parfait pour l'attaquant qui teste des milliards de candidats. Les fonctions dédiées sont volontairement coûteuses, et le sel individualise chaque attaque : casser un compte n'aide pas à casser les autres.

### Question 7 : Les algorithmes à proscrire
Pourquoi MD5 et SHA-1 ne doivent-ils plus être utilisés pour des usages de sécurité ?

* A. Parce qu'ils sont trop récents et mal documentés.
* B. Parce que des collisions y sont réalisables en pratique : deux contenus différents peuvent produire la même empreinte — la garantie d'intégrité s'effondre.
* C. Parce qu'ils sont payants.
* **Réponse correcte : B**
* *Explication* : Un hachage vaut par l'impossibilité de fabriquer deux contenus à empreinte identique. MD5 et SHA-1 sont cassés sur ce point : la référence actuelle est la famille SHA-2 (ex. SHA-256) — et bcrypt/Argon2 pour les mots de passe.

### Question 8 : La puissance des GPU
Les bancs d'essai publics d'outils comme Hashcat montrent que des cartes graphiques testent des milliards d'empreintes par seconde. Quelle conséquence pratique ?

* A. Les mots de passe courts, même « complexes », tombent en minutes : la LONGUEUR (phrases de passe) et les fonctions lentes (bcrypt/Argon2) sont les vraies défenses.
* B. Il faut interdire les cartes graphiques.
* C. Aucune : les GPU ne servent qu'aux jeux vidéo.
* **Réponse correcte : A**
* *Explication* : Face à des milliards d'essais par seconde, « P@ssw0rd! » ne tient pas. Chaque caractère ajouté multiplie exponentiellement le coût de l'attaque ; et une fonction volontairement lente divise d'autant la cadence de l'attaquant.

### Question 9 : Au repos et en transit
Quelle est la différence entre le chiffrement « au repos » et « en transit » ?

* A. Au repos : les données stockées (disques, bases, sauvegardes) ; en transit : les données qui circulent sur le réseau (TLS, VPN). Les deux sont nécessaires.
* B. Au repos : le chiffrement de nuit ; en transit : le chiffrement de jour.
* C. C'est la même chose sous deux noms différents.
* **Réponse correcte : A**
* *Explication* : Un portable volé teste le chiffrement au repos (BitLocker) ; un Wi-Fi espionné teste le chiffrement en transit (TLS). Chacun protège contre des menaces différentes — l'un ne remplace jamais l'autre.

### Question 10 : Le certificat numérique
Que lie fondamentalement un certificat numérique ?

* A. Une adresse IP et un nom d'utilisateur.
* B. Une identité (nom de domaine, organisation) et une clé publique, le tout signé par une Autorité de Certification.
* C. Un mot de passe et une date d'expiration.
* **Réponse correcte : B**
* *Explication* : Le certificat est la carte d'identité cryptographique : la CA atteste que cette clé publique appartient bien à ce domaine. C'est le pont entre la cryptographie (B10) et la confiance du web (B07).

---

## Session B11 : Sécurité du cloud

### Question 1 : Le modèle de responsabilité partagée en SaaS
Dans un modèle SaaS (ex. Microsoft 365), quelle responsabilité incombe **au client** ?

* A. Assurer la sécurité physique des centres de données accueillant les serveurs.
* B. Mettre à jour les serveurs d'infrastructure sous-jacents contre les vulnérabilités de l'OS.
* C. Gérer les identités des utilisateurs, les accès et configurer la sécurité des données stockées.
* **Réponse correcte : C**
* *Explication* : En SaaS, le fournisseur gère l'infrastructure, le réseau et l'application ; le client reste responsable de SES utilisateurs (identités, MFA), de SES partages et de SES données. On externalise l'exploitation, jamais la responsabilité.

### Question 2 : La menace du « Shadow IT »
Pourquoi le Shadow IT (applications cloud non validées par l'informatique) représente-t-il un danger ?

* A. Parce qu'il augmente la facture énergétique du réseau local de l'entreprise.
* B. Parce que des données confidentielles peuvent se retrouver sur des plateformes externes non maîtrisées et non conformes au RGPD.
* C. Parce qu'il ralentit le fonctionnement général de la suite bureautique officielle.
* **Réponse correcte : B**
* *Explication* : Fichiers clients sur un compte personnel, données sensibles collées dans une IA générative grand public : l'entreprise perd visibilité et contrôle. La réponse est autant l'offre d'alternatives validées que l'interdiction.

### Question 3 : Capital One (2019)
La violation de Capital One (2019, ~106 millions de dossiers) a exploité un pare-feu applicatif mal configuré dans le cloud AWS. Qu'illustre ce cas ?

* A. Que le cloud AWS est intrinsèquement défaillant.
* B. Que dans le modèle de responsabilité partagée, la CONFIGURATION reste côté client : le fournisseur fournit des briques sûres, mal assemblées elles exposent tout.
* C. Que les banques ne devraient pas utiliser l'informatique.
* **Réponse correcte : B**
* *Explication* : L'infrastructure du fournisseur n'a pas été percée : c'est la configuration du client qui a été exploitée. La sécurité cloud est d'abord une discipline de configuration et de droits.

### Question 4 : Le bucket public — Verizon (2017)
En 2017, les données de millions de clients Verizon ont été exposées via un espace de stockage cloud (bucket S3) laissé public par un prestataire. Quelle leçon en tirer ?

* A. Une seule case mal cochée expose des millions de dossiers au monde entier — et la responsabilité reste chez le donneur d'ordre, même si le prestataire configure.
* B. Les buckets de stockage sont interdits depuis 2017.
* C. Seuls les hébergeurs sont responsables des fuites.
* **Réponse correcte : A**
* *Explication* : Le stockage cloud mal configuré est LA fuite archétypale : silencieuse, mondiale, découverte par des robots qui scannent en permanence. Et la chaîne de sous-traitance transporte la responsabilité (Target, encore).

### Question 5 : L'origine des incidents cloud
Selon une prédiction du cabinet Gartner (publiée en 2019, devenue référence du secteur), quelle proportion des défaillances de sécurité cloud relèvent d'une erreur du CLIENT ?

* A. Environ 20 %.
* B. Environ 50 %.
* C. La quasi-totalité — de l'ordre de 99 %.
* **Réponse correcte : C**
* *Explication* : Les hyperscalers sécurisent massivement leur infrastructure ; les incidents naissent presque toujours côté client : configurations, droits excessifs, absence de MFA. Le maillon faible du cloud, c'est l'usage qu'on en fait.

### Question 6 : IaaS, PaaS, SaaS
En modèle IaaS (Infrastructure as a Service), qui est responsable de l'application des correctifs du système d'exploitation des machines virtuelles ?

* A. Le fournisseur cloud, automatiquement.
* B. Le client : il loue l'infrastructure, mais administre ses systèmes — OS, middleware et applications compris.
* C. Personne : les VM cloud n'ont pas besoin de correctifs.
* **Réponse correcte : B**
* *Explication* : Plus on descend vers l'IaaS, plus la part du client grandit : le fournisseur garantit l'infrastructure physique et l'hyperviseur, le client patche et durcit tout ce qu'il installe dessus.

### Question 7 : Les outils CSPM
À quoi sert un outil CSPM (Cloud Security Posture Management) ?

* A. À mesurer la vitesse des connexions cloud.
* B. À scanner en continu les configurations cloud pour détecter les expositions (stockages publics, droits excessifs, MFA absent) avant les attaquants.
* C. À facturer les services cloud aux différents départements.
* **Réponse correcte : B**
* *Explication* : Les erreurs de configuration étant la première cause d'incident cloud, le CSPM fait ce qu'un humain ne peut pas : vérifier en permanence des milliers de réglages contre les bonnes pratiques — le re-scan permanent du cloud.

### Question 8 : Le compte à protéger absolument
Quel compte cloud exige le niveau de protection maximal (MFA fort, usage exceptionnel, surveillance) ?

* A. Le compte de test du stagiaire.
* B. Le compte d'administration global (« root » / administrateur général) de la plateforme cloud.
* C. Le compte de la newsletter marketing.
* **Réponse correcte : B**
* *Explication* : Ce compte peut tout : créer, supprimer, ouvrir, facturer. Bonnes pratiques : MFA le plus fort disponible (clé physique), pas d'usage quotidien, comptes d'administration délégués et journalisés pour le travail courant.

### Question 9 : Les clés de chiffrement dans le cloud
Pourquoi la question « qui détient les clés de chiffrement ? » est-elle centrale pour les données sensibles hébergées dans le cloud ?

* A. Parce que les clés coûtent cher à fabriquer.
* B. Parce que celui qui détient les clés peut techniquement lire les données : selon les options (clés gérées par le fournisseur ou par le client), le niveau de confiance requis change complètement.
* C. Parce que les clés doivent être imprimées et stockées en coffre.
* **Réponse correcte : B**
* *Explication* : Chiffrer avec les clés du fournisseur protège des tiers, pas du fournisseur lui-même (ni des réquisitions qui le visent). Pour les données les plus sensibles, garder la main sur ses clés est un choix de souveraineté.

### Question 10 : Localisation des données et RGPD
Pourquoi la localisation géographique des données hébergées importe-t-elle juridiquement ?

* A. Pour des raisons de vitesse de connexion uniquement.
* B. Parce que le RGPD encadre strictement les transferts de données personnelles hors de l'Union européenne : la région d'hébergement et le droit applicable au fournisseur font partie de la conformité.
* C. Parce que les données stockées à l'étranger sont automatiquement perdues.
* **Réponse correcte : B**
* *Explication* : Choisir la région d'hébergement, vérifier les clauses de transfert et le droit auquel le fournisseur est soumis : c'est le volet contractuel et juridique de la sécurité cloud — le pont vers B15.

---

## Session B12 : Sécurité & confidentialité des données

### Question 1 : Chiffrement des données « au repos »
Quel outil protège la confidentialité des données stockées sur le disque d'un ordinateur portable professionnel volé dans un train ?

* A. Un antivirus de nouvelle génération (EDR).
* B. Un logiciel de chiffrement complet du disque (ex. BitLocker ou FileVault).
* C. Un filtre de confidentialité posé sur l'écran physique de l'ordinateur.
* **Réponse correcte : B**
* *Explication* : Machine éteinte, le voleur peut extraire le disque et le lire sur une autre machine — sauf si le volume est intégralement chiffré : sans la clé, les fichiers restent illisibles. Le vol de matériel n'est alors plus une fuite de données.

### Question 2 : Anonymisation vs pseudonymisation
Quelle est la différence fondamentale entre anonymisation et pseudonymisation selon le RGPD ?

* A. L'anonymisation est réversible tandis que la pseudonymisation est définitive.
* B. L'anonymisation est irréversible (on ne peut plus remonter à l'individu), alors que la pseudonymisation permet de réidentifier via des informations complémentaires protégées.
* C. Seule la pseudonymisation est reconnue comme protection valide par les tribunaux.
* **Réponse correcte : B**
* *Explication* : La donnée pseudonymisée reste une donnée personnelle (la table de correspondance existe) et reste soumise au RGPD ; la donnée réellement anonymisée sort de son champ d'application.

### Question 3 : La règle 3-2-1
Que prescrit la règle de sauvegarde « 3-2-1 » ?

* A. Trois sauvegardes par jour, deux par nuit, une le week-end.
* B. Trois copies des données, sur deux types de supports différents, dont une copie hors site.
* C. Trois administrateurs, deux serveurs, un seul mot de passe.
* **Réponse correcte : B**
* *Explication* : La redondance (3) protège de la défaillance, la diversité des supports (2) d'une panne de technologie, le hors-site (1) du sinistre local — incendie compris. Version moderne : ajouter une copie hors ligne ou immuable contre les rançongiciels.

### Question 4 : La sauvegarde hors ligne
Pourquoi une copie de sauvegarde déconnectée (hors ligne) est-elle devenue indispensable face aux rançongiciels ?

* A. Parce qu'elle est plus rapide à restaurer.
* B. Parce que les attaquants ciblent d'abord les sauvegardes accessibles — plus de 9 attaques par rançongiciel sur 10 les visent (rapport Veeam, Ransomware Trends, 2023).
* C. Parce que le stockage hors ligne est gratuit.
* **Réponse correcte : B**
* *Explication* : Chiffrer les sauvegardes avant les données rend la victime captive. Une copie que le réseau ne peut pas atteindre (bande éjectée, disque déconnecté, stockage immuable) reste la garantie de dernier recours.

### Question 5 : OVHcloud (2021)
L'incendie du centre de données OVHcloud de Strasbourg (2021) a définitivement détruit les données de clients dont les sauvegardes se trouvaient au même endroit que la production. Quelle règle ce sinistre a-t-il rappelée ?

* A. Les centres de données sont ininflammables.
* B. La copie hors site de la règle 3-2-1 : une sauvegarde qui partage le sort de la production n'en est pas une.
* C. Le cloud dispense de sauvegardes.
* **Réponse correcte : B**
* *Explication* : Le risque n'est pas que cyber : incendie, inondation, panne majeure. La distance géographique entre production et sauvegarde est une exigence de résilience — et la responsabilité de la vérifier revient au client.

### Question 6 : Morgan Stanley et le matériel réformé
Morgan Stanley a été sanctionnée pour avoir laissé partir des équipements décommissionnés contenant des données clients non effacées. Quelle pratique ce cas impose-t-il ?

* A. Ne jamais remplacer le matériel informatique.
* B. L'effacement sécurisé certifié (ou la destruction physique) de tout support de stockage en fin de vie — le cycle de vie de la donnée va jusqu'à sa destruction.
* C. Revendre le matériel le plus vite possible.
* **Réponse correcte : B**
* *Explication* : Supprimer des fichiers ne les efface pas ; formater ne suffit pas toujours. Disques, photocopieurs, téléphones : tout support qui sort de l'entreprise doit être effacé de manière certifiée ou détruit — et tracé.

### Question 7 : Le test de restauration
Pourquoi dit-on qu'« une sauvegarde non testée n'est pas une sauvegarde » ?

* A. Parce que les tests rendent les sauvegardes plus rapides.
* B. Parce que seule une restauration d'essai régulière prouve que les données sont réellement récupérables — les sauvegardes silencieusement défaillantes se découvrent sinon le jour de la crise.
* C. Parce que la loi impose un test quotidien.
* **Réponse correcte : B**
* *Explication* : Supports usés, périmètres incomplets, mots de passe de chiffrement perdus : tout cela se découvre en test… ou en catastrophe. La métrique qui compte n'est pas « la sauvegarde a tourné » mais « la restauration a réussi en N heures ».

### Question 8 : La classification des données
Dans une classification à trois niveaux (Public / Interne / Confidentiel), comment classer les fiches de paie stockées sur l'espace cloud de l'entreprise ?

* A. Public : elles ne contiennent que des chiffres.
* B. Interne : tous les salariés peuvent les consulter.
* C. Confidentiel : données personnelles et sensibles par nature, accès strictement limité (RH, paie) et chiffrement exigé.
* **Réponse correcte : C**
* *Explication* : La classification pilote les protections : ce qui est confidentiel exige chiffrement, accès restreint et traçabilité. Sans classification, tout est protégé pareil — c'est-à-dire mal.

### Question 9 : RTO et RPO
Que mesurent respectivement le RTO et le RPO d'un plan de continuité ?

* A. RTO : la durée d'interruption maximale tolérable (temps pour redémarrer) ; RPO : la perte de données maximale tolérable (ancienneté de la dernière sauvegarde utilisable).
* B. RTO : le coût de la sauvegarde ; RPO : son volume en téraoctets.
* C. Deux noms différents pour la même métrique.
* **Réponse correcte : A**
* *Explication* : « Combien de temps peut-on rester arrêté ? » (RTO) et « combien d'heures de travail peut-on perdre ? » (RPO) : deux réponses métier qui dimensionnent la fréquence des sauvegardes et l'architecture de reprise (PCA/PRA).

### Question 10 : L'immuabilité
Qu'est-ce qu'une sauvegarde « immuable » ?

* A. Une sauvegarde stockée sur papier.
* B. Une copie qui, une fois écrite, ne peut être ni modifiée ni supprimée pendant une durée définie — même par un administrateur (donc même par un attaquant qui a volé ses droits).
* C. Une sauvegarde chiffrée deux fois.
* **Réponse correcte : B**
* *Explication* : L'immuabilité (WORM : write once, read many) neutralise le scénario où l'attaquant, muni de droits d'administration volés, détruit les sauvegardes avant de chiffrer — le complément moderne de la copie hors ligne.

---

## Session B13 : Gouvernance & cadres de sécurité

### Question 1 : Le rôle de l'ISO 27001
Quelle est la finalité principale de la norme internationale ISO/IEC 27001 ?

* A. Proposer des configurations techniques précises pour les pare-feux de chaque constructeur.
* B. Définir les exigences pour mettre en place, maintenir et améliorer un Système de Management de la Sécurité de l'Information (SMSI).
* C. Rendre obligatoire le licenciement des administrateurs système en cas d'attaque réussie.
* **Réponse correcte : B**
* *Explication* : ISO 27001 est une norme organisationnelle et certifiable : elle structure la gouvernance de la sécurité (SMSI) dans une démarche d'amélioration continue — le cadre, pas les réglages techniques.

### Question 2 : L'hygiène selon l'ANSSI
Dans le cadre de l'hygiène informatique définie par l'ANSSI, quelle mesure organisationnelle est jugée prioritaire ?

* A. Publier régulièrement des vidéos humoristiques sur les failles logicielles.
* B. Établir et maintenir un inventaire complet et à jour de tous les matériels et logiciels connectés au réseau.
* C. Acheter uniquement du matériel informatique fabriqué en France.
* **Réponse correcte : B**
* *Explication* : On ne protège pas ce qu'on ignore posséder : l'inventaire est le socle qui permet de savoir quoi corriger, surveiller et durcir — la règle n°1, revérifiée à chaque crise (Log4Shell).

### Question 3 : NIST CSF 2.0
Quelle nouveauté majeure la version 2.0 du NIST Cybersecurity Framework (février 2024) a-t-elle introduite ?

* A. La suppression de la fonction « Détecter ».
* B. Une sixième fonction, GOVERN (Gouverner), qui place la gouvernance au cœur du cadre — aux côtés d'Identifier, Protéger, Détecter, Répondre et Récupérer.
* C. L'obligation légale d'utiliser le cadre dans toute l'Union européenne.
* **Réponse correcte : B**
* *Explication* : Le passage de 5 à 6 fonctions consacre l'idée que la sécurité se gouverne (stratégie, rôles, risques, supervision) avant de se techniciser. Réciter « les 5 fonctions » est devenu obsolète en 2024.

### Question 4 : Qui porte la PSSI ?
Qui doit porter et arbitrer la Politique de Sécurité du Système d'Information (PSSI) d'une organisation ?

* A. Le stagiaire du service informatique.
* B. La direction générale : la sécurité est un risque d'entreprise — la direction décide, la direction assume ; le RSSI instruit et met en œuvre.
* C. Le prestataire d'infogérance.
* **Réponse correcte : B**
* *Explication* : Sans portage par la direction, la PSSI reste un document technique sans budget ni autorité. Les arbitrages (qu'accepte-t-on ? que finance-t-on ?) sont des décisions de gouvernance, pas d'ingénierie.

### Question 5 : La condamnation du CSO d'Uber (2022)
L'ancien responsable sécurité d'Uber a été condamné pénalement pour avoir dissimulé une violation de données (2016) en la maquillant en prime de bug bounty. Que retenir ?

* A. Les responsables sécurité ne risquent jamais rien personnellement.
* B. Dissimuler n'est pas gérer : la transparence vis-à-vis des autorités est une obligation, et la responsabilité peut devenir PERSONNELLE — jusqu'au pénal.
* C. Les bug bounties sont désormais illégaux.
* **Réponse correcte : B**
* *Explication* : Le problème n'était pas la violation mais sa dissimulation. Ce précédent a marqué toute la profession : documenter, notifier, tracer les décisions — la conformité protège aussi ceux qui la respectent.

### Question 6 : Yahoo et la valeur de l'entreprise
Lors de son rachat par Verizon, Yahoo a vu son prix de vente réduit de 350 millions de dollars après la révélation de violations massives dissimulées, plus une amende de la SEC. Qu'illustre ce cas ?

* A. La cybersécurité est un sujet purement technique sans effet financier.
* B. La posture cyber pèse directement sur la valeur d'une entreprise : les violations cachées se paient en décote, en sanctions et en confiance — la due diligence cyber fait partie de toute acquisition.
* C. Les rachats d'entreprises ne tiennent jamais compte de l'informatique.
* **Réponse correcte : B**
* *Explication* : 350 M$ de décote : la sécurité chiffrée au bilan. Et le miroir de Marriott (B17) : lors d'un rachat, on achète aussi les intrusions en cours — l'audit cyber préalable n'est pas optionnel.

### Question 7 : La roue de Deming (PDCA)
Dans le cycle PDCA appliqué à un SMSI, que recouvre l'étape « Check » ?

* A. Vérifier : audits, indicateurs, revues — mesurer si les mesures décidées sont réellement appliquées et efficaces.
* B. Choisir les nouveaux logiciels à acheter.
* C. Cocher les cases du registre sans contrôle réel.
* **Réponse correcte : A**
* *Explication* : Planifier, faire, VÉRIFIER, corriger : sans le Check (audits, tests, revues), les écarts entre le papier et la réalité s'accumulent en silence — c'est le re-scan d'Equifax (B18) et l'audit de B20.

### Question 8 : Le positionnement du RSSI
Pourquoi recommande-t-on que le RSSI ne soit pas hiérarchiquement subordonné au DSI ?

* A. Parce que les deux fonctions ne se parlent jamais.
* B. Pour éviter le conflit d'intérêts : le DSI est jugé sur la disponibilité et les projets, le RSSI sur la sécurité — l'arbitrage entre les deux doit remonter à la direction, pas se régler dans un lien de subordination.
* C. Parce que le RSSI doit gagner plus que le DSI.
* **Réponse correcte : B**
* *Explication* : Quand la sécurité dépend de celui qu'elle doit parfois ralentir, elle perd les arbitrages. Un RSSI rattaché à la direction porte les risques au bon niveau — celui qui décide et assume.

### Question 9 : La directive NIS2
Quel changement majeur la directive européenne NIS2 introduit-elle pour les dirigeants ?

* A. Rien : elle ne concerne que les techniciens.
* B. La responsabilité des organes de direction est engagée : les dirigeants doivent approuver les mesures de gestion des risques, se former, et peuvent être tenus responsables des manquements.
* C. L'interdiction des sous-traitants informatiques.
* **Réponse correcte : B**
* *Explication* : NIS2 élargit massivement le périmètre des entités régulées et fait de la cybersécurité un devoir de gouvernance nominatif : la sécurité entre au conseil d'administration par la porte du droit.

### Question 10 : La charte informatique
Qu'est-ce qui donne à une charte informatique sa force juridique vis-à-vis des salariés ?

* A. Sa longueur : plus elle est épaisse, plus elle est valable.
* B. Son annexion au règlement intérieur (avec les procédures de consultation et de dépôt associées), qui la rend opposable — et son contenu proportionné et porté à la connaissance de tous.
* C. Sa rédaction en anglais juridique.
* **Réponse correcte : B**
* *Explication* : Une charte publiée nulle part n'engage personne. Annexée au règlement intérieur et communiquée, elle fonde les usages autorisés, la surveillance proportionnée (B15) et les sanctions éventuelles.

---

## Session B14 : Gestion des risques

### Question 1 : Le transfert du risque cyber
Quelle action correspond à une stratégie de **transfert** du risque cyber ?

* A. Souscrire un contrat d'assurance cyber spécifique auprès d'une compagnie d'assurance.
* B. Former l'ensemble des logisticiens à ne pas ouvrir les pièces jointes douteuses.
* C. Migrer tous les serveurs locaux vers un hébergeur cloud public.
* **Réponse correcte : A**
* *Explication* : Transférer, c'est faire porter l'impact financier à un tiers (assurance, clauses contractuelles). Former RÉDUIT le risque ; migrer le TRANSFORME (responsabilité partagée, B11) mais ne le transfère pas entièrement.

### Question 2 : La notion d'actif
En gestion des risques, que désigne le terme « actif » (*asset*) ?

* A. Tout élément physique, virtuel ou humain ayant de la valeur pour la mission de l'entreprise (serveurs, données, savoir-faire, réputation).
* B. Uniquement les liquidités bancaires de l'entreprise.
* C. Les seuls équipements achetés dans l'année.
* **Réponse correcte : A**
* *Explication* : L'analyse de risques commence par l'inventaire des actifs et de leur valeur : on ne peut coter l'impact d'une menace que si l'on sait ce qu'elle menace. Fichier clients, chaîne logistique, image de marque : tout ce dont la perte ferait mal est un actif.

### Question 3 : L'équation de la criticité
Dans une matrice de risques 4×4, comment calcule-t-on la criticité d'un risque ?

* A. Criticité = Vraisemblance × Gravité (score de 1 à 16).
* B. Criticité = Budget × Nombre de serveurs.
* C. Criticité = Nombre d'employés ÷ Nombre d'incidents.
* **Réponse correcte : A**
* *Explication* : La probabilité que le scénario survienne (vraisemblance, 1-4) multipliée par ses conséquences (gravité, 1-4) donne un score de 1 à 16 qui permet de comparer et prioriser des risques de natures différentes.

### Question 4 : Les quatre traitements du risque
Quels sont les quatre traitements possibles d'un risque identifié ?

* A. Réduire, transférer, éviter, accepter.
* B. Ignorer, cacher, minimiser, reporter.
* C. Assurer, chiffrer, sauvegarder, former.
* **Réponse correcte : A**
* *Explication* : Réduire (mesures de sécurité), transférer (assurance, contrat), éviter (renoncer à l'activité risquée), accepter (en connaissance de cause). Point clé : l'acceptation est une décision FORMELLE de la direction, écrite et datée — jamais un silence.

### Question 5 : Mondelez vs Zurich
Après NotPetya, l'assureur Zurich a refusé d'indemniser Mondelez (~100 M$ de dégâts réclamés) en invoquant la clause d'exclusion « acte de guerre ». Quelle leçon en tirer ?

* A. Les assurances cyber sont des arnaques à éviter.
* B. Le transfert de risque vaut ce que vaut le contrat : lire les exclusions (guerre, État-nation…), vérifier les plafonds et privilégier des polices cyber dédiées.
* C. Les attaques d'États sont toujours indemnisées.
* **Réponse correcte : B**
* *Explication* : L'attribution de NotPetya à un État a ouvert la porte à l'exclusion guerre d'une police dommages classique. L'affaire (finalement transigée) a poussé tout le marché à clarifier les clauses — à lire AVANT la crise.

### Question 6 : Merck et les tribunaux
Merck a réclamé environ 1,4 milliard de dollars à ses assureurs après NotPetya, ceux-ci invoquant aussi l'exclusion guerre. Qu'ont retenu les juridictions américaines ?

* A. Que toute cyberattaque est un acte de guerre par défaut.
* B. Que l'exclusion « guerre », rédigée pour des conflits armés traditionnels, ne s'appliquait pas telle quelle à cette cyberattaque — donnant raison à l'assuré avant un accord final.
* C. Que les assurances n'ont jamais à payer les sinistres cyber.
* **Réponse correcte : B**
* *Explication* : Les tribunaux ont refusé d'étendre une clause pensée pour les bombes aux logiciels malveillants. Conséquence de marché : les assureurs réécrivent désormais des exclusions cyber explicites — d'où l'importance des polices dédiées.

### Question 7 : Le risque résiduel
Qu'est-ce que le « risque résiduel » ?

* A. Le risque qui subsiste APRÈS l'application des mesures de traitement — celui que la direction doit formellement accepter.
* B. Le risque des entreprises résidentielles.
* C. Un risque théorique qui n'existe jamais en pratique.
* **Réponse correcte : A**
* *Explication* : Aucune mesure ne ramène un risque à zéro. Nommer, coter et faire accepter le résiduel par la direction ferme la boucle : chacun sait ce qui reste à porter — et par qui.

### Question 8 : EBIOS Risk Manager
Qu'est-ce qu'EBIOS Risk Manager ?

* A. Un antivirus français pour PME.
* B. La méthode française d'appréciation et de traitement des risques numériques, publiée par l'ANSSI.
* C. Une norme comptable européenne.
* **Réponse correcte : B**
* *Explication* : EBIOS RM structure l'analyse par scénarios (sources de risques, parties prenantes, chemins d'attaque) et alimente registre, PSSI et plans de traitement — l'outillage méthodologique souverain, cohérent avec ISO 27005.

### Question 9 : Coter un risque émergent
Vos salariés collent des extraits de fichiers clients dans une IA générative grand public pour « gagner du temps ». Comment traiter ce risque ?

* A. L'ignorer : les IA sont incontournables, donc intouchables.
* B. Le coter comme les autres (vraisemblance élevée, gravité forte : fuite de données personnelles), puis le RÉDUIRE : offre d'outil validé, règles d'usage claires, sensibilisation — plutôt qu'une interdiction incantatoire.
* C. Interdire Internet à toute l'entreprise.
* **Réponse correcte : B**
* *Explication* : Le Shadow IT se traite par le registre des risques, pas par le déni : coter, décider, offrir une alternative sûre. Un usage massif et commode ne disparaît jamais par simple interdiction.

### Question 10 : Le registre des risques
Qu'est-ce qui distingue un registre des risques utile d'un document d'affichage ?

* A. Sa mise en forme soignée avec un logo en couleur.
* B. Son caractère VIVANT : revu périodiquement et à chaque changement majeur, avec pour chaque risque un propriétaire nommé, un traitement décidé et une échéance suivie.
* C. Son épaisseur : au moins 200 pages.
* **Réponse correcte : B**
* *Explication* : Un registre figé date du jour de sa rédaction ; les menaces, elles, évoluent chaque semaine. Propriétaire, décision, échéance, revue : quatre colonnes qui transforment l'inventaire en pilotage.
---

## Session B15 : Conformité & réglementations vie privée

### Question 1 : Délai de notification CNIL
Sous quel délai maximal une entreprise doit-elle notifier la CNIL après avoir pris connaissance d'une violation de données personnelles ?

* A. 24 heures.
* B. 72 heures.
* C. 30 jours.
* **Réponse correcte : B**
* *Explication* : Le RGPD (article 33) impose la notification à l'autorité de contrôle sans retard injustifié et, si possible, sous 72 heures au plus tard après la prise de connaissance — heures CALENDAIRES : le week-end compte.

### Question 2 : L'information des personnes concernées
Dans quel cas une violation impose-t-elle de notifier individuellement les personnes affectées, en plus de la CNIL ?

* A. Lorsque la violation est susceptible d'engendrer un risque élevé pour les droits et libertés des personnes (ex. données bancaires ou médicales exploitables).
* B. Uniquement si l'entreprise dispose du budget pour envoyer des courriers postaux.
* C. Si la violation concerne moins de 10 personnes.
* **Réponse correcte : A**
* *Explication* : La notification individuelle s'impose en cas de risque élevé (usurpation, préjudice financier, discrimination). Si les données volées étaient fortement chiffrées et donc illisibles, elle peut ne pas être requise — le chiffrement de B12 a aussi une valeur juridique.

### Question 3 : Les deux paliers de sanctions RGPD
Comment s'articulent les sanctions financières prévues par le RGPD ?

* A. Un montant unique de 1 million d'euros pour toute infraction.
* B. Deux paliers : jusqu'à 10 M€ ou 2 % du CA mondial pour certains manquements, et jusqu'à 20 M€ ou 4 % pour les plus graves — le montant le plus élevé étant retenu.
* C. Un pourcentage fixe de 10 % du chiffre d'affaires français.
* **Réponse correcte : B**
* *Explication* : Le règlement gradue selon la nature du manquement (obligations de l'entreprise vs droits des personnes et principes fondamentaux). Le « montant le plus élevé retenu » rend la sanction dissuasive quelle que soit la taille de l'organisation.

### Question 4 : Google et la CNIL (2019)
Pourquoi la CNIL a-t-elle infligé à Google une amende de 50 millions d'euros en 2019 — alors record européen ?

* A. Pour une fuite de données massive causée par un piratage.
* B. Pour manque de transparence et défaut de base légale valable : information diluée et consentement à la publicité personnalisée ni éclairé ni univoque.
* C. Pour avoir refusé d'ouvrir un bureau en France.
* **Réponse correcte : B**
* *Explication* : Aucun piratage ici : la sanction visait la CONCEPTION du recueil de consentement. Le RGPD ne punit pas que les fuites — il encadre la loyauté même de la collecte.

### Question 5 : Clearview AI
Qu'est-ce qui a valu à Clearview AI une amende CNIL de 20 M€, puis une astreinte de 5,2 M€ pour non-exécution ?

* A. La collecte massive de photos de visages sur Internet, sans base légale, pour alimenter une reconnaissance faciale commerciale.
* B. Un simple retard de paperasse administrative.
* C. L'utilisation de serveurs trop lents.
* **Réponse correcte : A**
* *Explication* : Aspirer des milliards d'images « publiques » n'est pas légal pour autant : donnée accessible ne veut pas dire donnée librement exploitable. Et l'astreinte rappelle qu'ignorer une injonction coûte encore plus cher que la sanction initiale.

### Question 6 : Les données sensibles
Pourquoi les données de santé bénéficient-elles d'un régime de protection renforcé dans le RGPD ?

* A. Parce qu'elles sont plus volumineuses que les autres.
* B. Parce qu'elles relèvent des « catégories particulières » (santé, opinions, biométrie…) dont le traitement est par principe interdit, sauf exceptions strictes — leur divulgation peut nuire gravement et durablement aux personnes.
* C. Parce qu'elles appartiennent à l'État.
* **Réponse correcte : B**
* *Explication* : Un mot de passe se change, pas un dossier médical. Ces données exigent base légale spécifique, sécurité renforcée (chiffrement, accès restreints) et vigilance accrue en cas de violation — le cœur du dossier MedDistri (B20).

### Question 7 : Le registre des traitements
Qu'est-ce que le registre des traitements que tient le DPO ?

* A. La liste des mots de passe de l'entreprise.
* B. Le document obligatoire qui recense chaque traitement de données personnelles : finalité, données concernées, durées de conservation, destinataires, mesures de sécurité.
* C. Le journal des connexions au serveur web.
* **Réponse correcte : B**
* *Explication* : Le registre est la cartographie de conformité : c'est la première pièce demandée en cas de contrôle CNIL, et l'outil qui révèle les traitements oubliés, disproportionnés ou sans durée de conservation.

### Question 8 : La minimisation
Que prescrit le principe de minimisation des données ?

* A. Compresser les fichiers pour gagner de l'espace disque.
* B. Ne collecter que les données strictement nécessaires à la finalité déclarée — et ne les garder que le temps nécessaire.
* C. Réduire le nombre de salariés du service informatique.
* **Réponse correcte : B**
* *Explication* : La donnée qu'on ne collecte pas ne peut ni fuiter ni coûter une sanction : la minimisation est autant un principe juridique qu'une mesure de sécurité — moins de surface de données, moins de risque.

### Question 9 : 72 heures, même le week-end
Une violation est découverte un vendredi à 18h. Quand expire le délai de notification CNIL ?

* A. Le mercredi suivant à 18h : les week-ends ne comptent pas.
* B. Le lundi à 18h : les 72 heures sont calendaires — le week-end compte.
* C. À la fin du mois en cours.
* **Réponse correcte : B**
* *Explication* : Le délai court en heures calendaires à partir de la prise de connaissance. D'où l'importance d'une procédure et d'astreintes prêtes AVANT l'incident — le vendredi soir est précisément la fenêtre préférée des attaquants.

### Question 10 : Les droits des personnes
Un client vous écrit : « je veux savoir ce que vous détenez sur moi, et que vous l'effaciez ». Que devez-vous faire ?

* A. Ignorer : ces demandes sont facultatives.
* B. Traiter la demande : droit d'accès et droit à l'effacement font partie des droits RGPD, à satisfaire dans un délai d'un mois en principe (sauf exceptions légitimes documentées).
* C. Facturer la réponse au tarif horaire de l'informatique.
* **Réponse correcte : B**
* *Explication* : Accès, rectification, effacement, opposition, portabilité : des droits opposables, dont le non-traitement alimente les plaintes CNIL — première source de contrôles. Un circuit interne de traitement des demandes est indispensable.

---

## Session B16 : Centre des opérations de sécurité (SOC) & supervision

### Question 1 : Le rôle de l'analyste SOC Niveau 1
Dans l'organisation d'un SOC, quelle est la mission principale d'un analyste de Niveau 1 ?

* A. Négocier les tarifs de rançon avec les pirates lors d'une crise.
* B. Effectuer le tri initial des alertes générées par le SIEM, écarter les faux positifs et escalader les menaces réelles au Niveau 2.
* C. Réécrire le code source des applications web compromises de l'entreprise.
* **Réponse correcte : B**
* *Explication* : Le L1 est l'infirmier de tri des urgences : qualification contextuelle rapide, clôture documentée des faux positifs, escalade avec un dossier propre. Le L2 investigue, le L3 gère les crises et chasse (threat hunting).

### Question 2 : Le concept de faux positif
Qu'est-ce qu'un « faux positif » en supervision de sécurité ?

* A. Une alerte déclenchée par un comportement légitime mais identifié à tort comme suspect par l'outil de détection.
* B. Une cyberattaque réussie qui n'a généré aucune alerte dans le SIEM.
* C. Un virus détecté et supprimé sans intervention humaine.
* **Réponse correcte : A**
* *Explication* : Le faux positif est la fausse alarme (ex. l'outil d'inventaire interne détecté comme un scan hostile) ; l'attaque passée inaperçue est un faux négatif. Le faux positif se qualifie par le CONTEXTE et se clôt documenté.

### Question 3 : MTTD et MTTR
Que mesurent respectivement le MTTD et le MTTR d'un SOC ?

* A. Le temps moyen de détection d'une intrusion, puis le temps moyen de neutralisation après détection.
* B. Le nombre d'alertes traitées par jour et par analyste.
* C. Le coût moyen d'un incident et son remboursement par l'assurance.
* **Réponse correcte : A**
* *Explication* : Les deux chronomètres vont ensemble : détecter en 30 secondes ne sert à rien si l'on réagit en 24 heures — le rançongiciel aura chiffré le réseau. Playbooks et SOAR servent précisément à écraser le MTTR.

### Question 4 : SolarWinds et l'alerte décisive (2020)
Comment la campagne d'espionnage SolarWinds — environ 18 000 organisations ayant téléchargé la mise à jour piégée (chiffres de l'éditeur, 2020) — a-t-elle finalement été découverte ?

* A. Par une intelligence artificielle de nouvelle génération.
* B. Par un analyste de Mandiant qui a vérifié une alerte banale (un deuxième appareil MFA enrôlé) en appelant l'employé concerné.
* C. Par la revendication publique des attaquants.
* **Réponse correcte : B**
* *Explication* : L'attaque de la décennie est tombée sur un playbook appliqué sans paresse : vérification humaine par canal indépendant d'une alerte « banale mais sensible ». La qualification contextuelle est LE geste professionnel du SOC.

### Question 5 : Le contre-exemple Target
Chez Target (2013), les outils avaient détecté le malware et le SOC de Bangalore avait remonté l'alerte. Pourquoi l'attaque a-t-elle quand même réussi ?

* A. Les alertes n'ont pas été suivies d'action : la chaîne de traitement et d'escalade s'est arrêtée avant la décision.
* B. Les outils de détection étaient éteints ce jour-là.
* C. L'attaque était indétectable par principe.
* **Réponse correcte : A**
* *Explication* : Mêmes ingrédients que SolarWinds (une alerte, un humain), issue inverse : 40 millions de cartes. La différence ne tient ni au budget ni aux outils, mais au PROCESSUS de qualification et d'escalade — l'objet des playbooks.

### Question 6 : Le threat hunting
Qu'est-ce qui distingue le *threat hunting* (chasse aux menaces) du traitement d'alertes classique ?

* A. Il se pratique uniquement la nuit.
* B. Il utilise des outils nécessairement plus chers.
* C. Il cherche proactivement, par hypothèses, les menaces qui n'ont déclenché AUCUNE alerte automatique.
* **Réponse correcte : C**
* *Explication* : Le hunter part du principe que les outils ont raté quelque chose : « si un attaquant utilisait cette technique chez nous, où verrait-on des traces ? » — hypothèse, recherche, confirmation. C'est la réponse aux intrusions discrètes de type APT.

### Question 7 : La fatigue des alertes
Selon une étude Cisco (2017), 44 % des alertes de sécurité n'étaient jamais investiguées dans les entreprises sondées. Quel phénomène ce chiffre mesure-t-il ?

* A. La paresse individuelle des analystes.
* B. La fatigue des alertes : noyées sous les faux positifs, les équipes traitent superficiellement — et finissent par rater la vraie attaque.
* C. Une saine économie de moyens.
* **Réponse correcte : B**
* *Explication* : Le vrai risque du SOC n'est pas de manquer d'outils mais de se noyer. Les réponses : des règles de détection de meilleure qualité (moins mais mieux) et l'automatisation du tri (SOAR).

### Question 8 : Le SOAR
Un incident survient à 3 heures du matin, sans analyste disponible. Quel dispositif permet de confiner automatiquement l'attaque ?

* A. Le pare-feu local de la machine.
* B. Un playbook d'isolement automatique configuré dans le SOAR, déclenché par exemple par un contact avec une IP malveillante connue, qui isole le poste via l'EDR en quelques secondes.
* C. Un script de redémarrage nocturne des serveurs.
* **Réponse correcte : B**
* *Explication* : Le SOAR exécute la réaction écrite à l'avance quand l'humain dort : détection d'un IoC → isolement réseau automatique. Redémarrer, au contraire, détruit des preuves sans confiner (la RAM, B18).

### Question 9 : Le MSSP
Pourquoi la plupart des PME passent-elles par un MSSP plutôt que de créer un SOC interne ?

* A. Parce que la loi leur interdit d'avoir un SOC.
* B. Parce qu'une surveillance 24/7 exige au minimum 8 à 10 analystes en rotation, hors outillage : le SOC mutualisé d'un prestataire rend la supervision accessible — à condition de soigner le contrat (contexte métier, délais garantis, réversibilité).
* C. Parce que les MSSP sont gratuits.
* **Réponse correcte : B**
* *Explication* : L'économie du 24/7 est hors de portée d'une PME. Le MSSP mutualise analystes et renseignement (les IoC d'un client protègent les autres) ; les points de vigilance s'écrivent au contrat — le MTTR notamment.

### Question 10 : Le breakout time
Selon le rapport CrowdStrike 2024, combien de temps s'écoule en moyenne entre l'intrusion initiale et le début du mouvement latéral (« breakout time ») ?

* A. Environ 62 minutes — avec un record observé d'à peine plus de 2 minutes.
* B. Environ une semaine.
* C. Environ un mois.
* **Réponse correcte : A**
* *Explication* : Une heure : c'est la fenêtre du défenseur entre « l'attaquant est entré » et « l'attaquant se propage ». Toute l'organisation du SOC — tri rapide, playbooks, SOAR — se calibre sur cette course contre la montre.

---

## Session B17 : Outils SIEM & Analyse de logs

### Question 1 : Les 3 composants fondamentaux d'un log
Quelles sont les trois informations minimales qu'une ligne de log doit contenir pour être exploitable en investigation ?

* A. L'adresse e-mail de l'utilisateur, son pays d'origine et son navigateur.
* B. Un horodatage précis, la source de l'événement (IP ou machine ou compte) et l'action réalisée avec son résultat.
* C. Le nom de l'éditeur du logiciel, la taille du fichier log et le type de processeur.
* **Réponse correcte : B**
* *Explication* : Quand, qui, quoi : sans ces trois éléments, impossible de reconstituer une chronologie d'attaque. L'horodatage cohérent (temps synchronisé) est ce qui permet de croiser plusieurs machines.

### Question 2 : Détection d'une injection SQL dans les logs
Quelle requête dans un fichier de logs Apache révèle une tentative d'injection SQL ?

* A. `GET /index.php?id=12`
* B. `GET /images/logo.png`
* C. `GET /product.php?id=1%20OR%201=1`
* **Réponse correcte : C**
* *Explication* : La chaîne `%20OR%201=1` (décodée : `OR 1=1`) rend la condition SQL toujours vraie — la signature classique. Pour juger de la réussite, on regarde ensuite le code HTTP et la taille de la réponse.

### Question 3 : La normalisation (parsing)
À quoi sert la normalisation dans un SIEM ?

* A. À compresser les journaux pour économiser du stockage.
* B. À traduire les formats de logs hétérogènes (Windows, Linux, pare-feu) vers un schéma commun — la condition préalable de toute corrélation.
* C. À chiffrer les journaux pour les rendre confidentiels.
* **Réponse correcte : B**
* *Explication* : Sans langue commune, le SIEM comparerait des formats incompatibles. Le parsing est l'étape ingrate et chronophage de l'intégration d'une nouvelle source — et le fondement de tout le reste.

### Question 4 : La règle de corrélation
Le SIEM observe 10 « Failed password » puis un « Accepted password » depuis la même IP en 60 secondes. Que doit faire la règle de corrélation ?

* A. Rien : des échecs de connexion arrivent tous les jours.
* B. Lever une alerte critique « force brute probablement réussie » — et isoler la session si un SOAR est branché.
* C. Bloquer immédiatement tout le réseau de l'entreprise.
* **Réponse correcte : B**
* *Explication* : Un échec isolé est un non-événement ; l'ENCHAÎNEMENT échecs→succès, même source, fenêtre courte, est une histoire — et les histoires se détectent. Réponse graduée : alerte critique, pas coupure générale.

### Question 5 : Le déport des journaux
Pourquoi centralise-t-on les journaux sur un serveur distinct des machines qui les produisent ?

* A. Pour accélérer les machines de production.
* B. Parce que le protocole Syslog l'impose.
* C. Parce qu'un attaquant efface d'abord ses traces locales : le déport en temps réel les met hors de sa portée — et fonde leur valeur probante.
* **Réponse correcte : C**
* *Explication* : L'effacement des traces est un geste standard de l'attaquant devenu administrateur. La copie centralisée, déjà expédiée, transforme les journaux en pièces à conviction inaltérables.

### Question 6 : Codes HTTP et taille de réponse
Dans un log web, une requête suspecte reçoit un code 200 avec une réponse de 6 800 octets, contre ~850 octets pour une page normale. Comment interpréter ?

* A. Le code 200 prouve que l'attaque a échoué.
* B. Le serveur a traité la requête (200) et la taille anormale suggère fortement que des données supplémentaires — probablement volées — ont été renvoyées.
* C. La taille de réponse n'a aucune signification en sécurité.
* **Réponse correcte : B**
* *Explication* : Le code 200 dit « requête traitée », pas « données fuitées » : c'est la TAILLE qui accable. Ce couple code+volume est l'outil du verdict dans l'analyse de l'Atelier de Synthèse 4.

### Question 7 : Marriott/Starwood (2018)
Les attaquants sont restés environ 4 ans dans les systèmes de Starwood/Marriott (intrusion 2014, découverte 2018, ~339 millions de dossiers selon le régulateur britannique, amende ICO de 18,4 M£ en 2020). Qu'est-ce qui a fini par révéler l'intrusion ?

* A. Une alerte d'un outil de supervision de base de données sur une requête anormale.
* B. Un e-mail de revendication des attaquants.
* C. Une panne générale du système de réservation.
* **Réponse correcte : A**
* *Explication* : Une seule alerte bien placée — sur l'actif critique — a fait ce que quatre ans de silence n'avaient pas fait. Autre leçon : lors d'un rachat, on achète aussi les intrusions en cours (due diligence cyber, B13).

### Question 8 : Desjardins (2019)
Chez Desjardins, un employé a exfiltré pendant ~26 mois les données de 9,7 millions de personnes ; c'est une enquête de POLICE qui a mis l'entreprise sur la piste (rapport du Commissariat à la protection de la vie privée du Canada, 2020). Quelle surveillance manquait ?

* A. Un pare-feu périmétrique plus puissant.
* B. La surveillance des comportements internes : règles de corrélation sur les copies massives et récurrentes de données par un même compte, ou outil DLP.
* C. Un antivirus sur les postes du marketing.
* **Réponse correcte : B**
* *Explication* : La menace était à l'intérieur, et les traces aussi. La journalisation ne vise pas que l'attaquant externe : elle est le seul témoin des abus internes — volume, récurrence, destination.

### Question 9 : Lire les métriques de délai
Le temps de présence médian mondial d'un attaquant est tombé à 10 jours (Mandiant M-Trends, 2024), alors qu'IBM mesure 258 jours en moyenne pour identifier puis contenir une violation (2024). Comment concilier ces chiffres ?

* A. L'un des deux rapports se trompe forcément.
* B. Ils ne mesurent pas la même chose : la médiane du temps avant détection baisse (tirée par les rançongiciels qui s'annoncent eux-mêmes), tandis que la moyenne identification+confinement inclut la reprise de contrôle — et les intrusions discrètes durent des mois.
* C. Les deux chiffres sont identiques une fois convertis en heures.
* **Réponse correcte : B**
* *Explication* : Médiane vs moyenne, détection vs détection+confinement : lire la définition d'une métrique avant de la citer est un réflexe d'analyste — et un grand classique des débats mal engagés.

### Question 10 : Le protocole Syslog
Qu'est-ce que Syslog ?

* A. Le protocole réseau standard de transfert des messages de journaux vers un serveur de collecte central.
* B. Un antivirus pour serveurs Linux.
* C. Le format des mots de passe chiffrés.
* **Réponse correcte : A**
* *Explication* : Syslog est la lingua franca du transport de logs : équipements réseau, serveurs et applications savent expédier leurs événements vers le puits central — la brique de base de la collecte d'un SIEM.

---

## Session B18 : Introduction à la réponse aux incidents

### Question 1 : Confinement vs éradication
Dans le cycle de réponse aux incidents, quelle action correspond à la phase de **confinement** ?

* A. Supprimer les clés de registre créées par un malware.
* B. Isoler du réseau la machine compromise en débranchant son câble Ethernet ou en la plaçant dans un VLAN d'isolement.
* C. Restaurer la dernière sauvegarde propre de la base de données.
* **Réponse correcte : B**
* *Explication* : Confiner = stopper la propagation (isoler) ; éradiquer = nettoyer (malware, portes dérobées, faille d'origine — réponse A) ; recouvrer = restaurer et redémarrer sous surveillance (réponse C).

### Question 2 : Règle d'or face à un rançongiciel actif
Quelle consigne donner à un utilisateur découvrant un message de rançon sur son écran ?

* A. Éteindre immédiatement l'ordinateur en restant appuyé sur le bouton d'alimentation.
* B. Ne pas éteindre l'ordinateur, mais débrancher immédiatement le câble réseau ou couper le Wi-Fi, puis alerter l'équipe de sécurité.
* C. Payer immédiatement la rançon demandée avec sa carte de crédit personnelle.
* **Réponse correcte : B**
* *Explication* : Éteindre détruit les preuves volatiles de la RAM (processus actifs, connexions, parfois la clé de chiffrement). Isoler sans éteindre stoppe la propagation ET préserve la mémoire pour les enquêteurs.

### Question 3 : CVE vs CWE
Quelle est la différence entre une CVE et une CWE ?

* A. Aucune : deux noms pour la même chose.
* B. La CVE identifie une faille précise d'un produit précis (ex. CVE-2021-44228) ; la CWE décrit la catégorie de faiblesse sous-jacente (ex. CWE-89, l'injection SQL).
* C. La CVE concerne le matériel, la CWE le logiciel.
* **Réponse correcte : B**
* *Explication* : L'analogie médicale : la CWE est la maladie en général, la CVE le cas déclaré chez un patient précis. Les scanners remontent des CVE ; les développeurs apprennent des CWE.

### Question 4 : Prioriser les correctifs
Une faille CVSS 9.8 touche à la fois le serveur web exposé sur Internet et un serveur de test isolé sans données. Comment prioriser ?

* A. Même urgence partout : le score est identique.
* B. Serveur exposé : correction en urgence (24 h) ; serveur de test : fenêtre planifiée — la priorité se calcule en gravité × exposition, pas au score seul.
* C. Aucun des deux : attendre le prochain audit annuel.
* **Réponse correcte : B**
* *Explication* : Le score CVSS mesure la dangerosité intrinsèque ; la priorité la pondère par le contexte (le « score environnemental ») — la criticité V×G de B14 appliquée aux failles. Tout traiter en urgence, c'est ne plus rien trier.

### Question 5 : La faille zero-day
Qu'est-ce qu'une vulnérabilité « zero-day » et comment s'en protéger ?

* A. Une faille inconnue de l'éditeur, sans correctif : les parades sont architecturales — EDR comportemental, segmentation, défense en profondeur.
* B. Une faille corrigée depuis zéro jour : il suffit de patcher.
* C. Une faille qui ne fonctionne que le premier jour du mois.
* **Réponse correcte : A**
* *Explication* : « Zéro jour » pour préparer la défense : pas de patch, pas de signature antivirus. On ne peut pas empêcher l'inconnu — on limite ce qu'il peut atteindre et on détecte le comportement anormal qu'il produit.

### Question 6 : Equifax (2017)
La violation Equifax (147 millions de personnes, accord avec les autorités américaines pouvant atteindre 700 M$ — FTC, 2019) a exploité une faille Apache Struts. Qu'est-ce qui rend ce cas exemplaire ?

* A. La faille était inconnue : rien n'était possible.
* B. La faille était publiée avec correctif disponible depuis des mois : inventaire défaillant, patch non appliqué, re-scan raté, et 76 jours d'exfiltration invisibles à cause d'un certificat expiré — une chaîne de négligences ordinaires.
* C. L'attaque a été menée par un employé.
* **Réponse correcte : B**
* *Explication* : Chaque étape du cycle a cédé : identification, remédiation, vérification, détection. Pas un exploit de génie — l'accumulation de petites défaillances de processus. C'est tout l'enjeu du « Check » de B13.

### Question 7 : Log4Shell (2021)
Lors de la crise Log4Shell (CVE-2021-44228, score CVSS 10.0, décembre 2021), quelle a été la première difficulté des équipes de sécurité du monde entier ?

* A. Trouver OÙ la bibliothèque Log4j était utilisée : l'inventaire logiciel, souvent incomplet, a conditionné toute la réponse.
* B. Convaincre les attaquants de ne pas exploiter la faille.
* C. Redémarrer Internet.
* **Réponse correcte : A**
* *Explication* : On ne protège que ce qu'on sait posséder : la leçon d'inventaire (A01, B13) vécue en accéléré mondial. Réponse type : mesure compensatoire immédiate (WAF), puis campagne de correctifs vérifiés.

### Question 8 : NIST et PICERL
Comment s'articulent le cycle NIST SP 800-61 et le modèle PICERL du SANS ?

* A. Ce sont deux méthodes incompatibles entre lesquelles il faut choisir son camp.
* B. Le NIST définit 4 phases (confinement-éradication-recouvrement regroupés en une seule, car on itère entre les trois) ; PICERL déplie les mêmes réalités en 6 étapes mnémotechniques.
* C. PICERL remplace légalement le NIST depuis 2020.
* **Réponse correcte : B**
* *Explication* : Deux découpages du même cycle : Préparation, Détection/Identification, Confinement, Éradication, Recouvrement, Leçons apprises. Retenir PICERL pour la mémoire, savoir que le NIST regroupe pour la rigueur.

### Question 9 : La phase la plus négligée
Pourquoi la phase « post-incident » (REX / leçons apprises) est-elle la plus souvent sacrifiée — et pourquoi est-ce une erreur ?

* A. Parce qu'elle est inutile une fois la production rétablie.
* B. Épuisement et pression de reprise la font sauter — mais sans REX, les failles de processus demeurent : on ne sort pas de l'incident, on attend le suivant.
* C. Parce qu'elle est juridiquement interdite.
* **Réponse correcte : B**
* *Explication* : Le REX transforme l'incident en amélioration : corriger la cause, mettre à jour playbooks et PSSI. C'est l'étape la moins chère et la plus rentable du cycle — et celle qui empêche la récidive.

### Question 10 : La mesure compensatoire
Le correctif d'une faille critique ne peut pas être appliqué immédiatement (risque de bloquer la production). Que faire ?

* A. Rien : attendre la prochaine maintenance annuelle.
* B. Poser une mesure compensatoire immédiate (règle de pare-feu, filtrage WAF, désactivation du service vulnérable), tester le correctif rapidement, puis le déployer.
* C. Débrancher définitivement le serveur concerné.
* **Réponse correcte : B**
* *Explication* : Le faux dilemme « sécurité OU production » se résout par la séquence compenser-tester-déployer : le risque est réduit tout de suite, la correction définitive suit vite — ni porte ouverte, ni panne auto-infligée.

---

## Session B19 : Simulation de crise cyber (Tabletop exercise)

### Question 1 : Le rôle du DPO/juriste en cellule de crise
Pourquoi le responsable juridique ou DPO doit-il intégrer la cellule de crise dès les premières heures ?

* A. Pour configurer les règles de filtrage sur le pare-feu de l'entreprise.
* B. Pour piloter les obligations légales : notification CNIL sous 72 h, information des personnes, dépôt de plainte, relations avec l'assureur.
* C. Pour rédiger les messages internes destinés à rassurer techniquement les administrateurs système.
* **Réponse correcte : B**
* *Explication* : Les deux « 72 heures » (notification CNIL, plainte LOPMI pour l'assurance) courent dès la prise de connaissance : sans juriste dans la boucle immédiatement, les délais légaux se consument pendant que la technique confine.

### Question 2 : La communication de crise externe
Quelle attitude recommander pour la communication externe d'une entreprise victime d'un rançongiciel ?

* A. Nier l'attaque auprès de la presse pour ne pas abîmer l'image de l'entreprise.
* B. Publier un communiqué factuel confirmant l'incident, précisant ce qui est touché et ce qui ne l'est pas, détaillant les mesures engagées et exprimant des regrets.
* C. Divulguer publiquement les adresses IP et vulnérabilités exploitées pour prouver sa bonne foi.
* **Réponse correcte : B**
* *Explication* : La transparence contrôlée rassure ; le déni devient l'histoire principale dès la première fuite ; le détail technique arme d'autres attaquants. Des faits, une voix, un calendrier.

### Question 3 : L'inject
Dans un exercice de crise, qu'est-ce qu'un « inject » ?

* A. Le rapport final de l'exercice.
* B. Une information ou un rebondissement introduit par l'animateur (demande de rançon, appel d'un journaliste) pour faire évoluer le scénario et tester une capacité précise.
* C. Un logiciel d'injection SQL.
* **Réponse correcte : B**
* *Explication* : Chaque inject teste UNE chose : la chaîne d'alerte, la décision rançon, la communication. C'est l'outil du maître du jeu pour transformer un scénario en épreuve progressive.

### Question 4 : La raison d'être du tabletop
Qu'est-ce qui caractérise un bon exercice de crise sur table ?

* A. Il se déroule parfaitement, sans accroc, et rassure tout le monde.
* B. Il RÉVÈLE des failles (canaux de crise absents, décisions non préparées, rôles flous) — sans aucun impact sur la production : c'est sa raison d'être.
* C. Il remplace définitivement les sauvegardes.
* **Réponse correcte : B**
* *Explication* : Un exercice réussi d'avance était trop facile. On s'exerce pour découvrir les manques À FROID, quand ils ne coûtent rien — le RETEX transforme la liste des manques en plan d'action.

### Question 5 : Norsk Hydro (2019)
Frappé par le rançongiciel LockerGoga, Norsk Hydro a refusé de payer, isolé massivement ses systèmes, communiqué en transparence totale et produit en mode manuel — pour un coût d'environ 70 M$ (chiffres de l'entreprise, 2019). Pourquoi ce cas est-il devenu un modèle ?

* A. Parce que l'entreprise a payé discrètement et vite.
* B. Parce que les trois décisions dures (déconnecter, refuser, tout dire) étaient PRÉPARÉES — et que l'entreprise en est sortie avec une réputation renforcée, sans financer l'écosystème criminel.
* C. Parce qu'aucune usine n'a été touchée.
* **Réponse correcte : B**
* *Explication* : Le mode manuel existait (PCA), la position rançon était claire, la parole était organisée : rien ne s'improvisait ce matin-là. La transparence a inversé le rapport de force médiatique.

### Question 6 : Maersk, côté reconstruction (2017)
Maersk a reconstruit ~4 000 serveurs et 45 000 postes en 10 jours après NotPetya (~300 M$ de pertes déclarées), grâce à une copie d'annuaire survivante au Ghana. Quelle leçon de gestion de crise en tirer ?

* A. La chance suffit comme stratégie de continuité.
* B. L'improvisation héroïque a sauvé Maersk UNE fois : des sauvegardes hors ligne et une communication hors bande préparées auraient coûté infiniment moins cher que ce coup de chance.
* C. Dix jours est un délai anormalement long pour reconstruire un réseau mondial.
* **Réponse correcte : B**
* *Explication* : Le contrôleur de domaine du Ghana n'a survécu que par une coupure de courant. La préparation (B12 : sauvegardes, PCA) est l'assurance que la survie ne dépendra pas d'un hasard électrique.

### Question 7 : La communication hors bande
La messagerie interne est chiffrée par le rançongiciel. Comment la cellule de crise communique-t-elle ?

* A. Elle attend la restauration de la messagerie.
* B. Par des canaux indépendants du SI compromis, préparés À L'AVANCE : annuaire de crise imprimé (téléphones personnels), messagerie chiffrée externe convenue, pont téléphonique.
* C. Par notes manuscrites déposées sur les bureaux des absents.
* **Réponse correcte : B**
* *Explication* : Improviser un canal en pleine crise fait perdre des heures critiques. Le « hors bande » se prépare comme un extincteur : avant l'incendie, testé, connu de tous les membres de la cellule.

### Question 8 : La question de la rançon
Quelle est la position des autorités françaises (ANSSI) sur le paiement des rançons, et quel texte l'accompagne ?

* A. Payer est recommandé si le montant est raisonnable.
* B. Ne pas payer : le paiement finance l'écosystème, ne garantit rien et signale un payeur ; et la LOPMI (2023) conditionne l'indemnisation assurantielle à une plainte sous 72 h.
* C. La question est laissée à l'appréciation du service informatique.
* **Réponse correcte : B**
* *Explication* : Colonial Pipeline a payé pour un déchiffreur si lent que la restauration sur sauvegardes est restée nécessaire. La position rançon se décide À FROID, avec juridique et assureur — pas à 10h30 un lundi de crise.

### Question 9 : La valeur du plan testé
Selon le rapport IBM Cost of a Data Breach 2022, quel écart de coût moyen sépare les organisations dotées d'une équipe de réponse ET d'un plan régulièrement testé de celles qui n'ont ni l'un ni l'autre ?

* A. Environ 2,66 millions de dollars.
* B. Environ 50 000 dollars.
* C. Aucun écart mesurable.
* **Réponse correcte : A**
* *Explication* : Le mot-clé est TESTÉ : un plan jamais exercé est une hypothèse. L'écart de 2,66 M$ est l'argument budgétaire de l'exercice annuel — une demi-journée d'exercice contre des millions d'impréparation.

### Question 10 : Qui parle pendant la crise ?
Pendant une crise cyber, qui s'exprime publiquement sur l'incident ?

* A. Chaque manager pour son périmètre : c'est plus rapide.
* B. Personne, jamais : silence complet jusqu'à la fin de l'enquête.
* C. Le porte-parole unique, avec des faits vérifiés — et personne d'autre, consigne interne à l'appui dès la première heure.
* **Réponse correcte : C**
* *Explication* : Le silence total nourrit rumeurs et fuites ; la cacophonie fabrique des contradictions. Une voix, des faits — et la consigne de silence externe se donne AVANT le premier tweet de salarié, pas après.

---

## Session B20 : Grand Atelier d'Audit & Clôture

### Question 1 : Traduire un risque cyber pour la Direction
Comment présenter un risque lié à l'absence de mots de passe robustes sur un serveur de fichiers à la directrice générale de MedDistri ?

* A. « Le port RDP 3389 ouvert sur Internet risque de subir des attaques par dictionnaire exploitant le protocole TLS 1.2. »
* B. « L'absence de mots de passe robustes expose l'entreprise au chiffrement de ses contrats par un pirate : arrêt de l'entrepôt, perte de chiffre d'affaires, notification CNIL. »
* C. « L'absence de stratégie de complexité empêche le processeur du serveur de fonctionner à son niveau optimal. »
* **Réponse correcte : B**
* *Explication* : Un décisionnaire arbitre des risques d'entreprise, pas des protocoles : traduire en impact métier (arrêt, coût, sanction, réputation) est la compétence qui débloque les budgets — la restitution managériale.

### Question 2 : La veille post-formation
Qu'implique une démarche de veille technologique régulière en cybersécurité ?

* A. Racheter de nouveaux ordinateurs portables tous les six mois.
* B. Consulter régulièrement les alertes des éditeurs et les bulletins du CERT-FR pour appliquer les correctifs sur les vulnérabilités nouvellement découvertes.
* C. Interdire définitivement l'accès à Internet à tous les salariés.
* **Réponse correcte : B**
* *Explication* : La sécurité n'est pas un état mais un processus : la veille (CERT-FR, rapports annuels de référence) permet de corriger les failles critiques avant leur exploitation automatisée à grande échelle.

### Question 3 : L'efficacité du MFA
Selon une étude Microsoft (2019), quelle proportion des attaques par compromission de compte l'activation du MFA permet-elle de bloquer ?

* A. Environ 50 %.
* B. Environ 80 %.
* C. Plus de 99 %.
* **Réponse correcte : C**
* *Explication* : Le meilleur rapport protection/effort de la cybersécurité — et l'argument chiffré face à l'objection « le MFA fait perdre du temps » : trois secondes par connexion contre un arrêt d'activité complet.

### Question 4 : Les « quick wins »
Dans un plan de remédiation, qu'appelle-t-on les « quick wins » ?

* A. Les mesures les plus chères, à planifier sur cinq ans.
* B. Les mesures à fort impact et faible effort, réalisables immédiatement : activer le MFA, fermer RDP/SSH exposés, changer le mot de passe administrateur, déconnecter la sauvegarde USB.
* C. Les mesures purement cosmétiques pour rassurer la direction.
* **Réponse correcte : B**
* *Explication* : Prioriser par impact/effort donne de la crédibilité au plan : des résultats visibles dès le premier mois financent politiquement les chantiers longs (segmentation, supervision, conformité).

### Question 5 : La règle d'or de la DMZ
Quelle règle de filtrage protège le réseau interne contre un rebond depuis la DMZ ?

* A. Autoriser tous les flux sortants du LAN interne vers la DMZ.
* B. Interdire tout flux initié depuis la DMZ vers le LAN administratif interne.
* C. Autoriser le trafic SSH de la DMZ vers le LAN.
* **Réponse correcte : B**
* *Explication* : La DMZ est la pièce sacrifiable : si le serveur web tombe, l'attaquant ne doit pas pouvoir rebondir vers l'interne. Le SENS d'initiation des flux fait la sécurité de l'architecture.

### Question 6 : Remplacer la sauvegarde USB
Quelle stratégie remplace efficacement une sauvegarde sur disque USB branché en permanence ?

* A. Une sauvegarde locale deux fois par jour sur un autre serveur du même réseau.
* B. La règle 3-2-1 avec une copie hors ligne et une copie immuable déportée — le disque branché en permanence serait chiffré AVEC le serveur.
* C. Des copies manuelles occasionnelles sur un service cloud personnel.
* **Réponse correcte : B**
* *Explication* : Plus de 9 attaques par rançongiciel sur 10 ciblent aussi les sauvegardes (Veeam, 2023) : seule une copie hors d'atteinte du réseau (hors ligne ou immuable) garantit la restauration.

### Question 7 : L'incident en pleine séance
Un rançongiciel chiffre les postes de la comptabilité et l'attaquant menace de publier des données de santé. Première mesure ?

* A. Éteindre complètement les ordinateurs du réseau et contacter l'ANSSI.
* B. Isoler chaque machine infectée (câble, Wi-Fi) et le réseau au pare-feu, SANS éteindre — pour stopper la propagation et préserver la RAM.
* C. Payer immédiatement la rançon avec la carte bancaire de l'entreprise.
* **Réponse correcte : B**
* *Explication* : Les réflexes de B18 : confiner sans détruire les preuves. Ensuite : cellule de crise, plainte (72 h, LOPMI), notification CNIL (données de santé : 72 h), restauration après éradication.

### Question 8 : Ce que le score d'audit ne dit pas
MedDistri termine l'audit avec un score de résilience de 80 %. Que faut-il garder à l'esprit ?

* A. L'entreprise est tranquille pour cinq ans.
* B. Le score photographie des DÉCISIONS à un instant donné : sans mise en œuvre vérifiée, veille, re-scans et exercices réguliers, il se dégrade — la sécurité est un processus, pas un état.
* C. Le score garantit l'absence légale de responsabilité en cas d'incident.
* **Réponse correcte : B**
* *Explication* : Les menaces évoluent (plus de 40 000 CVE en 2024), les configurations dérivent, les équipes changent. L'audit est une photo — la roue de Deming (B13) ne s'arrête jamais.

### Question 9 : La suite du parcours
Quelle certification constitue la « première marche » généraliste la plus accessible après ce parcours ?

* A. Le CISSP, qui exige environ cinq ans d'expérience professionnelle.
* B. CompTIA Security+, certification généraliste d'entrée validant les fondamentaux couverts par ce parcours.
* C. Aucune : les certifications n'existent plus.
* **Réponse correcte : B**
* *Explication* : Security+ valide le socle (le contenu de ce parcours en est une excellente préparation) ; CEH oriente vers l'offensif ; le CISSP vient plus tard, avec l'expérience. Et la pratique continue sur TryHackMe ou Hack The Box entretient les réflexes.

### Question 10 : La règle d'or du parcours
Quelle affirmation résume le mieux la leçon d'ensemble des 20 sessions ?

* A. La cybersécurité est un produit : le bon pare-feu suffit.
* B. La cybersécurité est un processus continu : des fondamentaux d'hygiène qui bloquent l'essentiel, des humains entraînés qui font la différence, et une vigilance qui recommence chaque matin.
* C. La cybersécurité est l'affaire exclusive du service informatique.
* **Réponse correcte : B**
* *Explication* : Des affaires étudiées (Target, Equifax, SolarWinds, Hydro…), une constante : les outils comptent moins que les processus et les réflexes des humains qui les opèrent. Entretenir ces réflexes est la mission d'après-formation.
