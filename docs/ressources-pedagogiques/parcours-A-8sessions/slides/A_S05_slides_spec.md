# Spécifications des slides — Session 05 : Gouvernance, risque, conformité & vie privée
Parcours : A 8 sessions  |  Module : GRC & Vie Privée  |  Format : Spécifications Markdown  |  Modalité : Webinaire Livestorm

> **Principe directeur** : le texte affiché reste minimal ; le contenu riche est dans les notes du présentateur et dans le [plan d'animation minuté](../plans-de-seance/A_S05_plan.md), qui fait référence pour les verbatims et débriefs. Les numéros de sondages renvoient à la checklist Livestorm du plan.

---

## Slide 1 : Page de garde
* **Layout** : Titre (Emphase visuelle, fond sombre)
* **Texte affiché sur la slide** :
  * **Gouvernance, Risque, Conformité & Vie Privée**
  * Parcours A — Session 05
  * *Organiser la cybersécurité : des lois aux choix stratégiques d'entreprise*
  * Nom du Mentor / IBM SkillsBuild
* **Visuels suggérés** : Graphique symbolisant la justice ou l'organisation (colonnes grecques stylisées de manière moderne, engrenages de conformité imbriqués). Logo officiel dans un angle.
* **Notes du présentateur** :
  * Accueillir ; retour devoirs A4 : « tapez "fait", "en cours" ou "pas encore" pour le MFA + gestionnaire de mots de passe » — encourager sans juger.
  * Pivot : « jusqu'ici la technique ; aujourd'hui le comité de direction : qui décide, avec quel budget, et que dit la loi. »

---

## Slide 2 : Objectifs de la séance & Sommaire
* **Layout** : Deux colonnes (Gauche : Objectifs, Droite : Sommaire)
* **Texte affiché sur la slide** :
  * **Nos objectifs aujourd'hui** :
    * Comprendre la gouvernance cyber et le rôle de la PSSI.
    * Connaître les référentiels : ISO 27001 et NIST CSF 2.0 (6 fonctions).
    * Coter et traiter les risques (matrice 4×4, quatre stratégies).
    * Maîtriser les principes et obligations du RGPD.
  * **Sommaire de la séance** :
    * 1. Brise-glace : le prix du non-respect (6 min)
    * 2. Gouvernance : PSSI, ISO 27001, NIST CSF 2.0 (14 min)
    * 3. La gestion des risques (10 min)
    * 4. Activité : Le Comité des Risques (14 min)
    * 5. Démo : la matrice en direct (8 min)
    * 6. Le RGPD (14 min)
    * 7. Amendes réelles, quiz & synthèse (15 min)
* **Visuels suggérés** : Icônes cibles pour les objectifs et icône de liste pour le sommaire.
* **Notes du présentateur** :
  * Présenter la GRC comme le « pourquoi » qui justifie les dépenses de sécurité (et non plus seulement le « comment »).
  * Annoncer le rythme : un sondage ou une question chat toutes les 8 minutes environ.

---

## Slide 3 : Brise-glace — Le prix du non-respect
* **Layout** : Plein écran interactif (sondage)
* **Texte affiché sur la slide** :
  * **📊 Sondage n°1 — À votre avis...**
  * *Quelle amende maximale une autorité comme la CNIL peut-elle infliger en cas de manquement grave au RGPD ?*
    * A) 10 000 €  ·  B) 100 000 €  ·  C) Jusqu'à 20 M€ ou 4 % du CA mondial (le plus élevé retenu)
  * (Réponse révélée après le vote)
* **Visuels suggérés** : Marteau de justice sur fond sombre ; après le vote, « 20 M€ / 4 % » en très grand, avec en dessous, plus petit : « record européen : > 1 Md€ ».
* **Notes du présentateur** :
  * Lancer le sondage n°1, laisser 60-90 s.
  * Débrief : réponse C — expliquer les deux paliers (10 M€/2 % et 20 M€/4 %) et la règle du montant le plus élevé. Teaser du record Meta (fin de session).
  * Nuancer : la CNIL accompagne d'abord ; mais amende + réputation = souvent fatal pour une PME.

---

