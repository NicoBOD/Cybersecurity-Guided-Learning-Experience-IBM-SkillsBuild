# Spécifications des slides — Session B03 : Types d'attaques & vecteurs
Parcours : B 20 sessions  |  Module : A — Fondations  |  Format : Spécifications Markdown

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Types d'attaques & vecteurs d'intrusion
  - Décoder la méthodologie d'une cyberattaque
  - Parcours B — Session B03
- **Notes orateur** : Bienvenue dans cette troisième session de notre parcours. Aujourd'hui, nous allons entrer dans la technique : comment fonctionnent les logiciels malveillants et quelles sont les étapes chronologiques par lesquelles passe un attaquant pour s'introduire dans un réseau d'entreprise.
- **Visuel suggéré** : Fond sombre avec des lignes de code informatique vertes et un symbole de crâne stylisé ou d'alerte système discret.
  - **alt-text** : Code source informatique affiché en vert cyberpunk sur un écran noir d'ordinateur.
- **Élément interactif** : Question à main levée pour savoir qui a déjà été confronté personnellement ou professionnellement à un malware.

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Classifier les familles de logiciels malveillants (*malwares*).
  - Modéliser une cyberattaque à l'aide des 7 étapes de la *Cyber Kill Chain*.
  - Découvrir la structure du framework MITRE ATT&CK.
  - Différencier les attaques DDoS des injections SQL applicatives.
  - Sommaire : Typologie des malwares (20 min), La Cyber Kill Chain (25 min), Infrastructure vs Web (15 min), Exercice Reconstruction d'incident (20 min), Quiz & Devoirs (10 min).
- **Notes orateur** : Nous avons un programme dense mais passionnant. Nous allons commencer par une classification claire des virus, vers et chevaux de Troie. Puis, nous verrons l'outil de référence pour analyser le déroulement d'une attaque : la Cyber Kill Chain, avant de passer à notre exercice de reconstruction d'incident.
- **Visuel suggéré** : Tableau divisé en deux parties présentant d'une part les concepts à acquérir et d'autre part le minutage précis.
  - **alt-text** : Mise en page moderne avec des icônes d'horloges et de dossiers pour structurer le planning de la session.

---

### Slide 3 — Qu'est-ce qu'un logiciel malveillant (Malware) ?
- **Type** : contenu
- **Points clés (bullets)** :
  - **Malware** : Contraction de *malicious software*.
  - Tout programme développé dans le but de nuire à un système ou d'en détourner l'usage.
  - Deux critères de distinction : comment il se propage et quel est son but final.
  - Les dégâts typiques : sabotage, espionnage, extorsion financière.
- **Notes orateur** : Le terme "virus" est souvent utilisé à tort pour désigner n'importe quel code malveillant. En réalité, le terme exact est "malware". Nous allons voir qu'il en existe de nombreuses familles, classées selon leur mode d'action et leur moyen de propagation.
- **Visuel suggéré** : Illustration d'un engrenage mécanique bloqué par un élément extérieur rouge symbolisant l'infection informatique.
  - **alt-text** : Dessin en 3D d'un rouage informatique endommagé avec une clé USB rouge insérée à côté.

---

### Slide 4 — Virus, Ver & Cheval de Troie
- **Type** : schéma
- **Points clés (bullets)** :
  - **Le Virus** : A besoin d'un fichier hôte et d'une action humaine pour s'exécuter et se propager.
  - **Le Ver (*Worm*)** : Autonome, il exploite les failles réseau pour se propager tout seul de machine en machine.
  - **Le Cheval de Troie (*Trojan*)** : Se cache derrière un programme légitime pour ouvrir une porte dérobée.
- **Notes orateur** : Ces trois malwares historiques se propagent de façons très différentes. Le virus attend que vous cliquiez sur une pièce jointe pour infecter un fichier. Le ver se déplace silencieusement sur le réseau sans votre aide. Le cheval de Troie se déguise en logiciel utile pour vous inciter à l'installer vous-même.
- **Visuel suggéré** : Schéma explicatif en trois sections montrant le fonctionnement de la propagation pour chaque type.
  - **alt-text** : Diagramme représentant la chaîne de propagation d'un virus (action humaine), d'un ver (de réseau en réseau) et d'un cheval de Troie (déguisement).

---

