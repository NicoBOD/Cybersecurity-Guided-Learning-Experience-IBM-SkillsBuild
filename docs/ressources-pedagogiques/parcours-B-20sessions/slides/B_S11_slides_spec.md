# Spécifications des slides — Session B11 : Sécurité du cloud
Parcours : B 20 sessions  |  Module : C — Identités, cloud & données  |  Format : Spécifications Markdown

> **Principe** : le texte affiché reste minimal (mots-clés, chiffres, schémas) ; le contenu riche est dans les notes orateur et le [plan de séance minuté](../plans-de-seance/B_S11_plan.md). Toutes les interactions passent par les sondages et le chat Livestorm.

---

### Slide 1 — Page de garde
- **Type** : titre
- **Points clés (bullets)** :
  - Sécurité du cloud
  - Vos données chez quelqu'un d'autre : qui ferme les portes ?
  - Parcours B — Session B11
- **Notes orateur** : Accueillir. Retour self-paced : « tapez dans le chat un exemple de service IaaS, PaaS ou SaaS » — corriger en direct (EC2/Heroku/M365). Rappel B10 : chiffrer, hacher, certifier — le cloud met tous ces outils à l'épreuve. Annonce : la frontière de responsabilité, les erreurs à millions, et l'affaire des 106 millions de dossiers.
- **Visuel suggéré** : Nuage stylisé posé sur des piliers de datacenter, avec une porte au premier plan dont la clé est tendue vers le spectateur.
  - **alt-text** : Nuage informatique dont la porte d'entrée est confiée au client, symbolisant la responsabilité partagée.
- **Élément interactif** : 💬 Chat d'accueil — exemples IaaS/PaaS/SaaS.

---

### Slide 2 — Objectifs & agenda
- **Type** : contenu
- **Points clés (bullets)** :
  - Attribuer les responsabilités de sécurité (client vs fournisseur) en IaaS, PaaS, SaaS.
  - Identifier les erreurs de configuration majeures (buckets, secrets, Root sans MFA).
  - Gouverner les accès cloud : Root isolé, IAM nominatif, moindre privilège.
  - Agenda : responsabilité partagée → mauvaises configs → gouvernance → matrice → Capital One & Verizon → quiz.
- **Notes orateur** : Le fil rouge : le cloud ne vous décharge pas de la sécurité, il en redistribue les rôles. La soirée sert à savoir exactement lesquels — et deux affaires montreront le prix de la confusion.
- **Visuel suggéré** : Deux colonnes présentant les objectifs et l'agenda de la séance.
  - **alt-text** : Tableau présentant les objectifs d'apprentissage et les étapes de la session.

---

### Slide 3 — Brise-glace : la faute à qui ?
- **Type** : sondage
- **Points clés (bullets)** :
  - 📊 **Sondage n°1** : selon Gartner, quelle part des incidents de sécurité cloud est imputable au CLIENT ?
  - A) ~50 % — B) ~99 % — C) ~10 %
- **Notes orateur** : Lancer le sondage n°1 (60-90 s). Réponse B : la quasi-totalité, selon la prédiction devenue référence de Gartner. Les datacenters des fournisseurs sont des forteresses ; ce qui fuit, ce sont les configurations du client — bucket public, clé dans le code, compte sans MFA.
- **Visuel suggéré** : Balance dont un plateau porte un datacenter blindé et l'autre une simple case à cocher « Public » qui fait tout basculer.
  - **alt-text** : Balance illustrant qu'une simple case de configuration pèse plus lourd que la sécurité physique du datacenter.
- **Élément interactif** : 📊 Sondage Livestorm n°1 (brise-glace).

---

### Slide 4 — La responsabilité partagée : la colocation
- **Type** : schéma
- **Points clés (bullets)** :
  - Sécurité **DU** cloud (fournisseur) : bâtiments, serveurs, hyperviseur.
  - Sécurité **DANS** le cloud (client) : données, identités, configurations.
  - Le propriétaire répond des murs — le locataire ferme sa porte à clé.
