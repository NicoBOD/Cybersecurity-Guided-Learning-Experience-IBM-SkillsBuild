# Session B03 — Types d'attaques & vecteurs

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - La typologie des logiciels malveillants (*malwares*)
    - Modéliser l'attaque : Cyber Kill Chain & MITRE ATT&CK
    - Attaques d'infrastructure et d'applications
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Les malwares se différencient par leur propagation (vers autonomes vs virus dépendants) et leurs buts (ransomwares pour rançonner, spywares pour espionner).
*   Un DDoS utilise des machines infectées à distance (botnets) pour surcharger et mettre hors ligne des serveurs web.
*   La Cyber Kill Chain modélise une attaque en 7 étapes : perturber une seule de ces étapes permet de stopper l'intrusion.
*   Le framework MITRE ATT&CK offre un langage universel pour classifier les tactiques (buts) et techniques (moyens) observées chez les attaquants.

---

## 2. Développement
Plongez dans les détails de la Cyber Kill Chain de Lockheed Martin. Décortiquez chaque étape : Reconnaissance, Armement, Livraison, Exploitation, Installation, Commandement & Contrôle (C2), et Actions sur les objectifs. Montrez comment l'interruption de la chaîne à n'importe quelle étape fait échouer l'attaque complète.

---

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Classifier les principales familles de logiciels malveillants (*malwares*) en fonction de leur mode de propagation et de leur objectif.
* Modéliser le déroulement d'une cyberattaque complexe à l'aide des 7 étapes de la *Cyber Kill Chain*.
* Naviguer dans le framework d'analyse technique MITRE ATT&CK pour décoder les tactiques et techniques des attaquants.
* Expliquer le principe général des attaques par déni de service (DoS/DDoS) et des injections applicatives (web).

---

### Glossaire
*   **Worm (Ver)** — Logiciel malveillant capable de se propager de manière autonome dans un réseau en exploitant des vulnérabilités sans intervention humaine.
*   **Trojan (Cheval de Troie)** — Programme nuisible camouflé sous l'apparence d'un logiciel légitime pour tromper l'utilisateur et infecter son système.
*   **Cyber Kill Chain** — Modèle en 7 étapes théorisé par Lockheed Martin décrivant le cycle de vie d'une attaque ciblée.
*   **Command & Control (C2)** — Serveur externe contrôlé par un attaquant servant à envoyer des commandes à des systèmes piratés au sein d'un réseau cible.

---

### Concepts clés

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

### 1. La typologie des logiciels malveillants (*malwares*)
Un *malware* (contraction de *malicious software*) est un programme développé dans le but de nuire à un système informatique. On les classe selon leur mode d'action et de propagation :

*   **Le virus** : Un programme qui s'attache à un fichier ou à un programme légitime. Il a besoin d'une action humaine (comme l'ouverture d'une application ou d'un fichier infecté) pour s'exécuter et se propager.
*   **Le ver (*worm*)** : Contrairement au virus, le ver est autonome. Il exploite les failles réseau pour se propager automatiquement de machine en machine, sans aucune interaction humaine.
*   **Le cheval de Troie (*Trojan horse*)** : Un programme malveillant qui se dissimule au sein d'un logiciel apparemment inoffensif et légitime (ex. un jeu gratuit ou un utilitaire de nettoyage). Une fois installé, il ouvre une porte dérobée (*backdoor*) pour l'attaquant.
*   **Le rançongiciel (*ransomware*)** : Il prend en otage les données de l'ordinateur en les chiffrant avec une clé mathématique robuste. L'attaquant exige le paiement d'une rançon en cryptomonnaies pour fournir la clé de déchiffrement.
*   **Le logiciel espion (*spyware*)** : Il s'installe discrètement pour surveiller l'activité de l'utilisateur (historique de navigation, captures d'écran) ou enregistrer les frappes au clavier (*keylogger*) afin de voler des identifiants et des mots de passe.

### 2. Modéliser l'attaque : Cyber Kill Chain & MITRE ATT&CK
Pour se défendre efficacement, il faut comprendre le parcours de l'attaquant. Deux cadres d'analyse font autorité :

#### La Cyber Kill Chain (Lockheed Martin)
Elle découpe une attaque ciblée en 7 étapes chronologiques obligatoires. Briser un seul maillon de cette chaîne suffit à stopper l'attaque :

