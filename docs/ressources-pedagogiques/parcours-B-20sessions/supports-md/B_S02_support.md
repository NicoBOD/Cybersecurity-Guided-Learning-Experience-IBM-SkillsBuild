# Session B02 — Paysage des menaces & acteurs

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Typologie des attaquants et motivations
    - La Cybercriminalité organisée : Une économie de services
    - La Cyber Threat Intelligence (CTI) : Connaître son ennemi
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Les attaquants se divisent en 4 familles majeures : cybercriminels (argent), États (géopolitique/espionnage), hacktivistes (causes politiques) et internes (employés).
*   La cybercriminalité moderne est professionnalisée et fonctionne en réseau (modèle de type RaaS - Ransomware-as-a-Service).
*   La Cyber Threat Intelligence (CTI) permet de collecter les indices techniques (IoC) laissés par les pirates pour renforcer proactivement nos défenses.
*   Le CERT-FR et la base MITRE ATT&CK sont des ressources essentielles de veille cyber opérationnelle.

---

## 2. Développement
Prenez 30 minutes pour classifier les acteurs de la menace : Script Kiddies (faible compétence, outils clés en main), Cybercriminels (financier, ransomwares), Hacktivistes (Anonymous, idéologie), et APT / États-Nations (Ressources illimitées, furtivité extrême). Expliquez la notion de surface d'attaque en constante expansion (IoT, télétravail).

---

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Catégoriser les quatre principaux profils de cyberattaquants (cybercriminels, États-nations, hacktivistes, menaces internes) et expliquer leurs motivations respectives.
* Expliquer le fonctionnement structurel de la cybercriminalité moderne sous forme d'économie de services (*Ransomware-as-a-Service*).
* Identifier et exploiter les sources de renseignement sur les menaces (*Cyber Threat Intelligence*) pour réaliser une veille efficace.

---

### Glossaire

*   **APT (Advanced Persistent Threat)** — Groupe d'attaquants sophistiqué, souvent étatique, menant des campagnes d'intrusion ciblées et à long terme.
*   **APT (Advanced Persistent Threat)** — Groupe d'attaquants hautement qualifié (généralement soutenu par un État) menant des cyberattaques ciblées et furtives sur le long terme.
*   **Dark Web** — Partie d'Internet accessible uniquement via des réseaux spécifiques (ex. Tor) où se déroulent des activités cybercriminelles comme la vente d'exploits.
*   **Insider Threat (Menace interne)** — Risque cyber provenant d'un employé, prestataire ou partenaire ayant des droits d'accès légitimes sur le réseau de l'entreprise.
*   **IOC (Indicator of Compromise)** — Indicateur de compromission technique (adresse IP, hash de fichier, domaine) signalant une activité potentiellement malveillante sur un système.
*   **IoC (Indicators of Compromise)** — Signes techniques (IP, empreinte numérique de fichier) indiquant qu'un système d'information a probablement été compromis par un intrus.
*   **RaaS (Ransomware-as-a-Service)** — Modèle de location logicielle où des criminels louent un ransomware clé en main en échange d'un pourcentage sur la rançon extorquée.
*   **Threat Intelligence** — Renseignements sur les cybermenaces consistant à collecter, analyser et organiser des informations sur les attaquants et leurs techniques.

---

### Concepts clés

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

### 1. Typologie des attaquants et motivations
Le monde des cyberattaquants est hétérogène. Identifier qui attaque permet de mieux anticiper les techniques employées et de calibrer la défense de l'entreprise. On distingue quatre grands profils d'acteurs de menace :