- **Notes orateur** : Dérouler l'analogie de la colocation : toiture et tuyauterie au propriétaire, serrure et meubles au locataire. Relance chat : « si le locataire laisse sa porte ouverte et se fait cambrioler — la faute à qui ? » La formule à mémoriser : DU cloud vs DANS le cloud (question n°6 du quiz).
- **Visuel suggéré** : Immeuble en coupe : structure porteuse colorée aux couleurs du fournisseur, intérieurs d'appartements aux couleurs du client.
  - **alt-text** : Immeuble en coupe séparant la structure gérée par le fournisseur des appartements gérés par les locataires.
- **Élément interactif** : 💬 Chat — la colocation cambriolée.

---

### Slide 5 — IaaS, PaaS, SaaS : la frontière qui glisse
- **Type** : schéma
- **Points clés (bullets)** :
  - **IaaS** (EC2) : le client gère l'OS et tout au-dessus.
  - **PaaS** (Heroku) : le client répond de son code et de ses données.
  - **SaaS** (M365) : restent au client — données, identités, partages... et **sauvegarde**.
  - Deux lignes invariantes : les **données** et les **identités**, toujours au client.
- **Notes orateur** : Le critère : qui a la main sur la couche ? En IaaS, patcher l'OS est au client — WannaCry (B03) s'applique au cloud aussi. Point ignoré du SaaS : supprimer ≠ sauvegarder — le fournisseur ne restaure pas vos suppressions au-delà de ses corbeilles ; la plupart des fuites SaaS viennent de partages trop larges.
- **Visuel suggéré** : Trois colonnes empilant les couches (matériel → OS → application → données), la frontière client/fournisseur glissant de l'une à l'autre.
  - **alt-text** : Trois piles de couches techniques montrant la frontière de responsabilité selon le modèle IaaS, PaaS ou SaaS.

---

### Slide 6 — Les trois portes laissées ouvertes
- **Type** : contenu
- **Points clés (bullets)** :
  - **Le bucket public** : une case cochée → exposition mondiale, instantanée, silencieuse.
  - **Le secret codé en dur** : une clé sur GitHub = exploitée en **minutes**.
  - **Le Root sans MFA** : l'entreprise entière détruite ou rançonnée — sauvegardes comprises.