## Slide 4 : Qui décide, qui paie ? La voiture de course
* **Layout** : Plein écran interactif (chat) + analogie illustrée
* **Texte affiché sur la slide** :
  * **💬 Dans le chat : chez vous, qui décide du budget sécurité informatique ?**
  * **L'analogie de la voiture de course :**
    * 🏎️ **Le Risque** = l'accident (casque, airbags, pneus)
    * 🚦 **La Conformité** = le code de la route (et ses amendes)
    * 👨‍✈️ **La Gouvernance** = le pilote et l'écurie (stratégie, budget, règles d'équipe)
* **Visuels suggérés** : Voiture de course stylisée avec trois annotations (casque/panneau/pilote).
* **Notes du présentateur** :
  * Lire 4-5 réponses du chat (technicien ? DSI ? dirigeant ? personne ?) — la dispersion illustre le problème que la GRC résout.
  * Punchline : « une voiture sans pilote ne gagne pas de championnat, quelle que soit la qualité de ses pneus. »

---

## Slide 5 : La Gouvernance : PSSI & ISO 27001
* **Layout** : Deux colonnes
* **Texte affiché sur la slide** :
  * **La PSSI : la loi interne**
    * Rédigée par le RSSI, **signée par la direction** — valeur de règlement intérieur.
    * Règles concrètes : mots de passe, clés USB, arrivées... et départs.
  * **ISO 27001 : le management de la sécurité (SMSI)**
    * Une méthode, pas une liste d'outils.
    * Amélioration continue : cycle **PDCA** (Plan-Do-Check-Act).
    * La certification = une preuve auditée, un argument commercial.
* **Visuels suggérés** : Document officiel avec sceau (PSSI) ; roue de Deming (PDCA) en rotation.
* **Notes du présentateur** :
  * Insister : le RSSI propose, la direction décide et signe — la sécurité engage l'employeur et les salariés.
  * Question rhétorique : « pourquoi ISO 27001 fait-elle gagner des appels d'offres ? » (preuve auditée vs confiance déclarative).
  * Rappel A4 : le « Leaver » oublié, exactement le genre de règle qu'une PSSI impose.

---

## Slide 6 : Le NIST CSF 2.0 — désormais 6 fonctions
* **Layout** : Six blocs en arc, la fonction Gouverner en socle
* **Texte affiché sur la slide** :
  * **NIST CSF 2.0 (février 2024) : les 6 fonctions de la résilience**
  * **🆕 Gouverner** : stratégie, rôles, supervision des risques — *la fonction ajoutée par la v2.0*
  * **Identifier** : cartographier actifs et risques
  * **Protéger** : accès, chiffrement, sensibilisation
  * **Détecter** : logs, alertes, surveillance
  * **Répondre** : confinement, communication
  * **Récupérer** : restaurer et tirer les leçons
* **Visuels suggérés** : Roue à 5 segments (Identifier → Récupérer) posée sur un socle « Gouverner » distinct et mis en avant (conforme au visuel officiel CSF 2.0).
* **Notes du présentateur** :
  * Le point d'actualité : la v2.0 a ajouté GOUVERNER — dix ans pour graver que la cybersécurité se pilote en comité de direction.
  * Complémentarité : ISO 27001 structure le management, le CSF structure l'action.
  * Repère méta : « votre parcours suit ce cadre — A1-A5 : Gouverner/Identifier/Protéger ; A6-A7 : Détecter/Répondre/Récupérer. »

---

