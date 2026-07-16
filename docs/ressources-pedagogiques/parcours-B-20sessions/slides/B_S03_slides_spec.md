# Spécifications des slides — Session B03 : Types d'attaques & vecteurs
Parcours : B 20 sessions  |  Module : A — Fondations  |  Format : Spécifications Markdown

> **Principe** : le texte affiché reste minimal (mots-clés, chiffres, schémas) ; le contenu riche est dans les notes orateur et le [plan de séance minuté](../plans-de-seance/B_S03_plan.md). Toutes les interactions passent par les sondages et le chat Livestorm.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Types d'attaques & vecteurs d'intrusion
  - Décoder la mécanique d'une cyberattaque
  - Parcours B — Session B03
- **Notes orateur** : Accueillir, puis lancer le retour sur la veille : « qui s'est abonné au CERT-FR ? Tapez dans le chat le produit concerné par une alerte repérée cette semaine. » Lire 3-4 alertes, féliciter. Rappel express de B02 (quatre familles d'attaquants, RaaS, CTI). Annonce : après QUI attaque, place à COMMENT.
- **Visuel suggéré** : Fond sombre avec des lignes de code informatique vertes et un symbole d'alerte système discret.
  - **alt-text** : Code source informatique affiché en vert sur un écran noir d'ordinateur avec une icône d'alerte.
- **Élément interactif** : 💬 Chat d'accueil — les alertes CERT-FR repérées pendant la semaine.

---

### Slide 2 — Objectifs & agenda
- **Type** : contenu
- **Points clés (bullets)** :
  - Classifier les familles de logiciels malveillants (*malwares*).
  - Modéliser une attaque : les 7 étapes de la *Cyber Kill Chain* + MITRE ATT&CK.
  - Comprendre DDoS et injections SQL.
  - Agenda : typologie → Kill Chain → enquête « PlastiqueNord » → WannaCry & NotPetya → DDoS/SQL → quiz.
- **Notes orateur** : Programme dense : d'abord mettre de l'ordre dans le zoo des malwares, puis l'outil d'analyse de référence (la Kill Chain), une enquête à mener ensemble par sondages, et deux catastrophes mondiales décortiquées — dont l'une a été stoppée par un achat à 10 dollars.
- **Visuel suggéré** : Deux colonnes claires séparant les objectifs opérationnels et l'agenda de la séance.
  - **alt-text** : Tableau présentant les objectifs d'apprentissage à gauche et les étapes de la séance à droite.

---

### Slide 3 — Brise-glace : la vitesse d'un ver
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **Sondage n°1** : WannaCry — plus de 200 000 machines, 150 pays... en combien de temps ?
  - A) Un seul week-end — B) Six mois — C) Deux ans
- **Notes orateur** : Lancer le sondage n°1 (60-90 s). Réponse A : l'essentiel en quelques heures, le 12 mai 2017 (Europol). Aucun humain ne clique aussi vite — c'est la signature d'un ver, un malware autonome. Teaser : l'histoire complète de WannaCry arrive en seconde partie de session.
- **Visuel suggéré** : Carte du monde s'illuminant de points rouges avec un chronomètre en surimpression.
  - **alt-text** : Planisphère couvert de points d'infection rouges accompagné d'un chronomètre symbolisant la vitesse de propagation.
- **Élément interactif** : 📊 Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — Le zoo des malwares : cinq familles
- **Type** : schéma
- **Points clés (bullets)** :
  - **Virus** : a besoin d'un fichier hôte et d'un clic humain.
  - **Ver** : autonome — se propage seul par le réseau.
  - **Cheval de Troie** : le cadeau piégé, installé par la victime.
  - **Rançongiciel** : chiffre et rançonne (la charge du RaaS, cf. B02).
  - **Spyware / keylogger** : observe et vole en silence.
- **Notes orateur** : Le mot juste est « malware » — le virus n'est qu'une famille. Deux questions pour classer : comment ça se propage, et qu'est-ce que ça fait une fois en place. Dérouler les analogies : virus biologique, bactérie autonome, mythe grec. Relance chat : « qui a déjà croisé l'un d'eux, au travail ou à la maison ? »
- **Visuel suggéré** : Planche de cinq vignettes illustrées, une par famille, avec une icône de propagation (clic, réseau, cadeau) et une icône d'objectif (cadenas, œil).
  - **alt-text** : Cinq vignettes illustrant virus, ver, cheval de Troie, rançongiciel et logiciel espion avec leurs modes de propagation.
