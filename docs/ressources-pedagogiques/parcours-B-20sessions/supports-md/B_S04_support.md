# Session B04 — Ingénierie sociale & facteur humain
Parcours : B 20 sessions  |  Module : A — Fondations  |  Niveau : Débutant  |  Format : Webinaire Livestorm (1h30)

---

!!! abstract "Résumé"
    Ce document synthétise les concepts essentiels de la session. Vous y découvrirez notamment :
    - La psychologie de la manipulation (Ingénierie sociale)
    - Canaux et vecteurs d'attaque (phishing, smishing, vishing, BEC)
    - Deux affaires réelles : la fraude au président chez Pathé (2018) et le deepfake Arup (2024)
    - L'hygiène numérique d'entreprise et la culture du signalement
    L'objectif est de vous fournir les bases théoriques et pratiques nécessaires pour maîtriser ces notions.

---

## 1. Introduction

*   L'ingénierie sociale repose sur l'exploitation de faiblesses psychologiques (urgence, peur, autorité) et non sur des failles logicielles.
*   Les attaques se déclinent sur tous les canaux : e-mail (phishing), SMS (smishing), téléphone (vishing) — et jusqu'à la visioconférence truquée par intelligence artificielle (deepfake).
*   L'hameçonnage ciblé (spear-phishing) et la fraude au président (BEC) utilisent des informations publiques et personnelles pour piéger précisément leur victime — sans le moindre malware.
*   L'hygiène cyber (mots de passe forts, MFA, verrouillage, doute systématique et culture du signalement) est le premier bouclier de l'entreprise.

### Objectifs de la session
À la fin de cette session, vous serez capable de :

* Décoder les 5 principaux leviers psychologiques (urgence, autorité, sympathie, peur, preuve sociale) exploités par les attaquants lors d'une manipulation.
* Distinguer techniquement et fonctionnellement les différents vecteurs d'ingénierie sociale : *Phishing* (email), *Spear-phishing* (ciblé), *Smishing* (SMS), *Vishing* (téléphone) et la fraude au président (BEC).
* Rédiger et structurer des règles d'hygiène numérique simples et applicables pour sensibiliser efficacement des collaborateurs en entreprise.

!!! tip "📊 Sondage Livestorm n°1 — Brise-glace (à lancer en tout début de session)"
    **Question :** Selon le rapport Verizon DBIR 2024, combien de temps s'écoule en médiane entre l'ouverture d'un e-mail de phishing et la saisie des identifiants par la victime ?

    - A) Moins d'une minute ✅
    - B) Environ un quart d'heure
    - C) Plus d'une heure

    **Débrief mentor :** Réponse A : **moins de 60 secondes** en médiane — environ 21 secondes pour cliquer sur le lien, 28 de plus pour saisir ses identifiants (Verizon DBIR 2024). La manipulation est conçue précisément pour court-circuiter la réflexion : quand on agit dans la minute, on n'a pas vérifié. Toute cette session vise une seule chose : installer le réflexe qui fait GAGNER une minute — celle qui suffit à déjouer la quasi-totalité de ces attaques.

---

## 2. Développement

### Approfondissement technique pour le mentor (Contenu dense)

**1. Le BEC, l'attaque la plus chère du monde**
Consacrez du temps à la **fraude au président / BEC (Business Email Compromise)** : l'attaquant usurpe (domaine ressemblant, affichage falsifié) ou compromet réellement la boîte e-mail d'un dirigeant ou d'un fournisseur, étudie le style d'écriture et le calendrier (fusions, audits, congés), puis ordonne un virement « confidentiel et urgent » — classiquement le vendredi après-midi, pour gagner le week-end avant la découverte. Aucun malware : les passerelles antivirus ne voient rien. La parade est **procédurale** : double validation hors canal (contre-appel au numéro connu), séparation des pouvoirs sur les virements, délai obligatoire pour tout changement de RIB.

