# Spécifications des slides — Session B08 : Durcissement des systèmes & endpoints (+ Atelier de Synthèse 1)
Parcours : B 20 sessions  |  Module : B — Systèmes & réseaux  |  Format : Spécifications Markdown

> **Principe** : le texte affiché reste minimal (mots-clés, chiffres, schémas) ; le contenu riche est dans les notes orateur et le [plan de séance minuté](../plans-de-seance/B_S08_plan.md). Toutes les interactions passent par les sondages et le chat Livestorm.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Durcissement des systèmes & endpoints
  - Le dernier rempart : la machine elle-même
  - Parcours B — Session B08 · **Atelier de Synthèse 1** inclus
- **Notes orateur** : Accueillir : grande soirée — dernière session du module réseau ET premier Atelier de Synthèse : « dans une heure, vous aurez conçu ensemble l'architecture sécurisée complète d'une PME. » Retour self-paced : « qui a préparé son schéma draw.io ? Tapez dans le chat les équipements que vous y avez mis. » Rappel express de B07 (TLS, VPN, DigiNotar).
- **Visuel suggéré** : Cadenas blindé intégré au cœur d'une carte mère stylisée avec pistes de circuits rétroéclairées.
  - **alt-text** : Carte mère d'ordinateur avec un verrou de sécurité intégré symbolisant le durcissement du système.
- **Élément interactif** : 💬 Chat d'accueil — les équipements des schémas draw.io.

---

### Slide 2 — Objectifs & agenda
- **Type** : contenu
- **Points clés (bullets)** :
  - Appliquer le moindre privilège (droits, élévation, cycle de vie des comptes).
  - Durcir un poste ou un serveur (checklist, GPO, référentiels CIS/ANSSI).
  - Différencier antivirus à signatures et EDR comportemental.
  - **Atelier de Synthèse 1** : l'architecture sécurisée de MedDistri.
  - Agenda : moindre privilège → durcissement → EDR → Colonial Pipeline → ATELIER → quiz.
- **Notes orateur** : Après les murailles et les tunnels, la cible finale de presque toutes les attaques : la machine. Puis le moment fort : l'atelier où tout le module B s'assemble sur un cas concret, entièrement par sondages et chat.
- **Visuel suggéré** : Deux colonnes présentant les objectifs et l'agenda, avec l'atelier mis en évidence.
  - **alt-text** : Tableau des objectifs et de l'agenda de la session avec l'atelier de synthèse surligné.

---

### Slide 3 — Brise-glace : l'oléoduc et le compte dormant
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **Sondage n°1** : Colonial Pipeline (2021), pénuries d'essence sur la côte Est — le point d'entrée ?
  - A) Un compte VPN dormant sans MFA — B) Une faille zero-day — C) Un employé complice
- **Notes orateur** : Lancer le sondage n°1 (60-90 s). Réponse A : un compte qui n'aurait plus dû exister, un mot de passe issu d'une fuite, pas de MFA (Mandiant). Pas de génie : du ménage non fait. La leçon du soir : le durcissement est l'art de fermer ce qui n'a pas de raison d'être ouvert — comptes, services, ports.
- **Visuel suggéré** : Oléoduc stylisé traversant un paysage, arrêté par un simple badge d'accès poussiéreux en surimpression.
  - **alt-text** : Oléoduc à l'arrêt symboliquement bloqué par un badge d'accès oublié représentant le compte dormant.
- **Élément interactif** : 📊 Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — Le moindre privilège
- **Type** : contenu
- **Points clés (bullets)** :
  - Le strict nécessaire — pour chaque utilisateur, programme, processus.
  - Jamais d'administrateur / `root` au quotidien.
  - L'élévation **temporaire et tracée** : UAC, `sudo`.
  - Et dans le temps : un compte qui ne sert plus se **désactive** (Colonial !).
- **Notes orateur** : Question rhétorique : si vous cliquez sur une pièce jointe piégée avec un compte standard, que peut faire le malware ? Pas grand-chose — ni s'installer en profondeur, ni modifier le système. Le moindre privilège transforme l'infection en incident mineur. Le cycle de vie des comptes est l'angle mort classique : rappel de l'offboarding de B02.
- **Visuel suggéré** : Trousseau minimaliste à deux clés face à un trousseau surchargé barré, avec un badge « admin » rangé dans un coffre.
  - **alt-text** : Comparaison entre un trousseau de clés minimal autorisé et un trousseau excessif barré, symbolisant le moindre privilège.

