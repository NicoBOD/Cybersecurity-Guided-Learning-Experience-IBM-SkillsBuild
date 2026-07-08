# Manifeste des Parcours GLE Cybersécurité
### Index Global, Suivi d'Avancement et Glossaire Commun

---

## 1. Organisation du projet & arborescence des fichiers

Le projet est structuré selon l'arborescence standardisée suivante :

```text
/parcours-A-8sessions/
   /plans-de-seance/      A_S01_plan.md … A_S08_plan.md
   /supports-md/          A_S01_support.md … A_S08_support.md
   /slides/               A_S01_slides.pptx (+ A_S01_slides_spec.md)
   /projet/               A_capstone.md
   /outils/               A_banque_quiz.md, A_scripts_demo.md, A_messages.md
/parcours-B-20sessions/
   /plans-de-seance/      B_S01_plan.md … B_S20_plan.md
   /supports-md/          B_S01_support.md … B_S20_support.md
   /slides/               B_S01_slides.pptx (+ B_S01_slides_spec.md)
   /projet/               B_capstone.md, B_miniprojets.md
   /outils/               B_banque_quiz.md, B_scripts_demo.md, B_messages.md
/00_MANIFESTE.md          (Index global + état d'avancement + glossaire commun)
```

Toutes les productions respecteront les conventions de nommage `<Parcours>_S<NN>_<type>.<ext>` avec des titres de H1 explicites à l'intérieur de chaque fichier.

---

## 2. Index & Cartographie des Parcours

### 2.1 Parcours A — 8 sessions (Fondamentaux + Atelier d'Audit Final)
*Cible : Certification de type « Cybersecurity Fundamentals ». Charge self-paced estimée : 1h30 à 3h par session (~12h à 24h au total).*

* **A1 — Découverte de la cybersécurité & paysage des menaces**
  * **Objectifs clés** : Définir la triade CIA ; situer l'offense par rapport à la défense ; identifier les principaux acteurs de menace et leurs motivations ; expliquer l'importance de la cybersécurité à l'échelle personnelle et de l'entreprise.
  * **Prérequis** : Aucun.
  * **Lien de progression** : Pose les fondements conceptuels et la terminologie de base nécessaires pour l'ensemble du parcours.
* **A2 — Menaces, attaques & ingénierie sociale**
  * **Objectifs clés** : Classifier les familles de logiciels malveillants (*malware*) ; identifier les techniques d'hameçonnage (*phishing*) et d'ingénierie sociale ; décrire les grandes étapes de la chaîne d'attaque (*cyber kill chain*) ; appliquer les réflexes de vigilance immédiate face aux sollicitations suspectes.
  * **Prérequis** : A1.
  * **Lien de progression** : Explique la nature des menaces courantes, ce qui justifie les mesures de défense techniques (A3) et humaines (A4).
* **A3 — Sécurité des systèmes & réseaux**
  * **Objectifs clés** : Expliquer le fonctionnement d'un pare-feu (*firewall*) et d'un VPN ; distinguer les protocoles sécurisés (HTTPS, SSH) des non sécurisés (HTTP, Telnet) ; expliquer le concept de segmentation réseau ; identifier les composants réseaux d'entreprise.
  * **Prérequis** : A1, A2.
  * **Lien de progression** : Met en œuvre les protections périmétriques et systèmes, qui se prolongeront sur les données et identités dans la session suivante.
* **A4 — Sécurité du cloud, des données & des identités**
  * **Objectifs clés** : Appliquer les principes d'authentification et d'accès (IAM, MFA) ; expliquer le principe du chiffrement symétrique et asymétrique ; distinguer les périmètres du modèle de responsabilité partagée dans le *cloud* ; concevoir une stratégie de sauvegarde simple.
  * **Prérequis** : A3.
  * **Lien de progression** : Déplace le focus technique de l'infrastructure réseau vers les identités logiques et les actifs de données.
