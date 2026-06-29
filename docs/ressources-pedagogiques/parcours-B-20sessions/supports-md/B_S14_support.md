# Session B14 — Gestion des risques

## Objectifs de la session
À la fin de cette session, vous serez capable de :
* Expliquer et articuler les composantes d'un risque cyber : atout (actif), menace, vulnérabilité, impact et probabilité.
* Construire un registre des risques cyber pragmatique et calculer sa criticité à l'aide d'une matrice qualitative 4x4.
* Justifier et choisir une stratégie de traitement du risque adaptée parmi les 4 options fondamentales (réduire, transférer, éviter, accepter).

---

## Concepts clés

### 1. Qu'est-ce qu'un risque cyber ? (L'équation du risque)
En sécurité de l'information, le risque n'est pas un concept abstrait. Il se définit comme la possibilité qu'un événement indésirable survienne et affecte l'activité de l'entreprise. 

Pour caractériser un risque, on décompose l'équation en plusieurs éléments :
*   **L'Atout / Actif (*Asset*)** : Ce qui a de la valeur pour l'entreprise et doit être protégé (ex. les fichiers de brevets, la base de données clients, le serveur de messagerie).
*   **La Menace (*Threat*)** : L'événement redouté d'origine externe ou interne qui pourrait causer un dommage (ex. un ransomware, un employé malveillant, une panne électrique, un incendie).
*   **La Vulnérabilité (*Vulnerability*)** : La faiblesse ou la faille exploitable au sein du système d'information (ex. l'absence de mises à jour système, un personnel non formé au phishing, l'absence de pare-feu local).
*   **L'Impact (*Impact*)** : La conséquence préjudiciable pour l'entreprise si la menace se concrétise (perte financière, amende réglementaire, atteinte à la réputation, arrêt de la production).
*   **La Probabilité / Vraisemblance (*Likelihood*)** : La plausibilité que la menace réussisse à exploiter la vulnérabilité sur une période donnée.

> [!NOTE]
> **Formulation logique** :
> Un risque se formule toujours ainsi : *« La **menace** [ex. un ransomware] pourrait exploiter la **vulnérabilité** [ex. ports RDP ouverts sur Internet] pour atteindre l'**actif** [ex. serveurs de fichiers] et causer un **impact** [ex. arrêt complet de l'activité pendant 5 jours]. »*

### 2. Le Registre des risques et la Matrice de Criticité 4x4
Pour prioriser les chantiers de sécurité, les entreprises listent leurs risques dans un **registre des risques** et évaluent leur **criticité brute** (le risque sans aucune mesure de sécurité).

On évalue qualitativement sur une échelle de 1 à 4 :
*   **Vraisemblance / Probabilité (V)** : 1 (Rare) | 2 (Possible) | 3 (Probable) | 4 (Presque certain).
*   **Gravité / Impact (G)** : 1 (Mineur) | 2 (Modéré) | 3 (Majeur) | 4 (Critique/Catastrophique).
*   **Criticité (C)** = Vraisemblance $\times$ Gravité. Le score varie de 1 à 16.