**2. L'IA industrialise la manipulation**
Les leviers psychologiques ne changent pas, mais l'IA change l'échelle et le réalisme : e-mails de phishing sans fautes rédigés par IA générative, **clonage de voix** à partir de quelques secondes d'audio public (le « vishing 2.0 »), et **deepfakes vidéo** en visioconférence — le cas Arup (détaillé plus bas) en est la démonstration à 25 millions de dollars. Message : « je reconnais sa voix / son visage » n'est plus une preuve d'identité ; seule une vérification par un canal séparé l'est.

**3. Les leviers viennent de la psychologie sociale**
Pour les curieux : les leviers présentés dérivent des principes d'influence formalisés par le psychologue Robert Cialdini (autorité, rareté/urgence, sympathie, réciprocité, preuve sociale, cohérence). Les attaquants n'ont rien inventé — ils appliquent la même boîte à outils que le marketing, à des fins criminelles. C'est aussi pour cela que la sensibilisation fonctionne : les leviers sont connus, identifiables et enseignables.

---

### Glossaire

*   **Baiting (Appâtage)** — Technique consistant à laisser un support piégé (clé USB « Salaires 2026 » sur un parking) en pariant sur la curiosité de la victime.
*   **BEC (Business Email Compromise)** — Fraude au président consistant à pirater ou usurper la boîte e-mail d'un dirigeant ou d'un fournisseur pour ordonner des transactions financières frauduleuses.
*   **Deepfake (Hypertrucage)** — Contenu audio ou vidéo falsifié par intelligence artificielle, imitant de façon réaliste la voix ou le visage d'une personne réelle.
*   **OSINT (Open Source Intelligence)** — Renseignement en sources ouvertes (terme officiel français : « renseignement d'origine sources ouvertes », ROSO) : collecte légale d'informations publiques (réseaux sociaux, site web, presse) servant notamment à préparer les attaques ciblées.
*   **Phishing (Hameçonnage)** — Envoi massif d'e-mails frauduleux usurpant l'identité de tiers de confiance pour voler des informations sensibles ou propager un malware.
*   **Smishing** — Hameçonnage réalisé par le biais de messages textes (SMS).
*   **Spear-phishing (Hameçonnage ciblé)** — Variante d'hameçonnage hautement personnalisée visant un individu ou une organisation spécifique à l'aide d'informations préalablement collectées.
*   **Typosquatting** — Enregistrement d'un nom de domaine imitant un domaine légitime à un caractère près (`st0rmshield.fr` pour `stormshield.fr`) afin de tromper l'œil.
*   **Vishing (Hameçonnage vocal)** — Technique d'ingénierie sociale par téléphone visant à extorquer des informations confidentielles (y compris des codes de double authentification).

---

### Concepts clés

!!! info "À retenir"
    L'ingénierie sociale n'attaque pas la machine : elle attaque la **décision humaine**, en fabriquant un contexte (urgence, autorité, confiance) où la victime contourne elle-même les règles de sécurité. La parade n'est donc pas un logiciel : c'est un **réflexe de vérification** par un canal séparé.

### 1. La psychologie de la manipulation (Ingénierie sociale)
L'ingénierie sociale (*Social Engineering*) regroupe l'ensemble des techniques de manipulation psychologique visant à inciter une personne à contourner les règles de sécurité ou à divulguer des informations confidentielles. Les pirates ciblent les failles cognitives humaines plutôt que les failles logicielles. Ils exploitent des leviers psychologiques précis :

*   **L'autorité** : Se faire passer pour une figure hiérarchique supérieure (le directeur général, un avocat de l'entreprise, un policier). La victime obéit par respect ou crainte de la hiérarchie.
    *   *Exemple* : L'arnaque au président, où un comptable reçoit l'ordre direct (présumé) du PDG d'effectuer un virement confidentiel et urgent pour un rachat d'entreprise.
*   **L'urgence** : Créer un sentiment de panique temporelle pour empêcher la victime de réfléchir rationnellement ou de vérifier l'information.
    *   *Exemple* : "Votre compte bancaire va être suspendu dans 2 heures si vous ne validez pas ce lien."
*   **La sympathie ou la réciprocité** : Instaurer une relation cordiale ou feindre de rendre service pour endormir la méfiance.
    *   *Exemple* : Un faux support technique qui appelle pour aider à résoudre un "problème réseau détecté" sur votre poste.
