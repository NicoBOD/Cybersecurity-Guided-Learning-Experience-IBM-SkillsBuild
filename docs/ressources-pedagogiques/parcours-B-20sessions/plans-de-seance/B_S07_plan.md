# Plan de séance — Session B07 : Communications sécurisées
Parcours : B 20 sessions  |  Module : B — Systèmes & réseaux  |  Durée : 90 min  |  Modalité : Webinaire Livestorm (grand groupe — interactions par sondages et chat)

## Objectifs pédagogiques (verbes d'action)
- **Expliquer** le fonctionnement du handshake TLS (HTTPS) et le rôle des autorités de certification.
- **Comparer** les protocoles et architectures VPN (IPsec, OpenVPN, WireGuard) selon les cas d'usage (nomade ou site-à-site).
- **Préconiser** une configuration Wi-Fi moderne (WPA3, WPA-Enterprise) et les règles d'usage sur réseau public.

## Prérequis & progression
- **Prérequis** : B05 (ports, paquets, sniffing) et B06 (architecture segmentée).
- **Lien de progression** : B06 a protégé le réseau ; B07 protège les données qui en sortent (transit). B08 clôturera le module avec le durcissement des postes et l'Atelier de Synthèse 1, où toutes les briques s'assemblent.

## Checklist technique Livestorm (à préparer AVANT la session)
- [ ] Les **9 sondages** de la session sont créés dans Livestorm, numérotés et ordonnés (voir tableau ci-dessous).
- [ ] Le partage d'écran est testé avec le diaporama B07 ([spécifications](../slides/B_S07_slides_spec.md)) ; en option, un navigateur prêt pour montrer le certificat d'un site (clic sur le cadenas).
- [ ] Le chat est ouvert à tous ; si possible, un modérateur remonte les meilleures questions.
- [ ] Un minuteur est visible du mentor (le déroulé est calibré à la minute).

| N° | Moment | Type | Question (résumé) | Bonne réponse |
|----|--------|------|-------------------|---------------|
| 1 | 0:04 | Sondage | Part des pages web chargées en HTTPS aujourd'hui ? | C) Plus de 90 % |
| 2 | 0:46 | Sondage | Wi-Fi du siège : quelle configuration ? | B) WPA3-Enterprise (802.1X) |
| 3 | 0:50 | Sondage | Accès nomade : quelle technologie ? | B) VPN moderne (WireGuard) |
| 4 | 0:54 | Sondage | Au café : première action ? | C) Activer le VPN avant tout |
| 5 | 1:08 | Sondage | Votre pratique sur Wi-Fi public ? | Opinion (pas de bonne réponse) |
| 6 | 1:16 | Sondage | À quoi sert le certificat dans le handshake ? | B) Prouver l'identité du serveur |
| 7 | 1:18 | Sondage | Pourquoi asymétrique PUIS symétrique ? | A) Échanger la clé, puis chiffrer vite |
| 8 | 1:20 | Sondage | L'avantage décisif du WPA-Enterprise ? | C) Identifiants individuels révocables |
| 9 | Tampon | Sondage | Différence VPN / proxy web ? | B) Le VPN chiffre tout le trafic |

## Vue d'ensemble du déroulé (90 min)

