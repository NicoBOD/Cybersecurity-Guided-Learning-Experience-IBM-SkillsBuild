# Grand Atelier d'Audit Interactif — MedDistri
Parcours : A 8 sessions  |  Module : Consolidation & Clôture  |  Format : Atelier Décisionnel Collectif (Livestorm)

---

## 1. Contexte de l'entreprise : "MedDistri"

Mme Legrand est la Directrice Générale de **MedDistri**, une PME de 25 salariés spécialisée dans la distribution de matériel médical (pansements, masques, petits instruments) pour les cliniques et hôpitaux. Elle n'a pas de profil informatique et s'inquiète de la recrudescence des cyberattaques visant le secteur de la santé — elle a suivi de près l'affaire de l'hôpital de Corbeil-Essonnes (étudiée en session A1) et sait que ses clients hospitaliers lui demanderont bientôt des garanties.

### L'infrastructure informatique actuelle de MedDistri :
* **Effectifs** : 15 commerciaux en télétravail ou déplacement régulier, 5 logisticiens (entrepôt), 4 administratifs (RH, compta, direction) et 1 technicien informatique polyvalent jouant le rôle d'administrateur système de manière informelle.
* **Systèmes locaux** : Un serveur de fichiers physique situé dans un placard à balai dans l'entrepôt. Il stocke les dossiers administratifs, la comptabilité et les fichiers de propriété industrielle de l'entreprise (plans de produits, brevets).
* **Accès distant** : Pour accéder au serveur à distance, le technicien a configuré un accès ouvert sur Internet sur le port 22 (SSH) et le port 3389 (Bureau à distance Windows) sans restriction d'adresses IP. Le mot de passe du compte administrateur est `Admin@MedDistri2025` (mot de passe fictif, pour les besoins de l'exercice).
* **Services Cloud** : L'entreprise utilise la suite Microsoft 365 pour les courriels, Teams et le partage de documents commerciaux sur OneDrive. L'authentification multifacteur (MFA) n'est pas activée car les utilisateurs trouvent cela "trop lourd au quotidien".
* **Sauvegardes** : Le technicien informatique effectue une sauvegarde de la base de données de ventes chaque vendredi soir sur un disque dur externe branché en permanence au serveur de l'entrepôt.
* **Sécurité & Vie Privée** : L'entreprise n'a pas de Politique de Sécurité des Systèmes d'Information (PSSI) écrite ni de registre de traitement des données RGPD, bien qu'elle gère des fichiers contenant des données nominatives de ses clients (médecins, directeurs de cliniques) et les historiques de commandes.

!!! info "Pour le mentor — le fil rouge du parcours"
    Chaque faille de MedDistri renvoie à une session et à un cas réel étudié : les ports exposés (A3 — le brise-glace du serveur-appât et Mirai), l'absence de MFA (A4 — le chiffre Microsoft des 99,9 %), le disque USB branché en permanence (A4 — le NAS piégé et l'incendie OVHcloud), l'absence de PSSI et de registre (A5 — la gouvernance et le RGPD), le secteur santé lui-même (A1 — l'hôpital de Corbeil-Essonnes). L'atelier est la tournée d'adieu de tous les cas du parcours : nommez-les au fil des débriefs.

---

## 2. Déroulement de l'Atelier en Visioconférence (Livestorm)

Cet atelier n'exige aucun rendu écrit ni travail de groupe hors séance. Il s'agit d'une simulation collective où les participants conseillent Mme Legrand et le technicien de MedDistri en direct en répondant à des sondages interactifs. Le mentor anime la séance en commentant les choix faits par l'auditoire et en mettant à jour le **Score de Résilience Cyber** de la PME (qui commence à **10 %**).

