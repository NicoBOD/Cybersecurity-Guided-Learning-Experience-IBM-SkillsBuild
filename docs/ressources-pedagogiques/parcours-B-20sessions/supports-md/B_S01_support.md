# Session B01 — Introduction à la cybersécurité & triade CIA
Parcours : B 20 sessions  |  Module : A — Fondations  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - La Triade CIA (ou CID) : Le socle de la sécurité
    - Les impacts business d'une cyberattaque
    - Les métiers de la cybersécurité
    - La menace en chiffres et deux cas réels français : l'hôpital de Corbeil-Essonnes et France Travail
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   La **triade CIA (Confidentialité, Intégrité, Disponibilité)** structure toute analyse de sécurité informatique.
*   Chaque pilier répond à une question clé : Qui peut lire la donnée ? (Confidentialité), Qui peut la modifier ? (Intégrité), La donnée est-elle accessible quand on en a besoin ? (Disponibilité).
*   Une cyberattaque réussie entraîne des coûts financiers de restauration, mais aussi des sanctions juridiques (RGPD) et une perte de confiance des clients — deux affaires françaises récentes le démontreront.
*   La sécurité est un travail d'équipe associant la défense (Blue Team), les tests de résistance (Red Team) et le pilotage managérial (RSSI) — un secteur qui recrute massivement.

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Définir les trois piliers de la triade CIA (Confidentialité, Intégrité, Disponibilité) et illustrer chaque pilier par des exemples d'incidents réels.
* Identifier et expliquer les impacts directs et indirects (financiers, juridiques, réputationnels) d'une cyberattaque sur la viabilité d'une entreprise.
* Cartographier les principaux métiers de la cybersécurité en distinguant les postures de défense (*Blue Teaming*) et de test d'intrusion (*Red Teaming*).

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** À votre avis, dans quelle proportion des violations de données le facteur humain (erreur, manipulation, mot de passe volé) est-il impliqué ?

    - A) Environ 10 %
    - B) Environ 30 %
    - C) Environ 60 % ✅
    - D) Environ 90 %

    **Débrief mentor :** Environ 60 %, selon le *Data Breach Investigations Report* 2025 de Verizon. Message fondateur du parcours : la cybersécurité n'est pas qu'une affaire de machines — c'est une affaire de personnes. Et c'est une excellente nouvelle pour vous : en suivant ces 20 sessions, vous devenez une ligne de défense... et peut-être un futur professionnel du secteur.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Évolution historique du paysage des menaces**
Prenez le temps d'expliquer comment nous sommes passés de virus informatiques créés par des passionnés (années 90) cherchant la notoriété, à une véritable industrie du cybercrime (Ransomware-as-a-Service, courtiers en accès initiaux). Détaillez la notion d'économie souterraine : les attaquants achètent des vulnérabilités sur le Dark Web comme on achète un service légal. Les exemples historiques (Stuxnet pour le sabotage étatique, WannaCry pour la propagation mondiale) démontrent la bascule entre le piratage d'amateur et la cyberguerre — ils seront approfondis en B02 (acteurs) et B03 (attaques).

**2. La Triade CIA dans le détail**
- **Confidentialité** : Évoquez l'importance des contrôles d'accès physiques (badges) et logiques (chiffrement AES-256).
- **Intégrité** : Expliquez comment le hachage (SHA-256) permet de garantir qu'une donnée n'a pas été altérée par un "Man-in-the-Middle".
- **Disponibilité** : Abordez les plans de reprise d'activité (PRA), le rôle des clusters de serveurs, et l'impact d'une attaque DDoS sur les serveurs DNS.
- Précisez également la différence entre les objectifs de la cybersécurité (protéger le système) et la sécurité de l'information (protéger la donnée quel que soit le support, y compris papier).