- **Élément interactif** : 💬 Chat — « quelle famille avez-vous déjà croisée ? »

---

### Slide 5 — Les familles se combinent
- **Type** : contenu
- **Points clés (bullets)** :
  - Un malware = propagation **+** charge utile.
  - Exemple : WannaCry = ver (propagation) + ransomware (charge).
  - Un cheval de Troie peut livrer un spyware... ou un chargeur.
- **Notes orateur** : Le point que les débutants ratent : ces catégories ne sont pas étanches. On décrit toujours un malware par ses deux dimensions. C'est pour cela que WannaCry a été si dévastateur : la vitesse d'un ver avec la destructivité d'un ransomware. Mentionner (pour les curieux) l'évolution moderne : malwares sans fichier, exécutés en mémoire.
- **Visuel suggéré** : Équation visuelle : icône de réseau (propagation) + icône de cadenas (charge utile) = silhouette de malware composite.
  - **alt-text** : Équation graphique combinant un mode de propagation et une charge utile pour former un malware hybride.

---

### Slide 6 — La Cyber Kill Chain : l'attaque en 7 étapes
- **Type** : schéma
- **Points clés (bullets)** :
  - Modèle Lockheed Martin : 7 étapes chronologiques obligatoires.
  - Reconnaissance → Armement → Livraison → Exploitation → Installation → C2 → Actions sur objectifs.
  - **Principe défensif : briser UN seul maillon suffit.**
- **Notes orateur** : Dérouler les 7 étapes avec le fil rouge d'un e-mail piégé : repérage sur LinkedIn, création du document piégé, envoi, clic qui déclenche la faille, persistance, la machine qui « téléphone » à l'attaquant, puis l'action finale. Question rhétorique : le défenseur doit-il bloquer les 7 étapes ? Non — une seule. C'est le message le plus rassurant de la session.
- **Visuel suggéré** : Chaîne de 7 maillons étiquetés, dont un maillon central brisé par un bouclier.
  - **alt-text** : Chaîne métallique de sept maillons nommés selon les étapes de la Cyber Kill Chain, avec un maillon brisé par un bouclier.

---

### Slide 7 — À chaque étape sa parade
- **Type** : tableau
- **Points clés (bullets)** :
  - Livraison → filtrage e-mail + sensibilisation.
  - Exploitation → correctifs et mises à jour.
  - C2 → surveillance du trafic **sortant**.
  - Actions sur objectifs → sauvegardes hors ligne.
- **Notes orateur** : La défense en profondeur : chaque couche pallie la défaillance d'une autre. Insister sur le C2 : la machine compromise ouvre une connexion sortante, car les pare-feux bloquent l'entrant mais laissent sortir — d'où l'intérêt de surveiller aussi ce qui sort du réseau. Ce tableau servira de grille de correction pour l'enquête qui arrive.
- **Visuel suggéré** : Tableau à deux colonnes « Étape → Parade » avec des icônes de bouclier alignées.
  - **alt-text** : Tableau associant chaque étape de la Kill Chain à la mesure de défense correspondante.

---

### Slide 8 — MITRE ATT&CK : l'encyclopédie du réel
- **Type** : contenu
- **Points clés (bullets)** :
  - Matrice mondiale des comportements **observés** des attaquants.
  - **Tactiques** (le but) × **Techniques** (le moyen).
  - C'est là que vivent les **TTP** vus en B02 — fiche « Lazarus Group » incluse.
  - Kill Chain = la vue d'ensemble ; ATT&CK = le détail de terrain.
- **Notes orateur** : Contrairement à la Kill Chain, ATT&CK n'impose pas d'ordre : il recense tout ce qui a réellement été observé, groupe par groupe. Option démo (2 min) : partager l'écran sur attack.mitre.org et ouvrir la technique « Phishing » (T1566) — description, groupes utilisateurs, parades. Le devoir de la semaine dernière prend vie.
- **Visuel suggéré** : Aperçu épuré de la matrice ATT&CK avec colonnes de tactiques et cellules de techniques, quelques cellules surlignées.
  - **alt-text** : Représentation simplifiée de la matrice MITRE ATT&CK en tableau à double entrée avec des cellules mises en évidence.
- **Élément interactif** : Démonstration en direct de la fiche T1566 (optionnelle).

