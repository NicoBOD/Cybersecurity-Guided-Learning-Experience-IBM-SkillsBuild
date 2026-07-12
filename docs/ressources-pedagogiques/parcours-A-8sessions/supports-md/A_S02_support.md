# Support de cours — Session 02 : Menaces, attaques & ingénierie sociale
Parcours : A 8 sessions  |  Module : Menaces Cyber  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - La typologie des logiciels malveillants (*Malwares*)
    - Les mécanismes de l'ingénierie sociale
    - La Cyber Kill Chain : Comprendre le parcours de l'attaquant
    - L'hameçonnage en chiffres (sources récentes) et deux fraudes réelles spectaculaires
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

Les cyberattaques modernes ciblent de plus en plus le maillon réputé le plus vulnérable de la chaîne de sécurité : l'être humain. Ce support de cours détaille les mécanismes de l'ingénierie sociale, l'art de manipuler les personnes pour contourner les protections technologiques. Vous étudierez les principaux types de logiciels malveillants (*malware*), du rançongiciel destructeur au cheval de Troie discret. Nous décrypterons également les ressorts psychologiques du phishing (hameçonnage), du vishing (par téléphone) et les grandes étapes de la *Cyber Kill Chain*, le modèle théorique qui décrit le déroulement d'une attaque de son ciblage initial jusqu'à sa conclusion logique. Deux affaires réelles — dont une fraude par deepfake à 25 millions de dollars — démontreront que ces manipulations piègent même des professionnels aguerris. L'objectif est de vous donner les clés pour identifier instantanément les signaux d'alerte et adopter des réflexes d'hygiène numérique indispensables.

### Objectifs de la session

À l'issue de cette session, vous serez capable de :

- **Classifier** les principales familles de codes malveillants (rançongiciels, chevaux de Troie, logiciels espions, vers) selon leurs modes de fonctionnement.
- **Reconnaître** les indices de suspicion d'une tentative d'hameçonnage par e-mail, SMS (*smishing*) ou téléphone (*vishing*), et les leviers psychologiques exploités.
- **Décrire** les 7 étapes d'une intrusion avec la *Cyber Kill Chain* et identifier où la briser.
- **Appliquer** le réflexe de la double validation par canal alternatif face à toute demande sensible.

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** À votre avis, combien de temps s'écoule, en médiane, entre l'ouverture d'un e-mail de phishing et le moment où la victime clique et saisit ses données ?

    - A) Moins d'une minute ✅
    - B) Environ une heure
    - C) Environ une journée
    - D) Environ une semaine

    **Débrief mentor :** Moins d'une minute, selon le *Data Breach Investigations Report* 2024 de Verizon (environ 21 secondes pour cliquer, 28 secondes de plus pour saisir les données). Message clé : l'hameçonnage ne laisse pas le temps de la réflexion *a posteriori* — c'est AVANT, par le réflexe, que tout se joue. Cette session sert à installer ce réflexe.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Psychologie de l'Ingénierie Sociale**
Détaillez les ressorts psychologiques exploités par les attaquants : l'urgence (faux e-mail du PDG demandant un virement sous 2 heures), la peur (fausse amende gouvernementale), ou la cupidité (faux gain à un concours). Insistez sur le fait que l'humain est souvent le maillon faible malgré les meilleurs pare-feux. Référence utile pour aller plus loin : les six principes d'influence de Robert Cialdini (réciprocité, cohérence, preuve sociale, autorité, sympathie, rareté), dont les attaquants sont d'excellents praticiens.

**2. Anatomie d'une attaque de Spear-Phishing**
Décomposez une attaque ciblée étape par étape :
- *Reconnaissance* (OSINT) : Collecte d'informations sur l'organigramme via LinkedIn — c'est exactement la surface d'exposition cartographiée en session A1.
- *Fabrication de l'arme* : Création d'un e-mail reprenant la signature exacte du directeur financier.
- *Exploitation* : L'utilisateur clique sur une pièce jointe Excel contenant une macro malveillante.

