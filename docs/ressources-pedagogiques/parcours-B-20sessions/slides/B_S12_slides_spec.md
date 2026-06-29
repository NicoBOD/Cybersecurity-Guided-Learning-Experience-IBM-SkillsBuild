# Spécifications des slides — Session B12 : Sécurité & confidentialité des données
Parcours : B 20 sessions  |  Module : C — Identités, cloud & données  |  Format : Spécifications Markdown

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Sécurité & confidentialité des données
  - Classification, chiffrement, DLP, stratégies de sauvegarde et Mini-projet 2
  - Parcours B — Session B12
- **Notes orateur** : Bienvenue dans notre douzième session. Aujourd'hui, nous allons nous concentrer sur l'actif le plus critique de l'entreprise : ses données. Nous allons voir comment classifier ces informations, comment les chiffrer efficacement au repos et en transit, comment prévenir les fuites de données avec un DLP, et comment élaborer un plan de sauvegarde résistant aux ransomwares.
- **Visuel suggéré** : Une cascade virtuelle de zéros et de uns vert cyberpunk se déversant dans un coffre-fort numérique géant sécurisé par des verrous cryptographiques lumineux.
  - **alt-text** : Flots de données sécurisés au sein d'un espace de stockage blindé.
- **Élément interactif** : Question sondage : "Qui a déjà sauvegardé ses fichiers importants cette semaine sur un support déconnecté d'Internet ?"

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Concevoir un schéma de classification des données adapté aux contraintes réglementaires.
  - Différencier le chiffrement des données au repos et le chiffrement en transit.
  - Expliquer le fonctionnement et l'intérêt d'un outil de prévention des fuites de données (DLP).
  - Appliquer la règle de sauvegarde 3-2-1 pour se prémunir des attaques par ransomware.
  - Sommaire : Classification des données (20 min), Chiffrement & DLP (20 min), Sauvegardes & Règle 3-2-1 (20 min), Lancement du Mini-projet 2 (20 min), Quiz (10 min).
- **Notes orateur** : Nous débuterons la séance en étudiant la classification des données. Nous aborderons ensuite le chiffrement et la prévention des fuites avec les outils DLP. Nous analyserons ensuite la règle de sauvegarde 3-2-1 avant de lancer officiellement les travaux du Mini-projet 2. Nous terminerons par notre quiz traditionnel.
- **Visuel suggéré** : Agenda temporel minuté affiché dans un panneau latéral, avec à gauche la liste des compétences clés.
  - **alt-text** : Tableau d'agenda minuté de la session synchrone de 90 minutes.

---

### Slide 3 — La classification des données : Pourquoi faire ?
- **Type** : contenu
- **Points clés (bullets)** :
  - **Problème** : On ne peut pas appliquer le même niveau de sécurité maximal à toutes les données (trop coûteux et trop complexe au quotidien).
  - **Solution** : Classer les données par niveau de sensibilité pour appliquer les bonnes protections.
  - Exemple de taxonomie standard à 4 niveaux :
    - **Publique** : Informations diffusables sans restriction (ex: plaquettes commerciales).
    - **Interne** : Usage restreint aux employés (ex: annuaire interne).
    - **Confidentielle** : Accès limité à certaines équipes (ex: salaires, projets en cours).
    - **Strictement confidentielle** : Secret stratégique (ex: secrets industriels, fusions-acquisitions).
- **Notes orateur** : Si vous protégez votre menu de cantine de la même manière que vos secrets industriels, vous allez dépenser beaucoup d'énergie pour rien et compliquer le travail des équipes. La classification permet d'identifier précisément les données hautement sensibles pour y allouer nos ressources de sécurité les plus fortes.
- **Visuel suggéré** : Pyramide à quatre niveaux de couleurs différentes (vert, bleu, jaune, rouge) illustrant la taxonomie de classification des données.
  - **alt-text** : Pyramide des niveaux de sensibilité de la classification des données.

---

