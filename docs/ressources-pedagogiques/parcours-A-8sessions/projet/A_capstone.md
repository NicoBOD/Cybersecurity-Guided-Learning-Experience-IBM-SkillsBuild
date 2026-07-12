# Grand Atelier d'Audit Interactif — MedDistri
Parcours : A 8 sessions  |  Module : Consolidation & Clôture  |  Format : Atelier Decisionnel Collectif (Livestorm)

---

## 1. Contexte de l'entreprise : "MedDistri"

Mme Legrand est la Directrice Générale de **MedDistri**, une PME de 25 salariés spécialisée dans la distribution de matériel médical (pansements, masques, petits instruments) pour les cliniques et hôpitaux. Elle n'a pas de profil informatique et s'inquiète de la recrudescence des cyberattaques visant le secteur de la santé.

### L'infrastructure informatique actuelle de MedDistri :
* **Effectifs** : 15 commerciaux en télétravail ou déplacement régulier, 5 logisticiens (entrepôt), 4 administratifs (RH, compta, direction) et 1 technicien informatique polyvalent jouant le rôle d'administrateur système de manière informelle.
* **Systèmes locaux** : Un serveur de fichiers physique situé dans un placard à balai dans l'entrepôt. Il stocke les dossiers administratifs, la comptabilité et les fichiers de propriété industrielle de l'entreprise (plans de produits, brevets).
* **Accès distant** : Pour accéder au serveur à distance, le technicien a configuré un accès ouvert sur Internet sur le port 22 (SSH) et le port 3389 (Bureau à distance Windows) sans restriction d'adresses IP. Le mot de passe du compte administrateur est `Admin@MedDistri2025`.
* **Services Cloud** : L'entreprise utilise la suite Microsoft 365 pour les courriels, Teams et le partage de documents commerciaux sur OneDrive. L'authentification multifacteur (MFA) n'est pas activée car les utilisateurs trouvent cela "trop lourd au quotidien".
* **Sauvegardes** : Le technicien informatique effectue une sauvegarde de la base de données de ventes chaque vendredi soir sur un disque dur externe branché en permanence au serveur de l'entrepôt.
* **Sécurité & Vie Privée** : L'entreprise n'a pas de Politique de Sécurité des Systèmes d'Information (PSSI) écrite ni de registre de traitement des données RGPD, bien qu'elle gère des fichiers contenant des données nominatives de ses clients (médecins, directeurs de cliniques) et les historiques de commandes.

---

## 2. Déroulement de l'Atelier en Visioconférence (Livestorm)

Cet atelier n'exige aucun rendu écrit ni travail de groupe hors séance. Il s'agit d'une simulation collective où les participants conseillent Mme Legrand et le technicien de MedDistri en direct en répondant à des sondages interactifs. Le mentor anime la séance en commentant les choix faits par l'auditoire et en mettant à jour le **Score de Résilience Cyber** de la PME (qui commence à 10%).

### Phase 1 : Diagnostic d'urgence (Fermer les portes d'entrée)

* **Sondage 1 : L'accès RDP et SSH ouvert sur Internet**
  * *Question :* Les ports RDP (3389) et SSH (22) de MedDistri sont accessibles depuis n'importe quelle adresse IP publique avec un mot de passe connu (`Admin@MedDistri2025`). Quelle est l'action prioritaire absolue ?
    * A) Installer un pare-feu local gratuit sur chaque poste et changer le mot de passe tous les ans.
    * B) Fermer l'accès direct aux ports 22 et 3389 depuis Internet, déployer un serveur VPN d'accès distant et activer le MFA sur ce VPN *(Bonne réponse — Gain : +25% de résilience)*.
    * C) Ne rien changer car les commerciaux ont besoin d'accéder aux données et le mot de passe est complexe.
  * *Explication du mentor :* Ouvrir le port 3389 directement sur Internet est la cause n°1 d'infection par ransomware. Les cybercriminels scannent le web en continu pour forcer ces accès. Le VPN avec MFA est la seule méthode d'accès nomade sécurisée.

* **Sondage 2 : L'absence de MFA sur Microsoft 365**
  * *Question :* Mme Legrand craint que l'activation du MFA sur Microsoft 365 ne ralentisse le travail des commerciaux nomades. Comment la convaincre ?
    * A) Lui expliquer que, selon Microsoft, le MFA bloque plus de 99,9 % des attaques automatisées de compromission de comptes, et que le vol d'un compte mail permettrait d'envoyer de fausses factures à vos clients *(Bonne réponse — Gain : +20% de résilience)*.
    * B) Mettre en place un mot de passe obligatoire de 30 caractères sans MFA.
    * C) Menacer de couper l'accès aux serveurs aux employés récalcitrants.
  * *Explication du mentor :* Le vol d'identité par hameçonnage est massif. Les mots de passe complexes ne protègent pas contre un site de phishing ; seul le MFA bloque la connexion du pirate.

---

### Phase 2 : Assurer la résilience (La survie après l'attaque)

* **Sondage 3 : Analyse critique des sauvegardes**
  * *Question :* La sauvegarde manuelle hebdomadaire de MedDistri est copiée sur un disque dur externe branché en permanence en USB sur le serveur de fichiers local. Pourquoi cette méthode est-elle obsolète ?
    * A) Le disque dur externe est trop lent et chauffe.
    * B) En cas d'attaque par ransomware, le disque dur connecté sera également chiffré par l'attaquant, rendant la sauvegarde inutile *(Bonne réponse — Gain : +25% de résilience)*.
    * C) La sauvegarde manuelle du vendredi soir fatigue le technicien informatique.
  * *Explication du mentor :* Pour se protéger des rançongiciels, la sauvegarde doit respecter la règle 3-2-1. La copie de sauvegarde principale doit être stockée de manière déconnectée (hors ligne) ou dans un espace de stockage cloud immuable (non modifiable par le réseau).

* **Sondage 4 : Répartition du budget cyber**
  * *Question :* Le budget cyber annuel total de MedDistri est limité à 2 000 €. Quelle est l'allocation la plus efficace ?
    * A) Acheter un équipement pare-feu haut de gamme d'une valeur de 2 000 € et conserver les systèmes actuels sans mise à jour.
    * B) Investir dans des licences VPN/MFA légères, mettre en place une sauvegarde cloud cryptée et former les collaborateurs aux risques numériques *(Bonne réponse — Gain : +20% de résilience)*.
    * C) Réaliser un test de pénétration complet par un cabinet d'audit externe à 2 000 €.
  * *Explication du mentor :* Une PME doit allouer son budget sur l'hygiène informatique de base (sauvegarde, identités, sensibilisation) plutôt que sur des outils coûteux et isolés.

---

## 3. Bilan de l'Atelier
À l'issue de cet atelier décisionnel, le mentor compile les scores de l'auditoire. Si le score de résilience de la PME MedDistri atteint ou dépasse **80%**, l'audit est validé avec succès par la communauté des apprenants.