### Slide 5 — Rançongiciels & Logiciels espions
- **Type** : contenu
- **Points clés (bullets)** :
  - **Ransomware (Rançongiciel)** :
    - Chiffre les données de la victime avec une clé robuste.
    - Demande le paiement d'une rançon contre la clé de déchiffrement.
  - **Spyware (Logiciel espion)** :
    - S'installe discrètement pour surveiller l'activité.
    - Exemples : Keyloggers (enregistreurs de frappes), capture d'identifiants.
- **Notes orateur** : Le rançongiciel est le malware le plus visible et le plus destructeur financièrement pour les entreprises. À l'inverse, le logiciel espion cherche la discrétion la plus totale afin de voler des données personnelles ou d'entreprise sur une longue période sans se faire remarquer.
- **Visuel suggéré** : Une comparaison visuelle montrant un écran rouge bloqué (Ransomware) d'un côté, et de l'autre un œil stylisé observant discrètement des frappes clavier sur un ordinateur (Spyware).
  - **alt-text** : Illustration divisée : à gauche une interface de ransomware réclamant des bitcoins, à droite une silhouette d'œil observant un clavier virtuel.

---

### Slide 6 — Modéliser l'attaque : La Cyber Kill Chain
- **Type** : schéma
- **Points clés (bullets)** :
  - Créée par Lockheed Martin pour analyser les intrusions ciblées.
  - Découpe l'attaque en 7 étapes chronologiques obligatoires.
  - **Principe défensif** : Casser un seul maillon de cette chaîne suffit à stopper l'attaque et protéger l'entreprise.
- **Notes orateur** : Pour bloquer une attaque, nous n'avons pas besoin d'être infaillibles partout. La Cyber Kill Chain montre qu'une intrusion réussie est une succession d'étapes logiques. Si nous coupons la communication à n'importe quelle étape, par exemple lors de la livraison ou du commandement, l'attaque échoue.
- **Visuel suggéré** : Schéma d'une chaîne en acier dont l'un des maillons centraux est brisé par un bouclier vert.
  - **alt-text** : Graphique d'une chaîne métallique tendue représentant les 7 étapes, avec un maillon brisé au milieu.

---

### Slide 7 — Zoom sur les 7 étapes (1 à 4)
- **Type** : contenu
- **Points clés (bullets)** :
  - **1. Reconnaissance** : Recherche d'informations sur la cible (OSINT, LinkedIn).
  - **2. Armement (*Weaponization*)** : Création du malware associé à un exploit.
  - **3. Livraison (*Delivery*)** : Envoi de la charge utile (email, clé USB).
  - **4. Exploitation** : Déclenchement du malware en exploitant une vulnérabilité.
- **Notes orateur** : Les quatre premières étapes préparent et initient l'intrusion. Tout commence par la recherche d'informations sur l'entreprise, suivie de la création d'un document ou d'un email piégé. L'exploitation a lieu lorsque l'utilisateur clique sur le lien ou ouvre la pièce jointe, déclenchant la faille de sécurité.
- **Visuel suggéré** : Suite logique d'icônes : une loupe (reconnaissance), un marteau de forge (armement), une enveloppe volante (livraison) et un engrenage brisé (exploitation).
  - **alt-text** : Progression chronologique illustrée représentant les quatre premières phases de la Cyber Kill Chain.

---

### Slide 8 — Zoom sur les 7 étapes (5 à 7)
- **Type** : contenu
- **Points clés (bullets)** :
  - **5. Installation** : Le malware installe un accès permanent (persistance).
  - **6. Commandement & Contrôle (C2)** : La machine infectée contacte le serveur de l'attaquant pour recevoir des ordres.
  - **7. Actions sur Objectifs** : L'attaquant réalise son but (chiffrement, vol de données).
- **Notes orateur** : Une fois la faille exploitée, le pirate installe ses outils de persistence pour ne pas perdre l'accès en cas de redémarrage. La machine compromise ouvre ensuite une connexion sortante vers le serveur de contrôle de l'attaquant (C2) pour recevoir des ordres. Enfin, l'attaquant exécute son action finale, comme le chiffrement ou l'exfiltration de fichiers sensibles.
- **Visuel suggéré** : Suite d'icônes faisant suite à la slide précédente : une clé d'installation (installation), une antenne réseau émettant des ondes (C2) et un sac de données barré (actions sur objectifs).
  - **alt-text** : Progression chronologique illustrée représentant les trois dernières phases de la Cyber Kill Chain.

---