* **A5 — Gouvernance, risque, conformité & vie privée**
  * **Objectifs clés** : Décrire le rôle de la GRC ; identifier les référentiels majeurs (ISO 27001, NIST CSF) ; évaluer un risque simple (impact/vraisemblance) ; expliquer les bases réglementaires de la protection des données personnelles (RGPD).
  * **Prérequis** : A1 à A4.
  * **Lien de progression** : Structure les mesures techniques acquises dans un cadre de gestion organisationnel, méthodologique et juridique.
* **A6 — Opérations de sécurité & gestion des vulnérabilités**
  * **Objectifs clés** : Expliquer le rôle d'un SOC et d'un SIEM ; distinguer un scan de vulnérabilités d'un test d'intrusion ; interpréter un score CVSS pour prioriser les correctifs ; appliquer le processus de gestion des vulnérabilités.
  * **Prérequis** : A3, A5.
  * **Lien de progression** : Initie les apprenants à la phase opérationnelle ("run") et de surveillance active des systèmes.
* **A7 — Réponse aux incidents & introduction au forensics**
  * **Objectifs clés** : Dérouler les phases du cycle de réponse sur incident ; analyser des traces/logs simples ; expliquer le cadre éthique et légal du piratage éthique ; concevoir un plan d'urgence de communication post-incident.
  * **Prérequis** : A6.
  * **Lien de progression** : Clôture le cycle opérationnel d'apprentissage (prévenir, détecter, réagir, analyser) et prépare le projet de fin d'études.
* **A8 — Grand Atelier d'Audit & Synthèse**
  * **Objectifs clés** : Résoudre l'Atelier d'Audit Interactif MedDistri en direct ; évaluer la posture et la résilience cyber de la PME ; décider collectivement des priorités de remédiation ; valider les acquis du parcours.
  * **Prérequis** : A1 à A7.
  * **Lien de progression** : Consolidateur final du parcours évaluant l'autonomie et l'intégration des compétences.

---

### 2.2 Parcours B — 20 sessions (Fondations + Approfondissements + Pratique + Projets)
*Cible : Certification de type « Cybersecurity Certificate ». Charge self-paced estimée : 1h30 à 2h30 par session (~30h à 50h au total).*

#### Module A — Fondations (S1–S4)
* **B1 : Introduction à la cybersécurité & triade CIA**
  * **Objectifs** : Définir la triade CIA avec des exemples réels ; expliquer les impacts business des cyberattaques ; identifier les opportunités professionnelles du secteur cyber.
  * **Prérequis** : Aucun.
  * **Lien** : Socle terminologique et conceptuel commun.
* **B2 : Paysage des menaces & acteurs**
  * **Objectifs** : Distinguer les profils d'attaquants (cybercriminels, États, hacktivistes, menaces internes) ; analyser leurs motivations ; identifier les sources de veille (*threat intelligence*).
  * **Prérequis** : B1.
  * **Lien** : Explique qui attaque et pourquoi, avant d'aborder les méthodes dans la session suivante.
* **B3 : Types d'attaques & vecteurs**
  * **Objectifs** : Classifier les *malwares* ; expliquer la chaîne d'attaque (*cyber kill chain*) ; appliquer le framework MITRE ATT&CK pour décortiquer une menace ; expliquer les attaques par déni de service (DoS) et attaques web de base.
  * **Prérequis** : B1, B2.
  * **Lien** : Introduit la technique de l'attaquant pour justifier les mesures préventives et la sensibilisation (B4).
* **B4 : Ingénierie sociale & facteur humain**
  * **Objectifs** : Repérer les leviers psychologiques de la manipulation ; différencier les canaux de phishing (e-mail, téléphone, SMS) ; concevoir une campagne de sensibilisation interne ; adopter des règles d'hygiène numérique personnelle.
  * **Prérequis** : B3.
  * **Lien** : Traite la dimension humaine et boucle le module de fondation avant la technique réseau.

