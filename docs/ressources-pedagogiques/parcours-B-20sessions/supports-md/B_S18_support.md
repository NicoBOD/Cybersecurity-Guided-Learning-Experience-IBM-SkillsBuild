# Session B18 — Introduction à la réponse aux incidents
Parcours : B 20 sessions  |  Module : E — Opérations, détection & réponse  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Avant l'incident : la gestion des vulnérabilités (CVE, score CVSS, priorisation des correctifs)
    - Le cycle de réponse aux incidents : NIST SP 800-61 et PICERL (SANS)
    - Confinement, éradication, recouvrement — et la règle d'or de la RAM
    - Une affaire réelle : Equifax (2017), la faille non corrigée à 700 millions de dollars
    - La fiche réflexe (playbook) « premier répondant rançongiciel », construite ensemble
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   Un incident commence presque toujours par une **vulnérabilité** exploitée : les gérer (identifier, évaluer via **CVSS**, corriger, vérifier) est la première ligne de la préparation.
*   La réponse aux incidents est un processus normalisé : **4 phases** selon le NIST SP 800-61, détaillées en **6 étapes** par le modèle PICERL du SANS.
*   Face à un rançongiciel actif, l'urgence absolue est le **confinement** : isoler la machine du réseau — **sans l'éteindre**, pour préserver les preuves en mémoire vive (RAM).
*   Les **playbooks** (fiches réflexes) permettent de réagir de manière calme et coordonnée sous stress — c'était votre recherche de la semaine : le confinement et ses gestes techniques.

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Décrire le cycle de gestion des vulnérabilités (identification, évaluation CVSS, remédiation, vérification) et prioriser des correctifs selon la gravité ET l'exposition.
* Citer les phases du cycle de réponse aux incidents (NIST SP 800-61 / PICERL) et distinguer confinement, éradication et recouvrement.
* Appliquer les gestes du premier répondant face à un rançongiciel : isoler sans éteindre, préserver la RAM, escalader — et rédiger la fiche réflexe correspondante.

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** Combien de nouvelles vulnérabilités (CVE) ont été publiées dans le monde sur la seule année 2024 ?

    - A) Environ 4 000
    - B) Environ 15 000
    - C) Plus de 40 000 ✅

    **Débrief mentor :** Réponse C : **plus de 40 000 CVE publiées en 2024** (programme CVE / base NVD, 2024) — plus de cent par jour, un record. Personne ne peut tout corriger : la question n'est donc pas « faut-il patcher ? » mais « quoi d'abord ? ». Première partie de la session : apprendre à trier. Et comme aucun tri n'est parfait, deuxième partie : que faire quand une faille est exploitée malgré tout — la réponse aux incidents.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Lire un vecteur CVSS en 60 secondes — et ses limites**
Pour les curieux du « comment est calculé le score » : le vecteur `CVSS:3.1/AV:N/AC:L/PR:N/UI:N/...` se lit ainsi — **AV:N** (*Attack Vector: Network*) : exploitable par le réseau, donc potentiellement depuis Internet ; **AC:L** (*Attack Complexity: Low*) : exploitation facile ; **PR:N** (*Privileges Required: None*) : aucun compte nécessaire ; **UI:N** (*User Interaction: None*) : aucune action de la victime requise. Ce quatuor au pire niveau + impacts C/I/A élevés ≈ score 9.8+, le profil « ver » (WannaCry, B03). Précisions utiles : CVSS **4.0** existe (publié fin 2023), la 3.1 reste la plus rencontrée ; et le score de base ne dit PAS si la faille est réellement exploitée — d'où les compléments : le catalogue **KEV** de la CISA (vulnérabilités exploitées constatées) et **EPSS** (probabilité d'exploitation). Priorité pratique : d'abord ce qui est exploité (KEV), puis le CVSS pondéré par l'exposition de VOS actifs — c'est le score environnemental, et c'est l'activité de ce soir.

**2. NIST SP 800-61 et PICERL : deux découpages, un même cycle**
Rigueur terminologique pour les questions pointues : le NIST SP 800-61 r2 définit **4 phases** (Préparation ; Détection & Analyse ; Confinement-Éradication-Recouvrement en une seule phase, car on itère entre les trois ; Activité post-incident). Le modèle **PICERL** du SANS déplie les mêmes réalités en **6 étapes** (Preparation, Identification, Containment, Eradication, Recovery, Lessons learned) — c'est le moyen mnémotechnique le plus répandu. À noter : la **révision 3** du SP 800-61 (avril 2025) réorganise le guide autour des fonctions du CSF 2.0 (B13) — le cycle opérationnel reste le socle pédagogique. Point d'insistance : la phase la plus sautée est la dernière (le REX), et c'est la plus rentable — sans elle, on se fait repirater par la même porte.

