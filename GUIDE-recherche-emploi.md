# Organiser sa recherche d'emploi avec Claude

Guide pratique pour structurer une recherche d'emploi avec Claude et le skill [cv-builder](cv-builder/SKILL.md) : un **projet Claude dédié**, un **dossier dédié sur l'ordinateur**, et les **bons documents de base** déposés dès le départ. Avec cette organisation, Claude a toujours le contexte (CV, diplômes, postes visés) et vous n'avez plus à tout réexpliquer à chaque conversation.

## En bref

| Étape | Temps | Résultat |
|---|---|---|
| 1. Créer le dossier sur l'ordinateur | 5 min | Tous vos documents au même endroit, rangés |
| 2. Y déposer les documents de base | 15 min | CV, LinkedIn, diplômes, certificats prêts à l'emploi |
| 3. Créer le projet Claude « Recherche d'emploi » | 5 min | Claude connaît votre profil dans toutes les conversations du projet |
| 4. Relier le dossier à Claude Desktop | 1 min | Claude lit vos fichiers et y range ce qu'il produit |
| 5. Une conversation par candidature | au fil de l'eau | Historique clair, CV et lettre adaptés à chaque offre |

## 1. Créer le dossier « Recherche-emploi » sur l'ordinateur

Copiez le kit [`kit-recherche-emploi/`](kit-recherche-emploi/) de ce dépôt, ou créez cette arborescence :

```
Recherche-emploi/
├── 00-Base/                 # Documents de référence, rarement modifiés
│   ├── CV/                  # CV actuel (.docx + .pdf), anciennes versions
│   ├── LinkedIn/            # Export PDF du profil LinkedIn
│   ├── Diplomes/            # Diplômes, relevés de notes
│   ├── Certificats/         # Certifications, MOOC, attestations de formation
│   ├── Attestations/        # Certificats de travail, attestations employeurs
│   ├── Recommandations/     # Lettres de recommandation, contacts de référence
│   ├── Portfolio/           # Réalisations, études de cas, présentations
│   └── Photo/               # Photo professionnelle (CV design, LinkedIn)
├── 01-Cible/                # Postes visés, entreprises, mots-clés
├── 02-Candidatures/         # Un sous-dossier par candidature
│   └── 2026-11-NomEntreprise-Poste/
│       ├── annonce.pdf
│       ├── CV-NomEntreprise.docx
│       ├── lettre-NomEntreprise.docx
│       └── notes.md
├── 03-Suivi/                # Tableau de suivi des candidatures
├── 04-Entretiens/           # Préparation, questions, retours d'entretien
└── 05-Reseau/               # Contacts, messages d'approche, relances
```

Pourquoi cette structure : `00-Base` contient la vérité sur votre parcours (Claude s'y réfère et n'invente rien), `01-Cible` contient ce que vous visez (Claude en tire les mots-clés), et `02-Candidatures` garde chaque candidature isolée et datée.

## 2. Les documents de base à y déposer

À rassembler dès le départ, même si vous ne les utiliserez pas tous tout de suite :

- **CV actuel**, en .docx (modifiable) et en .pdf.
- **Export PDF du profil LinkedIn** (sur LinkedIn : votre profil, bouton « Plus » ou « Ressources », « Enregistrer au format PDF »).
- **Diplômes et relevés de notes**, en PDF.
- **Certifications et attestations de formation** (MOOC, certifications éditeur, langues : TOEIC, TOEFL...).
- **Certificats de travail et attestations employeurs**.
- **Lettres de recommandation** et liste de références (nom, rôle, accord pour être contacté).
- **Fiches de poste** de vos postes actuels et passés si vous les avez : elles décrivent votre périmètre réel.
- **Évaluations annuelles** ou bilans : utiles pour retrouver des résultats chiffrés.
- **Portfolio** : réalisations, études de cas, présentations, liens.
- **Photo professionnelle**.
- Dans `01-Cible` : 3 à 5 **offres d'emploi** représentatives du poste visé, et une liste d'**entreprises cibles**.

À ne pas déposer : pièce d'identité, numéro de sécurité sociale, RIB, bulletins de salaire complets. Ils ne servent pas à préparer une candidature. Si un recruteur les demande plus tard, transmettez-les directement par les canaux officiels.

## 3. Créer un projet Claude « Recherche d'emploi »

Dans Claude, créez un **projet** dédié. Tout ce qui s'y trouve est partagé par les conversations du projet.

1. **Instructions du projet** : collez et adaptez le modèle [`kit-recherche-emploi/instructions-projet-claude.md`](kit-recherche-emploi/instructions-projet-claude.md).
2. **Connaissances du projet** : ajoutez les fichiers clés de `00-Base` (CV actuel, export LinkedIn, diplômes et certifications principaux) et les offres de `01-Cible`.
3. **Mettez à jour** ces fichiers quand votre CV ou votre cible changent.

Ce que ça change : chaque nouvelle conversation du projet démarre avec votre parcours, vos documents et vos objectifs, sans rien recoller.

## 4. Relier le dossier à Claude Desktop

Avec l'application **Claude Desktop** :
- Dans une conversation, ouvrez le menu « + » à côté de la zone de message, puis choisissez **« Add folder »** et sélectionnez `Recherche-emploi`.
- Claude peut alors lire vos documents et enregistrer directement les CV, lettres et notes produits dans le bon sous-dossier de `02-Candidatures`.
- Pour lire et optimiser votre profil LinkedIn, connectez aussi l'extension **Claude in Chrome** (ou utilisez le navigateur intégré de Claude Desktop). Le skill cv-builder vous le demande au démarrage.

Sans Claude Desktop, le projet Claude suffit : vous téléchargez les fichiers produits et les rangez vous-même dans le dossier.

## 5. Routine de recherche

- **Une conversation par candidature**, dans le projet, nommée « Entreprise - Poste ». Collez l'annonce et demandez : « Adapte mon CV et ma lettre à cette offre ».
- **Tableau de suivi** dans `03-Suivi` : entreprise, poste, date, source, statut, prochaine action, contact. Claude peut le créer et le tenir à jour.
- **Préparation d'entretien** dans `04-Entretiens` : demandez à Claude les questions probables pour le poste et un entraînement en simulation.
- **Réseau** dans `05-Reseau` : messages d'approche LinkedIn, relances à J+7, remerciements après entretien.
- **Revue hebdomadaire** : « Fais le point sur mes candidatures de la semaine et propose les relances à faire ». Une tâche planifiée peut le faire automatiquement chaque lundi.

## Premières demandes à faire dans le projet

1. « Lis mes documents de base et fais-moi un diagnostic de mon CV et de mon LinkedIn pour un poste de [intitulé]. »
2. « Construis la carte de mots-clés à partir des offres de 01-Cible. »
3. « Refais mon CV au format ATS et optimise mon profil LinkedIn. »
4. « Crée mon tableau de suivi des candidatures. »
