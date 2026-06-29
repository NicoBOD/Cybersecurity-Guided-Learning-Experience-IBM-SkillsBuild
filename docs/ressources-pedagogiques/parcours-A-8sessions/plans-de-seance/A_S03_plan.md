# Parcours A — Session 03 : Sécurité des systèmes & réseaux
Module : Réseaux & Systèmes  |  Durée : 90 min  |  Parcours : A 8 sessions

## Objectifs pédagogiques (4, verbes d'action)
- **Expliquer** le rôle de filtrage d'un pare-feu (*firewall*) et son utilité pour bloquer les connexions non autorisées.
- **Identifier** les cas d'usage d'un réseau privé virtuel (VPN) pour sécuriser la confidentialité des communications sur Internet.
- **Distinguer** le trafic chiffré (HTTPS, SSH) du trafic non chiffré (HTTP, Telnet) et expliquer le risque d'interception (*sniffing*).
- **Proposer** un plan de segmentation réseau simple (LAN, Wi-Fi Invités, Zone Démilitarisée - DMZ) pour isoler les composants critiques d'une entreprise.

## Prérequis
- Sessions précédentes : A1, A2.
- Self-paced AVANT la séance (~90 min) : Module SkillsBuild sur les bases du fonctionnement d'Internet (adresses IP, ports, notion de routeur et de commutateur/switch).

## Découpage temporel (90 min)
| Min | Segment | Format | Support |
|-----|---------|--------|---------|
| 0–5 | Accueil, logistique & présentation de la séance | Plénière | Slide titre & objectifs |
| 5–15 | Mini-sondage : "Sécurité Wi-Fi public" + Rappel Kill Chain | Interactif | Outil de sondage en ligne |
| 15–35 | Apport de contenu 1 : Pare-feu (firewall) & VPN (Réseau Privé Virtuel) | Exposé illustré | Slides concepts et analogies (frontière, tunnel) |
| 35–50 | Activité 1 : Audit et remédiation réseau d'une PME | Travail en groupe (3-4) | Fiche d'activité A_S03 (Schéma réseau) |
| 50–70 | Apport de contenu 2 : Protocoles (HTTPS vs HTTP) & principes de segmentation | Exposé interactif | Slides protocoles, ports & zones réseau |
| 70–85 | Démo 3 : Visualisation d'une interception de trafic + Quiz | Démo + Quiz interactif | Script de démo & Banque de quiz (Thème A3) |
| 85–90 | Clôture de la session & consignes pour la session A4 | Plénière | Slide récapitulatif & devoirs |

## Activités détaillées
- **Activité 1 — Audit et segmentation réseau d'une PME** :
  - *Objectif* : Identifier les vulnérabilités d'architecture d'un réseau plat et proposer une segmentation logique sécurisée.
  - *Consignes pas-à-pas* :
    1. Répartir les apprenants en groupes de 3 ou 4.
    2. Distribuer la fiche d'activité présentant le schéma d'un réseau plat de PME (où les serveurs internes, les ordinateurs comptables, les postes R&D et la borne Wi-Fi publique des clients partagent tous le même espace d'adressage IP).
    3. Demander aux groupes de lister les risques en cas de compromission d'un poste connecté au Wi-Fi public.
    4. Demander aux groupes de redessiner l'architecture en y ajoutant un pare-feu et en segmentant le réseau en trois zones distinctes (Réseau Interne, Wi-Fi Invités, Zone Démilitarisée - DMZ pour le serveur web).
    5. Mise en commun : chaque groupe affiche ses correctifs et explique le placement de son pare-feu.
  - *Livrable attendu* : Une liste écrite de 3 risques majeurs identifiés et un schéma révisé d'architecture réseau segmentée.
  - *Durée* : 15 minutes (10 min en sous-groupe, 5 min de restitution).
  - *Modalité* : Travail collaboratif en équipe sur tableau virtuel.
  - *Critères de réussite* : Placement correct du pare-feu à la frontière réseau, isolation logique complète du Wi-Fi Invités et des serveurs internes.

- **Démonstration — Interception de flux en clair vs chiffré** :
  - *Lien* : Renvoi au script de démonstration `A_scripts_demo.md#demo-3-interception-flux`.
  - *Description* : Le mentor présente un cas d'usage fictif où un utilisateur soumet un formulaire contenant un mot de passe d'abord via une page HTTP non sécurisée, puis via une page HTTPS. Le mentor montre (à travers des captures pré-enregistrées ou un schéma interactif) que le mot de passe est lisible en clair dans le premier cas alors qu'il est indéchiffrable dans le second.

## Questions d'interaction (pour stimuler la réflexion)
- "Si vous êtes connecté au réseau Wi-Fi gratuit d'un hôtel et que vous naviguez sur un site bancaire en HTTPS, le gérant de l'hôtel peut-il voir le solde de votre compte ou votre mot de passe ? Pourquoi ?" (Focus chiffrement de protocole TLS)
- "Quelle analogie du monde réel pourriez-vous utiliser pour expliquer la différence entre un pare-feu (filtrage) et un VPN (tunnel sécurisé) à un non-technicien ?" (Focus vulgarisation)
- "En cas d'attaque par ransomware sur le poste de l'accueil, comment la segmentation du réseau protège-t-elle le serveur de base de données de production ?" (Focus confinement de la menace)

## Articulation avec le projet
- Les livrables de cette session fournissent la brique "Réseau" du **Projet Capstone**. Les apprenants devront concevoir et justifier le plan d'architecture réseau cible sécurisé pour la PME fictive afin de remédier à ses vulnérabilités d'infrastructure actuelles.

## Self-paced APRÈS la séance (~90 min) & évaluation formative
- Suivre le module d'auto-formation sur la sécurité des réseaux (pare-feux et VPN).
- Réaliser le lab pratique virtuel d'écriture de règles de pare-feu élémentaires (autoriser/bloquer un port).
- Auto-évaluation (10 questions sur les protocoles, les ports par défaut et les principes de filtrage).

## Checklist matériel mentor
- [x] Supports de présentation (Slides S03)
- [x] Fiche d'activité A_S03 (Schéma réseau plat à auditer)
- [x] Script visuel de démo de capture réseau (dans `A_scripts_demo.md`)
- [x] Outil de sondage interactif
- [x] Support complet de cours en format `.MD` (`A_S03_support.md`)
