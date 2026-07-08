# Support de cours — Session 07 : Réponse aux incidents & introduction au forensics
Parcours : A 8 sessions  |  Module : Réponse aux Incidents  |  Niveau : Débutant

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - Le cycle de réponse aux incidents (IR) : Les 6 étapes clés
    - Introduction au Forensics et préservation des preuves
    - Cadre légal : Piratage éthique vs Intrusions illégales
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

Même avec les meilleures protections logicielles et humaines, le risque zéro n'existe pas : toute entreprise sera confrontée un jour ou l'autre à un incident de sécurité. Ce qui différencie une organisation résiliente d'une organisation qui s'effondre est la qualité de sa préparation et de sa réaction. Ce support de cours vous présente le cycle méthodologique de la réponse aux incidents (modèle international du NIST et du SANS) pour savoir comment réagir étape par étape lors d'une attaque. Nous aborderons les bases du *forensics* (investigation numérique) afin de comprendre comment les analystes collectent et préservent les preuves d'une intrusion en respectant la chaîne de contrôle. Enfin, nous définirons le cadre légal du piratage éthique en France, afin de clarifier les limites juridiques indispensables aux métiers de la cybersécurité.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Les 4 phases de la Réponse aux Incidents (NIST SP 800-61)**
Détaillez le cycle de vie d'une attaque :
1. *Préparation* : Création des playbooks, cellules de crise, outillage.
2. *Détection et Analyse* : Qualifier l'alerte. S'agit-il d'un ransomware ou d'une erreur admin ?
3. *Confinement, Éradication et Recouvrement* : Couper le réseau (Confinement), supprimer les backdoors (Éradication), restaurer les sauvegardes (Recouvrement).
4. *Activité post-incident (Leçons apprises)* : L'étape la plus critique pour ne pas subir la même attaque le mois suivant.

**2. Ordre de volatilité et Forensics**
Expliquez pourquoi on ne doit **jamais** éteindre un ordinateur infecté par un ransomware : l'extinction vide la mémoire RAM qui contient potentiellement les clés de chiffrement et les preuves de l'attaque. L'ordre légal exige de d'abord dumper la RAM, puis les caches réseau, et enfin cloner le disque dur physique.

**3. Exercice de Tabletop (Simulation)**
Passez 20 minutes à faire un jeu de rôle avec la salle : "Il est 8h00, tous les écrans affichent une demande de rançon. Qui appelez-vous en premier ? Comment communiquez-vous si les e-mails sont coupés ?"


---

### Glossaire

*   **Chaîne de contrôle (Chain of Custody)** — Documentation chronologique stricte recensant l'historique des personnes ayant manipulé, transféré et analysé une preuve physique ou numérique, afin de garantir qu'elle n'a subie aucune altération.
*   **Confinement** — Phase de la réponse aux incidents visant à isoler le système d'information ou les hôtes compromis pour empêcher la propagation de l'attaque.
*   **Forensics (Investigation numérique)** — Discipline scientifique consistant à collecter, analyser et préserver les preuves numériques à la suite d'un incident de sécurité en vue de procédures internes ou judiciaires.
*   **Forensics (Investigation numérique)** — Discipline scientifique et légale consistant à collecter, analyser et préserver les preuves numériques après un incident.
*   **Mémoire volatile (RAM)** — Mémoire temporaire d'un ordinateur contenant les données actives des programmes en cours d'exécution. Elle s'efface dès que la machine est éteinte.
*   **Piratage éthique (Ethical Hacking)** — Pratique consistant à utiliser les mêmes techniques d'intrusion qu'un pirate malveillant, mais de manière légale, encadrée et autorisée, afin d'identifier et de corriger les faiblesses d'un système.
*   **Réponse aux incidents (Incident Response - IR)** — Processus structuré permettant à une organisation de détecter, de contenir, d'éradiquer et de se relever d'une cyberattaque.
*   **Sauvegarde immuable** — Sauvegarde dont le contenu ne peut être modifié, modifié ou effacé, même par un administrateur système, protégeant des rançongiciels.
*   **Éradication** — Phase consistant à éliminer définitivement la source de l'incident (ex. supprimer un code malveillant ou fermer un compte piraté).

---

### 1. Le cycle de réponse aux incidents (IR) : Les 6 étapes clés

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.


