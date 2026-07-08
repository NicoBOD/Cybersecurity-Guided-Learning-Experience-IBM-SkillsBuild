# Support de cours — Session 02 : Menaces, attaques & ingénierie sociale
Parcours : A 8 sessions  |  Module : Menaces Cyber  |  Niveau : Débutant

---

!!! abstract "Résumé"
    Les cyberattaques modernes ciblent de plus en plus le maillon réputé le plus vulnérable de la chaîne de sécurité : l'être humain. Ce support de cours détaille les mécanismes de l'ingénierie sociale, l'art de manipuler les personnes pour contourner les protections technologiques. Vous étudierez les principaux types de logiciels malveillants (*malware*), du rançongiciel destructeur au cheval de Troie discret. Nous décrypterons également les ressorts psychologiques du phishing (hameçonnage), du vishing (par téléphone) et les grandes étapes de la *Cyber Kill Chain*, le modèle théorique qui décrit le déroulement d'une attaque de son ciblage initial jusqu'à sa conclusion logique. L'objectif est de vous donner les clés pour identifier instantanément les signaux d'alerte et adopter des réflexes d'hygiène numérique indispensables.

---

## Glossaire de la session
* **Malware (Logiciel malveillant)** : Terme générique désignant tout programme conçu pour nuire à un système informatique (virus, ver, rançongiciel, etc.).
* **Ransomware (Rançongiciel)** : Malware qui chiffre les fichiers d'un utilisateur ou d'une entreprise et réclame le paiement d'une rançon en échange de la clé de déchiffrement.
* **Phishing (Hameçonnage)** : Technique frauduleuse par e-mail visant à tromper le destinataire pour lui soutirer des informations confidentielles (mots de passe, numéros de carte bancaire) en usurpant l'identité d'une marque de confiance.
* **Spear-phishing (Hameçonnage ciblé)** : Variante hautement personnalisée du phishing, ciblant un individu ou une organisation spécifique en exploitant des détails personnels collectés à l'avance.
* **Ingénierie sociale (Social Engineering)** : Manipulation psychologique visant à extorquer des informations confidentielles ou à faire accomplir des actions dangereuses à une victime.
* **Cyber Kill Chain** : Cadre conceptuel décrivant les 7 étapes chronologiques d'une cyberattaque réussie, développé par Lockheed Martin.

---

## Contenu théorique

### 1. La typologie des logiciels malveillants (*Malwares*)

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.


Les programmes malveillants revêtent des formes diverses selon l'objectif poursuivi par les attaquants :

#### A. Les Rançongiciels (*Ransomware*)
C'est la menace financière majeure pour les organisations. Le malware s'introduit dans le système, identifie les serveurs et les partages de fichiers critiques, puis applique un chiffrement fort. Les pirates réclament une rançon payable en cryptomonnaie en échange de l'outil de déchiffrement. Souvent, ils menacent également de divulguer publiquement les données volées (double extorsion).

#### B. Les Chevaux de Troie (*Trojan Horse*)
Un programme d'apparence légitime et inoffensive, mais contenant des fonctionnalités malveillantes cachées. Une fois installé par l'utilisateur, il ouvre des portes dérobées (*backdoors*) pour permettre aux pirates de prendre le contrôle de la machine à distance.

#### C. Les Logiciels espions (*Spyware / Keylogger*)
Des outils discrets installés sur le système pour collecter des données à l'insu de l'utilisateur. Un *keylogger* enregistre chaque touche pressée sur le clavier, capturant ainsi les mots de passe lors de leur saisie.

#### D. Les Vers (*Worms*)
Des malwares autonomes capables de se propager d'ordinateur en ordinateur à travers le réseau en exploitant des failles de sécurité, sans nécessiter d'interaction humaine (contrairement aux virus traditionnels qui nécessitent l'exécution d'un fichier hôte).

---

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

---

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

---

