# Spécifications des slides — Session 08 : Grand Atelier d'Audit Interactif & Synthèse
Parcours : A 8 sessions  |  Module : Consolidation & Clôture  |  Format : Spécifications Markdown  |  Modalité : Webinaire Livestorm

> **Principe directeur** : le texte affiché reste minimal ; le contenu riche est dans les notes du présentateur, le [plan d'animation minuté](../plans-de-seance/A_S08_plan.md) et le [dossier MedDistri](../projet/A_capstone.md), qui font référence. Les numéros de sondages renvoient à la checklist Livestorm du plan (9 sondages : 3 échauffement, 4 audit, 1 objection, 1 bilan).

---

## Slide 1 : Page de garde
* **Layout** : Titre (Emphase visuelle, fond sombre)
* **Texte affiché sur la slide** :
  * **Grand Atelier d'Audit Interactif & Synthèse**
  * Parcours A — Session 08
  * *Ce soir, vous êtes le cabinet d'audit. Votre cliente : MedDistri.*
  * Nom du Mentor / IBM SkillsBuild
* **Visuels suggérés** : Dossier d'audit stylisé estampillé « CONFIDENTIEL — MedDistri » ; ambiance de mission.
* **Notes du présentateur** :
  * Ton solennel et ludique : dernière session, pas un cours — une mission.
  * Rappeler : aucun travail individuel évalué ; l'audit est collectif, voté, et mesuré par le Score de Résilience.
  * « Tapez "prêt" dans le chat si vous acceptez la mission. »

---

## Slide 2 : La mission & les règles du jeu
* **Layout** : Deux colonnes (Gauche : Objectifs, Droite : Règles + Sommaire)
* **Texte affiché sur la slide** :
  * **Votre mission** :
    * Auditer l'infrastructure de MedDistri (PME santé, 25 salariés).
    * Voter chaque décision de remédiation — la majorité l'emporte.
    * Convaincre la direction (objections métier).
    * Porter le **Score de Résilience** de 10 % à **80 % ou plus**.
  * **Le déroulé** :
    * 1. Échauffement de l'auditeur (7 min)
    * 2. Le dossier MedDistri (8 min)
    * 3. L'AUDIT : 4 décisions, 4 votes (32 min)
    * 4. Objections métier & feuille de route (20 min)
    * 5. Score final, carte du parcours & suite (18 min)
* **Visuels suggérés** : Jauge de résilience à 10 % bien visible ; icône de tampon « AUDIT ».
* **Notes du présentateur** :
  * Insister sur la mécanique : chaque bonne décision majoritaire fait monter la jauge (+25/+20/+25/+20).
  * En cas d'erreur majoritaire : « seconde délibération » après débat — l'objectif est d'apprendre, pas de sanctionner.

---

## Slide 3 : Échauffement de l'auditeur
* **Layout** : Trois sondages express
* **Texte affiché sur la slide** :
  * **⚡ Trois questions éclair — dérouillage des réflexes**
  * **📊 Sondage n°1** : Chiffrer les fichiers ET menacer de publier les données volées = ? *(double extorsion / spear-phishing / déni de service)*
  * **📊 Sondage n°2** : E-mail « le RIB a changé, payez avant midi » : votre réflexe ?
  * **📊 Sondage n°3** : Poste infecté : votre TOUT premier geste ?
* **Visuels suggérés** : Chronomètre ; trois cartes éclair révélées en rafale.
* **Notes du présentateur** :
  * ~2 min par question. Réponses : double extorsion (A1 — « MedDistri est dans la santé, comme le CHSF... ») ; canal alternatif initié par soi (A2 — « Pathé, 19,2 M€ ») ; débrancher sans éteindre (A7 — « votre vote avant/après »).
  * Rythme volontairement rapide : c'est un échauffement, pas un cours.

---

## Slide 4 : Le dossier MedDistri
* **Layout** : Fiche entreprise + inventaire des faiblesses
* **Texte affiché sur la slide** :
  * **MedDistri — distribution de matériel médical, 25 salariés, Mme Legrand (DG)**
  * *L'état des lieux (visite du [dossier complet](../projet/A_capstone.md)) :*
    * 🚪 Ports SSH (22) et RDP (3389) **ouverts sur Internet**, mot de passe `Admin@MedDistri2025`
    * 📧 Microsoft 365 **sans MFA** (« trop lourd au quotidien »)
    * 💾 Sauvegarde hebdo sur disque USB **branché en permanence**
    * 📋 **Ni PSSI, ni registre RGPD** — données nominatives de clients santé
    * 🧑‍🔧 1 technicien polyvalent, serveur dans un placard à balai
  * **💬 Dans le chat : quelle faille vous choque le plus ?**
* **Visuels suggérés** : Plan stylisé de l'entrepôt avec les points faibles épinglés en rouge ; portrait néutre de « Mme Legrand ».
* **Notes du présentateur** :
  * Raconter comme une visite client (le placard à balai, le technicien débordé) SANS commenter les failles — c'est le travail de l'auditoire.
  * Lire 4-5 réponses du chat sans valider : « gardez vos intuitions, l'audit commence. »

---

## Slide 5 : La jauge — Score de Résilience Cyber
* **Layout** : Jauge plein écran (slide réutilisée entre chaque décision)
* **Texte affiché sur la slide** :
  * **Score de Résilience Cyber de MedDistri**
  * Jauge de 0 à 100 % — position courante affichée en très grand (départ : **10 %**)
  * *Prochaine étape : décision d'audit n°[X]*
* **Visuels suggérés** : Grande jauge horizontale rouge→orange→verte ; paliers marqués à 35 %, 55 %, 80 %, 100 %.
* **Notes du présentateur** :
  * Cette slide revient après CHAQUE décision d'audit avec la jauge mise à jour (10 → 35 → 55 → 80 → 100 % si sans-faute).
  * Rituel verbal : « Décision actée. Le Score de Résilience passe à X %. Mme Legrand respire un peu mieux. »

---

## Slide 6 : Décision d'audit 1 — Les portes ouvertes
* **Layout** : Mise en situation + sondage
* **Texte affiché sur la slide** :
  * **🚪 SSH (22) et RDP (3389) exposés à tout Internet, mot de passe prévisible.**
  * **📊 Sondage n°4 — L'action prioritaire absolue ?**
    * A) Pare-feu local gratuit sur chaque poste + rotation annuelle du mot de passe
    * B) Fermer les ports 22/3389, déployer un VPN d'accès distant + MFA
    * C) Ne rien changer : les commerciaux ont besoin d'accès et le mot de passe est complexe
