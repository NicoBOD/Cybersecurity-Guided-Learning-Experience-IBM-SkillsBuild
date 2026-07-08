# Session B13 — Gouvernance & cadres de sécurité

## Objectifs de la session
À la fin de cette session, vous serez capable de :

* Expliquer la structure, l'utilité et le processus d'élaboration d'une Politique de Sécurité des Systèmes d'Information (PSSI).
* Comparer les référentiels de sécurité mondiaux ISO 27001 (management organisationnel) et NIST CSF (cadre opérationnel technique).
* Identifier la répartition des rôles et responsabilités entre la Direction Générale et le RSSI au sein de la gouvernance de sécurité d'une entreprise.

---

## Concepts clés

### 1. La Politique de Sécurité des Systèmes d'Information (PSSI)

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.

La **PSSI** est le document de référence stratégique et juridique d'une entreprise. Elle traduit les objectifs de sécurité en règles d'usage précises et en exigences techniques obligatoires pour l'ensemble des collaborateurs et prestataires.

*   **Portage par la direction** : Une PSSI ne doit pas être un simple document technique rédigé dans son coin par le service informatique. Pour être légitime, applicable et juridiquement contraignante, elle doit être **validée et signée par la Direction Générale** (souvent annexée au règlement intérieur de l'entreprise).
*   **Structure classique d'une PSSI** :
    *   *Champ d'application* : Qui et quels équipements sont concernés.
    *   *Rôles et responsabilités* : Qui gère la sécurité, qui valide les accès.
    *   *Règles d'usage informatique* : Complexité des mots de passe, règles d'usage de la messagerie, charte de télétravail, gestion du matériel d'entreprise.
    *   *Sanctions* : Conséquences prévues en cas de violation volontaire des règles.

### 2. Les référentiels mondiaux : ISO 27001 vs NIST CSF
Pour concevoir leur stratégie cyber, les entreprises s'appuient sur des cadres de référence reconnus mondialement :

*   **ISO/IEC 27001 (Management de la sécurité)** : C'est la norme internationale décrivant la mise en place d'un **SMSI** (Système de Management de la Sécurité de l'Information). Elle repose sur le principe de l'amélioration continue (la roue de Deming ou **PDCA** : *Plan, Do, Check, Act*). C'est une démarche organisationnelle globale qui aboutit, après audit externe, à une certification officielle très valorisée auprès des clients.
*   **NIST CSF (Cybersecurity Framework - Cadre d'action technique)** : Proposé par l'organisme public américain NIST, c'est un cadre pragmatique, axé sur la gestion opérationnelle et technique des risques. Il structure la défense autour de **5 fonctions clés** :
    1.  **Identify (Identifier)** : Cartographier les actifs matériels, logiciels et les risques.
    2.  **Protect (Protéger)** : Mettre en œuvre des barrières de sécurité (pare-feu, IAM, formation).
    3.  **Detect (Détecter)** : Déployer des outils pour identifier les anomalies en continu (supervision).
    4.  **Respond (Répondre)** : Définir des procédures de réaction rapide en cas d'attaque détectée.
    5.  **Recover (Restaurer)** : Planifier la restauration des systèmes d'information (sauvegardes, continuité).

*   *L'analogie du bâtiment* :
    *   **ISO 27001** est le code de la construction et le manuel de gestion de l'immeuble. Il garantit que vous avez mis en place des comités de suivi, des processus de réévaluation et des audits pour veiller à la qualité continue du bâtiment.
    *   **NIST CSF** est le plan d'action opérationnel des pompiers et de la sécurité physique de l'immeuble. Il détaille exactement comment verrouiller les portes (Protect), où installer les détecteurs de fumée (Detect), et comment évacuer les occupants en cas d'incendie (Respond/Recover).

### 3. Rôles et responsabilités : Direction vs RSSI
La gouvernance cyber exige une distinction claire entre le pouvoir de décision et le rôle d'expertise :

*   **Le RSSI (Responsable de la Sécurité des Systèmes d'Information / *CISO*)** : C'est l'expert, le conseiller et le chef d'orchestre. Il analyse les menaces, rédige la PSSI, recommande des investissements techniques et sensibilise les équipes. **Le RSSI conseille, mais il ne prend pas les décisions stratégiques finales**.
*   **La Direction Générale** : C'est l'arbitre et le donneur d'ordres. C'est elle qui valide les budgets de sécurité, accepte formellement le niveau de risque restant, et assume la responsabilité civile et pénale en cas de sinistre majeur ou de fuite de données.

---

## Activités / exercices

### Exercice 1 — Rédaction d'une charte PSSI simplifiée sur les accès logiques
**Objectif :** Formaliser des règles de sécurité claires, exploitables et compréhensibles par les utilisateurs finaux dans le cadre d'une PSSI.

**Consignes :**
L'entreprise de logistique "EcoLog" souhaite intégrer une section "Sécurité des accès logiques et télétravail" dans sa PSSI. Rédigez 4 règles impératives à destination des salariés, en évitant le jargon trop technique mais en fixant des obligations claires et mesurables. 

*Indication : Pensez aux mots de passe, au MFA, à l'usage des terminaux personnels, et au verrouillage d'écran.*

**Corrigé / Éléments de réponse :**

*   **Règle 1 (Mots de passe)** : *"Chaque collaborateur doit utiliser un mot de passe unique composé d'au moins 12 caractères, comprenant des majuscules, des minuscules, des chiffres et des caractères spéciaux. L'usage d'un gestionnaire de mots de passe d'entreprise est obligatoire pour stocker ces secrets."*
    *   *Justification* : Prévient les attaques par force brute ou dictionnaire et évite la réutilisation de mots de passe identiques.
*   **Règle 2 (Authentification forte)** : *"L'authentification multifacteur (MFA) doit obligatoirement être activée pour toute connexion à distance au réseau de l'entreprise (VPN) ou aux applications Cloud d'entreprise."*
    *   *Justification* : Protège les comptes en cas de vol de mot de passe à la suite d'un hameçonnage.
*   **Règle 3 (Télétravail & Équipements)** : *"Il est strictement interdit d'utiliser un ordinateur personnel pour accéder aux applications internes ou traiter des données de l'entreprise. Seuls les ordinateurs portables fournis et configurés par le service informatique d'EcoLog sont autorisés."*
    *   *Justification* : Garantit que les outils de sécurité (EDR, pare-feu local) sont actifs sur les machines traitant les données de l'entreprise.
*   **Règle 4 (Sécurité physique du poste)** : *"Tout collaborateur quittant son poste de travail, même temporairement, doit obligatoirement verrouiller sa session informatique (touche Raccourci Windows + L)."*
    *   *Justification* : Évite qu'une personne de passage (visiteur, personnel d'entretien) n'accède à des données sensibles à l'insu de l'employé.

---

## Questions de réflexion
1. Pourquoi est-il risqué qu'un RSSI soit directement rattaché à la Direction Informatique (DSI) plutôt qu'au Secrétariat Général ou à la Direction des Risques ? (Pensez aux conflits d'intérêts entre la production informatique et le contrôle de sécurité).
2. Si une entreprise est certifiée ISO 27001, cela signifie-t-il qu'elle est techniquement impossible à pirater ? Expliquez la différence entre un système de management de la sécurité et une garantie de sécurité absolue.

---

!!! abstract "Résumé"
    / points à retenir
    *   La **PSSI** définit le cadre légal et technique de la sécurité. Elle doit être validée et portée politiquement par la **Direction Générale** pour être contraignante.
    *   L'**ISO 27001** structure le management de la sécurité (SMSI) autour de l'amélioration continue (**PDCA**), tandis que le **NIST CSF** fournit un cadre d'action opérationnel basé sur 5 fonctions techniques.
    *   Le **RSSI** propose et orchestre les mesures de sécurité, mais c'est la **Direction Générale** qui prend les décisions stratégiques et financières de couverture des risques.

---

## Glossaire de la session
*   **PSSI** — Politique de Sécurité des Systèmes d'Information. Document de référence traduisant la stratégie de sécurité de l'entreprise en règles opérationnelles.
*   **SMSI** — Système de Management de la Sécurité de l'Information. Cadre organisationnel (processus, personnes, technologies) visant à protéger l'information d'une entreprise.
*   **RSSI (CISO)** — Responsable de la Sécurité des Systèmes d'Information. Expert technique et organisationnel chargé de piloter la sécurité informatique de l'organisation.
*   **PDCA (Plan, Do, Check, Act)** — Cycle d'amélioration continue (ou roue de Deming) à la base du management de la qualité et des normes ISO.

---

## Pour aller plus loin (self-paced)
*   **Sur IBM SkillsBuild** : Suivre le cours *"Cybersecurity Governance and Risk Management - Part 1"* (durée estimée : 1h30).
*   **Ressource complémentaire** : Visiter le site de l'ANSSI (cyber.gouv.fr) et télécharger le document *"La PSSI en 10 principes de base"* pour observer comment un État structure ses exigences nationales.


## Exercice Bonus (Temps additionnel)
**Si vous avez terminé en avance (avant les 1h30 de session) :**
- **Objectif :** Mise en pratique autonome.
- **Consignes :** Réfléchissez à un exemple réel ou une actualité récente liée au sujet de cette session. Discutez en groupe de la manière dont les concepts vus s'appliquent à cet exemple.
- **Correction :** Le mentor validera les réflexions et apportera son expertise.

## Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Concept clé** | À compléter selon la session |

## Ressources pour aller plus loin

* [ANSSI - Agence Nationale de la Sécurité des Systèmes d'Information](https://www.ssi.gouv.fr/)
* [Cybermalveillance.gouv.fr](https://www.cybermalveillance.gouv.fr/)
* [OWASP - Open Worldwide Application Security Project](https://owasp.org/)
