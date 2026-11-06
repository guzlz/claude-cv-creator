# CV Builder : skill Claude pour créer un CV ATS et optimiser son profil LinkedIn

**Skill Claude (Anthropic) gratuit et open source** qui crée un **CV optimisé ATS** ou un **CV design avec photo**, puis **optimise votre profil LinkedIn** (titre, section À propos, expériences, compétences, mots-clés, SEO) pour le poste que vous visez. Claude vous interviewe comme un recruteur, lit votre profil LinkedIn via **Claude in Chrome** ou le navigateur intégré de **Claude Desktop**, et livre un CV Word/PDF d'une page et un profil LinkedIn prêt à copier-coller.

> **English:** Free, open-source **Claude skill** to build an **ATS-friendly resume / CV** and **optimize your LinkedIn profile** (headline, About section, skills, keywords, LinkedIn SEO and Google SEO) for a target job. Works in French and English.

![Claude Skill](https://img.shields.io/badge/Claude-Skill-D97757)
![Langue](https://img.shields.io/badge/langue-FR%20%7C%20EN-blue)
![Licence MIT](https://img.shields.io/badge/licence-MIT-green)

---

## Sommaire

- [Ce que fait le skill](#ce-que-fait-le-skill)
- [CV ATS ou CV design : lequel choisir ?](#cv-ats-ou-cv-design--lequel-choisir-)
- [Pourquoi un CV compatible ATS pour un poste à responsabilité](#pourquoi-un-cv-compatible-ats-pour-un-poste-à-responsabilité)
- [Optimisation du profil LinkedIn et SEO LinkedIn](#optimisation-du-profil-linkedin-et-seo-linkedin)
- [Installation](#installation)
- [Exemples de demandes](#exemples-de-demandes)
- [FAQ](#faq)
- [Structure du dépôt](#structure-du-dépôt)

## Ce que fait le skill

| Fonction | Détail |
|---|---|
| **Interview recruteur** | Questions une par une sur vos expériences, résultats chiffrés, périmètre (équipe, budget), formations, compétences. Rien n'est inventé. |
| **CV optimisé ATS** | Une colonne, sans tableau ni icône, intitulés standards, mots-clés exacts des offres d'emploi, puces verbe + action + résultat chiffré. Livré en .docx et PDF texte. |
| **CV design avec photo** | Pour les commerces de proximité (restaurant, boulangerie, boutique, coiffure) : mise en page soignée, savoir-être, disponibilités, photo ou emplacement photo. |
| **Lecture du profil LinkedIn** | Via Claude in Chrome, le navigateur intégré de Claude Desktop, ou l'export PDF du profil. |
| **Optimisation LinkedIn** | Carte de mots-clés tirée de 2 à 5 offres réelles, réécriture du titre (220 car.), de la section À propos (2 600 car.), des expériences et des compétences. |
| **SEO LinkedIn et Google** | Visibilité dans LinkedIn Recruiter (localisation, Open to Work, compétences) et sur Google (URL personnalisée, profil public, liens entrants). |
| **Cohérence CV / LinkedIn** | Mêmes intitulés, dates et chiffres sur les deux supports. |

## CV ATS ou CV design : lequel choisir ?

- **CV ATS** : candidature en ligne, scale-up, PME, grand groupe, cabinet de recrutement, et **tout poste cadre ou à responsabilité**.
- **CV design** : candidature remise en main propre chez un commerçant, lue directement par un humain.

## Pourquoi un CV compatible ATS pour un poste à responsabilité

Un **ATS** (Applicant Tracking System, logiciel de suivi des candidatures) extrait le texte du CV, le range dans des champs et le stocke dans une base que les recruteurs interrogent par mots-clés.

| | Outils légers | ATS d'entreprise |
|---|---|---|
| Exemples | Teamtailor, Welcome to the Jungle, Flatchr, Recruitee | Workday, SAP SuccessFactors, Oracle Taleo, iCIMS, SmartRecruiters, Greenhouse |
| Lecture du CV | Souvent ouvert directement par le recruteur | Fiche structurée, filtres, recherche dans la base |

Teamtailor est aussi un ATS. Mais pour un poste de direction ou de management, le CV passe le plus souvent par un ATS d'entreprise ou un cabinet : volume élevé, plusieurs lecteurs, recherche par mots-clés des mois plus tard. Un CV mal parsé arrive incomplet ou n'est jamais retrouvé. Le skill explique cet enjeu et écarte les mythes (non, 75 % des CV ne sont pas « rejetés par un robot »).

## Optimisation du profil LinkedIn et SEO LinkedIn

Le skill applique une méthode complète ([`references/linkedin.md`](cv-builder/references/linkedin.md)) :

1. **Mots-clés LinkedIn** : intitulé principal, compétences métier, outils, secteur, localisation, tirés des offres d'emploi visées.
2. **Titre LinkedIn (headline)** : mot-clé principal dans les 60-70 premiers caractères, plusieurs variantes avec compteur.
3. **Section À propos** : accroche visible avant « Voir plus », parcours chiffré, expertises, appel à l'action.
4. **Expériences et compétences** : descriptions indexées, compétences rattachées à chaque poste, compétences épinglées.
5. **Être trouvé par les recruteurs** : localisation, Open to Work (recruteurs uniquement ou public), profil complet, réseau.
6. **Référencement Google du profil LinkedIn** : URL personnalisée, profil public visible des moteurs de recherche, liens depuis CV, site et GitHub.

Par défaut, vous copiez-collez vous-même les textes proposés. Claude ne saisit jamais vos identifiants LinkedIn et ne modifie votre profil qu'avec votre accord, section par section.

## Installation

### Claude (application web et Claude Desktop)
1. Téléchargez [`dist/cv-builder.skill`](dist/cv-builder.skill).
2. Importez-le dans la section Skills des paramètres de Claude (ou ouvrez le fichier dans une conversation et cliquez sur « Save skill »).
3. Pour la lecture automatique de LinkedIn : utilisez Claude Desktop avec l'extension **Claude in Chrome** connectée, ou le navigateur intégré.

### Claude Code
```bash
git clone https://github.com/guzlz/claude-cv-creator.git
cp -r claude-cv-creator/cv-builder ~/.claude/skills/
```

## Exemples de demandes

- « Refais mon CV pour un poste de Directeur des Opérations, voici l'annonce »
- « Optimise mon profil LinkedIn pour être trouvé par les chasseurs de têtes en supply chain »
- « Crée-moi un CV pour travailler en boulangerie, avec ma photo »
- « Make my resume ATS-friendly and rewrite my LinkedIn headline for a Head of RevOps role »

## FAQ

**Le skill est-il gratuit ?** Oui, sous licence MIT. Il faut un accès à Claude avec les skills activés.

**Faut-il Claude Desktop ?** Non. Sans navigateur connecté, le skill vous demande l'export PDF de votre profil LinkedIn ou un copier-coller.

**Mon CV passera-t-il les ATS ?** Le format ATS (une colonne, texte, intitulés standards) est lu correctement par les ATS courants. Aucun outil ne peut garantir un entretien.

**Le skill invente-t-il des expériences ?** Non. Tout vient de vos réponses ou de votre profil existant.

**Le skill fonctionne-t-il en anglais ?** Oui : CV, resume et profil LinkedIn en français ou en anglais.

## Structure du dépôt

```
cv-builder/
├── SKILL.md                 # Instructions du skill (workflow complet)
└── references/
    ├── linkedin.md          # Méthode d'optimisation LinkedIn et SEO
    └── ats.md               # ATS, Teamtailor vs ATS d'entreprise, règles de format
dist/
└── cv-builder.skill         # Paquet prêt à importer dans Claude
```

## Licence

MIT. Contributions et suggestions bienvenues via les issues.

---

Mots-clés : skill Claude, Claude AI, Anthropic, CV ATS, CV optimisé, CV cadre, resume builder, ATS resume, optimisation LinkedIn, profil LinkedIn, titre LinkedIn, SEO LinkedIn, recherche d'emploi, chasseur de têtes, Teamtailor, Workday, lettre de motivation.
