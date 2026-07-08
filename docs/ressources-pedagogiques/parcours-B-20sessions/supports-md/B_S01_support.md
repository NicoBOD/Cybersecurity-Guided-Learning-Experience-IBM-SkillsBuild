# Session B01 — Introduction à la cybersécurité & triade CIA

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - La Triade CIA (ou CID) : Le socle de la sécurité
    - Les impacts business d'une cyberattaque
    - Les métiers de la cybersécurité
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   La **triade CIA (Confidentialité, Intégrité, Disponibilité)** structure toute analyse de sécurité informatique.
*   Chaque pilier répond à une question clé : Qui peut lire la donnée ? (Confidentialité), Qui peut la modifier ? (Intégrité), La donnée est-elle accessible quand on en a besoin ? (Disponibilité).
*   Une cyberattaque réussie entraîne des coûts financiers de restauration, mais aussi des sanctions juridiques (RGPD) et une perte de confiance des clients.
*   La sécurité est un travail d'équipe associant la défense (Blue Team), les tests de résistance (Red Team) et le pilotage managérial (RSSI).

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Évolution historique du paysage des menaces**
Prenez le temps d'expliquer comment nous sommes passés de virus informatiques créés par des passionnés (années 90) cherchant la notoriété, à une véritable industrie du cybercrime (Ransomware-as-a-Service, courtiers en accès initiaux). Détaillez la notion d'économie souterraine : les attaquants achètent des vulnérabilités sur le Dark Web comme on achète un service légal.

**2. La Triade CIA dans le détail**
- **Confidentialité** : Évoquez l'importance des contrôles d'accès physiques (badges) et logiques (chiffrement AES-256).
- **Intégrité** : Expliquez comment le hachage (SHA-256) permet de garantir qu'une donnée n'a pas été altérée par un "Man-in-the-Middle".
- **Disponibilité** : Abordez les plans de reprise d'activité (PRA), le rôle des clusters de serveurs, et l'impact d'une attaque DDoS sur les serveurs DNS.

**3. Discussion ouverte (15 minutes)**
Demandez aux apprenants d'identifier l'actif le plus critique de leur entreprise actuelle ou passée, et de classer les risques (Perte de CA vs Perte de réputation).


*(Même que A_S01)* Ce cours nécessite de s'attarder sur les exemples historiques (Stuxnet, WannaCry) pour démontrer la bascule entre le piratage d'amateur et la cyberguerre. Détaillez également la différence entre les objectifs de la cybersécurité (protéger le système) et la sécurité de l'information (protéger la donnée quel que soit le support).

---

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Définir les trois piliers de la triade CIA (Confidentialité, Intégrité, Disponibilité) et illustrer chaque pilier par des exemples d'incidents réels.
* Identifier et expliquer les impacts directs et indirects (financiers, juridiques, réputationnels) d'une cyberattaque sur la viabilité d'une entreprise.
* Cartographier les principaux métiers de la cybersécurité en distinguant les postures de défense (*Blue Teaming*) et de test d'intrusion (*Red Teaming*).

---

### Glossaire

*   **AES-256** — Standard de chiffrement symétrique hautement sécurisé utilisant des clés de 256 bits, considéré comme inviolable par la force brute actuelle.
*   **Blue Team** — Équipe interne chargée de surveiller les réseaux et de repousser les attaques au quotidien.
*   **CIA Triad (Triade CIA)** — Modèle de sécurité basé sur la Confidentialité, l'Intégrité et la Disponibilité.
*   **DDoS (Distributed Denial of Service)** — Attaque par déni de service distribué visant à rendre un serveur ou un réseau indisponible en le submergeant de requêtes provenant de multiples sources.
*   **DDoS (Déni de service distribué)** — Attaque visant à rendre un service indisponible en le submergeant de requêtes réseau depuis de nombreuses sources.
*   **RaaS (Ransomware-as-a-Service)** — Modèle économique cybercriminel où des développeurs vendent ou louent des rançongiciels à des affiliés qui exécutent les attaques.
*   **Ransomware (Rançongiciel)** — Logiciel malveillant qui chiffre les données d'une victime et demande une rançon pour les déchiffrer.
*   **Red Team** — Groupe d'experts simulant des attaques physiques ou informatiques pour évaluer les défenses d'une organisation.
*   **SHA-256** — Algorithme de hachage cryptographique produisant une empreinte numérique unique de 256 bits pour vérifier l'intégrité d'une donnée.