- **Notes orateur** : Détailler chaque porte : les robots qui scannent GitHub en continu (minage sur votre facture, pivot vers les données — rappel du script d'Uber en B09) ; le Root compromis qui peut tout supprimer en minutes. Question rhétorique : le point commun ? Aucune faille du fournisseur — des choix ou des oublis du client. Gartner, en pratique.
- **Visuel suggéré** : Trois portes entrouvertes étiquetées « stockage », « code », « Root », avec des silhouettes de robots scanneurs en approche.
  - **alt-text** : Trois portes entrouvertes symbolisant les erreurs de configuration cloud les plus courantes.

---

### Slide 7 — La gouvernance des accès cloud
- **Type** : contenu
- **Points clés (bullets)** :
  - **Root au coffre** : jamais au quotidien, MFA matériel.
  - **Comptes IAM nominatifs** + MFA obligatoire (B09 transposé).
  - **Moindre privilège — machines comprises** : un composant ne voit que son besoin.
  - **Surveillance continue (CSPM)** : détecter la dérive avant les scanners.
- **Notes orateur** : Le Root est au cloud ce que l'admin local est au poste (B08). Le moindre privilège des identités TECHNIQUES est le point neuf : un pare-feu applicatif n'a rien à faire dans le stockage — l'affaire qui suit le démontre à 106 millions de dossiers. Question rhétorique : qui serait alerté chez vous si un bucket passait en public un dimanche soir ? Si « personne » : chantier n°1.
- **Visuel suggéré** : Coffre-fort contenant une clé « Root », entouré de badges nominatifs et d'un radar de surveillance.
  - **alt-text** : Coffre-fort isolant le compte racine, entouré de comptes nominatifs et d'un radar de surveillance des configurations.

---

### Slide 8 — Activité : la matrice de responsabilité
- **Type** : activité (sondages)
- **Points clés (bullets)** :
  - 6 tâches × 3 modèles — qui est responsable : Client ou Fournisseur ?
  - 📊 **Sondage n°2** : les correctifs de l'OS invité ? · 📊 **n°3** : la protection des données ? · 📊 **n°4** : le WAF ?
  - La matrice se complète à l'écran au fil des votes.
- **Notes orateur** : Lancer les trois sondages avec débrief : n°2 — qui a la main sur la couche la patche (IaaS : client) ; n°3 — LA ligne de la session : la donnée appartient TOUJOURS au client ; n°4 — client en IaaS/PaaS, fournisseur en SaaS... « et un WAF mal configuré côté client, c'est l'histoire qui arrive ». Compléter les 3 lignes restantes : physique (F×3), correctifs applicatifs (C/C/F), identités & MFA (C×3 — l'autre invariante).
- **Visuel suggéré** : Matrice 6×3 vide projetée, remplie ligne par ligne avec un code couleur client/fournisseur.
  - **alt-text** : Matrice de responsabilité cloud à compléter progressivement pendant l'activité collective.
- **Élément interactif** : 📊 Sondages Livestorm n°2 à 4 — construction collective de la matrice.

---

### Slide 9 — Le paysage en chiffres
- **Type** : chiffres clés
- **Points clés (bullets)** :
  - **~99 %** des défaillances cloud imputables au client (Gartner).
  - **~106 M de dossiers** · 80 M$ d'amende · 190 M$ d'accord : Capital One (2019).
  - **~14 M de dossiers** exposés par un bucket public : Verizon (2017, UpGuard).
- **Notes orateur** : Trois lectures : le maillon faible est la configuration du client, pas la technologie du fournisseur ; une erreur s'expose au monde entier instantanément ; et le régulateur poursuit le client, pas AWS — la responsabilité juridique suit la responsabilité de configuration. Transition : les deux histoires.
- **Visuel suggéré** : Trois grands chiffres en typographie XXL avec leurs sources et années en petit.
  - **alt-text** : Trois statistiques géantes sur les incidents de sécurité cloud avec leurs sources.

---

### Slide 10 — Affaire n°1 : Capital One (2019)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - Un pare-feu applicatif **mal configuré** (technique SSRF).
  - Le service de métadonnées remet des identifiants temporaires...
  - ... porteurs de **droits excessifs** sur des centaines d'espaces de stockage.
  - **~106 millions de dossiers** téléchargés — 80 M$ + 190 M$.
- **Notes orateur** : Dérouler la chaîne, côté client de bout en bout : WAF détourné pour interroger l'intérieur → identifiants temporaires → droits sans rapport avec la fonction → exfiltration massive. L'attaquante (une ancienne ingénieure du fournisseur) s'en vante en ligne et se fait arrêter. Leçons : le fournisseur n'a pas été piraté ; le moindre privilège s'applique aux MACHINES (l'Admin_IT de B09 qui ne lit pas les factures) ; la surveillance du stockage aurait vu l'exfiltration.
- **Visuel suggéré** : Chaîne de trois maillons étiquetés « WAF mal configuré », « métadonnées », « droits excessifs » menant à une base de données ouverte.
  - **alt-text** : Chaîne d'exploitation de l'affaire Capital One reliant la mauvaise configuration aux données exposées.

---

### Slide 11 — Affaire n°2 : Verizon (2017)
- **Type** : étude de cas
- **Points clés (bullets)** :
  - **~14 millions de dossiers clients** librement accessibles sur Internet.
  - Un bucket configuré en **public**... par un **prestataire**.
  - Découvert par un chercheur (UpGuard) — avant les attaquants, cette fois.
- **Notes orateur** : Aucun piratage : une case cochée au mauvais endroit. Les robots parcourent en permanence l'espace des services de stockage à la recherche de cet oubli exact. Leçons : la fuite cloud archétypale ; la sous-traitance transporte la responsabilité (le prestataire configure, le donneur d'ordre assume — Target, encore) ; la détection ne doit rien au hasard : CSPM. Relance chat : « quel détail vous marque le plus ? »
- **Visuel suggéré** : Entrepôt de dossiers dont la porte est grande ouverte sur une rue passante, un chercheur avec une loupe sur le seuil.
  - **alt-text** : Entrepôt de données ouvert sur la rue symbolisant le bucket de stockage public découvert par un chercheur.