**3. Discussion via le chat (à doser selon le temps)**
Demandez aux apprenants d'identifier l'actif le plus critique de leur entreprise actuelle ou passée, et de classer les impacts redoutés (perte de chiffre d'affaires vs perte de réputation). En grand groupe, faites-le via le chat et lisez 3 à 4 réponses à voix haute.

---

### Glossaire

*   **AES-256** — Standard de chiffrement symétrique hautement sécurisé utilisant des clés de 256 bits, considéré comme inviolable par la force brute actuelle.
*   **Blue Team** — Équipe interne chargée de surveiller les réseaux et de repousser les attaques au quotidien.
*   **DDoS (Déni de service distribué)** — Attaque visant à rendre un service indisponible en le submergeant de requêtes réseau provenant de nombreuses sources.
*   **RaaS (Ransomware-as-a-Service)** — Modèle économique cybercriminel où des développeurs vendent ou louent des rançongiciels à des affiliés qui exécutent les attaques.
*   **Ransomware (Rançongiciel)** — Logiciel malveillant qui chiffre les données d'une victime et demande une rançon pour les déchiffrer, souvent doublé d'une menace de publication des données volées (double extorsion).
*   **Red Team** — Groupe d'experts simulant des attaques physiques ou informatiques pour évaluer les défenses d'une organisation, dans un cadre légal et contractuel.
*   **RSSI (CISO)** — Responsable de la Sécurité des Systèmes d'Information : pilote la stratégie, les budgets et le dialogue entre la technique et la direction.
*   **SHA-256** — Algorithme de hachage cryptographique produisant une empreinte numérique unique de 256 bits pour vérifier l'intégrité d'une donnée.
*   **Triade CIA (ou CID)** — Modèle de sécurité fondé sur la Confidentialité, l'Intégrité et la Disponibilité ; l'acronyme CIA vient de l'anglais *Confidentiality, Integrity, Availability*.

---

### Concepts clés

!!! info "À retenir"
    Face à n'importe quel incident, le réflexe professionnel n°1 : **quel pilier de la triade est touché ?** C'est la grille d'analyse que vous utiliserez pendant les 20 sessions de ce parcours — et toute votre vie numérique.

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
> Une sécurité à 100 % n'existe pas. Les attaquants ne cherchent pas à forcer la porte blindée la plus solide d'un système, mais à trouver la faille la plus simple (un mot de passe par défaut, un logiciel non mis à jour ou une erreur humaine). La force globale d'un système de sécurité est égale à celle de son composant le plus faible — souvenez-vous du sondage d'ouverture : ce maillon, c'est très souvent l'humain.

!!! question "💬 Question chat — À vous de jouer"
    Pensez à votre métier ou à votre quotidien : laquelle des trois lettres — **C**, **I** ou **D** — serait la plus grave à perdre pour vous ? Tapez la lettre dans le chat, avec votre secteur si vous le souhaitez. Le mentor lit quelques réponses et montre que la réponse dépend du métier : un hôpital privilégie la Disponibilité, une banque l'Intégrité, un cabinet d'avocats la Confidentialité.

### Activité — Qualification d'incidents (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Présentez successivement les trois scénarios et faites voter le pilier compromis **en premier**. Après chaque vote, déroulez le débrief (pilier + mesure préventive) avant le scénario suivant. C'est l'activité phare de la première moitié de session.

*   **📊 Sondage n°2 — Scénario A :** Un hôpital subit une attaque par rançongiciel : les écrans affichent une demande de rançon, l'ensemble des dossiers médicaux est chiffré et inaccessible. Quel pilier est compromis en premier ?
    *   A) Confidentialité
    *   B) Intégrité
    *   C) Disponibilité ✅
*   **📊 Sondage n°3 — Scénario B :** Un étudiant accède à la base de données des notes de son université et passe sa note de cybersécurité de 08/20 à 18/20 avant la publication. Quel pilier est violé ?
    *   A) Confidentialité
    *   B) Intégrité ✅
    *   C) Disponibilité
*   **📊 Sondage n°4 — Scénario C :** Une entreprise de e-commerce laisse par erreur un fichier (e-mails, mots de passe hachés, adresses postales de clients) en accès libre sur un serveur web ; il est téléchargé et publié sur un forum. Quel pilier est rompu ?
    *   A) Confidentialité ✅
    *   B) Intégrité
    *   C) Disponibilité

**Éléments de débriefing (pour le mentor) :**

