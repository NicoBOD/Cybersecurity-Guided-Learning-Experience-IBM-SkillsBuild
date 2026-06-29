# Support de cours — Session 07 : Réponse aux incidents & introduction au forensics
Parcours : A 8 sessions  |  Module : Réponse aux Incidents  |  Niveau : Débutant

---

## Résumé exécutif
Même avec les meilleures protections logicielles et humaines, le risque zéro n'existe pas : toute entreprise sera confrontée un jour ou l'autre à un incident de sécurité. Ce qui différencie une organisation résiliente d'une organisation qui s'effondre est la qualité de sa préparation et de sa réaction. Ce support de cours vous présente le cycle méthodologique de la réponse aux incidents (modèle international du NIST et du SANS) pour savoir comment réagir étape par étape lors d'une attaque. Nous aborderons les bases du *forensics* (investigation numérique) afin de comprendre comment les analystes collectent et préservent les preuves d'une intrusion en respectant la chaîne de contrôle. Enfin, nous définirons le cadre légal du piratage éthique en France, afin de clarifier les limites juridiques indispensables aux métiers de la cybersécurité.

---

## Glossaire de la session
* **Réponse aux incidents (Incident Response - IR)** : Processus structuré permettant à une organisation de détecter, de contenir, d'éradiquer et de se relever d'une cyberattaque.
* **Forensics (Investigation numérique)** : Discipline scientifique consistant à collecter, analyser et préserver les preuves numériques à la suite d'un incident de sécurité en vue de procédures internes ou judiciaires.
* **Chaîne de contrôle (Chain of Custody)** : Documentation chronologique stricte recensant l'historique des personnes ayant manipulé, transféré et analysé une preuve physique ou numérique, afin de garantir qu'elle n'a subie aucune altération.
* **Confinement** : Phase de la réponse aux incidents visant à isoler le système d'information ou les hôtes compromis pour empêcher la propagation de l'attaque.
* **Mémoire volatile (RAM)** : Mémoire temporaire d'un ordinateur contenant les données actives des programmes en cours d'exécution. Elle s'efface dès que la machine est éteinte.
* **Piratage éthique (Ethical Hacking)** : Pratique consistant à utiliser les mêmes techniques d'intrusion qu'un pirate malveillant, mais de manière légale, encadrée et autorisée, afin d'identifier et de corriger les faiblesses d'un système.

---

## Contenu théorique

### 1. Le cycle de réponse aux incidents (IR) : Les 6 étapes clés

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

---

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

---

### 3. Cadre légal : Piratage éthique vs Intrusions illégales

En France, la loi encadre strictement l'accès aux systèmes informatiques. Les articles 323-1 et suivants du Code pénal définissent les délits liés aux "atteintes aux systèmes de traitement automatisé de données" (STAD).

* **L'infraction de base** : Le simple fait d'accéder ou de se maintenir frauduleusement dans un système informatique sans autorisation est puni de sanctions pénales allant jusqu'à 3 ans d'emprisonnement et 100 000 euros d'amende. Le fait que le système ait été mal sécurisé n'est pas une excuse légale.
* **Le cadre du piratage éthique** : Un testeur d'intrusion (*pentester*) ne peut agir qu'après la signature d'un **contrat écrit explicite** (ordre de mission) définissant précisément le périmètre d'attaque autorisé, la période de test et les outils utilisés. Dépasser ce périmètre contractuel (ex. attaquer le site d'un sous-traitant de son client) constitue un délit pénal.

---

## Focus pratique : Ordre de volatilité et processus de collecte

Lors d'un incident sur un poste de travail, voici l'ordre dans lequel les éléments techniques doivent être capturés par l'équipe de réponse à incident :

| Niveau de volatilité | Élément technique | Méthode d'acquisition | Risque de perte |
| :--- | :--- | :--- | :--- |
| **Très Élevé** | Données de la mémoire vive (RAM). | Extraction via outil de dump mémoire (ex. FTK Imager). | Perte immédiate si arrêt de la machine ou redémarrage. |
| **Élevé** | Connexions réseau et processus actifs. | Commandes système d'observation en direct. | Perte dès la déconnexion réseau ou arrêt du processus. |
| **Moyen** | Fichiers temporaires et fichiers système. | Copie logique des répertoires temporaires. | Écriture de nouveaux logs écrasant les anciens. |
| **Bas** | Données du disque dur (fichiers stockés). | Copie bit-à-bit (clonage physique du disque). | Persistant sur le support physique hors tension. |

---

## Exercice d'application (self-paced)
**Titre** : Gestion d'une réaction sur incident de rançongiciel

### Énoncé
À 9h00 du matin, un employé de la comptabilité d'une entreprise s'aperçoit que les noms de ses fichiers sur son poste de travail sont renommés avec l'extension `.locked` et qu'un fichier texte s'ouvre automatiquement affichant une demande de rançon. Le poste est connecté au réseau local de l'entreprise par un câble Ethernet.

1. Quelle étape du cycle de réponse aux incidents devez-vous engager immédiatement ?
2. Parmi les deux actions suivantes, laquelle choisissez-vous en expliquant votre décision au regard des contraintes du forensics et du confinement :
   * **Action A** : Débrancher immédiatement le câble réseau Ethernet du poste de travail pour l'isoler, mais laisser la machine allumée.
   * **Action B** : Éteindre immédiatement l'ordinateur en restant appuyé sur le bouton d'alimentation physique afin de stopper le chiffrement des fichiers.
3. Quelle sera la phase d'éradication pour ce poste ?

---

### Corrigé de l'exercice
1. **Étape à engager : Le Confinement**. Il faut empêcher le rançongiciel de se propager via le réseau local aux autres postes de travail et surtout aux serveurs de sauvegarde ou serveurs de fichiers partagés de l'entreprise.
2. **Décision : Action A (Débrancher le câble réseau en laissant la machine allumée)**.
   * *Pourquoi ?* Débrancher le câble réseau assure un confinement réseau immédiat et total (le malware ne peut plus se propager). Laisser la machine allumée permet aux enquêteurs de collecter le contenu de la mémoire vive (RAM). C'est dans la RAM que l'on pourra potentiellement récupérer la clé de chiffrement utilisée par le rançongiciel ou identifier le processus malveillant en cours d'exécution. L'action B détruirait définitivement ces preuves volatiles et pourrait corrompre le système.
3. **Phase d'éradication** : Elle consistera à formater complètement le disque dur du poste infecté, à réinstaller le système d'exploitation à partir d'une image d'installation saine et certifiée par l'entreprise, à déployer les derniers correctifs de sécurité et à changer tous les mots de passe associés à l'utilisateur du poste.

---

## Ressources pour aller plus loin
* **IBM SkillsBuild** : Cours sur l'investigation numérique (Digital Forensics) et la réponse à incident.
* **SANS Institute** : Fiches de référence sur la réponse aux incidents (Incident Handler's Handbook).
* **Légifrance** : Consulter la section du Code pénal sur les atteintes aux systèmes de traitement automatisé de données (articles 323-1 à 323-7).