## Focus pratique : Anatomie d'un e-mail de phishing

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
* **Indice B** : Ton alarmiste incitant à agir sans réfléchir.
* **Indice C** : Le lien de destination réel (visible en survolant le bouton avec la souris sans cliquer) ne correspond pas au site officiel.

---

## Exercice d'application (self-paced)
**Titre** : Simulation de réaction face à un appel suspect (Vishing)

### Énoncé
Vous recevez un appel sur votre téléphone professionnel. L'appelant se présente comme "Marc de la direction informatique". Il vous explique que votre poste de travail émet des alertes réseau anormales et qu'il doit réinitialiser vos accès immédiatement. Il vous demande de lui lire le code à 6 chiffres que vous venez de recevoir par SMS sur votre mobile pour "valider la connexion de sécurité".

1. Identifiez la technique d'attaque utilisée.
2. Identifiez les leviers psychologiques exploités par l'attaquant.
3. Rédigez la réponse précise que vous feriez à l'interlocuteur et l'action immédiate que vous entreprendriez.

---

### Corrigé de l'exercice
1. **Technique utilisée** : Vishing (hameçonnage vocal / par téléphone) combiné à une tentative de contournement de la double authentification (demande du code SMS OTP).
2. **Leviers psychologiques** : L'autorité ("direction informatique") et l'urgence/peur ("votre poste émet des alertes réseau").
3. **Réaction attendue** :
   * Refuser catégoriquement de donner le code SMS (ne jamais partager un code MFA ou mot de passe).
   * Raccrocher poliment.
   * Contacter le support informatique interne en utilisant le numéro officiel répertorié dans l'annuaire d'entreprise (ne pas rappeler le numéro de l'appelant).
   * Signaler l'incident au responsable sécurité de l'entreprise.

---


## Exercice Bonus (Temps additionnel)
**Si vous avez terminé en avance (avant les 1h30 de session) :**
- **Objectif :** Mise en pratique autonome.
- **Consignes :** Réfléchissez à un exemple réel ou une actualité récente liée au sujet de cette session. Discutez en groupe de la manière dont les concepts vus s'appliquent à cet exemple.
- **Correction :** Le mentor validera les réflexions et apportera son expertise.

## Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **Malware (Logiciel malveillant)** | Terme générique désignant tout programme conçu pour nuire à un système informatique (virus, ver, rançongiciel, etc.). |
| **Ransomware (Rançongiciel)** | Malware qui chiffre les fichiers d'un utilisateur ou d'une entreprise et réclame le paiement d'une rançon en échange de la clé de déchiffrement. |
| **Phishing (Hameçonnage)** | Technique frauduleuse par e-mail visant à tromper le destinataire pour lui soutirer des informations confidentielles (mots de passe, numéros de carte bancaire) en usurpant l'identité d'une marque de confiance. |
| **Spear-phishing (Hameçonnage ciblé)** | Variante hautement personnalisée du phishing, ciblant un individu ou une organisation spécifique en exploitant des détails personnels collectés à l'avance. |
| **Ingénierie sociale (Social Engineering)** | Manipulation psychologique visant à extorquer des informations confidentielles ou à faire accomplir des actions dangereuses à une victime. |
| **Cyber Kill Chain** | Cadre conceptuel décrivant les 7 étapes chronologiques d'une cyberattaque réussie, développé par Lockheed Martin. |

## Ressources pour aller plus loin
* **IBM SkillsBuild** : Cours sur l'ingénierie sociale et la sensibilisation au phishing.
* **Cybermalveillance.gouv.fr (ou organisme national équivalent)** : Fiches pratiques sur les rançongiciels et l'hameçonnage.
* **MITRE ATT&CK Framework** : Base de connaissances mondiale sur les tactiques et techniques réelles des attaquants (consulter la matrice simplifiée).

* [ANSSI - Agence Nationale de la Sécurité des Systèmes d'Information](https://www.ssi.gouv.fr/)
* [Cybermalveillance.gouv.fr](https://www.cybermalveillance.gouv.fr/)
* [OWASP - Open Worldwide Application Security Project](https://owasp.org/)