- **Scénario A** : la **Disponibilité** tombe en premier (les soignants n'accèdent plus aux dossiers — des vies en jeu) ; la Confidentialité peut suivre si les données ont été volées avant chiffrement (la « double extorsion »). *Mesure préventive : sauvegardes régulières hors ligne pour restaurer sans payer.* Annoncez : « ce scénario n'a rien de théorique — nous l'étudierons en vrai dans quelques minutes. »
- **Scénario B** : l'**Intégrité** — la donnée est altérée, l'exactitude du relevé est faussée. Notez qu'aucune donnée n'a été volée ni bloquée : l'attaque à l'intégrité est la plus discrète des trois. *Mesure préventive : restreindre l'écriture aux seuls autorisés et journaliser les modifications (audit trail).*
- **Scénario C** : la **Confidentialité** — divulgation à des tiers non autorisés, sans intrusion : une simple erreur de configuration suffit. *Mesure préventive : principe du moindre privilège et audits réguliers des partages publics.*

### 2. Les impacts business d'une cyberattaque
Une cyberattaque n'est pas seulement un problème technique pour le département informatique ; c'est un risque majeur pour l'existence même de l'entreprise (*business*). Ses conséquences se classent en trois grandes catégories :

*   **Impact financier direct** : Perte immédiate liée à l'arrêt d'une usine ou d'un site de vente en ligne (perte d'exploitation), coûts de remédiation (frais des experts techniques appelés en urgence pour nettoyer le réseau) et rançons éventuelles (bien qu'il soit fortement déconseillé de payer — c'est la doctrine française).
*   **Impact juridique et réglementaire** : Amendes administratives lourdes en cas de non-respect du RGPD si des données personnelles ont été volées faute de sécurité suffisante (jusqu'à 20 M€ ou 4 % du chiffre d'affaires mondial — approfondi en session B15). À cela s'ajoutent les frais de litiges intentés par les clients ou partenaires lésés.
*   **Impact réputationnel** : C'est souvent l'impact le plus difficile à chiffrer mais le plus destructeur à long terme. La perte de confiance des clients et des investisseurs peut conduire à une baisse brutale des ventes et à la résiliation de contrats clés.

### 3. La menace en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **Le facteur humain est impliqué dans environ 60 % des violations de données** (Verizon, *Data Breach Investigations Report*, 2025).
    - **L'ANSSI a traité près de 4 400 événements de sécurité en 2024**, en hausse d'environ 15 % sur un an ; TPE/PME/ETI et collectivités territoriales sont les premières victimes des rançongiciels (ANSSI, *Panorama de la cybermenace 2024*).
    - **Une violation de données coûte en moyenne environ 4,4 millions de dollars** dans le monde, et plusieurs mois s'écoulent en moyenne entre l'intrusion et son confinement (IBM, *Cost of a Data Breach Report*, 2025).
    - **Les violations notifiées à la CNIL ont atteint un record en 2024** (plus de 5 000 notifications, en forte hausse), portées par plusieurs fuites d'ampleur nationale (CNIL, bilan 2024).

**Comment lire ces chiffres ?** L'attaque n'est pas un événement rare : c'est un flux industriel et permanent, qui vise d'abord les structures qui se croient trop petites pour intéresser qui que ce soit. Et l'humain y est à la fois la première porte d'entrée et la première ligne de défense.

### 4. Deux études de cas réelles (France)

#### Cas n°1 — L'hôpital de Corbeil-Essonnes (2022) : la Disponibilité qui s'effondre

Dans la nuit du 20 au 21 août 2022, le Centre Hospitalier Sud Francilien (CHSF) est frappé par le rançongiciel **LockBit** : dossiers patients, laboratoire et imagerie inaccessibles. L'hôpital bascule en « mode dégradé » — retour au papier, transfert des patients critiques, déprogrammation d'interventions. Les attaquants exigent **10 millions de dollars** ; conformément à la doctrine française, l'hôpital refuse. En représailles, environ **11 Go de données** de patients et de personnels sont publiés : la violation de **Disponibilité** se double d'une violation de **Confidentialité** (la double extorsion). Des mois de reconstruction suivront, pour un coût de plusieurs millions d'euros.

**Ce que ce cas illustre :** votre scénario A de l'activité, en grandeur nature — et les trois impacts business simultanés : financier (reconstruction), juridique (données de santé), réputationnel (une crise nationale).

#### Cas n°2 — France Travail (2024) : la Confidentialité à l'échelle nationale

En mars 2024, France Travail révèle une intrusion via des comptes de partenaires usurpés : les données personnelles de potentiellement **43 millions de personnes** (identité, numéro de sécurité sociale, coordonnées) sont exfiltrées — l'une des plus grandes fuites jamais enregistrées en France. Ni mot de passe ni donnée bancaire volés, et pourtant : ces informations alimenteront des campagnes d'hameçonnage ultra-crédibles et des tentatives d'usurpation d'identité pendant des années.

**Ce que ce cas illustre :** une violation de **Confidentialité** pure — aucun système bloqué, rien de modifié — dont l'effet est différé. Les données volées aujourd'hui sont les attaques de demain : vous verrez exactement comment en session B04 (ingénierie sociale).