*   **La peur ou l'intimidation** : Utiliser la menace pour forcer l'action.
    *   *Exemple* : "Si vous ne payez pas l'amende pour téléchargement illégal immédiatement, des poursuites judiciaires seront engagées."
*   **La preuve sociale** : Faire croire que tout le monde réalise déjà l'action demandée pour rassurer la victime.
    *   *Exemple* : "Tous vos collègues ont déjà signé cette nouvelle charte RH en ligne, veuillez cliquer ici pour faire de même."

Ces leviers se **combinent** : un bon scénario d'attaque en superpose deux ou trois (l'autorité du PDG + l'urgence du délai + la flatterie du « je compte sur votre discrétion »).

### Activité — Décodez le levier (Sondages Livestorm n°2 à 4)

**Consignes pour le mentor :** Affichez chaque message piégé, lisez-le à voix haute avec le ton approprié, puis lancez le sondage : quel est le levier psychologique **dominant** ? Débriefez après chaque vote (levier principal, leviers secondaires, canal utilisé).

*   **📊 Sondage n°2 — Le message :** *« Maître Durand, avocat de votre PDG. Il vous demande personnellement de traiter un virement strictement confidentiel avant 16h — dossier sous accord de confidentialité, n'en parlez à personne. »* Levier dominant ?
    *   A) L'autorité (renforcée par l'urgence et le secret) ✅
    *   B) La preuve sociale
    *   C) La sympathie
*   **📊 Sondage n°3 — Le SMS :** *« Votre colis est bloqué au centre de tri. Réglez 1,95 € de frais de douane sous 24h ou il sera retourné à l'expéditeur : lien-suivi-colis.net »* Levier dominant ?
    *   A) La peur ou l'intimidation
    *   B) L'urgence (facilitée par un montant dérisoire qui endort la méfiance) ✅
    *   C) L'autorité
*   **📊 Sondage n°4 — L'appel :** *« Bonjour, c'est Julien du support informatique ! J'ai vu que votre poste ramait ce matin, je vous appelle pour vous aider. J'ai juste besoin de votre identifiant et du code qui va s'afficher sur votre téléphone. »* Levier dominant ?
    *   A) La peur ou l'intimidation
    *   B) La preuve sociale
    *   C) La sympathie / réciprocité (il « rend service »... et récupère votre code MFA) ✅

**Éléments de débriefing (pour le mentor) :**

- N°2 : le trio classique du **BEC** — autorité + urgence + injonction au secret. Le secret est le signal d'alarme n°1 : une procédure légitime n'interdit jamais de vérifier. Canal : e-mail ou téléphone.
- N°3 : le **smishing** type (fausse amende, faux colis). Le montant dérisoire est le génie du piège : qui se méfie pour 1,95 € ? Or l'objectif n'est pas 1,95 € — c'est votre numéro de carte complet.
- N°4 : le **vishing** serviable. Remarquez la demande finale : le « code qui s'affiche sur votre téléphone » est votre code MFA — celui qui valide la connexion que l'attaquant est en train de faire à votre place. Règle absolue : ce code ne se communique JAMAIS oralement, à personne.

### 2. Canaux et vecteurs d'attaque
L'ingénierie sociale emprunte différents canaux technologiques et de communication :

*   **Le Phishing (Hameçonnage)** : Envoi d'un email massif et impersonnel imitant un tiers de confiance (banque, impôts, service de livraison) pour collecter des identifiants ou propager un malware.
*   **Le Spear-phishing (Hameçonnage ciblé)** : Attaque hautement personnalisée visant une personne précise. L'attaquant utilise des informations glanées au préalable (sur les réseaux sociaux professionnels, le site de l'entreprise — c'est l'**OSINT**) pour rendre l'email extrêmement crédible.
*   **Le Smishing (SMS phishing)** : Hameçonnage par SMS. Le message contient généralement un lien raccourci vers une fausse interface mobile (ex. fausse amende de stationnement ANTAI, colis bloqué).
*   **Le Vishing (Voice phishing)** : Hameçonnage vocal par téléphone. L'attaquant appelle la victime en usurpant l'identité d'un conseiller bancaire, d'un technicien informatique ou d'un auditeur de sécurité pour lui extorquer des codes de double authentification (MFA).
*   **Le Baiting (Appâtage)** : Un support piégé laissé en évidence — la clé USB « Salaires 2026 » sur le parking — qui parie sur la curiosité.
*   **La fraude au président (BEC)** : L'aboutissement de tous les précédents — usurpation ou compromission de la messagerie d'un dirigeant ou d'un fournisseur pour ordonner des virements. Les deux affaires réelles ci-dessous en montrent l'ampleur.

