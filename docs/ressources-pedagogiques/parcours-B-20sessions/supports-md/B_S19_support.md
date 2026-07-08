# Session B19 — Simulation de crise cyber (Tabletop exercise)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Qu'est-ce qu'un Tabletop Exercise ?
    - Organisation de la cellule de crise cyber
    - Les règles d'or de la communication de crise
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Un **Tabletop Exercise** est un entraînement théorique permettant de tester la capacité décisionnelle d'une entreprise face à un scénario de cyberattaque.
*   La gestion de crise réunit la **Direction**, l'**IT**, la **Communication** et le **Juridique/DPO** pour coordonner la réponse technique, légale et réputationnelle.
*   La communication de crise doit être **factuelle, empathique, et centralisée** autour d'un porte-parole unique.
*   Toute fuite de données personnelles impose une notification rapide aux autorités de contrôle (**CNIL**) et aux personnes concernées.

---

## 2. Développement

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer le fonctionnement et l'intérêt d'une simulation de crise sur table (*Tabletop Exercise*) pour une organisation.
* Décrire les rôles et les responsabilités des membres clés d'une cellule de crise (Direction, IT, Communication, DPO/Juridique).
* Rédiger un communiqué de crise externe factuel, transparent et conforme aux obligations réglementaires (RGPD).

---

### Glossaire
*   **Tabletop Exercise** — Simulation sur table d'un incident de sécurité permettant de tester les plans de réponse sans impact réel sur la production.
*   **Inject (Stimulus)** — Nouvelle information ou rebondissement introduit par l'animateur d'une simulation pour faire évoluer le scénario de crise.
*   **Communication Hors Bande (Out-of-band)** — Utilisation de réseaux de communication indépendants du système d'information principal (ex. téléphones personnels, applications de messagerie chiffrée grand public) lorsque le réseau d'entreprise est compromis.

---

### Concepts clés

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

### 1. Qu'est-ce qu'un Tabletop Exercise ?
Un **Tabletop Exercise** (ou exercice sur table) est une simulation de crise théorique durant laquelle les décisionnaires d'une entreprise se réunissent pour réagir en temps réel à un scénario de cyberattaque fictif.

*   **Le Maître du Jeu (MJ)** : Il anime la session et apporte régulièrement de nouvelles informations perturbatrices (appelées **injects**), telles que : la découverte d'une fuite sur Twitter, la demande de rançon d'un pirate, l'appel téléphonique d'un client en colère ou d'un journaliste.
*   **Objectifs** :
    *   Tester l'efficacité et la clarté des procédures d'urgence (Playbooks).
    *   S'entraîner à prendre des décisions majeures en situation d'incertitude et sous pression de temps (ex. couper l'intégralité des serveurs de production, notifier la CNIL).
    *   Renforcer la coordination entre les départements techniques et non techniques.

### 2. Organisation de la cellule de crise cyber
Face à une cyberattaque d'ampleur, l'informatique ne peut pas décider seule. La **cellule de crise** regroupe plusieurs fonctions complémentaires :

*   **Le Directeur de Crise (Direction Générale)** : Il valide la stratégie globale, prend les décisions financières d'urgence (ex. recours à des experts externes) et assume la responsabilité légale finale de la gestion de crise.
*   **Le Responsable IT/Sécurité (RSSI/DSI)** : Il fournit le diagnostic technique, pilote les équipes d'investigation, propose les mesures d'isolation du réseau et évalue le temps nécessaire à la restauration des systèmes.
*   **Le Responsable Juridique / DPO** : Il analyse la responsabilité légale de l'entreprise, pilote la rédaction et l'envoi de la déclaration de violation de données personnelles à la **CNIL sous 72h**, et vérifie le respect des engagements contractuels vis-à-vis des clients.
*   **Le Responsable Communication** : Il rédige et distribue les messages destinés aux collaborateurs internes (pour éviter les rumeurs) et aux parties externes (presse, clients, partenaires).

### 3. Les règles d'or de la communication de crise
En période de crise cyber, une mauvaise communication peut causer plus de dégâts réputationnels et financiers que l'attaque technique elle-même.

> [!IMPORTANT]
> **Règles fondamentales de communication de crise** :
> 1.  **S'en tenir strictement aux faits** : Ne jamais mentir, spéculer ou désigner un coupable sans preuves techniques irréfutables du SOC.
> 2.  **Centraliser la parole** : Nommer un porte-parole unique. Il est formellement interdit aux salariés de s'exprimer sur l'incident, que ce soit à des journalistes ou sur leurs réseaux sociaux personnels.
> 3.  **Faire preuve d'empathie et de responsabilité** : Reconnaître la situation, exprimer des regrets pour la gêne occasionnée et expliquer les mesures concrètes mises en œuvre pour sécuriser et rétablir le système.
> 4.  **Transparence contrôlée** : Expliquer ce qui s'est passé de manière compréhensible sans pour autant dévoiler de détails techniques précis sur les faiblesses du réseau (ce qui pourrait aider d'autres attaquants).

---

### Activités / exercices
### Exercice 1 — Rédaction d'un communiqué de crise externe
**Objectif :** Rédiger un communiqué de presse officiel après une cyberattaque par ransomware avec fuite de données, en veillant à la précision factuelle et à la préservation de la réputation de l'entreprise.

**Consignes :**
L'entreprise EcoLog a subi une attaque par rançongiciel qui a perturbé ses outils logistiques. Le SOC a découvert qu'un fichier de facturation contenant les noms, adresses et historiques d'achats de 200 clients a été dérobé et mis en ligne sur un forum. La CNIL a été notifiée conformément à la loi. Un communiqué de presse officiel doit être publié. Rédigez ce texte en respectant les règles d'or de la communication de crise.