### 5. Les métiers de la cybersécurité
Le secteur de la cybersécurité regroupe des profils variés qui collaborent pour protéger les organisations. On divise traditionnellement ces rôles en deux postures :

*   **La Red Team (Posture offensive)** : Experts chargés de tester la résistance de l'entreprise en simulant des attaques réelles (tests d'intrusion ou *pentesting*), toujours dans un cadre contractuel strict. Leur but : identifier les failles avant que de vrais criminels ne le fassent.
*   **La Blue Team (Posture défensive)** : Ingénieurs et analystes chargés de construire les défenses au quotidien, de surveiller les réseaux (analystes SOC — *Security Operations Center*, découverts en B16) et de réagir en cas d'attaque avérée (répondeurs d'incident, session B18).
*   **Le RSSI (*CISO*)** : Le rôle de direction qui orchestre la stratégie de sécurité globale, gère les budgets et fait le lien entre la technique et la direction de l'entreprise (gouvernance, session B13).

Et le marché de l'emploi ? Les études internationales de référence estiment le déficit mondial de professionnels de la cybersécurité à **plusieurs millions de postes** (de l'ordre de 4 à 5 millions selon les études (ISC)², 2024) : peu de secteurs offrent une telle sécurité de parcours à qui se forme sérieusement.

!!! tip "📊 Sondage Livestorm n°5 — Votre profil (sondage d'opinion, pas de bonne réponse)"
    **Question :** Si vous deviez rejoindre le secteur demain, quelle posture vous attirerait le plus ?

    - A) Red Team — attaquer (légalement) pour tester
    - B) Blue Team — défendre, surveiller, réagir
    - C) Gouvernance — piloter, organiser, mettre en conformité
    - D) Je ne sais pas encore

    **Débrief mentor :** Aucune mauvaise réponse — et une bonne nouvelle : le parcours B couvre les trois postures (offensive en filigrane, défensive dans les modules réseau/SOC, gouvernance au module D). Les « je ne sais pas encore » ont 19 sessions pour se décider.

---

### Questions de réflexion
1. Si un site de e-commerce subit une interruption de service (indisponibilité) d'une heure lors du Black Friday, quel pilier est touché et quelles sont les conséquences financières et de réputation potentielles ?
2. Pourquoi dit-on souvent que la confidentialité et la disponibilité peuvent parfois s'opposer ? (Indice : Pensez aux mécanismes de contrôle d'accès stricts qui ralentissent l'accès rapide aux données).
3. Le CHSF a refusé de payer 10 M$ de rançon. Quels arguments pour et contre cette décision, du point de vue du directeur d'hôpital ? Et du point de vue de la société ?

**Corrigé / Éléments de réponse :**
1. La Disponibilité est touchée. Les conséquences incluent une perte financière directe énorme (ventes manquées) et un impact réputationnel important.
2. La confidentialité impose des contrôles (mots de passe, chiffrements) qui peuvent ralentir ou compliquer l'accès rapide et fluide (disponibilité) aux données. La sécurité est toujours un arbitrage.
3. Pour : ne pas financer le crime, aucune garantie de déchiffrement, ne pas se désigner comme « payeur ». Contre (à discuter) : la pression de la continuité des soins. La doctrine française tranche : on ne paie pas — et on investit dans les sauvegardes.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Pour bien comprendre la cybersécurité, imaginez l'analogie d'un **château fort médiéval** :
    - **Les Douves et le Pont-levis** agissent comme le pare-feu : ils filtrent les accès et n'autorisent le passage que par une seule entrée surveillée.
    - **Les Gardes à l'intérieur de la cour** sont l'Antivirus/EDR : s'il y a un intrus ou une bagarre dans la cour, ils interviennent immédiatement.
    - **La Salle du trésor (donjon)** représente les données sensibles. Elle nécessite plusieurs clés et l'accord de plusieurs officiers (Authentification Multifacteur - MFA).
    - **Les Espions et éclaireurs** représentent la sécurité offensive : ils étudient les faiblesses des murs du château pour les réparer avant qu'une armée ennemie ne les attaque.

    Cette superposition de protections indépendantes s'appelle la **défense en profondeur** : aucune muraille n'est infranchissable, l'objectif est qu'aucune brèche isolée ne suffise à atteindre le trésor.

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

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après la séquence métiers.

