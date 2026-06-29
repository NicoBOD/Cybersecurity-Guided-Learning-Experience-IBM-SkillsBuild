# Support de cours — Session 08 : Projet capstone — restitution & synthèse
Parcours : A 8 sessions  |  Module : Consolidation & Soutenance  |  Niveau : Débutant / Intermédiaire

---

## Résumé exécutif
Le Projet Capstone constitue l'aboutissement de votre parcours de formation de 8 sessions. C'est l'occasion de démontrer votre autonomie et de mettre en pratique l'ensemble des compétences acquises (triade CIA, analyse de menaces, sécurité des réseaux, cloud, RGPD, gestion des risques et réponse aux incidents) en vous confrontant à une étude de cas d'entreprise réelle ou fictive (une PME ayant besoin d'un audit de sécurité). Ce support de cours vous guidera dans la structuration de vos livrables finaux et dans la préparation de votre présentation orale. Vous y apprendrez à formaliser une feuille de route de remédiation cyber réaliste et à pitcher vos recommandations devant un jury d'évaluation (composé de votre mentor et de vos pairs). C'est la dernière étape pour décrocher votre badge numérique d'achèvement de formation.

---

## Glossaire de la session
* **Projet Capstone** : Un travail d'évaluation final synthétisant l'ensemble des compétences pratiques et théoriques développées tout au long d'un parcours d'apprentissage.
* **Feuille de route de remédiation (Remediation Roadmap)** : Plan d'action chronologique et priorisé décrivant les étapes techniques et organisationnelles à accomplir pour corriger les vulnérabilités identifiées lors d'un audit.
* **Synthèse managériale (Executive Summary)** : Courte introduction synthétique (1 page max) rédigée à l'intention des dirigeants de l'entreprise, résumant les menaces majeures découvertes et le budget requis, exempte de jargon technique trop complexe.
* **Hygiène informatique (Cyber Hygiene)** : Ensemble des règles élémentaires de sécurité à appliquer de manière systématique pour minimiser la majorité des cybermenaces courantes (ex. mises à jour, mots de passe complexes, sauvegardes).
* **Évaluation par les pairs (Peer Review)** : Méthode d'évaluation collaborative où les apprenants analysent et notent de manière constructive le travail de leurs pairs à l'aide d'une grille de critères partagée.

---

## Contenu théorique

### 1. Objectifs du Projet Capstone

L'objectif principal du Projet Capstone est de vous placer dans la posture d'un consultant en cybersécurité junior chargé d'accompagner une PME dans sa transition sécuritaire. Vous devez être capable de traduire des concepts techniques en enjeux métiers intelligibles pour un chef d'entreprise (qui n'est pas un informaticien).

Vos recommandations doivent respecter trois critères :

* **La pertinence technique** : Vos solutions doivent cibler les failles réelles identifiées dans l'énoncé.
* **Le réalisme économique** : Une PME de 20 personnes ne peut pas s'offrir un SOC interne disponible 24/7 de 10 personnes ou des outils de chiffrement coûtant des dizaines de milliers d'euros. Vous devez privilégier l'hygiène informatique et des solutions managées externes ou open-source à coût modéré.
* **L'acceptabilité humaine** : Vos propositions ne doivent pas paralyser le travail quotidien des employés de la PME sous peine d'être contournées (ex. éviter de forcer le changement hebdomadaire des mots de passe sans gestionnaire de mots de passe adapté).

---

### 2. Structurer son rapport d'évaluation finale (Livrable écrit)

Votre rapport d'évaluation (3 à 5 pages) doit être organisé selon la structure standard suivante :

1. **Executive Summary (Synthèse managériale)** : Un résumé de 500 mots maximum à l'attention du dirigeant détaillant le niveau de risque global de la PME et la feuille de route de remédiation (priorités, budgets et bénéfices).
2. **Analyse de risques** : Présentation des 3 risques majeurs menaçant la PME (exfiltration de données clients, rançongiciel paralysant, ou vol d'identité d'administration) avec cotation en criticité brute.
3. **Diagnostic technique et organisationnel** : Analyse critique de l'architecture réseau actuelle de la PME, de la gestion de ses données/sauvegardes et de son niveau de conformité RGPD.
4. **Recommandations détaillées** : Propositions de mesures techniques et d'organisation (politique de mots de passe, segmentation réseau, politique de sauvegarde 3-2-1, processus de gestion des patchs et sensibilisation des équipes).
5. **Feuille de route et plan d'action** : Calendrier de déploiement des recommandations classées en trois catégories : Court terme (priorités immédiates à coût zéro/faible), Moyen terme (projets d'infrastructure réseau/cloud) et Long terme (surveillance continue et audits annuels).