## Slide 7 : Évaluer le risque — Matrice 4×4 & stratégies
* **Layout** : Grille colorée + bandeau de stratégies
* **Texte affiché sur la slide** :
  * **Criticité = Vraisemblance (1-4) × Impact (1-4)**
  * Matrice 4×4 : zone **Verte (1-3)** accepter et suivre · zone **Orange (4-9)** réduire de façon planifiée · zone **Rouge (12-16)** traiter immédiatement
  * **Les 4 stratégies** : **Réduire** (sécuriser) · **Transférer** (assurance — l'impact financier seulement !) · **Éviter** (renoncer) · **Accepter** (documenté)
* **Visuels suggérés** : Grille 4×4 en dégradé vert→orange→rouge avec les criticités affichées dans les cellules ; quatre pictogrammes de stratégies.
* **Notes du présentateur** :
  * Prolongement chiffré de la formule d'A1 : de l'intuition à la cotation ; brute avant traitement, résiduelle après.
  * Point subtil : la criticité 4 (4×1, 2×2, 1×4) tombe toujours en orange — le rarissime-critique mérite autant d'attention que le fréquent-bénin.
  * Analogie de l'assuré : vélo à 50 € (accepter), voiture (réduire + transférer), verglas nocturne (éviter).
  * Question rhétorique : « quelle criticité pour un ransomware sur votre serveur de facturation ? Gardez votre chiffre : vous allez voter. »

---

## Slide 8 : Activité — Le Comité des Risques
* **Layout** : Consignes d'activité + 3 sondages successifs
* **Texte affiché sur la slide** :
  * **🗂️ Le Comité des Risques — 3 dossiers, 3 votes**
  * *La cotation du RSSI est donnée ; le comité (vous) vote la stratégie :*
    * **Dossier A** (📊 Sondage n°2) : portable volé avec fichier clients — criticité **9**
    * **Dossier B** (📊 Sondage n°3) : rançongiciel sur la facturation — criticité **12**
    * **Dossier C** (📊 Sondage n°4) : inondation de la salle serveur — criticité **4**
* **Visuels suggérés** : Trois chemises cartonnées « dossier du comité » avec leur pastille de criticité colorée (orange, rouge, orange clair).
* **Notes du présentateur** :
  * ~4-5 min par dossier. Réponses : A (réduire : chiffrement + MFA) ; B (réduire puis transférer le résiduel) ; B (réduire à coût marginal + accepter documenté).
  * Débriefs clés : le chiffrement effondre l'impact (dossier A, rappel du consultant d'A1) ; l'assurance rembourse mais ne restaure rien (dossier B) ; accepter ≠ ignorer — documenté, daté, signé (dossier C).
  * Conclure : « trois scénarios, trois stratégies — la matrice est un outil d'allocation de budget. »

---

## Slide 9 : Démo 5 — La matrice de risques en direct
* **Layout** : Démonstration (feuille de calcul projetée)
* **Texte affiché sur la slide** :
  * **Démonstration : du vote du comité à la matrice**
    * Les 3 dossiers placés en direct dans la matrice 4×4
    * **Avant / Après traitement** : criticité brute → criticité **résiduelle**
    * *Ex. : le rançongiciel passe de 12 (rouge) à 6 (orange) après sauvegardes immuables + EDR*
  * **💬 Proposez dans le chat un 4e risque à coter ensemble !**