!!! question "💬 Question chat — La chasse aux indices"
    Affichez cet e-mail à l'écran et demandez : « **Tapez dans le chat tous les indices qui trahissent le faux.** »

    > De : Service Comptabilité `<compta@votre-entreprise-fr.net>`
    > Objet : URGENT — Facture impayée, régularisation sous 24h
    > « Bonjour, suite à un incident technique, merci de régulariser la facture jointe avant demain 17h afin d'éviter des pénalités. Règlement sécurisé ici : `paiement-securise-fr.net/facture`. Cordialement, Le Service Comptabilité. »

    **Débrief mentor (indices attendus) :** le domaine expéditeur modifié (`votre-entreprise-fr.net` au lieu du vrai domaine — typosquatting), l'urgence artificielle (24h, pénalités), le lien vers un domaine tiers sans rapport, la formulation impersonnelle (« Bonjour » sans nom), le prétexte vague (« incident technique »). Conclure : aucun indice ne demande de compétence technique — juste une minute d'attention.

### 3. Le paysage en chiffres

!!! info "Chiffres clés à retenir (sources et années citées)"
    - **Moins de 60 secondes** : le temps médian entre l'ouverture d'un e-mail de phishing et la saisie des identifiants (Verizon DBIR 2024).
    - **Environ 2,8 milliards de dollars** de pertes déclarées pour la seule fraude BEC en 2024 aux États-Unis (rapport IC3 du FBI) — l'une des catégories les plus coûteuses de la cybercriminalité.
    - **L'hameçonnage reste la menace n°1** signalée par les particuliers en France (rapport d'activité Cybermalveillance.gouv.fr 2024).
    - **Plus de 99,9 %** des attaques automatisées sur les comptes sont bloquées par la simple activation de la double authentification (étude Microsoft, 2019).

**Comment lire ces chiffres ?** (1) La victime tombe en secondes : la défense doit être un réflexe, pas une réflexion. (2) Le BEC coûte des milliards sans un seul malware : la procédure de contre-vérification vaut tous les antivirus. (3) La MFA est la mesure au meilleur rapport effort/protection qui existe — mais le vishing (sondage n°4) montre qu'elle se protège aussi.

### 4. Deux affaires réelles : le vendredi soir de Pathé et la visio fantôme d'Arup

#### Cas n°1 — Pathé (2018) : 19 millions d'euros sans un seul malware

En mars 2018, les deux dirigeants de la filiale **néerlandaise du groupe de cinéma français Pathé** reçoivent des e-mails semblant provenir du siège parisien : une acquisition confidentielle à Dubaï se prépare, il faut effectuer des virements urgents et discrets. Le domaine d'expédition ressemble au vrai, le ton est crédible, le contexte plausible. En **environ un mois**, une succession de virements part vers des comptes étrangers : **plus de 19 millions d'euros** au total. Aucun système n'a été piraté, aucun malware utilisé — uniquement des e-mails et la mécanique autorité + urgence + secret. Les deux dirigeants, pourtant victimes d'une manipulation professionnelle, ont été licenciés.

**Ce que ce cas illustre :** le BEC ne cible pas les naïfs — il cible des cadres expérimentés avec un scénario cohérent ; l'injonction au **secret** neutralise le meilleur antidote (en parler autour de soi) ; et la parade était purement procédurale : un seul contre-appel au siège, sur un numéro connu, aurait tout arrêté.

#### Cas n°2 — Arup (2024) : la visioconférence où tout le monde était faux

