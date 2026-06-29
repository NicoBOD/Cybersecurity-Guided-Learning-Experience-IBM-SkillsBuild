# Spécifications des slides — Session 06 : Opérations de sécurité & gestion des vulnérabilités
Parcours : A 8 sessions  |  Module : SecOps & Vulnérabilités  |  Format : Spécifications Markdown

---

## Slide 1 : Page de garde
* **Layout** : Titre (Emphase visuelle, fond sombre)
* **Texte affiché sur la slide** :
  * **Opérations de Sécurité & Gestion des Vulnérabilités**
  * Parcours A — Session 06
  * *Surveiller les signaux faibles, identifier les faiblesses logicielles et prioriser les correctifs*
  * Nom du Mentor / IBM SkillsBuild
* **Visuels suggérés** : Une salle de contrôle sombre avec des écrans de surveillance géants affichant des graphiques et des alertes de sécurité (style SOC). Logo officiel dans un angle.
* **Notes du présentateur** :
  * Accueillir les apprenants.
  * Faire le bilan sur le devoir autonome (politique de confidentialité RGPD).
  * Introduire le sujet : après avoir vu la gouvernance théorique, nous plongeons au cœur de la surveillance opérationnelle quotidienne d'un réseau d'entreprise.

---

## Slide 2 : Objectifs de la séance & Sommaire
* **Layout** : Deux colonnes (Gauche : Objectifs, Droite : Sommaire)
* **Texte affiché sur la slide** :
  * **Nos objectifs aujourd'hui** :
    * Décrire le rôle d'un SOC et le fonctionnement d'un outil SIEM.
    * Comprendre l'importance de la journalisation active (*logs*).
    * Différencier un scan de vulnérabilités automatisé d'un test d'intrusion.
    * Prioriser les correctifs de sécurité en s'appuyant sur le score *CVSS*.
  * **Sommaire de la séance** :
    * 1. Brise-glace : Le détective des traces (10 min)
    * 2. Surveillance active : Le SOC et le SIEM (20 min)
    * 3. Gestion des failles : Scans vs Pentest (20 min)
    * 4. Activité pratique 1 : Analyse de logs d'attaque (20 min)
    * 5. Priorisation des patchs : Le score CVSS (10 min)
    * 6. Quiz de validation & Clôture (10 min)
* **Visuels suggérés** : Icônes cibles pour les objectifs et icône de liste pour le sommaire.
* **Notes du présentateur** :
  * Expliquer aux apprenants qu'il s'agit d'une session très pratique où ils vont se glisser dans la peau d'un analyste de sécurité opérationnelle.

---

## Slide 3 : Rappel & Brise-glace interactif
* **Layout** : Plein écran interactif
* **Texte affiché sur la slide** :
  * **Brise-glace : Les boîtes noires de l'entreprise**
  * *Si un cambriolage a lieu dans un centre commercial durant la nuit, par quoi les enquêteurs commencent-ils pour comprendre ce qui s'est passé ?*
    * A. Les enregistrements des caméras de surveillance.
    * B. Le registre des entrées/sorties des vigiles.
  * **En cybersécurité**, quel est l'équivalent de ces enregistrements vidéo ?
* **Visuels suggérés** : Photo ou icône d'une caméra de sécurité braquée sur un couloir sombre.
* **Notes du présentateur** :
  * Laisser 3 minutes de discussion.
  * Faire le lien : en informatique, l'équivalent des caméras et registres physiques sont les **journaux d'événements (logs)**.
  * Expliquer qu'un système sans log est un système aveugle en cas d'attaque.

---

