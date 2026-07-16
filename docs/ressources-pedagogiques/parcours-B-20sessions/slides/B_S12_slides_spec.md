# Spécifications des slides — Session B12 : Sécurité & confidentialité des données (+ Atelier de Synthèse 2)
Parcours : B 20 sessions  |  Module : C — Identités, cloud & données  |  Format : Spécifications Markdown

> **Principe** : le texte affiché reste minimal (mots-clés, chiffres, schémas) ; le contenu riche est dans les notes orateur et le [plan de séance minuté](../plans-de-seance/B_S12_plan.md). Toutes les interactions passent par les sondages et le chat Livestorm.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Sécurité & confidentialité des données
  - La donnée, de sa création à sa destruction
  - Parcours B — Session B12 · **Atelier de Synthèse 2** inclus
- **Notes orateur** : Accueillir : dernière session du module C, ET deuxième Atelier de Synthèse. Retour self-paced : « citez dans le chat un type de donnée sensible d'entreprise » (attendu : paie, clients, R&D, santé) — « gardez cette liste : c'est la matière première de l'atelier. » Rappel B11 : la responsabilité partagée, la donnée toujours au client.
- **Visuel suggéré** : Frise du cycle de vie d'une donnée : création → étiquette → coffre → surveillance → sauvegarde → destructeur de documents.
  - **alt-text** : Frise illustrant le cycle de vie complet d'une donnée, de sa création à sa destruction sécurisée.
- **Élément interactif** : 💬 Chat d'accueil — les types de données sensibles.

---

### Slide 2 — Objectifs & agenda
- **Type** : contenu
- **Points clés (bullets)** :
  - Classifier les données sur 4 niveaux de sensibilité.
  - Chiffrer au repos et en transit · surveiller en usage (DLP).
  - Sauvegarder en 3-2-1 : hors site, hors ligne/immuable, testé.
  - **Atelier de Synthèse 2** : le plan de protection des données de MedDistri.
  - Agenda : classification → chiffrement & DLP → 3-2-1 → OVHcloud & Morgan Stanley → ATELIER → quiz.
- **Notes orateur** : Le fil rouge : la donnée se protège à chaque état de sa vie — et la plupart des catastrophes viennent d'une seule étape négligée. Deux affaires le prouveront, puis l'atelier assemblera tout le module C sur une page.
- **Visuel suggéré** : Deux colonnes présentant les objectifs et l'agenda, avec l'atelier mis en évidence.
  - **alt-text** : Tableau des objectifs et de l'agenda de la session avec l'atelier de synthèse surligné.

---

### Slide 3 — Brise-glace : la nuit de Strasbourg
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **Sondage n°1** : mars 2021, un datacenter brûle — combien de sites hors ligne ?
  - A) ~3 000 — B) ~360 000 — C) ~3,6 millions
- **Notes orateur** : Lancer le sondage n°1 (60-90 s). Réponse C : l'incendie du datacenter SBG2 d'OVHcloud à Strasbourg. Le vrai drame : des clients avaient leurs sauvegardes dans le même bâtiment — perte définitive. Ce soir : protéger la donnée à chaque étape, et la règle qui aurait tout sauvé.
- **Visuel suggéré** : Silhouette de datacenter nocturne avec une lueur d'incendie et des pictogrammes de sites web s'éteignant en cascade.
  - **alt-text** : Datacenter en feu la nuit avec des sites web s'éteignant en chaîne, illustrant l'incendie de Strasbourg.
- **Élément interactif** : 📊 Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — La classification : 4 niveaux
- **Type** : schéma
- **Points clés (bullets)** :
  - **Publique** : les livres en vitrine.
  - **Interne** : le planning dans le couloir.
  - **Confidentielle** : les contrats des auteurs.
  - **Secrète** : le manuscrit du prochain best-seller.
- **Notes orateur** : Dérouler l'analogie de la maison d'édition. Le principe : l'effort suit la valeur — on ne protège pas une brochure comme un brevet. Relance chat : « la liste des salaires de MedDistri : quel niveau ? Et le menu de la cantine ? » Le rôle pivot : la classification décide de TOUT le reste (droits, partages, chiffrement, DLP, sauvegardes).
- **Visuel suggéré** : Pyramide à quatre étages colorés du vert (publique) au rouge (secrète) avec les exemples de la maison d'édition.
  - **alt-text** : Pyramide des quatre niveaux de classification des données illustrée par l'analogie d'une maison d'édition.
