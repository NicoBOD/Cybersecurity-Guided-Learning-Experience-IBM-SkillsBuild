# Guide des Démonstrations — Parcours A (8 sessions)
Parcours : A 8 sessions  |  Module : Démonstrations Mentor  |  Format : Scripts de démonstrations pas-à-pas

---

## Démo 1 (Session A1) : Cartographie passive de la surface d'exposition (OSINT)

* **Objectif** : Montrer aux apprenants ce qu'un attaquant peut voir sur une entreprise à partir de sources publiques et d'outils légaux, sans commettre d'intrusion active.
* **Durée estimée** : 10 minutes.
* **Outils utilisés** : Outils de requête DNS en ligne (ex. dnschecker.org) ou commande système `nslookup`, et portails publics d'OSINT.

### Script pas-à-pas :

1. **Introduction orale (1 min)** :
   * *"Bonjour à tous. Avant de mener une attaque, un pirate cherche à cartographier sa cible. C'est la phase de Reconnaissance de la Cyber Kill Chain. Nous allons voir comment un pirate rassemble des pièces du puzzle sur MedDistri (ou une cible de test) à l'aide d'outils publics."*

2. **Étape 1 : Recherche DNS passive (3 min)** :
   * Ouvrir une console ou utiliser un service web public de requête DNS.
   * Exécuter la commande ou soumettre le domaine :
     ```bash
     nslookup -type=mx entreprise-cible.fr
     ```
   * *Explication en direct* :
     *"Ici, nous demandons les enregistrements MX (Mail Exchange) de l'entreprise. Cela nous indique quel serveur de messagerie elle utilise. Nous pouvons voir si elle héberge ses propres serveurs de messagerie (exposant des vulnérabilités potentielles) ou si elle utilise une solution managée cloud comme Office 365 ou Google Workspace."*

3. **Étape 2 : Cartographier les serveurs publics (3 min)** :
   * Exécuter :
     ```bash
     nslookup -type=txt entreprise-cible.fr
     ```
   * Relever l'enregistrement SPF (Sender Policy Framework).
   * *Explication en direct* :
     *"L'enregistrement SPF contient la liste des serveurs autorisés à envoyer des e-mails au nom de cette entreprise. Un attaquant l'analyse pour repérer des services tiers sous-traitants (comme des outils d'envoi de newsletters ou de facturation) afin d'usurper leur identité."*

4. **Étape 3 : Synthèse pédagogique (3 min)** :
   * Rappeler que ces requêtes ne laissent aucune trace suspecte chez la victime.
   * *"Cette phase de reconnaissance passive donne à l'attaquant la liste des employés (via LinkedIn) et l'architecture de base (via DNS). Il a maintenant tout en main pour préparer son e-mail de phishing de la session suivante."*

---

## Démo 2 (Session A2) : Simulation de Vishing (Jeu de rôle vocal)

* **Objectif** : Sensibiliser les apprenants à la rapidité et à la force de persuasion de la manipulation humaine par téléphone.
* **Durée estimée** : 10 minutes.
* **Rôles** : Le Mentor (L'attaquant), Un apprenant volontaire (La victime - prévenue à l'avance pour le jeu de rôle).

### Script pas-à-pas :

1. **Mise en situation (2 min)** :
   * Le mentor appelle (par le micro de la classe virtuelle) la victime désignée.
   * *Le ton du mentor* : Pressé, sérieux, directif, mais chaleureux et rassurant à la fois.