* **Visuels suggérés** : Porte de garage grande ouverte sur une rue passante ; scanner radar en arrière-plan.
* **Notes du présentateur** :
  * Rituel : vote 1-2 min → faire argumenter le chat AVANT de révéler → débrief ([dossier](../projet/A_capstone.md)) → jauge +25 % (35 %).
  * Débrief clé : le serveur-appât d'A3 (attaqué en minutes, vecteur n°1 selon l'ANSSI) ; `Admin@MedDistri2025` = schéma nom+année que testent tous les dictionnaires.

---

## Slide 7 : Décision d'audit 2 — Le MFA refusé
* **Layout** : Mise en situation + sondage
* **Texte affiché sur la slide** :
  * **📧 Mme Legrand craint que le MFA « ralentisse les commerciaux ».**
  * **📊 Sondage n°5 — Comment la convaincre ?**
    * A) « Selon Microsoft, le MFA bloque plus de 99,9 % des attaques automatisées — et un compte mail volé = de fausses factures envoyées à VOS clients »
    * B) Imposer un mot de passe de 30 caractères sans MFA
    * C) Menacer de couper l'accès aux récalcitrants
* **Visuels suggérés** : Balance : « 3 secondes par connexion » vs « 3 semaines d'arrêt » ; icône de fausse facture.
* **Notes du présentateur** :
  * Débrief : le phishing va plus vite que la complexité des mots de passe (A2 : < 1 minute) ; les fausses factures = mécanique Pathé — l'argument qui parle à une DG. Jauge +20 % (55 %).

