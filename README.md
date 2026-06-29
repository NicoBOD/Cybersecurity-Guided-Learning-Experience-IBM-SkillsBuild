# Cybersecurity Guided Learning Experience (GLE) — IBM SkillsBuild

Ce dépôt rassemble l'ensemble des livrables pédagogiques et organisationnels conçus pour les parcours de formation en cybersécurité, alignés avec la plateforme **IBM SkillsBuild**.

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
│       ├── parcours-A-8sessions/        # Parcours court (12 heures synchrone)
│       │   ├── plans-de-seance/         # Fiches d'animation pour le mentor (A_S01 à A_S08)
│       │   ├── supports-md/             # Supports théoriques de cours (800-1500 mots)
│       │   ├── slides/                  # Spécifications détaillées des diaporamas
│       │   ├── projet/                  # Énoncé du projet Capstone & grille d'évaluation
│       │   └── outils/                  # Banque de quiz, scripts de démo et messages types
│       │
│       └── parcours-B-20sessions/       # Parcours long (30 heures synchrone)
│           ├── plans-de-seance/         # Fiches d'animation pour le mentor (B_S01 à B_S20)
│           ├── supports-md/             # Supports théoriques de cours (800-1500 mots)
│           ├── projet/                  # Sujets (Capstone B, mini-projets) et grille
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
| **01** | Fondations de la cybersécurité & triade CIA | [Plan 📄](docs/ressources-pedagogiques/parcours-A-8sessions/plans-de-seance/A_S01_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-A-8sessions/supports-md/A_S01_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-A-8sessions/slides/A_S01_slides_spec.md) |
| **02** | Menaces, malwares & ingénierie sociale | [Plan 📄](docs/ressources-pedagogiques/parcours-A-8sessions/plans-de-seance/A_S02_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-A-8sessions/supports-md/A_S02_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-A-8sessions/slides/A_S02_slides_spec.md) |
| **03** | Réseaux informatiques & sécurité des architectures | [Plan 📄](docs/ressources-pedagogiques/parcours-A-8sessions/plans-de-seance/A_S03_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-A-8sessions/supports-md/A_S03_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-A-8sessions/slides/A_S03_slides_spec.md) |
| **04** | Sécurité physique, des données et du cloud | [Plan 📄](docs/ressources-pedagogiques/parcours-A-8sessions/plans-de-seance/A_S04_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-A-8sessions/supports-md/A_S04_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-A-8sessions/slides/A_S04_slides_spec.md) |
| **05** | RGPD, conformité et gouvernance des risques | [Plan 📄](docs/ressources-pedagogiques/parcours-A-8sessions/plans-de-seance/A_S05_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-A-8sessions/supports-md/A_S05_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-A-8sessions/slides/A_S05_slides_spec.md) |
| **06** | Vulnérabilités logicielles, mises à jour & score CVSS | [Plan 📄](docs/ressources-pedagogiques/parcours-A-8sessions/plans-de-seance/A_S06_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-A-8sessions/supports-md/A_S06_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-A-8sessions/slides/A_S06_slides_spec.md) |
| **07** | Gestion des accès, authentification forte & IAM | [Plan 📄](docs/ressources-pedagogiques/parcours-A-8sessions/plans-de-seance/A_S07_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-A-8sessions/supports-md/A_S07_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-A-8sessions/slides/A_S07_slides_spec.md) |
| **08** | Gestion d'incidents & Présentations du projet final | [Plan 📄](docs/ressources-pedagogiques/parcours-A-8sessions/plans-de-seance/A_S08_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-A-8sessions/supports-md/A_S08_support.md) | [Slides 📊](docs/ressources-pedagogiques/parcours-A-8sessions/slides/A_S08_slides_spec.md) |