2. **Le Dialogue simulé (5 min)** :
   * **Mentor** : *"Bonjour Thomas ? C'est Alexandre du support informatique central. Je t'appelle en urgence parce que notre SIEM vient de détecter une tentative d'intrusion russe sur ton compte Office 365. Tu as dû recevoir une notification ou un SMS d'alerte à l'instant, c'est bien le cas ?"*
   * **Thomas** (Victime) : *"Ah, attendez... oui, je viens de recevoir un SMS avec un code à 6 chiffres."*
   * **Mentor** : *"Parfait, c'est ce que je voulais vérifier. La connexion pirate est bloquée en attente. Pour la rejeter définitivement et réinitialiser tes accès, j'ai besoin que tu me dictes les 6 chiffres du SMS immédiatement. Faisons vite pour éviter qu'ils n'accèdent à tes emails commerciaux."*
   * **Thomas** : *"D'accord, c'est le 458 962."*
   * **Mentor** : *"Super, c'est validé de mon côté, la menace est écartée. Tu peux reprendre ton travail normalement. Merci pour ta réactivité, bonne journée !"*

3. **Débriefing collectif (3 min)** :
   * Arrêter la simulation. Interroger la classe.
   * *Questions au groupe* :
     * *"Qu'est-ce qui s'est réellement passé ?"* (L'attaquant a tenté de se connecter au compte Office de Thomas, ce qui a déclenché l'envoi d'un SMS MFA de sécurité. L'attaquant a appelé pour subtiliser ce code et valider sa connexion pirate).
     * *"Quels leviers ont été utilisés ?"* (L'urgence artificielle, l'autorité usurpée du support informatique, la confiance).
     * *"Quelle est la consigne d'hygiène cyber ?"* (Un administrateur informatique n'a **jamais** besoin de demander votre code MFA ou votre mot de passe par téléphone. Si on vous le demande, raccrochez).

---

## Démo 3 (Session A3) : Audit et logique de filtrage Pare-feu (Firewall)

* **Objectif** : Expliquer aux apprenants le concept de filtrage réseau et l'importance cruciale de l'ordre de priorité des règles.
* **Durée estimée** : 10 minutes.
* **Outils utilisés** : Projection d'un simulateur de tableau de règles ou fichier texte contenant les règles.

### Script pas-à-pas :

1. **Introduction orale (2 min)** :
   * *"Un pare-feu est comme le portier d'une discothèque. Il lit des consignes strictes écrites sur sa fiche de haut en bas. Dès qu'une consigne correspond au client qui se présente, il l'applique et s'arrête de lire la suite."*

2. **Étape 1 : Analyse de la configuration initiale (4 min)** :
   * Projeter le tableau de règles suivant :
     ```text
     [ RÈGLE 1 ] Source: LAN_Interne | Dest: Internet | Port: ANY | Action: ALLOW
     [ RÈGLE 2 ] Source: Internet   | Dest: Serv_Web | Port: 443 | Action: ALLOW
     [ RÈGLE 3 ] Source: Internet   | Dest: ANY      | Port: ANY | Action: DENY
     ```
   * *Explication en direct* :
     * *"La règle 1 permet à tous les salariés du réseau local (LAN) de naviguer sur Internet (tous ports autorisés en sortie)."*
     * *"La règle 2 permet aux clients extérieurs d'accéder au site web public de l'entreprise uniquement sur le port sécurisé HTTPS 443."*
     * *"La règle 3 est notre bouclier par défaut : tout le trafic entrant restant depuis Internet est bloqué (*Default Deny*)."*

3. **Étape 2 : Le piège de l'ordre d'application (3 min)** :
   * Poser la question aux apprenants :
     *"Imaginons que je commette une erreur et que je déplace la règle 3 tout en haut du tableau (en RÈGLE 1). Que se passe-t-il ?"*
   * *Explication en direct après réponse des élèves* :
     *"Si la règle interdisant tout trafic de manière globale est lue en premier, elle va correspondre à toutes les connexions. Les règles d'autorisation situées en dessous ne seront jamais lues. Les serveurs web seront inaccessibles et le réseau sera totalement paralysé. L'ordre des règles de pare-feu est donc tout aussi important que le contenu des règles elles-mêmes."*

4. **Synthèse pédagogique (1 min)** :
   * Résumer la consigne : toujours ordonner les règles du pare-feu de la plus spécifique (en haut) à la plus générale (en bas), en terminant toujours par le blocage implicite total.