**3. L'ordre de volatilité : pourquoi la RAM d'abord**
Si l'on veut des preuves exploitables (et opposables : plainte, assurance — B13/B14), on collecte du plus volatil au plus stable : **RAM** (processus actifs, connexions en cours, parfois clés de chiffrement du rançongiciel) → état réseau et tables systèmes → disques (copie bit à bit, jamais l'original) → sauvegardes et journaux déportés (B17, les pièces à conviction déjà en lieu sûr). D'où les deux interdits du premier répondant : ne pas éteindre (la RAM s'évapore), ne pas « nettoyer » ou formater (on détruit la scène de crime). Rappels juridiques français utiles : conserver la chronologie factuelle (qui a fait quoi, quand), déposer plainte — et depuis la LOPMI (2023), l'indemnisation assurantielle d'une cyberattaque est conditionnée à une plainte sous **72 heures** (B02).

---

### Glossaire

*   **CVE (Common Vulnerabilities and Exposures)** — Répertoire public attribuant un identifiant unique à chaque vulnérabilité logicielle connue (ex. CVE-2021-44228, alias Log4Shell).
*   **CVSS (Common Vulnerability Scoring System)** — Standard industriel évaluant de 0 à 10 la sévérité technique d'une vulnérabilité.
*   **CWE (Common Weakness Enumeration)** — Dictionnaire catégorisant les types de faiblesses de conception ou de code à l'origine des failles (ex. CWE-89 : injection SQL).
*   **Mémoire volatile (RAM)** — Mémoire de travail effacée dès que l'alimentation est coupée — et qui contient les preuves les plus précieuses d'une attaque en cours.
*   **Mesure compensatoire (Mitigation)** — Parade temporaire (règle de pare-feu, désactivation d'un service, filtrage WAF) réduisant le risque en attendant l'application du correctif.
*   **NIST SP 800-61** — Guide de référence de la gestion des incidents de sécurité (4 phases) ; le modèle PICERL du SANS en est le découpage en 6 étapes.
*   **Patch (Correctif de sécurité)** — Mise à jour publiée par un éditeur pour combler une faille identifiée.
*   **Playbook (Fiche réflexe)** — Procédure documentée détaillant pas à pas les actions à mener face à un type d'incident spécifique.
*   **REX (Retour d'expérience)** — Analyse post-incident des défaillances du processus de réponse, pour s'améliorer — l'étape la plus négligée et la plus rentable.
*   **Zero-day (0-day)** — Vulnérabilité inconnue de l'éditeur, donc sans correctif : « zéro jour » pour préparer la défense.

---

### Concepts clés

!!! info "À retenir"
    Tout se tient : les vulnérabilités non corrigées ouvrent la porte (Equifax), la détection lit les traces (B16-B17), et la réponse aux incidents transforme la panique en procédure. Les deux gestes qui sauvent : **isoler sans éteindre**, et **apprendre de chaque incident** (REX).

### 1. Avant l'incident : gérer les vulnérabilités
Un incident de sécurité commence presque toujours par une faille exploitée. La **gestion des vulnérabilités** est donc le versant préventif de la réponse aux incidents — la phase « Préparation » du cycle NIST commence ici. C'est un processus **continu**, en 4 étapes :

1.  **Identification** : des scanners automatisés (Nessus, OpenVAS…) inventorient les failles présentes sur le parc, en croisant les logiciels installés avec la base mondiale des **CVE**.
2.  **Évaluation** : chaque faille reçoit un score **CVSS** de 0 à 10 (10 = critique). Mais le score technique ne suffit pas : une faille critique sur un serveur de test isolé pèse moins qu'une faille moyenne sur le serveur exposé sur Internet — c'est le **contexte** (l'exposition de l'actif) qui fait la priorité, exactement comme la criticité V×G de B14.
3.  **Remédiation** : appliquer le **correctif** (la solution définitive) ; si c'est impossible immédiatement (risque de casser la production), poser une **mesure compensatoire** (règle de pare-feu, filtrage WAF, désactivation du service) en attendant ; dans certains cas résiduels, **accepter** le risque — formellement (B14).
4.  **Vérification** : re-scanner pour confirmer que la faille est bien fermée. Sans vérification, pas de gestion — des correctifs « appliqués » échouent silencieusement plus souvent qu'on ne croit.

**Le cas limite : la faille zero-day.** Inconnue de l'éditeur, sans correctif disponible — l'antivirus par signature ne la voit pas. Les parades sont architecturales : défense en profondeur, analyse comportementale (EDR, B08), segmentation (B06) pour confiner ce qu'on ne peut pas empêcher.

### Activité — Le comité de priorisation des correctifs (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Vous êtes le comité sécurité d'EcoLog. Trois dossiers arrivent ; pour chacun, affichez le contexte, laissez 30 secondes de lecture, lancez le vote, débriefez.

*   **📊 Sondage n°2 — Dossier A :** Faille **CVSS 9.8** (exploitable depuis Internet, sans compte requis) sur le serveur web de la boutique en ligne, **exposé sur Internet**. Un correctif est disponible. Votre décision ?
    *   A) Corriger en urgence absolue, sous 24 h ✅
    *   B) Attendre la maintenance mensuelle planifiée
    *   C) Accepter le risque : le serveur n'a jamais été attaqué
