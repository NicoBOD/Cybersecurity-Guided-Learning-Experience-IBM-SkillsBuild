# Session B17 — Outils SIEM & Analyse de logs

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Qu'est-ce qu'un SIEM ?
    - Anatomie d'une ligne de log
    - Les règles de corrélation logique
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Le **SIEM** centralise, normalise, corrèle et stocke les logs de sécurité de l'ensemble d'une entreprise.
*   Une ligne de log contient des informations clés indispensables : un **horodatage**, une **source (IP/compte)** et un **événement**.
*   L'analyse des codes d'état HTTP (ex. 200 vs 403/404) et de la taille des paquets est essentielle pour évaluer la réussite d'une tentative d'attaque.
*   Les **règles de corrélation** du SIEM détectent automatiquement des enchaînements logiques d'événements pour lever des alertes de sécurité en temps réel.

---

## 2. Développement

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer le rôle d'un outil SIEM dans la centralisation, la normalisation, la corrélation et le stockage des événements de sécurité.
* Analyser et décoder des lignes de logs brutes issues de serveurs web ou de systèmes d'exploitation pour identifier une anomalie ou une cyberattaque.
* Décrire le principe de fonctionnement d'une règle de corrélation logique pour automatiser la détection des menaces.

---

### Glossaire
*   **SIEM (Security Information and Event Management)** — Outil de gestion centralisée des logs et des alertes de sécurité en temps réel.
*   **Log (Journal)** — Fichier texte généré automatiquement par un système ou une application décrivant les événements survenus.
*   **Normalisation (Parsing)** : Processus de conversion de formats de journaux d'événements diversifiés dans un format de données unifié.
*   **Syslog** — Protocole réseau standard utilisé pour le transfert de messages de journaux d'événements d'une machine vers un serveur central.

---

### Concepts clés

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

### 1. Qu'est-ce qu'un SIEM ?
Un **SIEM** (*Security Information and Event Management* - Gestion des Informations et des Événements de Sécurité) est le moteur logiciel centralisé d'un SOC. Son but est de rassembler en temps réel tous les journaux d'événements (**logs**) générés par les équipements du système d'information (pare-feu, serveurs, routeurs, postes de travail) pour y détecter des activités suspectes.

Le traitement des données par un SIEM suit 4 étapes indispensables :