Début 2024 à Hong Kong, un employé du service financier du cabinet d'ingénierie britannique **Arup** reçoit un e-mail suspect du « directeur financier » demandant des virements confidentiels. Méfiant, il demande une visioconférence — et l'obtient : à l'écran, le directeur financier et plusieurs collègues qu'il reconnaît. Rassuré, il exécute une quinzaine de virements pour un total d'environ **25 millions de dollars**. La réunion était un **deepfake** : chaque visage et chaque voix à l'écran avaient été générés par intelligence artificielle à partir d'enregistrements publics.

**Ce que ce cas illustre :** la victime a eu le bon réflexe (vérifier) mais sur le **même canal** que l'attaque — or une visio truquée « confirme » une demande truquée ; à l'ère des deepfakes, reconnaître un visage ou une voix ne prouve plus rien ; la vérification doit passer par un canal **indépendant** (rappeler soi-même un numéro connu, vérifier en personne, procédure interne à deux personnes).

!!! tip "📊 Sondage Livestorm n°5 — Et chez vous ? (sondage d'opinion, pas de bonne réponse)"
    **Question :** Dans votre organisation, existe-t-il une procédure formalisée de contre-vérification pour les demandes de virement ou de changement de RIB (contre-appel, double validation) ?

    - A) Oui, formalisée et appliquée
    - B) Il existe des habitudes informelles, mais rien d'écrit
    - C) Non / Je ne sais pas

    **Débrief mentor :** Sondage d'opinion — pas de bonne réponse, mais un diagnostic. Pathé et Arup montrent que la vigilance individuelle ne suffit pas face à un scénario professionnel : il faut une **procédure** qui tienne même quand l'humain est convaincu (double validation systématique au-dessus d'un seuil, contre-appel obligatoire sur numéro connu, aucun traitement d'un changement de RIB reçu par e-mail sans vérification). Les réponses B et C sont un excellent point de départ pour la fiche d'hygiène de fin de session.

!!! question "🤔 Mini-scénario — Que feriez-vous si... ?"
    Vous travaillez en comptabilité. Un fournisseur régulier vous envoie un e-mail : « Suite à un changement bancaire, merci d'utiliser ce nouveau RIB pour la facture du mois (en pièce jointe). » L'e-mail vient de la bonne adresse, la facture est authentique. **Tapez A, B ou C dans le chat :**

    - A) Mettre à jour le RIB : l'adresse est la bonne et la facture est exacte.
    - B) Rappeler le fournisseur au numéro habituel (pas celui de l'e-mail) pour confirmer de vive voix avant tout changement. ✅
    - C) Répondre à l'e-mail pour demander confirmation écrite.

    **Débrief mentor :** B — le contre-appel sur un canal indépendant. A tombe dans le piège : une boîte e-mail de fournisseur compromise envoie de « vrais » e-mails depuis la vraie adresse, avec les vraies factures... et un faux RIB. C est le piège subtil : si la boîte est compromise, c'est **l'attaquant qui répondra** « oui, tout est bon ». C'est l'arnaque au faux RIB, l'une des fraudes les plus courantes visant les PME françaises.

### 5. L'hygiène numérique d'entreprise
La sécurité humaine repose sur des réflexes simples mais rigoureux, que l'on qualifie d'**hygiène numérique** (*cyber hygiene*). Elle comprend :