---

## Slide 8 : Décision d'audit 3 — La sauvegarde piégée
* **Layout** : Mise en situation + sondage
* **Texte affiché sur la slide** :
  * **💾 Sauvegarde hebdomadaire sur un disque USB branché en permanence au serveur.**
  * **📊 Sondage n°6 — Pourquoi est-ce dangereux ?**
    * A) Le disque externe est trop lent et chauffe
    * B) En cas de ransomware, le disque connecté sera chiffré avec le serveur — sauvegarde inutile
    * C) La sauvegarde du vendredi soir fatigue le technicien
* **Visuels suggérés** : Disque USB enchaîné au serveur, tous deux verrouillés par un même cadenas de rançon.
* **Notes du présentateur** :
  * Débrief : le NAS piégé d'A4 version PME ; rappeler OVHcloud (le hors-site protège aussi du feu) et Maersk (A7 : la survie ne se confie pas au hasard). Règle 3-2-1, copie déconnectée ou immuable. Jauge +25 % (80 %).

---

## Slide 9 : Décision d'audit 4 — Les 2 000 euros
* **Layout** : Mise en situation + sondage
* **Texte affiché sur la slide** :
  * **💶 Budget cyber annuel total : 2 000 €. Une seule enveloppe, trois stratégies.**
  * **📊 Sondage n°7 — L'allocation la plus efficace ?**
    * A) Un pare-feu haut de gamme à 2 000 €, systèmes actuels inchangés
    * B) Licences VPN/MFA légères + sauvegarde cloud chiffrée + formation des collaborateurs
    * C) Un test d'intrusion complet par un cabinet externe à 2 000 €
* **Visuels suggérés** : Trois caddies : un gros équipement luxueux / un panier varié d'essentiels / une loupe d'expert.
* **Notes du présentateur** :
  * Débrief : l'hygiène avant les outils ; le pentest n'est pas inutile, il est PRÉMATURÉ (A6 : auditer des failles béantes déjà connues = payer pour apprendre ce qu'on sait) ; logique du Comité des Risques d'A5. Jauge +20 % (100 %).

---

## Slide 10 : L'objection métier — convaincre, pas imposer
* **Layout** : Mise en situation + sondage
* **Texte affiché sur la slide** :
  * **🗣️ Dernier obstacle : la directrice hésite encore sur le MFA.**
  * **📊 Sondage n°8 — L'argument le plus percutant ?**
    * A) 99,9 % des attaques automatisées bloquées (Microsoft) + « 3 secondes par jour contre 3 semaines d'arrêt »
    * B) « Le MFA est obligatoire par la loi sur les données personnelles »
    * C) « Les commerciaux n'ont pas leur mot à dire »
  * **Auditer = 50 % technique, 50 % conviction.**
* **Visuels suggérés** : Table de réunion de direction ; bulles d'argumentaire.
* **Notes du présentateur** :
  * Débrief : B est FAUX en l'état (le RGPD exige des mesures « appropriées », pas nommément le MFA — un auditeur n'invente jamais une obligation légale) ; C échoue toujours (la sécurité imposée sans adhésion est contournée).
  * L'exercice de vulgarisation managériale : bénéfice business, pas jargon.

---

## Slide 11 : La feuille de route de MedDistri
* **Layout** : Trois horizons + schéma cible
* **Texte affiché sur la slide** :
  * **La feuille de route née de VOS votes :**
    * **Mois 1 (budget ~0 €)** : fermer les ports exposés · activer le MFA · changer les mots de passe prévisibles
    * **Mois 2-3** : VPN d'accès distant · sauvegarde 3-2-1 déconnectée/immuable · registre RGPD
    * **Mois 6+** : sensibilisation continue · scans de vulnérabilités · PSSI signée · exercice de crise
  * **💬 Dans le chat : si c'était VOTRE organisation, que feriez-vous lundi matin ? (une seule mesure)**