---

### Slide 5 — Le durcissement en 5 étapes
- **Type** : schéma
- **Points clés (bullets)** :
  - 1. Désactiver services & protocoles inutiles (SMBv1, Telnet).
  - 2. Correctifs rapides — en jours pour le critique.
  - 3. Politiques locales : mots de passe, verrouillage, comptes par défaut.
  - 4. Chiffrement du disque (BitLocker / LUKS).
  - 5. Pare-feu local actif.
- **Notes orateur** : L'analogie de la voiture neuve livrée vitres baissées — relance chat : « pourquoi les systèmes sont-ils livrés "ouverts" par défaut ? » (compatibilité et confort avant sécurité). SMBv1 = le vecteur de WannaCry (B03). À l'échelle : référentiels CIS/ANSSI + déploiement GPO + vérification OpenSCAP — on ne durcit pas 500 postes à la main.
- **Visuel suggéré** : Checklist verticale à cinq cases cochées sur fond d'écran de configuration système.
  - **alt-text** : Checklist de durcissement système en cinq étapes affichée sur un écran de configuration.
- **Élément interactif** : 💬 Chat — pourquoi les systèmes sont-ils livrés « ouverts » ?

---

### Slide 6 — Antivirus vs EDR
- **Type** : schéma
- **Points clés (bullets)** :
  - **Antivirus** : des **signatures** — les photos de cambrioleurs connus.
  - **EDR** : des **comportements** — les capteurs de mouvement.
  - Word → PowerShell → chiffrement massif : chaîne anormale → blocage + **isolement réseau**.
- **Notes orateur** : L'antivirus est aveugle face au zero-day, au polymorphe, au fileless (B03). L'EDR observe les processus, les fichiers, le réseau — et isole la machine automatiquement. Question rhétorique : l'alerte de 2h du matin de B06 — qui isole le poste quand personne ne regarde ? L'EDR. C'est aussi la boîte noire qu'exploitera le SOC (B16).
- **Visuel suggéré** : Diptyque : trombinoscope de malwares connus (antivirus) face à des capteurs de mouvement surveillant des processus (EDR).
  - **alt-text** : Comparaison entre la détection par signatures d'un antivirus et la surveillance comportementale d'un EDR.

---

### Slide 7 — Le paysage en chiffres
- **Type** : chiffres clés
- **Points clés (bullets)** :
  - **~4,4 M$** de rançon payés par Colonial Pipeline (2021) — ~2,3 M$ récupérés par la justice.
  - **1 compte VPN dormant, 0 MFA** : le point d'entrée (Mandiant).
  - **52 000 $ demandés → jusqu'à ~17 M$ de reconstruction** : Atlanta, 2018.
- **Notes orateur** : Trois lectures : les plus grandes pannes partent du plus petit oubli ; payer ne dispense pas de reconstruire (et la justice ne récupère pas toujours — rappel du débat B02) ; refuser de payer se prépare AVANT — durcissement et sauvegardes, sinon la facture décuple. Transition : l'histoire complète.
- **Visuel suggéré** : Trois grands chiffres en typographie XXL avec leurs sources et années en petit.
  - **alt-text** : Trois statistiques géantes sur les coûts des attaques Colonial Pipeline et Atlanta.

---

### Slide 8 — Affaire : Colonial Pipeline (2021)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - 7 mai 2021 : rançongiciel **DarkSide** (un RaaS) détecté.
  - L'oléoduc arrêté : ~la moitié des carburants de la côte Est.
  - Rançon payée (~4,4 M$) · saisie partielle par la justice.
  - Le point d'entrée : **un compte VPN dormant, sans MFA**.
- **Notes orateur** : Raconter : l'arrêt préventif de 9 000 km de conduites, les files d'attente, l'état d'urgence — l'impact déborde l'informatique. Puis l'enquête : mot de passe issu d'une fuite, compte jamais désactivé, pas de MFA. Trois contrôles simples auraient CHACUN suffi : revue des comptes, MFA, non-réutilisation des mots de passe. Cas complémentaire Atlanta (1 min) : refuser de payer est la bonne doctrine — à condition d'avoir durci et sauvegardé avant. Relance chat : « quel détail vous marque ? »
- **Visuel suggéré** : Carte de la côte Est américaine avec le tracé de l'oléoduc en pointillés rouges et des stations-service en rupture.
  - **alt-text** : Carte stylisée montrant l'oléoduc Colonial arrêté et les pénuries de carburant sur la côte Est américaine.