*   **La gestion des mots de passe** : Utiliser des mots de passe longs (au moins 12 à 15 caractères), uniques pour chaque service, et stockés dans un gestionnaire de mots de passe sécurisé.
*   **Le Double Facteur (MFA — *Multi-Factor Authentication*)** : Activer systématiquement la double validation (application d'authentification de préférence) pour toutes les connexions — la mesure qui bloque à elle seule plus de 99,9 % des attaques automatisées (Microsoft, 2019). Et retenir sa règle d'or : un code MFA ne se communique jamais, ni par téléphone, ni par SMS, à personne.
*   **La culture de la vérification** : Mettre en place des procédures de double validation hors canal (ex. rappeler un fournisseur sur son numéro officiel connu en cas de changement de RIB reçu par email).
*   **La culture du signalement** : Faire du signalement rapide un réflexe valorisé — chaque minute gagnée entre le clic malheureux et l'alerte réduit la propagation.

> 💡 **Bon à savoir : L'erreur humaine n'est pas une fatalité**
> Punir ou humilier un employé qui s'est fait piéger par une simulation de phishing est contre-productif. Les meilleures politiques de sensibilisation valorisent le signalement rapide de l'erreur au département de sécurité afin de circonscrire l'incident au plus vite. Une victime qui signale en 5 minutes vaut mieux qu'un « bon élève » qui se tait pendant 3 jours.

### Boîte à outils — Exemple de kit d'onboarding « 5 réflexes de sécurité »

Modèle de fiche mémo, positive et sans jargon, à remettre aux nouveaux salariés d'une PME (à adapter en autonomie à votre propre organisation — c'est l'exercice de la semaine) :

#### Bienvenue chez EcoLog ! Vos 5 réflexes de sécurité au quotidien

1.  **Vos clés d'accès : Longues et uniques !**
    *   *Le comportement* : Utilisez des phrases de passe (mots de passe de plus de 12 caractères faciles à retenir) et stockez-les dans le gestionnaire de mots de passe de l'entreprise. Ne réutilisez jamais votre mot de passe professionnel sur un site personnel (loisirs, e-commerce).
    *   *Le risque évité* : Le piratage en cascade de tous vos comptes si l'un d'eux venait à fuiter sur Internet.
2.  **La double clé (MFA) : Activée partout !**
    *   *Le comportement* : Configurez l'application d'authentification sur votre téléphone professionnel pour valider vos accès à la messagerie et aux outils cloud. Ne communiquez jamais un code de validation, à personne.
    *   *Le risque évité* : Même si un attaquant devine ou vole votre mot de passe, il ne pourra pas se connecter à votre compte sans le code de votre téléphone.
3.  **Au bureau comme en déplacement : Verrouillez !**
    *   *Le comportement* : Prenez le réflexe de verrouiller votre session (touche `Windows + L` ou `Cmd + Ctrl + Q` sur Mac) dès que vous quittez votre bureau, même pour une minute.
    *   *Le risque évité* : La consultation ou modification de données sensibles par une personne de passage ou un prestataire externe.
4.  **Emails et SMS : Doutez d'abord !**
    *   *Le comportement* : Si un message vous demande une action urgente, suspecte (changement de RIB, mot de passe à renouveler) ou inhabituelle, ne cliquez sur aucun lien. Contactez l'expéditeur via son numéro de téléphone habituel pour vérifier.
    *   *Le risque évité* : Le vol d'identifiants ou l'installation d'un rançongiciel sur le réseau de l'entreprise.
5.  **En cas d'erreur : Alertez immédiatement !**
    *   *Le comportement* : Vous avez cliqué sur un lien suspect ou saisi vos identifiants sur une page douteuse ? Ne paniquez pas et prévenez tout de suite le support informatique. Aucun blâme ne vous sera fait.
    *   *Le risque évité* : Permettre à une infection de se propager en silence sur l'ensemble des serveurs de l'entreprise pendant des heures.

---

### Questions de réflexion
1. Pourquoi le Spear-phishing (hameçonnage ciblé) a-t-il un taux de réussite beaucoup plus élevé que le phishing de masse ? Quelles traces publiques un attaquant recherche-t-il sur LinkedIn pour monter son scénario ?
2. Face à un appel téléphonique d'un interlocuteur affirmant être de votre banque et vous demandant de "valider des transactions de test" sur votre application mobile pour annuler une fraude en cours (Vishing), quelle est la seule réaction sécurisée ?
3. Dans l'affaire Arup, l'employé a VÉRIFIÉ avant d'agir — et s'est quand même fait piéger. Qu'est-ce qui a rendu sa vérification inefficace, et comment aurait-elle dû être menée ?

**Corrigé / Éléments de réponse :**

1. Le spear-phishing utilise des éléments personnalisés (collègues, projets, organigramme) trouvés sur LinkedIn, ce qui rend le message très crédible et baisse la garde de la cible. L'attaquant y cherche : les fonctions (qui peut payer ?), les liens hiérarchiques (qui obéit à qui ?), les absences annoncées et les projets en cours (le prétexte).
2. Raccrocher, chercher le vrai numéro de sa banque et la rappeler soi-même pour vérifier la réalité de l'alerte. Jamais de « transaction de test » : valider dans l'application, c'est autoriser un vrai paiement.
3. Sa vérification a utilisé le **même canal** que l'attaque (la visioconférence proposée dans l'échange suspect) — un canal que l'attaquant contrôlait. Une vérification efficace passe par un canal indépendant : rappeler le directeur financier à son numéro interne connu, ou appliquer la procédure de double validation.