#### Module B — Systèmes & réseaux (S5–S8)
* **B5 : Fondamentaux réseau pour la sécurité**
  * **Objectifs** : Expliquer les modèles OSI et TCP/IP sous l'angle de la sécurité ; identifier les protocoles clés (DNS, DHCP, ARP, ICMP) et ports courants ; lire une adresse IP et un en-tête de paquet réseau simple.
  * **Prérequis** : Module A.
  * **Lien** : Fournit le bagage infrastructurel minimal requis pour le filtrage (B6).
* **B6 : Défenses réseau**
  * **Objectifs** : Expliquer le fonctionnement des pare-feux (filtrage simple vs NGFW) ; différencier IDS et IPS ; modéliser une architecture réseau avec DMZ et segmentation logique.
  * **Prérequis** : B5.
  * **Lien** : Met en place les barrières de protection des flux réseaux, prolongées par le chiffrement des communications (B7).
* **B7 : Communications sécurisées**
  * **Objectifs** : Expliquer le rôle de TLS/SSL dans les protocoles sécurisés (HTTPS, etc.) ; comparer les technologies VPN (IPsec vs OpenVPN/WireGuard) ; identifier les vulnérabilités Wi-Fi et configurer un chiffrement WPA3.
  * **Prérequis** : B6.
  * **Lien** : Sécurise les flux de données en transit avant d'aborder les hôtes d'extrémité (B8).
* **B8 : Durcissement des systèmes & endpoints**
  * **Objectifs** : Appliquer le moindre privilège sur un OS ; lister les étapes clés du durcissement d'un serveur/poste ; comparer antivirus traditionnel et EDR ; concevoir un processus de gestion des patchs.
  * **Prérequis** : B5 à B7.
  * **Lien** : Finalise le module infrastructure. **Associe le Mini-projet 1 (Architecture réseau sécurisée).** Ouvre sur le contrôle d'accès logique (Module C).

#### Module C — Identités, cloud & données (S9–S12)
* **B9 : Gestion des identités et des accès (IAM)**
  * **Objectifs** : Expliquer les étapes IAM (identification, authentification, autorisation, audit) ; comparer les modèles d'accès (RBAC, ABAC) ; concevoir des politiques MFA et SSO robustes.
  * **Prérequis** : Module B.
  * **Lien** : Règle le droit d'accès aux actifs logiques, qui s'appuient sur la cryptographie (B10).
* **B10 : Cryptographie essentielle**
  * **Objectifs** : Expliquer le chiffrement symétrique et asymétrique ; utiliser des fonctions de hachage pour assurer l'intégrité ; décrire le fonctionnement d'une PKI et des certificats X.509.
  * **Prérequis** : B9.
  * **Lien** : Apporte le formalisme mathématique sous-jacent nécessaire pour le cloud (B11) et les données (B12).
* **B11 : Sécurité du cloud**
  * **Objectifs** : Analyser le modèle de responsabilité partagée (IaaS, PaaS, SaaS) ; identifier les risques majeurs de mauvaise configuration cloud ; sécuriser des politiques IAM sur un tenant cloud public.
  * **Prérequis** : B9, B10.
  * **Lien** : Transpose les concepts d'accès et de cryptographie au cloud, milieu d'hébergement des données (B12).
* **B12 : Sécurité & confidentialité des données**
  * **Objectifs** : Modéliser un plan de classification des données ; configurer du chiffrement au repos et en transit ; décrire le fonctionnement d'un DLP ; appliquer la règle 3-2-1 pour des sauvegardes anti-ransomware.
  * **Prérequis** : B9 à B11.
  * **Lien** : Clôture le module données. **Associe le Mini-projet 2 (Plan de protection des données).** Introduit le cadre méthodologique global (Module D).

#### Module D — Gouvernance, risque & conformité (S13–S15)
* **B13 : Gouvernance & cadres de sécurité**
  * **Objectifs** : Expliquer l'architecture et les rôles d'une PSSI ; présenter de manière vulgarisée les cadres ISO 27001 et NIST CSF ; distinguer les responsabilités du RSSI dans la gouvernance d'entreprise.
  * **Prérequis** : Modules A à C.
  * **Lien** : Donne les lignes directrices organisationnelles, prélude indispensable à l'analyse de risque (B14).
