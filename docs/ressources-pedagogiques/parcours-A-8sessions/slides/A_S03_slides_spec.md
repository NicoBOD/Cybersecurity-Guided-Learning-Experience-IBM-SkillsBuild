# Spécifications des slides — Session 03 : Sécurité des systèmes & réseaux
Parcours : A 8 sessions  |  Module : Réseau & Infrastructure  |  Format : Spécifications Markdown  |  Modalité : Webinaire Livestorm

> **Principe directeur** : le texte affiché reste minimal ; le contenu riche est dans les notes du présentateur et dans le [plan d'animation minuté](../plans-de-seance/A_S03_plan.md), qui fait référence pour les verbatims et débriefs. Les numéros de sondages renvoient à la checklist Livestorm du plan.

---

## Slide 1 : Page de garde
* **Layout** : Titre (Emphase visuelle, fond sombre)
* **Texte affiché sur la slide** :
  * **Sécurité des Systèmes & Réseaux**
  * Parcours A — Session 03
  * *Bâtir des barrières logiques : du pare-feu au chiffrement des communications*
  * Nom du Mentor / IBM SkillsBuild
* **Visuels suggérés** : Schéma épuré représentant un mur de briques incandescent (pare-feu) protégeant des serveurs contre un nuage Internet. Logo officiel dans un angle.
* **Notes du présentateur** :
  * Accueillir les apprenants ; retour sur les devoirs d'A2 : « qui a trouvé un phishing dans sa boîte ? Racontez dans le chat » — lire 2-3 trouvailles.
  * Pivot : A2 = l'attaquant entre par la manipulation ; A3 = les remparts techniques qui confinent les dégâts.

---

## Slide 2 : Objectifs de la séance & Sommaire
* **Layout** : Deux colonnes (Gauche : Objectifs, Droite : Sommaire)
* **Texte affiché sur la slide** :
  * **Nos objectifs aujourd'hui** :
    * Expliquer le rôle d'un pare-feu et la logique de ses règles.
    * Comprendre l'utilité (et les limites) d'un *VPN*.
    * Différencier *HTTP* et *HTTPS / TLS*.
    * Concevoir une segmentation réseau simple (LAN, Wi-Fi invités, *DMZ*).
  * **Sommaire de la séance** :
    * 1. Brise-glace : le serveur-appât (6 min)
    * 2. La carte postale : comment circule l'info (5 min)
    * 3. Pare-feu, VPN & HTTPS (22 min)
    * 4. Segmentation & DMZ (8 min)
    * 5. Activité : L'Architecte Réseau (14 min)
    * 6. Démo : audit de règles de pare-feu (8 min)
    * 7. Cas réels Target & Mirai, quiz & synthèse (27 min)
* **Visuels suggérés** : Icônes cibles pour les objectifs et icône de liste pour le sommaire.
* **Notes du présentateur** :
  * Rassurer : toutes les notions techniques (ports, protocoles) seront vulgarisées par des analogies du quotidien.
  * Annoncer le rythme : un sondage ou une question chat toutes les 8 minutes environ.

---

## Slide 3 : Brise-glace — Le serveur-appât
* **Layout** : Plein écran interactif (sondage)
* **Texte affiché sur la slide** :
  * **📊 Sondage n°1 — À votre avis...**
  * *Vous branchez un serveur tout neuf sur Internet, sans aucune protection. Combien de temps avant les premières tentatives de connexion malveillantes ?*
    * A) Quelques minutes  ·  B) Quelques jours  ·  C) Quelques semaines  ·  D) Seulement si l'on est ciblé
  * (Réponse révélée après le vote)
* **Visuels suggérés** : Pot de miel stylisé entouré d'abeilles-robots ; après le vote, un chronomètre affichant « quelques minutes » en très grand.
* **Notes du présentateur** :
  * Lancer le sondage n°1, laisser 60-90 s.
  * Débrief : réponse A — les études par honeypots montrent un balayage permanent d'Internet par des scanners automatisés. Enterrer le mythe D : l'exposition suffit, pas besoin d'être « intéressant » (rappel A1 : l'attaquant teste tout).

---

## Slide 4 : La carte postale
* **Layout** : Plein écran interactif (chat)
* **Texte affiché sur la slide** :
  * **💬 Dans le chat : vous envoyez une carte postale (sans enveloppe) avec un secret au dos.**
  * *Qui peut la lire pendant le voyage ?*
