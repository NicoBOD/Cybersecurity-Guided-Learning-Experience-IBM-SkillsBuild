# Spécifications des slides — Session B20 : Grand Atelier d'Audit Interactif & Clôture
Parcours : B 20 sessions  |  Module : Consolidation & Évaluation  |  Format : Spécifications Markdown

> **Principe** : texte affiché minimal (situations, options, chiffres) ; le discours complet est dans le [plan de séance minuté](../plans-de-seance/B_S20_plan.md) et le détail des votes dans le [dossier de l'atelier](../projet/B_capstone.md). Les slides 5 à 11 suivent le rituel : situation → débat chat → vote → débrief → score.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Grand Atelier d'Audit Interactif — MedDistri
  - Session finale : l'examen de sortie, en équipe et sans note
  - Parcours B — Session B20
- **Notes orateur** : Accueil chaleureux — c'est la dernière session. Annoncer le format : pas de cours, pas de soutenance ; un audit collectif voté en direct, avec un incident surprise. Vingt sessions de réflexes à mobiliser.
- **Visuel suggéré** : Loupe d'audit posée sur le logo MedDistri, jauge de score à 10 % en bas de slide.
  - **alt-text** : Ouverture du Grand Atelier d'Audit MedDistri avec le score de départ.

---

### Slide 2 — Le cadre : votre cabinet de conseil
- **Type** : contenu
- **Points clés (bullets)** :
  - Vous êtes **collectivement** le consultant sécurité de MedDistri (PME, 25 salariés, dispositifs médicaux)
  - Rituel de chaque décision : situation → **débat dans le chat** → vote → débrief → score
  - Score de départ : **10 %** · Label de Résilience Cyber si **> 75 %**
  - Au programme : 6 votes d'audit · 1 incident en direct · 1 débat final · le bilan du parcours
- **Notes orateur** : Insister sur le débat AVANT le vote : les arguments comptent plus que le score. Prévenir avec le sourire : « le programme dit "audit" — mais les crises ne préviennent pas. »
- **Visuel suggéré** : Parcours de jeu en 8 cases avec jauge de score sur le côté.
  - **alt-text** : Le déroulé de l'atelier sous forme de parcours à étapes.

---

### Slide 3 — 📊 Sondage n°1 : le chiffre à retenir
- **Type** : sondage
- **Points clés (bullets)** :
  - Quelle part des attaques par compromission de compte le **MFA** bloque-t-il ?
  - A) ~50 % — B) ~80 % — C) plus de 99 %
  - Source : étude Microsoft, 2019
- **Notes orateur** : Réponse C. Le meilleur rapport protection/effort de la cybersécurité. Teaser : « mémorisez-le — dans une heure, la directrice de MedDistri vous dira que le MFA fait perdre du temps, et ce chiffre sera votre argument. »
- **Visuel suggéré** : Grand « 99 % » avec un cadenas à deux facteurs.
  - **alt-text** : L'efficacité de l'authentification multifacteur contre les compromissions de compte.
- **Élément interactif** : Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — Le diagnostic MedDistri : cinq failles, cinq affaires réelles
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Réseau **à plat** → Target (2013, B06)
  - **RDP/SSH exposés** + `Admin@MedDistri2025` → le vecteur n°1 des rançongiciels PME (B05, B08)
  - M365 **sans MFA** → Colonial Pipeline, Uber (B08, B09)
  - Sauvegarde **USB branchée en permanence** → les sauvegardes ciblées 9 fois sur 10 (Veeam 2023, B12)
  - **RGPD ignoré** → Google/CNIL, Clearview (B15)
- **Notes orateur** : Une phrase par ligne : la faille, puis l'affaire réelle qui l'a payée. « Rien de caricatural : ce diagnostic est celui de milliers de PME françaises. Score de départ : 10 %. Améliorons-le. »
- **Visuel suggéré** : Tableau à deux colonnes « chez MedDistri / dans la vraie vie » avec pictogrammes.
  - **alt-text** : Correspondance entre les vulnérabilités de MedDistri et les affaires réelles du parcours.

---

### Slide 5 — 📊 Audit 1 : mettre fin au réseau plat (n°2)
- **Type** : sondage
- **Points clés (bullets)** :
  - A) Un VPN sur les téléphones des commerciaux
  - B) **3 VLANs** (LAN admin, LAN entrepôt, **DMZ**) isolés par un pare-feu à filtrage strict ✅
  - C) Un second pare-feu en série, réseau inchangé
- **Notes orateur** : Débat chat 90 s avant le vote. Débrief : rejouer l'Atelier 1 (B08) ; Target = le prestataire de climatisation qui atteint les caisses, c'est LE réseau plat. A ne traite pas le LAN ; C filtre un réseau qui reste plat. Mettre à jour le score.
- **Visuel suggéré** : Schéma avant/après : nuage de machines mélangées vs trois zones cloisonnées par un pare-feu.
  - **alt-text** : Le réseau plat de MedDistri face à l'architecture segmentée cible.
