# Guide des Démonstrations Mentor — Parcours B (20 sessions)
Parcours : B 20 sessions  |  Module : Démonstrations Pratiques  |  Format : Scripts de démonstration pas-à-pas

---

## Démo 1 (Module A - Fondations) : Simulation de Vishing (Ingénierie Sociale)
*   **Objectif** : Sensibiliser les apprenants à l'efficacité de la manipulation par téléphone pour contourner les protections techniques (MFA).
*   **Durée estimée** : 10 minutes.
*   **Rôles** : Le Mentor (L'attaquant), Un apprenant volontaire (La victime - prévenu à l'avance).

### Script pas-à-pas :
1.  **Mise en contexte (2 min)** :
    *   Le mentor appelle l'apprenant volontaire via la classe virtuelle.
    *   *Posture du mentor* : Voix posée, professionnelle, incarnant l'urgence légitime.
2.  **Dialogue (5 min)** :
    *   **Mentor** : *"Bonjour Julie ? Ici Marc du service sécurité informatique. Je vous appelle car nous détectons des connexions géolocalisées inhabituelles depuis l'étranger sur votre boîte Microsoft 365. Nous avons gelé l'accès pour sécurité. Avez-vous reçu un SMS de confirmation ou une notification sur votre application Microsoft Authenticator à l'instant ?"*
    *   **Julie** : *"Ah, attendez... oui, mon téléphone vient de vibrer avec un code."*
    *   **Mentor** : *"C'est parfait, c'est que la sécurité réagit bien. Pour rejeter définitivement la tentative de piratage et déverrouiller votre session professionnelle, j'ai besoin que vous me dictiez le code à 6 chiffres qui s'affiche."*
    *   **Julie** : *"D'accord, c'est le 892 415."*
    *   **Mentor** : *"Parfait. C'est validé, votre session est sécurisée. Merci Julie, bonne fin de journée."*
3.  **Débriefing (3 min)** :
    *   *Explication technique* : Le pirate a saisi les identifiants de Julie (volés au préalable) sur la page officielle. Pour passer l'étape du MFA, il l'a appelée pour se faire dicter le code.
    *   *Consigne d'hygiène* : L'assistance informatique légitime ne demande **jamais** de code temporaire MFA ou de mot de passe par téléphone.

---

## Démo 2 (Module B - Réseaux) : Risques du trafic non chiffré (Wireshark Concept)
*   **Objectif** : Illustrer visuellement le danger d'utiliser des protocoles non chiffrés (HTTP) sur un réseau Wi-Fi public ou local partagé.
*   **Durée estimée** : 10 minutes.
*   **Outils** : Projection d'un extrait de capture réseau (format texte).

### Script pas-à-pas :
1.  **Mise en situation (2 min)** :
    *   Un utilisateur se connecte à un portail de gestion commerciale non sécurisé (`http://site-ecolog.fr/login.php`) depuis un Wi-Fi public d'hôtel. Un attaquant sur le même réseau capture le trafic.
2.  **Analyse de la capture réseau (5 min)** :
    *   Projeter la trame HTTP brute interceptée suivante :
        ```http
        POST /login.php HTTP/1.1
        Host: site-ecolog.fr
        User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)
        Content-Type: application/x-www-form-urlencoded
        Content-Length: 37

        username=admin&password=Password123!&action=submit
        ```
    *   *Commentaire du Mentor* :
        *"Regardez la fin de la capture. Comme le protocole utilisé est le HTTP (sans S), aucune donnée n'est chiffrée. Les identifiants `admin` et `Password123!` transitent en texte clair sur les ondes du Wi-Fi de l'hôtel. N'importe quel pirate équipé d'un analyseur de paquets gratuit comme Wireshark peut intercepter ces données instantanément."*

3.  **Synthèse (3 min)** :
    *   *Remédiation* : Forcer l'utilisation de HTTPS (chiffrement TLS). En HTTPS, les données en transit seraient remplacées par une suite de caractères indéchiffrables pour l'espion.

---

## Démo 3 (Module C - Données) : Hachage & Intégrité avec la ligne de commande
*   **Objectif** : Montrer comment calculer et vérifier l'intégrité d'un fichier téléchargé ou partagé en calculant son empreinte SHA-256.
*   **Durée estimée** : 10 minutes.
*   **Outils** : Terminal Linux (ou PowerShell Windows).

### Script pas-à-pas :
1.  **Création du fichier initial (3 min)** :
    *   Dans le terminal, tapez :
        ```bash
        echo "Contrat MedDistri 2026" > contrat.txt
        sha256sum contrat.txt
        ```
    *   *Résultat affiché* :
        `7f8a9e8b... contrat.txt`

    *   *Commentaire* : *"Voici l'empreinte unique de notre contrat."*