* **Visuels suggérés** : Capture de la feuille de calcul avec pastilles qui se déplacent de la zone rouge vers l'orange.
* **Notes du présentateur** :
  * Suivre le [script de la Démo 5](../outils/A_scripts_demo.md#demo-5-matrice-risques) ; coter en direct le risque proposé par le chat.
  * Punchline budget : « voilà ce que vos 20 000 € achètent : un passage du rouge à l'orange. »
  * Secours : la matrice du support se déroule à l'oral avec les cotations pré-calculées.

---

## Slide 10 : Le RGPD & la vie privée
* **Layout** : Deux colonnes + 2 sondages
* **Texte affiché sur la slide** :
  * **Les 4 principes de chaque traitement :**
    * **Finalité** précise · **Minimisation** · **Consentement actif & transparence** · **Droits des personnes** (accès gratuit, rectification, effacement)
  * **En cas de violation : notifier la CNIL sous 72 h** (et informer les personnes si risque élevé)
  * **📊 Sondage n°5** : fuite de données — quelle obligation légale ?
  * **📊 Sondage n°6** : peut-on facturer le droit d'accès d'un client ?
* **Visuels suggérés** : Bouclier étoilé européen ; chronomètre « 72 h » ; les 4 principes en pictogrammes.
* **Notes du présentateur** :
  * Faire réagir : « votre adresse IP est une donnée personnelle — surpris ? » ; case pré-cochée interdite ; minimisation = « moindre privilège de la donnée » (écho A4).
  * Sondages n°5-6 : réponses A (72 h — le chrono court dès la découverte, d'où l'importance de la détection, teaser A6) et B (gratuit).
  * Relier à France Travail (A1) : l'information des personnes, c'est exactement ce qui s'est passé.

---

## Slide 11 : Les amendes réelles — le RGPD a des dents
* **Layout** : Mosaïque de grands chiffres (stat cards)
* **Texte affiché sur la slide** :
  * **Des sanctions bien réelles (sources : CNIL / autorités européennes)**
  * **1,2 Md€** — Meta, 2023 : transferts de données vers les États-Unis *(record européen)*
  * **50 M€** — Google, 2019 : transparence et consentement défaillants *(CNIL, la sanction fondatrice)*
  * **20 M€** — Clearview AI, 2022 : biométrie aspirée sur le web sans consentement *(CNIL)*
  * **Plusieurs milliards €** cumulés en Europe depuis 2018
* **Visuels suggérés** : Cartes de montants en très grand corps, logos neutralisés (pas de logos officiels), année et autorité en petit.
* **Notes du présentateur** :
  * Les 3 messages : le RGPD est appliqué y compris contre les géants ; on sanctionne des PRINCIPES, pas seulement des fuites ; pour une PME, le vrai coût est la confiance perdue.
  * Transition : « regardons la sanction fondatrice de plus près. »

---

## Slide 12 : Étude de cas — Google vs CNIL (2019)
* **Layout** : Étude de cas + question chat
* **Texte affiché sur la slide** :
  * **Google, janvier 2019 — 50 M€ : ni piratage, ni fuite**
    * Information **diluée** dans une arborescence de menus
    * Consentement **ni éclairé, ni spécifique** (une case unique = accord global)
    * → Manquements aux **principes** : transparence & consentement
  * **« Un système parfaitement sécurisé peut être parfaitement illégal. »**
  * **💬 Dans le chat : la dernière fois que vous avez « tout accepté » sans lire — quelle donnée avez-vous confiée sans le vouloir ?**
* **Visuels suggérés** : Parcours de menus labyrinthique stylisé ; case à cocher unique barrée de rouge.
* **Notes du présentateur** :
  * Raconter : 8 mois après l'entrée en application du RGPD, la première sanction d'ampleur — le message aux acteurs mondiaux.
  * Lire 3-4 réponses du chat ; conclure sur l'exercice self-paced de la semaine (lire une politique de confidentialité).
  * Boucler : depuis, l'échelle a changé (Meta 1,2 Md€) — « le RGPD a des dents, et elles poussent. »

---

## Slide 13 : Quiz de validation
* **Layout** : Contenu interactif (3 sondages successifs)
* **Texte affiché sur la slide** :
  * **✅ Quiz de validation — 3 questions, 3 votes (Vrai / Faux)**
  * **📊 Sondage n°7** : La PSSI a valeur de règlement intérieur.
  * **📊 Sondage n°8** : Transférer un risque (assurance) le fait disparaître du système.
  * **📊 Sondage n°9** : La minimisation = collecter le moins de données possible pour un but donné.
* **Visuels suggérés** : Trois cartes Vrai/Faux révélées successivement, coche verte à la révélation.
* **Notes du présentateur** :
  * Réponses : Vrai ; Faux (l'impact financier est partagé, le sinistre demeure — rejouer le débrief du dossier B) ; Vrai (le moindre privilège de la donnée).
  * Si le temps le permet : **📊 Sondage n°10** (bonus : le n° de sécurité sociale dans un fichier de prospection → Non, minimisation ; la case générique ne sauve rien — écho au cas Google).

---

## Slide 14 : Clôture & Devoirs
* **Layout** : Fin de session / Synthèse
* **Texte affiché sur la slide** :
  * **Vos trois lettres de la session 05 :**
    * **G** — Gouvernance : qui décide, avec quel budget *(NIST CSF 2.0 : fonction Gouverner)*
    * **R** — Risque : coter, puis Réduire / Transférer / Éviter / Accepter
    * **C** — Conformité : pas besoin d'être piraté pour être sanctionné
  * **💬 Dans le chat : le mot que vous retenez**
  * **Devoirs avant A6** : module IBM SkillsBuild *Opérations de sécurité, surveillance et gestion des logs* (~70 min) + lire la politique de confidentialité d'un de vos services en ligne et relever les finalités.
  * **Prochaine séance** : *Opérations de sécurité & gestion des vulnérabilités (A6)*.
* **Visuels suggérés** : Trois grandes lettres G-R-C avec leur pictogramme ; icône de cadenas RGPD ; logo IBM SkillsBuild.
* **Notes du présentateur** :
  * Lire 4-5 mots du chat à voix haute.
  * Teaser A6 : « le chrono des 72 h ne démarre que si quelqu'un DÉTECTE la fuite — la semaine prochaine : le SOC, les alertes, les vulnérabilités. »
  * Libérer à l'heure exacte.