- **Élément interactif** : 💬 Chat — classement express de documents.

---

### Slide 5 — Chiffrer : en transit ET au repos
- **Type** : schéma
- **Points clés (bullets)** :
  - **En transit** : TLS, SSH, VPN — protéger le trajet (B07).
  - **Au repos** : BitLocker, LUKS — protéger le support volé ou éteint (B08, B10).
  - ⚠️ Machine allumée, session ouverte = données **en clair** pour un malware actif.
- **Notes orateur** : Le piège conceptuel à désamorcer : « c'est chiffré donc c'est protégé » — faux sur une machine en fonctionnement : le déchiffrement est à la volée. Chaque état a son outil ; les deux chiffrements se complètent, ne se remplacent pas (question n°6 du quiz : HTTPS ne protège pas le stockage).
- **Visuel suggéré** : Camion blindé (transit) livrant un coffre-fort (repos), avec une fenêtre ouverte sur le coffre quand la maison est « allumée ».
  - **alt-text** : Camion blindé et coffre-fort illustrant les chiffrements en transit et au repos, avec leur limite en usage.

---

### Slide 6 — Le DLP : le gardien de sortie
- **Type** : contenu
- **Points clés (bullets)** :
  - Inspecte les flux sortants : e-mails, clés USB, uploads.
  - Bloque les contenus classifiés (mots-clés, expressions régulières, empreintes) **et alerte**.
  - Prérequis absolu : la **classification** — sans elle, tout ou rien.
- **Notes orateur** : L'exemple canonique : la liste de numéros de cartes bancaires en pièce jointe → envoi bloqué, équipe sécurité alertée. Le DLP couvre l'état « en usage » de la donnée — celui que le chiffrement au repos ne couvre pas. La classification décide, le DLP applique.
- **Visuel suggéré** : Portique de sécurité à la sortie d'un bâtiment scannant des enveloppes, certaines bloquées en rouge.
  - **alt-text** : Portique de contrôle filtrant les documents sortants de l'entreprise, symbolisant la prévention des fuites.

---

### Slide 7 — La sauvegarde 3-2-1
- **Type** : schéma
- **Points clés (bullets)** :
  - **3** copies · **2** supports différents · **1** hors site.
  - La copie hors site : **hors ligne ou immuable** (9 attaques sur 10 ciblent les sauvegardes — Veeam).
  - Et la restauration se **teste** : RPO (combien perdre ?) · RTO (redémarrer en combien de temps ?).
- **Notes orateur** : Dérouler l'exemple ArchiTech : production RAID + NAS local nocturne + cloud immuable ou coffre externe — survit à la panne, au rançongiciel ET à l'incendie. Question rhétorique : Maersk (B03) a survécu grâce à quoi ? Un serveur fortuitement hors ligne au Ghana — la chance n'est pas une stratégie, la copie hors ligne si.
- **Visuel suggéré** : Trois coffres numérotés : un dans le bureau, un dans la pièce technique, un dans un bâtiment distant débranché du réseau.
  - **alt-text** : Trois copies de sauvegarde réparties sur deux supports et un site distant hors ligne, illustrant la règle 3-2-1.

---

### Slide 8 — Le paysage en chiffres
- **Type** : chiffres clés
- **Points clés (bullets)** :
  - **~3,6 millions de sites** hors ligne : l'incendie OVHcloud (2021).
  - **95 M$ d'amendes cumulées** : Morgan Stanley et les disques revendus (2020-2022).
  - **> 9 attaques sur 10** : les rançongiciels ciblent aussi les sauvegardes (Veeam).
- **Notes orateur** : Trois lectures : le sinistre physique existe encore à l'ère du cloud ; la donnée reste dangereuse jusqu'à sa destruction certifiée ; la sauvegarde connectée n'est plus une protection. Transition : les deux histoires.
- **Visuel suggéré** : Trois grands chiffres en typographie XXL avec leurs sources et années en petit.
  - **alt-text** : Trois statistiques géantes sur les pertes de données avec leurs sources.

---

### Slide 9 — Affaire n°1 : OVHcloud (2021)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Nuit du 9 au 10 mars 2021 : le datacenter SBG2 ravagé.
  - ~3,6 millions de sites hors ligne.
  - « Activez votre plan de reprise d'activité » — beaucoup n'en avaient pas.
  - Sauvegardes **co-localisées** = pertes **définitives**.
