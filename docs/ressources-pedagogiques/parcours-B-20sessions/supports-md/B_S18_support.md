# Session B18 — Introduction à la réponse aux incidents

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Le cycle de réponse aux incidents (NIST SP 800-61 r2)
    - Confinement, Éradication et Recouvrement
    - Préservation des preuves : la règle d'or de la RAM
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   La gestion des incidents est un processus normalisé par le **NIST SP 800-61** en 6 étapes, de la préparation au retour d'expérience (REX).
*   En cas d'attaque par ransomware, l'urgence absolue est le **confinement** (isoler physiquement ou logiquement les machines du réseau).
*   Il ne faut **jamais éteindre électriquement** une machine infectée pour ne pas détruire les indices précieux localisés dans la **mémoire vive (RAM)**.
*   Les **Playbooks** (ou fiches réflexes) permettent aux équipes de réagir de manière calme et coordonnée en situation de stress cyber.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Les 4 phases de la Réponse aux Incidents (NIST SP 800-61)**
Détaillez le cycle de vie d'une attaque :
1. *Préparation* : Création des playbooks, cellules de crise, outillage.
2. *Détection et Analyse* : Qualifier l'alerte. S'agit-il d'un ransomware ou d'une erreur admin ?
3. *Confinement, Éradication et Recouvrement* : Couper le réseau (Confinement), supprimer les backdoors (Éradication), restaurer les sauvegardes (Recouvrement).
4. *Activité post-incident (Leçons apprises)* : L'étape la plus critique pour ne pas subir la même attaque le mois suivant.

**2. Ordre de volatilité et Forensics**
Expliquez pourquoi on ne doit **jamais** éteindre un ordinateur infecté par un ransomware : l'extinction vide la mémoire RAM qui contient potentiellement les clés de chiffrement et les preuves de l'attaque. L'ordre légal exige de d'abord dumper la RAM, puis les caches réseau, et enfin cloner le disque dur physique.

**3. Exercice de Tabletop (Simulation)**
Passez 20 minutes à faire un jeu de rôle avec la salle : "Il est 8h00, tous les écrans affichent une demande de rançon. Qui appelez-vous en premier ? Comment communiquez-vous si les e-mails sont coupés ?"


*(Même que A_S07 étendu)*. Insistez sur la notion de 'Leçons apprises' (Post-Incident Review). Une fois le système restauré, si on ne corrige pas la faille d'origine (ex: VPN non patché), l'entreprise sera repiratée la semaine suivante. Discutez de l'importance de ne pas détruire les preuves (ne pas formater les disques immédiatement).