*   **Projet Synthétique** : [Énoncé Capstone A 🏆](docs/ressources-pedagogiques/parcours-A-8sessions/projet/A_capstone.md) | [Grille d'évaluation 📐](docs/ressources-pedagogiques/parcours-A-8sessions/projet/A_grille_notation.md)
*   **Boîte à Outils** : [Banque de Quiz A 📝](docs/ressources-pedagogiques/parcours-A-8sessions/outils/A_banque_quiz.md) | [Scripts de Démos Techniques 💻](docs/ressources-pedagogiques/parcours-A-8sessions/outils/A_scripts_demo.md) | [Modèles de Messages Asynchrones 💬](docs/ressources-pedagogiques/parcours-A-8sessions/outils/A_messages.md)

---

### 🛡️ Parcours B : Approfondissement & Pratique Opérationnelle (20 Sessions)

| Session | Thématique / Module | Plan de séance | Support de Cours | Travaux Pratiques / Projets |
| :---: | :--- | :---: | :---: | :--- |
| **B01** | Fondations Cyber & Triade CIA | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S01_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S01_support.md) | Introduction théorique |
| **B02** | Menaces actives & Analyse de Malwares | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S02_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S02_support.md) | Études de cas ransomwares |
| **B03** | Ingénierie Sociale & Facteur Humain | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S03_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S03_support.md) | Analyse de mails d'hameçonnage |
| **B04** | Hygiène Cyber & Posture de Sécurité | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S04_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S04_support.md) | Lancement de la dynamique projet |
| **B05** | Protocoles Réseau & Modèle OSI | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S05_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S05_support.md) | Lancement **Mini-Projet 1 (Réseau Cible)** |
| **B06** | Sécurisation & Segmentation Réseau (VLAN, VPN) | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S06_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S06_support.md) | Conception de schéma de segmentation |
| **B07** | Configuration de Pare-feux (Firewalls/ACLs) | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S07_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S07_support.md) | Rédaction de règles de filtrage ACL |
| **B08** | Détection d'Intrusions (IDS/IPS, Wireshark) | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S08_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S08_support.md) | Restitution **Mini-Projet 1** |
| **B09** | IAM, Authentification Forte (MFA) & SSO | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S09_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S09_support.md) | Conception de politique d'accès |
| **B10** | Cryptographie (Chiffrement Symétrique/Asymétrique)| [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S10_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S10_support.md) | Lancement **Mini-Projet 2 (Data Protection)**|
| **B11** | Sécurité Cloud (SaaS, PaaS, IaaS, AWS/Azure) | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S11_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S11_support.md) | Modèles de responsabilité partagée |
| **B12** | Sauvegardes & Stratégie de Résilience 3-2-1 | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S12_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S12_support.md) | Restitution **Mini-Projet 2** |
| **B13** | OWASP Top 10 (Injections, XSS, Broken Auth) | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S13_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S13_support.md) | Lancement **Mini-Projet 3 (Audit Web App)** |
| **B14** | Cycle de Vie du Code Sécurisé (DevSecOps) | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S14_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S14_support.md) | Analyse de pipelines de CI/CD |
| **B15** | Gestion des Vulnérabilités & Scans (CVE, CVSS) | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S15_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S15_support.md) | Restitution **Mini-Projet 3** |
| **B16** | Supervision, SOC & Gestion des logs (SIEM) | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S16_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S16_support.md) | Lancement **Mini-Projet 4 (Incident Response)**|
| **B17** | Gouvernance Cyber, Politiques (PSSI) & ISO 27001 | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S17_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S17_support.md) | Analyse d'écarts de conformité |
| **B18** | Analyse de Risques & Méthode EBIOS RM Light | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S18_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S18_support.md) | Restitution **Mini-Projet 4** & Lancement Capstone B |
| **B19** | Réponse aux Incidents (Playbooks, Ransomware) | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S19_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S19_support.md) | Simulation de crise sur table (Tabletop Exercise) |
| **B20** | Clôture de la formation & Soutenance Capstone | [Plan 📄](docs/ressources-pedagogiques/parcours-B-20sessions/plans-de-seance/B_S20_plan.md) | [Support 📖](docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S20_support.md) | Soutenances orales devant jury |

*   **Sujets Projets intermédiaires** : [Les 4 Mini-projets 🛠️](docs/ressources-pedagogiques/parcours-B-20sessions/projet/B_miniprojets.md)
*   **Projet de Synthèse** : [Énoncé Capstone B 🏆](docs/ressources-pedagogiques/parcours-B-20sessions/projet/B_capstone.md) | [Grille d'évaluation 📐](docs/ressources-pedagogiques/parcours-B-20sessions/projet/B_grille_notation.md)
*   **Boîte à Outils** : [Banque de Quiz B 📝](docs/ressources-pedagogiques/parcours-B-20sessions/outils/B_banque_quiz.md) | [Scripts de Démos B 💻](docs/ressources-pedagogiques/parcours-B-20sessions/outils/B_scripts_demo.md) | [Modèles de Messages B 💬](docs/ressources-pedagogiques/parcours-B-20sessions/outils/B_messages.md)

---

## 🛠️ Documents Organisationnels (Fichiers de travail)
Les documents de cadrage du projet sont disponibles ci-dessous :
*   [Cahier des charges de la formation](docs/documents-de-travail/cahier-des-charges-gle-cybersecurite.md)
*   [Synthèse globale de transition](docs/documents-de-travail/summary_gle_cyber.md)
*   [Manifeste d'avancement détaillé](docs/documents-de-travail/00_MANIFESTE.md)