*   **Les Cybercriminels (Motivation lucrative)** : C'est le groupe le plus représenté. Leur seul but est de faire de l'argent. Ils utilisent des logiciels de rançon pour chiffrer les données d'entreprises de toutes tailles (hôpitaux, PME, multinationales) et exiger des rançons astronomiques, ou volent des données de cartes bancaires pour les revendre.
*   **Les États-nations (Motivation géopolitique, espionnage, sabotage)** : Ces groupes d'attaquants, souvent appelés **APT** (*Advanced Persistent Threat* — Menace persistante avancée), disposent de ressources financières et techniques quasi illimitées. Leurs objectifs sont l'espionnage industriel ou politique, le vol de propriété intellectuelle ou la déstabilisation d'infrastructures critiques (ex. coupure d'un réseau électrique).
*   **Les Hacktivistes (Motivation politique ou idéologique)** : Groupes de pirates informatiques militant pour une cause. Leurs attaques consistent le plus souvent à saturer un site web pour le rendre inaccessible (DDoS) ou à le défigurer (*defacement*) en remplaçant la page d'accueil par un message militant. Ils visent des entreprises ou gouvernements qu'ils considèrent comme contraires à leurs valeurs.
*   **La Menace Interne (*Insider Threat* - Motivation variée)** : Un collaborateur, un prestataire ou un administrateur système qui abuse de ses accès légitimes. Il peut agir par malveillance (vengeance d'un salarié licencié, sabotage de serveurs), par appât du gain (vol de secrets commerciaux pour les revendre à un concurrent) ou tout simplement par négligence.

### 2. La Cybercriminalité organisée : Une économie de services
Oubliez l'image du pirate solitaire en capuche dans son garage. La cybercriminalité actuelle est structurée comme une industrie légitime, avec une division du travail poussée :

*   **Le Ransomware-as-a-Service (RaaS)** : C'est un modèle d'affaires où des créateurs de malwares de pointe (les "opérateurs") louent leur code à des "affiliés" (les attaquants qui s'introduisent dans le réseau cible). Si l'attaque réussit et que la victime paye, la rançon est partagée (souvent 70-80 % pour l'affilié, 20-30 % pour l'opérateur).
*   **La spécialisation des rôles** : Cette économie s'accompagne d'intermédiaires spécialisés :
    *   Les *Initial Access Brokers* (courtiers d'accès initiaux) qui cherchent des failles, s'introduisent dans les réseaux, puis revendent ces accès aux groupes de ransomware.
    *   Des négociateurs de rançons spécialisés.
    *   Des réseaux de blanchiment d'argent par cryptomonnaies.

### 3. La Cyber Threat Intelligence (CTI) : Connaître son ennemi
La **CTI** (Renseignement sur les cybermenaces) consiste à collecter, analyser et organiser des informations sur les attaquants actifs et leurs méthodes.

*   **Les indicateurs de compromission (IoC — *Indicators of Compromise*)** : Ce sont les indices techniques laissés par les pirates (adresses IP de commande, signatures de fichiers malveillants, noms de domaine suspects).
*   **Les sources de confiance pour la veille** :
    *   Le **CERT-FR** (centre gouvernemental français d'alerte) publie régulièrement des fiches sur les vulnérabilités exploitées.
    *   La base de connaissances mondiale du **MITRE** répertorie les techniques réelles de chaque groupe d'attaquants.

> 💡 **Bon à savoir : APT (Advanced Persistent Threat)**
> Le terme "persistant" signifie que ces groupes étatiques ne font pas une intrusion rapide pour voler et repartir. Ils s'installent discrètement dans le réseau de la victime pendant des mois, voire des années, pour espionner et collecter des données à long terme sans se faire détecter.

---

### Activités / exercices
### Exercice 1 — Fiche d'identité d'un groupe APT
**Objectif :** Analyser le profil d'un groupe d'attaquants réel à partir de rapports de Threat Intelligence simplifiés pour comprendre ses objectifs et ses cibles.

**Consignes :**

1. Étudiez la description synthétique ci-dessous.
2. Complétez la "Fiche d'identité d'acteur" en identifiant le type d'attaquant, ses motivations probables, ses cibles préférées et ses techniques clés.

*   **Description de la menace** : Le groupe connu sous le nom de *Lazarus Group* (ou *APT38*) est actif depuis au moins 2009. Il est soupçonné d'être lié à un État d'Asie de l'Est. Ce groupe s'est fait connaître par le piratage massif de Sony Pictures en 2014, le vol de 81 millions de dollars à la Banque centrale du Bangladesh en 2016 (via le réseau interbancaire SWIFT), et la propagation mondiale du ransomware *WannaCry* en 2017. Le groupe cible principalement les institutions financières, les plateformes d'échange de cryptomonnaies et les infrastructures gouvernementales occidentales.

**Fiche d'identité d'acteur à compléter :**

*   **Nom du groupe d'attaque** : ...
*   **Origine géographique présumée** : ...
*   **Catégorie d'attaquant** (Cybercriminel, État-nation, Hacktiviste, Interne) : ...
*   **Motivations principales** (Financière, Espionnage, Sabotage, Militantisme) : ...
*   **Exemples d'attaques historiques majeures** : ...
*   **Cibles privilégiées** : ...

**Corrigé / Éléments de réponse :**

*   **Nom du groupe d'attaque** : Lazarus Group (APT38)
*   **Origine géographique présumée** : Corée du Nord (Asie de l'Est)
*   **Catégorie d'attaquant** : État-nation (avec la particularité unique de mener des actions financières à des fins étatiques).
*   **Motivations principales** : Financière (financement de l'État sous sanctions internationales) et Sabotage/Espionnage (comme lors du piratage de Sony Pictures).
*   **Exemples d'attaques historiques majeures** : WannaCry (2017), vol de la Banque du Bangladesh (2016), Sony Pictures (2014).
*   **Cibles privilégiées** : Banques, plateformes de cryptomonnaies, organisations gouvernementales.

---

### Questions de réflexion
1. Quelle différence majeure de défense appliquez-vous face à un cybercriminel opportuniste (qui attaque au hasard une PME vulnérable) vs un groupe APT étatique (qui cible précisément votre entreprise avec des ressources illimitées) ?
2. Pourquoi la menace interne (un collaborateur malveillant ou négligent) est-elle parfois considérée comme le risque le plus difficile à détecter pour une équipe de sécurité ?

**Corrigé / Éléments de réponse :**
1. Contre un cybercriminel opportuniste, on bloque les failles connues (hygiène de base). Contre un APT, on met en place une détection avancée (EDR/SOC) et du threat hunting car ils utiliseront des moyens inconnus.
2. L'interne a déjà des droits d'accès légitimes, donc ses actions se fondent dans le trafic normal. Les outils de sécurité classiques (pare-feu) sont conçus pour bloquer les menaces externes.

---


### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez le paysage des menaces cyber comme la **criminalité dans le monde physique** :
    - **Le voleur de rue** correspond au cybercriminel opportuniste : il cherche des portes déverrouillées (logiciels non mis à jour) pour voler ce qu'il peut (argent, données à revendre).
    - **L'espion industriel ou le commando militaire** représente l'APT (État-Nation) : il dispose de budgets colossaux, d'équipements de pointe et peut planifier son intrusion pendant des mois pour voler des plans secrets.
    - **Le manifestant devant un siège social** est le hacktiviste : il veut dégrader votre vitrine (défigurer votre site web) pour diffuser ses revendications politiques.
    - **Le garde corrompu ou l'employé négligent** est la menace interne.

**Exemple d'application professionnelle :**
Une entreprise technologique subit une intrusion discrète. Les outils de Threat Intelligence permettent de corréler les signatures techniques (IOCs) laissées par l'attaquant avec le mode opératoire documenté d'un groupe APT étatique. Grâce à ces données, l'équipe de sécurité comprend que l'attaquant cible spécifiquement les fichiers de R&D et applique immédiatement des mesures de confinement adaptées.


## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Cybersecurity Threat Landscape"* (~1h30).
*   **Action pratique** : Visiter le site du CERT-FR (cyber.gouv.fr/alertes) et lire la description d'une alerte "Active" pour comprendre comment les experts documentent une menace en temps réel.


---

* [CERT-FR - Centre gouvernemental de veille](https://www.cert.ssi.gouv.fr/)
* [Cybermalveillance - Rapport d'activité](https://www.cybermalveillance.gouv.fr)

## 4. Exercice bonus

- **Objectif :** Profilage de menace et analyse de Threat Intelligence.
- **Consignes :**
    1. Vous devez mener des recherches (ou simuler une analyse) sur un acteur de menace réel connu (ex. Cozy Bear / APT29 ou LockBit).
    2. Rédigez une fiche profil synthétique de cet acteur : motivations (financières, étatiques, géopolitiques), cibles privilégiées et techniques d'attaque récurrentes.
    3. Listez 2 indicateurs de compromission (IOC) typiques que cet acteur pourrait laisser sur votre réseau.
- **Correction pour le mentor :** Le mentor s'assurera que les profils rédigés par les apprenants distinguent bien les motivations cybercriminelles (gain rapide de LockBit via rançongiciel) des motivations d'espionnage (infiltration silencieuse et à long terme d'APT29). Les IOC mentionnés doivent être pertinents (ex. adresses IP de serveurs de commande C2 connus, empreintes SHA-256 de fichiers malveillants récurrents).

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **APT (Advanced Persistent Threat)** | Groupe d'attaquants sophistiqué, souvent étatique, menant des campagnes d'intrusion ciblées et à long terme. |
| **Dark Web** | Partie d'Internet accessible uniquement via des réseaux spécifiques (ex. Tor) où se déroulent des activités cybercriminelles comme la vente d'exploits. |
| **Insider Threat (Menace interne)** | Risque cyber provenant d'un employé, prestataire ou partenaire ayant des droits d'accès légitimes sur le réseau de l'entreprise. |
| **IoC (Indicators of Compromise)** | Signes techniques (IP, empreinte numérique de fichier) indiquant qu'un système d'information a probablement été compromis par un intrus. |
| **RaaS (Ransomware-as-a-Service)** | Modèle de location logicielle où des criminels louent un ransomware clé en main en échange d'un pourcentage sur la rançon extorquée. |
| **Threat Intelligence** | Renseignements sur les cybermenaces consistant à collecter, analyser et organiser des informations sur les attaquants et leurs techniques. |