---

### Concepts clés

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

### 1. La Triade CIA (ou CID) : Le socle de la sécurité
La triade **CIA** (pour *Confidentiality, Integrity, Availability* — ou **CID** en français pour Confidentialité, Intégrité, Disponibilité) est le modèle conceptuel de base à partir duquel toute politique de sécurité est construite. Elle permet de qualifier précisément le besoin de protection d'un système ou d'une information.

*   **Confidentialité (*Confidentiality*)** : Garantir que l'information n'est accessible qu'aux personnes autorisées.
    *   *Analogie* : Une lettre scellée dans une enveloppe de cire. Seul le destinataire légitime brise le sceau pour la lire.
    *   *Exemple d'incident* : La fuite et la revente sur le darknet d'une base de données contenant les dossiers médicaux de millions de patients.
*   **Intégrité (*Integrity*)** : Garantir que les données ne sont pas modifiées de manière accidentelle ou malveillante et restent exactes et complètes.
    *   *Analogie* : Un grand livre comptable écrit à l'encre indélébile. Toute rature ou page arrachée se verrait immédiatement.
    *   *Exemple d'incident* : Un attaquant qui modifie discrètement les coordonnées bancaires (IBAN) dans le système de facturation d'un fournisseur pour détourner les virements vers son propre compte.
*   **Disponibilité (*Availability*)** : Garantir que les systèmes informatiques et les données sont accessibles par les utilisateurs autorisés au moment où ils en ont besoin.
    *   *Analogie* : L'électricité domestique. Lorsque vous appuyez sur l'interrupteur, la lumière doit s'allumer instantanément.
    *   *Exemple d'incident* : Une attaque par déni de service distribué (DDoS — *Distributed Denial of Service*) qui sature de requêtes le site web d'une banque, empêchant les clients d'accéder à leurs comptes pendant plusieurs heures.

> 💡 **Bon à savoir : La règle du maillon le plus faible**
> Une sécurité à 100 % n'existe pas. Les attaquants ne cherchent pas à forcer la porte blindée la plus solide d'un système, mais à trouver la faille la plus simple (un mot de passe par défaut, un logiciel non mis à jour ou une erreur humaine). La force globale d'un système de sécurité est égale à celle de son composant le plus faible.

### 2. Les impacts business d'une cyberattaque
Une cyberattaque n'est pas seulement un problème technique pour le département informatique ; c'est un risque majeur pour l'existence même de l'entreprise (*business*). Ses conséquences se classent en trois grandes catégories :

*   **Impact financier direct** : Perte immédiate liée à l'arrêt d'une usine ou d'un site de vente en ligne (perte d'exploitation), coûts de remédiation (frais des experts techniques appelés en urgence pour nettoyer le réseau) et rançons éventuelles (bien qu'il soit fortement déconseillé de payer).
*   **Impact juridique et réglementaire** : Amendes administratives lourdes en cas de non-respect du RGPD (*General Data Protection Regulation*) si des données personnelles ont été volées faute de sécurité suffisante. À cela s'ajoutent les frais de litiges et de procès intentés par les clients ou les partenaires lésés.
*   **Impact réputationnel** : C'est souvent l'impact le plus difficile à chiffrer mais le plus destructeur à long terme. La perte de confiance des clients et des investisseurs peut conduire à une baisse brutale des ventes et à la résiliation de contrats clés.

### 3. Les métiers de la cybersécurité
Le secteur de la cybersécurité regroupe des profils variés qui collaborent pour protéger les organisations. On divise traditionnellement ces rôles en deux postures :

*   **La Red Team (Posture offensive)** : Experts en cybersécurité chargés de tester la résistance de l'entreprise en simulant des attaques réelles (tests d'intrusion ou *pentesting*). Leur but est d'identifier les failles avant que de vrais criminels ne le fassent.
*   **La Blue Team (Posture défensive)** : Ingénieurs et analystes chargés de construire les défenses au quotidien, de surveiller les réseaux (analystes SOC — *Security Operations Center*) et de réagir en cas d'attaque avérée (répondeurs d'incident).
*   **Le RSSI (*CISO — Chief Information Security Officer*)** : Le rôle de direction qui orchestre la stratégie de sécurité globale, gère les budgets et fait le lien entre la technique et la direction de l'entreprise.