> **Numérotation des sondages** : la session A8 compte 9 sondages Livestorm. Les n°1 à 3 (échauffement de l'auditeur) et n°8-9 (objections métier et bilan) sont définis dans le [support](../supports-md/A_S08_support.md) et le [plan de séance](../plans-de-seance/A_S08_plan.md). Les **quatre sondages d'audit ci-dessous sont les n°4 à 7** de la session.

### Phase 1 : Diagnostic d'urgence (Fermer les portes d'entrée)

*   **📊 Sondage n°4 — L'accès RDP et SSH ouvert sur Internet :** Les ports RDP (3389) et SSH (22) de MedDistri sont accessibles depuis n'importe quelle adresse IP publique avec un mot de passe connu. Quelle est l'action prioritaire absolue ?
    *   A) Installer un pare-feu local gratuit sur chaque poste et changer le mot de passe tous les ans.
    *   B) Fermer l'accès direct aux ports 22 et 3389 depuis Internet, déployer un serveur VPN d'accès distant et activer le MFA sur ce VPN ✅ *(Gain : +25 % de résilience)*
    *   C) Ne rien changer car les commerciaux ont besoin d'accéder aux données et le mot de passe est complexe.

    **Débrief mentor :** Exposer des ports d'administration directement sur Internet est l'un des tout premiers vecteurs d'infection par ransomware : les cybercriminels scannent le web en continu pour forcer ces accès (rappel A3 : le serveur-appât attaqué en quelques minutes, et l'ANSSI qui classe les équipements exposés parmi les premiers vecteurs d'intrusion). Le VPN avec MFA est la seule méthode d'accès nomade sécurisée. Bonus de débrief : faire remarquer que le mot de passe `Admin@MedDistri2025` suit un schéma prévisible (nom de l'entreprise + année) — exactement ce que testent les dictionnaires.

*   **📊 Sondage n°5 — L'absence de MFA sur Microsoft 365 :** Mme Legrand craint que l'activation du MFA sur Microsoft 365 ne ralentisse le travail des commerciaux nomades. Comment la convaincre ?
    *   A) Lui expliquer que, selon Microsoft, le MFA bloque plus de 99,9 % des attaques automatisées de compromission de comptes, et que le vol d'un compte mail permettrait d'envoyer de fausses factures à vos clients ✅ *(Gain : +20 % de résilience)*
    *   B) Mettre en place un mot de passe obligatoire de 30 caractères sans MFA.
    *   C) Menacer de couper l'accès aux serveurs aux employés récalcitrants.

    **Débrief mentor :** Le vol d'identité par hameçonnage est massif (rappel A2 : moins d'une minute entre l'ouverture et la saisie des identifiants). Les mots de passe complexes ne protègent pas contre un site de phishing ; seul le MFA bloque la connexion du pirate. Et le scénario des fausses factures aux clients est exactement la mécanique BEC de l'affaire Pathé (A2) — un argument que Mme Legrand, dirigeante, comprend immédiatement.

---

### Phase 2 : Assurer la résilience (La survie après l'attaque)

*   **📊 Sondage n°6 — Analyse critique des sauvegardes :** La sauvegarde manuelle hebdomadaire de MedDistri est copiée sur un disque dur externe branché en permanence en USB sur le serveur de fichiers local. Pourquoi cette méthode est-elle dangereuse ?
    *   A) Le disque dur externe est trop lent et chauffe.
    *   B) En cas d'attaque par ransomware, le disque dur connecté sera également chiffré par l'attaquant, rendant la sauvegarde inutile ✅ *(Gain : +25 % de résilience)*
    *   C) La sauvegarde manuelle du vendredi soir fatigue le technicien informatique.

    **Débrief mentor :** Pour se protéger des rançongiciels, la sauvegarde doit respecter la règle 3-2-1 (A4), avec une copie déconnectée ou immuable — les ransomwares chiffrent en priorité les sauvegardes joignables. Rappels utiles : le « NAS piégé » d'A4, l'incendie OVHcloud (le hors-site, c'est aussi contre le feu) et Maersk (A7 : la seule sauvegarde survivante était hors ligne... par accident).

*   **📊 Sondage n°7 — Répartition du budget cyber :** Le budget cyber annuel total de MedDistri est limité à 2 000 €. Quelle est l'allocation la plus efficace ?
    *   A) Acheter un équipement pare-feu haut de gamme d'une valeur de 2 000 € et conserver les systèmes actuels sans mise à jour.
    *   B) Investir dans des licences VPN/MFA légères, mettre en place une sauvegarde cloud chiffrée et former les collaborateurs aux risques numériques ✅ *(Gain : +20 % de résilience)*
    *   C) Réaliser un test de pénétration complet par un cabinet d'audit externe à 2 000 €.

    **Débrief mentor :** Une PME doit allouer son budget sur l'hygiène informatique de base (sauvegarde, identités, sensibilisation) plutôt que sur des outils coûteux et isolés. Le pentest (option C) n'est pas inutile — il est prématuré : auditer un système dont on connaît déjà les failles béantes, c'est payer pour apprendre ce qu'on sait (rappel A6 : scan d'abord, pentest quand l'hygiène est en place). C'est la logique du Comité des Risques d'A5 : prioriser par criticité et par coût.

---

## 3. Bilan de l'Atelier

À l'issue de cet atelier décisionnel, le mentor compile les scores de l'auditoire : le Score de Résilience Cyber démarre à **10 %** et chaque bonne réponse majoritaire ajoute son gain (+25, +20, +25, +20 = un maximum de **100 %**). Si le score de résilience de la PME MedDistri atteint ou dépasse **80 %**, l'audit est validé avec succès par la communauté des apprenants.

En cas de score inférieur : le mentor rejoue les questions manquées en mode « seconde délibération du comité d'audit » (re-vote après débat dans le chat) — l'objectif pédagogique est que le groupe reparte avec la feuille de route complète, pas de sanctionner.
