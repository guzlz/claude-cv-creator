---
name: cv-builder
description: "Créer un CV optimisé (format ATS ou format design avec photo) ET optimiser le profil LinkedIn de l'utilisateur pour le poste visé (mots-clés, titre, À propos, compétences, SEO LinkedIn et Google), en interviewant l'utilisateur et en lisant son profil LinkedIn via Claude in Chrome ou le navigateur intégré de Claude Desktop. Se déclenche sur : créer un CV, refaire mon CV, build a resume, make a CV, optimiser mon LinkedIn, améliorer mon profil LinkedIn, titre LinkedIn, section À propos, être trouvé par les recruteurs, chasseurs de têtes, ATS, Teamtailor, Workday, candidature cadre, recherche d'emploi, même si l'utilisateur ne parle que de LinkedIn ou que de CV."
---

# CV Builder : CV optimisé + profil LinkedIn optimisé

Outil qui interroge l'utilisateur sur son parcours, puis produit un CV d'une page (format ATS ou Design) et, si demandé, un profil LinkedIn réécrit pour être trouvé par les recruteurs sur le poste visé. Fonctionne en français ou en anglais.

Règle de fond : ne jamais inventer d'expérience, de chiffre, de compétence ou de titre. Tout vient de l'utilisateur ou de son profil existant. Un recruteur compare toujours le CV et le LinkedIn : une incohérence (dates, intitulés) coûte plus cher qu'un mot-clé manquant.

## Organisation de la recherche d'emploi

Le skill marche mieux quand la recherche d'emploi est organisée (guide complet dans `GUIDE-recherche-emploi.md` du dépôt) :
- **Dossier `Recherche-emploi` relié** (Claude Desktop, menu « + », « Add folder ») : lire d'abord `00-Base` (CV, export LinkedIn, diplômes, certificats, attestations) et `01-Cible` (offres visées) avant de poser des questions. Ranger chaque livrable dans `02-Candidatures/AAAA-MM-Entreprise-Poste/` et mettre à jour `03-Suivi/`.
- **Pas de dossier ni de projet dédié** : proposer en une ligne, sans bloquer la tâche, de créer un projet Claude « Recherche d'emploi » et un dossier `Recherche-emploi` sur l'ordinateur, pour que les prochaines candidatures partent avec tout le contexte.

## Étape 0 : Cadrage (poser ces questions d'abord, en une fois)

Utiliser AskUserQuestion si disponible, sinon une liste courte en texte.