1.  **Reconnaissance** : Collecte d'informations sur la cible (adresses email, serveurs exposés).
2.  **Armement (*Weaponization*)** : Création d'une charge utile malveillante (ex. un document Word piégé avec un exploit).
3.  **Livraison (*Delivery*)** : Envoi de la charge utile (ex. email de phishing, clé USB déposée).
4.  **Exploitation** : Déclenchement du code malveillant en exploitant une vulnérabilité sur la machine cible.
5.  **Installation** : Établissement d'une présence permanente sur la machine compromise (installation d'un cheval de Troie).
6.  **Commandement & Contrôle (C2 - *Command & Control*)** : Ouverture d'un canal de communication chiffré vers un serveur externe contrôlé par l'attaquant pour recevoir des ordres.
7.  **Actions sur Objectifs** : Réalisation de l'objectif final (vol de données, chiffrement des serveurs, destruction de systèmes).

#### Le framework MITRE ATT&CK
Il s'agit d'une encyclopédie mondiale et dynamique recensant les comportements réels des attaquants sous forme de matrice. Elle structure les **tactiques** (le but de l'attaquant, ex. *Accès initial*) et les **techniques** (comment il y parvient, ex. *Phishing*).

### 3. Attaques d'infrastructure et d'applications
En dehors des logiciels malveillants, les attaquants ciblent les capacités physiques ou logiques des serveurs :

*   **Déni de service (DoS/DDoS)** : L'attaquant sature la bande passante réseau ou les ressources d'un serveur à l'aide de millions de requêtes simultanées pour le rendre inaccessible aux utilisateurs légitimes. On parle de DDoS (Déni de service distribué) lorsque ces requêtes proviennent d'un réseau mondial de machines infectées contrôlées à distance (un réseau de robots ou *botnet*).
*   **Les injections web (SQL)** : Attaque applicative consistant à envoyer des commandes de base de données (SQL) déguisées en simples entrées utilisateur (dans un formulaire de connexion par exemple). Si le site est mal programmé, le serveur exécute ces commandes, permettant à l'attaquant de voler ou supprimer l'ensemble de la base de données.

---

### Activités / exercices
### Exercice 1 — Reconstruction d'incident (Cyber Kill Chain)
**Objectif :** Analyser le scénario chronologique d'un piratage d'entreprise et associer chaque événement réel à l'une des 7 étapes de la *Cyber Kill Chain*.

**Consignes :**

1. Lisez le récit de l'incident de l'entreprise "PlastiqueNord" ci-dessous.
2. Pour chaque étape (1 à 7) de la liste, retrouvez la phrase de l'incident qui y correspond.

*   **Récit de l'incident** :
    *   *Événement A* : Les attaquants chiffrent les bases de données de production de l'usine PlastiqueNord et affichent une demande de rançon sur tous les serveurs.
    *   *Événement B* : L'attaquant effectue des recherches sur LinkedIn pour lister les adresses e-mail des gestionnaires RH de l'entreprise.
    *   *Événement C* : Le cheval de Troie configuré par l'attaquant télécharge un utilitaire persistant qui s'exécute automatiquement à chaque démarrage du serveur.
    *   *Événement D* : Le serveur de PlastiqueNord établit une connexion sortante cryptée toutes les 5 minutes vers l'adresse IP externe du serveur pirate pour recevoir des instructions.
    *   *Événement E* : Le gestionnaire RH clique sur le lien présent dans le mail, ce qui déclenche une faille de sécurité dans son navigateur web non mis à jour.
    *   *Événement F* : L'attaquant conçoit un e-mail de phishing ciblé contenant un lien vers une page web maquillée et y intègre un code d'exploitation de navigateur.
    *   *Événement G* : L'attaquant envoie l'e-mail de phishing usurpant l'identité du service comptable à l'équipe RH.

**Corrigé / Éléments de réponse :**

*   **Étape 1 : Reconnaissance** $\rightarrow$ **Événement B** (recherche d'adresses email RH sur LinkedIn).
*   **Étape 2 : Armement (*Weaponization*)** $\rightarrow$ **Événement F** (conception de l'email de phishing avec l'exploit).
*   **Étape 3 : Livraison (*Delivery*)** $\rightarrow$ **Événement G** (envoi de l'email de phishing ciblé).
*   **Étape 4 : Exploitation** $\rightarrow$ **Événement E** (le clic déclenche la faille de sécurité du navigateur).
*   **Étape 5 : Installation** $\rightarrow$ **Événement C** (installation de la persistance sur le serveur).
*   **Étape 6 : Commandement & Contrôle (C2)** $\rightarrow$ **Événement D** (connexion régulière sortante vers l'IP pirate).
*   **Étape 7 : Actions sur Objectifs** $\rightarrow$ **Événement A** (chiffrement et demande de rançon).

---

### Questions de réflexion
1. Pourquoi la phase de Commandement et Contrôle (C2) de la Kill Chain nécessite-t-elle généralement une connexion *sortante* (du réseau de l'entreprise vers Internet) plutôt qu'une connexion *entrante* ? (Indice : Pensez au comportement par défaut des pare-feu réseau).
2. Si vous bloquez l'envoi des e-mails malveillants (étape de Livraison), l'attaquant peut-il tout de même compromettre vos serveurs ? Pourquoi la défense doit-elle être organisée en "couches" ?

**Corrigé / Éléments de réponse :**
1. Les pare-feu d'entreprise bloquent presque toutes les connexions entrantes non sollicitées, mais autorisent les flux sortants (navigation web). L'attaquant fait donc 'téléphoner' le malware vers l'extérieur pour contourner le filtrage.
2. L'attaquant peut trouver d'autres vecteurs (clé USB, faille exposée). La défense en profondeur permet qu'une couche pallie la défaillance d'une autre.

---


### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Pour bien comprendre ces concepts techniques, imaginez l'analogie suivante : la cybersécurité de votre entreprise est comme la sécurité d'une maison physique.
    - **Le Pare-feu (Firewall)** agit comme la porte d'entrée blindée : il filtre qui entre et qui sort.
    - **L'Antivirus / EDR** est comme le système d'alarme intérieur : s'il détecte un mouvement suspect, il bloque l'intrus.
    - **La Politique de mots de passe et le MFA** correspondent aux serrures multipoints et au digicode : posséder la clé ne suffit pas toujours, il faut aussi connaître le code secret.

**Exemple d'application professionnelle :**
Dans une PME, un attaquant tentera rarement de forcer les serveurs directement. Il enverra un e-mail frauduleux (Phishing) à un employé des ressources humaines. Si l'employé clique, le logiciel malveillant tente de s'installer. C'est ici que la *défense en profondeur* intervient : le filtre anti-spam aurait dû bloquer l'e-mail, l'antivirus aurait dû bloquer l'exécution, et l'absence de droits administrateurs de l'employé aurait empêché l'installation. Chaque couche est vitale.


## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Introduction to Cybersecurity Tools & Cyber Attacks"* (~1h30).
*   **Ressource complémentaire** : Visiter le site officiel d'ATT&CK (attack.mitre.org) et cliquer sur la technique "Phishing" (T1566) pour observer comment les techniques sont documentées mondialement.


---

* [Cybermalveillance - Fiche Ransomware](https://www.cybermalveillance.gouv.fr/tous-nos-contenus/fiches-reflexes/rancongiciels-ransomwares)
* [OWASP - Vulnérabilités](https://owasp.org/)

## 4. Exercice bonus

- **Objectif :** Mise en pratique autonome.
- **Consignes :** Réfléchissez à un exemple réel ou une actualité récente liée au sujet de cette session. Discutez en groupe de la manière dont les concepts vus s'appliquent à cet exemple.
- **Correction :** Le mentor validera les réflexions et apportera son expertise.

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Worm (Ver)** | Logiciel malveillant capable de se propager de manière autonome dans un réseau en exploitant des vulnérabilités sans intervention humaine. |
| **Trojan (Cheval de Troie)** | Programme nuisible camouflé sous l'apparence d'un logiciel légitime pour tromper l'utilisateur et infecter son système. |
| **Cyber Kill Chain** | Modèle en 7 étapes théorisé par Lockheed Martin décrivant le cycle de vie d'une attaque ciblée. |
| **Command & Control (C2)** | Serveur externe contrôlé par un attaquant servant à envoyer des commandes à des systèmes piratés au sein d'un réseau cible. |
