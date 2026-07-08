# Support de cours — Session 05 : Gouvernance, risque, conformité & vie privée
Parcours : A 8 sessions  |  Module : GRC & Vie Privée  |  Niveau : Débutant

---

!!! abstract "Résumé"
    La cybersécurité n'est pas uniquement une affaire de configurations techniques et de pare-feux. Pour être efficace, elle doit être intégrée dans la stratégie globale de l'entreprise à travers la Gouvernance, la Gestion des Risques et la Conformité (GRC). Ce support de cours détaille le cadre organisationnel de la cybersécurité. Vous découvrirez les référentiels de sécurité internationaux indispensables comme la norme ISO 27001 et le NIST CSF, qui guident les entreprises dans la structuration de leur sécurité. Nous étudierons ensuite la méthodologie de l'analyse de risques pour apprendre à prioriser les efforts de protection selon l'impact et la probabilité des menaces. Enfin, nous aborderons le RGPD, le règlement qui encadre la protection de la vie privée et des données personnelles, devenu un enjeu juridique et de réputation majeur pour toutes les organisations.

---

## Glossaire de la session
* **GRC (Gouvernance, Risques et Conformité)** : Approche intégrée visant à aligner l'informatique sur les objectifs de l'entreprise, à gérer les risques associés et à respecter les obligations réglementaires.
* **ISO/CEI 27001** : Norme internationale décrivant les exigences pour la mise en place d'un Système de Management de la Sécurité de l'Information (SMSI).
* **NIST CSF (Cybersecurity Framework)** : Cadre méthodologique du gouvernement américain structuré autour de 5 fonctions clés (Identifier, Protéger, Détecter, Répondre, Récupérer) pour améliorer la cybersécurité des infrastructures critiques.
* **PSSI (Politique de Sécurité des Systèmes d'Information)** : Document de référence formalisant les règles, directives et exigences de sécurité devant être respectées au sein d'une organisation.
* **RGPD (Règlement Général sur la Protection des Données)** : Texte réglementaire européen encadrant le traitement des données personnelles au sein de l'Union européenne ou ciblant ses citoyens.
* **Donnée personnelle** : Toute information se rapportant à une personne physique identifiée ou identifiable (ex. nom, e-mail, adresse IP, numéro de téléphone, données de santé).
* **CNIL (Commission Nationale de l'Informatique et des Libertés)** : Autorité administrative publique française chargée de veiller au respect de la protection des données personnelles (les équivalents existent dans chaque État européen).

---

## Contenu théorique

### 1. La Gouvernance et ses référentiels : ISO 27001 & NIST CSF

!!! info "À retenir"
    La maîtrise de ces concepts est fondamentale pour comprendre les enjeux pratiques de ce module.


La gouvernance cyber consiste à définir "qui fait quoi, comment et sous quelle autorité" pour sécuriser le patrimoine informationnel de l'entreprise.

#### A. La PSSI : La loi interne
La Politique de Sécurité des Systèmes d'Information (PSSI) est rédigée par le RSSI (Responsable de la Sécurité des SI) et signée par la Direction Générale. Elle a valeur de règlement intérieur. Elle fixe les règles obligatoires (ex. longueur des mots de passe, interdiction d'utiliser des clés USB personnelles, processus d'accueil des nouveaux arrivants).

#### B. ISO 27001 : L'approche par l'amélioration continue
La norme ISO 27001 n'impose pas de technologies précises, mais une méthode. Elle repose sur le principe de l'amélioration continue (Cycle PDCA : Plan-Do-Check-Act) afin de s'assurer que l'entreprise évalue constamment ses menaces et ajuste ses défenses. Une certification ISO 27001 prouve aux clients et partenaires que l'organisation gère sa sécurité de manière professionnelle.

#### C. Le NIST CSF : Le cadre pragmatique
Très utilisé à l'international, il structure la sécurité en 5 fonctions opérationnelles :

1. **Identifier** (*Identify*) : Cartographier les actifs, les systèmes, les données et les risques.
2. **Protéger** (*Protect*) : Mettre en œuvre les barrières de protection (sensibilisation, accès, chiffrement).
3. **Détecter** (*Detect*) : Identifier la survenue d'incidents de sécurité (journalisation, alertes).
4. **Répondre** (*Respond*) : Réagir aux incidents détectés (confinement, communication).
5. **Récupérer** (*Recover*) : Restaurer les systèmes pour revenir à la normale après un incident.

---

### 2. La Gestion des Risques : Évaluer pour mieux investir

Il est impossible de sécuriser un système à 100%. Le budget d'une entreprise étant limité, celle-ci doit prioriser ses investissements. C'est l'objectif de l'analyse de risques.

Un risque se caractérise par deux facteurs :

* **La Vraisemblance (ou Probabilité)** : Quelle est la chance que l'événement redouté se produise (de 1 - Très improbable à 4 - Presque certain) ?
* **L'Impact (ou Gravité)** : Si l'événement se produit, quels seront les dommages financiers, juridiques ou de réputation (de 1 - Négligeable à 4 - Catastrophique) ?

$$\text{Criticité brute} = \text{Vraisemblance} \times \text{Impact}$$

#### Les 4 stratégies de traitement du risque :
1. **Réduire** : Mettre en place des mesures de sécurité pour baisser l'impact ou la vraisemblance (ex. installer un pare-feu).
2. **Transférer** : Partager le risque avec un tiers (ex. souscrire une cyber-assurance qui paiera les frais en cas d'attaque).
3. **Éviter** : Supprimer l'activité qui génère le risque (ex. renoncer à héberger un fichier contenant des données hautement sensibles).
4. **Accepter** : Décider de ne rien faire car le coût de la protection est plus élevé que le coût de l'impact potentiel du risque.

---

### 3. La Conformité et la Vie Privée : Le RGPD

Le RGPD impose des règles strictes à toute entité (publique ou privée) collectant ou traitant des données personnelles.

#### Les 4 grands principes du RGPD :
1. **La finalité** : Les données doivent être collectées pour un but précis et légitime, et ne pas être réutilisées à d'autres fins (ex. si un client donne son numéro pour une livraison, l'entreprise ne peut pas le revendre pour de la prospection publicitaire sans son accord).
2. **La minimisation** : Collecter uniquement les données strictement nécessaires (ne pas demander le numéro de sécurité sociale pour s'inscrire à une newsletter).
3. **La transparence et le consentement** : L'utilisateur doit donner son accord explicite (bouton d'acceptation actif, pas de case pré-cochée) et savoir exactement ce qui sera fait de ses données.
4. **Les droits des personnes** : Droit d'accès (savoir quelles données sont conservées), droit de rectification (les modifier) et droit à l'oubli (demander leur suppression définitive).

En cas de non-respect, les autorités de contrôle (comme la CNIL en France) peuvent prononcer des amendes administratives s'levant jusqu'à 20 millions d'euros ou 4% du chiffre d'affaires mondial annuel de l'entreprise.

---

## Focus pratique : Utilisation de la matrice 4x4 de cotation des risques

Les entreprises projettent les risques identifiés dans une matrice visuelle pour cibler les risques prioritaires (ceux situés dans la zone rouge).

```text
    Impact ➔
    [ 1:Négligeable ] [ 2:Modéré ] [ 3:Majeur ] [ 4:Critique ]
  Vraisemblance ⬇
  [ 4:Presque sûr ]  (Moyen-4)    (Moyen-8)   (ÉLEVÉ-12)  (CRITIQUE-16)
  [ 3:Probable    ]  (Faible-3)   (Moyen-6)   (Moyen-9)   (ÉLEVÉ-12)
  [ 2:Improbable  ]  (Faible-2)   (Faible-4)  (Moyen-6)   (Moyen-8)
  [ 1:Très rare   ]  (Faible-1)   (Faible-2)  (Faible-3)  (Moyen-4)
```

* **Zone Rouge (12-16)** : Traitement obligatoire et immédiat.
* **Zone Orange (4-9)** : Surveillance active et réduction planifiée.
* **Zone Verte (1-3)** : Acceptation du risque sous réserve de suivi.

---

## Exercice d'application (self-paced)
**Titre** : Analyse et traitement d'un scénario de risque PME

### Énoncé
Une PME de 15 salariés stocke son fichier client contenant les coordonnées et numéros de cartes de fidélité de ses 10 000 clients sur un ordinateur connecté à Internet sans antivirus à jour et dont le mot de passe d'accès est "123456".

1. Identifiez la vulnérabilité et la menace dans cette situation.
2. À l'aide de la matrice de focus pratique ci-dessus, attribuez une note de vraisemblance (1 à 4) et d'impact (1 à 4) au risque de vol et de divulgation de ce fichier client. Calculez sa criticité brute.
3. Proposez trois mesures concrètes de réduction de ce risque.

---

### Corrigé de l'exercice
1. **Identification** :
   * *Vulnérabilités* : Absence d'antivirus à jour, mot de passe d'accès extrêmement faible ("123456").
   * *Menace* : Un cybercriminel ou un robot automatisé qui scanne Internet à la recherche de machines mal configurées pour y dérober des données.
2. **Cotation du risque** :
   * *Vraisemblance* : **4 (Presque sûr)**. Avec un mot de passe aussi trivial et sans protection, la machine sera compromise très rapidement.
   * *Impact* : **3 (Majeur)**. La divulgation des coordonnées de 10 000 clients nuira gravement à la réputation de la PME et l'exposera à des sanctions de la CNIL (non-respect des obligations de sécurité du RGPD).
   * *Criticité brute* : $4 \times 3 = 12$ (Risque situé dans la zone Élevée / Rouge de la matrice).
3. **Mesures de réduction** :
   * Forcer le changement du mot de passe pour une phrase de passe complexe (ex. minimum 14 caractères).
   * Installer et maintenir à jour un logiciel antivirus/antimalware de niveau professionnel.
   * Chiffrer le dossier contenant le fichier client et n'accorder l'accès qu'aux seuls collaborateurs autorisés.

---


## Exercice Bonus (Temps additionnel)
**Si vous avez terminé en avance (avant les 1h30 de session) :**
- **Objectif :** Mise en pratique autonome.
- **Consignes :** Réfléchissez à un exemple réel ou une actualité récente liée au sujet de cette session. Discutez en groupe de la manière dont les concepts vus s'appliquent à cet exemple.
- **Correction :** Le mentor validera les réflexions et apportera son expertise.

## Aide-mémoire / Fiche de révision

| Concept Clé | Définition synthétique |
| :--- | :--- |
| **GRC (Gouvernance, Risques et Conformité)** | Approche intégrée visant à aligner l'informatique sur les objectifs de l'entreprise, à gérer les risques associés et à respecter les obligations réglementaires. |
| **ISO/CEI 27001** | Norme internationale décrivant les exigences pour la mise en place d'un Système de Management de la Sécurité de l'Information (SMSI). |
| **NIST CSF (Cybersecurity Framework)** | Cadre méthodologique du gouvernement américain structuré autour de 5 fonctions clés (Identifier, Protéger, Détecter, Répondre, Récupérer) pour améliorer la cybersécurité des infrastructures critiques. |
| **PSSI (Politique de Sécurité des Systèmes d'Information)** | Document de référence formalisant les règles, directives et exigences de sécurité devant être respectées au sein d'une organisation. |
| **RGPD (Règlement Général sur la Protection des Données)** | Texte réglementaire européen encadrant le traitement des données personnelles au sein de l'Union européenne ou ciblant ses citoyens. |
| **Donnée personnelle** | Toute information se rapportant à une personne physique identifiée ou identifiable (ex. nom, e-mail, adresse IP, numéro de téléphone, données de santé). |
| **CNIL (Commission Nationale de l'Informatique et des Libertés)** | Autorité administrative publique française chargée de veiller au respect de la protection des données personnelles (les équivalents existent dans chaque État européen). |

## Ressources pour aller plus loin
* **IBM SkillsBuild** : Modules sur les principes de la GRC et le RGPD.
* **CNIL (France)** : Guide de la sécurité des données personnelles (un outil indispensable pour auditer sa conformité).
* **NIST (USA)** : Documentation officielle du Cybersecurity Framework v2.0.

* [ANSSI - Agence Nationale de la Sécurité des Systèmes d'Information](https://www.ssi.gouv.fr/)
* [Cybermalveillance.gouv.fr](https://www.cybermalveillance.gouv.fr/)
* [OWASP - Open Worldwide Application Security Project](https://owasp.org/)