*   **📊 Sondage n°3 — Dossier B :** La **même faille CVSS 9.8**, mais sur un serveur de **test**, isolé du réseau, sans donnée réelle. Votre décision ?
    *   A) Urgence absolue sous 24 h, comme le dossier A
    *   B) Priorité normale : correction lors d'une fenêtre planifiée ✅
    *   C) Débrancher définitivement le serveur
*   **📊 Sondage n°4 — Dossier C :** Faille critique sur le **logiciel métier de facturation** ; l'éditeur fournit un correctif, mais l'appliquer sans test risque de bloquer la facturation. Votre décision ?
    *   A) Ne jamais appliquer ce correctif : la production d'abord
    *   B) Poser immédiatement une mesure compensatoire (filtrage réseau/WAF), tester le correctif, puis le déployer vite ✅
    *   C) Forcer le déploiement immédiat sur tous les serveurs en pleine journée

**Éléments de débriefing (pour le mentor) :**

- N°2 : le pire profil au pire endroit — CVSS critique **et** exposition maximale : c'est la définition de la priorité 1. C'est exactement le dossier qu'Equifax a laissé traîner (l'affaire arrive dans dix minutes).
- N°3 : même score technique, contexte opposé — le score **environnemental** en action : la gravité intrinsèque ne change pas, la priorité si. Répondre A partout, c'est épuiser les équipes et ne plus savoir trier (la fatigue des alertes de B16, version patching).
- N°4 : le faux dilemme « sécurité OU production » se résout par la séquence : compenser tout de suite, tester vite, déployer vite. A laisse la porte ouverte indéfiniment ; C transforme un risque cyber en panne certaine.

