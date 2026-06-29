# Plan de séance — Session B17
Parcours : B 20 sessions  |  Module : E — Opérations, détection & réponse  |  Durée : 1h30 (90 minutes)

## 1. Métadonnées de la session
* **Titre** : Outils SIEM & Analyse de logs
* **Objectifs pédagogiques opérationnels** :
  * Expliquer le rôle d'un outil SIEM (Security Information and Event Management) dans la centralisation, la normalisation, la corrélation et le stockage des événements de sécurité.
  * Analyser et interpréter des lignes de logs brutes issues de différentes sources (pare-feu, serveur web HTTP, système d'exploitation Windows/Linux) pour identifier une activité malveillante ou anormale.
  * Configurer une règle de corrélation logique simple (ex. alerte de tentative de force brute).
* **Prérequis** : B05 (Réseau) et B16 (SOC).
* **Lien de progression** : Traduit techniquement les processus du SOC présentés en B16. Cette compétence pratique d'analyse de traces est indispensable pour l'investigation et la réponse à incident qui seront étudiées en B18.

---

## 2. Déroulé minuté (90 minutes)

| Minutage | Séquence | Contenu théorique & Activités | Rôle du Mentor | Rôle de l'Apprenant | Méthode pédagogique | Livrable / Jalon |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **00 - 15 min** *(15')* | **Brise-glace & Détective** | *Brise-glace : Le détective de bibliothèque.* Retrouver un "voleur de livre" à l'aide d'un registre papier des entrées/sorties pour illustrer l'utilité des logs d'accès. | Guide la réflexion, valide les devoirs de B16 sur les éléments clés d'un log. | Réfléchit aux informations nécessaires pour prouver la culpabilité du suspect. | Interrogative / Discussion | Jalon : Liste des 3 métadonnées indispensables d'un événement. |
| **15 - 35 min** *(20')* | **Apports Théoriques : SIEM** | *Qu'est-ce qu'un SIEM ?* Collecte (Agents, Syslog), Normalisation (formatage commun), Corrélation (analyse transverse en temps réel) et Visualisation (Dashboards). | Présente le schéma fonctionnel d'un SIEM et des exemples de logiciels (Splunk, Elastic, Wazuh). | Comprend comment le SIEM rassemble des téraoctets de données pour n'en extraire que les alertes clés. | Explicative / Visuelle | - |
| **35 - 50 min** *(15')* | **Apports Théoriques : Corrélation** | *Anatomie des logs et règles de corrélation.* Structure d'un log web Apache et d'un log de pare-feu. Logique d'écriture d'une règle (ex. *Si event_id = 4625 et count > 10 en 30s alors alerte*). | Décortique une ligne de log web en direct au tableau (champs IP, date, méthode, ressource, statut). | Apprend à repérer les informations clés dans une suite de caractères bruts. | Explicative | - |
| **50 - 80 min** *(30')* | **Activité Pratique** | *Activité : Analyse de logs web Apache.* Les apprenants analysent un fichier texte de 20 lignes de logs réelles pour identifier une attaque par injection SQL et un scan de vulnérabilités. | Distribue l'extrait de log d'une boutique en ligne fictive, guide le repérage des caractères spéciaux (`' OR 1=1`, `../`). | Analyse les lignes de logs, identifie l'IP de l'attaquant, l'heure de l'attaque et le type d'exploit tenté. | Active / Expérimentale | **Livrable** : Rapport d'investigation rapide identifiant la compromission et ses paramètres. |
| **80 - 90 min** *(10')* | **Quiz & Devoirs** | *Quiz de session & Devoirs.* Validation des acquis d'analyse technique et transition vers la gestion des incidents. | Lance le quiz de fin de session et présente le travail autonome SkillsBuild. | Répond au quiz de session et prend note des devoirs. | Interrogative | Jalon : Score au quiz individuel. |

---

## 3. Travail en autonomie (Self-paced)
* **Avant la session suivante (B18)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Log Analysis and SIEM Concepts"* (durée estimée : 1h30).
  * **Recherche autonome** : Chercher ce qu'est le "confinement" d'une machine compromise dans un réseau et citer une action technique permettant de l'isoler (ex. déconnexion câble, VLAN d'isolation, règle firewall locale).