**3. La nouvelle frontière : l'IA générative au service de la fraude**
Les modèles d'IA ont fait disparaître les indices historiques (fautes d'orthographe, formulations maladroites) et permettent désormais l'usurpation de voix (*voice cloning*) et de visage (*deepfake*) en temps réel — le cas Arup étudié plus bas en est l'illustration. Conséquence pédagogique : la détection ne peut plus reposer uniquement sur la forme du message ; elle doit reposer sur la **procédure** (double validation par canal alternatif, quel que soit le réalisme de la demande).

**4. Ateliers pratiques de détection**
L'activité « Chasse au phishing » (sondages n°2 à 5) projette quatre messages à l'écran : montrez comment inspecter l'adresse de l'expéditeur, vérifier le domaine (typosquatting comme `amaz0n.com`) et survoler les liens hypertextes sans cliquer. En webinaire, faites voter avant de révéler chaque analyse.

---

### Glossaire

*   **Backdoor (Porte dérobée)** — Accès caché installé sur un système, permettant à un attaquant d'y revenir à volonté en contournant les authentifications normales.
*   **BEC (Business Email Compromise)** — Fraude par compromission de la messagerie professionnelle, où un pirate usurpe l'identité d'un dirigeant ou d'un fournisseur pour ordonner des virements frauduleux (dont « l'arnaque au président »).
*   **Cyber Kill Chain** — Cadre conceptuel décrivant les 7 étapes chronologiques d'une cyberattaque réussie, développé par Lockheed Martin.
*   **Deepfake (Hypertrucage)** — Contenu audio ou vidéo falsifié par intelligence artificielle, imitant de manière réaliste la voix ou le visage d'une personne réelle.
*   **Ingénierie sociale (Social Engineering)** — Manipulation psychologique visant à extorquer des informations confidentielles ou à faire accomplir des actions dangereuses à une victime.
*   **Malware (Logiciel malveillant)** — Terme générique désignant tout programme conçu pour nuire à un système informatique (virus, ver, rançongiciel, etc.).
*   **Phishing (Hameçonnage)** — Technique frauduleuse par e-mail visant à tromper le destinataire pour lui soutirer des informations confidentielles (mots de passe, numéros de carte bancaire) en usurpant l'identité d'une marque de confiance.
*   **Ransomware (Rançongiciel)** — Malware qui chiffre les fichiers d'un utilisateur ou d'une entreprise et réclame le paiement d'une rançon en échange de la clé de déchiffrement.
*   **Smishing** — Attaque d'ingénierie sociale réalisée par SMS pour pousser la victime à visiter un site malveillant ou à divulguer des données.
*   **Spear-phishing (Hameçonnage ciblé)** — Variante hautement personnalisée du phishing, ciblant un individu ou une organisation spécifique en exploitant des détails personnels collectés à l'avance.
*   **Typosquatting** — Enregistrement d'un nom de domaine imitant celui d'une marque à une ou deux lettres près (`netf1ix.com`, `amaz0n.com`) pour tromper l'œil de la victime.
*   **Vishing (Hameçonnage vocal)** — Technique de manipulation par téléphone où l'attaquant usurpe l'identité d'un tiers de confiance (ex. conseiller bancaire) pour extorquer des informations.

---

### 1. La typologie des logiciels malveillants (*Malwares*)

!!! info "À retenir"
    Retenez la question qui classe chaque malware : **que cherche-t-il à faire ?** Extorquer (rançongiciel), ouvrir une porte (cheval de Troie), observer (logiciel espion) ou se propager (ver).

Les programmes malveillants revêtent des formes diverses selon l'objectif poursuivi par les attaquants :

#### A. Les Rançongiciels (*Ransomware*)
C'est la menace financière majeure pour les organisations. Le malware s'introduit dans le système, identifie les serveurs et les partages de fichiers critiques, puis applique un chiffrement fort. Les pirates réclament une rançon payable en cryptomonnaie en échange de l'outil de déchiffrement. Souvent, ils menacent également de divulguer publiquement les données volées (double extorsion) — vous avez vu ce mécanisme à l'œuvre en session A1 avec le cas de l'hôpital de Corbeil-Essonnes.