---

### Activités / exercices
### Exercice 1 — Qualification d'incidents (Matrice CIA)
**Objectif :** Analyser des scénarios réels d'incidents informatiques et identifier le ou les piliers de la triade CIA qui ont été directement violés.

**Consignes :**

1. Lisez attentivement chacun des trois scénarios ci-dessous.
2. Pour chaque scénario, déterminez quel pilier de la triade CIA a été compromis en premier et pourquoi.
3. Proposez une mesure simple de bon sens pour éviter que cet incident ne se reproduise.

*   **Scénario A** : Un hôpital subit une attaque par rançongiciel (*ransomware*). Les écrans des ordinateurs de l'accueil affichent un message demandant une rançon, et l'ensemble des dossiers médicaux des patients est chiffré et inaccessible.
*   **Scénario B** : Un étudiant curieux réussit à accéder à la base de données des notes de son université. Il modifie sa note de cybersécurité en la passant de 08/20 à 18/20 avant la publication officielle des résultats.
*   **Scénario C** : Une entreprise de commerce électronique laisse par erreur un fichier de sauvegarde contenant les adresses email, les mots de passe hachés et les adresses postales de ses clients en accès libre sur un serveur web non protégé. Le fichier est téléchargé et publié sur un forum public.

**Corrigé / Éléments de réponse :**

*   **Scénario A** :
    *   *Pilier violé* : La **Disponibilité**. Les dossiers médicaux sont chiffrés et donc inaccessibles pour les médecins (ce qui peut mettre des vies en danger). *Note* : La confidentialité peut également être menacée si le groupe d'attaquants a volé les données avant de les chiffrer.
    *   *Mesure préventive* : Mettre en place des sauvegardes régulières hors ligne (déconnectées du réseau) pour pouvoir restaurer les données sans payer la rançon.
*   **Scénario B** :
    *   *Pilier violé* : L'**Intégrité**. La donnée (la note) a été altérée sans autorisation, faussant l'exactitude du relevé.
    *   *Mesure préventive* : Restreindre l'accès en écriture à la base de données des notes au seul personnel administratif autorisé et activer des journaux de logs (*audit trails*) pour suivre toute modification.
*   **Scénario C** :
    *   *Pilier violé* : La **Confidentialité**. Des données sensibles réservées à l'usage de l'entreprise ont été divulguées à des tiers non autorisés.
    *   *Mesure préventive* : Appliquer le principe du moindre privilège sur le serveur de stockage et réaliser des audits réguliers des fichiers partagés publiquement.

---

### Questions de réflexion
1. Si un site de e-commerce subit une interruption de service (indisponibilité) d'une heure lors du Black Friday, quel pilier est touché et quelles sont les conséquences financières et de réputation potentielles ?
2. Pourquoi dit-on souvent que la confidentialité et la disponibilité peuvent parfois s'opposer ? (Indice : Pensez aux mécanismes de contrôle d'accès stricts qui ralentissent l'accès rapide aux données).

**Corrigé / Éléments de réponse :**
1. La Disponibilité est touchée. Les conséquences incluent une perte financière directe énorme (ventes manquées) et un impact réputationnel important.
2. La confidentialité impose des contrôles (mots de passe, chiffrements) qui peuvent ralentir ou compliquer l'accès rapide et fluide (disponibilité) aux données.

---


### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Pour bien comprendre la cybersécurité, imaginez l'analogie d'un **château fort médiéval** :
    - **Les Douves et le Pont-levis** agissent comme le pare-feu : ils filtrent les accès et n'autorisent le passage que par une seule entrée surveillée.
    - **Les Gardes à l'intérieur de la cour** sont l'Antivirus/EDR : s'il y a un intrus ou une bagarre dans la cour, ils interviennent immédiatement.
    - **La Salle du trésor (donjon)** représente les données sensibles. Elle nécessite plusieurs clés et l'accord de plusieurs officiers (Authentification Multifacteur - MFA).
    - **Les Espions et éclaireurs** représentent la sécurité offensive : ils étudient les faiblesses des murs du château pour les réparer avant qu'une armée ennemie ne les attaque.

