# Grille d'évaluation du Projet Capstone — Parcours B
Parcours : B 20 sessions  |  Module : Consolidation & Évaluation  |  Format : Grille de notation sur 20 points

---

## 1. Répartition des points

La note globale du projet est calculée sur un total de **20 points**, répartie selon 5 critères d'évaluation fondamentaux :

| Critère d'évaluation | Points | Descriptif rapide |
| :--- | :---: | :--- |
| **1. Diagnostic technique & Réseau** | **/ 5 pts** | Analyse des accès distants, durcissement et schéma réseau cible segmenté (VLANs/DMZ). |
| **2. Analyse de risques & RGPD** | **/ 4 pts** | Pertinence de la matrice 4x4 (5 risques) et plan de mise en conformité RGPD pragmatique. |
| **3. Résilience & Réponse aux incidents** | **/ 4 pts** | Règle 3-2-1, objectifs RTO/RPO et qualité du Playbook d'urgence Ransomware (RAM). |
| **4. Réalisme de la feuille de route** | **/ 3 pts** | Phasage court/moyen/long terme cohérent avec les budgets et ressources de la PME. |
| **5. Qualité du Pitch & Échanges** | **/ 4 pts** | Dynamique d'équipe, respect du temps (7 min), vulgarisation et levée d'objections. |

---

## 2. Grille détaillée par niveau de maîtrise

### Critère 1 : Diagnostic technique & Réseau (/ 5 points)
*   **0 - 1.5 pt (Très insuffisant)** : Diagnostic absent ou superficiel. Les vulnérabilités des accès RDP/SSH ou le manque de segmentation ne sont pas traités. Pas de schéma réseau proposé.
*   **2 - 3 pts (Insuffisant)** : Diagnostic réalisé mais les recommandations techniques sont vagues ou inadaptées (ex. pas de chiffrement des flux, pas de VPN). Schéma réseau incomplet ou manquant de logique de cloisonnement.
*   **3.5 - 4.5 pts (Conforme)** : Bon diagnostic. Proposition d'un schéma d'architecture segmenté et documenté (WAN, DMZ pour le VPN, LANs internes). Table de flux pare-feu correcte et proposition systématique de MFA.
*   **5 pts (Excellent)** : Diagnostic exhaustif et ultra-rigoureux. Schéma réseau exemplaire (utilisant Mermaid ou équivalent) avec isolation stricte par VLANs. Table de flux pare-feu impeccable détaillant chaque protocole (HTTPS, SSH, RDP encapsulé) avec gestion des accès distants sécurisée.

---

### Critère 2 : Analyse de risques & RGPD (/ 4 points)
*   **0 - 1 pt (Très insuffisant)** : Absence de matrice de risques qualitative. Le RGPD est ignoré ou traité de manière théorique sans plan d'application concret pour les fichiers clients de MedDistri.
*   **1.5 - 2.5 pts (Insuffisant)** : Risques identifiés mais leur cotation brute et résiduelle est incohérente. Mesures RGPD incomplètes (ex. pas de registre des traitements simplifié ni de gestion des droits des personnes).
*   **3 pts (Conforme)** : Matrice 4x4 complète listant 5 risques réalistes pour MedDistri. Plan d'action RGPD pragmatique avec répartition des rôles (DPO mutualisé/externe) et mise en place d'une politique de conservation des données.
*   **3.5 - 4 pts (Excellent)** : Analyse de risques remarquable et parfaitement documentée. Plan de mise en conformité RGPD complet et directement applicable par la PME (mentions légales types, formulaires d'exercice de droits, registre opérationnel).

---

### Critère 3 : Résilience & Réponse aux incidents (/ 4 points)
*   **0 - 1 pt (Très insuffisant)** : Aucune stratégie de sauvegarde définie. Objectifs RTO/RPO absents. Pas de playbook ou de procédure de réaction d'urgence en cas d'attaque informatique.
*   **1.5 - 2.5 pts (Insuffisant)** : Stratégie de sauvegarde floue ne respectant pas l'isolation physique. Playbook d'incident générique sans consignes claires pour les collaborateurs ou le technicien.
*   **3 pts (Conforme)** : Politique de sauvegarde respectant la règle 3-2-1 avec externalisation hors ligne. Objectifs RTO et RPO définis de façon réaliste. Playbook de réaction Ransomware structuré répertoriant les étapes de confinement et d'éradication.
*   **3.5 - 4 pts (Excellent)** : Stratégie de résilience irréprochable (sauvegardes immuables). Objectifs RTO/RPO parfaitement justifiés au regard des activités logistiques. Playbook d'incident de niveau professionnel insistant sur la **préservation de la mémoire RAM** avant extinction et détaillant les rôles de communication.

---

### Critère 4 : Réalisme de la feuille de route (/ 3 points)
*   **0 - 1 pt (Très insuffisant)** : Actions de remédiation en vrac sans planification chronologique. Recommandations déconnectées des réalités budgétaires et humaines d'une PME de 25 personnes.
*   **1.5 - 2.5 pts (Insuffisant)** : Feuille de route chronologique proposée mais manquant de cohérence dans les priorités (ex. investissements lourds programmés dès le premier mois alors que des failles critiques gratuites restent ouvertes).
*   **3 pts (Excellent)** : Feuille de route parfaitement découpée dans le temps (Court, Moyen et Long terme). Arbitrage pragmatique entre sécurité technique, coûts d'implémentation et continuité des opérations commerciales.

---

### Critère 5 : Qualité du Pitch & Échanges (/ 4 points)
*   **0 - 1 pt (Très insuffisant)** : Dépassement majeur du temps imparti (7 minutes). Prise de parole monopolisée par un seul membre. Discours trop technique et inintelligible pour une directrice de PME.
*   **1.5 - 2.5 pts (Insuffisant)** : Diapositives trop chargées de texte. Posture passive ou défensive lors des questions. Difficulté à justifier ses arbitrages techniques ou financiers.
*   **3 pts (Conforme)** : Pitch chronométré respectant les 7 minutes. Collaboration équilibrée du groupe à l'oral. Présentation vulgarisée avec succès. Réponses convaincantes et professionnelles aux questions du jury.
*   **3.5 - 4 pts (Excellent)** : Soutenance de niveau professionnel. Diapositives épurées et percutantes. Leadership partagé au sein de l'équipe. Capacité remarquable à désamorcer les objections sur les contraintes d'utilisabilité (ex. lourdeur du MFA pour les commerciaux) et à justifier le retour sur investissement de la cybersécurité.

---

## 3. Formulaire de Feedback (Jury et Pairs)

### Section administrative :
*   **Groupe d'évaluation** : N° ______
*   **Noms des membres du groupe** : ____________________________________________________
*   **Note finale attribuée** : ______ / 20
*   **Décision finale** :
    *   ⬜ **Validé** (Félicitations, acquisition des compétences certifiée)
    *   ⬜ **Rattrapage requis** (Livrables à retravailler sous 15 jours sur les points mentionnés ci-dessous)

### Commentaires qualitatifs détaillés :
*   **Points forts du projet (Ce qui a été particulièrement bien traité)** :
    *   __________________________________________________________________________________
    *   __________________________________________________________________________________
*   **Axes d'amélioration prioritaires (Ce qui doit être retravaillé ou approfondi)** :
    *   __________________________________________________________________________________
    *   __________________________________________________________________________________
