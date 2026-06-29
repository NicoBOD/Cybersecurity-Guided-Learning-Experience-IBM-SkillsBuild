# État d'avancement du projet — Ingénierie Pédagogique GLE Cybersécurité

Ce document résume les travaux réalisés et définit la feuille de route pour la poursuite de la conception des parcours de formation en cybersécurité pour la Global Learning Enterprise (GLE).

---

## 1. Contexte du projet
La Global Learning Enterprise (GLE) développe deux parcours de formation en cybersécurité :
1.  **Parcours A (Accompagnement court)** : 8 sessions de 2 heures (total 16 heures).
2.  **Parcours B (Accompagnement long)** : 20 sessions de 1h30 (total 30 heures).

Les contenus doivent respecter une structure pédagogique rigoureuse pour adultes (méthodologies actives, vulgarisation des concepts avec analogies, exercices pratiques exploitables, quiz de validation des acquis, et auto-apprentissage guidé sur IBM SkillsBuild).

---

## 2. État d'avancement des livrables

### 📂 Parcours A (8 sessions) — 100 % Finalisé
*   **Plans de séance** : Les 8 plans de séance complets ont été rédigés et validés dans `/home/user/Documents/Antigravity/parcours-A-8sessions/plans-de-seance/`.
*   **Supports de cours (.MD)** : Les 8 supports de cours correspondants ont été rédigés selon le Gabarit 5.2 et validés dans `/home/user/Documents/Antigravity/parcours-A-8sessions/supports-md/`.

### 📂 Parcours B (20 sessions) — Supports de cours 100 % Rédigés
Le parcours B est divisé en plusieurs modules thématiques (Fondations, Systèmes & réseaux, Sécurité applicative, Gestion des risques, et Opérations).
*   **Plans de séance** : Les plans de séance de B01 à B20 ont été créés et stockés dans `/home/user/Documents/Antigravity/parcours-B-20sessions/plans-de-seance/`.
*   **Supports de cours (.MD)** :
    *   **Lot 1 (Session B01 à B04 - Fondations)** : Rédigés et stockés dans `/home/user/Documents/Antigravity/parcours-B-20sessions/supports-md/`.
        *   `B_S01_support.md` (Introduction à la cybersécurité & triade CIA)
        *   `B_S02_support.md` (Paysage des menaces & acteurs)
        *   `B_S03_support.md` (Types d'attaques & vecteurs)
        *   `B_S04_support.md` (Ingénierie sociale & facteur humain)
    *   **Lot 2 (Session B05 à B08 - Systèmes & réseaux)** : Rédigés et stockés dans `/home/user/Documents/Antigravity/parcours-B-20sessions/supports-md/`.
        *   `B_S05_support.md` (Fondations réseau pour la sécurité)
        *   `B_S06_support.md` (Défenses réseau)
        *   `B_S07_support.md` (Communications sécurisées)
        *   `B_S08_support.md` (Durcissement des systèmes & endpoints)
    *   **Lot 3 (Session B09 à B12 - Identités, cloud & données)** : Rédigés et stockés dans `/home/user/Documents/Antigravity/parcours-B-20sessions/supports-md/`.
        *   `B_S09_support.md` (Gestion des identités et des accès (IAM))
        *   `B_S10_support.md` (Cryptographie essentielle)
        *   `B_S11_support.md` (Sécurité du cloud)
        *   `B_S12_support.md` (Sécurité & confidentialité des données)
    *   **Lot 4 (Session B13 à B16 - Gouvernance, risque & conformité)** : Rédigés et stockés dans `/home/user/Documents/Antigravity/parcours-B-20sessions/supports-md/`.
        *   `B_S13_support.md` (Gouvernance & cadres de sécurité)
        *   `B_S14_support.md` (Gestion des risques)
        *   `B_S15_support.md` (Conformité & réglementations vie privée - Validation Mini-projet 3)
        *   `B_S16_support.md` (Centre des opérations de sécurité (SOC) & supervision)
    *   **Lot 5 (Session B17 à B20 - Opérations, détection & réponse)** : Rédigés et stockés dans `/home/user/Documents/Antigravity/parcours-B-20sessions/supports-md/`.
        *   `B_S17_support.md` (Outils SIEM & Analyse de logs)
        *   `B_S18_support.md` (Introduction à la réponse aux incidents)
        *   `B_S19_support.md` (Simulation de crise cyber - Tabletop exercise)
        *   `B_S20_support.md` (Soutenance finale & Clôture - Validation Capstone Project B)

### 📝 Manifeste du projet — 100 % Mis à jour
Le fichier `00_MANIFESTE.md` à la racine répertorie la structure globale du projet, les fichiers associés et l'état de complétion de chaque livrable. Il a été mis à jour après la création de chaque lot de documents.

---

## 3. Structure des fichiers dans le Workspace
```text
/home/user/Documents/Antigravity/
├── 00_MANIFESTE.md                               # Manifeste de suivi du projet
├── cahier-des-charges-gle-cybersecurite.md       # Spécifications de la GLE
├── summary_gle_cyber.md                           # Présent résumé de transition
├── parcours-A-8sessions/
│   ├── outils/                                    # A_banque_quiz.md, A_scripts_demo.md, A_messages.md
│   ├── plans-de-seance/                           # A01_plan.md à A08_plan.md
│   ├── projet/                                    # A_capstone.md, A_grille_notation.md
│   └── supports-md/                               # A01_support.md à A08_support.md
└── parcours-B-20sessions/
    ├── outils/                                    # B_banque_quiz.md, B_scripts_demo.md, B_messages.md
    ├── plans-de-seance/                           # B01_plan.md à B20_plan.md
    ├── projet/                                    # B_capstone.md, B_miniprojets.md, B_grille_notation.md
    └── supports-md/                               # B01_support.md à B20_support.md (Tous les supports rédigés)
```

---

## 4. Prochaines étapes
1.  **Revue globale finale et validation** de l'ensemble de la formation (Parcours A et B) par le commanditaire.
2.  **Vérification de la cohérence de la terminologie** technique franco-anglaise entre les plans de séance, les supports de cours et la banque de quiz.
3.  **Contrôle qualité final** sur l'alignement des liens IBM SkillsBuild recommandés en auto-apprentissage.
