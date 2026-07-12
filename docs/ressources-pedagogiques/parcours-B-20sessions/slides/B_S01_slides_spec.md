# Spécifications des slides — Session B01 : Introduction à la cybersécurité & triade CIA
Parcours : B 20 sessions  |  Module : A — Fondations  |  Format : Spécifications Markdown  |  Modalité : Webinaire Livestorm

> **Principe directeur** : le texte affiché reste minimal ; le contenu riche est dans les notes orateur et dans le [plan d'animation minuté](../plans-de-seance/B_S01_plan.md), qui fait référence pour les verbatims et débriefs. Les numéros de sondages renvoient à la checklist Livestorm du plan.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Introduction à la cybersécurité
  - Le socle fondamental : la Triade CIA
  - Parcours B — Session B01
- **Notes orateur** : Bienvenue dans la première des vingt sessions du parcours. Tout se passe par le chat et les sondages — test immédiat : « écrivez la ville d'où vous nous suivez ». Présenter le cadre : 6 modules, 4 ateliers de synthèse, un grand atelier final (MedDistri).
- **Visuel suggéré** : Un fond sobre gris anthracite et blanc avec une touche de vert. Une illustration abstraite représentant des réseaux connectés de manière sécurisée.
  - **alt-text** : Graphisme abstrait montrant des lignes de connexion lumineuses vertes sur un fond sombre de circuit imprimé.
- **Élément interactif** : Test du chat (ville d'origine), lecture de 3-4 réponses.

---

### Slide 2 — Objectifs de la séance & Sommaire
- **Type** : contenu
- **Points clés (bullets)** :
  - Définir les trois piliers de la Triade CIA (CID).
  - Évaluer l'impact financier, juridique et réputationnel d'une cyberattaque.
  - Différencier les postures Red Team / Blue Team / RSSI.
  - Sommaire : Brise-glace (11 min) · Triade CIA (14 min) · Activité Qualification d'incidents (14 min) · Impacts business (10 min) · Chiffres & cas réels (10 min) · Métiers (10 min) · Quiz & synthèse (16 min).
- **Notes orateur** : Annoncer le rythme interactif : un sondage ou une question chat toutes les 8 minutes environ. Promesse : « en sortant, vous saurez qualifier n'importe quel incident avec trois lettres. »
- **Visuel suggéré** : Deux colonnes — cible pour les objectifs, liste ordonnée pour le sommaire.
  - **alt-text** : Icône de cible verte à gauche et une liste de sept points à droite sur fond clair.

---

### Slide 3 — Brise-glace : le facteur humain
- **Type** : sondage
- **Points clés (bullets)** :
  - **📊 Sondage n°1** : Dans quelle proportion des violations de données le facteur humain est-il impliqué ?
  - A) ~10 % · B) ~30 % · C) ~60 % · D) ~90 %
  - (Réponse révélée après le vote)
- **Notes orateur** : Lancer le sondage n°1 (60-90 s). Débrief : réponse C, ~60 % (Verizon DBIR 2025). Message fondateur : la cybersécurité est d'abord une affaire de personnes — et les apprenants deviennent une ligne de défense (teaser métiers en fin de session).
- **Visuel suggéré** : Silhouettes humaines et cadenas ; après le vote, « ~60 % » en très grand.
  - **alt-text** : Groupe de silhouettes humaines dont une en surbrillance rouge, à côté d'un grand cadenas.
- **Élément interactif** : 📊 Sondage Livestorm n°1.

---

### Slide 4 — Le monde sans sécurité
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Votre smartphone cesse de fonctionner.
  - Les feux de signalisation de la ville sont piratés.
  - Vos données bancaires sont publiées en ligne.
  - **💬 Dans le chat : le PREMIER impact auquel vous pensez ?**
- **Notes orateur** : Brainstorming chat (3 min), lire 4-5 réponses. Synthèse : argent, vie privée, sécurité physique, confiance — « tout cela tient en trois lettres : C, I, D. »
- **Visuel suggéré** : Image contrastée : smartphone en alerte rouge et carrefour aux feux éteints.
  - **alt-text** : Écran de smartphone avec une alerte rouge devant une ville aux feux de circulation éteints.
- **Élément interactif** : Brainstorming dans le chat.

---