- **Notes orateur** : Raconter : le leader européen de l'hébergement, le message du fondateur resté célèbre, et les clients qui ont perdu des années de travail — leurs sauvegardes partageaient le bâtiment, parfois la salle. Leçons : le cloud n'abolit pas le risque physique ; la sauvegarde reste au client (B11) ; « hors site » = séparation géographique RÉELLE.
- **Visuel suggéré** : Plan d'un datacenter où production et sauvegardes sont dans la même salle, entourées par les flammes.
  - **alt-text** : Plan de datacenter montrant les serveurs et leurs sauvegardes dans la même salle menacée par l'incendie.

---

### Slide 10 — Affaire n°2 : Morgan Stanley
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Des serveurs décommissionnés... revendus **sans effacement fiable**.
  - Des disques pleins de données clients aux enchères — certains jamais récupérés.
  - **60 M$ + 35 M$** d'amendes (2020, 2022).
- **Notes orateur** : Raconter : l'opération de « ménage » confiée à un prestataire, les disques non chiffrés dans la nature. Leçons : le cycle de vie va jusqu'à la destruction — supprimer n'efface que l'index, formater ne suffit pas ; le chiffrement au repos systématique aurait transformé chaque disque en brique illisible ; la sous-traitance transporte la responsabilité. Relance chat : « quel détail vous marque le plus ? » Enchaîner sur le mini-scénario des disques de MedDistri : « tapez A, B ou C » (réponse B — effacement certifié / destruction physique + chiffrement en amont).
- **Visuel suggéré** : Étal de vente aux enchères présentant des disques durs étiquetés « données clients » avec un marteau de commissaire-priseur.
  - **alt-text** : Disques durs contenant des données vendus aux enchères, illustrant la fin de vie négligée du matériel.
- **Élément interactif** : 💬 Chat — réactions, puis 🤔 mini-scénario en chat (A/B/C).

---

### Slide 11 — Atelier de Synthèse 2 : MedDistri passe au cloud
- **Type** : atelier (présentation)
- **Points clés (bullets)** :
  - 15 commerciaux nomades · suite bureautique SaaS · mots de passe dans les navigateurs · fiches de paie sur l'espace partagé.
  - 💬 « Qu'est-ce qui vous inquiète le PLUS ? »
- **Notes orateur** : Afficher les contraintes (cf. B_miniprojets). Laisser le chat réagir (attendu : mots de passe navigateur, paie accessible à tous, pas de MFA) : « tout y est — corrigeons, décision par décision. » Trois votes puis les règles d'or collectives.
- **Visuel suggéré** : Bureau de PME stylisé avec des post-it de mots de passe, un nuage SaaS et des valises de commerciaux.
  - **alt-text** : Situation initiale de la PME MedDistri après sa migration cloud, avec ses mauvaises pratiques visibles.
- **Élément interactif** : 💬 Chat — l'audit spontané de la situation.

---

### Slide 12 — Atelier : les trois décisions
- **Type** : atelier (sondages)
- **Points clés (bullets)** :
  - 📊 **Sondage n°2** : la MFA des 15 commerciaux ?
  - 📊 **Sondage n°3** : classer les fiches de paie sur le cloud ?
  - 📊 **Sondage n°4** : où placer la 3ᵉ copie (règle 3-2-1) ?
- **Notes orateur** : Un sondage par décision (~4 min), débriefs scriptés dans le support : n°2 — le SMS est la MFA la plus fragile (SIM swapping, B09) : application en standard, FIDO2 en idéal ; n°3 — paie = personnel + bancaire = Confidentielles : accès restreint, chiffrement, traçabilité ; n°4 — A est le scénario OVHcloud exact, C confond corbeille et sauvegarde : cloud immuable hors site.
- **Visuel suggéré** : Trois cartes de décision illustrées : smartphone MFA, dossier de paie étiqueté, coffre distant.
  - **alt-text** : Trois cartes représentant les décisions de protection des données à voter pour MedDistri.
- **Élément interactif** : 📊 Sondages Livestorm n°2 à 4 — les décisions de protection.

---