#### B. Les Chevaux de Troie (*Trojan Horse*)
Un programme d'apparence légitime et inoffensive, mais contenant des fonctionnalités malveillantes cachées. Une fois installé par l'utilisateur, il ouvre des portes dérobées (*backdoors*) pour permettre aux pirates de prendre le contrôle de la machine à distance. Comme le cheval du mythe grec : c'est la victime elle-même qui fait entrer la menace dans ses murs.

#### C. Les Logiciels espions (*Spyware / Keylogger*)
Des outils discrets installés sur le système pour collecter des données à l'insu de l'utilisateur. Un *keylogger* enregistre chaque touche pressée sur le clavier, capturant ainsi les mots de passe lors de leur saisie. Leur force : ils ne cassent rien, ne bloquent rien — ils observent, parfois pendant des mois.

#### D. Les Vers (*Worms*)
Des malwares autonomes capables de se propager d'ordinateur en ordinateur à travers le réseau en exploitant des failles de sécurité, sans nécessiter d'interaction humaine (contrairement aux virus traditionnels qui nécessitent l'exécution d'un fichier hôte). C'est cette capacité d'auto-propagation qui a permis à WannaCry (vu en A1) de faire le tour du monde en quelques jours.

!!! question "💬 Question chat — À vous de jouer"
    Un « antivirus gratuit » téléchargé sur un site douteux installe en réalité un programme qui enregistre vos frappes clavier. **Combien de familles de malwares reconnaissez-vous dans cette seule phrase ? Tapez votre réponse dans le chat.** (Réponse mentor : deux — un cheval de Troie, car le programme se fait passer pour légitime, qui installe un logiciel espion de type keylogger. Les familles se combinent presque toujours.)

### 2. Les mécanismes de l'ingénierie sociale

L'ingénierie sociale repose sur l'exploitation de biais psychologiques humains. Les pirates n'attaquent pas les serveurs chiffrés, ils manipulent l'humain pour qu'il leur ouvre la porte.

#### Les 4 leviers de manipulation les plus courants :
1. **L'Urgence** : "Votre compte bancaire sera suspendu dans 2 heures si vous ne validez pas ce lien." L'urgence empêche la victime de réfléchir rationnellement.
2. **L'Autorité** : Le pirate se fait passer pour le directeur général, la police, ou un inspecteur des impôts pour exiger un transfert d'information.
3. **La Confiance** : Usurper l'identité d'un collègue, d'un fournisseur habituel ou d'un service connu (EDF, Netflix, La Poste).
4. **La Curiosité / L'Appât du gain** : "Vous avez gagné un bon d'achat" ou "Découvrez le fichier contenant les salaires de l'entreprise".

#### Les déclinaisons de l'hameçonnage :
* **Phishing** : E-mail générique envoyé à des millions de destinataires.
* **Spear-phishing** : E-mail personnalisé (ex. "Bonjour Julie, suite à notre discussion de ce matin sur le projet X, merci de valider ce document").
* **Smishing** : Hameçonnage par SMS (ex. "Votre colis a rencontré un problème de livraison, visitez...").
* **Vishing** : Hameçonnage par téléphone (ex. le faux conseiller bancaire appelant pour faire annuler de "fausses transactions frauduleuses").

Notez la logique économique : le phishing de masse mise sur le volume (un taux de réussite de 0,1 % sur un million d'e-mails = 1 000 victimes), tandis que le spear-phishing mise sur la préparation — quelques heures de recherche OSINT (session A1) pour un seul e-mail, mais un taux de réussite démultiplié et des gains bien supérieurs.

### 3. La Cyber Kill Chain : Comprendre le parcours de l'attaquant

La *Cyber Kill Chain* permet aux défenseurs de comprendre la séquence logique d'une intrusion. Si la chaîne est brisée à n'importe quelle étape, l'attaque échoue.

```
[1. Reconnaissance] ➔ [2. Armement] ➔ [3. Livraison] ➔ [4. Exploitation] ➔ [5. Installation] ➔ [6. Commande & Contrôle (C2)] ➔ [7. Actions sur Objectifs]
```

1. **Reconnaissance** : Recherche d'informations sur la cible (adresses e-mail, outils utilisés, organigramme).
2. **Armement** : Création d'une charge malveillante (ex. un document PDF contenant un code malveillant associé à un message de phishing convaincant).
3. **Livraison** : Envoi de la charge à la victime (par e-mail, clé USB, ou téléchargement web).
4. **Exploitation** : Le code malveillant s'exécute en exploitant une vulnérabilité du système (ex. le lecteur PDF de la victime n'est pas à jour).
5. **Installation** : Le logiciel malveillant s'installe sur la machine cible pour s'y implanter durablement.
6. **Commande & Contrôle (C2)** : Le malware ouvre un canal de communication avec le serveur des pirates pour recevoir des instructions.
7. **Actions sur Objectifs** : Les attaquants atteignent leur but final (exfiltration de données confidentielles ou chiffrement du réseau).