- **Élément interactif** : Débat chat + sondage Livestorm n°2.

---

### Slide 6 — 📊 Audit 2 : la règle qui protège l'interne (n°3)
- **Type** : sondage
- **Points clés (bullets)** :
  - A) Autoriser tous les flux du LAN vers la DMZ
  - B) **Interdire tout flux initié depuis la DMZ vers le LAN administratif** ✅
  - C) Autoriser le SSH de la DMZ vers le LAN
- **Notes orateur** : Débrief : la DMZ est la pièce sacrifiable — si le serveur web tombe, l'attaquant ne rebondit PAS vers l'interne. Le SENS du flux fait la sécurité (B06). Score.
- **Visuel suggéré** : Flèche DMZ→LAN barrée en rouge, flèche LAN→DMZ verte et contrôlée.
  - **alt-text** : Règle de filtrage interdisant les flux initiés depuis la DMZ vers le réseau interne.
- **Élément interactif** : Débat chat + sondage Livestorm n°3.

---

### Slide 7 — 📊 Audit 3 : les portables des commerciaux (n°4)
- **Type** : sondage
- **Points clés (bullets)** :
  - 15 commerciaux, ordinateurs utilisés dans des lieux publics — en cas de **vol** ?
  - A) Un pare-feu personnel
  - B) **Chiffrement intégral du disque** (BitLocker/FileVault) + mots de passe de session robustes ✅
  - C) Supprimer le mot de passe de session
- **Notes orateur** : Débrief : un portable volé est une fuite de données SAUF si le disque est chiffré (Atelier 2/B12, et le portable dans le train de B15). C est une faute professionnelle. Score.
- **Visuel suggéré** : Portable ouvert dans un café, disque symbolisé par un coffre-fort verrouillé.
  - **alt-text** : La protection des données d'un ordinateur portable nomade par chiffrement intégral.
- **Élément interactif** : Débat chat + sondage Livestorm n°4.

---

### Slide 8 — 📊 Audit 4 : remplacer la sauvegarde USB (n°5)
- **Type** : sondage
- **Points clés (bullets)** :
  - A) Sauvegarde locale 2×/jour, sur un serveur du même réseau
  - B) **Règle 3-2-1** : deux supports locaux (dont un **hors ligne**) + une copie **immuable** déportée dans le cloud ✅
  - C) Copies manuelles OneDrive « de temps en temps »
- **Notes orateur** : Débrief : le disque USB branché en permanence sera chiffré AVEC le serveur — plus de 9 attaques sur 10 ciblent les sauvegardes (Veeam, 2023 — B12). A reste sur le même réseau ; C n'est ni systématique ni versionnée. Score — et transition abrupte : « Stop. Votre téléphone sonne. »
- **Visuel suggéré** : Trois copies symbolisées (3-2-1) avec l'une hors ligne débranchée et une dans un nuage verrouillé.
  - **alt-text** : La règle de sauvegarde 3-2-1 avec copie hors ligne et copie immuable.
- **Élément interactif** : Débat chat + sondage Livestorm n°5.

---

### Slide 9 — 🚨 INCIDENT EN DIRECT : le confinement (n°6)
- **Type** : sondage
- **Points clés (bullets)** :
  - « Les fichiers de la compta se chiffrent — demande de rançon — menace de publier les **données de santé** ! »
  - A) Tout éteindre et contacter l'ANSSI
  - B) **Isoler chaque machine (câble/Wi-Fi) et le réseau au pare-feu — SANS éteindre (la RAM !)** ✅
  - C) Payer la rançon immédiatement
- **Notes orateur** : Ton maître du jeu (comme en B19). Débrief : les réflexes de B18 — la RAM est le coffre à preuves (parfois la clé) ; on confine PUIS on signale ; payer ne garantit rien et finance l'écosystème (ANSSI, B02/B19). Score.
- **Visuel suggéré** : Écran de rançon stylisé, câble réseau débranché au premier plan, machine toujours allumée.
  - **alt-text** : Confinement d'un rançongiciel actif sans extinction des machines.
- **Élément interactif** : Sondage Livestorm n°6.

---

### Slide 10 — 🚨 INCIDENT : les journalistes appellent (n°7)
- **Type** : sondage
- **Points clés (bullets)** :
  - Des journalistes contactent le service logistique au sujet de l'attaque
  - A) Chaque employé répond librement — transparence !
  - B) **Toutes les demandes vers la cellule de crise : porte-parole unique, consigne interne de silence** ✅
  - C) Couper le téléphone de l'entreprise
- **Notes orateur** : Débrief : les règles d'or de B19 — une voix, des faits. A fabrique contradictions et fuites ; C transforme la crise en scandale. Rappeler les deux 72 h : notification CNIL (données de santé !) et plainte LOPMI. Score.
- **Visuel suggéré** : Standard téléphonique avec toutes les lignes redirigées vers un unique mégaphone.
  - **alt-text** : Centralisation de la communication de crise vers un porte-parole unique.
- **Élément interactif** : Sondage Livestorm n°7.