## Slide 4 : Surveiller en continu : Le SOC et le SIEM
* **Layout** : Deux colonnes
* **Texte affiché sur la slide** :
  * **Le SIEM : Le moteur de corrélation**
    * Centralise les logs de tous les équipements (serveurs, pare-feu, postes).
    * Analyse les événements en temps réel.
    * Déclenche des alertes automatiques selon des règles complexes (ex. 100 échecs de connexion en 1 min = suspicion d'attaque).
  * **Le SOC : La tour de contrôle humaine**
    * Équipe d'analystes de sécurité qui traitent les alertes du SIEM 24/7.
    * Rôle : Qualifier l'alerte pour éliminer les **faux positifs** (alertes déclenchées à tort) et traiter les **vrais incidents**.
* **Visuels suggérés** : Schéma d'entonnoir montrant des millions de logs bruts entrant, filtrés par le SIEM, et générant quelques alertes qualifiées par le SOC.
* **Notes du présentateur** :
  * Expliquer le concept de faux positif par une métaphore simple (ex. l'alarme incendie qui se déclenche parce que quelqu'un a fait brûler du pain).
  * Insister sur le fait que le SIEM automatise le tri, mais que l'analyste SOC prend la décision finale.

---

## Slide 5 : Trouver les failles : Scans de vulnérabilités vs Pentest
* **Layout** : Deux colonnes comparatives
* **Texte affiché sur la slide** :
  * **Vulnerability Scan (Scan automatisé)** :
    * Outil logiciel automatique qui recherche les failles connues (CVE) dans une base de données.
    * *Avantages* : Rapide, peu cher, automatisable à grande échelle.
    * *Limites* : Nombreux faux positifs, ne trouve pas les failles logiques de conception.
  * **Penetration Test (Pentest)** :
    * Audit manuel mené par un hacker éthique humain qui simule une attaque réelle.
    * *Avantages* : Analyse profonde, exploitation combinée de failles logiques et humaines.
    * *Limites* : Coûteux, ponctuel.
* **Visuels suggérés** : Icône d'un radar automatique de vitesse (le scanneur) vs icône d'un pilote professionnel testant les limites d'un véhicule (le pentester).
* **Notes du présentateur** :
  * Souligner la complémentarité des deux méthodes : le scan sert d'hygiène de base régulière, le pentest valide la robustesse globale une à deux fois par an.

---

## Slide 6 : Prioriser la remédiation : Le score CVSS
* **Layout** : Contenu structuré / Échelle de notation
* **Texte affiché sur la slide** :
  * **CVSS : Common Vulnerability Scoring System**
  * *Une échelle de gravité de 0.0 à 10.0 pour prioriser le patching :*
    * **Critique [9.0 - 10.0]** ➔ À corriger en urgence absolue (sous 24h).
    * **Élevé [7.0 - 8.9]** ➔ À corriger rapidement (sous quelques jours).
    * **Moyen [4.0 - 6.9]** ➔ À planifier lors des maintenances de routine.
    * **Faible [0.0 - 3.9]** ➔ Risque marginal, correction non prioritaire.
  * *Exemple de critères d'évaluation* : La faille est-elle exploitable à distance sans mot de passe ?
* **Visuels suggérés** : Une jauge de température colorée allant du bleu (0.0) au rouge vif (10.0).
* **Notes du présentateur** :
  * Expliquer qu'une entreprise a souvent trop de failles pour pouvoir toutes les corriger. Le score CVSS sert de boussole de priorisation.
  * Mentionner le catalogue des CVE (dictionnaire public mondial des failles).

---

## Slide 7 : Focus pratique — La feuille de route de remédiation
* **Layout** : Tableau de synthèse
* **Texte affiché sur la slide** :
  * **Feuille de route de remédiation post-scan (Exemple)**
  * *Comment organiser les travaux de correction :*
  * **Priorité 1 : Immédiate** ➔ Faille critique (CVSS 9.8) sur le serveur web externe d'e-commerce (vulnérable à l'exécution de code à distance).
  * **Priorité 2 : Sous 7 jours** ➔ Faille élevée (CVSS 7.8) sur la base de données interne contenant les salaires (élévation de privilèges).
  * **Priorité 3 : Fin de mois** ➔ Faille moyenne (CVSS 4.3) sur les postes des employés (fuite d'informations mémoire locale).
* **Visuels suggérés** : Tableau synthétique avec codes couleur (Rouge pour priorité 1, Orange pour 2, Vert pour 3).
* **Notes du présentateur** :
  * Montrer comment le contexte d'exposition (serveur public sur Internet vs serveur interne) modifie l'urgence réelle de traitement, même si les scores CVSS bruts sont proches.

---

## Slide 8 : Activité 1 — Analyse de logs d'une alerte SOC
* **Layout** : Consignes de travail (Activité pratique)
* **Texte affiché sur la slide** :
  * **Activité 1 : Analyser une intrusion à partir de logs**
  * *Analysez la séquence d'événements projetée à l'écran :*
    * `16:45:01 | LOGIN_FAILED | IP: 198.51.100.12 | User: admin`
    * `16:45:03 | LOGIN_FAILED | IP: 198.51.100.12 | User: administrator`
    * `16:45:08 | LOGIN_SUCCESS | IP: 198.51.100.12 | User: admin`
    * `16:45:15 | FILE_DOWNLOAD | IP: 198.51.100.12 | File: brevets-2026.zip`
  * **Questions :**
    * 1. Quelle attaque a eu lieu ? Comment s'est-elle soldée ?
    * 2. Quel pilier CIA a été compromis ?
    * 3. Quelle action d'urgence devez-vous mener ?
  * **Consignes** : 15 min de réflexion en sous-salle de 3 apprenants.
* **Visuels suggérés** : Capture de console de logs. Minuteur de 15 minutes.
* **Notes du présentateur** :
  * Lancer l'activité.
  * Circuler dans les groupes pour aider à la lecture syntaxique des logs.
  * Lors de la mise en commun, expliquer comment l'adresse IP externe a réalisé un brute force réussi et insister sur la nécessité de bloquer cette IP d'urgence sur le pare-feu.

---

## Slide 9 : Quiz de validation & Débriefing
* **Layout** : Contenu interactif (Quiz)
* **Texte affiché sur la slide** :
  * **Quiz rapide de session :**
    * 1. *Quel outil applique des règles de corrélation automatique sur les logs d'une entreprise ?* ➔ **[L'antivirus / Le SIEM / Le Pentest ?]**
    * 2. *Qu'est-ce qu'un faux positif ?* ➔ **[Une vraie attaque non détectée / Une alerte de sécurité déclenchée à tort par une activité normale ?]**
    * 3. *Quel est le score CVSS maximal d'une vulnérabilité informatique ?* ➔ **[5.0 / 10.0 / 100.0 ?]**
* **Visuels suggérés** : QR code Kahoot/Wooclap de la session.
* **Notes du présentateur** :
  * Lancer le quiz. Corriger.
  * *Réponses* : 1. Le SIEM ; 2. Une alerte déclenchée à tort ; 3. 10.0.

---

## Slide 10 : Clôture & Devoirs
* **Layout** : Fin de session / Devoirs
* **Texte affiché sur la slide** :
  * **Vos devoirs avant la prochaine séance (Self-paced)** :
    * Suivre le module IBM SkillsBuild : *Principes de la réponse aux incidents et bases de l'investigation numérique*.
    * Durée estimée : ~70 min.
    * Lire la documentation simplifiée sur le cycle de réponse à incident (lien fourni).
  * **Prochaine séance** : *Réponse aux incidents & introduction au forensics (A7)*.
  * Merci pour votre attention, soyez vigilants aux traces numériques !
* **Visuels suggérés** : Logo IBM SkillsBuild. Icône de loupe forensics.
* **Notes du présentateur** :
  * Remercier la classe.
  * Rappeler la prochaine date de session synchrone.
  * Déconnecter.