### 2. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **Plus de 40 000** vulnérabilités (CVE) publiées sur la seule année 2024, un record (programme CVE / base NVD, 2024).
    - L'exploitation de vulnérabilités comme porte d'entrée initiale a presque **triplé en un an** (rapport Verizon DBIR, 2024 — dopée notamment par l'affaire MOVEit).
    - **147 millions** de personnes touchées par la violation Equifax de 2017 ; accord avec les autorités américaines pouvant atteindre **700 M$** (FTC, 2019).
    - **CVSS 10.0** : le score maximal attribué à Log4Shell (CVE-2021-44228, décembre 2021) — une bibliothèque présente dans d'innombrables logiciels.

**Comment lire ces chiffres ?** (1) Plus de cent failles publiées par jour : la question n'est pas de tout corriger, mais de corriger la bonne faille au bon endroit d'abord. (2) Les attaquants industrialisent l'exploitation (DBIR) : le délai entre publication d'une faille et attaques massives se compte désormais en jours. (3) Equifax le montre : une seule faille connue, avec correctif disponible, non appliqué — et c'est l'une des violations les plus coûteuses de l'histoire.

### 3. Une affaire réelle : Equifax (2017) — la faille connue que personne n'a corrigée

Mars 2017 : une faille critique du framework web **Apache Struts** (CVE-2017-5638) est publiée, correctif disponible le jour même. Chez **Equifax**, l'un des trois grands bureaux de crédit américains (il détient les données financières de la moitié du pays), la consigne interne de patcher est envoyée… mais le serveur vulnérable — le portail de contestation des litiges — n'est **jamais corrigé**, et le scan de vérification ne le repère pas. Mi-mai, des attaquants entrent par cette porte. Ils restent **76 jours** : le dispositif qui inspectait le trafic chiffré était hors service depuis des mois à cause d'un **certificat expiré** — l'exfiltration est passée sous les radars (la leçon de B17, encore). Bilan : les données de **147 millions de personnes** (numéros de sécurité sociale, dates de naissance, adresses), un accord avec la FTC et les autorités pouvant atteindre **700 M$** (2019), la démission du PDG, du DSI et du RSSI.

**Ce que ce cas illustre :** chaque étape du cycle a cassé — l'identification (l'inventaire ne savait pas où Struts tournait), la remédiation (consigne envoyée ≠ correctif appliqué), la **vérification** (le re-scan a raté le serveur) ; puis la détection a cassé aussi (un certificat expiré = 76 jours d'aveuglement) ; et la réponse enfin (communication de crise désastreuse — site d'information bricolé, dirigeants ayant vendu des actions avant l'annonce). Une chaîne de petites négligences ordinaires, pas un exploit de génie.

**Le stress test mondial — Log4Shell (décembre 2021).** Une faille **CVSS 10.0** (CVE-2021-44228) dans **Log4j**, bibliothèque de journalisation utilisée dans d'innombrables logiciels : exploitable à distance, sans compte, trivialement. En un week-end, toutes les équipes de sécurité du monde ont vécu le même scénario : *où* utilise-t-on Log4j (l'inventaire ! — souvent introuvable), mesures compensatoires immédiates (règles WAF, désactivation de la fonction vulnérable), puis campagne de correctifs sous surveillance du CERT-FR et de l'ANSSI. La leçon : la gestion des vulnérabilités vit ou meurt par l'**inventaire** — on ne protège que ce qu'on sait posséder (le tout premier contrôle de toute démarche sécurité, depuis A01).

### 4. Quand l'incident survient : le cycle de réponse (NIST SP 800-61 / PICERL)

Faire face à une cyberattaque ne s'improvise pas. Le guide **NIST SP 800-61** structure la réponse en **4 phases** ; le moyen mnémotechnique le plus répandu, **PICERL** (SANS), déplie les mêmes réalités en 6 étapes :

```text
NIST SP 800-61 (4 phases)          PICERL / SANS (6 étapes)
─────────────────────────          ────────────────────────
1. Préparation                     P — Preparation
2. Détection & Analyse             I — Identification
3. Confinement, Éradication   ┌──  C — Containment (confinement)
   & Recouvrement (une phase, ├──  E — Eradication (éradication)
   car on itère entre les 3)  └──  R — Recovery (recouvrement)
4. Activité post-incident          L — Lessons learned (REX)
        └────────────── et le cycle recommence ──────────────┘
```

1.  **Préparation** : sauvegardes testées et hors ligne (B12), playbooks rédigés, rôles définis, gestion des vulnérabilités active — tout ce qui précède.
2.  **Détection & Analyse** : les alertes du SOC (B16) et les journaux (B17) : qualifier, évaluer la sévérité, comprendre la nature de l'attaque.
3.  **Confinement → Éradication → Recouvrement** : le cœur opérationnel, détaillé ci-dessous.
4.  **Post-incident (REX)** : analyser les défaillances, corriger la faille d'origine, mettre à jour PSSI (B13) et playbooks. L'étape la plus négligée — et la seule qui empêche de revivre le même incident le mois suivant.

#### Confinement, éradication, recouvrement — l'analogie de l'incendie de cuisine
*   **Confinement** : on stoppe l'hémorragie — isoler les machines compromises pour protéger le reste (fermer la porte de la cuisine pour contenir les flammes). *Rappel de vos recherches : débrancher le câble, couper le Wi-Fi, VLAN d'isolement, règle de pare-feu.*
*   **Éradication** : on assainit — supprimer les malwares ET les portes dérobées laissées par l'attaquant, fermer les comptes compromis, corriger la faille exploitée (éteindre le feu à sa source et retirer les débris).
*   **Recouvrement** : on redémarre — restaurer depuis des sauvegardes saines (B12), valider, remettre en production **progressivement et sous surveillance renforcée** (nettoyer la suie, repeindre, remplacer la cuisinière).

### 5. Préservation des preuves : la règle d'or de la RAM