Pour éviter la panique et les erreurs de manipulation lors d'une cyberattaque (ex. un rançongiciel en cours de chiffrement), les équipes de sécurité suivent le cycle standardisé composé de 6 phases :

```
[1. Préparation] ➔ [2. Identification] ➔ [3. Confinement] ➔ [4. Éradication] ➔ [5. Restauration] ➔ [6. Leçons apprises]
```

1. **Préparation** : Mettre en place les outils de sécurité, former les équipes, rédiger les procédures d'urgence et définir qui appeler en cas de crise.
2. **Identification** : Détecter l'incident de sécurité (ex. une alerte SOC) et en déterminer la nature, la gravité et le périmètre.
3. **Confinement** : Isoler les systèmes touchés pour empêcher l'attaque de se propager (ex. débrancher un serveur infecté du réseau, désactiver des comptes compromis).
4. **Éradication** : Supprimer l'origine de l'incident (ex. supprimer les malwares, effacer les portes dérobées, réinstaller les serveurs à partir d'une image propre).
5. **Restauration** : Remettre en production les systèmes nettoyés et restaurer les données à partir de sauvegardes saines, tout en surveillant attentivement l'activité pour s'assurer que le pirate ne revient pas.
6. **Leçons apprises** : Analyser l'incident a posteriori pour comprendre comment il s'est produit, évaluer l'efficacité de la réaction et modifier les défenses pour éviter qu'il ne se reproduise.



### 2. Introduction au Forensics et préservation des preuves

L'investigation numérique s'apparente à une enquête de police scientifique, transposée au monde virtuel. Les enquêteurs doivent collecter des indices sans modifier la scène de crime.

#### A. L'ordre de volatilité des données
Les données informatiques s'effacent à des vitesses différentes. Les enquêteurs collectent d'abord les données les plus volatiles :

* **Mémoire vive (RAM)** : Contient les mots de passe saisis en clair, les clés de chiffrement temporaires et la liste des connexions réseau actives de l'attaquant. Si on éteint l'ordinateur, toutes ces preuves cruciales disparaissent instantanément.
* **Fichiers temporaires & caches système** : Traces d'exécution récentes.
* **Stockage physique (Disque dur)** : Fichiers persistants, logs enregistrés, fichiers supprimés récupérables.

#### B. La Chaîne de contrôle (*Chain of Custody*)
Pour qu'une preuve numérique soit acceptée devant un tribunal, l'enquêteur doit prouver qu'elle n'a pas été modifiée lors de sa collecte ou de son analyse.

* *Comment ?* On réalise une **copie bit-à-bit** (clone exact) du disque dur d'origine. On calcule ensuite l'**empreinte numérique** (hachage) du clone. Si l'empreinte correspond exactement à celle du disque d'origine, on prouve que la copie est identique. Toutes les analyses sont ensuite menées uniquement sur la copie, l'original restant scellé sous clé.



### 3. Cadre légal : Piratage éthique vs Intrusions illégales

En France, la loi encadre strictement l'accès aux systèmes informatiques. Les articles 323-1 et suivants du Code pénal définissent les délits liés aux "atteintes aux systèmes de traitement automatisé de données" (STAD).

* **L'infraction de base** : Le simple fait d'accéder ou de se maintenir frauduleusement dans un système informatique sans autorisation est puni de sanctions pénales allant jusqu'à 3 ans d'emprisonnement et 100 000 euros d'amende. Le fait que le système ait été mal sécurisé n'est pas une excuse légale.
* **Le cadre du piratage éthique** : Un testeur d'intrusion (*pentester*) ne peut agir qu'après la signature d'un **contrat écrit explicite** (ordre de mission) définissant précisément le périmètre d'attaque autorisé, la période de test et les outils utilisés. Dépasser ce périmètre contractuel (ex. attaquer le site d'un sous-traitant de son client) constitue un délit pénal.

---

### Focus pratique
Lors d'un incident sur un poste de travail, voici l'ordre dans lequel les éléments techniques doivent être capturés par l'équipe de réponse à incident :

| Niveau de volatilité | Élément technique | Méthode d'acquisition | Risque de perte |
| :--- | :--- | :--- | :--- |
| **Très Élevé** | Données de la mémoire vive (RAM). | Extraction via outil de dump mémoire (ex. FTK Imager). | Perte immédiate si arrêt de la machine ou redémarrage. |
| **Élevé** | Connexions réseau et processus actifs. | Commandes système d'observation en direct. | Perte dès la déconnexion réseau ou arrêt du processus. |
| **Moyen** | Fichiers temporaires et fichiers système. | Copie logique des répertoires temporaires. | Écriture de nouveaux logs écrasant les anciens. |
| **Bas** | Données du disque dur (fichiers stockés). | Copie bit-à-bit (clonage physique du disque). | Persistant sur le support physique hors tension. |

---

### Exercice d'application
**Titre** : Gestion d'une réaction sur incident de rançongiciel

### Énoncé
À 9h00 du matin, un employé de la comptabilité d'une entreprise s'aperçoit que les noms de ses fichiers sur son poste de travail sont renommés avec l'extension `.locked` et qu'un fichier texte s'ouvre automatiquement affichant une demande de rançon. Le poste est connecté au réseau local de l'entreprise par un câble Ethernet.

1. Quelle étape du cycle de réponse aux incidents devez-vous engager immédiatement ?
2. Parmi les deux actions suivantes, laquelle choisissez-vous en expliquant votre décision au regard des contraintes du forensics et du confinement :
   * **Action A** : Débrancher immédiatement le câble réseau Ethernet du poste de travail pour l'isoler, mais laisser la machine allumée.
   * **Action B** : Éteindre immédiatement l'ordinateur en restant appuyé sur le bouton d'alimentation physique afin de stopper le chiffrement des fichiers.
3. Quelle sera la phase d'éradication pour ce poste ?



### Corrigé de l'exercice
1. **Étape à engager : Le Confinement**. Il faut empêcher le rançongiciel de se propager via le réseau local aux autres postes de travail et surtout aux serveurs de sauvegarde ou serveurs de fichiers partagés de l'entreprise.
2. **Décision : Action A (Débrancher le câble réseau en laissant la machine allumée)**.
   * *Pourquoi ?* Débrancher le câble réseau assure un confinement réseau immédiat et total (le malware ne peut plus se propager). Laisser la machine allumée permet aux enquêteurs de collecter le contenu de la mémoire vive (RAM). C'est dans la RAM que l'on pourra potentiellement récupérer la clé de chiffrement utilisée par le rançongiciel ou identifier le processus malveillant en cours d'exécution. L'action B détruirait définitivement ces preuves volatiles et pourrait corrompre le système.
3. **Phase d'éradication** : Elle consistera à formater complètement le disque dur du poste infecté, à réinstaller le système d'exploitation à partir d'une image d'installation saine et certifiée par l'entreprise, à déployer les derniers correctifs de sécurité et à changer tous les mots de passe associés à l'utilisateur du poste.

---


### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Imaginez la réponse sur incident de cybersécurité comme l'intervention des **pompiers après un départ de feu** :
    - **La Détection** : L'alarme incendie se déclenche (l'alerte remonte au SOC).
    - **Le Confinement (Containment)** : Fermer les portes coupe-feu pour éviter que les flammes ne se propagent au reste du bâtiment (ex. débrancher la machine infectée du réseau local).
    - **L'Éradication** : Éteindre le foyer du feu avec de l'eau et s'assurer qu'il ne reste plus de braises chaudes (ex. nettoyer le malware et supprimer le script malveillant).
    - **La Reconstruction (Recovery)** : Aérer les pièces, nettoyer la suie et rouvrir les bureaux (ex. réinstaller le système propre et restaurer les fichiers depuis la dernière sauvegarde saine).
    - **Le Forensics** : L'enquêteur de police cherche l'origine du départ de feu pour savoir s'il est criminel ou accidentel (ex. analyser les logs systèmes pour trouver l'adresse IP d'origine de l'intrus).

