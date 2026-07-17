# Plan de séance — Session B20
Parcours : B 20 sessions  |  Module : Consolidation & Évaluation  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## 1. Métadonnées de la session
* **Titre** : Grand Atelier d'Audit Interactif & Clôture du Parcours
* **Objectifs pédagogiques opérationnels** :
  * Évaluer l'architecture, les identités, les sauvegardes et la gouvernance de la PME MedDistri par six décisions d'audit votées en direct ([dossier de l'atelier](../projet/B_capstone.md)).
  * Réagir à un incident rançongiciel déclenché en cours de séance (confinement, préservation des preuves, communication de crise).
  * Traduire les constats techniques en risques d'entreprise (restitution managériale) et planifier la suite de sa montée en compétences (certifications, laboratoires, veille).
* **Prérequis** : Sessions B01 à B19 — la session mobilise l'ensemble du parcours, dont les quatre Ateliers de Synthèse (B08, B12, B15, B17).
* **Lien de progression** : Session finale. L'audit rejoue en 90 minutes les réflexes des cinq modules ; la clôture ouvre sur l'après (badges, certifications, veille).
* **Spécificité d'animation** : session 100 % atelier — un score de résilience collectif (départ : 10 %, label si > 75 %) progresse à chaque décision correcte ; faire débattre le chat AVANT chaque vote.

## 2. Checklist technique Livestorm (avant la session)

- [ ] Les **9 sondages** sont pré-créés dans Livestorm, dans l'ordre du tableau ci-dessous.
- [ ] Le partage d'écran est testé avec le diaporama B20 ([spécifications](../slides/B_S20_slides_spec.md)) — le tableau blanc interactif est prêt pour le schéma réseau cible du débrief.
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleurs arguments avant chaque vote.
- [ ] Le formulaire d'évaluation de fin de formation est prêt à être partagé dans le chat.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
| :-- | :-- | :-- | :-- | :-- |
| 1 | 0:05 | Brise-glace | Part des attaques par compromission de compte bloquées par le MFA (Microsoft 2019) ? | C — Plus de 99 % |
| 2 | 0:16 | Audit | Segmentation : comment mettre fin au réseau plat ? | B — 3 VLANs + DMZ + pare-feu |
| 3 | 0:24 | Audit | Filtrage : quelle règle contre le rebond depuis la DMZ ? | B — Interdire DMZ → LAN |
| 4 | 0:31 | Audit | Portables des commerciaux volés : quelle parade ? | B — Chiffrement intégral du disque |
| 5 | 0:38 | Audit | Remplacer la sauvegarde USB permanente ? | B — Règle 3-2-1, hors ligne + immuable |
| 6 | 0:45 | Incident | Rançongiciel en cours : première mesure ? | B — Isoler sans éteindre (RAM) |
| 7 | 0:53 | Incident | Les journalistes appellent : quelle directive ? | B — Porte-parole unique |
| 8 | 1:00 | Débat | Objection de la directrice : quel argument pour le MFA ? | A — >99 % + coût d'un arrêt vs 3 secondes |
| 9 | 1:23 | Bonus | Meilleur retour sur investissement pour une TPE/PME ? | B — MFA + mots de passe + sensibilisation |

## 3. Vue d'ensemble du déroulé

| Créneau | Séquence | Interactions |
| :-- | :-- | :-- |
| 0:00–0:05 | Accueil & cadre de l'atelier final | — |
| 0:05–0:10 | Brise-glace : le chiffre du MFA | 📊 Sondage n°1 |
| 0:10–0:16 | Le diagnostic MedDistri & le score de départ | — |
| 0:16–0:24 | **Audit 1 — Segmentation réseau** | 📊 Sondage n°2 + chat |
| 0:24–0:31 | **Audit 2 — Filtrage pare-feu** | 📊 Sondage n°3 + chat |
| 0:31–0:38 | **Audit 3 — Chiffrement des portables** | 📊 Sondage n°4 + chat |
| 0:38–0:45 | **Audit 4 — Sauvegarde 3-2-1** | 📊 Sondage n°5 + chat |
| 0:45–0:53 | **🚨 Incident en direct — Confinement** | 📊 Sondage n°6 + chat |
| 0:53–1:00 | **Incident — Communication de crise** | 📊 Sondage n°7 + chat |
| 1:00–1:06 | **Le débat final — L'objection de la directrice (MFA)** | 📊 Sondage n°8 + chat |
| 1:06–1:14 | Débrief : score, label & schéma réseau cible | Tableau blanc |
| 1:14–1:18 | Mini-scénario : « tranquilles pour cinq ans ? » | 🤔 Chat A/B/C |
| 1:18–1:23 | Bilan du parcours : les cinq modules | 💬 Chat « le module qui vous a marqué » |
| 1:23–1:26 | Exercice bonus : le meilleur ROI (tampon) | 📊 Sondage n°9 |
| 1:26–1:30 | Certification, suite & remerciements | Chat + formulaire d'évaluation |

## 4. Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:05 — Accueil & cadre

**🎙️ Verbatim d'ouverture :**
> « Bonsoir à toutes et à tous — et bienvenue dans votre DERNIÈRE session ! Vingt sessions, cinq modules, quatre ateliers, des dizaines d'affaires réelles… Ce soir, pas de cours : un examen de sortie, en équipe et sans note. Vous êtes le cabinet de conseil ; votre client s'appelle MedDistri ; son score de sécurité de départ est de 10 %. Chaque bonne décision collective le fera monter. Au-dessus de 75 % : le Label de Résilience Cyber. À vous de jouer. »

**Points de contenu :**
- Présenter le fonctionnement : débat dans le chat AVANT chaque vote, puis sondage, puis débrief.
- Rappeler que chaque vulnérabilité de MedDistri est la copie d'une affaire réelle vue dans le parcours.

### 0:05–0:10 — 📊 Sondage n°1 (brise-glace) : le chiffre du MFA

Lancer le sondage n°1 (part des attaques de compte bloquées par le MFA). Laisser voter ~60 secondes.

**🎙️ Débrief scripté :**
> « Réponse C : plus de 99 % — étude Microsoft, 2019. Le meilleur rapport protection/effort de toute la cybersécurité. Mémorisez-le : dans une heure, la directrice de MedDistri vous expliquera que le MFA fait perdre du temps à ses commerciaux… et ce chiffre sera votre meilleur argument. »

### 0:10–0:16 — Le diagnostic MedDistri

**Points de contenu (dossier de l'atelier + support §1) :**
- Dérouler les cinq vulnérabilités : réseau à plat, RDP/SSH exposés avec `Admin@MedDistri2025`, M365 sans MFA, disque USB branché en permanence, RGPD ignoré.
- Pour chacune, UNE phrase de rappel du cas réel associé (Target B06, vecteur rançongiciel n°1, Colonial/Uber B08-B09, Veeam/OVHcloud B12, Google/Clearview B15).
- 🎙️ « Rien de caricatural ici : ce diagnostic est celui de milliers de PME françaises. Score de départ : 10 %. Améliorons-le. »

### 0:16–0:45 — 📊 L'audit : quatre votes (sondages n°2 à n°5)

**Rituel identique pour chaque vote (détail des options dans le [dossier](../projet/B_capstone.md)) :** afficher la situation → 60-90 secondes de débat chat (« quels arguments pour quelle option ? ») → vote → débrief → mise à jour du score.

1. **📊 n°2 — Segmentation (0:16–0:24)** : → B, 3 VLANs + DMZ + pare-feu. Débrief : rejouer l'Atelier 1 (B08) ; rappeler Target — le prestataire de climatisation qui atteint les caisses, c'est le réseau plat. A (VPN des téléphones) ne traite pas le LAN ; C (pare-feu en série) filtre un réseau qui reste plat.
2. **📊 n°3 — Filtrage (0:24–0:31)** : → B, interdire DMZ → LAN. Débrief : la DMZ est la pièce sacrifiable ; si le serveur web tombe, l'attaquant ne doit PAS pouvoir rebondir vers l'interne (le sens du flux fait la sécurité — B06).
3. **📊 n°4 — Chiffrement nomade (0:31–0:38)** : → B, chiffrement intégral (BitLocker/FileVault). Débrief : le vol de portable est une PERTE DE DONNÉES sauf si le disque est chiffré (rappel Atelier 2/B12 et l'affaire du portable dans le train — B15) ; C est une faute professionnelle.
4. **📊 n°5 — Sauvegarde (0:38–0:45)** : → B, 3-2-1 avec hors ligne + immuable. Débrief : le disque USB branché en permanence sera chiffré AVEC le serveur (plus de 9 attaques sur 10 ciblent les sauvegardes — Veeam 2023, B12) ; A garde tout sur le même réseau ; C n'est ni systématique ni versionnée.

### 0:45–1:00 — 🚨 L'incident en direct : deux votes (sondages n°6 et n°7)

**🎙️ Verbatim de bascule (ton maître du jeu, comme en B19) :**
> « Stop. Pendant que nous délibérions… votre téléphone sonne. La comptable de MedDistri : *"les fichiers se chiffrent les uns après les autres, il y a une demande de rançon à l'écran — et ils menacent de publier les données de santé des clients !"* L'audit attendra. Gérez. »

1. **📊 n°6 — Confinement (0:45–0:53)** : → B, isoler chaque machine (câble/Wi-Fi) et le réseau au pare-feu, SANS éteindre. Débrief : les réflexes de B18 — la RAM est le coffre à preuves (parfois la clé de chiffrement) ; A détruit les preuves (et on ne « contacte pas l'ANSSI » à la place du confinement — on confine PUIS on signale) ; C finance l'écosystème sans rien garantir (position ANSSI constante, B02/B19).
2. **📊 n°7 — Communication (0:53–1:00)** : → B, porte-parole unique + interdiction de s'exprimer. Débrief : les règles d'or de B19 — une voix, des faits ; A fabrique des contradictions et des fuites ; C (couper le téléphone) transforme la crise en scandale. Rappeler : notification CNIL sous 72 h (données de santé !) et plainte sous 72 h (LOPMI).

### 1:00–1:06 — 📊 Le débat final : l'objection de la directrice (sondage n°8)

**🎙️ Verbatim :**
> « L'incident est contenu, l'audit reprend — et la directrice vous attend : *"Le MFA, très peu pour moi. Mes commerciaux perdent déjà assez de temps."* Quel argument choisissez-vous ? »

**📊 n°8 + débrief :** → A : « le MFA bloque plus de 99 % des attaques de compte (Microsoft 2019), et un arrêt d'activité coûte infiniment plus cher que 3 secondes par connexion ». Débrief : c'est LA compétence de restitution managériale — traduire en risque d'entreprise, pas en protocole. B est faux (le RGPD impose la sécurité des traitements, pas le MFA nommément) ; C perd la direction — et sans la direction, pas de budget (B13 : la direction décide, la direction assume).

### 1:06–1:14 — Débrief : score, label & schéma cible

**Points d'animation :**
- Annoncer le score final et, le cas échéant, décerner le **Label de Résilience Cyber** (> 75 %).
- Dessiner au tableau blanc le schéma réseau cible : DMZ, VLANs, pare-feu avec règles de flux, VPN + MFA pour les nomades — le schéma de l'Atelier 1, enfin complet.
- Dérouler le plan de remédiation priorisé : **quick wins** du mois (MFA activé, RDP/SSH fermés, mot de passe admin changé, rotation de sauvegarde hors ligne) puis chantiers (segmentation, chiffrement, registre RGPD, supervision).
- 🎙️ « Regardez ce schéma : en B05, c'était du vocabulaire. Ce soir, c'est VOTRE plan de remédiation, voté ligne par ligne. »

### 1:14–1:18 — 🤔 Mini-scénario : « tranquilles pour cinq ans ? »

Afficher le scénario (la directrice : « donc une fois tout cela en place, tranquilles pour cinq ans ? ») — réponses A/B/C dans le chat.

**🎙️ Débrief scripté :**
> « B — et vous le saviez : les menaces évoluent, plus de 40 000 CVE par an, les configurations dérivent, les équipes changent. L'audit est une photo, pas un film. Veille CERT-FR, correctifs, re-scans, un exercice de crise par an, sensibilisation continue : la roue de Deming de B13 ne s'arrête jamais. C'est la dernière leçon du parcours : la sécurité est un processus, pas un état. »

### 1:18–1:23 — 💬 Bilan du parcours : les cinq modules

**Points de contenu :**
- Dérouler la fresque : **A** Fondations (CIA, menaces) → **B** Systèmes & réseaux → **C** Identités, accès & cloud → **D** Gouvernance, risques & conformité → **E** Opérations, détection & réponse — et les quatre Ateliers de Synthèse comme jalons pratiques.
- 💬 **Chat :** « le module, l'affaire réelle ou le réflexe qui vous a le plus marqué — celui que vous raconterez demain à un collègue ? » Récolter, rebondir — c'est le RETEX du parcours.
- Rappeler la boîte à arguments (encadré « Les chiffres du parcours » du support) : 99 % MFA, 62 minutes, 258 jours, 9 sur 10, 2,66 M$, 20 M€/4 %.

### 1:23–1:26 — 📊 Sondage n°9 (bonus tampon) : le meilleur ROI

Lancer si le temps le permet (sinon : « à faire en autonomie, il est dans le support »).

**🎙️ Débrief scripté :**
> « B : les fondamentaux gratuits d'abord — MFA, mots de passe uniques, humains entraînés. Le pare-feu et la charte viennent APRÈS les fondamentaux, jamais à leur place. Si vous ne retenez qu'une chose pour une TPE : celle-là. »

### 1:26–1:30 — Certification, suite & remerciements

**Points de clôture :**
- Procédure badges : valider les quiz IBM SkillsBuild, réclamer le badge final (Credly), l'ajouter sur LinkedIn.
- La suite en trois axes (détail dans le support) : certifications (Security+ en première marche), pratique légale (TryHackMe, Hack The Box), veille (CERT-FR — l'abonnement de B02 continue).
- Partager le formulaire d'évaluation de la formation dans le chat.
- 🎙️ **Verbatim de clôture :** « Vingt sessions, et une conviction pour finir : la cybersécurité repose moins sur les outils que sur des humains qui ont les bons réflexes. Vous les avez, désormais — entretenez-les. Merci pour votre assiduité, vos votes, vos débats. Prenez soin de vos données, et à bientôt sur LinkedIn ! »
- Terminer à l'heure exacte.

## 5. Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**exercice bonus n°9** (1:23–1:26) — il est dans le support.
2. Compresser le bilan des cinq modules (1:18–1:23) : la fresque en 2 minutes, le chat en continu pendant la clôture.
3. Raccourcir les débats de chat avant les votes n°4 et n°5 (60 secondes au lieu de 90).

**Ne JAMAIS couper :** les six votes d'audit (n°2-7), le débat MFA (n°8), le débrief avec schéma cible et plan de remédiation, la procédure de certification, le verbatim de clôture.

**Si vous êtes en avance :**
- Poser les questions de réflexion du support (pourquoi la restitution managériale ; les quick wins ; ce que le score ne dit pas).
- Ouvrir un tour de chat « questions carrière » (métiers, certifications, laboratoires) — les réponses types sont dans le bloc mentor.

## 6. Travail en autonomie (Après la formation)
* **Certification** : valider les derniers quiz IBM SkillsBuild, réclamer le badge numérique final (Credly) et le partager sur LinkedIn.
* **Veille active** : s'abonner aux bulletins du **CERT-FR** et suivre les rapports annuels de référence (panorama ANSSI, Verizon DBIR, IBM *Cost of a Data Breach*).
* **Pratique continue** : créer un compte sur un laboratoire en ligne légal (TryHackMe pour un parcours guidé, Hack The Box pour se dépasser) et pratiquer régulièrement.