1. **Objectif** : CV seul, LinkedIn seul, ou les deux (recommandé : les deux, cohérents entre eux).
2. **Environnement de travail** (à demander dès que LinkedIn est dans le périmètre) :
   « Travaillez-vous sur Claude Desktop (l'application installée sur votre ordinateur) ? L'extension Claude in Chrome est-elle connectée ? »
   Pourquoi on le demande : pour lire le profil LinkedIn, Claude a besoin d'un navigateur où l'utilisateur est connecté à LinkedIn. Voir l'Étape 1bis pour les trois cas. Vérifier aussi silencieusement quels outils navigateur sont réellement présents dans la session (outils `mcp__claude-in-chrome__*`, `mcp__Claude_Browser__*` / `mcp__remote-devices__Claude_Browser__*`, ou leurs outils `enable__...`) : la réponse de l'utilisateur et les outils disponibles doivent concorder avant de lancer quoi que ce soit.
3. **Poste visé** (indispensable pour les mots-clés) : intitulé exact, niveau de responsabilité, secteur, 2 à 5 annonces réelles si possible (liens ou texte collé). Sans annonce, proposer d'en chercher (connecteur Indeed ou recherche web) et les faire valider.
4. **Format du CV** (si CV dans le périmètre), en expliquant en 3-4 lignes l'enjeu ATS (voir `references/ats.md`, section « Explication courte à donner ») :
   - **(A) ATS / optimisé** : candidature en ligne, scale-ups, PME, grands groupes, cabinets de recrutement, et tous les postes à responsabilité. Sobre, une colonne, sans photo.
   - **(B) Design / joli** : commerces de proximité (restaurant, boulangerie, boutique, coiffeur...). Lu directement par un humain, souvent remis en main propre. Photo obligatoire.
5. Langue (FR / EN), pays ou marché visé, coordonnées (prénom nom, téléphone, email, ville, URL LinkedIn, portfolio).

## Étape 1 : Interview structuré (une section à la fois)

Si le profil LinkedIn a été lu (Étape 1bis), partir de son contenu : confirmer, corriger, puis creuser ce qui manque. Ne pas reposer des questions dont la réponse est déjà sur le profil.

Mener l'entretien comme un recruteur : une question, réponse, relance.

- **Expériences** (anti-chronologique) : intitulé, entreprise, dates (mois/année), lieu, contexte en une phrase, missions, **résultats chiffrés** (relancer : « combien ? », « quel gain ? », « quel périmètre : budget, équipe, CA ? »). Pour un poste à responsabilité, toujours demander le périmètre managérial et budgétaire.
- **Formations** : diplôme, établissement, années, spécialités utiles.
- **Compétences** : outils, compétences techniques et métier, méthodes, regroupées par thème.
- **Langues** + niveau. **Certifications, distinctions, projets** pertinents.
- Format Design uniquement : savoir-être, disponibilités, photo (voir Étape 2B).

Honnêteté : distinguer « maîtrisé en production » de « notions ». Ne jamais gonfler l'ancienneté ni un titre.

## Étape 1bis : Lire le profil LinkedIn (si LinkedIn dans le périmètre)

Trois cas, selon la réponse de l'Étape 0 et les outils présents :

| Situation | Méthode |
|---|---|
| Claude in Chrome connecté | Charger le skill `chrome-browser`, ouvrir un nouvel onglet sur `https://www.linkedin.com/in/me/`, lire la page en texte. L'utilisateur est déjà connecté dans son Chrome. |
| Claude Desktop sans l'extension | Charger le skill `built-in-browser`, ouvrir LinkedIn dans le navigateur intégré. L'utilisateur se connecte lui-même dans le panneau : Claude ne saisit jamais d'identifiant ni de mot de passe. |
| Ni l'un ni l'autre (claude.ai web ou mobile, ou outils absents) | Demander l'export PDF du profil (sur LinkedIn : Profil, bouton « Plus » / « Ressources », « Enregistrer au format PDF ») ou un copier-coller des sections. Mentionner en une ligne qu'avec Claude Desktop + Claude in Chrome la lecture serait automatique. |

Pendant la lecture :
- Lire uniquement le profil de l'utilisateur et les annonces qu'il a validées. Pas d'aspiration en masse ni de lecture de profils de tiers : c'est contraire aux conditions de LinkedIn et inutile ici.
- Dérouler « Voir plus » sur À propos, Expériences, Compétences (ouvrir les pages détaillées `/details/experience/` et `/details/skills/` si besoin) pour ne rien rater.
- Ne rien modifier sur LinkedIn à ce stade.

Restituer un diagnostic court : ce qui est bon, ce qui manque, écart avec le poste visé (mots-clés absents, titre trop vague, À propos vide, compétences non alignées, incohérences avec le CV).

## Étape 2A : Rédaction CV FORMAT ATS

Détails et justification dans `references/ats.md`.

**Ordre des sections** (intitulés standards) : Coordonnées (1 ligne, dans le corps) → Synthèse professionnelle → Compétences → Expérience → Formation → Certifications / Langues.
- **Synthèse** (3-4 lignes) : type de profil + périmètre + 3-5 mots-clés du poste visé.
- **Puces** : verbe d'action + action + impact chiffré. FR = infinitif (Piloter, Concevoir...) ; EN = verbe fort, présent pour le poste en cours, passé sinon. Un seul format de verbe par langue.
- **Mots-clés** : mots exacts des annonces ; chaque exigence clé à 3 endroits (Compétences + intitulé ou synthèse + puce qui le prouve). Développer une fois les acronymes peu connus (« ERP (Enterprise Resource Planning) »). Pas de bourrage.
- **Format** : une colonne ; aucun tableau, image, icône, photo, barre de niveau ; rien en en-tête/pied de page ; police standard (Calibri, Arial) 10-12 pt ; dates homogènes (« 09/2024 - 06/2026 ») ; une page (deux pour un profil très senior, en le signalant).

## Étape 2B : Rédaction CV FORMAT DESIGN (commerces de proximité)

Lecteur : un gérant pressé. Lisible en 10 secondes, soigné, chaleureux, crédible.
- **Photo obligatoire** : intégrée proprement en haut près du nom ; sinon un emplacement photo matérialisé (cadre portrait ~3:4, mention « Photo »). Jamais de CV Design sans l'un ou l'autre.
- Mise en page visuelle assumée : deux colonnes possibles, une couleur d'accent sobre, icônes discrètes.
- Mettre en avant savoir-être, disponibilités, expériences concrètes (encaissement, service, mise en rayon, gestion de rush...).
- Sections : Photo + Coordonnées → Accroche (1-2 lignes) → Expériences → Compétences & qualités → Formation → Langues / Disponibilités.
- Les règles ATS ne s'appliquent pas ici.

## Étape 2C : Optimisation LinkedIn

Suivre `references/linkedin.md` (le lire en entier avant de rédiger). En résumé :
1. Construire la **carte de mots-clés** à partir des annonces (principal = intitulé du poste visé, secondaires = compétences métier, tertiaires = outils, secteur, localisation).
2. Réécrire chaque section avec ces mots-clés placés là où ils pèsent dans la recherche LinkedIn Recruiter et dans Google : **titre**, **intitulés d'expérience**, **compétences**, **À propos** (premières lignes surtout), puis descriptions d'expérience.
3. Régler la visibilité (URL personnalisée, profil public visible des moteurs de recherche, localisation, Open to Work, photo, bannière).
4. Vérifier la cohérence avec le CV (mêmes intitulés, dates, chiffres).
5. **Accompagner la mise à jour réelle du profil**, section par section, en commençant par l'en-tête (photo, bannière, titre, poste actuel, localisation, coordonnées, URL), puis Open to Work, À propos, Sélection, chaque expérience, formation, certifications, compétences, recommandations et visibilité (ordre détaillé : section 5 de `references/linkedin.md`). Attendre la confirmation de l'utilisateur entre deux sections et vérifier le résultat.

## Style d'écriture (CV et LinkedIn)

Zéro tiret cadratin. Ton factuel, pas de superlatifs creux (« passionné », « dynamique », « motivé » sans preuve). Pas d'emojis sur le CV ; sur LinkedIn, aucun dans le titre, au plus un ou deux dans À propos si l'utilisateur le souhaite. LinkedIn s'écrit à la première personne, le CV sans pronom.

## Étape 3 : Livrables

- **CV ATS** : lire le SKILL.md du skill `docx`, produire un .docx une page (le plus sûr au parsing). Proposer un export PDF texte (pas un PDF image).
- **CV Design** : CV visuel d'une page avec photo ou emplacement réservé (type d'artifact Design si disponible, sinon page HTML stylée), livré en PDF + source éditable.
- **LinkedIn** : un document « Profil LinkedIn optimisé » prêt à copier-coller, section par section : version actuelle, version proposée, nombre de caractères, mots-clés couverts. Plus une checklist des réglages. Type d'artifact Docs s'il est listé, sinon fichier Markdown.
- Livrer les fichiers avec SendUserFile. Avec une annonce précise, viser 65-75 % de correspondance de mots-clés.

**Appliquer les changements sur LinkedIn** : par défaut, l'utilisateur copie-colle lui-même (il garde la main sur ce qui est public). S'il demande à Claude de le faire via le navigateur : accord explicite section par section avant chaque enregistrement, et proposer d'abord de désactiver « Partager les modifications du profil avec votre réseau » (sinon chaque modification notifie ses contacts). C'est un réglage de compte : le changer seulement avec son accord.

## Garde-fous

- Ne rien inventer. En cas de trou, redemander.
- Jamais de saisie d'identifiants LinkedIn par Claude ; jamais de modification publique sans accord explicite par action.
- CV Design : jamais sans photo ni emplacement photo.
- Terminer en proposant une seule suite pertinente : version anglaise, adaptation à une annonce précise, lettre de motivation, ou plan de publications LinkedIn pour renforcer la visibilité.