### Slide 9 — Le framework MITRE ATT&CK
- **Type** : contenu
- **Points clés (bullets)** :
  - Une encyclopédie collaborative mondiale des comportements d'attaquants.
  - Organisé sous forme de matrice.
  - **Tactiques** : Les objectifs de l'attaquant (Pourquoi ? Ex. Accès Initial, Persistance).
  - **Techniques** : Les méthodes utilisées pour atteindre l'objectif (Comment ? Ex. Phishing, Injection).
- **Notes orateur** : Le framework MITRE ATT&CK est l'outil indispensable des professionnels de la cybersécurité. Il permet de cartographier précisément les tactiques et techniques observées dans le monde réel afin de s'assurer que nos défenses couvrent l'ensemble des scénarios possibles.
- **Visuel suggéré** : Aperçu graphique épuré de la matrice MITRE ATT&CK montrant les colonnes de tactiques et les lignes de techniques associées.
  - **alt-text** : Représentation visuelle d'un tableau à double entrée simulant la matrice MITRE ATT&CK avec des cellules colorées en vert et gris.

---

### Slide 10 — Attaques d'infrastructure & d'applications
- **Type** : schéma
- **Points clés (bullets)** :
  - **Déni de service distribué (DDoS)** :
    - Surcharge d'un serveur par un réseau mondial de machines infectées (botnet).
    - But : rendre le service inaccessible (atteinte à la disponibilité).
  - **Injections SQL** :
    - Envoi de commandes de base de données déguisées dans des formulaires web.
    - But : contourner l'authentification ou voler les données (atteinte à la confidentialité/intégrité).
- **Notes orateur** : En dehors des malwares, les attaquants s'en prennent aux serveurs directement. Soit en saturant la bande passante avec un botnet pour bloquer les serveurs légitimes : c'est le DDoS. Soit en exploitant des erreurs de programmation sur un site web pour injecter du code et piller les bases de données : c'est l'injection SQL.
- **Visuel suggéré** : Diagramme montrant à gauche un serveur submergé par de multiples ordinateurs (DDoS) et à droite un formulaire web renvoyant une commande SQL vers une base de données.
  - **alt-text** : Schéma conceptuel illustrant les mécanismes d'une attaque DDoS par botnet et d'une injection SQL sur un formulaire web.

---

### Slide 11 — Activité pratique : Reconstruction d'incident
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Cas concret : Le piratage de l'usine "PlastiqueNord".
  - **Objectif** : Replacer les 7 événements réels de l'attaque dans l'ordre de la Cyber Kill Chain.
  - Durée : 20 minutes en équipes.
  - Restitution orale des rapporteurs de groupes.
- **Notes orateur** : Nous allons mettre en pratique la modélisation de la Cyber Kill Chain. Vous disposez de la description chronologique de l'attaque subie par l'entreprise PlastiqueNord, mais les événements sont désordonnés. À vous de retrouver quel événement correspond à chaque étape de 1 à 7.
- **Visuel suggéré** : Les 7 étapes de la chaîne listées de manière verticale avec des boîtes vides à côté pour y glisser les événements de A à G.
  - **alt-text** : Interface d'exercice montrant la structure verticale de la Kill Chain avec des encadrés d'événements mélangés à côté.
- **Élément interactif** : Travail collaboratif en groupes avec saisie partagée.

---

### Slide 12 — Conclusion & Travail autonome
- **Type** : récap
- **Points clés (bullets)** :
  - **Résumé** : Différence de propagation des malwares, utilité de la Cyber Kill Chain, et rôle des IoC.
  - **Devoirs** : Compléter le module SkillsBuild *"Introduction to Cybersecurity Tools & Cyber Attacks"* (~1h30).
  - **Pratique** : Visiter le site MITRE ATT&CK et rechercher la technique "Phishing" (T1566) pour lire sa fiche descriptive.
  - Prochaine session : *Ingénierie sociale & facteur humain (B04)*.
- **Notes orateur** : Félicitations pour votre travail sur la reconstruction d'incident ! Pour la prochaine séance, nous aborderons le maillon humain et les techniques de manipulation psychologique. Complétez bien le module SkillsBuild d'ici là. Bonne semaine à tous !
- **Visuel suggéré** : Illustration d'une page du site internet MITRE ATT&CK affichant la fiche de la technique Phishing T1566.
  - **alt-text** : Capture d'écran épurée montrant la page descriptive d'une technique cyber sur le site officiel de MITRE ATT&CK.