---

### 3. Réussir son pitch de soutenance (Livrable oral)

Vous disposez de **10 minutes strictes** pour convaincre votre jury. Une bonne soutenance orale s'appuie sur une répartition temporelle rigoureuse de vos diapositives :

* **Minute 1** : Présentation du groupe et résumé du contexte de la PME.
* **Minutes 2–3** : Présentation des risques prioritaires (les "zones rouges" de votre matrice de risques).
* **Minutes 4–7** : Vos recommandations concrètes (divisées de manière équilibrée : Sécurité Réseau, Cloud & Identités, Gouvernance & RGPD).
* **Minutes 8–9** : Présentation de la feuille de route chronologique et du plan de réponse aux incidents.
* **Minute 10** : Conclusion et ouverture vers la phase de questions-réponses.

*Conseils de posture* : Ne lisez pas vos notes ou vos diapositives. Soyez clairs, synthétiques et justifiez vos choix en liant chaque mesure technique à une réduction concrète de risque financier ou d'impact juridique pour la PME.

---

## Focus pratique : Modèle de feuille de route de remédiation chronologique

La feuille de route permet d'organiser dans le temps le déploiement des recommandations de sécurité proposées à l'issue de l'audit.

```text
  [ PRIORITÉS IMMÉDIATES - Mois 1 ] ➔ 1. Forcer l'activation du MFA sur tous les accès.

                                         2. Mettre en place un gestionnaire de mots de passe.
                                         3. Déployer un antivirus mis à jour sur tous les postes.
                                         
  [ PROJETS MOYEN TERME - Mois 2-3 ] ➔  1. Configurer la règle de sauvegarde 3-2-1 (copie cloud).

                                         2. Segmenter le réseau de la PME (VLANs / DMZ).
                                         3. Rédiger la PSSI de base et le registre RGPD.
                                         
  [ CONTINU & LONG TERME - Mois 6+ ] ➔  1. Lancer une campagne annuelle de sensibilisation au phishing.

                                         2. Externaliser la surveillance vers un SOC managé.
                                         3. Planifier un scan de vulnérabilités bi-annuel.
```

---

## Exercice d'application (self-paced)
**Titre** : Préparer la réponse aux objections d'un dirigeant de PME

### Énoncé
Dans le cadre de votre soutenance, le chef d'entreprise fictif (joué par le mentor) vous interrompt et vous oppose l'objection suivante :
*"Vous me demandez d'activer l'authentification multifacteur (MFA) pour tous les accès cloud de mes commerciaux et de mes comptables. Mais cela va ralentir leur travail quotidien de devoir manipuler leur téléphone personnel toutes les 5 minutes pour entrer des codes SMS. Je refuse de pénaliser la productivité de mes équipes pour des craintes théoriques de piratage."*

Rédigez un argumentaire de réponse structuré en 3 points pour lever cette objection tout en maintenant votre recommandation.

---

### Corrigé de l'exercice
1. **Point 1 : Reconnaissance et empathie (Valider la préoccupation de l'interlocuteur)** :
   * *Argument* : "Je comprends tout à fait votre préoccupation concernant le confort de travail et la productivité de vos équipes. Une sécurité qui paralyse l'activité est une sécurité qui sera contournée."
2. **Point 2 : Ajustement technique pour minimiser l'impact (Démontrer la flexibilité)** :
   * *Argument* : "Pour éviter de ralentir vos commerciaux, nous ne leur demanderons pas de s'authentifier par MFA à chaque connexion, mais uniquement lors de la première connexion depuis un nouvel équipement ou s'ils se connectent hors de vos locaux de l'entreprise (en déplacement). De plus, l'utilisation de notifications push rapides sur application d'authentification évite la saisie manuelle de longs codes SMS."
3. **Point 3 : Rappel du coût du risque (Démontrer le bénéfice/risque financier)** :
   * *Argument* : "Le coût en temps d'une validation MFA est de 5 secondes par jour. Le coût moyen d'une compromission de compte de messagerie (phishing) pour une PME est de plusieurs milliers d'euros en factures détournées ou en rançon, sans compter la paralysie potentielle de votre activité pendant plusieurs jours si vos serveurs sont chiffrés. Le MFA est votre assurance la plus rentable pour éviter ce scénario."

---

## Ressources pour aller plus loin
* **IBM SkillsBuild** : Section méthodologie de gestion de projet informatique et restitution orale.
* **ANSSI** : "La cybersécurité pour les TPE/PME en 12 questions" (Guide pratique d'aide à la décision).
* **Cybermalveillance.gouv.fr** : Kit de sensibilisation aux risques numériques pour les entreprises.