* **Visuels suggérés** : Dessin humoristique d'une carte postale avec « mot de passe : Azerty2024 » écrit au dos, passant de main en main.
* **Notes du présentateur** :
  * Lire les réponses (facteur, centre de tri, voisin, concierge...).
  * Révéler l'analogie : HTTP = la carte postale (tout en clair) ; HTTPS = la même carte sous enveloppe blindée (TLS) ; le VPN = le convoyeur privé qui masque même le destinataire.
  * Annoncer : « toute la session tient dans cette image ».

---

## Slide 5 : Le pare-feu (Firewall)
* **Layout** : Contenu structuré avec tableau de règles
* **Texte affiché sur la slide** :
  * **Le Pare-feu : le douanier du réseau** — *3 critères : IP source/destination · Protocole · Port*
  * **La table de filtrage (lue de haut en bas, première correspondance gagne) :**
    * 1. LAN → Internet · 443 (HTTPS) · **AUTORISER**
    * 2. Internet → Serveur Web (DMZ) · 443 · **AUTORISER**
    * 3. DMZ → LAN · Tout · **BLOQUER**
    * 4. Tout → Tout · Tout · **BLOQUER** *(Default Deny)*
* **Visuels suggérés** : Schéma d'un pare-feu laissant passer des paquets verts et bloquant des paquets rouges ; la table de règles avec la dernière ligne en surbrillance.
* **Notes du présentateur** :
  * Métaphore des ports = portes numérotées de l'immeuble (443 : entrée visiteurs sécurisée ; 22 : entrée technicien).
  * Marteler Default Deny : « on autorise le nécessaire, on n'énumère jamais le mal — la liste serait infinie ».
  * Question rhétorique : « pourquoi ne pas tout autoriser et bloquer les méchants connus ? » (les méchants inconnus d'aujourd'hui dépassent les méchants connus d'hier).

---

## Slide 6 : Le tunnel sécurisé : Le VPN
* **Layout** : Deux colonnes comparatives
* **Texte affiché sur la slide** :
  * **VPN : le tunnel chiffré**
  * **Sans VPN (Wi-Fi public)** : vos flux non chiffrés sont lisibles par quiconque partage le réseau (*sniffing*).
  * **Avec VPN** : chiffrement dès votre machine → tunnel → passerelle de l'entreprise ; illisible pour tous les intermédiaires.
  * **Deux limites à connaître :**
    * Il protège le **transport**, pas le contenu (un malware voyage très bien chiffré).
    * La passerelle VPN est elle-même exposée : elle **se met à jour** !
* **Visuels suggérés** : Schéma « sans VPN » (données à nu sous l'œil d'un attaquant) vs « avec VPN » (tunnel bleu opaque) ; panneau « maintenance » sur la passerelle.
* **Notes du présentateur** :
  * Cas d'usage : télétravail, déplacement, Wi-Fi d'hôtel.
  * Distinguer sniffing (écoute passive) et Man-in-the-Middle (interposition active qui peut modifier les échanges).
  * Teaser : « les passerelles VPN non maintenues sont devenues un vecteur d'intrusion majeur — chiffres dans quelques slides ».

---

## Slide 7 : Le standard du Web chiffré : HTTPS & TLS
* **Layout** : Deux colonnes + sondage
* **Texte affiché sur la slide** :
  * **HTTP vs HTTPS : repérer le cadenas**
  * **HTTP** : tout circule en clair — mots de passe lisibles par écoute (*sniffing*).
  * **HTTPS (TLS)** : échanges chiffrés + certificat authentifiant le site (contre l'interposition *Man-in-the-Middle*).
  * *NB : on dit « SSL » par habitude — le protocole moderne est TLS (SSL est déprécié).*
  * **📊 Sondage n°2 : Wi-Fi d'hôtel + site bancaire en HTTPS — le gérant peut-il lire votre mot de passe ?**
* **Visuels suggérés** : Deux barres d'adresse de navigateur (« Non sécurisé » rouge vs cadenas fermé) ; carte postale vs enveloppe blindée en rappel.
* **Notes du présentateur** :
  * Lancer le sondage n°2. Réponse : B (non) — mais nuance clé : contenu chiffré, métadonnées visibles (il voit QUE vous parlez à la banque) ; c'est ce que le VPN ajoute.
  * Piège inverse à marteler : le cadenas ≠ site honnête — un site de phishing obtient un certificat gratuit en minutes (reboucler avec A2).

---

## Slide 8 : Segmentation & DMZ — Protéger le cœur du réseau
* **Layout** : Architecture réseau graphique
* **Texte affiché sur la slide** :
  * **Le réseau plat : une maison sans portes intérieures** → un poste infecté = **déplacement latéral** vers tout le reste.
  * **La parade : cloisonner en zones étanches**
    * **LAN interne** : postes et données de l'entreprise
    * **Wi-Fi invités** : Internet seul, zéro accès interne
    * **DMZ** : serveurs exposés (web, mail) — interrogeable depuis Internet, **jamais** de connexion initiée vers le LAN
* **Visuels suggérés** : Schéma à trois zones séparées par un pare-feu central multi-interfaces ; portes coupe-feu stylisées entre les zones.
* **Notes du présentateur** :
  * Analogie de l'immeuble : guichet (pare-feu), salle d'attente aux portes blindées (DMZ), badges par étage (VLAN).
  * Relier à A1 : la segmentation = la défense en profondeur version réseau ; chaque zone peut tomber sans entraîner les autres.
  * Question rhétorique : « le Wi-Fi visiteurs de VOTRE entreprise mène-t-il quelque part ? En êtes-vous sûr ? » — transition vers l'activité.

---

## Slide 9 : Activité — L'Architecte Réseau
* **Layout** : Schéma + 3 sondages successifs
* **Texte affiché sur la slide** :
  * **🏗️ L'Architecte Réseau — 3 décisions, 3 votes**
  * *Le réseau plat de la PME : postes, serveur web public, compta et Wi-Fi clients... tous ensemble !*
    * **Décision 1** (📊 Sondage n°3) : un téléphone infecté rejoint le Wi-Fi — quel risque ?
    * **Décision 2** (📊 Sondage n°4) : où placer le serveur web public ?
    * **Décision 3** (📊 Sondage n°5) : quelle règle pour le Wi-Fi invités ?
* **Visuels suggérés** : Schéma « avant » (réseau plat, tout relié à un seul switch) qui se transforme en schéma « après » (3 zones + pare-feu) au fil des débriefs.
* **Notes du présentateur** :
  * ~4-5 min par décision (vote + débrief). Réponses : déplacement latéral ; DMZ ; Internet seul.
  * Débriefs clés : réseau plat = maison sans portes (teaser Target « à 200 M$ ») ; DMZ = sas sans porte vers l'intérieur (règle 3) ; « c'est pratique » = l'ennemi de la segmentation.
  * Conclure sur le schéma cible : « trois votes = le travail d'un architecte sécurité ».

---

## Slide 10 : Démo 3 — Audit de règles de pare-feu
* **Layout** : Console textuelle / Liste de règles
* **Texte affiché sur la slide** :
  * **Démonstration : audit d'une table de filtrage**
    1. `Source: LAN | Dest: Internet | Port: ANY | ALLOW`
    2. `Source: Internet | Dest: Server_Web | Port: 443 | ALLOW`
    3. `Source: Internet | Dest: LAN | Port: ANY | DENY`
  * **💬 Prédiction dans le chat : que se passe-t-il si j'inverse les règles 2 et 3 ?**
* **Visuels suggérés** : Extrait de console d'administration de pare-feu simulée ; flèches d'inversion animées entre les règles 2 et 3.
* **Notes du présentateur** :
  * Suivre le [script de la Démo 3](../outils/A_scripts_demo.md#demo-3-firewall) ; lire la table de haut en bas.
  * Faire voter les prédictions dans le chat, puis révéler : le site public devient inaccessible — la règle DENY, placée avant, capte tout : **l'ordre des règles compte autant que les règles**.
  * Secours : la table est dans le support (Focus pratique), la démo se raconte avec les captures préparées.

---

## Slide 11 : Le réseau en chiffres
* **Layout** : Mosaïque de grands chiffres (stat cards)
* **Texte affiché sur la slide** :
  * **La réalité du terrain (sources citées)**
  * **Quelques minutes** : délai avant les premières attaques sur une machine exposée *(études honeypots)*
  * **Vecteur n°1** : l'exploitation d'équipements de bordure exposés — VPN, pare-feux *(ANSSI, Panorama 2024)*
  * **~1 Tbit/s** : les DDoS records du botnet Mirai dès 2016 *(objets connectés compromis)*
  * **> 200 M$** : coûts cumulés de la violation Target 2013 *(défaut de segmentation)*
* **Visuels suggérés** : Cartes de statistiques, chiffres en très grand corps, sources en petit ; pictogrammes chronomètre, passerelle, caméra, caddie.
* **Notes du présentateur** :
  * Les 3 messages : brancher = être attaqué (d'où Default Deny) ; les protections se protègent (mises à jour des équipements de sécurité) ; le maillon faible peut être un prestataire ou un objet connecté.
  * Transition : « voyons ces deux histoires en détail ».

---

## Slide 12 : Deux cas réels — Target (2013) & Mirai/Dyn (2016)
* **Layout** : Deux panneaux « étude de cas » + question chat
* **Texte affiché sur la slide** :
  * **Target, 2013 — le climatiseur à 200 M$** : identifiants d'un prestataire de climatisation → déplacement latéral jusqu'aux caisses → **~40 M de cartes bancaires** volées.
  * **Mirai/Dyn, 2016 — les caméras qui ont éteint le web** : mots de passe d'usine → botnet géant → DDoS ~1 Tbit/s → Twitter, Netflix, Spotify inaccessibles.
  * **💬 Dans le chat : chez Target, qui ou quoi aurait dû bloquer le déplacement latéral ?**
* **Visuels suggérés** : Deux cartes « dossier » : caddie + climatiseur (Target), caméra de surveillance + globe éteint (Mirai). Montants et chiffres en très grand.
* **Notes du présentateur** :
  * Raconter chronologiquement (le récit marque plus que les chiffres). Punchlines : « le climatiseur a coûté 200 millions » ; « des caméras à 40 € ont mis le web à genoux ».
  * Relier explicitement Target aux 3 votes de l'activité (accès tiers, réseau plat, absence de sas) et Mirai au brise-glace (balayage permanent) + à la Disponibilité (triade A1).
  * Question chat : réponse = un pare-feu interne entre zones (règle 3) — « la technologie existait, c'est l'architecture qui a manqué ».

---

## Slide 13 : Quiz de validation
* **Layout** : Contenu interactif (3 sondages successifs)
* **Texte affiché sur la slide** :
  * **✅ Quiz de validation — 3 questions, 3 votes**
  * **📊 Sondage n°6** : La règle de base du moindre privilège sur un pare-feu ? *(tout autoriser + liste noire / tout interdire + liste blanche / confiance aux employés)*
  * **📊 Sondage n°7** : Le VPN empêche-t-il de télécharger un virus ? *(oui / non / seulement les virus connus)*
  * **📊 Sondage n°8** : Vrai ou faux — cadenas HTTPS = site de confiance ?
* **Visuels suggérés** : Trois cartes de questions révélées successivement, coche verte à la révélation.
* **Notes du présentateur** :
  * Réponses : Default Deny ; non (transport ≠ contenu) ; faux (chiffré ≠ honnête).
  * Si le temps le permet, enchaîner le **📊 Sondage n°9** (bonus : serveur DMZ compromis — qu'est-ce qui protège le LAN ? → la règle DMZ→LAN bloquée). Sinon, le laisser en autonomie (il est dans le support).

---

## Slide 14 : Clôture & Devoirs
* **Layout** : Fin de session / Synthèse
* **Texte affiché sur la slide** :
  * **Vos trois réflexes réseau :**
    * 🛂 **FILTRER** — tout ce qui n'est pas autorisé est interdit
    * ✉️ **CHIFFRER** — HTTPS/TLS et VPN : l'enveloppe blindée
    * 🧱 **CLOISONNER** — chaque zone peut tomber sans entraîner les autres
  * **💬 Dans le chat : le mot que vous retenez**
  * **Devoirs avant A4** : module IBM SkillsBuild *Principes de la sécurité des identités et du cloud* (~75 min) + vérifier votre e-mail sur *Have I Been Pwned*.
  * **Prochaine séance** : *Sécurité du cloud, des données & des identités (A4)*.
* **Visuels suggérés** : Trois pictogrammes des réflexes ; capture de l'interface Have I Been Pwned ; logo IBM SkillsBuild.
* **Notes du présentateur** :
  * Lire 4-5 mots du chat à voix haute.
  * Expliquer Have I Been Pwned en 30 secondes (base de fuites publiques, préparation directe d'A4 sur les identités).
  * Teaser A4 : « pourquoi le MFA est la meilleure serrure du siècle ». Libérer à l'heure exacte.