Face à des fichiers qui se chiffrent en direct, le réflexe instinctif est d'éteindre la machine. C'est précisément **l'erreur à ne pas commettre** :

!!! warning "Ne jamais éteindre brutalement une machine compromise !"
    *   **La RAM est volatile** : l'extinction efface définitivement les processus malveillants actifs, les connexions réseau en cours, les adresses des attaquants — et parfois **la clé de chiffrement du rançongiciel** encore en mémoire.
    *   **Le redémarrage peut aggraver** : certains malwares profitent du redémarrage pour chiffrer les fichiers de démarrage et rendre la machine définitivement inutilisable.
    *   **La bonne pratique** : **isoler du réseau** (câble débranché, Wi-Fi coupé) mais **laisser la machine allumée**, pour que les experts puissent extraire la mémoire vive.

L'investigation collecte les preuves du plus volatil au plus stable (l'**ordre de volatilité**) : RAM → état réseau → disques (copie, jamais l'original) → journaux déportés (déjà en lieu sûr grâce à B17). Ces preuves servent l'enquête technique, la plainte (sous 72 h pour l'indemnisation assurantielle — LOPMI 2023, vue en B02) et l'assurance (B14).

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Lundi, 10h04. Un utilisateur appelle le support, paniqué : « mon écran affiche une demande de rançon, les fichiers du service changent d'extension les uns après les autres ! » Vous êtes le technicien helpdesk. **Tapez A, B ou C dans le chat :**

    - A) Lui dire d'éteindre immédiatement l'ordinateur pour stopper le chiffrement.
    - B) Lui faire débrancher le câble réseau et couper le Wi-Fi, exiger que la machine reste ALLUMÉE, puis escalader immédiatement au responsable sécurité. ✅
    - C) Lui demander de redémarrer pour voir si le problème persiste.

    **Débrief mentor :** B — les trois gestes dans l'ordre : isoler (stopper la propagation vers les partages réseau), préserver (la RAM reste sous tension), escalader (le helpdesk n'investigue pas, il alerte). A détruit les preuves et peut-être la clé de déchiffrement ; C peut déclencher le chiffrement du démarrage. Ce script de 30 secondes, c'est exactement ce qu'un playbook met par écrit — on le rédige ensemble maintenant.

### Activité — La fiche réflexe « premier répondant rançongiciel », construite ensemble (chat)

**Consignes pour le mentor :** demandez au chat : « *dans l'ordre, quelles sont les 5 étapes que le technicien helpdesk doit dérouler au téléphone ?* » Récoltez, reformulez, écrivez la fiche en direct — puis affichez le modèle :

```text
FICHE RÉFLEXE : SIGNALEMENT DE RANÇONGICIEL (HELPDESK)
--------------------------------------------------------------------------------
DÉCLENCHEUR : écran de rançon, ou fichiers illisibles avec extension inhabituelle.

Étape 1 : ISOLER DU RÉSEAU (action immédiate de l'utilisateur)
-> Débrancher le câble Ethernet, couper le Wi-Fi (mode avion).
   Pourquoi ? Stopper la propagation vers les serveurs et partages de fichiers.

Étape 2 : MAINTENIR L'ALIMENTATION
-> Ordonner formellement : NE PAS éteindre, NE PAS redémarrer.
   Pourquoi ? Préserver la RAM (preuves, connexions actives, parfois la clé).

Étape 3 : COLLECTER LES PREMIÈRES INFORMATIONS
-> Heure exacte des premiers symptômes ; photo de l'écran de rançon
   (téléphone personnel, envoi par un canal secondaire) ; derniers fichiers
   ou pièces jointes ouverts avant le blocage.

Étape 4 : ESCALADER (alerte sécurité)
-> Ticket prioritaire [CRITIQUE - RANÇONGICIEL] + appel direct au RSSI /
   à l'astreinte SOC, avec IP de la machine, nom d'utilisateur, photo.

Étape 5 : CONSIGNER
-> Compte rendu factuel horodaté : heure de l'appel, actions menées,
   heure d'isolement. (Cette chronologie servira à l'enquête et à la plainte.)
```

**Éléments de débriefing :** une bonne fiche réflexe se reconnaît à trois qualités : **zéro jargon** (elle sera lue sous stress par un non-expert), **des interdits explicites** (ne pas éteindre, ne pas payer, ne pas « nettoyer »), **une escalade nominative** (qui appeler, à quel numéro). Rappelez la position constante de l'ANSSI : ne pas payer la rançon (B02) — payer finance l'écosystème et ne garantit rien.