| Min | Segment | Interaction Livestorm |
|-----|---------|----------------------|
| 0:00–0:04 | Accueil & retour sur l'observation du cadenas | 💬 Chat : les CA repérées |
| 0:04–0:10 | Brise-glace : le web est-il chiffré ? | 📊 Sondage n°1 |
| 0:10–0:24 | Séquence 1 : TLS, le handshake & les certificats | Question rhétorique |
| 0:24–0:34 | Séquence 2 : Les VPN (architectures & protocoles) | 💬 Chat : télétravail |
| 0:34–0:44 | Séquence 3 : La sécurité Wi-Fi (WEP → WPA3) | Question rhétorique |
| 0:44–0:58 | Activité : Mission « 100 consultants nomades » | 📊 Sondages n°2, 3, 4 |
| 0:58–1:08 | Chiffres clés & affaires Firesheep + DigiNotar | 💬 Chat : réactions |
| 1:08–1:12 | Et vous ? Le Wi-Fi public | 📊 Sondage n°5 |
| 1:12–1:16 | Mini-scénario : les deux Wi-Fi de l'hôtel | 🤔 Chat : A, B ou C |
| 1:16–1:22 | Quiz de validation | 📊 Sondages n°6, 7, 8 |
| 1:22–1:26 | Exercice bonus : VPN vs proxy (tampon) | 📊 Sondage n°9 |
| 1:26–1:30 | Synthèse, devoirs & teaser B08 | Chat : « un mot retenu » |

## Déroulé minuté détaillé (script semi-verbatim)

### 0:00–0:04 — Accueil & retour sur le self-paced

**🎙️ Verbatim d'ouverture :**
> « Bonjour à toutes et à tous ! Vos murailles sont construites depuis la semaine dernière — mais vos données, elles, voyagent : Wi-Fi, hôtels, Internet. Ce soir, on les protège en chemin. D'abord, votre mission de la semaine : qui a cliqué sur le cadenas de son navigateur ? Tapez dans le chat le nom de l'autorité de certification que vous avez vue. »