---

### Slide 9 — Enquête : le piratage de PlastiqueNord
- **Type** : activité (sondages)
- **Points clés (bullets)** :
  - 7 événements réels... livrés dans le désordre par les journaux.
  - Votre mission : replacer chaque événement dans la Kill Chain.
  - 📊 **Sondages n°2, 3, 4** : LinkedIn ? Connexion sortante ? Exécution au démarrage ?
- **Notes orateur** : Lire le récit à voix haute (affiché au support), puis lancer les trois sondages avec débrief entre chaque. Pièges : la connexion sortante régulière est du C2 (pas de l'installation) ; l'exécution au démarrage est de l'Installation (persistance). Terminer par la reconstitution complète B → F → G → E → C → D → A et demander : « où auriez-vous cassé la chaîne ? Réponse : partout. »
- **Visuel suggéré** : Les 7 étapes de la chaîne en colonne verticale avec des cartes d'événements A à G mélangées à côté.
  - **alt-text** : Exercice visuel associant des cartes d'événements désordonnées aux sept étapes de la Cyber Kill Chain.
- **Élément interactif** : 📊 Sondages Livestorm n°2 à 4 — classification collective par votes.

---

### Slide 10 — Affaire n°1 : WannaCry (mai 2017)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Ver + ransomware · exploit **EternalBlue** (volé à la NSA).
  - **200 000+ machines, 150 pays** en quelques heures (Europol).
  - NHS : ~19 000 rendez-vous et opérations annulés (National Audit Office).
  - Stoppé par... l'achat d'un nom de domaine à quelques dollars.
- **Notes orateur** : Raconter : la fuite Shadow Brokers, la déferlante du 12 mai, Renault qui stoppe des usines par précaution — puis le chercheur de 22 ans qui enregistre le domaine trouvé dans le code et déclenche le « kill switch » sans le savoir. Attribution : Lazarus, le groupe de la fiche d'identité de B02. La leçon qui tue : le correctif MS17-010 existait depuis deux mois.
- **Visuel suggéré** : Écran de rançon WannaCry stylisé à gauche, interrupteur d'arrêt d'urgence étiqueté « kill switch » à droite.
  - **alt-text** : Interface de demande de rançon de WannaCry face à un interrupteur d'arrêt d'urgence symbolisant le kill switch.

---

### Slide 11 — Affaire n°2 : NotPetya (juin 2017)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Déguisé en ransomware — en réalité un **wiper** : payer ne rend rien.
  - Vecteur : mise à jour piégée d'un logiciel comptable (**supply chain**).
  - Maersk : 45 000 PC détruits — sauvé par un serveur au Ghana.
  - **> 10 milliards $** de dégâts mondiaux (estimation des autorités américaines).
- **Notes orateur** : Six semaines après WannaCry, en pire : EternalBlue encore, plus le vol de mots de passe en mémoire. Saint-Gobain : ~250 M€ de ventes perdues. Maersk réinstalle toute son informatique en une dizaine de jours grâce à un contrôleur de domaine épargné par une coupure de courant. Motivation : sabotage étatique visant l'Ukraine — la typologie de B02 s'applique aussi aux malwares. Règle d'or : sauvegardes hors ligne. Relance chat : « quel détail vous marque le plus ? »
- **Visuel suggéré** : Porte-conteneurs stylisé à quai avec des écrans rouges, et un unique serveur allumé sur une carte de l'Afrique de l'Ouest.
  - **alt-text** : Navire porte-conteneurs immobilisé face à des écrans en erreur, avec un serveur isolé mis en évidence au Ghana.
- **Élément interactif** : 💬 Chat — réactions au cas NotPetya.

---

### Slide 12 — Et chez vous ? Le rythme des mises à jour
- **Type** : sondage (opinion)
- **Points clés (bullets)** :
  - 📊 **Sondage n°5** : chez vous, les mises à jour de sécurité sont appliquées...
  - A) Vite et systématiquement — B) En fenêtres planifiées — C) Irrégulièrement / je ne sais pas.
  - Rappel : WannaCry = un correctif ignoré pendant 2 mois.