L'intérêt défensif du modèle : à chaque maillon correspond une contre-mesure. La sensibilisation (que vous suivez en ce moment) agit sur les étapes 1 et 3-4 ; le filtrage de messagerie sur l'étape 3 ; les mises à jour sur l'étape 4 ; l'antivirus/EDR sur l'étape 5 ; la surveillance réseau sur l'étape 6. C'est la défense en profondeur d'A1, projetée dans le temps de l'attaque. Pour les curieux : le framework MITRE ATT&CK (cité en ressources) est la version moderne et détaillée de cette logique, recensant les techniques réelles observées.

### 4. L'hameçonnage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **Moins d'une minute** : temps médian entre l'ouverture d'un e-mail de phishing et la saisie des données par la victime (Verizon, *Data Breach Investigations Report*, 2024).
    - **L'hameçonnage est la menace n°1 en volume pour les particuliers** en France ; côté entreprises et collectivités, le **piratage de compte** — souvent consécutif à un hameçonnage — figure en tête des demandes d'assistance (Cybermalveillance.gouv.fr, rapport d'activité 2024).
    - **De l'ordre de 2,8 milliards de dollars** : pertes annuelles déclarées au FBI pour la seule fraude BEC (faux ordres de virement) aux États-Unis — l'une des fraudes les plus lucratives au monde, loin devant les rançongiciels en montants déclarés (FBI, *Internet Crime Report* IC3, 2024).
    - Rappel de la session A1 : **le facteur humain est impliqué dans environ 60 % des violations** (Verizon DBIR 2025) — et l'hameçonnage en est le premier artisan.

**Comment lire ces chiffres ?** L'ingénierie sociale n'est pas un folklore de « petites arnaques » : c'est l'industrie la plus rentable de la cybercriminalité, parce qu'elle attaque ce qui ne se met pas à jour — nos réflexes. La bonne nouvelle : contrairement à une faille logicielle, le « correctif humain » existe, il s'appelle la procédure de double validation, et vous allez l'entraîner aujourd'hui.

### 5. Deux fraudes réelles spectaculaires

#### Cas n°1 — Pathé (2018) : l'arnaque au président à 19 millions d'euros

En mars 2018, les deux dirigeants de la filiale néerlandaise du groupe de cinéma français Pathé reçoivent des e-mails semblant provenir du siège parisien : une « acquisition confidentielle à Dubaï » est en cours et exige des virements urgents et strictement secrets. En quelques semaines, environ **19,2 millions d'euros** sont transférés vers des comptes frauduleux, en plusieurs virements successifs. Aucun malware, aucune intrusion technique : uniquement de faux e-mails et les leviers de l'**autorité** (le siège), de l'**urgence** (l'opération est imminente) et du **secret** (interdiction d'en parler, ce qui neutralise la double validation). Les deux dirigeants — expérimentés et de bonne foi — ont été licenciés ; les fonds n'ont jamais été intégralement récupérés.

**Ce que ce cas illustre :** le BEC ne cible pas les naïfs, il cible les processus. Quand une demande combine autorité + urgence + confidentialité, c'est précisément le moment d'appliquer la procédure de vérification, pas de la suspendre.

#### Cas n°2 — Arup (2024) : la visioconférence deepfake à 25 millions de dollars

Début 2024, un employé de la branche hongkongaise du cabinet d'ingénierie britannique Arup (le concepteur de l'Opéra de Sydney) reçoit un e-mail suspect demandant des virements confidentiels. Méfiant, il demande une confirmation... et l'obtient : une **visioconférence** avec le directeur financier et plusieurs collègues qu'il reconnaît. Il exécute alors une quinzaine de virements, pour un total d'environ **25 millions de dollars** (200 millions de dollars de Hong Kong). Tous les participants de la visioconférence étaient des **deepfakes** générés par intelligence artificielle à partir d'images et de voix publiques des vrais dirigeants.

