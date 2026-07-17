# Ateliers de Synthèse Pratiques (Visioconférence)
Parcours : B 20 sessions  |  Module : Consolidation Pratique  |  Format : Ateliers Collectifs Synchrone (Livestorm)

---

## Fonctionnement des Ateliers de Synthèse
Dans le cadre de cette formation en visioconférence à forte audience, les apprenants ne réalisent pas de projets écrits individuels hors session. Le mentor anime des **Ateliers de Synthèse Pratiques** répartis tout au long du parcours. Ces ateliers d'une durée de 30 minutes remplacent les anciens mini-projets. 

Le mentor présente une problématique concrète sur son écran (un cas technique, un log, un schéma), et le public collabore via le **Chat** et les **Sondages (Polls)** Livestorm pour résoudre le problème.

---

## Atelier de Synthèse 1 (Session B08) — Architecture & Segmentation Réseau
*   **Objectif** : Valider l'isolement du réseau de la PME MedDistri à la suite du module réseau.
*   **Méthodologie sur Livestorm** :
    1.  *Présentation* : Le mentor affiche un schéma de réseau local à plat (sans routeur ni pare-feu).
    2.  *Sondage* : Quelle est la meilleure position pour installer la DMZ hébergeant le serveur web ?
        *   A) Directement branché sur le commutateur des postes de travail administratifs.
        *   B) Connecté à un port dédié du pare-feu avec des règles de filtrage étanches ✅
    3.  *Discussion* : Le mentor dessine le schéma cible sur son tableau blanc interactif et définit la table de flux pare-feu à partir des suggestions écrites par les apprenants dans le chat.

---

## Atelier de Synthèse 2 (Session B12) — Plan de durcissement et conformité
*   **Objectif** : Concevoir la politique de durcissement des accès et des terminaux d'une PME.
*   **Méthodologie sur Livestorm** :
    1.  *Présentation* : Le mentor liste les contraintes logistiques (employés en déplacement, accès cloud, mots de passe enregistrés sur navigateur).
    2.  *Sondage 1 (MFA)* : Quelle méthode de MFA préconisez-vous pour les 15 commerciaux nomades ?
        *   A) Authentification par SMS.
        *   B) Application d'authentification (ex. Microsoft Authenticator) ou clé physique FIDO2 ✅
    3.  *Sondage 2 (Classification)* : Les fiches de paie stockées sur OneDrive doivent être classées :
        *   A) Internes.
        *   B) Confidentielles ✅
    4.  *Discussion* : Le mentor rédige en direct la liste des 5 règles de sécurité de base d'accès cloud en fonction des votes et des commentaires des participants.

---

## Atelier de Synthèse 3 (Session B15) — Analyse de Risques & Matrice 4x4
*   **Objectif** : Identifier et évaluer 3 menaces critiques pour MedDistri.
*   **Méthodologie sur Livestorm** :
    1.  *Présentation* : Le mentor présente les scénarios de menace (Ransomware, Vol d'un ordinateur de commercial, Usurpation d'identité pour fraude au virement).
    2.  *Sondage (Cotation)* : Pour le scénario "Ransomware sur la base de données comptables", comment évaluez-vous l'impact sur l'activité ?
        *   A) Faible (1) - B) Moyen (2) - C) Majeur (3) - D) Critique (4) — *Majeur ou Critique : les deux se défendent, c'est le débat qui compte.*
    3.  *Discussion* : Les apprenants justifient leur choix dans le chat (ex. *« C'est critique car la comptabilité bloque les salaires et la facturation »*). Le mentor remplit la matrice 4x4 de risques en direct en synthétisant l'avis général.

---

## Atelier de Synthèse 4 (Session B17) — Analyse de Logs & Détection
*   **Objectif** : Lire et interpréter un extrait de fichier `access.log` Apache suspect (l'extrait complet de 5 lignes et les débriefs détaillés figurent dans le [support B17](../supports-md/B_S17_support.md)).
*   **Méthodologie sur Livestorm** :
    1.  *Présentation* : Le mentor affiche l'extrait de 5 lignes de logs web, dont la ligne clé :
        `203.0.113.66 - - [08/Jul/2026:21:00:15 +0200] "GET /product.php?id=1' OR 1=1-- HTTP/1.1" 200 4522`
    2.  *Sondage 1* : Quelle est l'attaque en cours de tentative dans ce log ?
        *   A) Traversée de répertoire (Path Traversal).
        *   B) Injection SQL (SQLi) ✅
        *   C) Déni de service (DDoS).
    3.  *Sondage 2* : D'après le code statut HTTP `200` et l'évolution des tailles de réponses (851 → 4522 → 6817 octets), la tentative a-t-elle potentiellement réussi ?
        *   A) Oui : le serveur a répondu favorablement, et le volume anormal suggère que des données ont été renvoyées ✅
        *   B) Non, la ressource a été bloquée.
    4.  *Sondage 3* : Quelles contre-mesures immédiates recommandez-vous ?
        *   A) Éteindre définitivement le serveur web.
        *   B) Bloquer l'IP `203.0.113.66` sur le pare-feu applicatif (WAF), passer le WAF en mode blocage et corriger l'application (requêtes paramétrées) ✅
        *   C) Effacer les journaux compromis et réinstaller.
    5.  *Discussion (chat)* : Que révèle la 5e ligne du log (code 400) ? Le mentor conclut sur la chronologie complète de l'attaque et la valeur probante des journaux.