* **B14 : Gestion des risques**
  * **Objectifs** : Articuler menace, vulnérabilité, impact et probabilité ; rédiger un registre des risques pragmatique ; classer et justifier les options de traitement (réduire, transférer, éviter, accepter).
  * **Prérequis** : B13.
  * **Lien** : Fournit les critères de choix d'actions réglementaires et opérationnelles (B15).
* **B15 : Conformité & réglementations vie privée**
  * **Objectifs** : Expliquer les devoirs RGPD d'un organisme ; identifier les sanctions et le rôle de la CNIL ; distinguer le rôle du DPO ; auditer la conformité d'une politique de confidentialité.
  * **Prérequis** : B13, B14.
  * **Lien** : Clôture le module GRC. **Associe le Mini-projet 3 (Évaluation des risques + ébauche de PSSI).** Bascule vers la surveillance continue (Module E).

#### Module E — Opérations, détection & réponse (S16–S19)
* **B16 : Centre des opérations de sécurité (SOC) & supervision**
  * **Objectifs** : Décrire l'organisation interne et les rôles (L1, L2, L3) d'un SOC ; expliquer la remontée d'alertes et le traitement des faux positifs ; interpréter les métriques clés de performance d'un SOC (MTTD, MTTR).
  * **Prérequis** : Modules B, C.
  * **Lien** : Cadre humain et fonctionnel de la détection, avant l'outil technologique principal (B17).
* **B17 : SIEM, journalisation & détection**
  * **Objectifs** : Expliquer le fonctionnement d'un SIEM (corrélation, normalisation) ; cibler les logs d'intérêt pour la sécurité ; analyser des lignes de logs d'événements pour isoler une anomalie d'attaque.
  * **Prérequis** : B16.
  * **Lien** : Rentre dans le dur de l'analyse opérationnelle. **Associe le Mini-projet 4 (Analyse de logs de SIEM fictif).** Initie à la prévention corrective (B18).
* **B18 : Gestion des vulnérabilités**
  * **Objectifs** : Expliquer les phases de gestion des vulnérabilités ; faire la différence entre CVE et CWE ; interpréter un score CVSS ; structurer et prioriser un plan de remédiation technique.
  * **Prérequis** : B17.
  * **Lien** : Réduit la surface d'attaque en continu, prélude au traitement des attaques subies et à l'investigation (B19).
* **B19 : Réponse aux incidents & bases du forensics**
  * **Objectifs** : Expliquer le cycle de réponse à incident (SANS/NIST) ; énoncer les règles de préservation des preuves numériques (chaîne de contrôle) ; définir le cadre juridique et méthodologique du pentest ; rédiger un rapport d'incident préliminaire.
  * **Prérequis** : B17, B18.
  * **Lien** : Clôture le module opérations. Prépare à l'exercice d'intégration global (B20).

#### Module F — Grand Atelier d'Audit (S20)
* **B20 : Grand Atelier d'Audit & Clôture**
  * **Objectifs** : Résoudre collectivement le cas d'audit MedDistri et simuler une gestion de crise Ransomware en direct ; décider des actions de remédiation par des votes interactifs ; valider la fin de formation.
  * **Prérequis** : B1 à B19.
  * **Lien** : Consolidateur et évaluateur final du certificat de formation.

---

## 3. Tableau d'avancement (Phase 2 : Production Supports Parcours A)

*Statuts autorisés : `À faire`, `En cours (Phase X)`, `Produit (En validation)`, `Validé`.*

### 3.1 Outils communs et Manifeste
| Fichier | Type | Description / Thème | Statut |
|---|---|---|---|
| `00_MANIFESTE.md` | Manifeste global | Index, avancement & glossaire commun | **En cours (Phase 5)** |

