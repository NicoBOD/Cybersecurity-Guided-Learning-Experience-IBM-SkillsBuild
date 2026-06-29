# Guide des Mini-projets intermédiaires — Parcours B
Parcours : B 20 sessions  |  Module : Projets d'application pratiques  |  Format : Énoncés et consignes

Les mini-projets sont des travaux pratiques réalisés en équipe tout au long de la formation. Ils permettent d'appliquer les connaissances théoriques acquises à la fin de chaque module thématique et servent de jalons pour la construction du livrable final (le Projet Capstone).

---

## Sommaire des mini-projets
1.  **Mini-projet 1** (Session B08) : Conception d'une architecture réseau segmentée et sécurisée.
2.  **Mini-projet 2** (Session B12) : Conception d'un plan de protection des données (M365, BitLocker, Sauvegardes).
3.  **Mini-projet 3** (Session B15) : Analyse de risques simplifiée & Rédaction d'une ébauche de PSSI.
4.  **Mini-projet 4** (Session B17) : Analyse de logs et détection d'une attaque web.

---

## Mini-projet 1 — Conception d'une architecture réseau sécurisée
*   **Jalon** : Fin du Module B (Systèmes & réseaux — Session B08)
*   **Objectifs pédagogiques** :
    *   Concevoir un schéma de réseau cloisonné et sécurisé pour une PME.
    *   Définir les flux autorisés et interdits entre différentes zones réseau à l'aide d'un pare-feu.
    *   Proposer une solution d'accès distant sécurisé pour les utilisateurs nomades (VPN).

### Énoncé & Consignes :
À partir du contexte de la PME **MedDistri**, proposez une nouvelle architecture réseau sous forme de schéma conceptuel (Mermaid ou outil de dessin) résolvant le problème de réseau local plat.
Votre proposition doit cloisonner :

1.  Le réseau interne administratif et comptable (LAN Administratif).
2.  Le réseau de l'entrepôt et des logisticiens (LAN Logistique).
3.  Un réseau d'accueil pour les smartphones des clients ou visiteurs (LAN Visiteurs).
4.  Une zone démilitarisée (DMZ) contenant les serveurs de fichiers accessibles depuis l'extérieur.

### Livrables attendus :
1.  **Le Schéma Réseau Cible** : Une modélisation claire montrant l'emplacement du pare-feu, des commutateurs (switches), des bornes Wi-Fi, des serveurs et des postes clients de chaque zone.
2.  **La Table de Filtrage Pare-feu (Matrice des flux)** : Un tableau spécifiant : Source, Destination, Protocole, Port, Action (Autoriser/Bloquer) et la justification métier de chaque règle.
3.  **Une note technique (1 page)** décrivant la technologie VPN recommandée pour les 15 commerciaux nomades et le protocole de chiffrement associé.

---

## Mini-projet 2 — Plan de protection des données
*   **Jalon** : Fin du Module C (Identités, cloud & données — Session B12)
*   **Objectifs pédagogiques** :
    *   Identifier et classifier les données sensibles d'une organisation.
    *   Concevoir une politique de protection des terminaux mobiles et des données locales.
    *   Structurer une politique de sauvegarde conforme à la règle 3-2-1.

### Énoncé & Consignes :
Concevez le plan de protection des données de MedDistri. Vous devez identifier les différents types de données de l'entreprise (données clients, brevets, RH, facturation), leur attribuer un niveau de sensibilité et proposer des solutions pratiques de sécurisation pour les données stockées localement et sur le Cloud Microsoft 365.

### Livrables attendus :
1.  **La Table de Classification des Données** : Classification en 3 niveaux (Publique, Interne, Confidentielle) avec les règles de stockage et d'accès correspondantes.
2.  **Plan de durcissement des identités (Microsoft 365)** : Description des règles de complexité des mots de passe et du protocole MFA à déployer pour les commerciaux.
3.  **Plan de durcissement des terminaux (Postes nomades)** : Recommandations pour le chiffrement des disques durs (ex. BitLocker) et la gestion des privilèges (limitation du compte administrateur local).
4.  **Schéma de sauvegarde 3-2-1** : Modélisation indiquant précisément les 3 copies, les 2 supports différents et la copie externe (hors ligne/immuable).

---

## Mini-projet 3 — Évaluation des risques & Ébauche de PSSI
*   **Jalon** : Fin du Module D (Gouvernance, risques & conformité — Session B15)
*   **Objectifs pédagogiques** :
    *   Identifier, évaluer et coter des risques cyber à l'aide d'une matrice qualitative.
    *   Rédiger des règles de sécurité claires et contraignantes sous forme de PSSI.
    *   Prendre en compte les contraintes réglementaires (RGPD) et métiers de l'organisation.

### Énoncé & Consignes :
Réalisez une analyse de risques simplifiée pour MedDistri en sélectionnant 3 scénarios de menaces critiques (ex. Ransomware chiffrant les données de santé, Vol d'un ordinateur de commercial, Usurpation d'identité d'un dirigeant pour fraude au virement). Estimez la vraisemblance ($V$) et l'impact ($I$) sur une échelle de 1 à 4 pour calculer la criticité brute ($C$). Rédigez ensuite une charte de sécurité (PSSI) de 5 règles clés pour les salariés de l'entreprise.

### Livrables attendus :
1.  **La Matrice de Cotation des Risques (Tableau)** : Description du scénario (Menace + Vulnérabilité), Cotation Brute ($V \times I$), Mesures de traitement proposées, et Cotation Résiduelle estimée.
2.  **L'Ébauche de la PSSI (5 Règles d'Or)** : Rédigez 5 directives de sécurité rédigées de manière impérative (ex. *"Tout utilisateur doit..."*) couvrant l'usage des mots de passe, le télétravail, la gestion des emails suspects, la sécurité physique des bureaux, et le signalement des anomalies au technicien.
3.  **Note de conformité RGPD** : Liste des 3 actions d'urgence à mener pour que le fichier clients contenant des historiques de commandes de matériel médical respecte le RGPD.

---

## Mini-projet 4 — Analyse de logs et détection d'une attaque web
*   **Jalon** : Module E (Opérations, détection & réponse — Session B17)
*   **Objectifs pédagogiques** :
    *   Lire et interpréter les champs d'un fichier de logs serveur (Timestamp, IP, Requête HTTP, Code Statut, User-Agent).
    *   Reconnaître les signatures typiques d'une attaque web (Injection SQL, Traversée de répertoires).
    *   Proposer des contre-mesures techniques immédiates pour bloquer l'attaquant.

### Énoncé & Consignes :
Le serveur de commandes en ligne de MedDistri a subi des requêtes suspectes. En tant qu'analyste SOC, on vous transmet un extrait de 10 lignes du fichier de logs Apache (`access.log`). Vous devez analyser ce fichier pour identifier la nature de l'attaque, isoler l'adresse IP de la machine attaquante et formuler des recommandations techniques d'urgence pour le pare-feu et le site web.

### Livrables attendus :
1.  **Rapport d'Analyse d'Incident (1 page)** :
    *   *Chronologie* : Horodatage précis du début et de la fin de l'attaque suspectée.
    *   *Identification de la menace* : Identification de l'adresse IP attaquante, de la faille ciblée et du succès ou de l'échec de la tentative (justifié par les codes de statut HTTP).
    *   *Signature technique* : Extraction de la ligne de log exacte montrant l'injection de code malveillant.
2.  **Plan de blocage immédiat** : Règle de pare-feu d'urgence à appliquer pour bannir l'attaquant et mesures correctives à court terme sur le code de l'application web.