- **Élément interactif** : 💬 Chat — réactions au cas.

---

### Slide 9 — 🤔 Que feriez-vous ? Les droits admin du commercial
- **Type** : scénario
- **Points clés (bullets)** :
  - « Je pars demain, il me faut les droits admin pour installer le logiciel du client. »
  - A) Admin permanent — B) Installation par le support / élévation temporaire tracée — C) Refus total.
- **Notes orateur** : Réponses par chat (A/B/C). Débrief : B — le moindre privilège n'est pas le refus du besoin, c'est le refus du privilège PERMANENT pour un besoin PONCTUEL. A laisse un poste à pleins pouvoirs longtemps après le déplacement ; C pousse au contournement (PC personnel, clé USB). La sécurité qui organise le OUI encadré est obéie. Transition : « et maintenant, le grand moment — MedDistri vous attend. »
- **Visuel suggéré** : Commercial avec sa valise devant trois guichets étiquetés A, B, C.
  - **alt-text** : Commercial pressé devant trois guichets représentant les trois réponses possibles à sa demande de droits.
- **Élément interactif** : 🤔 Mini-scénario — réponse A/B/C dans le chat.

---

### Slide 10 — Atelier de Synthèse 1 : MedDistri, l'état des lieux
- **Type** : atelier (présentation)
- **Points clés (bullets)** :
  - PME MedDistri : 40 salariés, distribution de matériel médical.
  - Le schéma actuel : **tout à plat** — postes, serveur web, serveur de gestion, aucun filtrage interne.
  - 💬 « Qu'est-ce qui vous choque sur ce schéma ? »
- **Notes orateur** : Afficher le schéma à plat (préparé, cf. B_miniprojets). Laisser le chat réagir : attendu — tout communique avec tout, serveur web exposé au milieu des postes, aucun VPN pour les 15 commerciaux. « Vous venez de décrire TV5 Monde et Target. Réparons cela — trois décisions d'architecture, trois votes. »
- **Visuel suggéré** : Schéma réseau volontairement chaotique : tous les équipements reliés à un unique switch central, sans zones.
  - **alt-text** : Schéma d'un réseau d'entreprise à plat où tous les équipements partagent le même segment sans cloisonnement.
- **Élément interactif** : 💬 Chat — l'audit spontané du schéma à plat.

---

### Slide 11 — Atelier : les trois décisions d'architecture
- **Type** : atelier (sondages)
- **Points clés (bullets)** :
  - 📊 **Sondage n°2** : où placer le serveur web public ?
  - 📊 **Sondage n°3** : comment connecter les 15 commerciaux nomades ?
  - 📊 **Sondage n°4** : quel durcissement prioritaire pour le poste de la comptable ?
- **Notes orateur** : Un sondage par décision (~4 min chacun), débriefs scriptés dans le support : n°2 — DMZ sur port dédié du pare-feu (A reproduit Target, C expose tout) ; n°3 — VPN + MFA (A est le scénario force brute RDP de B05 ; rappeler Colonial : un VPN sans MFA est lui-même une porte) ; n°4 — compte standard + EDR + chiffrement (deux antivirus se neutralisent ; un seul AV ignore le fileless et le vol physique).
- **Visuel suggéré** : Trois cartes de décision illustrées : serveur web, valise de commercial, poste comptable.
  - **alt-text** : Trois cartes représentant les décisions d'architecture à voter pour sécuriser MedDistri.
- **Élément interactif** : 📊 Sondages Livestorm n°2 à 4 — les décisions d'architecture.

---

### Slide 12 — Atelier : le schéma cible & la table de flux
- **Type** : atelier (co-construction)
- **Points clés (bullets)** :
  - Le schéma cible se dessine en direct : WAN → pare-feu → DMZ / VLAN / passerelle VPN.
  - 💬 « Proposez une règle : source → destination → port → action. »
  - Dernière ligne, toujours : `Any → Any : Deny`.
