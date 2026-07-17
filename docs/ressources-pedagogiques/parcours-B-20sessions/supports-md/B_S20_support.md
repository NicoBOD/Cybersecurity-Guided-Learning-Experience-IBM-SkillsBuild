# Session B20 — Grand Atelier d'Audit Interactif & Clôture du Parcours
Parcours : B 20 sessions  |  Module : Consolidation & Évaluation  |  Niveau : Intermédiaire / Avancé  |  Format : Webinaire Livestorm (1h30) — session finale, 100 % atelier

---

!!! abstract "Résumé"
    Ce document synthétise la session de clôture du Parcours B. Vous y découvrirez :
    - Le **Grand Atelier d'Audit MedDistri** : six décisions d'audit votées en direct, un incident en cours de séance, un score de résilience collectif
    - Le principe clé de la restitution managériale : traduire la technique en risque d'entreprise
    - Le bilan du parcours (modules A à E) et la suite : certifications, laboratoires d'entraînement, veille
    La session mobilise l'ensemble des 19 sessions précédentes — c'est l'examen de sortie, en équipe et sans note.

---

## 1. Introduction

Cette vingtième session clôt le Parcours B. Pas de soutenance : un **Grand Atelier d'Audit Interactif** mené en direct sur Livestorm. Vous êtes collectivement le consultant sécurité de **MedDistri**, PME de 25 salariés distribuant des dispositifs médicaux : six décisions d'audit à voter, un incident qui se déclenche en cours de séance, et un **score de résilience** qui progresse à chaque bonne décision. Chaque vulnérabilité de MedDistri est la copie d'une affaire réelle étudiée dans ce parcours — et chaque bonne réponse, la leçon qu'une vraie entreprise a payée cher.

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Évaluer l'architecture technique, les identités, les sauvegardes et la gouvernance d'une PME, et voter des arbitrages de sécurité argumentés (coût, productivité, risque).
* Réagir à un incident rançongiciel en direct : confinement, préservation des preuves, communication de crise.
* Traduire un constat technique en risque d'entreprise (financier, juridique, réputationnel) pour convaincre une direction — et planifier la suite de votre montée en compétences.

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** Selon une étude Microsoft (2019), quelle proportion des attaques par compromission de compte l'activation de l'authentification multifacteur (MFA) permet-elle de bloquer ?

    - A) Environ 50 %
    - B) Environ 80 %
    - C) Plus de 99 % ✅

    **Débrief mentor :** Réponse C : **plus de 99 %** (étude Microsoft, 2019) — le meilleur rapport protection/effort de toute la cybersécurité. Gardez ce chiffre en tête : dans une heure, la directrice de MedDistri vous expliquera que le MFA « fait perdre du temps aux commerciaux », et il faudra la convaincre. Bienvenue dans votre dernier exercice : aujourd'hui, vous n'apprenez plus — vous auditez.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. La restitution managériale : traduire la technique en risque**
Le fil rouge des débriefs : un Comex ne comprend ni les adresses IP ni les scores CVSS — il comprend l'argent, le droit et la réputation. Entraînez l'auditoire à traduire chaque constat : « injection SQL sur le serveur web » → « vol possible de l'intégralité du fichier clients : notification CNIL, amende potentielle, perte de confiance » ; « RDP exposé sans MFA » → « un attaquant entre et se propage en une heure environ (breakout time ~62 min — CrowdStrike 2024) : arrêt d'activité complet » ; « sauvegarde USB branchée en permanence » → « en cas de rançongiciel, la sauvegarde est chiffrée AVEC les données : c'est l'existence de l'entreprise qui est en jeu ». La compétence finale du parcours n'est pas technique : c'est cette traduction.