---

### Cas d'usages et exemples concrets

!!! info "Explication simplifiée"
    Pour comprendre la psychologie de l'ingénierie sociale, imaginez un **usurpateur d'identité** :
    - L'usurpateur ne cherche pas à défoncer la porte blindée de votre maison. Il s'habille en électricien et tient un bloc-notes à la main.
    - Il utilise la **sympathie** ("Bonjour, je viens faire la révision annuelle, cela ne prendra que 5 minutes") pour que vous baissiez votre garde.
    - Il utilise **l'autorité** ("C'est obligatoire, le syndic de l'immeuble m'a envoyé en urgence") pour vous dissuader de lui poser des questions ou de vérifier ses affirmations.
    - Il profite de votre confiance pour dérober vos clés de maison restées sur la table.

**Exemple d'application professionnelle :**
Dans une grande entreprise, un pirate appelle la réceptionniste du standard téléphonique (Vishing). Se faisant passer pour le directeur technique bloqué à l'aéroport avant un conseil d'administration urgent (combinaison d'autorité et d'urgence), il lui demande de lui générer un mot de passe temporaire pour accéder à sa messagerie. La réceptionniste, formée à cette menace, refuse poliment et applique la procédure de sécurité en rappelant le directeur technique sur son numéro officiel.

### Panorama des solutions du marché (Commerciales & Open-Source)

Pour lutter contre l'ingénierie sociale et sensibiliser les employés (facteur humain), les outils suivants se détachent :

*   **Solutions Leaders du Marché (Propriétaires / Payantes) :**
    *   **KnowBe4 Security Awareness Training** : Leader incontesté pour la formation à la sensibilisation des employés et les simulations d'hameçonnage automatisées.
    *   **Proofpoint Security Awareness / SEG (Secure Email Gateway)** : Solution haut de gamme de filtrage de messagerie et de sensibilisation des collaborateurs, réputée pour bloquer le Business Email Compromise (BEC).
    *   **SoSafe** : Plateforme européenne (conforme RGPD) de sensibilisation au phishing basée sur la gamification et la psychologie comportementale.
    *   **Mimecast Email Security** : Passerelle de messagerie cloud-native offrant une protection avancée contre le phishing ciblé, les malwares et le vol d'identifiants.
*   **Alternatives Open-Source et Gratuites (Idéal PME) :**
    *   **GoPhish** : Le framework open-source de simulation de phishing le plus populaire. Il permet aux administrateurs réseau de concevoir et lancer leurs propres campagnes de tests internes pour mesurer la vigilance des équipes.
    *   **Phishing-Initiative** : Projet citoyen et collaboratif (soutenu par l'ANSSI) permettant de signaler les adresses de phishing pour qu'elles soient bloquées dans les navigateurs du monde entier.

### Quiz de validation (Sondages Livestorm n°6 à 8)

**Consignes pour le mentor :** À lancer en fin de session, après la séquence sur l'hygiène numérique.

*   **📊 Sondage n°6 :** Quelle est la différence essentielle entre le phishing et le spear-phishing ?
    *   A) Le phishing est massif et impersonnel ; le spear-phishing est ciblé et personnalisé grâce à des informations collectées ✅
    *   B) Le phishing passe par e-mail, le spear-phishing uniquement par téléphone
    *   C) Le spear-phishing ne vise que les dirigeants d'entreprise
*   **📊 Sondage n°7 :** Un « conseiller bancaire » vous demande au téléphone le code de validation qui vient d'arriver sur votre téléphone. Que signifie cette demande ?
    *   A) La banque vérifie votre identité : c'est une procédure normale
    *   B) C'est une fraude certaine : ce code valide une opération en cours — celui qui le demande est en train d'agir sur votre compte ✅
    *   C) C'est acceptable si l'appelant connaît déjà votre nom et votre adresse
