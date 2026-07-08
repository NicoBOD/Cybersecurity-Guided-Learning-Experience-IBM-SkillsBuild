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

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Définir les trois piliers de la triade CIA (Confidentialité, Intégrité, Disponibilité) et illustrer chaque pilier par des exemples d'incidents réels.
* Identifier et expliquer les impacts directs et indirects (financiers, juridiques, réputationnels) d'une cyberattaque sur la viabilité d'une entreprise.
* Cartographier les principaux métiers de la cybersécurité en distinguant les postures de défense (*Blue Teaming*) et de test d'intrusion (*Red Teaming*).

---

### Glossaire
*   **CIA Triad (Triade CIA)** — Modèle de sécurité basé sur la Confidentialité, l'Intégrité et la Disponibilité.
*   **Ransomware (Rançongiciel)** — Logiciel malveillant qui chiffre les données d'une victime et demande une rançon pour les déchiffrer.
*   **DDoS (Déni de service distribué)** — Attaque visant à rendre un service indisponible en le submergeant de requêtes réseau depuis de nombreuses sources.
*   **Red Team** — Groupe d'experts simulant des attaques physiques ou informatiques pour évaluer les défenses d'une organisation.
*   **Blue Team** — Équipe interne chargée de surveiller les réseaux et de repousser les attaques au quotidien.

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

## 3. Ressources Complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Cybersecurity Fundamentals - Part 1"* (~1h30).
*   **Ressource complémentaire** : Consulter la section "Actualités" du site cyber.gouv.fr (ANSSI) pour observer des exemples d'incidents cyber récents en France.

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
| **CIA Triad (Triade CIA)** | Modèle de sécurité basé sur la Confidentialité, l'Intégrité et la Disponibilité. |
| **Ransomware (Rançongiciel)** | Logiciel malveillant qui chiffre les données d'une victime et demande une rançon pour les déchiffrer. |
| **DDoS (Déni de service distribué)** | Attaque visant à rendre un service indisponible en le submergeant de requêtes réseau depuis de nombreuses sources. |
| **Red Team** | Groupe d'experts simulant des attaques physiques ou informatiques pour évaluer les défenses d'une organisation. |
| **Blue Team** | Équipe interne chargée de surveiller les réseaux et de repousser les attaques au quotidien. |