- **Notes orateur** : Sondage d'opinion, pas de bonne réponse. B est la réalité majoritaire et c'est sain SI le délai se compte en jours pour les failles critiques « wormables ». Les C sont précieux : ne pas savoir est déjà une information. Enchaîner sur le mini-scénario : « et si le correctif critique impose de redémarrer la production ? Tapez A, B ou C » (le scénario est dans le support ; réponse B — fenêtre d'urgence organisée sous quelques jours).
- **Visuel suggéré** : Trois cadrans de vitesse (rapide, planifié, à l'arrêt) avec une jauge sur chacun.
  - **alt-text** : Trois compteurs de vitesse représentant les différents rythmes d'application des correctifs de sécurité.
- **Élément interactif** : 📊 Sondage Livestorm n°5 (opinion) puis 🤔 mini-scénario en chat (A/B/C).

---

### Slide 13 — Sans malware : DDoS & injections SQL
- **Type** : schéma
- **Points clés (bullets)** :
  - **DDoS** : un botnet sature le serveur → atteinte à la **Disponibilité**.
  - Mirai (2016) : des caméras infectées, des attaques de l'ordre du térabit/s.
  - **Injection SQL** : des commandes glissées dans un formulaire mal programmé → **Confidentialité + Intégrité**.
  - Point commun : rien à installer chez la victime.
- **Notes orateur** : L'analogie DDoS : une manifestation qui bloque l'entrée du magasin — chaque manifestant est inoffensif, c'est la foule qui paralyse. Mirai a rendu Twitter et Netflix inaccessibles en frappant leur prestataire DNS commun. L'injection SQL est un défaut de programmation, référencé par l'OWASP — ni le réseau ni les mots de passe n'y changent rien. Relier chaque attaque à la triade de B01.
- **Visuel suggéré** : Diptyque : à gauche un serveur submergé par une foule d'ordinateurs et de caméras ; à droite un formulaire web laissant passer une commande vers une base de données.
  - **alt-text** : Schéma comparant une attaque DDoS par botnet saturant un serveur et une injection SQL traversant un formulaire web.

---

### Slide 14 — Quiz de validation
- **Type** : quiz (sondages)
- **Points clés (bullets)** :
  - 📊 **Sondage n°6** : ver vs virus — la différence fondamentale ?
  - 📊 **Sondage n°7** : que suffit-il pour faire échouer une attaque (Kill Chain) ?
  - 📊 **Sondage n°8** : une injection SQL exploite avant tout... ?
- **Notes orateur** : Lancer les trois sondages à la suite (~2 min chacun), débriefs scriptés dans le support : la propagation autonome est LE critère du ver ; briser un seul maillon suffit — le défenseur n'a pas besoin d'être parfait partout, l'attaquant si ; l'injection SQL est un défaut de programmation. Si le temps le permet, enchaîner sur le bonus n°9 (la macro Word piégée — pont vers B04).
- **Visuel suggéré** : Trois cartes de quiz numérotées 6, 7, 8 avec l'icône de sondage Livestorm.
  - **alt-text** : Trois cartes de questions de quiz numérotées, associées à des sondages en direct.
- **Élément interactif** : 📊 Sondages Livestorm n°6 à 8 (+ n°9 en tampon).

---

### Slide 15 — Synthèse & prochaine session
- **Type** : récap
- **Points clés (bullets)** :
  - Le zoo des malwares : propagation + charge utile.
  - La Kill Chain : 7 étapes, **un seul maillon à briser**.
  - WannaCry & NotPetya : deux mois d'inertie, 10 milliards de dégâts.
  - Self-paced : IBM SkillsBuild *« Introduction to Cybersecurity Tools & Cyber Attacks »* + vidéo Stuxnet.
  - Prochaine session — B04 : Ingénierie sociale & facteur humain.
- **Notes orateur** : Faire écrire dans le chat UN mot retenu, en lire 4-5. Devoirs : le module SkillsBuild et la vidéo Stuxnet (replacer mentalement ses étapes dans la Kill Chain). Teaser B04 : « l'arme la plus efficace n'est pas un logiciel — une entreprise de cinéma française a perdu 19 millions d'euros sans qu'un seul malware ne soit utilisé. Réponse la semaine prochaine. » Terminer à l'heure exacte.
- **Visuel suggéré** : Récapitulatif en quatre vignettes (malwares, Kill Chain, cas 2017, mises à jour) et un panneau « B04 » fléché.
  - **alt-text** : Synthèse en quatre vignettes des thèmes de la session avec un panneau indiquant la prochaine session B04.
- **Élément interactif** : Chat de clôture — « un mot que vous retenez ».