**Corrigé / Éléments de réponse :**

```text
COMMUNIQUÉ DE PRESSE — ÉCOLOG
Pour diffusion immédiate — Paris, le 29 juin 2026

EcoLog informe avoir été la cible d'un incident de sécurité informatique ayant
partiellement perturbé certains de ses systèmes de gestion des livraisons.

Dès la détection de l'événement, nos équipes techniques ont immédiatement isolé 
les serveurs affectés afin de contenir la propagation. Nous collaborons avec des 
experts externes en cybersécurité pour mener des investigations approfondies et 
assurer un retour sécurisé à la normale de nos opérations.

Nos premières analyses indiquent que des données de facturation (noms, adresses 
postales et historiques de commandes) relatives à un nombre limité de clients ont 
pu être consultées sans autorisation. Aucune coordonnée bancaire ni mot de passe 
n'a été compromis lors de cet incident.

Conformément à la réglementation en vigueur (RGPD), nous avons procédé à la 
notification de cet incident auprès de la CNIL. Les clients concernés par cette 
fuite de données sont en cours d'information individuelle afin de leur apporter 
les recommandations nécessaires.

EcoLog regrette sincèrement les désagréments causés par cet acte malveillant et 
réaffirme son engagement total envers la protection et la sécurité des données de 
ses clients et partenaires.

Contact Presse unique : service.presse@ecolog.fr
```

*Analyse pédagogique des points forts du communiqué rédigé :*

*   *Factuel et transparent* : L'entreprise admet l'attaque et la fuite sans essayer de minimiser l'existence de l'incident.
*   *Rassurant* : Précise immédiatement ce qui n'a **pas** été volé (mots de passe, coordonnées bancaires) pour limiter la panique des clients.
*   *Légal et responsable* : Mentionne explicitement la notification CNIL et la prise de contact individuelle avec les victimes, démontrant ainsi le respect des lois.

---

### Questions de réflexion
1. Pourquoi est-il déconseillé d'annoncer publiquement le montant d'une rançon exigée par des pirates, ou même le fait que l'on négocie avec eux ?
2. En cas de blocage complet du système de messagerie interne de l'entreprise lors d'une cyberattaque, comment la cellule de crise peut-elle communiquer de manière sécurisée avec ses membres et ses collaborateurs ? (Pensez aux canaux de communication dits "hors bande" ou *out-of-band*).

**Corrigé / Éléments de réponse :**
1. C'est illégal dans certains cas, et cela incite d'autres attaquants à cibler l'entreprise sachant qu'elle est prête à négocier.
2. Utiliser des messageries chiffrées externes (ex: Signal ou WhatsApp sur téléphones personnels) ou une infrastructure cloud totalement décorrélée du réseau d'entreprise.

---


### Cas d'usages et Exemples Concrets (Pour les débutants)

!!! info "Explication simplifiée"
    Pour bien comprendre ces concepts techniques, imaginez l'analogie suivante : la cybersécurité de votre entreprise est comme la sécurité d'une maison physique.
    - **Le Pare-feu (Firewall)** agit comme la porte d'entrée blindée : il filtre qui entre et qui sort.
    - **L'Antivirus / EDR** est comme le système d'alarme intérieur : s'il détecte un mouvement suspect, il bloque l'intrus.
    - **La Politique de mots de passe et le MFA** correspondent aux serrures multipoints et au digicode : posséder la clé ne suffit pas toujours, il faut aussi connaître le code secret.

**Exemple d'application professionnelle :**
Dans une PME, un attaquant tentera rarement de forcer les serveurs directement. Il enverra un e-mail frauduleux (Phishing) à un employé des ressources humaines. Si l'employé clique, le logiciel malveillant tente de s'installer. C'est ici que la *défense en profondeur* intervient : le filtre anti-spam aurait dû bloquer l'e-mail, l'antivirus aurait dû bloquer l'exécution, et l'absence de droits administrateurs de l'employé aurait empêché l'installation. Chaque couche est vitale.


## 3. Ressources Complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Incident Response Fundamentals"* (durée estimée : 1h30).
*   **Guide pratique** : Rechercher et lire le document *"Organiser un exercice de gestion de crise cyber"* édité par l'ANSSI pour comprendre comment concevoir un scénario de simulation complet de A à Z.

* [ANSSI - Agence Nationale de la Sécurité des Systèmes d'Information](https://www.ssi.gouv.fr/)
* [Cybermalveillance.gouv.fr](https://www.cybermalveillance.gouv.fr/)
* [OWASP - Open Worldwide Application Security Project](https://owasp.org/)

---

## 4. Exercice Bonus

- **Objectif :** Mise en pratique autonome.
- **Consignes :** Réfléchissez à un exemple réel ou une actualité récente liée au sujet de cette session. Discutez en groupe de la manière dont les concepts vus s'appliquent à cet exemple.
- **Correction :** Le mentor validera les réflexions et apportera son expertise.

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Tabletop Exercise** | Simulation sur table d'un incident de sécurité permettant de tester les plans de réponse sans impact réel sur la production. |
| **Inject (Stimulus)** | Nouvelle information ou rebondissement introduit par l'animateur d'une simulation pour faire évoluer le scénario de crise. |
| **Communication Hors Bande (Out-of-band)** | Utilisation de réseaux de communication indépendants du système d'information principal (ex. téléphones personnels, applications de messagerie chiffrée grand public) lorsque le réseau d'entreprise est compromis. |