---

### Slide 11 — 📊 Le débat final : l'objection de la directrice (n°8)
- **Type** : sondage
- **Points clés (bullets)** :
  - « Le MFA ? Mes commerciaux perdent déjà assez de temps. »
  - A) **« Le MFA bloque plus de 99 % des attaques de compte (Microsoft 2019) — et un arrêt d'activité coûte infiniment plus que 3 secondes par connexion. »** ✅
  - B) « C'est obligatoire par la loi sur les données personnelles. »
  - C) « Les commerciaux n'ont pas leur mot à dire. »
- **Notes orateur** : Débrief : LA compétence de restitution managériale — traduire en risque d'entreprise. B est faux (le RGPD impose la sécurité, pas le MFA nommément) ; C perd la direction, donc le budget (B13). Boucler avec le sondage n°1 : le chiffre annoncé a servi. Score final.
- **Visuel suggéré** : Balance : « 3 secondes par connexion » d'un côté, « arrêt d'activité + amende » de l'autre.
  - **alt-text** : L'argumentaire coût-bénéfice de l'authentification multifacteur face à l'objection métier.
- **Élément interactif** : Débat chat + sondage Livestorm n°8.

---

### Slide 12 — Débrief : le score, le label & le schéma cible
- **Type** : schéma
- **Points clés (bullets)** :
  - Score final de MedDistri → **Label de Résilience Cyber** si > 75 %
  - Schéma cible (tableau blanc) : DMZ · VLANs · règles de flux · VPN + MFA nomades
  - Plan de remédiation : **quick wins du mois** (MFA, RDP/SSH fermés, mot de passe admin, sauvegarde hors ligne) puis chantiers (segmentation, chiffrement, registre RGPD, supervision)
- **Notes orateur** : Annoncer le score, décerner (ou non) le label. Dessiner le schéma cible en direct — « en B05, c'était du vocabulaire ; ce soir, c'est votre plan de remédiation, voté ligne par ligne. » Prioriser : l'impact fort à effort faible d'abord.
- **Visuel suggéré** : Tableau blanc interactif : schéma réseau cible d'un côté, plan de remédiation en deux colonnes (quick wins / chantiers) de l'autre.
  - **alt-text** : Le schéma réseau sécurisé cible et le plan de remédiation priorisé de MedDistri.

---

### Slide 13 — 🤔 « Tranquilles pour cinq ans ? » & le bilan du parcours
- **Type** : récap
- **Points clés (bullets)** :
  - 🤔 La directrice : « une fois tout en place, tranquilles pour 5 ans ? » — A) Oui B) **Non : la sécurité est un processus continu** ✅ C) Oui, avec un pare-feu plus cher
  - La fresque : **A** Fondations → **B** Systèmes & réseaux → **C** Identités & cloud → **D** Gouvernance & conformité → **E** Opérations & réponse — et 4 Ateliers de Synthèse
  - 💬 Chat : le module, l'affaire ou le réflexe qui vous a marqué ?
  - 📊 n°9 (bonus) : le meilleur ROI pour une TPE/PME ? → **MFA + mots de passe + sensibilisation**
- **Notes orateur** : Mini-scénario : l'audit est une photo, pas un film — veille, correctifs, re-scans, exercice annuel (la roue de Deming de B13). Puis la fresque en 2 minutes et la récolte chat (le RETEX du parcours). Rappeler la boîte à arguments du support (99 % MFA, 62 min, 258 jours, 9/10, 2,66 M$, 20 M€/4 %). N°9 = tampon.
- **Visuel suggéré** : Frise des 5 modules avec les 4 ateliers en jalons, roue de processus qui tourne en filigrane.
  - **alt-text** : La fresque complète du parcours et le rappel du processus continu de sécurité.
- **Élément interactif** : Scénario A/B/C dans le chat + question chat bilan + sondage Livestorm n°9 (bonus).

---

### Slide 14 — Félicitations & clôture
- **Type** : récap
- **Points clés (bullets)** :
  - 🎓 Bravo pour vos 20 sessions, vos votes et vos débats !
  - **Certification** : valider les quiz IBM SkillsBuild → badge final (Credly) → LinkedIn
  - **La suite** : Security+ en première marche · TryHackMe / Hack The Box pour pratiquer · veille CERT-FR
  - 📋 Formulaire d'évaluation de la formation dans le chat — merci !
- **Notes orateur** : Dérouler la procédure de badges, les trois axes de la suite, partager le formulaire. Verbatim de clôture : « la cybersécurité repose moins sur les outils que sur des humains qui ont les bons réflexes. Vous les avez — entretenez-les. Merci, et à bientôt sur LinkedIn ! » Terminer à l'heure exacte.
- **Visuel suggéré** : Badge de diplôme numérique, confettis sobres, logos SkillsBuild/Credly/LinkedIn alignés.
  - **alt-text** : Slide de félicitations et de clôture du parcours avec la procédure de certification.
- **Élément interactif** : Partage du formulaire d'évaluation dans le chat.