2.  **Modification mineure (3 min)** :
    *   Modifions un seul caractère (ajout d'un point à la fin) :
        ```bash
        echo "Contrat MedDistri 2026." > contrat.txt
        sha256sum contrat.txt
        ```
    *   *Résultat affiché* :
        `a3c5d6e2... contrat.txt`

    *   *Commentaire* : *"L'empreinte a totalement changé. C'est l'effet avalanche. Même une modification invisible à l'œil nu (comme un espace ou un point) rend le hachage complètement différent."*
3.  **Synthèse (4 min)** :
    *   Expliquer comment les éditeurs de logiciels fournissent la somme SHA-256 de leurs installateurs pour que les administrateurs puissent vérifier qu'ils n'ont pas été modifiés ou infectés par un virus sur la route du téléchargement.

---

## Démo 4 (Module D - Risques) : Calcul et traitement de risques en direct
*   **Objectif** : Guider la classe dans le calcul de la criticité brute et résiduelle d'un risque en direct.
*   **Durée estimée** : 10 minutes.
*   **Outils** : Tableau blanc numérique.

### Script pas-à-pas :
1.  **Présentation du scénario (2 min)** :
    *   *Scénario* : Perte ou vol d'un ordinateur portable non chiffré appartenant à un commercial de MedDistri.
2.  **Cotation Brute (sans mesures de sécurité) (3 min)** :
    *   *Vraisemblance (V)* : 3/4 (Fréquent : les commerciaux voyagent beaucoup dans les trains et gares).
    *   *Impact (I)* : 3/4 (Grave : les dossiers clients et contrats confidentiels sont stockés en clair sur l'appareil).
    *   *Criticité Brute* : 3 × 3 = 9 (Risque Élevé / Inacceptable).
3.  **Application des mesures de traitement (3 min)** :
    *   Mesure 1 : Activation du chiffrement BitLocker sur tous les postes nomades.
    *   Mesure 2 : Déploiement d'un outil de verrouillage à distance.
4.  **Cotation Résiduelle (après mesures) (2 min)** :
    *   *Vraisemblance (V)* : Reste à 3/4 (La probabilité de perdre ou de se faire voler le PC physique est la même).
    *   *Impact (I)* : Descend à 1/4 (Négligeable : les données étant chiffrées sur le disque dur, le voleur ne peut rien lire).
    *   *Criticité Résiduelle* : 3 × 1 = 3 (Risque Faible / Acceptable).

---

## Démo 5 (Module E - Opérations) : Analyse de logs d'intrusion en CLI Linux
*   **Objectif** : Montrer comment utiliser les commandes système Linux élémentaires (`grep`, `awk`, `wc -l`) pour repérer une attaque et isoler l'attaquant dans un fichier de logs.
*   **Durée estimée** : 15 minutes.
*   **Outils** : Terminal Linux.

### Script pas-à-pas :
1.  **Création du scénario de test (3 min)** :
    *   Le mentor montre aux élèves le fichier de logs `access.log` simulé.
2.  **Comptage du nombre de requêtes suspectes (4 min)** :
    *   Rechercher les tentatives d'accès aux fichiers sensibles du système :
        ```bash
        grep "etc/passwd" access.log
        ```
    *   *Explication* : *"Cette commande cherche les tentatives d'attaques par traversée de répertoires (directory traversal) où le pirate tente de lire le fichier de configuration des utilisateurs du serveur Linux."*
3.  **Isoler et dénombrer les adresses IP (4 min)** :
    *   Extraire la liste des adresses IP attaquant la page d'administration :
        ```bash
        grep "admin.php" access.log | awk '{print $1}' | sort | uniq -c
        ```
    *   *Explication en direct* :
        *   `grep "admin.php"` : isole les lignes visant l'administration.
        *   `awk '{print $1}'` : extrait la première colonne de la log (qui correspond à l'adresse IP source).
        *   `sort | uniq -c` : trie les IP et compte le nombre de fois que chaque IP apparaît.
    *   *Résultat* : L'IP `198.51.100.42` apparaît 150 fois en 2 minutes. C'est une attaque par force brute ou un scan agressif.
4.  **Action corrective (4 min)** :
    *   Expliquer comment copier cette adresse IP pour la bloquer sur le pare-feu local en tapant :
        ```bash
        iptables -A INPUT -s 198.51.100.42 -j DROP
        ```
    *   Le mentor conclut : *"En deux commandes système rapides, nous avons détecté l'attaquant et bloqué son accès au serveur."*