*   **📊 Sondage n°6 :** Quel impact d'une cyberattaque est réputé le plus difficile à chiffrer et le plus destructeur à long terme ?
    *   A) Le coût de remédiation technique
    *   B) L'amende réglementaire
    *   C) L'impact réputationnel (perte de confiance des clients) ✅
*   **📊 Sondage n°7 :** Que dit la « règle du maillon le plus faible » ?
    *   A) La force d'un système de sécurité est égale à celle de son composant le plus faible ✅
    *   B) Il faut renforcer uniquement la porte d'entrée principale
    *   C) Les petits systèmes sont plus sûrs que les grands
*   **📊 Sondage n°8 :** Quelle équipe simule des attaques réelles, dans un cadre légal, pour tester les défenses ?
    *   A) La Blue Team
    *   B) La Red Team ✅
    *   C) Le service juridique

**Éléments de débriefing (pour le mentor) :**

- N°6 : l'argent se réemprunte, la confiance ne se rachète pas — reboucler avec les trois impacts et le cas CHSF.
- N°7 : l'attaquant cherche la porte ouverte, pas la porte blindée — et cette porte est souvent humaine (sondage n°1).
- N°8 : Red = tester (avec contrat), Blue = défendre au quotidien ; le RSSI orchestre. Teaser des sessions B16-B18 pour la Blue Team.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Cybersecurity Fundamentals - Part 1"* (~1h30).
*   **[ANSSI — cyber.gouv.fr](https://cyber.gouv.fr/)** : consulter la section "Actualités" pour observer des incidents récents en France, et le *Panorama de la cybermenace* annuel (synthèse lisible par des non-spécialistes).
*   **[CNIL — Sécurité des données](https://www.cnil.fr)** : bilans annuels des violations notifiées et conseils aux personnes concernées.

## 4. Exercice bonus (Dilemme Décisionnel - Livestorm)

*   **Objectif :** Analyse d'impact rapide et priorisation, en écho direct au cas réel du CHSF étudié plus haut.
*   **📊 Sondage Livestorm n°9 :** Une attaque par Ransomware cible un hôpital. Les dossiers médicaux sont inaccessibles. Quelle est la première action d'urgence à voter ?
    *   A) Payer immédiatement la rançon demandée.
    *   B) Isoler physiquement le réseau et couper les liaisons réseau des machines affectées pour confiner l'attaque ✅
    *   C) Reconstruire les serveurs à partir des sauvegardes sur le même réseau actif.
*   **Guide d'animation (pour le mentor) :** Expliquez pourquoi isoler le réseau (B) est indispensable pour couper la propagation latérale avant d'envisager la restauration. Le paiement (A) n'offre aucune garantie et finance le cybercrime — le choix qu'a écarté le CHSF. Restaurer sur un réseau compromis (C) revient à reconstruire la maison pendant l'incendie. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **AES-256** | Standard de chiffrement symétrique hautement sécurisé utilisant des clés de 256 bits, considéré comme inviolable par la force brute actuelle. |
| **Blue Team** | Équipe interne chargée de surveiller les réseaux et de repousser les attaques au quotidien. |
| **DDoS (Déni de service distribué)** | Attaque visant à rendre un service indisponible en le submergeant de requêtes réseau depuis de nombreuses sources. |
| **RaaS (Ransomware-as-a-Service)** | Modèle économique cybercriminel où des développeurs vendent ou louent des rançongiciels à des affiliés qui exécutent les attaques. |
| **Ransomware (Rançongiciel)** | Logiciel malveillant qui chiffre les données puis exige une rançon, souvent doublé d'une menace de publication (double extorsion). |
| **Red Team** | Groupe d'experts simulant des attaques pour évaluer les défenses, dans un cadre légal et contractuel. |
| **RSSI (CISO)** | Pilote de la stratégie de sécurité : budgets, arbitrages, lien technique-direction. |
| **SHA-256** | Algorithme de hachage cryptographique produisant une empreinte numérique unique de 256 bits pour vérifier l'intégrité d'une donnée. |
| **Triade CIA (ou CID)** | Confidentialité, Intégrité, Disponibilité — la grille d'analyse de tout incident (acronyme anglais : *Confidentiality, Integrity, Availability*). |

**La règle d'or de la session :** face à tout incident, demandez-vous d'abord quel pilier — C, I ou D — est touché ; et souvenez-vous que le maillon le plus faible est rarement la machine.