**Ce que ce cas illustre :** l'ère du « je l'ai vu/entendu, donc c'est vrai » est terminée. La vérification ne vaut que si c'est **vous** qui initiez le contact, via un canal indépendant (le numéro de téléphone interne connu, pas celui fourni dans le message). C'est la règle d'or de cette session.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Vous êtes comptable. Votre directeur général vous appelle en visio — vous reconnaissez son visage et sa voix — pour vous demander un virement urgent et confidentiel vers un nouveau fournisseur. **Que faites-vous ? Tapez A, B ou C dans le chat :**

    - A) J'exécute le virement : je l'ai vu et entendu, la demande est authentifiée.
    - B) Je raccroche et je le rappelle moi-même sur son numéro interne habituel pour confirmer.
    - C) Je réponds à l'e-mail de convocation de la visio pour demander une confirmation écrite.

    **Débrief mentor :** B. Le cas Arup prouve que A ne suffit plus (deepfake temps réel). C est un piège : si le compte e-mail est compromis ou usurpé, c'est l'attaquant qui « confirmera ». Seul un contact **initié par vous** sur un canal **indépendant** casse le scénario de l'attaquant.

---

### Focus pratique
Savoir identifier les indices visuels d'un e-mail malveillant est une compétence d'autodéfense numérique cruciale.

```text
De : service-clients@netf1ix-securite.com  <-- [Indice A : Domaine suspect (typosquatting)]
À : destinataire@entreprise.fr
Objet : Action requise : Suspension imminente de votre abonnement ! <-- [Indice B : Urgence artificielle]

Cher Client,
Nous n'avons pas pu valider votre dernier prélèvement mensuel. 
Veuillez cliquer immédiatement sur le lien ci-dessous pour mettre à jour vos coordonnées bancaires et éviter la perte de vos services :

👉 [METTRE A JOUR MON COMPTE] <-- [Indice C : Le lien pointe vers http://193.168.1.45/login.php et non netflix.com]

L'équipe Netflix.
```

* **Indice A** : L'adresse de l'expéditeur semble légitime mais contient des fautes discrètes (un '1' au lieu d'un 'l' dans netflix).
* **Indice B** : Un objet et un ton alarmistes incitant à agir sans réfléchir.
* **Indice C** : Le lien de destination réel (visible en survolant le bouton avec la souris sans cliquer) ne correspond pas au site officiel.

Attention toutefois : avec l'IA générative, les fautes d'orthographe et les maladresses disparaissent des messages frauduleux. Les indices de **forme** (A, B) deviennent moins fiables ; les indices de **fond** (C : où mène réellement le lien ? la demande est-elle inhabituelle ?) et la **procédure** de double validation restent, eux, infaillibles.

### Activité — La Chasse au Phishing (Sondages Livestorm n°2 à 5)

**Consignes pour le mentor :** Projetez successivement les quatre messages ci-dessous (reconstitutions anonymisées). Pour chacun, lancez le sondage « **Phishing ou légitime ?** » (options : A) Phishing / B) Légitime / C) Je ne sais pas), laissez voter, puis déroulez l'analyse.

