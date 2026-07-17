# Grand Atelier d'Audit Interactif — MedDistri (Avancé)
Parcours : B 20 sessions  |  Module : Consolidation & Évaluation  |  Format : Atelier d'audit & de crise (Livestorm, session B20)

---

## 1. Contexte étendu de la PME : « MedDistri »

Vous êtes collectivement le consultant senior en cybersécurité. Vous auditez et sécurisez **MedDistri**, une PME de 25 salariés distribuant des dispositifs médicaux, qui manipule des données clients sensibles.

### Diagnostic de l'infrastructure initiale :
*   **Réseau à plat** : pas de segmentation — ordinateurs des commerciaux, serveurs sensibles et Wi-Fi visiteurs partagent le même réseau local.
*   **Accès externes non protégés** : ports 3389 (RDP) et 22 (SSH) ouverts sur l'IP publique, sans filtrage de source ; mot de passe administrateur faible et connu (`Admin@MedDistri2025`).
*   **Identités et cloud** : Microsoft 365 (e-mails RH et comptabilité) sans MFA.
*   **Sauvegardes vulnérables** : sauvegarde manuelle sur disque USB branché en permanence au serveur de fichiers.
*   **Conformité RGPD** : données médicales indirectes stockées sans chiffrement ni registre des traitements.

*Chaque vulnérabilité est la copie d'une affaire réelle du parcours — le tableau « MedDistri en miroir » figure dans le [support B20](../supports-md/B_S20_support.md).*

---

## 2. Déroulement de l'atelier (Livestorm)

La session B20 se déroule en **plénière interactive** : le mentor partage son écran, présente chaque situation, fait débattre le chat, puis lance le vote. Le sondage n°1 (brise-glace MFA), le n°8 (débat « objection de la directrice ») et le n°9 (bonus) sont décrits dans le [support B20](../supports-md/B_S20_support.md) ; les six votes d'audit ci-dessous occupent les sondages **n°2 à n°7**. MedDistri part d'un **score de résilience de 10 %** ; chaque décision collective correcte le fait progresser.

### Phase 1 : Durcissement technique & réseau (acquis de B05-B08)

*   **📊 Sondage n°2 — Segmentation réseau**
    *   *Question :* Pour mettre fin au réseau local à plat de MedDistri, quelle architecture de segmentation implémenter ?
        *   A) Configurer un VPN uniquement sur les téléphones des commerciaux
        *   B) Mettre en place 3 VLANs distincts (LAN administratif, LAN entrepôt, DMZ pour les serveurs exposés), isolés par un pare-feu avec filtrage strict ✅
        *   C) Ajouter un second pare-feu en série, sans modifier le réseau plat
*   **📊 Sondage n°3 — Règles de filtrage pare-feu**
    *   *Question :* Quelle règle de filtrage essentielle protège le réseau interne contre un rebond depuis la DMZ ?
        *   A) Autoriser tous les flux sortants du LAN interne vers la DMZ
        *   B) Interdire tout flux initié depuis la DMZ vers le LAN administratif interne ✅
        *   C) Autoriser le trafic SSH de la DMZ vers le LAN

### Phase 2 : Identités, protection des données & sauvegardes (acquis de B09-B12)

*   **📊 Sondage n°4 — Chiffrement des terminaux nomades**
    *   *Question :* Les 15 commerciaux utilisent leurs portables dans des lieux publics. Comment protéger les données locales en cas de vol du matériel ?
        *   A) Installer un pare-feu personnel sur les ordinateurs
        *   B) Chiffrer l'intégralité du disque (BitLocker ou FileVault) et imposer des mots de passe de session robustes ✅
        *   C) Désactiver le mot de passe de session pour accélérer le démarrage
*   **📊 Sondage n°5 — Sauvegarde résiliente face au rançongiciel**
    *   *Question :* Quelle stratégie remplace efficacement la sauvegarde USB branchée en permanence ?
        *   A) Une sauvegarde locale deux fois par jour, sur un autre serveur du même réseau
        *   B) La règle 3-2-1 : deux supports locaux (dont un déconnecté, hors ligne) et une sauvegarde immuable déportée dans le cloud ✅
        *   C) Copier manuellement les fichiers sur OneDrive de temps en temps

### Phase 3 : Incident en direct & gestion de crise (acquis de B18-B19)

*   **📊 Sondage n°6 — Incident actif en cours de séance**
    *   *Question :* Un rançongiciel commence à chiffrer les postes de la comptabilité ; l'attaquant menace de divulguer les données de santé des clients. Première mesure ?
        *   A) Éteindre complètement les ordinateurs du réseau et contacter l'ANSSI
        *   B) Débrancher le câble réseau (ou couper le Wi-Fi) de chaque machine infectée pour stopper la propagation, isoler au pare-feu — **sans éteindre**, pour préserver la RAM ✅
        *   C) Payer immédiatement la rançon avec la carte bancaire de l'entreprise
*   **📊 Sondage n°7 — Communication de crise**
    *   *Question :* Des journalistes contactent le service logistique au sujet de l'attaque. Quelle directive imposer en interne ?
        *   A) Laisser chaque employé répondre librement, pour montrer la transparence
        *   B) Diriger toutes les demandes vers la cellule de crise (porte-parole unique) et interdire aux collaborateurs de s'exprimer en direct ✅
        *   C) Couper le téléphone de l'entreprise

---

## 3. Bilan de résilience cyber de la PME

Le mentor évalue les décisions collectives : la PME obtient son **Label de Résilience Cyber** si le score final dépasse **75 %**. Le débrief s'appuie sur le schéma réseau cible (DMZ, VLANs, VPN + MFA) dessiné en direct, et sur le plan de remédiation priorisé (les « quick wins » d'abord : MFA, fermeture RDP/SSH, sauvegarde hors ligne). Ce format d'atelier collectif remplace les anciennes modalités de projet individuel, pour s'adapter au webinaire à forte audience.