- **Élément interactif** : 💬 Chat — réactions aux deux affaires.

---

### Slide 12 — Et chez vous ? La frontière
- **Type** : sondage (opinion)
- **Points clés (bullets)** :
  - 📊 **Sondage n°5** : la frontière de responsabilité cloud est-elle claire chez vous ?
  - A) Claire et surveillée — B) Floue (« c'est le fournisseur qui gère ») — C) Je ne sais pas / pas de cloud.
- **Notes orateur** : B est la réponse la plus répandue — et la plus dangereuse : vrai pour les murs, faux pour les portes. La question de lundi matin : qui vérifie les partages, le MFA, les configurations de stockage ? Si « personne » : premier chantier identifié. Enchaîner sur le mini-scénario de la clé d'API sur GitHub : « tapez A, B ou C » (réponse B — révoquer d'abord : la clé est déjà volée ; l'historique Git n'oublie rien).
- **Visuel suggéré** : Ligne de démarcation au sol entre deux zones, nette d'un côté, effacée de l'autre.
  - **alt-text** : Ligne de démarcation à moitié effacée symbolisant une frontière de responsabilité floue.
- **Élément interactif** : 📊 Sondage Livestorm n°5 (opinion) puis 🤔 mini-scénario en chat (A/B/C).

---

### Slide 13 — Quiz de validation
- **Type** : quiz (sondages)
- **Points clés (bullets)** :
  - 📊 **Sondage n°6** : que recouvre la « sécurité DU cloud » ?
  - 📊 **Sondage n°7** : la bonne pratique du compte Root ?
  - 📊 **Sondage n°8** : pourquoi les attaquants scannent-ils GitHub ?
- **Notes orateur** : Lancer les trois sondages à la suite (~2 min chacun), débriefs scriptés dans le support : DU cloud = physique + hyperviseur (fournisseur) ; le Root au coffre, MFA matériel, jamais au quotidien ; GitHub scanné pour les secrets codés en dur — une clé publiée = une clé volée. Si le temps le permet, enchaîner sur le bonus n°9 (le bucket de paie public).
- **Visuel suggéré** : Trois cartes de quiz numérotées 6, 7, 8 avec l'icône de sondage Livestorm.
  - **alt-text** : Trois cartes de questions de quiz numérotées, associées à des sondages en direct.
- **Élément interactif** : 📊 Sondages Livestorm n°6 à 8 (+ n°9 en tampon).

---

### Slide 14 — Synthèse & prochaine session
- **Type** : récap
- **Points clés (bullets)** :
  - Le cloud loue les murs — **vous fermez les portes**.
  - Invariants : données et identités, toujours au client.
  - Root au coffre · IAM nominatif · zéro secret en dur · CSPM.
  - Self-paced : SkillsBuild *« Cloud Security Fundamentals »* + typologie des données sensibles (préparation Atelier 2).
  - Prochaine session — B12 : Sécurité & confidentialité des données + **Atelier de Synthèse 2**.
- **Notes orateur** : Faire écrire dans le chat UN mot retenu, en lire 4-5. Insister sur la préparation de B12 : identifier les types de données sensibles (RH, R&D, clients, finances). Teaser B12 : « vos données elles-mêmes — les classer, les chiffrer, les sauvegarder. Avec l'Atelier de Synthèse 2, et l'histoire d'un datacenter parti en fumée... avec les sauvegardes rangées dans le même bâtiment. » Terminer à l'heure exacte.
- **Visuel suggéré** : Récapitulatif en quatre vignettes (colocation, matrice, coffre Root, radar CSPM) et un panneau « B12 — Atelier » fléché.
  - **alt-text** : Synthèse en quatre vignettes des thèmes cloud avec un panneau annonçant la session B12 et son atelier.
- **Élément interactif** : Chat de clôture — « un mot que vous retenez ».