!!! tip "📊 Sondage Livestorm n°5 — Et chez vous ? (sondage d'opinion, pas de bonne réponse)"
    **Question :** Votre organisation dispose-t-elle d'un plan de réponse aux incidents ?

    - A) Oui, et il est testé régulièrement (exercices)
    - B) Oui, sur le papier — jamais testé
    - C) Non / Je ne sais pas

    **Débrief mentor :** Sondage d'opinion — mais un repère : un plan jamais testé est une hypothèse, pas un plan (B croise les doigts). Les organisations dotées d'une équipe de réponse ET de plans testés économisent significativement sur le coût des violations (c'est un résultat récurrent des rapports IBM *Cost of a Data Breach*). La bonne nouvelle : le test se fait sans risque, sur table — c'est exactement le programme de la semaine prochaine (B19).

---

### Questions de réflexion
1. Pourquoi la phase « post-incident » (REX) est-elle si souvent sacrifiée une fois la production rétablie ? Quel est le risque concret de la sauter ?
2. Une entreprise restaure ses serveurs depuis les sauvegardes de la veille sans avoir identifié la vulnérabilité d'origine. Que risque-t-il de se passer dans les heures qui suivent ?
3. Chez Equifax, la consigne de patcher avait bien été envoyée en interne. Citez au moins deux maillons du cycle de gestion des vulnérabilités qui ont malgré tout cédé.

**Corrigé / Éléments de réponse :**

1. Épuisement des équipes, pression pour « passer à autre chose », peur des responsabilités individuelles. Risque : les mêmes failles de processus demeurent — on revit le même incident, parfois avec le même attaquant (qui a pu laisser des accès).
2. L'attaquant réutilise immédiatement la même faille (toujours ouverte) pour repirater les systèmes fraîchement restaurés — l'éradication exige de corriger la cause, pas seulement de restaurer les données.
3. L'inventaire (personne ne savait précisément où Struts tournait), l'application effective du correctif (consigne ≠ action), et la **vérification** (le re-scan n'a pas détecté le serveur toujours vulnérable). S'y ajoute la détection : 76 jours d'exfiltration invisibles à cause d'un certificat expiré.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Deux images pour la session :
    - **La gestion des vulnérabilités, c'est l'entretien de la plomberie d'un immeuble** : l'inspection trouve les fuites (scan → CVE), la gravité se juge par le tuyau concerné — la conduite principale du sous-sol (CVSS 9.8 exposé sur Internet) avant le robinet qui goutte dans un bureau vide (CVSS 3.0 isolé) —, on répare (patch) ou on pose un collier de serrage temporaire (mesure compensatoire), puis on rouvre l'eau en vérifiant (re-scan).
    - **La réponse à incident, c'est l'incendie de cuisine** : fermer la porte (confinement), éteindre à la source et déblayer (éradication), nettoyer et remplacer la cuisinière (recouvrement) — puis comprendre pourquoi le feu a pris, pour que ça ne recommence pas (REX).

**Exemple d'application professionnelle :**
Un scanner remonte une faille critique d'exécution de code à distance (CVE-2021-44228, Log4Shell) sur plusieurs serveurs. Grâce au score CVSS croisé avec l'exposition Internet de chaque machine, l'équipe pose une règle WAF le soir même (mesure compensatoire), patche le serveur exposé en moins de 24 h, puis traite le parc interne en fenêtres planifiées — et vérifie chaque correction par un re-scan.

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour cartographier les vulnérabilités du parc et outiller la réponse :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Tenable Nessus / Tenable One** : référence du scan et du management de vulnérabilités (CVE et défauts de configuration).
    *   **Qualys VMDR** : plateforme SaaS de détection des vulnérabilités et de priorisation des correctifs.
    *   **Rapid7 InsightVM** : évaluation continue de l'exposition, corrélée aux menaces actives.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **Greenbone Community Edition (OpenVAS)** : scanner de vulnérabilités open-source complet.
    *   **Wazuh** : détecte les vulnérabilités en corrélant l'inventaire logiciel des agents avec la base CVE — et sert déjà de SIEM (B17).
    *   **TheHive** : console open-source de gestion des incidents (tickets, tâches, preuves) pour outiller le cycle de réponse.

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après le sondage d'opinion.

*   **📊 Sondage n°6 :** Quelle est la différence entre une CVE et une CWE ?
    *   A) Aucune : deux noms pour la même chose
    *   B) La CVE identifie une faille précise d'un produit précis ; la CWE décrit la catégorie de faiblesse sous-jacente ✅
    *   C) La CVE concerne le matériel, la CWE le logiciel