*   **📊 Sondage n°2 — Le SMS de livraison :** « Chronopost : votre colis n°FR7729 est en attente. Frais de douane : 1,95 €. Régularisez sous 24h : `bit.ly/chrn-colis` » → **Phishing (smishing)**. Indices : lien raccourci masquant la destination, micro-paiement servant à capturer la carte bancaire, urgence des 24h, numéro d'expéditeur mobile ordinaire.
*   **📊 Sondage n°3 — L'e-mail Netflix :** le message du Focus pratique ci-dessus → **Phishing**. Indices : typosquatting `netf1ix`, urgence, lien vers une adresse IP.
*   **📊 Sondage n°4 — Le message interne maladroit :** « Bonjour, la maintenance du serveur mail aura lieu vendredi a 18h, merci de sauvegarder vos brouillon. IT » envoyé depuis `support@entreprise.fr` (le vrai domaine), sans lien ni pièce jointe → **Légitime** (mais maladroit). Indices : domaine authentique, aucune action sensible demandée, aucune urgence manipulatoire. Leçon : des fautes ne suffisent pas à condamner un message — c'est la **demande** qui compte.
*   **📊 Sondage n°5 — Le spear-phishing du DAF :** « Bonjour Julie, comme évoqué en réunion budget ce matin, merci de traiter la facture jointe du cabinet Deloitte avant midi — le RIB a changé, utilise celui du PDF. Bien à toi, Marc » → **Phishing (spear-phishing / BEC)**. Indices : changement de RIB (signal d'alarme absolu), pression temporelle, personnalisation troublante (issue de la reconnaissance OSINT — réunion mentionnée sur LinkedIn), demande financière par simple e-mail.

**Éléments de débriefing (pour le mentor) :**

- Score attendu : les sondages n°2 et n°3 sont faciles ; le n°4 piège ceux qui croient que « fautes = fraude » ; le n°5 piège presque tout le monde — c'est voulu, c'est la démonstration que la personnalisation désarme la vigilance.
- Règle à marteler : **tout changement de RIB ou demande de virement se vérifie par un canal alternatif initié par vous** — sans exception, même si le message est parfait.

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Pour comprendre la manipulation psychologique en cybersécurité, imaginez l'analogie d'un **imposteur habillé en agent du gaz** :
    - L'imposteur ne force pas la serrure (pas de faille technique). Il frappe à la porte, montre un faux badge, et utilise l'urgence ("fuite détectée dans la rue") pour que vous le laissiez entrer de votre plein gré.
    - Le **Phishing** est un e-mail envoyé à 1000 personnes en espérant qu'une seule laisse entrer l'imposteur.
    - Le **Spear-phishing** est un e-mail hautement personnalisé où l'imposteur connaît votre nom, le nom de votre chien, et prétend être envoyé par votre syndic de copropriété.
    - Le **Deepfake** est l'imposteur qui porte désormais un masque parfait du visage de votre voisin.

**Exemple d'application professionnelle :**
Dans une start-up, un comptable reçoit un SMS urgent (Smishing) prétendument de la banque, lui demandant de cliquer sur un lien pour annuler un débit frauduleux de 15 000 €. En panique (levier d'urgence), il clique et saisit ses codes d'accès. Grâce à la formation à la vigilance, il réalise son erreur 2 minutes après et appelle le service de sécurité informatique qui désactive immédiatement le compte avant que le pirate n'initie de virement. Moralité : la vigilance n'empêche pas toujours le clic, mais elle sauve la situation si le **réflexe de signalement immédiat** est acquis — signaler vite n'est jamais une faute, c'est un acte de défense.

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour lutter contre l'ingénierie sociale et sécuriser la messagerie d'entreprise (principal vecteur d'attaque), voici les outils recommandés :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **KnowBe4 Security Awareness Training** : Leader incontesté pour la formation à la sensibilisation des employés et les simulations d'hameçonnage automatisées.
    *   **Proofpoint Security Awareness / SEG (Secure Email Gateway)** : Solution haut de gamme de filtrage de messagerie et de sensibilisation des collaborateurs, réputée pour bloquer le Business Email Compromise (BEC).
    *   **SoSafe** : Plateforme européenne (conforme RGPD) de sensibilisation au phishing basée sur la gamification et la psychologie comportementale.
    *   **Mimecast Email Security** : Passerelle de messagerie cloud-native offrant une protection avancée contre le phishing ciblé, les malwares et le vol d'identifiants.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **GoPhish** : Le framework open-source de simulation de phishing le plus populaire. Il permet aux administrateurs réseau de concevoir et lancer leurs propres campagnes de tests internes pour mesurer la vigilance des équipes.
    *   **Phishing-Initiative** : Projet citoyen et collaboratif (soutenu par l'ANSSI) permettant de signaler les adresses de phishing pour qu'elles soient bloquées dans les navigateurs du monde entier.

### Mise en situation BEC (Sondages Livestorm n°6 et 7)

**Consignes pour le mentor :** À dérouler juste après les études de cas — le scénario en est l'application directe.

*   **📊 Sondage n°6 :** Un employé reçoit un e-mail pressant "de la direction" lui demandant d'acheter des cartes cadeaux d'urgence. De quel type d'attaque s'agit-il ?
    *   A) Ransomware
    *   B) Hameçonnage ciblé / Arnaque au président (Spear-phishing / BEC) ✅
    *   C) Attaque par déni de service (DDoS)
    *   D) Logiciel espion (Spyware)