**Exemple d'application professionnelle :**
Une PME subit une attaque par Ransomware. Le serveur de comptabilité commence à chiffrer ses fichiers. La procédure d'incident est immédiatement déclenchée : le serveur est isolé du réseau en moins de 15 minutes, limitant l'infection. Les logs de pare-feu et les journaux systèmes sont copiés de façon intègre (forensics) avant de restaurer le serveur à partir des sauvegardes de la veille.


### Panorama des solutions du marché (Commerciales & Open-Source)

Lors d'un incident de sécurité ou pour mener une investigation numérique (forensics), des outils spécialisés sont indispensables :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **EnCase Forensic / FTK (Forensic Toolkit)** : Standards industriels reconnus par la justice et les experts cyber pour l'acquisition intègre de disques durs et l'investigation numérique approfondie.
    *   **CrowdStrike Falcon Forensics** : Outil d'investigation cloud permettant aux analystes de collecter rapidement des artefacts système à distance lors d'un incident actif.
    *   **Veeam Incident Recovery** : Solution de restauration d'urgence après ransomware, garantissant que les données réinjectées sont exemptes de malwares.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **Autopsy (The Sleuth Kit)** : Plateforme d'investigation numérique open-source la plus connue. Elle permet d'analyser des images de disques durs, de récupérer des fichiers supprimés et d'explorer l'historique d'un système.
    *   **Volatility** : Outil open-source leader pour l'analyse judiciaire de la mémoire vive (RAM forensics), permettant d'extraire des connexions réseau actives et des clés de chiffrement en mémoire.
    *   **Velociraptor** : Outil open-source d'investigation rapide d'endpoints et de réponse active à grande échelle.

