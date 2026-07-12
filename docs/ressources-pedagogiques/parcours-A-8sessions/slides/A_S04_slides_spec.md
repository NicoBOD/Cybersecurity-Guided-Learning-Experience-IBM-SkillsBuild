# Spécifications des slides — Session 04 : Sécurité du cloud, des données & des identités
Parcours : A 8 sessions  |  Module : Cloud & Données  |  Format : Spécifications Markdown  |  Modalité : Webinaire Livestorm

> **Principe directeur** : le texte affiché reste minimal ; le contenu riche est dans les notes du présentateur et dans le [plan d'animation minuté](../plans-de-seance/A_S04_plan.md), qui fait référence pour les verbatims et débriefs. Les numéros de sondages renvoient à la checklist Livestorm du plan.

---

## Slide 1 : Page de garde
* **Layout** : Titre (Emphase visuelle, fond sombre)
* **Texte affiché sur la slide** :
  * **Sécurité du Cloud, des Données & des Identités**
  * Parcours A — Session 04
  * *Verrouiller l'accès : identités, responsabilité partagée et protection du patrimoine de données*
  * Nom du Mentor / IBM SkillsBuild
* **Visuels suggérés** : Représentation d'un nuage (cloud) entouré d'anneaux de sécurité lumineux, avec une clé dorée au centre. Logo officiel dans un angle.
* **Notes du présentateur** :
  * Accueillir ; retour sur les devoirs d'A3 : « tapez "trouvé" dans le chat si votre adresse apparaissait sur Have I Been Pwned, "rien" sinon » — commenter la proportion sans détails personnels.
  * Pivot : « vos identifiants circulent — comment faire pour que ça ne suffise plus à entrer ? C'est la session du jour. »

---

## Slide 2 : Objectifs de la séance & Sommaire
* **Layout** : Deux colonnes (Gauche : Objectifs, Droite : Sommaire)
* **Texte affiché sur la slide** :
  * **Nos objectifs aujourd'hui** :
    * Appliquer le moindre privilège avec l'IAM et la matrice RBAC.
    * Comprendre la puissance du MFA... et ses limites.
    * Situer la frontière de la responsabilité partagée dans le cloud.
    * Bâtir une sauvegarde qui résiste aux ransomwares (3-2-1).
  * **Sommaire de la séance** :
    * 1. Brise-glace : le chiffre du MFA (6 min)
    * 2. IAM & moindre privilège + activité « Gardien des Accès » (24 min)
    * 3. Le MFA en profondeur + démo (18 min)
    * 4. Chiffrement & responsabilité partagée (8 min)
    * 5. La règle 3-2-1 & le NAS piégé (8 min)
    * 6. Cas réels : OVHcloud & Capital One (9 min)
    * 7. Quiz & synthèse (8 min)
* **Visuels suggérés** : Icônes cibles pour les objectifs et icône de liste pour le sommaire.
* **Notes du présentateur** :
  * Souligner que tout s'applique aussi à la vie personnelle (comptes, sauvegardes familiales).
  * Annoncer le rythme : un sondage ou une question chat toutes les 8 minutes environ.

---

## Slide 3 : Brise-glace — Le chiffre du MFA
* **Layout** : Plein écran interactif (sondage)
* **Texte affiché sur la slide** :
  * **📊 Sondage n°1 — À votre avis...**
  * *Selon Microsoft, quelle proportion des attaques automatisées de compromission de comptes le MFA bloque-t-il ?*
    * A) ~50 %  ·  B) ~80 %  ·  C) > 99,9 %  ·  D) 100 %
  * (Réponse révélée après le vote)
* **Visuels suggérés** : Grand bouclier stylisé ; après le vote, « > 99,9 % » en très grand avec la mention *(Microsoft, 2019 — attaques automatisées)*.
* **Notes du présentateur** :
  * Lancer le sondage n°1, laisser 60-90 s.
  * Débrief : réponse C — préciser l'honnêteté du chiffre : attaques AUTOMATISÉES, et pas 100 % (les attaques ciblées savent parfois contourner — suite dans la session).
  * Message : le meilleur rapport protection/effort de toute la cybersécurité ; reboucler avec les « trouvé » du chat.

---