**Points à dérouler :**
- Lire 3-4 noms du chat (attendu : Let's Encrypt très fréquent, DigiCert, Sectigo...) : « retenez ces noms — l'une des histoires de ce soir raconte ce qui arrive quand un de ces organismes se fait pirater. »
- Rappel express de B06 : Default Deny, DMZ, segmentation — et Target.
- Annonce du programme : le cadenas décortiqué (TLS), les tunnels (VPN), le Wi-Fi — et deux affaires qui ont changé la confiance sur le web.

**Transition scriptée :** « Première question : ce cadenas, il est partout ou presque ? Votez. »

### 0:04–0:10 — Brise-glace : Sondage n°1 (le web chiffré)

**Consigne :** Lancer le **📊 Sondage n°1** — quelle proportion des pages web est chargée en HTTPS aujourd'hui ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Réponse C : plus de 90 %, selon le rapport de transparence de Google. Le chiffrement est devenu la norme — mais c'est très récent : au début des années 2010, la plupart des sites, réseaux sociaux compris, transmettaient vos sessions EN CLAIR sur le réseau. Ce qui a fait basculer le web ? En bonne partie, une petite extension de navigateur gratuite, créée pour provoquer un scandale. Je vous raconte ça tout à l'heure. D'abord : que garantit exactement ce cadenas ? »

**Transition scriptée :** « Ouvrons le capot du HTTPS : une poignée de main en quatre temps. »

### 0:10–0:24 — Séquence 1 : TLS, le handshake & les certificats

**Points de contenu à dérouler (support §1) :**
- Le problème : HTTP = la carte postale sans enveloppe (rappel de l'exercice bonus B05 : `password=Password123` lisible).
- **HTTPS = HTTP dans un tunnel TLS** (précision : SSL est mort — TLS 1.2 minimum, 1.3 recommandé par l'ANSSI ; « certificat SSL » est un abus de langage commercial).
- **Le handshake en 4 temps** : négociation des algorithmes → authentification du serveur par **certificat** (vérifié auprès d'une **CA** de confiance) → échange de la clé de session (cryptographie asymétrique) → chiffrement rapide du trafic (symétrique).
- **Pourquoi deux cryptographies ?** L'asymétrique échange un secret sans rencontre préalable mais elle est lente ; la symétrique est rapide mais exige une clé partagée. Le handshake combine : l'asymétrique livre la clé, la symétrique fait le travail.
- Question rhétorique : *« Que se passerait-il sans le certificat ? »* — vous chiffreriez peut-être... vers l'attaquant (MitM). Le chiffrement sans authentification ne vaut rien.
- **Option démonstration (2 min)** : cliquer sur le cadenas d'un site en partage d'écran — montrer l'émetteur du certificat, la période de validité, la version TLS.

**Transition scriptée :** « Le cadenas protège un flux applicatif. Pour chiffrer TOUT ce qui sort de la machine, il faut un tunnel. »

### 0:24–0:34 — Séquence 2 : Les VPN

**Points de contenu à dérouler (support §2) :**
- Le principe : un tunnel chiffré à travers un réseau public — l'autoroute souterraine blindée (analogie du support).
- **Deux architectures** : accès distant (*client-to-site*, le télétravailleur) et site-à-site (relier durablement deux sites).
- **Trois protocoles** : IPsec (le robuste historique, norme du site-à-site, couche 3), OpenVPN (le flexible open-source, plus lourd), WireGuard (le moderne : léger, rapide, reconnexion instantanée — idéal nomade).
- **La mise en garde** (Bon à savoir du support) : la passerelle VPN est un équipement de bordure — parmi les plus ciblés (ANSSI, rappel B05) ; elle se maintient à jour et se protège par MFA, sinon le tunnel des employés devient celui des attaquants.
- Relance chat (0:31) : *« Qui utilise un VPN d'entreprise en télétravail ? Oui / non / je ne sais pas. »* — lire et rebondir.

**Transition scriptée :** « Dernier maillon, le plus proche de vous : les ondes. Le Wi-Fi traverse les murs — et vos données avec. »

### 0:34–0:44 — Séquence 3 : La sécurité Wi-Fi

**Points de contenu à dérouler (support §3) :**
- Le problème physique : les ondes ne s'arrêtent pas à vos murs — l'interception est possible depuis le parking.
- **WEP** : mort — cassable en quelques secondes avec des outils grand public ; à bannir partout où on le croise encore.
- **WPA2-PSK** : le standard domestique — une clé partagée pour tous, vulnérable au dictionnaire (clé faible) et à des failles de conception (KRACK).
- **WPA3** : le standard moderne — l'échange SAE bloque l'interception passive et les attaques hors ligne.
- **WPA-Enterprise (802.1X)** : le mode entreprise — des identifiants **nominatifs** par salarié, contrôlés par un serveur RADIUS : révocation individuelle, traçabilité.
- Question rhétorique : *« Pourquoi une clé partagée est-elle un problème en entreprise, même robuste ? »* — un départ = changer le Wi-Fi de tout le monde ; aucune traçabilité individuelle. (La réponse complète arrive dans l'activité.)

**Transition scriptée :** « Vous avez toutes les cartes. Mission : sécuriser une société de 100 consultants nomades. Trois décisions, trois votes. »

### 0:44–0:58 — Activité : Mission « 100 consultants nomades » (Sondages n°2 à 4)

**Consigne :** Afficher le contexte (support, activité « Mission ») : 100 consultants mobiles — gares, hôtels, sites clients — accédant aux serveurs internes et au cloud. Lancer les **📊 Sondages n°2, 3, 4** l'un après l'autre (~4-5 min chacun : énoncé, vote, débrief).

**🎙️ Verbatim de lancement :**
> « Vous êtes le consultant cybersécurité. Première décision : le Wi-Fi du siège. WEP ? WPA2 avec un bon mot de passe affiché en salle de pause ? Ou WPA3-Enterprise ? Votez ! »

**Débriefs scriptés (points obligatoires) :**
- N°2 (Wi-Fi siège → WPA3-Enterprise) : le mot-clé est **nominatif** — révocation individuelle au départ d'un consultant, traçabilité RADIUS. La clé partagée affichée (A) cumule tous les défauts ; WEP (C) se casse en secondes.
- N°3 (nomade → VPN WireGuard) : le piège est A — « HTTPS suffit » ignore les métadonnées (domaines, destinations) et les applications non-web. WireGuard : léger, économe, reconnexion instantanée. Le proxy (C) ne chiffre pas globalement — c'est l'exercice bonus.
- N°4 (au café → VPN d'abord) : l'ordre des opérations EST la réponse — chaque seconde de trafic hors tunnel est lisible par le voisin. Compléter : HTTPS exigé partout (double chiffrement) + profil « réseau public » (partages désactivés).
- **Conclure** en affichant la fiche de préconisations complète (support, corrigé) : « voilà un livrable de consultant — trois choix techniques, trois justifications. »

**Transition scriptée :** « Ces règles ont l'air de bon sens ? Il a fallu deux électrochocs pour que le monde les adopte. »

### 0:58–1:08 — Chiffres clés & deux affaires réelles

**Chiffres (2 min, support §4) :** plus de 90 % du web en HTTPS aujourd'hui (Google) — contre une minorité au début des années 2010 ; plus de 100 000 téléchargements en 24h pour Firesheep (2010) ; ~300 000 internautes iraniens espionnés via les faux certificats DigiNotar (Fox-IT, 2011).

**Cas n°1 — Firesheep, 2010 (4 min, support §5) :** raconter : l'extension Firefox gratuite qui, sur un Wi-Fi ouvert, affichait la liste des comptes Facebook/Twitter des voisins — un double-clic pour naviguer dans leur session. Le mécanisme : seule la page de connexion était chiffrée ; le **cookie de session** circulait en clair (*session hijacking*). 100 000 téléchargements en 24h, scandale mondial — et c'était le but : en quelques mois, Facebook, Twitter puis le web entier basculent en HTTPS intégral ; Let's Encrypt achèvera la généralisation. Leçons : l'écoute passive est indétectable ; le chiffrement partiel est une illusion ; l'électrochoc a fait en un an ce que dix ans d'avertissements n'avaient pas obtenu.

**Cas n°2 — DigiNotar, 2011 (4 min, support §5) :** raconter : l'autorité de certification néerlandaise piratée ; plus de 500 faux certificats émis, dont `*.google.com`, valides pour tous les navigateurs ; utilisés en Iran pour espionner ~300 000 comptes Gmail — cadenas affiché, surveillance totale. La sanction : les navigateurs retirent leur confiance, tous les certificats DigiNotar invalidés du jour au lendemain, **faillite en quelques semaines**. Leçons : toute la confiance du web repose sur les CA ; le MitM parfait existe avec un certificat valide ; quand on vend de la confiance, on ne survit pas à sa perte (écho au RaaS de B02). Relance chat : *« Quel détail vous marque le plus ? »*

### 1:08–1:12 — Sondage n°5 : et vous, sur Wi-Fi public ?

**Consigne :** Lancer le **📊 Sondage n°5** (opinion) — votre pratique actuelle sur Wi-Fi public ? Vote 60-90 s.

**🎙️ Débrief scripté :**
> « Sans jugement — avant cette session, la réponse C est la plus fréquente. Si vous avez répondu B, bonne nouvelle : le HTTPS généralisé protège déjà le contenu — merci Firesheep. Ce qui manque : les métadonnées et les applications non-web, exactement ce que le VPN ajoute. L'objectif d'après ce soir : que le réflexe A — VPN d'abord — devienne automatique en déplacement professionnel. »

### 1:12–1:16 — 🤔 Mini-scénario : les deux Wi-Fi de l'hôtel

**Consigne :** Afficher le mini-scénario du support : deux réseaux ouverts à l'hôtel Bellevue — `Hotel_Bellevue` et `Hotel Bellevue - WiFi Gratuit`. *« Tapez A, B ou C dans le chat. »*

**Débrief :** B — l'un des deux est peut-être un **jumeau maléfique** (*Evil Twin*) : un point d'accès pirate au nom crédible, dont l'opérateur voit tout le trafic non chiffré. Le meilleur signal (A) peut justement être le pirate — il est peut-être dans la chambre d'à côté. Le réflexe en deux temps : vérifier le nom officiel à la source humaine, et n'accorder sa confiance à AUCUN Wi-Fi public — le VPN protège même en cas d'erreur de réseau.

**Transition scriptée :** « Trois questions pour verrouiller la session. »

### 1:16–1:22 — Quiz de validation (Sondages n°6 à 8)

**Consigne :** Lancer les **📊 Sondages n°6, 7, 8** à la suite (~2 min chacun). Réponses : le certificat prouve l'identité du serveur (il ne chiffre pas) ; l'asymétrique livre la clé, la symétrique chiffre vite ; le WPA-Enterprise apporte des identifiants individuels révocables (RADIUS). Débriefs scriptés dans le [support, « Quiz de validation »](../supports-md/B_S07_support.md).

### 1:22–1:26 — Exercice bonus (Sondage n°9) — *segment tampon*

**Consigne :** Lancer le **📊 Sondage n°9** — VPN vs proxy web : la différence majeure ? Débrief : le VPN chiffre la totalité du trafic de la machine (messagerie, applications métier, DNS) ; le proxy ne relaie que le trafic applicatif, sans chiffrement global. C'est pourquoi le VPN d'entreprise est LE standard des accès nomades. À couper en cas de retard.

### 1:26–1:30 — Synthèse & clôture

**🎙️ Verbatim de synthèse :**
> « Ce soir : le cadenas décortiqué — authentifier PUIS chiffrer ; les tunnels — le VPN qui protège tout, même sur un réseau hostile ; le Wi-Fi — WPA3 et des accès nominatifs. Et deux histoires : celle qui a forcé le web à se chiffrer, et celle qui rappelle que le cadenas ne vaut que ce que valent ses garants. Un mot que vous retenez, dans le chat ! »

**Points de clôture :**
- Lire 4-5 mots du chat.
- Self-paced : cours IBM SkillsBuild *"Secure Protocols & Cryptography Basics"* (~1h30) + relire ses notes B05-B07 et compléter son schéma draw.io (équipements de sécurité) — **préparation directe de l'Atelier de Synthèse B08**.
- Teaser B08 : « la semaine prochaine, pas de nouveau chapitre : ON ASSEMBLE TOUT. Vous concevrez de A à Z le réseau sécurisé d'une PME — segmentation, filtrage, chiffrement, durcissement des postes. C'est votre premier atelier de synthèse : venez avec vos notes. »
- Terminer à l'heure exacte.

## Gestion du temps (variable d'ajustement)

**Si vous êtes en retard :**
1. Couper l'**Exercice bonus n°9** (1:22–1:26) — il est dans le support en exercice bonus.
2. Sauter la démonstration du certificat en direct (séquence 1 ramenée à 12 min).
3. Compresser le cas Firesheep à 3 min (l'essentiel : cookie en clair → scandale → HTTPS partout).
4. Ne JAMAIS couper : l'activité « 100 consultants », le cas DigiNotar, le quiz.

**Si vous êtes en avance :**
1. Dérouler les **Questions de réflexion** du support (notamment la n°1 : ce que HTTPS ne cache pas — métadonnées, DNS, SNI).
2. Démonstration prolongée : inspecter les certificats de 2-3 sites connus (émetteur, validité, version TLS).
3. Questions/réponses libres.

## Travail en autonomie (Self-paced)
* **Avant la session suivante (B08)** :
  * **Sur IBM SkillsBuild** : Suivre le cours *"Secure Protocols & Cryptography Basics"* (durée estimée : 1h30).
  * **Préparation de l'Atelier de Synthèse 1** : Relire ses notes des sessions B05 à B07 et compléter le schéma draw.io commencé après B06 avec une première liste d'équipements de sécurité pour une infrastructure d'entreprise simple.