**2. Animer le score de résilience**
Le dispositif pédagogique : MedDistri part avec un score de **10 %** ; chaque décision majoritairement correcte ajoute des points (barème indicatif : +11 points par bonne décision collective sur les 6 votes d'audit, ajustez à la volée) ; le **Label de Résilience Cyber** est décerné si le score final dépasse **75 %**. Deux conseils d'animation : faire argumenter le chat AVANT chaque vote (les débats valent mieux que les scores), et relier chaque décision au cas réel du parcours (le tableau « MedDistri en miroir » ci-dessous) — la mémoire épisodique des affaires ancre les réflexes bien mieux que les définitions.

**3. Et après ? Certifications, laboratoires, métiers**
Pour les 30 dernières minutes et les questions individuelles : côté **certifications**, la marche d'entrée est CompTIA **Security+** (généraliste, accessible après ce parcours), puis selon l'orientation CEH (test d'intrusion) ou, avec environ cinq ans d'expérience professionnelle, CISSP (management de la sécurité) ; côté **pratique**, les laboratoires en ligne TryHackMe (guidé, parfait après ce parcours) et **Hack The Box** (plus exigeant) permettent de manipuler légalement ; côté **veille**, les bulletins du CERT-FR (l'abonnement pris en B02 !), et les rapports annuels cités tout au long du parcours (panorama ANSSI, DBIR Verizon, Cost of a Data Breach IBM) ; côté **métiers**, les portes d'entrée classiques : analyste SOC L1 (B16), technicien support sécurité, assistant RSSI — le parcours donne le socle et le vocabulaire d'entretien.

---

### Glossaire

*   **Audit de sécurité** — Évaluation formelle de la conformité et des vulnérabilités d'un système d'information, aboutissant à des constats et un plan de remédiation.
*   **CERT-FR** — Centre gouvernemental de veille, d'alerte et de réponse aux attaques informatiques, rattaché à l'ANSSI.
*   **Durcissement (Hardening)** — Réduction de la surface d'attaque d'un système : fermer les services inutiles, chiffrer, filtrer, authentifier fort.
*   **Plan de remédiation** — Document ordonnant les mesures correctives (techniques et organisationnelles) par priorité : criticité × effort.
*   **Playbook d'incident** — Fiche réflexe décrivant pas à pas confinement, éradication et restauration pour un type de menace donné.
*   **Veille (cyber)** — Suivi continu des vulnérabilités, menaces et alertes (bulletins CERT-FR, rapports annuels) — l'hygiène informationnelle du professionnel.

---

### Concepts clés

!!! info "À retenir"
    L'audit final ne teste pas votre mémoire : il teste vos **réflexes**. Chaque décision de ce soir a été apprise dans une session — et payée, dans la vraie vie, par une entreprise réelle. Si le réseau plat, le RDP ouvert, la sauvegarde USB et l'absence de MFA vous font désormais bondir : le parcours a fonctionné.

### 1. Le diagnostic MedDistri : cinq vulnérabilités, cinq affaires réelles

Le détail du cas et les six votes sont dans le [dossier de l'atelier](../projet/B_capstone.md). L'infrastructure de départ :

*   **Réseau à plat** : postes, serveurs sensibles et Wi-Fi visiteurs sur le même réseau.
*   **Accès externes ouverts** : RDP (3389) et SSH (22) exposés sur l'IP publique, mot de passe administrateur faible (`Admin@MedDistri2025`).
*   **Identités sans MFA** : Microsoft 365 (RH, comptabilité) protégé par mot de passe seul.
*   **Sauvegarde vulnérable** : disque USB branché en permanence au serveur de fichiers.
*   **RGPD ignoré** : données médicales indirectes non chiffrées, pas de registre des traitements.

#### MedDistri en miroir : chaque faille a déjà tué une vraie entreprise

| Vulnérabilité MedDistri | L'affaire réelle qui l'a prouvée | Session |
| :--- | :--- | :--- |
| Réseau à plat, aucun cloisonnement | Target (2013) : du prestataire de climatisation aux caisses | B06 |
| RDP/SSH exposés, mot de passe faible | Le vecteur n°1 des rançongiciels sur les PME (constats ANSSI récurrents) | B05, B08 |
| Pas de MFA sur la messagerie cloud | Colonial Pipeline (2021) : un VPN sans MFA ; Uber (2022) : la fatigue MFA | B08, B09 |
| Sauvegarde USB branchée en permanence | Les attaques ciblent d'abord les sauvegardes (Veeam, 2023) ; OVHcloud (2021) : le hors-site | B12 |
| Données sans registre ni chiffrement | Google/CNIL (2019), Clearview AI : le RGPD s'applique — et sanctionne | B15 |

### 2. Les deux temps forts de l'atelier

*   **L'audit (votes n°2 à n°7)** : six décisions — segmentation, filtrage, chiffrement des portables, sauvegarde 3-2-1, puis, **en cours de séance, l'incident se déclenche** : un rançongiciel chiffre la comptabilité (confinement ? communication ?). Tout le parcours en six votes.
*   **Le débat (vote n°8)** : la directrice objecte — « le MFA fait perdre du temps aux commerciaux ». L'exercice final de restitution managériale : trouver l'argument qui convainc une direction (indice : le chiffre du sondage n°1).

### 3. Les chiffres du parcours (rappel de synthèse)

!!! info "Chiffres clés à retenir (sources et années citées)"
    Les repères sourcés qui ont jalonné le parcours — votre boîte à arguments pour convaincre une direction :

    - **Plus de 99 %** des attaques par compromission de compte bloquées par le MFA (Microsoft, 2019).
    - **62 minutes** en moyenne entre l'intrusion et le début de la propagation (CrowdStrike, 2024) — B16.
    - **258 jours** en moyenne pour identifier puis contenir une violation (IBM, *Cost of a Data Breach*, 2024) — B17.
    - **Plus de 9 attaques sur 10** par rançongiciel ciblent aussi les sauvegardes (Veeam, *Ransomware Trends*, 2023) — B12.
    - **2,66 M$** d'économie moyenne avec une équipe de réponse et un plan testé (IBM, 2022) — B19.
    - Sanctions RGPD jusqu'à **20 M€ ou 4 % du CA mondial** (règlement européen, applicable depuis 2018) — B15.

**Comment lire ces chiffres ?** Ensemble, ils racontent l'argumentaire complet du consultant : l'attaquant va vite (62 min), la victime est lente (258 jours), la parade la plus rentable est simple (MFA), la dernière ligne de défense est visée (sauvegardes), la préparation rapporte (2,66 M$) et l'inaction coûte aussi en amendes (RGPD).

!!! question "💬 Question chat — Le module qui vous a marqué"
    **Dans le chat :** de B01 à B19, quelle session, quelle affaire réelle ou quel réflexe vous a le plus marqué — celui que vous raconterez à un collègue dès demain ?

    **Éléments de débriefing :** récolter et rebondir — c'est le RETEX du parcours. Les réponses fréquentes (le CHSF, « isoler sans éteindre », le contre-appel, la règle 3-2-1) montrent ce qui restera dans dix ans : des histoires et des réflexes, pas des définitions.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    L'audit est terminé, le plan de remédiation est validé. La directrice de MedDistri conclut, soulagée : « parfait — donc une fois tout cela en place, nous serons tranquilles pour cinq ans ? » **Tapez A, B ou C dans le chat :**

    - A) Oui : l'infrastructure sera saine, le sujet est clos.
    - B) Non : la sécurité est un processus continu — veille (CERT-FR), correctifs, re-scans, exercices de crise annuels, sensibilisation permanente ; l'audit est une photo, pas un film. ✅
    - C) Oui, à condition de racheter un pare-feu plus cher chaque année.

    **Débrief mentor :** B — la boucle du parcours se referme : les menaces évoluent (B02), les vulnérabilités naissent chaque jour (plus de 40 000 CVE en 2024, B18), les équipes changent, les configurations dérivent. C'est la roue de Deming de B13 : planifier, faire, **vérifier**, corriger — sans fin. La bonne nouvelle : MedDistri sait désormais quoi surveiller, et vous aussi.

---

### Questions de réflexion
1. Pourquoi présente-t-on un constat d'audit à une direction en termes de risque d'entreprise (financier, juridique, réputationnel) plutôt qu'en termes techniques ?
2. Dans le plan de remédiation de MedDistri, quelles mesures classeriez-vous en « quick wins » (fort impact, faible effort) à réaliser dans le mois ?
3. Le score de résilience de MedDistri atteint 80 % en fin d'atelier. Qu'est-ce que ce chiffre ne dit PAS ?

**Corrigé / Éléments de réponse :**

1. Parce que la direction arbitre des budgets et des risques, pas des protocoles : la décision de financer la remédiation se prend sur l'impact métier (arrêt d'activité, amende, réputation) — c'est aussi l'esprit de la gouvernance vue en B13 (la direction décide, la direction assume).
2. Typiquement : activer le MFA sur Microsoft 365 (gratuit, immédiat, >99 % d'efficacité), fermer RDP/SSH exposés (remplacés par un VPN avec MFA), changer le mot de passe administrateur et déconnecter le disque USB au profit d'une rotation hors ligne — quatre mesures à coût quasi nul qui traitent les vecteurs majeurs.
3. Qu'il faut le MAINTENIR : le score mesure des décisions à un instant donné, pas leur mise en œuvre réelle ni leur pérennité (dérive des configurations, nouvelles CVE, arrivées/départs). D'où la veille, les re-scans et les exercices — la sécurité est un processus, pas un état.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Le Grand Atelier, c'est **l'examen du permis de conduire** après vingt leçons :
    - Le moniteur (le mentor) ne réexplique plus le code — il met l'élève en circulation réelle (MedDistri) et observe les réflexes.
    - Les six votes sont les manœuvres imposées ; l'incident en cours de séance est le piéton qui surgit — c'est là qu'on voit si les réflexes sont acquis.
    - Et comme pour le permis : l'examen réussi n'est pas la fin de l'apprentissage, c'est l'autorisation de continuer à apprendre en conduisant (veille, pratique, exercices).

**Exemple d'application professionnelle :**
Le format de cet atelier est directement réutilisable en entreprise : un RSSI peut auditer la posture de son organisation en comité élargi exactement ainsi — présenter chaque faiblesse, faire voter les priorités par les métiers, dérouler un mini-incident sur table, et repartir avec un plan de remédiation co-décidé (donc financé). L'adhésion obtenue par le vote vaut tous les rapports de 80 pages.

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour prolonger l'atelier : simuler des attaques, s'entraîner et exercer les équipes :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **Immersive Labs / simulations de crise Mandiant** : plateformes interactives d'entraînement et de simulation de crise en direct.
    *   **XM Cyber** : simulation d'attaque continue (BAS) révélant les chemins d'attaque vers les actifs critiques.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **OpenBAS (anciennement OpenEx, Filigran)** : plateforme open-source de planification et d'exécution d'exercices de crise.
    *   **CISA Tabletop Exercise Packages** : banque gratuite de scénarios et guides d'animation d'exercices.
    *   **TryHackMe / Hack The Box** : laboratoires en ligne légaux pour pratiquer offensif et défensif (parcours guidés côté TryHackMe).

## 3. Ressources complémentaires

*   **Après la formation** : réclamer son badge numérique final (Credly) et l'ajouter à son profil LinkedIn, avec les badges **IBM SkillsBuild** du parcours.
*   **Veille continue** : s'abonner aux bulletins du **CERT-FR** (le réflexe pris en B02) et suivre les rapports annuels de référence (panorama de la menace ANSSI, Verizon DBIR, IBM *Cost of a Data Breach*).
*   [CERT-FR — Bulletins et alertes](https://www.cert.ssi.gouv.fr/)
*   [ANSSI — Bonnes pratiques](https://cyber.gouv.fr)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Le meilleur retour sur investissement de l'hygiène cyber.
*   **📊 Sondage Livestorm n°9 :** Quelle mesure simple et quasi gratuite offre le meilleur retour sur investissement immédiat pour une TPE/PME ?
    *   A) Acheter un pare-feu à 5 000 €
    *   B) Mots de passe robustes + MFA gratuit + sensibilisation des collaborateurs ✅
    *   C) Rédiger une charte informatique de 80 pages