## 3. Ressources complémentaires

* **IBM SkillsBuild** : Cours sur l'investigation numérique (Digital Forensics) et la réponse à incident.
* **SANS Institute** : Fiches de référence sur la réponse aux incidents (Incident Handler's Handbook).
* **Légifrance** : Consulter la section du Code pénal sur les atteintes aux systèmes de traitement automatisé de données (articles 323-1 à 323-7).


---

* [ANSSI - Exercice de crise cyber](https://cyber.gouv.fr/publications/organiser-un-exercice-de-gestion-de-crise-cyber)
* [Cybermalveillance - Que faire en cas de cyberattaque](https://www.cybermalveillance.gouv.fr)

## 4. Exercice bonus

- **Objectif :** Simulation de gestion d'incident de sécurité (Ransomware).
- **Consignes :**
    1. Vous êtes responsable informatique. Un utilisateur vous appelle en disant que tous ses fichiers ont l'extension `.locked` et qu'une note réclame 2 bitcoins.
    2. Rédigez la liste des 3 premières actions réflexes que vous effectuez dans les 10 premières minutes pour limiter l'impact.
    3. Rédigez le message d'alerte court et rassurant à envoyer à l'ensemble des employés de l'entreprise.
- **Correction pour le mentor :** Actions de base : 1. Ordonner à l'utilisateur de débrancher immédiatement le câble réseau et d'éteindre sa machine (confinement). 2. Vérifier sur la console EDR/antivirus si d'autres alertes similaires sont en cours. 3. Bloquer temporairement les accès VPN et partages de fichiers réseau. Message aux employés : "Bonjour à tous, nous rencontrons actuellement un incident technique sur notre réseau. Par mesure de sécurité, merci de ne pas ouvrir vos partages réseau et de signaler immédiatement au support tout comportement anormal sur vos postes. Nos équipes sont mobilisées." 

---

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Chaîne de contrôle (Chain of Custody)** | Documentation chronologique stricte recensant l'historique des personnes ayant manipulé, transféré et analysé une preuve physique ou numérique, afin de garantir qu'elle n'a subie aucune altération. |
| **Confinement** | Phase de la réponse aux incidents visant à isoler le système d'information ou les hôtes compromis pour empêcher la propagation de l'attaque. |
| **Forensics (Investigation numérique)** | Discipline scientifique consistant à collecter, analyser et préserver les preuves numériques à la suite d'un incident de sécurité en vue de procédures internes ou judiciaires. |
| **Mémoire volatile (RAM)** | Mémoire temporaire d'un ordinateur contenant les données actives des programmes en cours d'exécution. Elle s'efface dès que la machine est éteinte. |
| **Piratage éthique (Ethical Hacking)** | Pratique consistant à utiliser les mêmes techniques d'intrusion qu'un pirate malveillant, mais de manière légale, encadrée et autorisée, afin d'identifier et de corriger les faiblesses d'un système. |
| **Réponse aux incidents (Incident Response - IR)** | Processus structuré permettant à une organisation de détecter, de contenir, d'éradiquer et de se relever d'une cyberattaque. |
| **Sauvegarde immuable** | Sauvegarde dont le contenu ne peut être modifié, modifié ou effacé, même par un administrateur système, protégeant des rançongiciels. |
| **Éradication** | Phase consistant à éliminer définitivement la source de l'incident (ex. supprimer un code malveillant ou fermer un compte piraté). |

