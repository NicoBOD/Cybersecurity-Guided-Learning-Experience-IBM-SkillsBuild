# Spécifications des slides — Session B20 : Grand Atelier d'Audit Interactif & Clôture
Parcours : B 20 sessions  |  Module : Consolidation & Évaluation  |  Format : Spécifications Markdown

---

## Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  * Grand Atelier d'Audit Interactif — Restitution & Clôture du parcours
  * Résolution collective du cas MedDistri et exercice de gestion de crise
  * Parcours B — Session B20
- **Notes orateur** : Bienvenue pour cette dernière session de notre parcours de formation en cybersécurité de 20 sessions. Aujourd'hui, pas de soutenance orale classique de groupe. Nous menons ensemble un grand exercice d'audit interactif et de gestion de crise (Tabletop Exercise) à l'aide des sondages Livestorm. Nous ferons ensuite le bilan de toutes les compétences acquises.

---

## Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  * Évaluer globalement la sécurité d'une infrastructure d'entreprise.
  * Arbitrer entre sécurité technique, coûts et productivité opérationnelle.
  * Réagir face à une attaque par ransomware en cours (confinement, forensics, communication).
  * Sommaire : Lancement de l'Atelier MedDistri (10 min), Phase décisionnelle et votes (45 min), Débriefing & Schéma cible (15 min), Bilan & Certification IBM SkillsBuild (20 min).

---

## Slide 3 — Contexte étendu de MedDistri
- **Type** : étude de cas
- **Points clés (bullets)** :
  * PME de 25 salariés manipulant des données médicales.
  * Réseau à plat sans cloisonnement interne.
  * Ports SSH (22) et RDP (3389) ouverts sur le web sans authentification multifacteur (MFA).
  * Sauvegarde manuelle hebdomadaire sur disque dur USB connecté en permanence.
  * Données personnelles clients stockées sans registre RGPD ni DPO.
- **Notes orateur** : Notre objectif aujourd'hui est d'accompagner Mme Legrand pour transformer son entreprise vulnérable en structure cyber-résiliente. Nous partons d'un score de sécurité de 10% ; chaque bonne décision prise par le public augmentera ce score.

---

## Slide 4 — Sondage 1 : Architecture Réseau
- **Type** : quiz
- **Points clés (bullets)** :
  * *Quel schéma de segmentation réseau proposez-vous en priorité pour MedDistri pour mettre fin au réseau local plat ?*
    * **Choix A** : Mettre tous les postes sur le Wi-Fi invités.
    * **Choix B** : Créer 3 VLANs distincts (LAN Administratif, LAN Logistique, DMZ pour serveurs exposés) isolés par un pare-feu *(Bonne réponse)*.
    * **Choix C** : Acheter un commutateur supplémentaire sans configuration de VLAN.

---

## Slide 5 — Sondage 2 : Règles de filtrage
- **Type** : quiz
- **Points clés (bullets)** :
  * *Quelle règle de filtrage pare-feu essentielle devez-vous appliquer pour protéger le réseau interne contre un rebond depuis la DMZ ?*
    * **Choix A** : Autoriser tous les flux sortants du LAN interne vers la DMZ.
    * **Choix B** : Interdire tout flux initié depuis la DMZ vers le réseau interne LAN administratif *(Bonne réponse)*.
    * **Choix C** : Autoriser le trafic SSH de la DMZ vers le LAN.

---

## Slide 6 — Sondage 3 : Protection des données nomades
- **Type** : quiz
- **Points clés (bullets)** :
  * *Les 15 commerciaux utilisent leurs ordinateurs portables dans des lieux publics. Comment protéger les données stockées en cas de vol matériel ?*
    * **Choix A** : Installer un pare-feu personnel sur les ordinateurs.
    * **Choix B** : Chiffrer l'intégralité du disque système avec BitLocker ou FileVault *(Bonne réponse)*.
    * **Choix C** : Désactiver le mot de passe de session.

---

## Slide 7 — Sondage 4 : Politique de sauvegarde 3-2-1
- **Type** : quiz
- **Points clés (bullets)** :
  * *Quelle stratégie de sauvegarde remplace efficacement la sauvegarde USB permanente face à la menace des ransomwares ?*
    * **Choix A** : Mettre en œuvre une sauvegarde locale deux fois par jour sur un autre serveur du même réseau.
    * **Choix B** : Appliquer la règle 3-2-1 en combinant deux supports physiques locaux (dont un déconnecté hors ligne) et une sauvegarde immuable déportée dans le cloud *(Bonne réponse)*.
    * **Choix C** : Copier les fichiers sur OneDrive manuellement de temps en temps.

---

## Slide 8 — Sondage 5 : Incident Ransomware en Direct
- **Type** : quiz
- **Points clés (bullets)** :
  * *Un ransomware commence à chiffrer les postes de la comptabilité. Quelle est la première mesure de confinement à appliquer ?*
    * **Choix A** : Éteindre complètement les ordinateurs du réseau et contacter l'ANSSI.
    * **Choix B** : Débrancher le câble réseau (ou couper le Wi-Fi) de chaque machine infectée pour bloquer la propagation sans éteindre le système pour préserver la RAM *(Bonne réponse)*.
    * **Choix C** : Payer la rançon immédiatement à l'aide de la carte bancaire de l'entreprise.

---

## Slide 9 — Sondage 6 : Communication de crise
- **Type** : quiz
- **Points clés (bullets)** :
  * *Des journalistes contactent le service logistique de MedDistri au sujet de l'attaque. Quelle est la directive à imposer en interne ?*
    * **Choix A** : Laisser chaque employé répondre librement.
    * **Choix B** : Diriger toutes les demandes vers la directrice générale (cellule de crise) et interdire aux collaborateurs de s'exprimer en direct *(Bonne réponse)*.
    * **Choix C** : Couper le téléphone de l'entreprise.

---

## Slide 10 — Débriefing & Schéma réseau cible
- **Type** : schéma
- **Points clés (bullets)** :
  * Analyse des scores de résilience obtenus par MedDistri.
  * Modélisation de la DMZ, du pare-feu et des VLANs.
  * Validation du plan de réponse à incident.
- **Notes orateur** : Présenter le schéma réseau cible sécurisé et débriefez les choix d'incident. Expliquer l'importance du forensics sur la mémoire vive (RAM) qui justifie de ne pas éteindre brusquement le serveur.

---

## Slide 11 — Synthèse : Le chemin parcouru
- **Type** : récap
- **Points clés (bullets)** :
  * **Module A** : Fondations (Triade CIA, menaces, crypto).
  * **Module B** : Systèmes & Réseaux (segmentation, pare-feux).
  * **Module C** : Identités, accès & cloud (IAM, MFA, cloud).
  * **Module D** : Gouvernance, risque & conformité (PSSI, sauvegardes, RGPD).
  * **Module E** : Opérations & détection (SOC, SIEM, logs, incidents, crise Tabletop).

---

## Slide 12 — Félicitations & Clôture générale
- **Type** : récap
- **Points clés (bullets)** :
  * Un grand bravo pour votre investissement, votre assiduité et vos échanges.
  * **Prochaines étapes** : Validez vos quiz théoriques sur IBM SkillsBuild, récupérez votre badge numérique final et partagez-le sur LinkedIn !
  * *Restons connectés sur LinkedIn pour suivre vos réussites. Merci à tous !*
