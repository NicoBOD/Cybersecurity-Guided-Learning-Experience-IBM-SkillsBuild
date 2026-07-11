# Cybersecurity Guided Learning Experience (GLE) — IBM SkillsBuild

Ce dépôt rassemble l'ensemble des livrables pédagogiques et organisationnels conçus pour les parcours de formation en cybersécurité, alignés avec la plateforme **IBM SkillsBuild**. Les sessions synchrones sont animées en webinaire **Livestorm** (grand groupe), avec des interactions via sondages et chat.

> [!TIP]
> Ce dépôt est également consultable sous forme de site web interactif moderne et agréable à l'adresse suivante : **[https://cybersecurite.bodaine.fr](https://cybersecurite.bodaine.fr)**.

---

## 📂 Structure du Dépôt

Le dépôt est organisé pour distinguer les documents de cadrage stratégique (fichiers de travail) et les ressources pédagogiques finales destinées à l'animation des parcours.

```text
.
├── docs/                                # Dossier racine de la documentation
│   ├── index.md                         # Page d'accueil du site de documentation
│   ├── documents-de-travail/            # Fichiers internes d'organisation et de cadrage
│   │   ├── cahier-des-charges-gle-cybersecurite.md
│   │   ├── summary_gle_cyber.md         # Synthèse globale de la transition
│   │   ├── message-amorcage.md          # Document d'amorce initial
│   │   └── 00_MANIFESTE.md              # Index détaillé d'avancement des contenus
│   │
│   └── ressources-pedagogiques/         # Contenus animés (Apprenants & Mentors)
│       ├── parcours-A-8sessions/        # Parcours court : 8 sessions de 1h30 (12 h synchrones)
│       │   ├── plans-de-seance/         # Scripts d'animation minutés pour le mentor (A_S01 à A_S08)
│       │   ├── supports-md/             # Supports théoriques de cours enrichis
│       │   ├── slides/                  # Spécifications détaillées des diaporamas (Markdown)
│       │   ├── projet/                  # Atelier d'Audit Interactif final (A_capstone.md)
│       │   └── outils/                  # Banque de quiz, scripts de démo et messages types
│       │
│       └── parcours-B-20sessions/       # Parcours long : 20 sessions de 1h30 (30 h synchrones)
│           ├── plans-de-seance/         # Scripts d'animation minutés pour le mentor (B_S01 à B_S20)
│           ├── supports-md/             # Supports théoriques de cours enrichis
│           ├── slides/                  # Spécifications détaillées des diaporamas (Markdown)
│           ├── projet/                  # Ateliers de synthèse (B_miniprojets.md) & Grand Atelier d'Audit (B_capstone.md)
│           └── outils/                  # Banque de quiz, scripts de démo et messages types
├── mkdocs.yml                           # Fichier de configuration du site
├── README.md                            # Ce guide d'accueil
└── .github/
    └── workflows/
        └── deploy-documentation.yml     # CI/CD pour la publication automatique sur GitHub Pages
```

---

## 🗺️ Table des Matières Interactive des Ressources

### 🎓 Parcours A : Fondations Cyber & Hygiène de l'Entreprise (8 Sessions)

| Session | Titre / Thématique | Plan de séance | Support de Cours | Diaporama (Specs) |
| :---: | :--- | :---: | :---: | :---: |
| **01** | Découverte de la Cybersécurité & Paysage des Menaces | [Plan 📄](docs/ressources-pedagogiques/parcours-A-8sessions/plans-de-seance/A_S01_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-A-8sessions/supports-md/A_S01_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-A-8sessions/slides/A_S01_slides_spec.md) |
| **02** | Menaces, Attaques & Ingénierie Sociale | [Plan 📄](docs/ressources-pedagogiques/parcours-A-8sessions/plans-de-seance/A_S02_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-A-8sessions/supports-md/A_S02_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-A-8sessions/slides/A_S02_slides_spec.md) |
| **03** | Sécurité des Systèmes & Réseaux | [Plan 📄](docs/ressources-pedagogiques/parcours-A-8sessions/plans-de-seance/A_S03_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-A-8sessions/supports-md/A_S03_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-A-8sessions/slides/A_S03_slides_spec.md) |
| **04** | Sécurité du Cloud, des Données & des Identités | [Plan 📄](docs/ressources-pedagogiques/parcours-A-8sessions/plans-de-seance/A_S04_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-A-8sessions/supports-md/A_S04_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-A-8sessions/slides/A_S04_slides_spec.md) |
| **05** | Gouvernance, Risque, Conformité & Vie Privée | [Plan 📄](docs/ressources-pedagogiques/parcours-A-8sessions/plans-de-seance/A_S05_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-A-8sessions/supports-md/A_S05_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-A-8sessions/slides/A_S05_slides_spec.md) |
| **06** | Opérations de Sécurité & Gestion des Vulnérabilités | [Plan 📄](docs/ressources-pedagogiques/parcours-A-8sessions/plans-de-seance/A_S06_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-A-8sessions/supports-md/A_S06_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-A-8sessions/slides/A_S06_slides_spec.md) |
| **07** | Réponse aux Incidents & Introduction au Forensics | [Plan 📄](docs/ressources-pedagogiques/parcours-A-8sessions/plans-de-seance/A_S07_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-A-8sessions/supports-md/A_S07_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-A-8sessions/slides/A_S07_slides_spec.md) |
| **08** | Grand Atelier d'Audit & Synthèse | [Plan 📄](docs/ressources-pedagogiques/parcours-A-8sessions/plans-de-seance/A_S08_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-A-8sessions/supports-md/A_S08_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-A-8sessions/slides/A_S08_slides_spec.md) |