*   **Guide d'animation (pour le mentor) :** l'hygiène de base bloque la majorité des attaques opportunistes sans budget : le MFA d'abord (>99 % — Microsoft 2019), des mots de passe uniques (B09-B10), des humains entraînés (B04). Le pare-feu et la charte viennent APRÈS les fondamentaux, pas à leur place. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Audit de sécurité** | La photo de la posture : constats priorisés + plan de remédiation — à refaire, car tout dérive. |
| **Restitution managériale** | Traduire la technique en risque d'entreprise : argent, droit, réputation — c'est elle qui débloque les budgets. |
| **Quick wins MedDistri** | MFA partout, RDP/SSH fermés (VPN+MFA), mot de passe admin fort, sauvegarde 3-2-1 hors ligne. |
| **Incident en direct** | Isoler sans éteindre (la RAM !), cellule de crise, porte-parole unique — B18-B19 en réflexes. |
| **Après le parcours** | Security+ puis spécialisation ; TryHackMe / Hack The Box ; veille CERT-FR ; badges SkillsBuild sur LinkedIn. |

**La règle d'or de la session — et du parcours :** la cybersécurité n'est pas un produit qu'on achète ni un état qu'on atteint : c'est un processus qu'on entretient — des fondamentaux d'hygiène (qui bloquent l'essentiel), des humains entraînés (qui font la différence) et une vigilance continue (qui recommence chaque matin). Vous avez maintenant les réflexes : entretenez-les.
