---
# Document informations
title: "Document d'Architecture Technique"
author: [Fabien CHEVALIER]
subject: "Gouvernance"
date: "09-01-2023"
keywords: [DAT, Gouvernance]

#Headers titles
header-center: "Gouvernance"

#Footer titles
footer-center: "Projet Professionnel"

#Add TOC
toc: true
toc-title: "Sommaire"
toc-own-page: true

#Add a title page
titlepage: true,
titlepage-rule-height: 0
titlepage-background: "img/bg/pages_background.pdf"
titlepage-logo: "img/logo_infratech.png"

#Add special blocs by awesomebox
header-includes:
- |
  ```{=latex}
  \usepackage{awesomebox}
  ```
pandoc-latex-environment:
  noteblock: [note]
  tipblock: [tip]
  warningblock: [warning]
  cautionblock: [caution]
  importantblock: [important]

#Add figure TOC
lof: true

#Background page
page-background: "img/bg/pages_background.pdf"
---
## Références générales

| Références | DAT                               |
| ---------- | --------------------------------- |
| Type       | Document d'architecture technique |
| Diffusion  | Confidentiel                      |

### Historique du document

| Historique |         |             |                  |
| ---------- | ------- | ----------- | ---------------- |
| Date       | Version | Description | Auteur           |
| 11/01/2023 | 0.1     | Création    | Fabien CHEVALIER |

### Objectif du document

Ce document technique regroupe l’ensemble des informations concernant la **gouvernance de l’infrastructure de Maléo**. Il a pour objectif de spécifier l’ensemble des mécanismes techniques, des logiciels et des matériels qui sont mis en place dans le cadre de la gouvernance.

::: note
L'infrastructure présentée est majoritairement déployée sur le cloud Azure, mais bénéficie d’une interconnexion avec les sites de Paris et Bruxelles permettant le monitoring des équipements réseaux présents sur site.
:::

\newpage

## Architecture

### Schéma logique général d'architecture

![Schéma logique gouvernance](img/schemes/gov_schema_general.png)

\newpage

### Contraintes identifiées

| Scope                        | Type            | Description                                                            |
| ---------------------------- | --------------- | ---------------------------------------------------------------------- |
| Gestion des logs système     | Contrainte      | Rétention des logs systèmes sur 6 mois glissants                       |
| Gestion des logs de sécurité | Contrainte      | Rétention des logs de sécurité (type firewall sur 12 mois glissants)   |
| Supervision du stockage      | Contrainte| 
| Solution MDM                 | Exigence client | Solution de MDM souhaitée pour l'ensemble du parc (mobile/desk/laptop) |
| ITSM                         | Exigence client | Solution de gestion des tickets par mail/web attendue                  |
| ITSM                         | Contrainte      | Inventaire complet à effectuer 1x par trimestre                        |


### Revue des services

#### Azure Active Directory

##### Schéma logique de fonctionnement

![Schéma logique monitoring](img/schemes/gov_schema_monitoring.png)

##### Équipements on-premise

La présence d’équipements réseaux on-site nécessite un agent installé.

#### Accès à la plateforme (landing zone)