### 3.2 Livrables Parcours A (8 sessions)
| Session | Plan de séance | Support de cours (.MD) | Spec Slides (.MD) | Deck PPTX |
|---|---|---|---|---|
| **A1** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **A2** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **A3** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **A4** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **A5** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **A6** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **A7** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **A8** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **Projet** | `A_capstone.md` : 🟡 Produit (En validation) | - | - | - |
| **Outils** | `A_banque_quiz.md` : 🟡 Produit (En validation) | `A_scripts_demo.md` : 🟡 Produit (En validation) | `A_messages.md` : 🟡 Produit (En validation) | - |

### 3.3 Livrables Parcours B (20 sessions)
| Session | Plan de séance | Support de cours (.MD) | Spec Slides (.MD) | Deck PPTX |
|---|---|---|---|---|
| **B1** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B2** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B3** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B4** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B5** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B6** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B7** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B8** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B9** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B10** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B11** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B12** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B13** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B14** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B15** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B16** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B17** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B18** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B19** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **B20** | 🟡 Produit (En validation) | 🟡 Produit (En validation) | 🟡 Produit (En validation) | ⬜ À faire |
| **Projet** | `B_capstone.md` : 🟡 Produit (En validation) | `B_miniprojets.md` : 🟡 Produit (En validation) | - | - |
| **Outils** | `B_banque_quiz.md` : 🟡 Produit (En validation) | `B_scripts_demo.md` : 🟡 Produit (En validation) | `B_messages.md` : 🟡 Produit (En validation) | - |

---

## 4. Amorce du Glossaire Commun (Technique & Pédagogique)

*Ce glossaire recense les termes techniques en anglais utilisés dans les parcours, avec leur glose ou définition en français, assurant une parfaite cohérence sémantique d'un fichier à l'autre.*

* **CIA Triad** (Triade CIA) — Modèle fondamental de sécurité reposant sur trois piliers : Confidentialité (*Confidentiality*), Intégrité (*Integrity*) et Disponibilité (*Availability*).
* **Phishing** (Hameçonnage) — Technique d'ingénierie sociale consistant à usurper l'identité d'un tiers de confiance pour inciter une victime à divulguer des données sensibles ou exécuter une action malveillante.
* **Firewall** (Pare-feu) — Équipement réseau filtrant les flux de communication entrants et sortants selon des règles de sécurité prédéfinies.
* **VPN** (Réseau Privé Virtuel) — Tunnel chiffré permettant de sécuriser les flux de données transitant via un réseau public non sûr (comme Internet).
* **MFA** (Authentification Multifacteur) — Mécanisme de contrôle d'accès exigeant la validation d'au moins deux facteurs de preuve distincts pour confirmer une identité.
* **IAM** (Gestion des Identités et des Accès) — Cadre de processus et d'outils garantissant que les bons utilisateurs accèdent aux bonnes ressources, pour de bonnes raisons et au bon moment.
* **SOC** (Centre des Opérations de Sécurité) — Équipe opérationnelle chargée de surveiller, détecter et analyser les menaces de sécurité sur un système d'information en continu.
* **SIEM** (Gestion des Informations et des Événements de Sécurité) — Solution logicielle centralisant et analysant les journaux d'événements (logs) de sécurité pour y détecter des activités suspectes.
* **Vulnerability Scanning** (Scan de vulnérabilités) — Processus automatisé d'analyse d'un système pour y répertorier et évaluer les faiblesses logicielles ou de configuration connues.
* **Penetration Testing / Pentest** (Test d'intrusion) — Simulation d'attaque cyber autorisée et encadrée sur un système cible pour évaluer la robustesse de ses défenses en conditions réelles.
* **Forensics** (Investigation numérique) — Discipline scientifique et légale consistant à collecter, préserver et analyser les preuves numériques après une cyberattaque ou un incident.
* **Guided Learning Experience (GLE)** (Expérience d'apprentissage guidée) — Modèle d'apprentissage hybride associant phases d'auto-apprentissage à distance (*self-paced*) et ateliers collectifs synchrones en direct animés par un mentor.
