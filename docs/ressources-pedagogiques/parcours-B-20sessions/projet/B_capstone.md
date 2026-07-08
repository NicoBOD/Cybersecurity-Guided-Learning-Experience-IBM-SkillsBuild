# Grand Atelier d'Audit Interactif — MedDistri (Avancé)
Parcours : B 20 sessions  |  Module : Consolidation & Évaluation  |  Format : Atelier de Crise & Décision (Livestorm)

---

## 1. Contexte étendu de la PME : "MedDistri"

Vous êtes consultant senior en cybersécurité. Vous présentez l'audit complet et concevez la stratégie de sécurisation de **MedDistri**, une PME de 25 salariés distribuant des dispositifs médicaux et des données clients sensibles.

### Diagnostic de l'infrastructure initiale :
*   **Réseau à plat** : Pas de segmentation. Les ordinateurs des commerciaux, les serveurs sensibles et les smartphones des visiteurs Wi-Fi partagent le même réseau local interne.
*   **Accès externe non protégé** : Les ports 3389 (RDP) et 22 (SSH) sont ouverts sur l'adresse IP publique de la PME, sans filtrage de source. Le mot de passe administrateur est faible et connu (`Admin@MedDistri2025`).
*   **Identités et Cloud** : Microsoft 365 est utilisé pour les e-mails RH et de comptabilité sans MFA.
*   **Sauvegardes vulnérables** : Sauvegarde manuelle sur disque dur USB branché en permanence au serveur de fichiers Windows local.
*   **Conformité RGPD** : Fichiers contenant des données médicales indirectes stockés sans chiffrement ni registre de traitement formel.

---

## 2. Déroulement de l'Atelier Visioconférence (Livestorm)

La session finale B20 se déroule sous la forme d'un **exercice de table (Tabletop Exercise) interactif** animé par le mentor. Le mentor partage son écran, présente les scénarios techniques et de crise, puis lance les sondages Livestorm pour obtenir l'avis du public. Le public débat dans le chat avant chaque décision.

### Phase 1 : Durcissement Technique & Réseau (Session B08)

*   **Sondage 1 : Segmentation et filtrage réseau**
    *   *Question :* Pour mettre fin au réseau local à plat de MedDistri, quelle architecture de segmentation implémenter ?
        *   A) Configurer un VPN uniquement sur les téléphones des commerciaux.
        *   B) Mettre en place 3 VLANs distincts (LAN Admin, LAN Entrepôt, DMZ pour les serveurs exposés) isolés par un pare-feu avec filtrage strict *(Bonne réponse)*.
        *   C) Mettre en place un second pare-feu connecté en série sans modification du réseau local plat.
*   **Sondage 2 : Règles de filtrage pare-feu**
    *   *Question :* Quelle règle de filtrage pare-feu essentielle devez-vous appliquer pour protéger le réseau interne contre un rebond depuis la DMZ ?
        *   A) Autoriser tous les flux sortants du LAN interne vers la DMZ.
        *   B) Interdire tout flux initié depuis la DMZ vers le réseau interne LAN administratif *(Bonne réponse)*.
        *   C) Autoriser le trafic SSH de la DMZ vers le LAN.

---

### Phase 2 : Identités, Protection des Données & Sauvegardes (Session B12)

*   **Sondage 3 : Chiffrement et terminaux nomades**
    *   *Question :* Les 15 commerciaux utilisent leurs ordinateurs portables dans des lieux publics. Comment protéger les données stockées localement en cas de vol matériel ?
        *   A) Installer un pare-feu personnel sur les ordinateurs.
        *   B) Chiffrer l'intégralité du disque système avec BitLocker ou FileVault et configurer des mots de passe de session robustes *(Bonne réponse)*.
        *   C) Désactiver le mot de passe de session pour accélérer le démarrage.
*   **Sondage 4 : Sauvegarde de résilience face au Ransomware**
    *   *Question :* Quelle stratégie de sauvegarde remplace efficacement la sauvegarde USB permanente face à la menace des ransomwares ?
        *   A) Mettre en œuvre une sauvegarde locale deux fois par jour sur un autre serveur du même réseau.
        *   B) Appliquer la règle 3-2-1 en combinant deux supports physiques locaux (dont un déconnecté hors ligne) et une sauvegarde immuable déportée dans le cloud *(Bonne réponse)*.
        *   C) Copier manuellement les fichiers sur Microsoft OneDrive de temps en temps.

---

### Phase 3 : Gouvernance, Risques & Incident en Direct (Session B19)

*   **Sondage 5 : Incident actif en cours de séance**
    *   *Question :* Un ransomware commence à chiffrer les postes de la comptabilité. L'attaquant menace de divulguer les données de santé des clients. Quelle est la première mesure de gestion de crise à appliquer ?
        *   A) Éteindre complètement les ordinateurs du réseau et contacter l'ANSSI.
        *   B) Débrancher le câble réseau (ou désactiver le Wi-Fi) de chaque machine infectée pour bloquer la propagation, puis isoler le réseau via le pare-feu sans éteindre les serveurs pour préserver la RAM *(Bonne réponse)*.
        *   C) Payer la rançon immédiatement à l'aide de la carte bancaire de l'entreprise.
*   **Sondage 6 : Communication de crise**
    *   *Question :* Des journalistes contactent le service logistique de MedDistri au sujet de l'attaque. Quelle est la directive à imposer en interne ?
        *   A) Laisser chaque employé répondre librement pour montrer notre transparence.
        *   B) Diriger toutes les demandes vers la directrice générale (cellule de crise) et interdire aux collaborateurs de communiquer en direct *(Bonne réponse)*.
        *   C) Couper le téléphone de l'entreprise.

---

## 3. Bilan de Résilience Cyber de la PME
Le mentor évalue les décisions collectives de l'auditoire. La PME obtient son **Label de Résilience Cyber** si le taux de bonnes réponses dépasse **75%**. Ce cas pratique remplace les anciennes modalités de projet individuel pour s'adapter à la dynamique de visioconférence interactive.