*   **📊 Sondage n°7 :** Quelle est l'action la plus sûre que l'employé doit faire à ce stade ?
    *   A) Répondre à l'e-mail pour demander des clarifications.
    *   B) Acheter les cartes et envoyer les codes pour ne pas mécontenter la direction.
    *   C) Contacter la direction par un canal alternatif (téléphone, en personne) pour vérifier l'authenticité ✅
    *   D) Transférer l'e-mail à tous ses collègues pour les prévenir.

**Éléments de débriefing (pour le mentor) :**

- Le canal de messagerie d'origine ne doit jamais être utilisé pour confirmer une demande suspecte (l'attaquant peut avoir compromis le compte) — c'est le piège dans lequel l'employé d'Arup a failli ne pas tomber... avant que le deepfake ne l'y précipite.
- L'utilisation d'un canal alternatif **initié par soi-même** est la règle d'or de la double validation.
- Sur l'option D : prévenir les collègues est une bonne intention, mais le bon circuit est le signalement au service informatique/sécurité, qui alertera officiellement (et évitera 50 réponses paniquées au faux e-mail).

### Quiz de validation (Sondages Livestorm n°8 à 10)

**Consignes pour le mentor :** À lancer en fin de session pour ancrer les notions non couvertes par la Chasse au phishing.

*   **📊 Sondage n°8 :** Quel malware est caractérisé par sa capacité à se propager tout seul, sans action humaine ?
    *   A) Le virus
    *   B) Le ver ✅
    *   C) Le keylogger
    *   D) Le cheval de Troie
*   **📊 Sondage n°9 :** Dans la Cyber Kill Chain, l'envoi de l'e-mail piégé à la victime correspond à l'étape...
    *   A) Reconnaissance
    *   B) Armement
    *   C) Livraison ✅
    *   D) Exploitation
*   **📊 Sondage n°10 :** Quel levier psychologique vise à court-circuiter votre réflexion en vous pressant d'agir ?
    *   A) La politesse
    *   B) L'urgence ✅
    *   C) La curiosité
    *   D) La confiance

**Éléments de débriefing (pour le mentor) :**

- N°8 : le ver s'auto-propage via les failles ; le virus a besoin d'un fichier hôte exécuté ; rappel WannaCry (A1).
- N°9 : re-balayer la chaîne en 30 secondes ; insister sur « brisez un maillon, brisez l'attaque ».
- N°10 : l'urgence est le levier commun à quasi tous les cas vus aujourd'hui (Netflix, cartes cadeaux, Pathé) — c'est LE signal d'alarme n°1.

### Questions de réflexion

1. Dans l'affaire Pathé, les procédures de validation existaient probablement sur le papier. Pourquoi n'ont-elles pas fonctionné ? Que faudrait-il changer pour qu'une procédure résiste au levier d'autorité ?
2. Avec les deepfakes, « voir et entendre » ne prouve plus l'identité. Quels canaux de vérification restent fiables dans votre organisation, et pourquoi ?
3. Un collègue vient de cliquer sur un lien de phishing et vous l'avoue, honteux. Que lui dites-vous, et que fait-on dans les 10 minutes qui suivent ? En quoi la culture du blâme aggrave-t-elle le risque ?
4. Pourquoi le phishing de masse continue-t-il d'exister alors que ses indices sont connus de tous ?

