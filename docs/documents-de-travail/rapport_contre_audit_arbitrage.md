# Rapport de Contre-Audit & d'Arbitrage Technique

**Objet :** Arbitrage contradictoire du « Rapport d'Audit Technique et Pédagogique Approfondi (Zéro Défaut) » (`docs/documents-de-travail/rapport_audit_pedagogique_technique.md`)
**Périmètre contrôlé :** l'intégralité des 19 anomalies détaillées par l'audit initial, confrontées ligne à ligne aux 93 fichiers sources de `docs/ressources-pedagogiques/` (décompte des fichiers vérifié : 93 ✓)
**Méthode :** vérification d'existence de chaque « extrait exact incriminé » (grep exhaustif sur le corpus), contrôle des lignes citées, confrontation aux sources faisant autorité (IETF, NIST, ISO/IEC, ANSSI, OWASP, CNIL/RGPD, Verizon DBIR), analyse de non-régression de chaque correctif proposé.
**Date :** Août 2026
**Rôle :** Arbitre technique senior / relecture contradictoire

---

## 0. Synthèse exécutive de l'arbitrage

| # | Anomalie de l'audit initial | Gravité annoncée | Verdict du contre-audit |
| :--- | :--- | :---: | :--- |
| 1 | Confusion Diffie-Hellman / chiffrement asymétrique | MAJEUR | **CONFIRMÉ** (requalifié MINEUR, patch retravaillé) |
| 2 | « Déchiffrer la signature » (vérification de signature) | MAJEUR | **NUANCÉ** (simplification « textbook RSA », patch élargi à 7 occurrences) |
| 3 | Modes d'opération AES (GCM/AEAD) absents | MINEUR | **CORRECTIF AUDIT INVALIDE** (le patch attribue à tort l'intégrité à AES-XTS) |
| 4 | Stockage des mots de passe sans fonctions lentes | MINEUR | **FAUX POSITIF** (extrait inexistant ; exigence déjà satisfaite en B10) |
| 5 | WPA3 sans mention de SAE | MINEUR | **FAUX POSITIF** (SAE est nommé et développé à la ligne citée) |
| 6 | Taille de clés RSA 2048/4096 | DOUTE | **FAUX POSITIF** (extrait introuvable dans tout le corpus — hallucination) |
| 7 | `iptables` sans `nftables` | MAJEUR | **CORRECTIF AUDIT INVALIDE** (la commande `nft` proposée échoue sans table/chaîne préalables) |
| 8 | TLS positionné « couche 7 » du modèle OSI | MINEUR | **FAUX POSITIF** (et le correctif de l'audit mélange les couches 4/5/6/7) |
| 9 | Adresses IP RFC 5737 | MINEUR | **FAUX POSITIF** (constat de conformité, pas une anomalie — rien à corriger) |
| 10 | NIST CSF sans la fonction « Govern » | MAJEUR | **FAUX POSITIF** (la session B13 est entièrement bâtie sur le CSF 2.0 à 6 fonctions) |
| 11 | ISO 27001:2022 — Annexe A (93 mesures) | MAJEUR | **NUANCÉ** (aucune erreur dans le support ; enrichissement d'une phrase appliqué) |
| 12 | RGPD art. 83 — palier 10 M€/2 % omis | MINEUR | **FAUX POSITIF** (les deux paliers sont déjà enseignés, support et slides) |
| 13 | NIS 2 — calendrier de notification 24 h/72 h/1 mois | MINEUR | **NUANCÉ** (choix de périmètre assumé ; précision mentor ajoutée en B13) |
| 14 | Ordre de volatilité sans référence RFC 3227 | MAJEUR | **CONFIRMÉ** (requalifié MINEUR ; référence ajoutée, liste pédagogique conservée) |
| 15 | « Isoler, jamais éteindre » sans l'exception wiper | MINEUR | **NUANCÉ** (nuance ajoutée en aparté mentor uniquement) |
| 16 | Codes HTTP dans les logs de B17 | MINEUR | **FAUX POSITIF** (l'atelier enseigne déjà exactement cette distinction ; le patch de l'audit aurait cassé le sondage n°3) |
| 17 | Hexade de Parker absente du quiz A | MINEUR | **FAUX POSITIF** (hors périmètre débutant ; la source NIST invoquée ne la mentionne pas) |
| 18 | Complétude des 280 questions de quiz | MINEUR | **FAUX POSITIF** (constat de conformité re-vérifié : 80 + 200 ✓ — rien à corriger) |
| 19 | Chiffre du facteur humain (Verizon DBIR) | DOUTE | **FAUX POSITIF** (le correctif proposé contredirait le chiffre 2025 explicitement sourcé) |

**Bilan : 2 CONFIRMÉ · 4 NUANCÉ · 2 CORRECTIF AUDIT INVALIDE · 11 FAUX POSITIFS.**
Aucune anomalie « MAJEUR » ne survit à l'arbitrage avec cette gravité : sur les 6 annoncées, 2 sont des faux positifs purs (n° 5 implicite, n° 10), 2 sont requalifiées MINEUR (n° 1, n° 14), 1 relève de la nuance (n° 2) et 1 voit son correctif rejeté pour bug (n° 7).

---

## 1. Observations liminaires sur la fiabilité de l'audit initial

1. **Incohérence interne de comptage** : le tableau de bord exécutif annonce **21 anomalies**, mais seules **19 sont détaillées** (il manque 1 [DOUTE] en Axe 4 et 1 [MINEUR] en Axe 5 par rapport aux totaux du tableau).
2. **Extraits « exacts » hallucinés** : au moins 3 citations présentées comme verbatim n'existent nulle part dans le corpus (arbitrages n° 4, n° 6, et la version tronquée du n° 5) — vérifié par recherche exhaustive.
3. **Localisation défaillante** : la majorité des références `fichier (ligne X)` sont fausses ou pointent un autre fichier (n° 3 : A_S04 ne contient pas le tableau cité ; n° 8 : l'extrait est dans `B_S05_slides_spec.md`, pas dans A_S03 ni dans le support B_S05 ; n° 12 : la ligne 275 citée est une ligne de ressources SkillsBuild ; n° 16 : `app.php` n'existe pas, le log réel utilise `product.php` aux lignes 143-149).
4. **Deux « anomalies » sont des constats de conformité** (n° 9 et n° 18), comptabilisés à tort dans le total des ajustements, ce qui gonfle artificiellement le score de l'audit.
5. **Sources d'autorité** : les références citées (RFC 2631, RFC 8017, NIST SP 800-38D, SP 800-56A r3, SP 800-57 P1 r5, CSWP 29, RFC 5737, RFC 3227, Directive (UE) 2022/2555, RFC 9110, RFC 7664, RFC 9106) sont **toutes réelles et pertinentes dans leur intitulé** — mais trois correctifs les contredisent ou les surinterprètent (n° 3 : XTS vs SP 800-38E ; n° 8 : couches OSI ; n° 17 : SP 800-12 ne traite pas de l'hexade de Parker). À noter : NIST SP 800-61 Rev. 2, citée comme autorité au n° 15, est remplacée depuis avril 2025 par la **Rev. 3** (alignée CSF 2.0) — précision reportée dans le support B18.

---

## 2. Arbitrages détaillés

---

### Arbitrage 1 : Confusion entre échange de clés (Diffie-Hellman) et chiffrement asymétrique
- **Fichier concerné :** `docs/ressources-pedagogiques/parcours-B-20sessions/supports-md/B_S10_support.md` (ligne 271 — citation quasi exacte, « la signature » vs « les signatures ») + occurrences cohérentes non citées par l'audit : même fichier ligne 84, `slides/B_S10_slides_spec.md` ligne 62.
- **Statut de l'arbitrage :** **[CONFIRMÉ]** (gravité requalifiée MAJEUR → MINEUR ; patch de l'audit retravaillé)
- **Analyse critique :**
  - Sur le fond, l'audit a raison : Diffie-Hellman est un schéma d'**établissement de clé** (*key agreement*), pas un algorithme de chiffrement de messages ni de signature. Sources : **RFC 2631 §1** (« Diffie-Hellman key agreement method ») et **NIST SP 800-56A Rev. 3** (DH/ECDH classés *key-agreement schemes*, §5 et §6). Associer « (RSA, DH) » à « pour l'échange de clés **et les signatures** » attribue implicitement à DH une capacité qu'il n'a pas.
  - Requalification MINEUR : l'erreur ne figure que dans les lignes de synthèse (aide-mémoire, slide) ; le corps du support (§1, *Usage*) et la note mentor décrivent correctement DH comme mécanisme d'accord de clé (« construire un secret commun sans jamais le transmettre »). Aucun apprenant n'est exposé à une explication développée fausse.
  - Le patch de l'audit est rejeté dans sa forme : il introduit **ECC, ECDSA, Ed25519** dans un aide-mémoire de niveau « Débutant » alors que ces termes ne sont définis nulle part dans la session — régression de cohérence pédagogique. Le principe (séparer les deux lignes) est en revanche retenu.