* **Visuels suggérés** : Frise à trois horizons + schéma d'architecture cible (serveur isolé, VPN+MFA, sauvegarde hors ligne, zones cloisonnées — l'héritage d'A3).
* **Notes du présentateur** :
  * Reconstituer la feuille de route À PARTIR des votes (n°4-7) — « ce plan, c'est vous qui l'avez écrit ».
  * Lire 5-6 réponses du chat ; souligner la convergence : « vos réflexes sont installés ».

---

## Slide 12 : Le verdict — Score de Résilience final
* **Layout** : Jauge finale plein écran + tampon
* **Texte affiché sur la slide** :
  * **Score de Résilience final de MedDistri : [X] %**
  * *Départ : 10 % — Objectif : ≥ 80 %*
  * **✅ AUDIT VALIDÉ PAR LA COMMUNAUTÉ DES APPRENANTS** *(si objectif atteint)*
* **Visuels suggérés** : Jauge complète avec animation de remplissage ; tampon « VALIDÉ » ; confettis sobres.
* **Notes du présentateur** :
  * Verbatim de validation du plan : « il y a 90 minutes, cette entreprise était une statistique en puissance... elle est maintenant [X] % plus résiliente, pour moins de 2 000 €, grâce à VOS décisions. »
  * Si < 80 % : « seconde délibération » sur les décisions manquées (débat chat + re-vote), puis validation.

---

## Slide 13 : La carte du parcours & la suite
* **Layout** : Tableau de synthèse + sondage bilan
* **Texte affiché sur la slide** :
  * **8 sessions · 7 réflexes · 10 histoires vraies**
    * A1 C-I-D & risque *(CHSF, France Travail)* · A2 canal alternatif *(Pathé, Arup)* · A3 filtrer-chiffrer-cloisonner *(Target, Mirai)* · A4 MFA & 3-2-1 *(Capital One, OVHcloud)* · A5 coter & traiter *(Google, Meta)* · A6 gravité × exposition *(Equifax, Log4Shell)* · A7 isoler, jamais éteindre *(Maersk)* · A8 l'hygiène d'abord *(MedDistri)*
  * **📊 Sondage n°9** : le meilleur ROI sécurité pour une TPE/PME ? *(pare-feu à 5 000 € / mots de passe + MFA + sensibilisation / charte de 80 pages)*
  * **La suite** : badge IBM SkillsBuild · CompTIA Security+ · TryHackMe & Root-Me (pratique légale) · veille CERT-FR déjà en place
* **Visuels suggérés** : Frise des 8 sessions avec pictogrammes ; badge de fin de parcours.
* **Notes du présentateur** :
  * « Chacune de ces histoires est un argument à ressortir en réunion. »
  * Sondage n°9 : réponse B — le verdict de l'audit, généralisé ; la charte de 80 pages que personne ne lit est l'anti-PSSI (A5).
  * Détailler la suite : badge (comment le récupérer), Security+ comme premier objectif réaliste, pratique UNIQUEMENT sur plateformes dédiées (cadre légal A7).

---

## Slide 14 : Clôture & remerciements
* **Layout** : Fin de parcours
* **Texte affiché sur la slide** :
  * **🎓 Parcours A terminé — félicitations !**
  * *Vous êtes arrivés en vous demandant si la cybersécurité était pour vous. Vous repartez en ayant sécurisé une entreprise.*
  * **💬 Dans le chat : le parcours en UN mot**
  * Questionnaire de satisfaction : lien dans le chat
  * *Prenez soin de vos données — et de celles des autres.*
* **Visuels suggérés** : Badge numérique de fin de parcours ; mosaïque discrète des visuels des 8 sessions.
* **Notes du présentateur** :
  * Lire une dizaine de mots du chat à voix haute — c'est le moment d'émotion collective.
  * Coller le lien de satisfaction ; annoncer le message de clôture par e-mail (badge, ressources).
  * Terminer à l'heure exacte — la dernière impression compte double.