## Slide 4 : La clé unique de l'immeuble
* **Layout** : Plein écran interactif (chat)
* **Texte affiché sur la slide** :
  * **💬 Dans le chat : vous gérez un immeuble de bureaux.**
  * *Donneriez-vous le passe-partout (coffre-fort et locaux techniques compris) à tous les employés — y compris au stagiaire d'une semaine ?*
  * Pourquoi personne ne fait ça dans le monde physique... et pourquoi le fait-on si souvent en informatique ?
* **Visuels suggérés** : Photo d'un énorme trousseau de clés en désordre à côté d'un badge unique « ACCÈS TOTAL ».
* **Notes du présentateur** :
  * Laisser ~3 minutes de débat chat, lire 3-4 hypothèses.
  * Révéler : en informatique, donner tous les droits est invisible et immédiat — la facilité gagne, et chaque droit de trop est une porte de plus. La discipline qui corrige : l'IAM.

---

## Slide 5 : IAM & le moindre privilège
* **Layout** : Deux colonnes + matrice
* **Texte affiché sur la slide** :
  * **IAM : la bonne personne, le bon accès, le bon moment**
  * *Authentification (qui suis-je ?) ≠ Autorisation (que puis-je faire ?)*
  * **Moindre privilège : minimal · nominatif · temporaire**
  * **Matrice RBAC (extrait)** : Commercial → Ventes ✔ / Salaires ✖ · RH → Salaires ✔ / Ventes ✖ · DG → lecture large, écriture nulle part sans besoin