### Slide 13 — Atelier : les 5 règles d'or de MedDistri
- **Type** : atelier (co-construction)
- **Points clés (bullets)** :
  - 💬 « Proposez une règle en une phrase ! »
  - Cible : MFA partout · gestionnaire de mots de passe · classification & partages restreints · chiffrement au repos · 3-2-1 immuable testé.
- **Notes orateur** : Rédiger en direct au tableau blanc à partir du chat, compléter ce qui manque. Synthèse de l'atelier : « ce plan tient sur une page — et il couvre tout le module : B09 les identités, B10 le chiffrement, B11 le cloud, B12 les données. Une page, quatre sessions, une PME transformée. »
- **Visuel suggéré** : Tableau blanc affichant une charte à cinq lignes en cours de rédaction.
  - **alt-text** : Charte des cinq règles d'or de protection des données rédigée collectivement au tableau blanc.
- **Élément interactif** : 💬 Chat — co-rédaction des règles d'or.

---

### Slide 14 — Et vous ? Vos sauvegardes personnelles
- **Type** : sondage (opinion)
- **Points clés (bullets)** :
  - 📊 **Sondage n°5** : vos données personnelles importantes — où en êtes-vous ?
  - A) 3-2-1 ou presque — B) Une copie, pas très à jour — C) Tout au même endroit.
- **Notes orateur** : Sondage d'opinion, sans jugement — C est fréquent, la prise de conscience arrive souvent après la perte. Le kit minimal : un disque externe branché uniquement le temps de la sauvegarde + une copie cloud chiffrée. Dix ans de photos valent deux heures de configuration — l'action personnelle de la semaine.
- **Visuel suggéré** : Trois foyers stylisés : l'un avec coffre et cloud, l'un avec un disque poussiéreux, l'un croisant les doigts.
  - **alt-text** : Trois foyers illustrant les niveaux de maturité des sauvegardes personnelles.
- **Élément interactif** : 📊 Sondage Livestorm n°5 (opinion).

---

### Slide 15 — Quiz de validation
- **Type** : quiz (sondages)
- **Points clés (bullets)** :
  - 📊 **Sondage n°6** : HTTPS puis disque non chiffré — que manque-t-il ?
  - 📊 **Sondage n°7** : que fait un DLP face à l'envoi de cartes bancaires ?
  - 📊 **Sondage n°8** : pourquoi la copie hors site doit-elle être hors ligne/immuable ?
- **Notes orateur** : Lancer les trois sondages à la suite (~2 min chacun), débriefs scriptés dans le support : chaque état a son outil (TLS = le trajet) ; le DLP bloque ET alerte — aveugle sans classification ; les rançongiciels chassent les sauvegardes connectées (Veeam). Si le temps le permet, enchaîner sur le bonus n°9 (l'incendie fatal).
- **Visuel suggéré** : Trois cartes de quiz numérotées 6, 7, 8 avec l'icône de sondage Livestorm.
  - **alt-text** : Trois cartes de questions de quiz numérotées, associées à des sondages en direct.
- **Élément interactif** : 📊 Sondages Livestorm n°6 à 8 (+ n°9 en tampon).

---

### Slide 16 — Synthèse & fin du module Identités, cloud & données
- **Type** : récap
- **Points clés (bullets)** :
  - La donnée, protégée à chaque état : classée · chiffrée · surveillée · sauvegardée · détruite proprement.
  - Module C terminé : identités (B09), cryptographie (B10), cloud (B11), données (B12).
  - Self-paced : SkillsBuild *« Data Security and Privacy »* + sauvegarde personnelle + définitions PCA/PRA.
  - Prochaine session — B13 : le module Gouvernance, risques & conformité.
- **Notes orateur** : Faire écrire dans le chat UN mot retenu, en lire 4-5. Féliciter pour le module et l'atelier. Teaser B13 : « on monte à l'étage stratégie : qui décide, qui est responsable, selon quels référentiels — NIST, ISO 27001, ANSSI... et pourquoi la sécurité sans pilotage finit toujours par échouer. » Terminer à l'heure exacte.
- **Visuel suggéré** : Frise des quatre sessions du module C cochées, la charte MedDistri en vignette, flèche vers un panneau « Module D — Gouvernance ».
  - **alt-text** : Frise de progression du module données validé avec la charte de l'atelier et l'ouverture du module gouvernance.
- **Élément interactif** : Chat de clôture — « un mot que vous retenez ».