*   **📊 Sondage n°7 :** Un rançongiciel actif est confirmé sur un poste. Quel est le premier geste ?
    *   A) Éteindre le poste pour stopper le chiffrement
    *   B) Lancer immédiatement la restauration des sauvegardes
    *   C) Isoler le poste du réseau (câble, Wi-Fi) en le laissant allumé ✅
*   **📊 Sondage n°8 :** Pourquoi ne faut-il jamais éteindre électriquement une machine compromise ?
    *   A) Parce que la mémoire vive (RAM), volatile, contient des preuves — et parfois la clé de chiffrement ✅
    *   B) Parce que cela endommage le disque dur
    *   C) Parce que c'est interdit par le RGPD

**Éléments de débriefing (pour le mentor) :**

- N°6 : l'analogie médicale — la CWE est la maladie en général (l'injection SQL), la CVE est le cas déclaré chez un patient précis (telle faille de tel produit).
- N°7 : confiner d'abord — la propagation vers les partages réseau coûte plus cher que tout le reste ; la restauration (B) vient APRÈS l'éradication, sinon on restaure dans un environnement encore piégé.
- N°8 : l'ordre de volatilité — on collecte du plus fragile au plus stable ; éteindre, c'est passer l'éponge sur la scène de crime.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Incident Response Fundamentals"* (durée estimée : 1h30).
*   **Étude documentaire** : Consulter la base **NVD** (*National Vulnerability Database*) et rechercher la fiche de la faille *Log4Shell* (CVE-2021-44228) pour voir une fiche de vulnérabilité réelle ; parcourir les guides de gestion de crise cyber publiés par l'ANSSI.
*   [ANSSI — Gestion des incidents cyber](https://cyber.gouv.fr)
*   [Cybermalveillance — Victime d'une attaque](https://www.cybermalveillance.gouv.fr)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Arbitrer sécurité et disponibilité dans le déploiement des correctifs.
*   **📊 Sondage Livestorm n°9 :** L'éditeur d'un logiciel métier publie un correctif de sécurité urgent. Le technicien refuse de l'installer immédiatement par crainte de bloquer la production. Quelle est la meilleure approche ?
    *   A) Ne jamais installer la mise à jour, pour préserver la stabilité
    *   B) Tester le correctif sur un périmètre pilote pendant 24 h, puis déployer largement ✅
    *   C) Forcer le déploiement sur tous les serveurs à 14 h sans prévenir les équipes
*   **Guide d'animation (pour le mentor) :** le compromis permanent sécurité/disponibilité se résout par la méthode, pas par le dogme : périmètre pilote, fenêtre courte, déploiement en anneaux — et mesure compensatoire en attendant si la faille est exploitée (rappel du sondage n°4). Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Cycle des vulnérabilités** | Identifier (scan/CVE) → évaluer (CVSS + exposition) → remédier (patch ou compensation) → **vérifier**. |
| **CVE / CWE / CVSS** | La faille précise / la catégorie de faiblesse / le score de gravité 0-10. |
| **Priorisation** | Gravité × exposition : critique + exposé Internet = 24 h ; même faille isolée = fenêtre planifiée. |
| **Zero-day** | Sans correctif : parades architecturales (EDR comportemental, segmentation, défense en profondeur). |
| **NIST SP 800-61 / PICERL** | 4 phases / 6 étapes : préparer, détecter, confiner-éradiquer-recouvrer, apprendre (REX). |
| **Confinement** | Isoler du réseau SANS éteindre — stopper la propagation, préserver la RAM. |
| **Règle d'or de la RAM** | La mémoire volatile contient preuves et parfois la clé : on ne coupe jamais l'alimentation. |
| **Playbook** | La fiche réflexe : zéro jargon, interdits explicites, escalade nominative. |

**La règle d'or de la session :** avant l'incident, corrigez la bonne faille au bon endroit d'abord (gravité × exposition) ; pendant l'incident, isolez sans éteindre et escaladez ; après l'incident, faites le REX — Equifax rappelle qu'une seule faille connue non corrigée, et une chaîne de petites négligences, suffisent à tout perdre.