**Exemple d'application professionnelle :**
Dans un cabinet de conseil financier, un consultant perd son ordinateur portable dans le train. Grâce à la *défense en profondeur*, le disque dur de la machine est chiffré en AES-256 (Confidentialité préservée), les comptes d'accès sont désactivés à distance (Disponibilité contrôlée), et aucun attaquant ne peut usurper son identité car le MFA est requis pour se connecter au réseau de l'entreprise. Chaque couche de sécurité a joué son rôle pour éviter la catastrophe.


### Panorama des solutions du marché (Commerciales & Open-Source)

Pour mettre en œuvre une stratégie globale de défense en profondeur et anticiper les menaces actuelles, plusieurs solutions coexistent sur le marché :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Microsoft Defender for Endpoint (et Suite Defender/Entra)** : Leader du Magic Quadrant de Gartner pour la protection des endpoints (EPP/EDR) et des identités, particulièrement intégré pour les environnements Windows.
    *   **CrowdStrike Falcon** : Référence du marché des EDR/XDR cloud-natifs, reconnu pour ses capacités de détection des menaces avancées et sa Threat Intelligence intégrée.
    *   **SentinelOne Singularity** : Solution EDR/XDR utilisant l'intelligence artificielle comportementale sur l'agent pour bloquer et restaurer les systèmes en cas d'attaque par ransomware.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **Wazuh** : Plateforme open-source complète d'XDR et de supervision de sécurité. Elle assure la détection des intrusions, la surveillance de l'intégrité des fichiers, l'évaluation de la configuration et la réponse active.
    *   **ClamAV** : Moteur antivirus open-source standard, principalement utilisé sur les serveurs de fichiers et serveurs de messagerie Linux pour détecter les malwares.
    *   **Greenbone Community Edition (OpenVAS)** : Scanner de vulnérabilités open-source réputé pour identifier les failles de sécurité actives sur un réseau d'entreprise.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Cybersecurity Fundamentals - Part 1"* (~1h30).
*   **Ressource complémentaire** : Consulter la section "Actualités" du site cyber.gouv.fr (ANSSI) pour observer des exemples d'incidents cyber récents en France.


---

* [ANSSI - Introduction à la cybersécurité](https://cyber.gouv.fr/)
* [CNIL - Sécurité des données](https://www.cnil.fr)

## 4. Exercice bonus

- **Objectif :** Analyse d'impact sur cas réel.
- **Consignes :**
    1. Étudiez le cas d'une attaque par Ransomware ayant ciblé un hôpital régional fictif.
    2. Identifiez l'impact précis de cette attaque sur chacun des trois piliers de la Triade CIA.
    3. Proposez une mesure d'urgence pour restaurer la "Disponibilité" et une mesure préventive pour éviter que la "Confidentialité" ne soit compromise à l'avenir.
- **Correction pour le mentor :** Le mentor validera que les apprenants ont bien identifié que le chiffrement des données de santé bloque la *Disponibilité*, que la fuite potentielle de dossiers médicaux affecte la *Confidentialité*, et que la modification sauvage de fiches d'administration de médicaments menace l'*Intégrité*. La restauration depuis des sauvegardes hors-ligne sécurisées est la réponse pour la disponibilité, tandis que le chiffrement des bases de données et la restriction des droits d'accès protègent la confidentialité.

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **AES-256** | Standard de chiffrement symétrique hautement sécurisé utilisant des clés de 256 bits, considéré comme inviolable par la force brute actuelle. |
| **Blue Team** | Équipe interne chargée de surveiller les réseaux et de repousser les attaques au quotidien. |
| **CIA Triad (Triade CIA)** | Modèle de sécurité basé sur la Confidentialité, l'Intégrité et la Disponibilité. |
| **DDoS (Déni de service distribué)** | Attaque visant à rendre un service indisponible en le submergeant de requêtes réseau depuis de nombreuses sources. |
| **RaaS (Ransomware-as-a-Service)** | Modèle économique cybercriminel où des développeurs vendent ou louent des rançongiciels à des affiliés qui exécutent les attaques. |
| **Ransomware (Rançongiciel)** | Logiciel malveillant qui chiffre les données d'une victime et demande une rançon pour les déchiffrer. |
| **Red Team** | Groupe d'experts simulant des attaques physiques ou informatiques pour évaluer les défenses d'une organisation. |
| **SHA-256** | Algorithme de hachage cryptographique produisant une empreinte numérique unique de 256 bits pour vérifier l'intégrité d'une donnée. |