#### Matrice qualitative de criticité :
*   **1 à 4** : Risque Faible (à surveiller simplement).
*   **5 à 8** : Risque Moyen (mesures de sécurité à planifier).
*   **9 à 16** : Risque Élevé / Critique (mesures d'atténuation immédiates obligatoires).

### 3. Les 4 options de traitement du risque
Une fois les risques identifiés et évalués, l'entreprise doit décider comment y répondre. Elle dispose de 4 stratégies fondamentales :

1.  **Réduire / Atténuer (*Mitigate*)** : C'est la stratégie la plus courante. Elle consiste à mettre en place des mesures de sécurité pour réduire la probabilité ou l'impact du risque (ex. installer un antivirus pour réduire la probabilité d'infection, ou faire des sauvegardes pour réduire l'impact d'un ransomware).
2.  **Transférer (*Transfer*)** : Transférer la responsabilité financière ou opérationnelle à un tiers.
    *   *Exemples* : Souscrire à une **cyber-assurance** (transfert financier) ou confier l'hébergement de ses données à un hébergeur cloud hautement sécurisé et certifié (transfert opérationnel).
3.  **Éviter (*Avoid*)** : Renoncer à l'activité ou à la technologie à l'origine du risque.
    *   *Exemple* : Interdire l'utilisation d'une application mobile tierce de partage de fichiers non sécurisée pour les documents internes confidentiels.
4.  **Accepter (*Accept*)** : Décider sciemment d'assumer le risque sans mettre en place de mesures supplémentaires, généralement parce que le coût des mesures de protection dépasse la valeur de ce qu'on protège. **L'acceptation d'un risque doit être formalisée par écrit et signée par la Direction Générale**.

---

## Activités / exercices

### Exercice 1 — Élaboration d'une ligne de registre des risques pour l'entreprise "EcoLog"
**Objectif :** Rédiger et coter un risque cyber concret de l'identification initiale (Brute) à la mise en place de mesures correctives (Résiduelle).

**Consignes :**
L'entreprise EcoLog s'inquiète du phénomène de **Shadow IT** (utilisation d'outils numériques par les salariés sans l'accord de la DSI). Plus précisément, les équipes marketing utilisent des services d'IA générative en ligne publics et gratuits pour relire et améliorer les contrats des partenaires commerciaux ainsi que des données clients nominatives.

Rédigez la ligne de registre pour ce risque en suivant les consignes de cotation et de traitement ci-dessous.

**Données d'évaluation à appliquer :**
*   *Cotation Brute* : Sans aucun contrôle, l'utilisation est quotidienne (Vraisemblance = 4) et la fuite de secrets commerciaux ou de données RGPD causerait de lourdes amendes et un préjudice commercial fort (Gravité = 3).
*   *Mesure d'atténuation proposée* : Rédiger une charte d'utilisation de l'IA, bloquer l'accès aux IA publiques non sécurisées au niveau du pare-feu d'entreprise, et mettre à disposition des salariés un outil d'IA interne sécurisé qui ne réutilise pas les données pour son entraînement.
*   *Cotation Résiduelle (après mesure)* : La probabilité de fuite devient rare car les sites externes sont bloqués et une alternative sécurisée existe (Vraisemblance résiduelle = 1), mais l'impact légal d'une fuite resterait identique (Gravité résiduelle = 3).

**Tableau à remplir :**
| Composante du Risque | Descriptif technique / Valeurs |
|---|---|
| **Actif menacé** | ... |
| **Description du Risque** | *La menace exploite la vulnérabilité sur l'actif...* |
| **Impact business potentiel** | ... |
| **Cotation Brute** | Vraisemblance (1-4) = ... \| Gravité (1-4) = ... \| **Criticité Brute = ...** |
| **Stratégie de traitement** | **[Réduire / Transférer / Éviter / Accepter]** + Mesure concrète : ... |
| **Cotation Résiduelle** | Vraisemblance (1-4) = ... \| Gravité (1-4) = ... \| **Criticité Résiduelle = ...** |

**Corrigé / Éléments de réponse :**

| Composante du Risque | Descriptif technique / Valeurs |
|---|---|
| **Actif menacé** | Données de contrats commerciaux et données nominatives de clients. |
| **Description du Risque** | Des salariés du marketing (menace) soumettent des contrats et des données nominatives (actifs) à des outils d'IA publics non validés par la DSI (vulnérabilité), provoquant la fuite ou la réutilisation non contrôlée de données d'entreprise. |
| **Impact business potentiel** | Fuite de secrets industriels vers le domaine public, violation de la confidentialité des données clients entraînant des sanctions financières de la CNIL et rupture de confiance des clients. |
| **Cotation Brute** | Vraisemblance (1-4) = **4** \| Gravité (1-4) = **3** \| **Criticité Brute = 12 / 16 (Risque Critique)** |
| **Stratégie de traitement** | **Réduire / Atténuer** : Blocage technique des URL d'IA non sécurisées sur le pare-feu, formation de sensibilisation des employés et mise à disposition d'une plateforme d'IA souveraine privée. |
| **Cotation Résiduelle** | Vraisemblance (1-4) = **1** \| Gravité (1-4) = **3** \| **Criticité Résiduelle = 3 / 16 (Risque Faible / Acceptable)** |

---

## Questions de réflexion
1. Quelle est la différence entre le risque *Brut* et le risque *Résiduel* ? Pourquoi un risque résiduel n'est-il presque jamais égal à zéro ?
2. Une entreprise décide d'acheter une cyber-assurance pour couvrir les pertes financières en cas de rançongiciel. A-t-elle éliminé son risque ? Quelle composante du risque (vraisemblance ou gravité de l'impact) l'assurance permet-elle de transférer ?

---

## Résumé / points à retenir
*   Un **risque cyber** naît de la rencontre d'une menace et d'une vulnérabilité sur un actif de valeur pour l'entreprise.
*   L'évaluation du risque croise sa **vraisemblance** (probabilité d'occurrence) et sa **gravité** (impact financier, juridique ou d'image).
*   La **criticité brute** priorise les risques, tandis que la **criticité résiduelle** mesure le risque subsistant après l'application des contrôles de sécurité.
*   Il existe 4 réponses stratégiques au risque : **Réduire** (sécuriser), **Transférer** (assurance), **Éviter** (renoncer), ou **Accepter** (décision de direction).

---

## Glossaire de la session
*   **Actif (Asset)** — Tout élément physique, virtuel ou humain ayant de la valeur pour la réalisation de la mission de l'entreprise.
*   **Vulnérabilité** — Faille ou faiblesse logique, physique ou organisationnelle permettant à un attaquant de compromettre un système.
*   **Shadow IT** — Utilisation de systèmes, logiciels ou services informatiques par des employés sans l'autorisation ou le contrôle formel de la DSI.
*   **Risque Résiduel** — Niveau de risque subsistant après la mise en œuvre des mesures de traitement et des contrôles de sécurité.

---

## Pour aller plus loin (self-paced)
*   **Sur IBM SkillsBuild** : Suivre le cours *"Cybersecurity Governance and Risk Management - Part 2"* (durée estimée : 1h30).
*   **Recherche de méthodologie** : Rechercher les grandes lignes de la méthode d'analyse de risques française **EBIOS RM** (développée par l'ANSSI) pour comprendre comment l'État et les grandes organisations modélisent les scénarios de cyberattaques.