- **Notes orateur** : Basculer sur le tableau blanc (ou draw.io partagé) et dessiner le schéma cible au fil des propositions du chat, en reprenant la méthode EcoLog (B06). Corriger en direct, valoriser les bonnes règles. Synthèse : « chaque brique du module est sur ce schéma — B05 la lecture des flux, B06 la segmentation et cette table, B07 le VPN/MFA/TLS, B08 les postes durcis et l'EDR. Ce schéma, c'est VOTRE travail — et c'est ce qu'un consultant facture. »
- **Visuel suggéré** : Tableau blanc interactif montrant le schéma cible en cours de construction avec la table de flux à côté.
  - **alt-text** : Tableau blanc collaboratif où se dessine l'architecture réseau cible de MedDistri avec sa table de filtrage.
- **Élément interactif** : 💬 Chat — co-construction de la table de flux.

---

### Slide 13 — Et vous ? Administrateur local ?
- **Type** : sondage (opinion)
- **Points clés (bullets)** :
  - 📊 **Sondage n°5** : sur votre poste professionnel, êtes-vous administrateur local ?
  - A) Oui, régulièrement — B) Non, compte standard — C) Je ne sais pas.
- **Notes orateur** : Sondage d'opinion, sans jugement — un miroir de la maturité des organisations. B est la cible (avec une élévation fluide). A est fréquent en PME : chaque clic à pleins pouvoirs. C : vérifier prend 30 secondes (tenter une installation) — c'est l'action de la semaine.
- **Visuel suggéré** : Écran de session Windows avec une invite UAC en surimpression et un point d'interrogation.
  - **alt-text** : Écran d'ordinateur affichant une demande d'élévation de privilèges avec un point d'interrogation.
- **Élément interactif** : 📊 Sondage Livestorm n°5 (opinion).

---

### Slide 14 — Quiz de validation
- **Type** : quiz (sondages)
- **Points clés (bullets)** :
  - 📊 **Sondage n°6** : un service par défaut inutile — que faire ?
  - 📊 **Sondage n°7** : EDR vs antivirus — la différence ?
  - 📊 **Sondage n°8** : le chiffrement de disque protège contre... ?
- **Notes orateur** : Lancer les trois sondages à la suite (~2 min chacun), débriefs scriptés dans le support : « il pourrait servir un jour » est l'ennemi du durcissement ; signatures = photos de cambrioleurs, comportements = capteurs de mouvement ; le chiffrement au repos répond au portable volé dans le train. Si le temps le permet, enchaîner sur le bonus n°9 (la règle d'hygiène n°1 : retirer les droits admin).
- **Visuel suggéré** : Trois cartes de quiz numérotées 6, 7, 8 avec l'icône de sondage Livestorm.
  - **alt-text** : Trois cartes de questions de quiz numérotées, associées à des sondages en direct.
- **Élément interactif** : 📊 Sondages Livestorm n°6 à 8 (+ n°9 en tampon).

---

### Slide 15 — Synthèse & fin du module Systèmes & réseaux
- **Type** : récap
- **Points clés (bullets)** :
  - Module B terminé : lire le trafic (B05), bâtir les murailles (B06), chiffrer (B07), durcir (B08).
  - L'Atelier de Synthèse 1 : l'architecture MedDistri, conçue par VOUS.
  - Self-paced : SkillsBuild *« System Hardening and Patch Management »* + vérifier ses droits admin + repérer le SSO au quotidien.
  - Prochaine session — B09 : le module Identités & accès (MFA, SSO).
- **Notes orateur** : Faire écrire dans le chat UN mot retenu, en lire 4-5. Féliciter pour le module accompli et l'atelier. Teaser B09 : « les murailles sont là... mais qui a les clés ? Le module Identités : mots de passe, MFA, SSO — et pourquoi des attaquants ont appris à "fatiguer" la MFA. » Terminer à l'heure exacte.
- **Visuel suggéré** : Frise des quatre sessions du module B cochées, le schéma MedDistri en vignette, flèche vers un panneau « Module C — Identités ».
  - **alt-text** : Frise de progression du module réseau validé avec le schéma final de l'atelier et l'ouverture du module identités.
- **Élément interactif** : Chat de clôture — « un mot que vous retenez ».