*   **Atelier de Synthèse** : [Atelier d'Audit Interactif MedDistri 🏆](docs/ressources-pedagogiques/parcours-A-8sessions/projet/A_capstone.md)
*   **Boîte à Outils** : [Banque de Quiz A 📝](docs/ressources-pedagogiques/parcours-A-8sessions/outils/A_banque_quiz.md) | [Scripts de Démos Techniques 💻](docs/ressources-pedagogiques/parcours-A-8sessions/outils/A_scripts_demo.md) | [Modèles de Messages Asynchrones 💬](docs/ressources-pedagogiques/parcours-A-8sessions/outils/A_messages.md)

---

### 🛡️ Parcours B : Approfondissement & Pratique Opérationnelle (20 Sessions)

| Session | Thématique / Module | Plan de séance | Support de Cours | Diaporama (Specs) | Jalon / Atelier |
| :---: | :--- | :---: | :---: | :---: | :--- |
| **B01** | Introduction & Triade CIA | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S01_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S01_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S01_slides_spec.md) | Introduction théorique |
| **B02** | Paysage des Menaces & Acteurs | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S02_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S02_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S02_slides_spec.md) | Études de cas ransomwares |
| **B03** | Types d'Attaques & Vecteurs | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S03_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S03_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S03_slides_spec.md) | Analyse de la kill chain |
| **B04** | Ingénierie Sociale & Facteur Humain | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S04_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S04_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S04_slides_spec.md) | Analyse de mails d'hameçonnage |
| **B05** | Fondamentaux Réseau | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S05_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S05_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S05_slides_spec.md) | Lecture de paquets & ports |
| **B06** | Défenses Réseau | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S06_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S06_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S06_slides_spec.md) | Conception de schéma de segmentation |
| **B07** | Communications Sécurisées | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S07_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S07_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S07_slides_spec.md) | Comparatif VPN & TLS |
| **B08** | Durcissement Systèmes & Endpoints | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S08_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S08_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S08_slides_spec.md) | **Atelier de Synthèse 1 (Réseau sécurisé)** |
| **B09** | Gestion des Identités & des Accès (IAM) | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S09_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S09_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S09_slides_spec.md) | Conception de politique d'accès |
| **B10** | Cryptographie Essentielle | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S10_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S10_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S10_slides_spec.md) | Chiffrement & hachage en pratique |
| **B11** | Sécurité du Cloud | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S11_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S11_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S11_slides_spec.md) | Modèles de responsabilité partagée |
| **B12** | Sécurité & Confidentialité des Données | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S12_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S12_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S12_slides_spec.md) | **Atelier de Synthèse 2 (Protection des données)** |
| **B13** | Gouvernance & Cadres de Sécurité | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S13_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S13_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S13_slides_spec.md) | Vulgarisation ISO 27001 / NIST CSF |
| **B14** | Gestion des Risques | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S14_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S14_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S14_slides_spec.md) | Registre des risques pragmatique |
| **B15** | Conformité & Vie Privée | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S15_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S15_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S15_slides_spec.md) | **Atelier de Synthèse 3 (Risques & PSSI)** |
| **B16** | SOC & Supervision | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S16_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S16_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S16_slides_spec.md) | Rôles L1/L2/L3 & métriques SOC |
| **B17** | Outils SIEM & Analyse de Logs | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S17_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S17_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S17_slides_spec.md) | **Atelier de Synthèse 4 (Analyse de logs)** |
| **B18** | Introduction à la Réponse aux Incidents | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S18_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S18_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S18_slides_spec.md) | Cycle NIST/SANS & préservation des preuves |
| **B19** | Simulation de Crise Cyber (Tabletop) | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S19_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S19_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S19_slides_spec.md) | Simulation de crise interactive (sondages) |
| **B20** | Grand Atelier d'Audit & Clôture | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S20_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S20_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-B-20sessions/slides/B_S20_slides_spec.md) | Grand Atelier d'Audit MedDistri (Avancé) |

*   **Ateliers intermédiaires** : [Les 4 Ateliers de Synthèse Pratiques 🛠️](docs/ressources-pedagogiques/parcours-B-20sessions/projet/B_miniprojets.md)
*   **Atelier de Synthèse Final** : [Grand Atelier d'Audit MedDistri (Avancé) 🏆](docs/ressources-pedagogiques/parcours-B-20sessions/projet/B_capstone.md)
*   **Boîte à Outils** : [Banque de Quiz B 📝](docs/ressources-pedagogiques/parcours-B-20sessions/outils/B_banque_quiz.md) | [Scripts de Démos B 💻](docs/ressources-pedagogiques/parcours-B-20sessions/outils/B_scripts_demo.md) | [Modèles de Messages B 💬](docs/ressources-pedagogiques/parcours-B-20sessions/outils/B_messages.md)

---

## 🛠️ Documents Organisationnels (Fichiers de travail)
Les documents de cadrage du projet sont disponibles ci-dessous :
*   [Cahier des charges de la formation](docs/documents-de-travail/cahier-des-charges-gle-cybersecurite.md)
*   [Synthèse globale de transition](docs/documents-de-travail/summary_gle_cyber.md)
*   [Manifeste d'avancement détaillé](docs/documents-de-travail/00_MANIFESTE.md)