- **Action retenue :** Appliquer un correctif minimal — scinder la ligne d'aide-mémoire, attribuer la signature à RSA sur la slide 5 et à la ligne 84, sans introduire de vocabulaire nouveau. **Appliqué.**
- **Patch / Remplacement exact :**
  ```diff
  # B_S10_support.md (aide-mémoire)
  - | **Chiffrement asymétrique (RSA, DH)** | Couple publique/privée — lent, pour l'échange de clés et les signatures. |
  + | **Chiffrement asymétrique (RSA)** | Couple publique/privée — lent, pour l'échange de clés et les signatures. |
  + | **Diffie-Hellman (DH)** | Accord de clé : deux parties construisent un secret partagé sans jamais le transmettre — ni chiffrement de messages, ni signature. |

  # B_S10_support.md (§1, Usage)
  - ...comme **RSA** ou **Diffie-Hellman**) ou pour signer numériquement des documents.
  + ...comme **RSA** ou **Diffie-Hellman**) ou pour signer numériquement des documents (avec RSA — Diffie-Hellman, lui, sert uniquement à établir une clé partagée).

  # B_S10_slides_spec.md (slide 5)
  - - **Asymétrique (RSA, DH)** : clé publique (chiffrer) + clé privée (déchiffrer) — lent, mais résout l'échange et permet la signature.
  + - **Asymétrique (RSA, DH)** : clé publique (chiffrer) + clé privée (déchiffrer) — lent, mais résout l'échange de clés (DH, RSA) et permet la signature (RSA).
  ```
  Une phrase de rigueur a également été ajoutée à la note mentor (« DH est un protocole d'accord de clé, il ne chiffre pas de messages et ne produit pas de signatures »).

---

### Arbitrage 2 : Raccourci « déchiffre la signature » dans la vérification de signature numérique
- **Fichier concerné :** `parcours-B-20sessions/slides/B_S10_slides_spec.md` (lignes 100-101 — citation exacte ✓) + 4 occurrences du même modèle **non recensées par l'audit** : `supports-md/B_S10_support.md` (lignes 52, 66, 115, 276) et `plans-de-seance/B_S10_plan.md` (ligne 102).
- **Statut de l'arbitrage :** **[NUANCÉ / SIMPLIFICATION PÉDAGOGIQUE]**
- **Analyse critique :**
  - Le modèle « signer = chiffrer l'empreinte avec la clé privée ; vérifier = la déchiffrer » n'est exact que pour le RSA « de manuel » (*textbook RSA*). Pour **RSA-PSS (RFC 8017 §8.1, RSASSA-PSS-VERIFY)**, **ECDSA (FIPS 186-5 / RFC 6979)** et **Ed25519 (RFC 8032 §5.1.7)**, la vérification est une **équation de contrôle** renvoyant vrai/faux — aucune opération de « déchiffrement » n'existe. Le Guide ANSSI *Mécanismes cryptographiques* (v2.04) traite d'ailleurs signature et chiffrement asymétrique comme des primitives distinctes.
  - Ce n'est toutefois pas une « contrevérité » au niveau visé (Débutant) : c'est l'analogie historique la plus répandue de la vulgarisation, et la CA du cours signe réellement en RSA dans la plupart des chaînes X.509 actuelles. D'où le statut NUANCÉ plutôt que CONFIRMÉ-MAJEUR.
  - Le correctif de l'audit (reformulation neutre de la note orateur) est **techniquement bon mais incomplet** : il ne traite qu'1 occurrence sur 7 — le même modèle resterait enseigné par le support, le glossaire, l'aide-mémoire et le plan de séance de la même session (incohérence garantie).
- **Action retenue :** Reformulation neutre vis-à-vis de l'algorithme sur les **7 occurrences** (support ×4, plan ×1, slides ×2), avec le verbe « sceller » (cohérent avec la métaphore du sceau de cire déjà utilisée par le cours) + précision d'expert réservée à la section mentor. **Appliqué.**
- **Patch / Remplacement exact (extraits représentatifs) :**
  ```diff
  # B_S10_slides_spec.md (notes orateur, slide 8)
  - La signature, mécanique dévoilée : quiconque a la clé publique vérifie (déchiffre la signature, recalcule le hachage, compare) — hachage + asymétrique = authenticité + intégrité.
  + La signature, mécanique dévoilée : l'émetteur scelle l'empreinte du document avec sa clé privée ; quiconque possède la clé publique vérifie mathématiquement que la signature correspond au document reçu (recalcul du hachage + contrôle de validité) — hachage + asymétrique = authenticité + intégrité.

  # B_S10_support.md (glossaire)
  - **Signature numérique** — Empreinte d'un document chiffrée avec la clé privée du signataire — vérifiable par tous avec sa clé publique (authenticité + intégrité).
  + **Signature numérique** — Preuve cryptographique calculée sur l'empreinte d'un document avec la clé privée du signataire — vérifiable par tous avec sa clé publique (authenticité + intégrité).

  # B_S10_support.md (note mentor, ajout de la précision d'expert)
  + (Précision pour un participant avancé : l'image classique « chiffrer l'empreinte, puis la déchiffrer pour vérifier » ne décrit que le RSA historique — les schémas modernes comme RSA-PSS, ECDSA ou Ed25519 n'ont pas d'opération de « déchiffrement » : la vérification est une équation qui répond vrai ou faux.)
  ```
  (Reformulations analogues appliquées en B_S10_support.md l.115 et l.276, B_S10_plan.md l.102, B_S10_slides_spec.md l.100.)

---

### Arbitrage 3 : Précision sur les modes d'opération AES (GCM vs CBC/ECB)
- **Fichiers concernés :** `parcours-B-20sessions/supports-md/B_S10_support.md` (ligne 270). ⚠️ La seconde localisation citée par l'audit (`A_S04_support.md` lignes 110-125) est **erronée** : A_S04 est la session « cloud, données & identités » et ne contient aucun tableau de ce type ; la citation elle-même est inexacte (« flux TLS » n'y figure pas).
- **Statut de l'arbitrage :** **[CORRECTIF AUDIT INVALIDE]**
- **Analyse critique :**
  - L'anomalie de fond (ne jamais évoquer les modes d'opération) est recevable au niveau mentor, pas au niveau apprenant débutant : citer « AES » sans mode est l'usage constant des cours d'initiation, et le corpus enseigne déjà **narrativement** le danger du mode ECB — le cas Adobe de la même session décrit « un mode de chiffrement qui produit le même résultat pour la même entrée » (c'est le 3DES-ECB du fichier Adobe 2013).
  - Le correctif de l'audit contient une **erreur technique caractérisée** : sa ligne de remplacement présente « AES-256-GCM / AES-XTS » comme « combinant confidentialité et intégrité ». Or **XTS n'offre aucune intégrité ni authentification** — NIST SP 800-38E le précise explicitement (XTS-AES protège la confidentialité du stockage, sans authentification ; seuls GCM/CCM sont des modes AEAD au sens de SP 800-38D/38C). Appliquer ce patch aurait introduit dans le cours une contrevérité plus grave que l'imprécision reprochée.
  - Ajouter GCM/XTS/AEAD dans l'aide-mémoire débutant créerait en outre trois termes jamais définis dans la session.
- **Action retenue :** Rejeter le remplacement de l'audit ; enrichir à la place la section « Approfondissement technique pour le mentor » (seul endroit adapté), en reliant ECB au cas Adobe. **Appliqué.**
- **Patch / Remplacement exact :**
  ```diff
  # B_S10_support.md — note mentor (ajout)
  + Et si la question des **modes d'opération** d'AES surgit : la référence actuelle est le chiffrement authentifié type **AES-GCM** (AEAD : confidentialité + intégrité, utilisé par TLS 1.3) ; le mode historique **ECB** est à proscrire — même bloc en clair, même bloc chiffré : les motifs se voient, et c'est précisément le défaut du chiffrement (3DES en mode ECB) de l'affaire Adobe racontée plus bas.

  # Ligne 270 de l'aide-mémoire : INCHANGÉE (simplification pédagogique légitime au niveau visé).
  ```

---

### Arbitrage 4 : Mention des fonctions lentes pour le stockage des mots de passe
- **Fichier concerné :** `parcours-A-8sessions/supports-md/A_S04_support.md` (ligne 85 selon l'audit)
- **Statut de l'arbitrage :** **[FAUX POSITIF]**
- **Analyse critique :**
  - L'« extrait exact incriminé » (« Les mots de passe ne sont jamais stockés en clair, mais hachés avec un sel. ») **n'existe nulle part dans le corpus** (recherche exhaustive sur les 93 fichiers). La ligne 85 d'A_S04 est un encadré sur l'identité comme nouveau périmètre de sécurité. Citation hallucinée.
  - Sur le fond, l'exigence de l'audit (fonctions dédiées lentes, conformes à l'*OWASP Password Storage Cheat Sheet* et à la RFC 9106) est **déjà intégralement satisfaite** là où le sujet est traité : B_S10_support.md enseigne trois fois « bcrypt, scrypt, **Argon2** » avec la justification exacte attendue (GPU à milliards de tests/seconde, sel unique par utilisateur, rainbow tables, bannissement MD5/SHA-1) — lignes 49, 58, 102, 274. Le parcours A, lui, ne traite pas du stockage des mots de passe côté serveur (choix de périmètre du programme en 8 sessions).
- **Action retenue :** Rejeter la remarque. Aucun correctif.
- **Patch / Remplacement exact :** aucun (l'extrait à corriger n'existe pas).

---

### Arbitrage 5 : Caractérisation de la sécurité Wi-Fi WPA3 (protocole SAE)
- **Fichier concerné :** `parcours-B-20sessions/supports-md/B_S07_support.md` (ligne 107)
- **Statut de l'arbitrage :** **[FAUX POSITIF]**
- **Analyse critique :**
  - L'audit cite : « *Il corrige les failles de WPA2 en remplaçant l'échange de clés initial par une méthode résistante aux attaques par dictionnaire* » et déplore « l'absence du nom du protocole clé (SAE) ». Or la ligne 107 réelle est : « ***WPA3** : Le standard moderne. Il corrige les failles de WPA2 en remplaçant l'échange de clés initial par le protocole **SAE** (*Simultaneous Authentication of Equals*), empêchant le piratage de la clé Wi-Fi par interception passive et attaque hors ligne.* » — **SAE y est nommé, développé et expliqué**. La citation de l'audit est une réécriture tronquée ; le grief est sans objet.
  - Accessoirement, l'explication de l'audit est elle-même approximative : KRACK (2017) est une attaque par réinstallation de clé contre le 4-way handshake (corrigée par correctifs dans WPA2), pas une attaque par dictionnaire hors ligne résolue par SAE ; et WPA3 conserve un 4-way handshake après l'échange SAE. Le support, lui, classe correctement KRACK comme « faille de conception » de WPA2 (ligne 106).
- **Action retenue :** Rejeter la remarque. Aucun correctif.
- **Patch / Remplacement exact :** aucun.

---

### Arbitrage 6 : Taille minimale de clé RSA recommandée post-2025/2030
- **Fichier concerné :** `parcours-B-20sessions/supports-md/B_S10_support.md` (lignes 90-105 selon l'audit)
- **Statut de l'arbitrage :** **[FAUX POSITIF]** (hallucination)
- **Analyse critique :**
  - La phrase citée (« RSA utilise des clés de 2048 ou 4096 bits. ») **n'existe dans aucun des 93 fichiers du corpus** (grep exhaustif sur `2048|3072|4096` : la seule occurrence est… le rapport d'audit lui-même). Les lignes 90-105 de B_S10 traitent du hachage et du sel. Le cours ne mentionne aucune taille de clé RSA, nulle part.
  - Sur le fond théorique, les données de l'audit sont exactes (SP 800-57 Part 1 Rev. 5 : RSA-2048 ≈ 112 bits de sécurité, acceptable jusqu'en 2030 ; ANSSI : modules ≥ 3072 bits recommandés pour un usage pérenne) — mais elles s'appliquent à un texte qui n'existe pas.
- **Action retenue :** Rejeter la remarque (aucun support à corriger).
- **Patch / Remplacement exact :** aucun.

---

### Arbitrage 7 : Utilisation de `iptables` sans mention de `nftables`
- **Fichier concerné :** `parcours-B-20sessions/outils/B_scripts_demo.md` (ligne 134 — citation exacte ✓)
- **Statut de l'arbitrage :** **[CORRECTIF AUDIT INVALIDE]** (anomalie recevable, requalifiée MAJEUR → MINEUR ; correctif buggé)
- **Analyse critique :**
  - Fond partiellement recevable : mentionner nftables est une actualisation utile (framework de filtrage par défaut de Debian 10+, RHEL 8+, etc.).
  - Gravité exagérée : la commande `iptables` **fonctionne sur toutes les distributions modernes** via la couche de compatibilité `iptables-nft` — la démo n'est ni cassée ni « obsolète » au sens opérationnel ; elle reste d'ailleurs le choix le plus universel pour une démo en direct (Docker et de nombreux systèmes de production restent pilotés en syntaxe iptables).
  - Le correctif de l'audit est **inexécutable en l'état** : `nft add rule inet filter input ip saddr 198.51.100.42 drop` échoue sur un système vierge avec `Error: No such file or directory`, car **nftables ne fournit aucune table ni chaîne par défaut** (contrairement aux chaînes intégrées INPUT/OUTPUT/FORWARD d'iptables). Il faut créer préalablement la table (`nft add table inet filter`) puis la chaîne avec son hook (`nft add chain inet filter input '{ type filter hook input priority 0 ; policy accept ; }'`). Présenté tel quel « en tête » de démo, le patch garantissait un échec en direct devant les apprenants.
- **Action retenue :** Conserver `iptables` comme commande de démonstration ; ajouter une note mentor complète (couche iptables-nft + équivalent natif **avec** les prérequis de table/chaîne). **Appliqué.**
- **Patch / Remplacement exact :**
  ```diff
    ```bash
    iptables -A INPUT -s 198.51.100.42 -j DROP
    ```
  + *   *Note mentor (modernisation)* : sur les distributions récentes (Debian 10+, Ubuntu 20.04+, RHEL 8+), la commande `iptables` est fournie par la couche de compatibilité **iptables-nft** : elle fonctionne toujours, mais le moteur de filtrage sous-jacent du noyau est désormais **nftables**. L'équivalent natif est `nft add rule inet filter input ip saddr 198.51.100.42 drop` — à condition d'avoir créé au préalable la table et la chaîne (`nft add table inet filter`, puis `nft add chain inet filter input '{ type filter hook input priority 0 ; policy accept ; }'`), car nftables ne fournit aucune chaîne par défaut. Pour une démo en direct, `iptables` reste le choix le plus universel.
  ```

---

### Arbitrage 8 : Positionnement de TLS dans le modèle OSI
- **Fichiers concernés (réels) :** l'extrait cité n'existe ni dans `A_S03_support.md` (l. 45) ni dans `B_S05_support.md` (l. 60-70) ; il figure dans `parcours-B-20sessions/slides/B_S05_slides_spec.md` (ligne 64).
- **Statut de l'arbitrage :** **[FAUX POSITIF]**
- **Analyse critique :**
  - Le support B_S05 (l. 87-89) n'affirme jamais que « TLS est un protocole de couche 7 » : il apparie attaques et défenses du niveau applicatif — *injections → WAF ; usurpation de services → chiffrement/authentification TLS* — ce qui est exact (HTTPS = HTTP protégé par TLS, l'authentification du serveur par certificat contrant précisément l'usurpation). La note mentor d'A_S03 (l. 47) est, elle, irréprochable (pare-feu L3/4 vs injection SQL L7 → WAF).
  - **RFC 8446** ne positionne TLS dans aucune couche OSI (le modèle OSI n'est pas le cadre de conception de TCP/IP) ; la doctrine commune le situe « au-dessus du transport, en dessous de l'application ». Reprocher au cours de ne pas trancher un point que la RFC elle-même ne tranche pas est excessif pour un support débutant.
  - Surtout, le correctif de l'audit — « **Couche 4/7 (Session / Présentation / Application)** » — est **lui-même faux** : la couche 4 est Transport ; Session = 5, Présentation = 6, Application = 7. L'appliquer aurait introduit une erreur de modèle OSI dans un support jusque-là exact.
- **Action retenue :** Rejeter la remarque (aucune modification ; la slide « minimaliste » reste couverte par les notes orateur et le support, corrects).
- **Patch / Remplacement exact :** aucun.

---

### Arbitrage 9 : Adresses IP d'exemple (RFC 5737)
- **Fichiers concernés :** `parcours-A-8sessions/outils/A_scripts_demo.md` (l. 178-183 ✓), `parcours-B-20sessions/outils/B_scripts_demo.md` (l. 130 ✓)
- **Statut de l'arbitrage :** **[FAUX POSITIF]** (non-anomalie)
- **Analyse critique :**
  - L'audit constate lui-même que l'usage est « exemplaire et parfaitement conforme » à la RFC 5737 — c'est un **constat de conformité**, pas une anomalie ; sa « correction recommandée » se réduit à « conserver ». Le comptabiliser parmi les « 21 ajustements » fausse le tableau de bord.
  - Contre-vérification élargie : toutes les adresses IP d'exemple du corpus (`203.0.113.42`, `203.0.113.66`, `203.0.113.88`, `198.51.100.23`, `198.51.100.42`) appartiennent aux plages TEST-NET-2/TEST-NET-3. Conforme.
- **Action retenue :** Rejeter (aucune action — la consigne de maintien va de soi et figure déjà dans les pratiques du corpus).
- **Patch / Remplacement exact :** aucun.

---

### Arbitrage 10 : « Absence » de la fonction Govern (NIST CSF 2.0)
- **Fichiers concernés :** `parcours-B-20sessions/supports-md/B_S13_support.md` (l. 36 et 133), `slides/B_S13_slides_spec.md` (l. 41)
- **Statut de l'arbitrage :** **[FAUX POSITIF]** (le plus manifeste du rapport)
- **Analyse critique :**
  - La session B13 est **entièrement construite autour du NIST CSF 2.0 à 6 fonctions** : résumé introductif (« 6 fonctions — la sixième, *Govern*, ajoutée en 2024, est précisément le sujet de cette session », l. 19), sondage brise-glace dédié à la 6ᵉ fonction (l. 29-36), note mentor « NIST CSF 2.0 : pourquoi GOVERN change tout » (l. 47-48), glossaire (l. 59), développement complet des 6 fonctions avec Govern en n° 1 (l. 110-116), chiffres clés « Février 2024 : publication du NIST CSF 2.0 » (l. 133), aide-mémoire (l. 256). La banque de quiz B contient même une question dont l'explication précise que « réciter “les 5 fonctions” est devenu obsolète en 2024 ».
  - L'« extrait incriminé » est l'alt-text de la slide 3, **tronqué par l'auditeur** : le texte réel est « Roue des fonctions du NIST CSF avec la gouvernance au centre reliant les cinq fonctions **historiques** » — description fidèle du **schéma officiel du CSF 2.0** (NIST CSWP 29, Figure 1 : GOVERN au centre/moyeu, alimentant les cinq autres fonctions). L'auditeur a pris la représentation officielle de la version 2.0 pour une survivance de la version 1.1.
  - La « correction recommandée » de l'audit reproduit une liste de 6 fonctions… que le support contient déjà, en plus précis (avec le pont vers chaîne d'approvisionnement, B16, B19, B12).
- **Action retenue :** Rejeter la remarque. Aucun correctif.
- **Patch / Remplacement exact :** aucun.

---

### Arbitrage 11 : Annexe A d'ISO/IEC 27001:2022 (93 mesures vs 114)
- **Fichier concerné :** `parcours-B-20sessions/supports-md/B_S13_support.md` (les lignes 70-85 citées correspondent en réalité à la section PSSI ; les passages ISO 27001 sont aux lignes 57 et 109)
- **Statut de l'arbitrage :** **[NUANCÉ / SIMPLIFICATION PÉDAGOGIQUE]**
- **Analyse critique :**
  - Aucune erreur à corriger : le support ne mentionne **ni** la structure 2013 (114 contrôles / 14 domaines), **ni** aucun décompte de mesures — le « risque de confusion avec la version 2013 » dénoncé par l'audit ne repose sur aucun contenu existant. Le choix de traiter ISO 27001 au niveau SMSI / PDCA / certification (sans plonger dans l'Annexe A) est un périmètre légitime pour une session d'initiation à la gouvernance.
  - Les chiffres avancés par l'audit sont exacts (ISO/IEC 27001:2022, Annexe A alignée sur ISO/IEC 27002:2022 : **93 mesures** en 4 thèmes — 37 organisationnelles, 8 personnes, 14 physiques, 34 technologiques) et constituent un enrichissement peu coûteux, utile en entretien et en audit.
- **Action retenue :** Modifier le texte avec nuance — une phrase de millésime + Annexe A dans le développement, mention courte au glossaire. Pas de bloc de 7 lignes comme proposé par l'audit (surdimensionné pour la place du sujet dans la session). **Appliqué.**
- **Patch / Remplacement exact :**
  ```diff
  # B_S13_support.md (§2, ISO/IEC 27001)
  - ...aboutit, après audit externe, à une **certification** officielle très valorisée auprès des clients. Point essentiel : ...
  + ...aboutit, après audit externe, à une **certification** officielle très valorisée auprès des clients. La version en vigueur — **ISO/IEC 27001:2022** — adosse au SMSI une **Annexe A de 93 mesures de référence** réparties en 4 thèmes (37 organisationnelles, 8 liées aux personnes, 14 physiques, 34 technologiques), qui remplace les 114 contrôles de l'édition 2013. Point essentiel : ...

  # B_S13_support.md (glossaire)
  - *   **ISO 27001** — Norme internationale définissant les exigences de mise en place et de certification d'un SMSI.
  + *   **ISO 27001** — Norme internationale (édition en vigueur : 2022) définissant les exigences de mise en place et de certification d'un SMSI ; son Annexe A recense 93 mesures de sécurité de référence en 4 thèmes.
  ```

---

### Arbitrage 12 : Sanctions RGPD — « omission » du palier de l'article 83.4
- **Fichier concerné :** `parcours-A-8sessions/supports-md/A_S05_support.md` (la ligne 275 citée est une ligne de ressources ; le tableau cité n'existe pas)
- **Statut de l'arbitrage :** **[FAUX POSITIF]**
- **Analyse critique :**
  - Les deux paliers de l'article 83 sont **déjà enseignés, exactement comme le demande l'audit** :
    - A_S05_support.md l. 138 : « *amendes administratives à deux paliers : jusqu'à 10 millions d'euros ou 2 % du chiffre d'affaires mondial annuel, et pour les manquements les plus graves jusqu'à 20 millions d'euros ou 4 % — le montant le plus élevé étant à chaque fois retenu* » ;
    - A_S05_slides_spec.md l. 55 (débrief scripté : « expliquer les deux paliers ») ; A_banque_quiz.md l. 456 (explication à deux paliers) ;
    - Parcours B : B_S15_support.md l. 20, 47, 94, 229, 268 (traitement le plus détaillé, avec la répartition art. 83.4/83.5 par type de manquement).
  - Les seules occurrences « 20 M€ / 4 % » isolées répondent à des questions portant sur le **plafond maximal** (sondage brise-glace l. 34) ou sont des synthèses avec « jusqu'à » — juridiquement exactes au sens de l'article 83.5 du Règlement (UE) 2016/679.
- **Action retenue :** Rejeter la remarque. Aucun correctif.
- **Patch / Remplacement exact :** aucun.

---

### Arbitrage 13 : Directive NIS 2 — calendrier de notification en 3 étapes
- **Fichier concerné (réel) :** le traitement de fond de NIS2 est dans `parcours-B-20sessions/supports-md/B_S13_support.md` (note mentor, l. 51) ; `B_S15_support.md` ne fait qu'une mention volontairement non détaillée (l. 52-53 : « situez […] sans détailler »). L'extrait cité par l'audit n'existe pas verbatim.
- **Statut de l'arbitrage :** **[NUANCÉ / SIMPLIFICATION PÉDAGOGIQUE]**
- **Analyse critique :**
  - L'absence du calendrier n'est pas une erreur : c'est un choix de périmètre explicite (« sans en faire un cours de droit »). Aucune affirmation fausse n'est en cause.
  - Le contenu proposé par l'audit est exact et vérifié : **Directive (UE) 2022/2555, article 23 §4** — alerte précoce ≤ **24 h**, notification d'incident ≤ **72 h**, rapport final ≤ **1 mois** (rapport d'avancement si l'incident est toujours en cours), auprès du CSIRT national ou de l'autorité compétente (l'ANSSI en France). Sa valeur pédagogique est réelle : le parallèle avec les 72 h du RGPD (déjà enseignées en B15 et A_S05) fixe la mémoire.
  - Emplacement du correctif de l'audit rejeté (B_S15) au profit de B_S13, là où les obligations NIS2 sont réellement présentées aux mentors.
- **Action retenue :** Modifier avec nuance — une phrase dans la note mentor NIS2 de B13. **Appliqué.**
- **Patch / Remplacement exact :**
  ```diff
  # B_S13_support.md (note mentor « NIS2 »)
  - ...avec des sanctions pouvant viser les dirigeants. Le temps où la cybersécurité était « le problème de l'informatique » est juridiquement terminé.
  + ...avec des sanctions pouvant viser les dirigeants. Autre nouveauté opérationnelle (art. 23) : la notification des incidents significatifs au CSIRT national (l'ANSSI en France) suit un calendrier en trois temps — **alerte précoce sous 24 h**, **notification complète sous 72 h**, **rapport final sous un mois** ; un parallèle utile avec les 72 h du RGPD (B15). Le temps où la cybersécurité était « le problème de l'informatique » est juridiquement terminé.
  ```

---

### Arbitrage 14 : Ordre de volatilité — référence normative RFC 3227
- **Fichiers concernés :** `parcours-A-8sessions/supports-md/A_S07_support.md` (l. 128 ✓ exacte) ; `parcours-B-20sessions/supports-md/B_S18_support.md` (le contenu est à la ligne 163, pas aux lignes 135-145 qui correspondent au schéma PICERL)
- **Statut de l'arbitrage :** **[CONFIRMÉ]** (gravité requalifiée MAJEUR → MINEUR ; patch de l'audit allégé)
- **Analyse critique :**
  - Vérifié : ni « RFC 3227 » ni « ISO 27037 » n'apparaissent dans le corpus, alors que le contenu enseigné EST l'ordre de volatilité de la **RFC 3227 §2.1** (complétée par **ISO/IEC 27037:2012** pour l'identification/collecte/préservation des preuves numériques) et que le corpus cite systématiquement ses sources partout ailleurs (NIST SP 800-61, art. 323-1 du Code pénal, LOPMI…). L'ajout de la référence est justifié — mais une citation manquante n'induit aucune erreur technique : MINEUR, pas MAJEUR.
  - Le remplacement intégral proposé par l'audit (liste brute en 6 points calquée sur la RFC) est rejeté : il supprimerait les annotations didactiques du cours (pourquoi la RAM compte : mots de passe en clair, clés de chiffrement, connexions actives), qui sont sa vraie valeur pour un débutant. Détail : l'ordre simplifié du cours (RAM citée avant l'état réseau) est un choix pédagogique compatible avec la pratique réelle (une capture mémoire moderne embarque processus et connexions) — la RFC 3227 groupe d'ailleurs mémoire, tables de routage/ARP et processus dans le même niveau de volatilité.
- **Action retenue :** Ajouter la double référence normative en tête des deux passages, conserver les listes pédagogiques. **Appliqué.**
- **Patch / Remplacement exact :**
  ```diff
  # A_S07_support.md (§2.A)
  - Les données informatiques s'effacent à des vitesses différentes. Les enquêteurs collectent d'abord les données les plus volatiles :
  + Les données informatiques s'effacent à des vitesses différentes. Principe canonique de l'investigation numérique — formalisé par la **RFC 3227** (*Guidelines for Evidence Collection and Archiving*) et la norme **ISO/IEC 27037** —, la collecte procède toujours du plus volatil au plus stable :

  # B_S18_support.md (§5)
  - L'investigation collecte les preuves du plus volatil au plus stable (l'**ordre de volatilité**) : RAM → état réseau → disques...
  + L'investigation collecte les preuves du plus volatil au plus stable (l'**ordre de volatilité**, formalisé par la **RFC 3227** et la norme **ISO/IEC 27037**) : RAM → état réseau → disques...
  ```

---

### Arbitrage 15 : « Isoler, jamais éteindre » — exception des malwares destructeurs (wipers)
- **Fichiers concernés :** `parcours-A-8sessions/outils/A_scripts_demo.md` (l. 222 ✓ exacte) ; `parcours-B-20sessions/supports-md/B_S18_support.md` (le passage réel est l'encadré des lignes 156-161, pas la ligne 110)
- **Statut de l'arbitrage :** **[NUANCÉ / SIMPLIFICATION PÉDAGOGIQUE]**
- **Analyse critique :**
  - La règle enseignée est la doctrine standard, conforme aux guides ANSSI/CERT-FR sur les rançongiciels (isoler du réseau sans éteindre, préserver la mémoire) et au NIST SP 800-61 : la conserver intacte côté apprenant est la bonne décision — un scénario voté de niveau débutant ne doit pas être brouillé par une exception rarissime.
  - La nuance de l'audit est néanmoins techniquement fondée (wiper actif en cours d'effacement : la coupure d'alimentation peut être l'ultime recours, au prix des preuves en RAM — HermeticWiper/CaddyWiper, 2022, sont des références réelles) et a sa place **en aparté mentor**, comme l'audit le suggère lui-même (« les formateurs seniors doivent apporter la nuance »).
  - Vérification de la source d'autorité citée : l'audit invoque « NIST SP 800-61 Rev. 2 » — attention, cette révision est remplacée depuis avril 2025 par la **Rev. 3** (réorganisée autour des fonctions du CSF 2.0). La précision de révision a été ajoutée au support B18 par la même occasion.
- **Action retenue :** Modifier avec nuance — aparté mentor ajouté aux deux emplacements réels (sans toucher à la règle d'or ni aux mécaniques de vote), et précision « (Rev. 2 / Rev. 3 2025) » sur la référence SP 800-61 de B18. **Appliqué.**
- **Patch / Remplacement exact :**
  ```diff
  # B_S18_support.md (encadré « Ne jamais éteindre... », 4e puce ajoutée)
  + *   *Nuance d'expert (pour le mentor, si la question vient)* : face à un malware purement **destructeur** (*wiper* type HermeticWiper) en train d'effacer physiquement les disques, couper l'alimentation peut devenir l'ultime recours pour sauver ce qui n'est pas encore détruit — arbitrage exceptionnel, au prix des preuves en RAM. Pour un rançongiciel, la règle reste : isoler, ne pas éteindre.

  # A_scripts_demo.md (Démo 7, après la branche B)
  + * *Aparté mentor (si un participant avancé objecte le cas des malwares destructeurs)* : face à un *wiper* en train d'effacer physiquement les disques (type HermeticWiper), couper l'alimentation peut être l'ultime recours pour sauver ce qui reste — arbitrage exceptionnel de niveau expert, au prix des preuves en RAM. Pour un rançongiciel, la règle enseignée ici reste la bonne : isoler, ne pas éteindre.

  # B_S18_support.md (§4)
  - Le guide **NIST SP 800-61** structure la réponse en **4 phases** ; ...
  + Le guide **NIST SP 800-61** (Rev. 2 — la Rev. 3 de 2025 réorganise les mêmes fondamentaux autour des fonctions du CSF 2.0 vu en B13) structure la réponse en **4 phases** ; ...
  ```

---

### Arbitrage 16 : Sémantique des codes HTTP dans les journaux (B17)
- **Fichier concerné :** `parcours-B-20sessions/supports-md/B_S17_support.md` (le log est aux lignes 143-149, pas 110-120 ; l'URL citée « app.php » n'existe pas — le fichier réel utilise `product.php`)
- **Statut de l'arbitrage :** **[FAUX POSITIF]** (correctif de surcroît destructeur)
- **Analyse critique :**
  - L'exigence de l'audit — « montrer la différence entre une tentative bloquée (400/403/404) et une tentative réussie (200 avec données exfiltrées) » — est **précisément la conception actuelle de l'atelier** : la ligne 5 du log montre une traversée de répertoires **bloquée avec un code 400**, les lignes 3-4 montrent une injection SQL **réussie avec un code 200 et une taille de réponse croissante** (851 → 4522 → 6817 octets) ; le sondage n°3 fait explicitement raisonner les apprenants sur ce couple code + volume, et la section « Anatomie d'une ligne de log » (l. 94) enseigne en amont la sémantique 200/400/403/404/500 (conforme RFC 9110).
  - Appliquer le « correctif » de l'audit (traversée en 403, SQLi en 500) aurait **cassé la clé de correction du sondage n°3** (« Oui : le serveur a répondu favorablement… ») et détruit la leçon centrale de l'atelier : une injection SQL *réussie* renvoie typiquement 200 — le 500 signale au contraire une tentative qui a fait échouer la requête SQL. Le remplacement aurait donc dégradé la justesse ET la pédagogie.
- **Action retenue :** Rejeter la remarque. Aucun correctif.
- **Patch / Remplacement exact :** aucun.

---

### Arbitrage 17 : Hexade de Parker absente du quiz A
- **Fichier concerné :** `parcours-A-8sessions/outils/A_banque_quiz.md` (l. 35 ✓ exacte)
- **Statut de l'arbitrage :** **[FAUX POSITIF]**
- **Analyse critique :**
  - L'explication en place est exacte et remplit parfaitement son rôle (déjouer le piège authentification/autorisation vs triade C-I-D). L'audit ne relève d'ailleurs **aucune erreur** — uniquement une « absence de mention » d'un prolongement théorique.
  - L'hexade de Parker (Parker, *Fighting Computer Crime*, 1998) est un modèle alternatif minoritaire, absent des référentiels sur lesquels le cours s'aligne — et absent de la source même que l'audit invoque : **NIST SP 800-12 Rev. 1 est construit sur la triade CIA** et ne traite pas de l'hexade. L'ajouter dans l'explication d'un QCM de session 1 pour grands débutants serait une charge cognitive sans bénéfice d'évaluation.
- **Action retenue :** Rejeter la remarque. Aucun correctif. (Libre au mentor d'en parler en question ouverte — hors banque de quiz.)
- **Patch / Remplacement exact :** aucun.

---

### Arbitrage 18 : Complétude des 280 questions de validation
- **Fichiers concernés :** `A_banque_quiz.md`, `B_banque_quiz.md`
- **Statut de l'arbitrage :** **[FAUX POSITIF]** (non-anomalie)
- **Analyse critique :**
  - Contre-vérification indépendante : **80 questions** (parcours A) + **200 questions** (parcours B), soit 280, chacune dotée d'une ligne « Réponse correcte » (80/80 et 200/200). Le constat de conformité de l'audit est confirmé — mais un constat de conformité n'est pas une anomalie et n'appelle aucun « ajustement ».
  - La recommandation associée (« répercuter NIST CSF 2.0 et ISO 27001:2022 dans les questions de gouvernance ») est **déjà sans objet** : la banque B contient une question dédiée au CSF 2.0 dont l'explication précise que « réciter “les 5 fonctions” est devenu obsolète en 2024 », et les questions ISO 27001 portent sur le SMSI/PDCA (invariants entre éditions).
- **Action retenue :** Rejeter (aucune action).
- **Patch / Remplacement exact :** aucun.

---

### Arbitrage 19 : Taux d'implication du facteur humain (Verizon DBIR)
- **Fichiers concernés :** `A_banque_quiz.md` (l. 73-80 ✓), `B_S01_support.md` (l. 38 et 131 — pas 120)
- **Statut de l'arbitrage :** **[FAUX POSITIF]** (le correctif proposé aurait introduit une erreur)
- **Analyse critique :**
  - Le corpus applique déjà la seule parade durable contre la péremption des statistiques : **citer l'édition** (« Verizon DBIR **2025** ») et donner le chiffre de cette édition (« environ 60 % » — conforme au DBIR 2025, qui chiffre l'élément humain à ~60 % des violations). Les encadrés s'intitulent d'ailleurs « Chiffres clés à retenir (**sources et années citées**) ».
  - Les chiffres avancés par l'audit (82 % en 2022, 74 % en 2023, 68 % en 2024) sont exacts pour les éditions antérieures, mais sa recommandation — reformuler en « environ deux tiers à trois quarts selon les rapports annuels » — **contredirait le chiffre de l'édition 2025 explicitement citée** (60 % n'est ni « deux tiers » ni « trois quarts ») et rendrait la clé de réponse du QCM (« Environ 60 % ») incohérente avec son propre énoncé. Le correctif aurait créé l'imprécision qu'il prétendait prévenir.
- **Action retenue :** Rejeter la remarque. Aucun correctif. (Consigne de maintenance déjà implicite dans le corpus : mettre à jour chiffre + millésime ensemble à chaque édition.)
- **Patch / Remplacement exact :** aucun.

---

## 3. Récapitulatif des correctifs effectivement appliqués

| Fichier | Modifications |
| :--- | :--- |
| `parcours-B-20sessions/supports-md/B_S10_support.md` | Scission RSA / Diffie-Hellman dans l'aide-mémoire ; attribution de la signature à RSA (§1) ; reformulation neutre de la signature (note mentor, glossaire, §3, aide-mémoire) + précision d'expert RSA-PSS/ECDSA/Ed25519 ; note mentor modes AES (GCM/AEAD vs ECB, lien cas Adobe 3DES-ECB) |
| `parcours-B-20sessions/slides/B_S10_slides_spec.md` | Slide 5 : échange de clés (DH, RSA) / signature (RSA) ; slide 8 : « sceller l'empreinte » + vérification reformulée |
| `parcours-B-20sessions/plans-de-seance/B_S10_plan.md` | Séquence 3 : mécanique de signature reformulée (cohérence support/slides/plan) |
| `parcours-B-20sessions/outils/B_scripts_demo.md` | Démo 5 : note mentor iptables-nft / nftables avec prérequis table + chaîne |
| `parcours-B-20sessions/supports-md/B_S13_support.md` | ISO/IEC 27001:2022 + Annexe A (93 mesures, 4 thèmes) au développement et au glossaire ; calendrier de notification NIS2 (24 h / 72 h / 1 mois, art. 23) en note mentor |
| `parcours-A-8sessions/supports-md/A_S07_support.md` | Référence RFC 3227 + ISO/IEC 27037 en tête de l'ordre de volatilité |
| `parcours-B-20sessions/supports-md/B_S18_support.md` | Référence RFC 3227 + ISO/IEC 27037 ; nuance d'expert « wiper » (aparté mentor) ; précision NIST SP 800-61 Rev. 2 / Rev. 3 (2025) |
| `parcours-A-8sessions/outils/A_scripts_demo.md` | Démo 7 : aparté mentor « wiper » après la branche B (règle d'or inchangée) |

**Aucune modification** n'a été apportée aux fichiers visés par les constats rejetés (B_S07, B_S05, A_S03, A_S04, A_S05, B_S15, B_S17, banques de quiz, B_S13 slides) : leurs contenus sont conformes à l'état de l'art tel que vérifié.

---

## 4. Conclusion du contre-audit

Le rapport d'audit initial surestime très largement le nombre et la gravité des anomalies : **11 de ses 19 constats détaillés sont des faux positifs** (citations hallucinées, extraits tronqués, contenus déjà conformes, constats de conformité comptés comme anomalies), et **2 de ses correctifs auraient introduit des régressions techniques** (AES-XTS crédité d'une intégrité qu'il n'offre pas ; commande `nft` inexécutable sans création préalable de table/chaîne) tandis qu'un troisième aurait cassé un exercice noté (sondage n°3 de B17) et qu'un quatrième aurait faussé le modèle OSI qu'il prétendait préciser.

Les 8 points retenus (2 confirmés, 4 nuancés, 2 à correctif retravaillé) ont été corrigés avec des patchs minimaux, sourcés et non régressifs, harmonisés sur l'ensemble support / plan de séance / slides des sessions concernées. Le corpus pédagogique en sort conforme aux référentiels en vigueur (NIST CSF 2.0, ISO/IEC 27001:2022, RGPD art. 83, NIS2 art. 23, RFC 3227/8017/8032/9110, guides ANSSI) — sans sacrifier la clarté didactique qui fait sa qualité première.