### Slide 5 — Le pilier de base : la Triade CIA / CID
- **Type** : schéma
- **Points clés (bullets)** :
  - **C**onfidentialité (*Confidentiality*) — qui peut lire ? *(la lettre scellée à la cire)*
  - **I**ntégrité (*Integrity*) — qui peut modifier ? *(le livre comptable à l'encre indélébile)*
  - **D**isponibilité (*Availability*) — accessible quand on en a besoin ? *(l'électricité domestique)*
  - **💬 Dans le chat : C, I ou D — laquelle serait la plus grave à perdre dans VOTRE métier ?**
- **Notes orateur** : Préciser l'acronyme : CIA vient de l'anglais, le « A » = *Availability* = Disponibilité (d'où CID en français). Dérouler les trois analogies et les trois exemples d'incidents du support. Question chat : lire 4-5 réponses — la criticité dépend du métier (hôpital → D, banque → I, avocat → C).
- **Visuel suggéré** : Triangle C-I-D avec icônes (cadenas, sceau, horloge) et les trois questions clés.
  - **alt-text** : Triangle aux sommets étiquetés Confidentialité, Intégrité, Disponibilité avec une icône par sommet.
- **Élément interactif** : Question chat C/I/D.

---

### Slide 6 — Activité : Qualification d'incidents
- **Type** : activité (3 sondages successifs)
- **Points clés (bullets)** :
  - **🕵️ Trois incidents, trois votes : quel pilier est touché EN PREMIER ?**
  - **Incident 1** (📊 Sondage n°2) : rançongiciel sur un hôpital — dossiers chiffrés, écrans de rançon.
  - **Incident 2** (📊 Sondage n°3) : un étudiant passe sa note de 08/20 à 18/20 dans la base de l'université.
  - **Incident 3** (📊 Sondage n°4) : un fichier clients laissé en accès libre, téléchargé et publié sur un forum.
- **Notes orateur** : ~4-5 min par incident (vote + débrief). Réponses : Disponibilité (introduire la double extorsion — teaser du cas réel à venir) ; Intégrité (l'attaque la plus discrète : rien de volé ni bloqué) ; Confidentialité (sans intrusion — une simple erreur de configuration). Donner la mesure préventive à chaque débrief (sauvegardes hors ligne ; droits d'écriture + journalisation ; moindre privilège + audits).
- **Visuel suggéré** : Trois cartes « dossier d'enquête » révélées une à une, avec pastille C/I/D à la révélation.
  - **alt-text** : Trois chemises cartonnées numérotées avec une loupe de détective posée dessus.
- **Élément interactif** : 📊 Sondages Livestorm n°2, 3, 4.

---

### Slide 7 — La règle du maillon le plus faible
- **Type** : concept
- **Points clés (bullets)** :
  - Une sécurité à 100 % n'existe pas.
  - L'attaquant ne force pas la porte blindée : il cherche la porte ouverte.
  - Mot de passe par défaut · logiciel non mis à jour · erreur humaine.
  - **La force d'un système = celle de son composant le plus faible.**
- **Notes orateur** : Reboucler avec le sondage n°1 : le maillon le plus faible est très souvent humain. Illustration : à quoi bon une porte blindée si la fenêtre est ouverte ? Ce principe justifie la « défense en profondeur » (château fort du support).
- **Visuel suggéré** : Chaîne dont un maillon, fissuré, est en surbrillance rouge.
  - **alt-text** : Chaîne métallique dont un maillon central fissuré brille en rouge.

---

### Slide 8 — Les impacts business d'une cyberattaque
- **Type** : contenu
- **Points clés (bullets)** :
  - 💶 **Financier direct** : perte d'exploitation, coûts de remédiation, rançon (déconseillée).
  - ⚖️ **Juridique** : amendes RGPD (jusqu'à 20 M€ / 4 % du CA mondial — session B15), litiges.
  - 🤝 **Réputationnel** : le plus dur à chiffrer, le plus destructeur à long terme.
- **Notes orateur** : Question rhétorique : « lequel des trois ruine une entreprise deux ans après l'attaque ? » — la réputation : l'argent se réemprunte, la confiance ne se rachète pas. Une cyberattaque est un risque d'entreprise, pas un problème du service informatique.
- **Visuel suggéré** : Trois colonnes avec pictogrammes (billets, balance, poignée de main brisée).
  - **alt-text** : Trois colonnes illustrées : des billets, une balance de justice et une poignée de main barrée.

---

### Slide 9 — La menace en chiffres
- **Type** : chiffres clés (stat cards)
- **Points clés (bullets)** :
  - **~60 %** des violations impliquent le facteur humain *(Verizon DBIR 2025)*
  - **~4 400** événements traités par l'ANSSI en 2024 (+15 %) — PME et collectivités en première ligne *(Panorama 2024)*
  - **~4,4 M$** : coût moyen mondial d'une violation ; plusieurs mois pour la confiner *(IBM 2025)*
  - **Record** de violations notifiées à la CNIL en 2024 (> 5 000)
- **Notes orateur** : Donner les ordres de grandeur, citer systématiquement source + année. Message : l'attaque est un flux industriel qui vise d'abord ceux qui se croient trop petits pour intéresser qui que ce soit.
- **Visuel suggéré** : Quatre cartes de statistiques, chiffres en très grand corps, sources en petit.
  - **alt-text** : Quatre cartes affichant de grands chiffres avec leurs sources en petits caractères.

---

### Slide 10 — Cas réel n°1 : l'hôpital de Corbeil-Essonnes (2022)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Nuit du 20 au 21 août 2022 — rançongiciel **LockBit**
  - Systèmes chiffrés → retour au **papier**, transferts de patients
  - Rançon : **10 M$** → **refus** (doctrine française)
  - Représailles : **~11 Go** de données publiées → *Disponibilité PUIS Confidentialité (double extorsion)*
- **Notes orateur** : Raconter chronologiquement — le récit marque plus que les chiffres. Relier au sondage n°2 : « votre diagnostic était le bon. » Les trois impacts business réunis : financier (des mois de reconstruction), juridique (données de santé), réputationnel (crise nationale). Enterrer l'idée reçue : « les pirates ne s'attaquent pas aux hôpitaux » — si : plus la cible est critique, plus elle est censée payer vite.
- **Visuel suggéré** : Frise chronologique de l'incident (intrusion → chiffrement → refus → fuite → reconstruction) avec icône hôpital.
  - **alt-text** : Frise chronologique en cinq étapes avec une icône d'hôpital et un cadenas rouge.

---

### Slide 11 — Cas réel n°2 : France Travail (2024)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Mars 2024 — comptes de **partenaires usurpés**
  - **43 millions** de personnes potentiellement concernées (identité, n° de sécurité sociale, coordonnées)
  - Ni mot de passe, ni RIB volés... **et pourtant** : hameçonnage crédible et usurpation d'identité pendant des années
  - *Pilier touché : Confidentialité — la violation « silencieuse »*
- **Notes orateur** : L'une des plus grandes fuites françaises. Expliquer l'effet différé : les données volées aujourd'hui alimentent les attaques de demain. Punchline-teaser : « comment ? Réponse complète en session B04, l'ingénierie sociale. »
- **Visuel suggéré** : Le chiffre « 43 000 000 » en très grand, une enveloppe hameçonnée, silhouette de la France.
  - **alt-text** : Grand chiffre 43 millions devant une carte de France stylisée et une enveloppe piégée.

---

### Slide 12 — Les métiers de la cybersécurité
- **Type** : contenu + sondage
- **Points clés (bullets)** :
  - 🔴 **Red Team** — attaquer (légalement, sous contrat) pour tester.
  - 🔵 **Blue Team** — défendre : SOC (B16), réponse aux incidents (B18).
  - 🎩 **RSSI / CISO** — stratégie, budgets, gouvernance (B13).
  - **4 à 5 millions** de professionnels manquants dans le monde *(études (ISC)², 2024)*
  - **📊 Sondage n°5 : quelle posture vous attire le plus ?**
- **Notes orateur** : Lancer le sondage n°5 (opinion). Débrief : aucune mauvaise réponse — le parcours couvre les trois postures ; les « je ne sais pas encore » ont 19 sessions pour se décider. Le déficit mondial de talents = une opportunité de carrière réelle.
- **Visuel suggéré** : Trois personnages stylisés (rouge, bleu, costume) autour d'un bouclier commun.
  - **alt-text** : Trois silhouettes professionnelles rouge, bleue et en costume entourant un bouclier.
- **Élément interactif** : 📊 Sondage Livestorm n°5.

---

### Slide 13 — Quiz de validation
- **Type** : quiz (3 sondages successifs)
- **Points clés (bullets)** :
  - **✅ Trois questions, trois votes**
  - **📊 Sondage n°6** : l'impact le plus destructeur à long terme ? *(remédiation / amende / réputation)*
  - **📊 Sondage n°7** : la règle du maillon le plus faible ?
  - **📊 Sondage n°8** : qui simule des attaques dans un cadre légal ?
- **Notes orateur** : Esprit : ancrage, pas évaluation. Réponses : réputationnel ; force = composant le plus faible ; Red Team. Si le temps le permet, enchaîner le 📊 Sondage n°9 (dilemme : ransomware sur hôpital → isoler le réseau, jamais payer, jamais restaurer sur un réseau actif — écho au cas CHSF).
- **Visuel suggéré** : Trois cartes de questions révélées successivement, coche verte à la révélation.
  - **alt-text** : Trois cartes de quiz avec une coche verte sur la carte retournée.
- **Élément interactif** : 📊 Sondages Livestorm n°6, 7, 8 (+ n°9 en tampon).

---

### Slide 14 — Clôture & Devoirs
- **Type** : clôture
- **Points clés (bullets)** :
  - **Votre boîte à outils B01** : 🧭 la triade C-I-D · 💥 3 familles d'impacts · 🗺️ la carte des métiers · 🇫🇷 2 cas réels
  - **💬 Dans le chat : UN mot que vous retenez**
  - **Self-paced avant B02** : IBM SkillsBuild *Cybersecurity Fundamentals - Part 1* (~1h30) + synthèse du Panorama ANSSI
  - **Prochaine séance** : *Paysage des menaces & acteurs (B02)*
- **Notes orateur** : Lire 4-5 mots du chat. Teaser B02 : « QUI nous attaque — et une histoire de braquage de banque à 81 millions de dollars, sans arme ni cagoule. » Terminer à l'heure exacte.
- **Visuel suggéré** : Récapitulatif en quatre vignettes + calendrier de la session B02.
  - **alt-text** : Quatre vignettes de synthèse et une icône de calendrier annonçant la prochaine session.