---

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Citer et détailler les 6 phases du cycle de gestion des incidents de sécurité selon le standard international NIST SP 800-61 r2.
* Distinguer et planifier les étapes clés de confinement, d'éradication et de recouvrement après une cyberattaque.
* Rédiger une fiche réflexe opérationnelle (Playbook d'action rapide) pour guider un premier intervenant face à une attaque par rançongiciel.

---

### Glossaire

*   **CVE (Common Vulnerabilities and Exposures)** — Répertoire public attribuant un identifiant unique à chaque vulnérabilité logicielle connue.
*   **CVSS (Common Vulnerability Scoring System)** — Standard industriel évaluant de 0 à 10 la sévérité technique d'une vulnérabilité.
*   **CWE (Common Weakness Enumeration)** — Dictionnaire catégorisant les types de faiblesses architecturales ou de code logicielles sous-jacentes.
*   **Mémoire Volatile (RAM)** — Mémoire informatique à accès rapide effacée dès que l'alimentation électrique est coupée.
*   **NIST SP 800-61** — Guide de référence du gouvernement américain détaillant les bonnes pratiques de gestion des incidents de sécurité.
*   **Patch (Correctif de sécurité)** — Mise à jour logicielle publiée par un éditeur pour combler une faille de sécurité identifiée.
*   **Playbook** — Procédure de sécurité documentée détaillant pas à pas les actions à mener face à un type d'incident spécifique.
*   **REX (Retour d'Expérience)** — Analyse menée après la clôture d'un incident pour identifier les failles du processus de réponse et s'améliorer.

---

### Concepts clés

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

### 1. Le cycle de réponse aux incidents (NIST SP 800-61 r2)
Faire face à une cyberattaque ne s'improvise pas. L'institut de normalisation américain NIST a structuré le cycle de vie de la réponse à incident en **6 étapes chronologiques et itératives** :

```mermaid
graph TD
    A["1. Préparation"] --> B["2. Détection & Analyse"]
    B --> C["3. Confinement"]
    C --> D["4. Éradication"]
    D --> E["5. Recouvrement"]
    E --> F["6. Activité Post-incident (REX)"]
    F --> A
```

1.  **La Préparation** : Construire les défenses, sécuriser et tester les sauvegardes hors ligne, former les équipes techniques et rédiger les procédures d'urgence (**Playbooks**).
2.  **La Détection et l'Analyse** : Détecter les premiers indices d'une intrusion (alertes SIEM, rapports d'utilisateurs), analyser la sévérité et identifier la nature de l'attaque.
3.  **Le Confinement** : Limiter la propagation de la menace au reste du réseau pour protéger les systèmes encore sains (ex. isoler une machine compromise).
4.  **L'Éradication** : Nettoyer les systèmes infectés en supprimant les programmes malveillants, en fermant les comptes compromis et en corrigeant les failles exploitées par l'attaquant.
5.  **Le Recouvrement (Récupération)** : Restaurer les systèmes affectés à partir de sauvegardes saines, valider leur bon fonctionnement et surveiller étroitement le retour en production.
6.  **L'Activité Post-incident (Retour d'Expérience - REX)** : Analyser les défaillances ayant permis l'attaque, documenter les leçons apprises et mettre à jour la PSSI et les processus pour éviter toute récidive.

### 2. Confinement, Éradication et Recouvrement
Ces trois étapes constituent le cœur opérationnel de la gestion d'un incident actif :

*   **Confinement** : On stoppe l'hémorragie. L'objectif n'est pas encore de réparer, mais d'éviter que la menace n'atteigne d'autres serveurs.
*   **Éradication** : On assainit. On cherche toutes les portes dérobées (*backdoors*) créées par le pirate pour s'assurer qu'il ne pourra pas revenir.
*   **Recouvrement** : On redémarre. On remet les services en ligne progressivement en s'assurant que les vulnérabilités de départ ont bien été corrigées.

*L'analogie de l'incendie de cuisine* :

*   Le **confinement** consiste à fermer la porte de la cuisine pour empêcher la fumée et les flammes d'envahir le reste de la maison.
*   L'**éradication** consiste à utiliser l'extincteur pour éteindre le feu à sa source et enlever les débris brûlés.
*   Le **recouvrement** consiste à nettoyer la suie, repeindre les murs et installer une nouvelle cuisinière pour reprendre une activité normale.

### 3. Préservation des preuves : la règle d'or de la RAM
Lorsqu'un utilisateur ou un technicien découvre qu'une machine est victime d'une attaque active (ex. fichiers qui se chiffrent en direct par un ransomware), le premier réflexe est souvent d'éteindre brusquement l'ordinateur en restant appuyé sur le bouton d'alimentation ou en débranchant la prise électrique.

> [!WARNING]
> **Ne jamais éteindre brutalement une machine compromise !**
> *   **Destruction de la mémoire vive (RAM)** : La RAM est une mémoire volatile. Si vous éteignez la machine, toutes les données en cours d'exécution sont définitivement effacées. Or, c'est en RAM que se trouvent les indices les plus précieux : les processus malveillants actifs, les connexions réseau en cours, les adresses IP des pirates, et parfois même **la clé de déchiffrement du rançongiciel**.
> *   **Accélération des dommages** : Certains malwares profitent du redémarrage pour chiffrer les fichiers de démarrage du système d'exploitation et rendre la machine définitivement inutilisable.
> *   **La bonne pratique** : **Isoler du réseau** en débranchant le câble Ethernet et en désactivant le Wi-Fi, mais **laisser la machine allumée** pour permettre au SOC d'extraire la mémoire vive.

---

### Activités / exercices
### Exercice 1 — Rdaction d'un Playbook "Premier Répondant Ransomware"
**Objectif :** Rédiger une fiche de procédure claire, séquentielle et dénuée de jargon technique complexe, utilisable immédiatement par le technicien du centre d'appels informatique (Helpdesk) lorsqu'un employé appelle paniqué.

**Consignes :**
L'entreprise EcoLog souhaite créer sa fiche d'action d'urgence pour le Helpdesk. Rédigez les 5 étapes chronologiques et impératives que le technicien Helpdesk doit appliquer et faire appliquer à l'utilisateur au téléphone en cas de détection d'un ransomware.

**Corrigé / Éléments de réponse :**

```text
FICHE RÉFLEXE : SIGNALEMENT DE RANSOMGICIEL (HELP-DESK)
--------------------------------------------------------------------------------
DÉFINITION : L'utilisateur signale un écran bloqué avec une demande de rançon,
ou des fichiers professionnels impossibles à ouvrir avec une extension ".locked".

Étape 1 : ISOLATION DU RÉSEAU (Action immédiate de l'utilisateur)
-> Demander à l'utilisateur de débrancher immédiatement le câble réseau (Ethernet)
   de sa machine et de désactiver le Wi-Fi (activer le mode avion).
   *Pourquoi ?* Pour bloquer la propagation du virus vers les serveurs de fichiers
   partagés de l'entreprise.

Étape 2 : MAINTIEN DE L'ALIMENTATION ÉLECTRIQUE
-> Ordonner formellement à l'utilisateur de LAISSER LA MACHINE ALLUMÉE.
   Ne pas éteindre, ne pas redémarrer.
   *Pourquoi ?* Pour préserver la mémoire vive (RAM) qui contient les preuves
   techniques et potentiellement la clé de déchiffrement.

Étape 3 : COLLECTE DES PREMIÈRES INFORMATIONS
-> Demander à l'utilisateur :

   - L'heure exacte du premier message d'erreur ou du comportement anormal.
   - Le message affiché à l'écran (lui demander de prendre une photo de l'écran
     avec son téléphone portable et de l'envoyer par SMS/canal secondaire).

   - Les noms des derniers fichiers ou dossiers ouverts avant le blocage.

Étape 4 : SIGNALEMENT AUX RESPONSABLES DE SÉCURITÉ (Escalade)
-> Créer un ticket d'incident prioritaire avec le tag [CRITIQUE - RANSOMWARE].
   Alerter immédiatement par téléphone le RSSI et l'analyste SOC de garde.
   Leur communiquer l'adresse IP de la machine, le nom de l'utilisateur et la photo
   du message de rançon.

Étape 5 : CONSIGNATION DE L'INCIDENT
-> Rédiger un compte rendu factuel dans l'outil de gestion d'incidents détaillant
   l'heure d'appel, les actions menées par le helpdesk, et l'heure d'isolation
   physique de la machine.
```

---

### Questions de réflexion
1. Pourquoi la phase "Activité Post-incident" (Leçons apprises) est-elle souvent négligée par les entreprises ? Quel est le risque de sauter cette étape une fois la production rétablie ?
2. Imaginez qu'une entreprise restaure ses serveurs à partir de sauvegardes datant de la veille de l'attaque sans avoir identifié la vulnérabilité d'origine. Quel événement risquez-vous de voir se produire dans les heures qui suivent le recouvrement ?

**Corrigé / Éléments de réponse :**
1. Sans retour d'expérience, les mêmes failles de processus demeurent et l'entreprise risque de subir la même attaque dans le futur.
2. Si la faille n'est pas corrigée, l'attaquant l'utilisera immédiatement à nouveau pour re-pirater le système fraîchement restauré.

---


### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez le processus de gestion des vulnérabilités comme l'**entretien de la plomberie d'un grand immeuble** :
    - **L'identification** consiste à inspecter tous les tuyaux pour trouver des fuites ou des zones de rouille (scans de vulnérabilités répertoriant les faiblesses logicielles).
    - **Le score CVSS** est l'évaluation de la gravité d'un tuyau rouillé : si c'est la conduite d'alimentation d'eau principale qui risque d'éclater au sous-sol (CVSS 9.8 - critique), il faut la remplacer immédiatement. Si c'est un robinet qui goutte dans un bureau inutilisé (CVSS 3.0), cela peut attendre.
    - **La remédiation (Patching)** consiste à réparer le tuyau ou à souder un renforcement (appliquer la mise à jour corrective).
    - **La différence entre CVE et CWE** : La *CVE* est l'adresse de la fuite sur un tuyau précis acheté chez un constructeur (ex. la faille Log4j sur tel logiciel). La *CWE* est la cause générale du défaut de construction (ex. utiliser des métaux de mauvaise qualité).

**Exemple d'application professionnelle :**
Un scanner de vulnérabilités remonte une faille critique de type exécution de code à distance (CVE-2021-44228) affectant plusieurs serveurs d'une entreprise. Grâce aux scores CVSS et à l'analyse de l'exposition internet des serveurs, l'équipe de sécurité priorise le patch de la machine externe en moins de 24h, neutralisant le risque avant toute intrusion.


### Panorama des solutions du marché (Commerciales & Open-Source)

Pour mener des investigations après incident et cartographier les vulnérabilités de l'infrastructure logicielle (CVE) :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Tenable Nessus / Tenable.io** : Référence mondiale pour le scan et le management des vulnérabilités, offrant une détection précise des CVE et des configurations défectueuses.
    *   **Qualys VMDR** : Plateforme SaaS leader de détection des vulnérabilités et de priorisation des correctifs en temps réel.
    *   **Rapid7 InsightVM** : Solution d'évaluation des vulnérabilités fournissant une visibilité en continu sur l'exposition et les menaces actives.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **Greenbone Community Edition (OpenVAS)** : Scanner de vulnérabilités open-source très complet pour évaluer les vulnérabilités de réseau local et de serveurs.
    *   **Wazuh** : Outil open-source qui intègre un module de détection automatique des vulnérabilités logicielles en corrélant la liste des paquets installés sur les agents avec la base de données CVE officielle.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Incident Response Fundamentals"* (durée estimée : 1h30).
*   **Étude documentaire** : Télécharger le modèle de plan de réponse à incident fourni gratuitement par l'ANSSI pour observer comment s'organise une cellule de crise au niveau national.


---

* [ANSSI - Gestion des incidents cyber](https://cyber.gouv.fr)
* [Cybermalveillance - Victime d'attaque](https://www.cybermalveillance.gouv.fr)

## 4. Exercice bonus

- **Objectif :** Analyse d'une vulnérabilité critique et plan d'action de remédiation.
- **Consignes :**
    1. Soit la vulnérabilité CVE-2024-XXXX affectant votre serveur de messagerie externe, notée 9.8 sur l'échelle CVSS. L'exploit est public et activement utilisé dans le monde.
    2. Rédigez le plan d'action d'urgence en 3 étapes à présenter à vos techniciens pour traiter cette menace.
    3. Quelle mesure temporaire (Workaround) pouvez-vous appliquer si aucun correctif n'est encore disponible ?
- **Correction pour le mentor :** Plan attendu : 1. Isoler le serveur de messagerie d'Internet temporairement si possible ou restreindre les flux. 2. Télécharger et appliquer le patch officiel de l'éditeur de messagerie. 3. Mener une analyse de logs pour vérifier si le serveur n'a pas déjà été compromis avant l'application du patch. Mesure temporaire (Workaround) : Bloquer le port spécifique utilisé par la faille sur le pare-feu externe ou désactiver la fonctionnalité vulnérable dans la configuration du logiciel.

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **CVE (Common Vulnerabilities and Exposures)** | Répertoire public attribuant un identifiant unique à chaque vulnérabilité logicielle connue. |
| **CVSS (Common Vulnerability Scoring System)** | Standard industriel évaluant de 0 à 10 la sévérité technique d'une vulnérabilité. |
| **CWE (Common Weakness Enumeration)** | Dictionnaire catégorisant les types de faiblesses architecturales ou de code logicielles sous-jacentes. |
| **Mémoire Volatile (RAM)** | Mémoire informatique à accès rapide effacée dès que l'alimentation électrique est coupée. |
| **NIST SP 800-61** | Guide de référence du gouvernement américain détaillant les bonnes pratiques de gestion des incidents de sécurité. |
| **Patch (Correctif de sécurité)** | Mise à jour logicielle publiée par un éditeur pour combler une faille de sécurité identifiée. |
| **Playbook** | Procédure de sécurité documentée détaillant pas à pas les actions à mener face à un type d'incident spécifique. |
| **REX (Retour d'Expérience)** | Analyse menée après la clôture d'un incident pour identifier les failles du processus de réponse et s'améliorer. |