* **Visuels suggérés** : Matrice RBAC simplifiée en tableau coloré (coches vertes / croix rouges) ; badge d'identité.
* **Notes du présentateur** :
  * Double bénéfice du moindre privilège : confiner la compromission (rappel A3 : déplacement latéral) et limiter la maladresse.
  * L'attaquant entre par un compte ordinaire (phishing A2) puis tente l'escalade de privilèges — le moindre privilège la transforme en parcours du combattant.
  * Mentionner JML : le « Leaver » oublié (compte d'ex-salarié actif) = grand classique d'audit.
  * Question rhétorique : « combien d'administrateurs dans une PME de 50 personnes ? Et combien devraient l'être ? »

---

## Slide 6 : Activité — Le Gardien des Accès
* **Layout** : Consignes d'activité + 3 sondages successifs
* **Texte affiché sur la slide** :
  * **🗝️ Le Gardien des Accès — 3 demandes, 3 votes**
  * *Vous administrez les accès de la PME. Tranchez dans le respect du moindre privilège :*
    * **Demande 1** (📊 Sondage n°2) : le commercial veut le dossier Salaires « pour ses commissions »
    * **Demande 2** (📊 Sondage n°3) : le stagiaire d'une semaine doit consulter deux contrats
    * **Demande 3** (📊 Sondage n°4) : le DG exige l'écriture sur TOUS les dossiers
* **Visuels suggérés** : Trois cartes « ticket de demande d'accès » révélées une à une ; tampons ACCORDÉ/REFUSÉ.
* **Notes du présentateur** :
  * ~4 min par demande (vote + débrief). Réponses : B / B / B.
  * Débriefs clés : répondre au besoin, pas à la demande (n°2) ; minimal-nominatif-temporaire, l'héritage du tuteur est le péché originel (n°3) ; l'exposition prime sur la hiérarchie — c'est le DG qu'on usurpe ET qu'on cible (n°4, rappel A2).

---

## Slide 7 : L'arme absolue : Le MFA — et ses limites
* **Layout** : Trois colonnes de facteurs + bandeau hiérarchie
* **Texte affiché sur la slide** :
  * **MFA : combiner deux facteurs de natures différentes**
    * **1. Ce que je sais** : mot de passe, code PIN
    * **2. Ce que j'ai** : application d'authentification, clé physique, (SMS)
    * **3. Ce que je suis** : empreinte, visage
  * **Les contournements à connaître** : SIM swapping · MFA fatigue · hameçonnage du code en temps réel
  * **Hiérarchie** : passkey/clé physique > application > SMS > mot de passe seul — *mais SMS ≫ rien !*
* **Visuels suggérés** : Icônes cerveau/smartphone/empreinte ; échelle de solidité à 4 barreaux, du mot de passe seul (rouge) à la passkey (vert).
* **Notes du présentateur** :
  * Deux mots de passe = un seul facteur ! La force vient de la combinaison de natures différentes.
  * Rappel A2 : la démo vishing demandait exactement le code MFA — l'hameçonnage du code existe, d'où les passkeys (FIDO2), liées au site légitime : un faux site n'obtient rien.
  * Priorités d'activation : messagerie (la clé de toutes les autres serrures), banque, comptes d'administration.

---

## Slide 8 : Démo 4 — Sécuriser une identité de A à Z
* **Layout** : Démonstration (partage d'écran)
* **Texte affiché sur la slide** :
  * **Démonstration : votre identité, blindée en 10 minutes**
    * Étape 1 : vérifier son exposition (fuites publiques — Have I Been Pwned)
    * Étape 2 : enrôler une application d'authentification (TOTP — le code qui tourne)
    * Étape 3 : générer et remplir des mots de passe forts avec un gestionnaire
  * *Le tout sur comptes de démonstration.*
* **Visuels suggérés** : Trois vignettes d'étapes ; QR code d'enrôlement TOTP stylisé (factice).
* **Notes du présentateur** :
  * Suivre le [script de la Démo 4](../outils/A_scripts_demo.md#demo-4-identites) ; captures de secours prêtes en cas de pépin.
  * Points clés : le code TOTP est généré localement (rien à intercepter par SMS) ; le gestionnaire résout « unique + long + mémorisable » — l'humain retient UN mot de passe maître.
  * **💬 Chat** : « qui utilise déjà un gestionnaire de mots de passe ? » — valoriser, renvoyer au self-paced.

---

## Slide 9 : Chiffrement — en transit vs au repos
* **Layout** : Deux colonnes comparatives
* **Texte affiché sur la slide** :
  * **Protéger la donnée à chaque étape de sa vie**
  * **En transit** : pendant le voyage — TLS/HTTPS (l'enveloppe blindée d'A3)
  * **Au repos** : une fois stockée — BitLocker, FileVault, chiffrement des bases
  * **Il faut les deux** : une lettre blindée déposée dans une boîte ouverte ne protège rien.
* **Visuels suggérés** : Enveloppe blindée en mouvement (transit) vs coffre-fort (repos) ; portable volé barré d'un cadenas.
* **Notes du présentateur** :
  * Rappel du consultant d'A1 : portable perdu dans le train, disque chiffré = données illisibles.
  * Moyen mnémotechnique : l'enveloppe pendant le voyage, le coffre-fort à l'arrivée.

---

## Slide 10 : Qui fait quoi dans le cloud ? Responsabilité partagée
* **Layout** : Schéma à couches empilées
* **Texte affiché sur la slide** :
  * **Le fournisseur sécurise LE cloud · Le client sécurise DANS le cloud**
  * **Fournisseur (EUX)** : centres de données, matériel, hyperviseurs, électricité
  * **Client (VOUS)** : identités & accès (IAM, MFA), configurations, données — *toujours, quel que soit le modèle*
  * **La frontière glisse selon IaaS / PaaS / SaaS** (en IaaS, vous patchez aussi l'OS et vos applications)
  * ❌ *« C'est dans le cloud donc c'est sécurisé »* · ❌ *« C'est dans le cloud donc c'est sauvegardé »*
* **Visuels suggérés** : Diagramme en barres horizontales IaaS/PaaS/SaaS avec la frontière de responsabilité qui monte ; les deux idées reçues barrées en rouge.
* **Notes du présentateur** :
  * Dérouler l'analogie du locataire : le propriétaire assure murs et porte d'immeuble ; la serrure de VOTRE porte, les fenêtres et qui entre, c'est vous.
  * **💬 Chat** : « citez UNE chose qui reste à la charge du locataire » — lire 3-4 réponses ; teaser : « l'assurance habitation, c'est la sauvegarde — juste après. »

---

## Slide 11 : La règle 3-2-1 & le NAS piégé
* **Layout** : Infographie + 2 sondages
* **Texte affiché sur la slide** :
  * **La règle 3-2-1 : 3 copies · 2 supports · 1 hors site**
  * **+ les compléments modernes** : copie **immuable** ou **déconnectée** · règle « 0 » : une sauvegarde jamais testée n'est pas une sauvegarde
  * **📊 Sondage n°5** : NAS branché en permanence + ransomware le week-end — quel risque ?
  * **📊 Sondage n°6** : la parade la plus efficace ?
* **Visuels suggérés** : Infographie 3-2-1 (trois disques, deux supports, un nuage distant) ; NAS avec chaîne brisée.
* **Notes du présentateur** :
  * Dérouler chaque chiffre avec son scénario de panne (corruption / panne matérielle / incendie-ransomware).
  * Sondages n°5-6 : réponses B et B — les ransomwares chiffrent EN PRIORITÉ les sauvegardes joignables ; relier au déplacement latéral d'A3 (un NAS joignable depuis le réseau compromis fait partie du réseau compromis).

---

## Slide 12 : Deux cas réels — OVHcloud (2021) & Capital One (2019)
* **Layout** : Deux panneaux « étude de cas » + scénario chat
* **Texte affiché sur la slide** :
  * **OVHcloud, mars 2021 — l'incendie de Strasbourg** : le bâtiment SBG2 détruit → les clients dont les « sauvegardes » étaient dans le même bâtiment ont **tout perdu**. *Ni piratage, ni fraude : un incendie.*
  * **Capital One, 2019 — la faille de configuration** : un pare-feu applicatif mal configuré + un rôle **trop privilégié** → **~106 M de clients** touchés, 80 M$ d'amende + 190 M$ d'indemnisation.
  * **🤔 Votre prestataire dit : « pas besoin de sauvegarde, c'est dans le cloud, c'est répliqué. » Que répondez-vous ? A/B/C dans le chat**
* **Visuels suggérés** : Deux cartes « dossier » : flammes + datacenter (OVH), nuage fissuré + cadenas ouvert (Capital One). Chiffres en très grand.
* **Notes du présentateur** :
  * OVHcloud : « le 1 hors site signifie VRAIMENT hors site » ; la sauvegarde des données reste au client sauf service souscrit.
  * Capital One : ce n'est pas le cloud qui a failli, c'est la configuration DU CLIENT — et le moindre privilège absent : le rôle compromis ouvrait la salle des coffres au lieu d'un placard (reboucler avec le Gardien des Accès).
  * Scénario chat : réponse B — la réplication synchronise tout, y compris les suppressions et le chiffrement ransomware.

---

## Slide 13 : Quiz de validation
* **Layout** : Contenu interactif (3 sondages successifs)
* **Texte affiché sur la slide** :
  * **✅ Quiz de validation — 3 questions, 3 votes**
  * **📊 Sondage n°7** : Le principe des accès strictement nécessaires ? *(moindre privilège / responsabilité partagée / 3-2-1 / SSO)*
  * **📊 Sondage n°8** : Pourquoi l'application d'authentification est-elle préférable au SMS ? *(rapidité / SIM swapping / coût)*
  * **📊 Sondage n°9** : Stockage cloud mal configuré, données exposées — qui est responsable ? *(le fournisseur / le client / personne)*
* **Visuels suggérés** : Trois cartes de questions révélées successivement, coche verte à la révélation.
* **Notes du présentateur** :
  * Réponses : moindre privilège ; SIM swapping ; le client.
  * Débriefs : minimal-nominatif-temporaire (n°7) ; hiérarchie des facteurs, SMS ≫ rien (n°8) ; Capital One et la serrure du locataire (n°9).
  * Si le temps le permet : **📊 Sondage n°10** (bonus : incendie + deux disques sur site → perte définitive, écho OVHcloud).

---

## Slide 14 : Clôture & Devoirs
* **Layout** : Fin de session / Synthèse
* **Texte affiché sur la slide** :
  * **Vos quatre réflexes de la session 04 :**
    * 🗝️ Moindre privilège — minimal, nominatif, temporaire
    * 🛡️ MFA partout — > 99,9 % des attaques automatisées bloquées
    * 🏠 Responsabilité partagée — la serrure de votre porte, c'est vous
    * 💾 3-2-1 — dont 1 copie VRAIMENT hors site, immuable, testée
  * **💬 Dans le chat : le réflexe que vous retenez**
  * **Devoirs avant A5** : module IBM SkillsBuild *Introduction à la GRC* (~60 min) + installer un gestionnaire de mots de passe et activer le MFA sur votre messagerie.
  * **Prochaine séance** : *Gouvernance, risque, conformité & vie privée (A5)* — 🎉 mi-parcours !
* **Visuels suggérés** : Quatre pictogrammes des réflexes ; jauge de progression à 50 % ; logo IBM SkillsBuild.
* **Notes du présentateur** :
  * Lire 4-5 réflexes du chat ; féliciter pour la première moitié du parcours.
  * Teaser A5 : « qui décide, qui paie, que dit la loi — avec une amende record à 9 chiffres au programme. »
  * Libérer à l'heure exacte.