## 3. Ressources complémentaires

* **IBM SkillsBuild** : Cours sur l'ingénierie sociale et la sensibilisation au phishing.
* **[Cybermalveillance.gouv.fr — Fiche réflexe Hameçonnage](https://www.cybermalveillance.gouv.fr/tous-nos-contenus/fiches-reflexes/hameconnage-phishing)** : la référence française pour réagir à un hameçonnage (particuliers et professionnels).
* **[CNIL — Signaler un phishing](https://www.cnil.fr/fr/spam-phishing-arnaques-signaler-pour-agir)** : signalement et conseils.
* **MITRE ATT&CK Framework** : Base de connaissances mondiale sur les tactiques et techniques réelles des attaquants (consulter la matrice simplifiée).
* **33700 / Signal Spam** : le numéro national de signalement des SMS frauduleux (transférez le smishing au 33700) et la plateforme de signalement des e-mails indésirables.

## 4. Exercice bonus (Sondage de Vigilance - Livestorm)

*   **Objectif :** Détection de signaux faibles d'hameçonnage.
*   **📊 Sondage Livestorm n°11 :** Vous recevez un e-mail d'un fournisseur habituel contenant une facture. Quelle anomalie doit vous alerter en premier ?
    *   A) Le montant de la facture est élevé.
    *   B) L'adresse de l'expéditeur a un domaine légèrement modifié (ex. `support@st0rmshield.fr` au lieu de `stormshield.fr`) ✅
    *   C) L'e-mail a été envoyé à 14h.
*   **Guide d'animation (pour le mentor) :** Montrez l'importance du typosquatting (changement de caractères subtils comme un zéro au lieu d'un 'o') comme vecteur classique pour tromper les utilisateurs. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Backdoor (Porte dérobée)** | Accès caché permettant à un attaquant de revenir à volonté en contournant les authentifications. |
| **BEC (Business Email Compromise)** | Fraude par compromission de la messagerie professionnelle, où un pirate usurpe l'identité d'un dirigeant ou d'un fournisseur pour ordonner des virements frauduleux. |
| **Cyber Kill Chain** | Cadre conceptuel décrivant les 7 étapes chronologiques d'une cyberattaque réussie, développé par Lockheed Martin. |
| **Deepfake (Hypertrucage)** | Contenu audio/vidéo falsifié par IA, imitant de manière réaliste la voix ou le visage d'une personne réelle. |
| **Ingénierie sociale (Social Engineering)** | Manipulation psychologique visant à extorquer des informations confidentielles ou à faire accomplir des actions dangereuses à une victime. |
| **Malware (Logiciel malveillant)** | Terme générique désignant tout programme conçu pour nuire à un système informatique (virus, ver, rançongiciel, etc.). |
| **Phishing (Hameçonnage)** | Technique frauduleuse par e-mail visant à tromper le destinataire pour lui soutirer des informations confidentielles en usurpant l'identité d'une marque de confiance. |
| **Ransomware (Rançongiciel)** | Malware qui chiffre les fichiers d'un utilisateur ou d'une entreprise et réclame le paiement d'une rançon en échange de la clé de déchiffrement. |
| **Smishing** | Attaque d'ingénierie sociale réalisée par SMS pour pousser la victime à visiter un site malveillant ou à divulguer des données. |
| **Spear-phishing (Hameçonnage ciblé)** | Variante hautement personnalisée du phishing, ciblant un individu ou une organisation spécifique en exploitant des détails personnels collectés à l'avance. |
| **Typosquatting** | Domaine imitant une marque à une lettre près (`netf1ix.com`) pour tromper l'œil. |
| **Vishing (Hameçonnage vocal)** | Technique de manipulation par téléphone où l'attaquant usurpe l'identité d'un tiers de confiance pour extorquer des informations. |

**La règle d'or de la session :** toute demande sensible (virement, RIB, code, mot de passe) se vérifie par un **canal alternatif que VOUS initiez** — quels que soient le réalisme et l'urgence de la demande.