1.  **La Collecte** : Des agents logiciels légers installés sur les machines ou des protocoles d'envoi réseau standardisés (comme **Syslog**) transmettent les logs vers la base de données centrale du SIEM.
2.  **La Normalisation (Parsing)** : Les logs bruts proviennent de systèmes différents avec des formats variés. La normalisation traduit ces écritures hétérogènes dans un schéma de données unique (ex. séparer l'adresse IP, le port, le nom de l'utilisateur et le type d'action dans des colonnes standardisées).
3.  **La Corrélation** : C'est le croisement logique des données normalisées. Le SIEM recherche des relations logiques ou temporelles entre des événements apparemment indépendants survenant sur des machines distinctes pour lever des alertes d'attaque complexe.
4.  **Le Stockage & la Visualisation** : Les logs sont archivés de façon sécurisée (pour des analyses judiciaires ou pour la conformité légale) et présentés aux analystes SOC via des tableaux de bord interactifs (*dashboards*).

*Outils SIEM populaires* : Splunk, Wazuh (open-source), Elastic Security, Microsoft Sentinel.

### 2. Anatomie d'une ligne de log
Une **log** (ou journal d'événements) est une trace écrite générée automatiquement par un programme informatique à chaque action réalisée. Pour être exploitable par la sécurité, une log doit obligatoirement comporter au moins 3 éléments :

*   **L'horodatage (Timestamp)** : Date et heure précises (généralement normalisées en temps universel UTC).
*   **La source / l'acteur** : Adresse IP d'origine, nom d'hôte ou identifiant de l'utilisateur à l'origine de l'action.
*   **L'événement** : Description factuelle de l'action effectuée et son résultat.

#### Analyse d'une log Web Apache (Common Log Format) :
`198.51.100.45 - - [29/Jun/2026:16:42:57 +0200] "GET /admin/login.php HTTP/1.1" 200 4502`

*   `198.51.100.45` : L'adresse IP de la machine cliente (l'origine).
*   `[29/Jun/2026:16:42:57 +0200]` : La date, l'heure et le décalage horaire local (+0200 pour la France en été).
*   `"GET /admin/login.php HTTP/1.1"` : La méthode HTTP utilisée (`GET`), la page ou ressource demandée (`/admin/login.php`), et le protocole utilisé (`HTTP/1.1`).
*   `200` : Le code d'état HTTP retourné par le serveur. Le code **200** indique que la page a été trouvée et transmise avec succès au client (un code *404* indiquerait une page introuvable, et *500* une erreur serveur).
*   `4502` : La taille des données renvoyées au client en octets (environ 4,5 Ko).

### 3. Les règles de corrélation logique
Les analystes SOC écrivent des règles logiques ou des requêtes mathématiques pour configurer le moteur de corrélation du SIEM. Ces règles permettent de transformer un bruit d'arrière-plan de millions de logs en alertes ciblées de sécurité.

> [!TIP]
> **Exemple de règle de corrélation : Détection de force brute SSH**
> *   **Condition** : *SI* plus de 10 événements d'échec d'authentification SSH (identifiables sous Linux par la chaîne de caractères `Failed password` ou l'ID d'événement Windows `4625`) se produisent depuis la même adresse IP source vers la même machine cible dans un intervalle de temps inférieur ou égal à 60 secondes...
> *   **Action** : *ALORS* générer une alerte de priorité haute étiquetée *"Tentative de Force Brute SSH suspectée"*.

---

### Activités / exercices
### Exercice 1 — Analyse de logs Web d'un serveur e-commerce
**Objectif :** Analyser un jeu de données de logs web réelles pour identifier des comportements malveillants d'attaquants extérieurs et évaluer le résultat de l'attaque.

**Consignes :**
Vous êtes analyste de sécurité et vous analysez l'extrait de logs Apache ci-dessous provenant du serveur web d'EcoLog. Lisez attentivement ces 4 lignes chronologiques de logs et répondez aux questions.

```text
Ligne 1 : 192.168.1.100 - - [29/Jun/2026:10:00:01] "GET /index.php HTTP/1.1" 200 1200
Ligne 2 : 203.0.113.88 - - [29/Jun/2026:10:01:15] "GET /products.php?id=5 HTTP/1.1" 200 850
Ligne 3 : 203.0.113.88 - - [29/Jun/2026:10:01:20] "GET /products.php?id=5' UNION SELECT null, username, password FROM users-- HTTP/1.1" 200 4500
Ligne 4 : 203.0.113.88 - - [29/Jun/2026:10:01:25] "GET /admin/../../etc/passwd HTTP/1.1" 400 120
```

1.  Quelle est l'adresse IP de l'attaquant potentiel ? Justifiez votre choix en indiquant quelles lignes appuient votre hypothèse.
2.  Quelle cyberattaque est tentée à la **Ligne 3** ? Expliquez succinctement son principe.
3.  Cette attaque (Ligne 3) a-t-elle été bloquée par le serveur ou a-t-elle fonctionné ? Pour répondre, comparez la taille de la réponse (en octets) entre la ligne 2 et la ligne 3, et observez le code de retour HTTP.
4.  Quelle attaque est tentée à la **Ligne 4** ? A-t-elle fonctionné ?

**Corrigé / Éléments de réponse :**

1.  **Adresse IP de l'attaquant** : L'adresse IP suspecte est **203.0.113.88**.
    *   *Justification* : L'IP *192.168.1.100* (Ligne 1) effectue une requête classique et légitime sur la page d'accueil (`/index.php`). En revanche, l'IP *203.0.113.88* injecte des commandes SQL (Ligne 3) et tente d'accéder à des fichiers système (Ligne 4).
2.  **Attaque de la Ligne 3** : Il s'agit d'une tentative d'**Injection SQL (SQLi)**.
    *   *Explication* : L'attaquant injecte une commande SQL (`UNION SELECT null, username, password FROM users--`) dans le paramètre de requête `id` afin de forcer la base de données à divulguer le contenu de la table `users` contenant les identifiants et mots de passe.
3.  **Résultat de la Ligne 3** : L'attaque semble avoir **réussi**.
    *   *Justification* : Le code HTTP retourné est **200** (succès). De plus, la taille de la réponse passe de *850 octets* (pour un produit classique à la ligne 2) à *4500 octets* à la ligne 3. Ce volume de données supplémentaire anormal correspond à l'exfiltration de la table des utilisateurs renvoyée dans la page web.
4.  **Attaque de la Ligne 4** : Il s'agit d'une tentative de **Traversée de Répertoire** (*Directory Traversal* ou *Path Traversal*).
    *   *Explication* : L'attaquant utilise des séquences de retour arrière (`../../`) pour sortir de l'arborescence web du serveur et tenter de lire le fichier de configuration des utilisateurs de la machine Linux (`/etc/passwd`).
    *   *Résultat* : Cette attaque a **échoué**. Le code d'état HTTP retourné est **400** (Bad Request / Mauvaise Requête), indiquant que le serveur a refusé de traiter ou de formater cette requête invalide, et la taille de la réponse est très faible (120 octets, correspondant à un message d'erreur standard).

---

### Questions de réflexion
1. Si un cybercriminel réussit à compromettre le compte administrateur d'un serveur, quelle est généralement l'une de ses premières actions pour dissimuler ses traces ? Comment un SIEM moderne empêche-t-il cette manœuvre ? (Pensez au stockage déporté des logs).
2. Pourquoi la normalisation (parsing) des logs est-elle l'étape la plus chronophage lors de l'intégration d'une nouvelle application ou d'un nouvel équipement réseau dans un SIEM ?

**Corrigé / Éléments de réponse :**
1. L'attaquant essaie de supprimer les logs locaux pour masquer ses actions. Le SIEM collecte les logs en temps réel sur un serveur distant sécurisé, préservant ainsi la trace.
2. Chaque équipement (pare-feu, Windows, Linux) génère des logs dans un format totalement différent. Il faut créer des règles pour traduire chaque champ dans un format commun.

---

## 3. Ressources Complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Log Analysis and SIEM Concepts"* (durée estimée : 1h30).
*   **Recherche de syntaxe** : Rechercher le format de journal standardisé **CEF** (*Common Event Format*) ou **LEEF** (*Log Event Extended Format*) pour comprendre comment l'industrie de la cybersécurité structure les données de logs partagées entre outils.

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
| **SIEM (Security Information and Event Management)** | Outil de gestion centralisée des logs et des alertes de sécurité en temps réel. |
| **Log (Journal)** | Fichier texte généré automatiquement par un système ou une application décrivant les événements survenus. |
| **Normalisation (Parsing)** | Processus de conversion de formats de journaux d'événements diversifiés dans un format de données unifié. |
| **Syslog** | Protocole réseau standard utilisé pour le transfert de messages de journaux d'événements d'une machine vers un serveur central. |