*   **📊 Sondage n°8 :** Un collaborateur signale immédiatement avoir cliqué sur un lien de phishing et saisi son mot de passe. Quelle est la réaction adaptée de l'entreprise ?
    *   A) Une sanction disciplinaire proportionnée, pour l'exemple
    *   B) Le remercier du signalement, réinitialiser ses accès et circonscrire l'incident au plus vite ✅
    *   C) Ne rien faire : le mal est déjà fait

**Éléments de débriefing (pour le mentor) :**

- N°6 : la personnalisation est LE multiplicateur d'efficacité — d'où l'importance de maîtriser sa propre empreinte publique (OSINT).
- N°7 : règle absolue et sans exception — aucun organisme légitime ne demande jamais ce code. Connaître votre nom et votre adresse ne prouve rien : ces données circulent dans les fuites (souvenez-vous de France Travail, vu en B01).
- N°8 : la culture du signalement est un investissement : punir la victime, c'est garantir que la prochaine se taira — et que l'incident durera des jours au lieu de minutes.

## 3. Ressources complémentaires

*   **Sur IBM SkillsBuild** : Suivre le cours *"Introduction to Cybersecurity Tools & Cyber Attacks - Social Engineering"* (~1h00).
*   **Recherche autonome** : Se renseigner sur le concept d'OSINT (*Open Source Intelligence*) pour comprendre comment les attaquants collectent légalement des informations publiques sur les entreprises.
*   [Cybermalveillance — Phishing](https://www.cybermalveillance.gouv.fr/tous-nos-contenus/fiches-reflexes/hameconnage-phishing)
*   [CNIL — Ingénierie sociale](https://www.cnil.fr/fr/spam-phishing-arnaques-signaler-pour-agir)

## 4. Exercice bonus (Sondage Livestorm)

*   **Objectif :** Détection de signaux faibles d'hameçonnage.
*   **📊 Sondage Livestorm n°9 :** Vous recevez un e-mail d'un fournisseur habituel contenant une facture. Quelle anomalie doit vous alerter en premier ?
    *   A) Le montant de la facture est élevé.
    *   B) L'adresse de l'expéditeur a un domaine légèrement modifié (ex. `support@st0rmshield.fr` au lieu de `stormshield.fr`) ✅
    *   C) L'e-mail a été envoyé à 14h.
*   **Guide d'animation (pour le mentor) :** Montrez l'importance du typosquatting (changement de caractères subtils comme un zéro au lieu d'un « o ») comme vecteur classique pour tromper les utilisateurs — le même mécanisme que dans la « chasse aux indices » de la session. Segment tampon : à faire en autonomie si la session est en retard.

## 5. Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Baiting (Appâtage)** | Support piégé laissé en évidence (clé USB) misant sur la curiosité de la victime. |
| **BEC (Business Email Compromise)** | Fraude au président : usurpation ou piratage de la messagerie d'un dirigeant/fournisseur pour ordonner des virements frauduleux. |
| **Deepfake** | Voix ou vidéo falsifiée par IA — « reconnaître » un visage ne prouve plus l'identité (cas Arup, 2024). |
| **OSINT** | Collecte légale d'informations publiques — le carburant du spear-phishing. |
| **Phishing (Hameçonnage)** | E-mails frauduleux massifs usurpant un tiers de confiance pour voler des données. |
| **Smishing** | Hameçonnage par SMS (faux colis, fausse amende). |
| **Spear-phishing** | Hameçonnage ciblé et personnalisé visant un individu ou une organisation précise. |
| **Typosquatting** | Domaine imitant un domaine légitime à un caractère près (`st0rmshield.fr`). |
| **Vishing** | Hameçonnage vocal — vise souvent l'extorsion des codes MFA. |

**La règle d'or de la session :** face à toute demande sensible (virement, RIB, code, mot de passe), la parade tient en un réflexe — **vérifier par un canal indépendant** : raccrocher et rappeler un numéro connu. Une minute de vérification déjoue des attaques à 19 millions d'euros.