### Slide 4 — Chiffrement : Au repos vs En transit
- **Type** : schéma
- **Points clés (bullets)** :
  - **Données en transit (In Transit)** :
    - Données circulant sur le réseau (ex: e-mail en cours d'envoi, transaction web).
    - Protection : **HTTPS / TLS / VPN**.
  - **Données au repos (At Rest)** :
    - Données stockées sur un disque physique ou une base de données (ex: serveurs, ordinateurs portables).
    - Protection : **AES-256 / BitLocker / Chiffrement de base de données**.
- **Notes orateur** : Il faut protéger les données dans tous leurs états. Quand elles bougent sur le réseau (en transit), on utilise des protocoles comme TLS pour empêcher l'interception. Quand elles dorment sur un support de stockage (au repos), on utilise des algorithmes comme l'AES-256 pour interdire la lecture en cas de vol du disque dur ou d'accès illégitime aux serveurs.
- **Visuel suggéré** : À gauche, un camion de livraison traversant un pont chiffré (en transit). À droite, un entrepôt de stockage blindé scellé par un cadenas (au repos).
  - **alt-text** : Comparatif graphique entre la sécurisation des données en mouvement et des données stockées.

---

### Slide 5 — DLP : Prévenir la fuite de données
- **Type** : contenu
- **Points clés (bullets)** :
  - **DLP (Data Loss Prevention)** : Outil logiciel qui inspecte les flux de données.
  - Empêche l'exfiltration accidentelle ou malveillante d'informations sensibles.
  - Détecte les anomalies en analysant le contenu (mots-clés, numéros de cartes bancaires, motifs regex) :
    - *Rèseau (Network DLP)* : Bloque l'envoi de documents confidentiels par e-mail externe.
    - *Poste (Endpoint DLP)* : Empêche la copie de fichiers clients sur une clé USB personnelle.
- **Notes orateur** : Le DLP est le garde-barrière des données. Il analyse en temps réel les flux d'informations. Si un employé tente de copier la liste complète des clients sur une clé USB, ou d'envoyer un fichier contenant 500 numéros de cartes de crédit par mail personnel, le DLP bloque l'action et avertit l'équipe de sécurité.
- **Visuel suggéré** : Un document texte étiqueté "Sensible" arrêté devant une barrière de sécurité numérique par un rayon laser de détection.
  - **alt-text** : Représentation fonctionnelle d'un système de prévention des fuites de données DLP.

---

### Slide 6 — La Règle d'or de la sauvegarde : Le 3-2-1
- **Type** : schéma
- **Points clés (bullets)** :
  - Seule défense infaillible contre la perte définitive due aux ransomwares.
  - **3 exemplaires** : Vos données de production + au moins 2 copies de sauvegarde.
  - **2 supports différents** : Stocker les copies sur des technologies physiques différentes (ex: disque dur externe, serveur NAS, cloud).
  - **1 copie hors site** : Conserver un exemplaire à l'extérieur des locaux (cloud sécurisé ou deuxième site physique) ET **hors ligne (Air-Gapped)**.
- **Notes orateur** : Les ransomwares modernes ne se contentent pas de chiffrer vos serveurs de production. Ils cherchent activement vos serveurs de sauvegardes sur le réseau pour les détruire en premier. La règle 3-2-1 vous protège de cela. Avoir une sauvegarde déconnectée physiquement du réseau (Air-Gapped) est la seule garantie de pouvoir reconstruire son informatique après une cyberattaque majeure.
- **Visuel suggéré** : Schéma présentant les trois chiffres 3, 2, 1 dans des cercles interconnectés avec des flèches illustrant la production, les deux supports physiques et le cloud distant.
  - **alt-text** : Schéma explicatif de la méthodologie de sauvegarde 3-2-1.

---

### Slide 7 — Le concept de sauvegarde "Air-Gapped" (Hors ligne)
- **Type** : contenu
- **Points clés (bullets)** :
  - **Définition** : Séparation physique ou logique complète entre le réseau informatique principal et le système de sauvegarde.
  - Une sauvegarde stockée sur un partage réseau accessible en permanence n'est **pas** protégée contre un ransomware.
  - Exemples de Air-Gap :
    - Bandes magnétiques de sauvegarde retirées physiquement du lecteur et rangées dans un coffre.
    - Disque dur externe USB débranché après chaque sauvegarde.
    - Coffres-forts cloud avec politiques d'écriture unique (WORM) non modifiables pendant X jours.
- **Notes orateur** : Qu'est-ce que l'Air-Gap ? C'est le fait d'avoir un "vide d'air" physique entre vos ordinateurs connectés à Internet et vos sauvegardes. Si un pirate prend le contrôle de vos serveurs de fichiers, il ne peut pas détruire un disque débranché posé sur une étagère. C'est simple, rustique, mais d'une efficacité redoutable.
- **Visuel suggéré** : Un pont-levis médiéval relevé, séparant un château fort (les sauvegardes) d'une plaine exposée aux attaques (le réseau Internet).
  - **alt-text** : Métaphore du pont-levis pour illustrer le concept d'Air-Gap cryptographique et physique.

---

### Slide 8 — Présentation du Mini-projet 2 : Contexte d'EcoLog
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **Entreprise** : EcoLog, société de conseil en environnement.
  - **Problème** : EcoLog gère des rapports clients confidentiels, des données RH de salariés et des informations financières. Aucune classification n'existe, et les sauvegardes se font sur un disque USB partagé en continu sur le réseau.
  - **Mission** : Élaborer un plan complet de protection des données pour l'entreprise.
- **Notes orateur** : Passons à la mise en œuvre de nos connaissances avec le lancement du Mini-projet 2. Vous allez intervenir chez EcoLog. L'entreprise est dans une situation risquée : ses données sont mélangées et son système de sauvegarde est vulnérable aux ransomwares. Votre rôle est de remettre de l'ordre et de concevoir leur stratégie de défense.
- **Visuel suggéré** : Logo fictif de la société EcoLog à gauche, et liste synthétique des trois types de données à risque à droite.
  - **alt-text** : Fiche de présentation du Mini-projet 2 pour l'entreprise EcoLog.

---

### Slide 9 — Cahier des charges du Mini-projet 2
- **Type** : contenu
- **Points clés (bullets)** :
  - Le livrable attendu doit contenir :
    - 1. **Une grille de classification des données** (RH, Finances, Rapports clients) avec les mesures de sécurité associées.
    - 2. **Une architecture de sauvegarde conforme 3-2-1** intégrant une isolation physique (Air-Gap).
    - 3. **Trois règles d'usage de DLP** pour empêcher les collaborateurs de fuiter involontairement des rapports clients confidentiels.
- **Notes orateur** : Ce mini-projet compte pour votre évaluation. Vous devez rédiger un rapport clair et structuré proposant une grille de classification à quatre niveaux adaptée, concevoir un schéma d'architecture de sauvegarde 3-2-1 et définir des règles d'usage pour un système DLP afin de sécuriser l'envoi de documents en externe.
- **Visuel suggéré** : Icône de document de rapport officiel tamponné et validé avec une liste à puces des trois livrables requis.
  - **alt-text** : Livrables obligatoires du Mini-projet 2.

---

### Slide 10 — Atelier collaboratif de démarrage
- **Type** : étude de cas
- **Points clés (bullets)** :
  - En groupes de 3 ou 4 apprenants (durée : 15 min).
  - **Première tâche** : Classer les trois types d'actifs suivants d'EcoLog :
    - Les bilans comptables de l'année précédente non encore publiés.
    - Les adresses e-mails professionnelles des salariés.
    - Les rapports écologiques finaux vendus et livrés aux clients.
  - Justifier vos choix en fonction de l'impact en cas de fuite publique.
- **Notes orateur** : Pour vous lancer sur le mini-projet, nous allons faire un premier atelier. Répartissez-vous en groupes. Vous devez classer trois types d'informations clés d'EcoLog dans notre taxonomie à quatre niveaux, et surtout justifier votre raisonnement. Qu'est-ce qui ferait le plus de dégâts s'il était publié dans la presse demain ?
- **Visuel suggéré** : Tableau croisé listant les 3 actifs avec des cases à cocher de couleur pour les niveaux de classification.
  - **alt-text** : Grille de démarrage de classification des données d'EcoLog.
- **Élément interactif** : Session de remue-méninges en petits groupes avec mise en commun.

---

### Slide 11 — Quiz de validation
- **Type** : quiz
- **Points clés (bullets)** :
  - 1. À quel niveau de classification (Publique, Interne, Confidente, Strictement Confidentielle) appartient une plaquette commerciale de vente ?
  - 2. Quelle est la différence majeure entre le chiffrement des données au repos et en transit ?
  - 3. Que signifie le chiffre "1" dans la règle de sauvegarde 3-2-1 ?
- **Notes orateur** : C'est le moment de tester vos acquis avant de vous laisser travailler sur le mini-projet. Connectez-vous sur la plateforme de vote et répondez aux questions sur la classification, le chiffrement et la règle 3-2-1.
- **Visuel suggéré** : QR Code d'accès au système de vote à gauche et questions interactives à droite.
  - **alt-text** : QR Code d'accès au vote électronique synchrone.
- **Élément interactif** : Quiz en direct avec correction immédiate.

---

### Slide 12 — Conclusion & Prochaines étapes
- **Type** : récap
- **Points clés (bullets)** :
  - **Résumé** : Classification indispensable, chiffrement (double aspect repos/transit), DLP pour bloquer les fuites d'usages, et règle 3-2-1 (Air-Gap contre ransomwares).
  - **Travail personnel** : Rédaction et dépôt de votre livrable pour le Mini-projet 2 d'ici la semaine prochaine.
  - **IBM SkillsBuild** : Suivre le cours *"Data Security and Privacy Essentials"* (~1h30).
  - Prochaine session : *Gouvernance & cadres de sécurité (B13)*.
- **Notes orateur** : Nous avons terminé notre module sur les systèmes et les données ! Vous avez désormais toutes les clés pour rédiger le plan de protection des données d'EcoLog. N'oubliez pas de déposer votre travail sur la plateforme avant la semaine prochaine et de valider votre module d'apprentissage SkillsBuild. Bon courage et bonne fin de journée !
- **Visuel suggéré** : Badge d'achèvement de cours d'IBM SkillsBuild pour la sécurité et la confidentialité des données.
  - **alt-text** : Badge de réussite du cours Data Security d'IBM SkillsBuild.
