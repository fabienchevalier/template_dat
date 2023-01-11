---
title: "Document d'Architecture Technique"
author: [Fabien CHEVALIER]
subject: "Gouvernance"
date: "09-01-2023"
keywords: [Markdown, Example]
toc: true
toc-title: "Sommaire"
toc-own-page: true
titlepage: true,
titlepage-text-color: "FFFFFF"
titlepage-rule-color: "360049"
titlepage-rule-height: 0
titlepage-background: "img/bg/background.pdf"
titlepage-logo: "img/logo_infratech.png"
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
lof: true
tables: true
---
# DAT - Gouvernance pour la société Maléo par InfraTech

## 1. Références générales

| Références | DAT                               |
| ---------- | --------------------------------- |
| Type       | Document d'architecture technique |
| Diffusion  | Confidentiel                      |

### 1.2 Historique du document

| Historique |         |             |                  |
| ---------- | ------- | ----------- | ---------------- |
| Date       | Version | Description | Auteur           |
| 11/01/2023 | 0.1     | Création    | Fabien CHEVALIER |

### 1.3 Objectif du document

Ce document technique regroupe l’ensemble des informations concernant la **gouvernance de l’infrastructure de Maléo**. Il a pour objectif de spécifier l’ensemble des mécanismes techniques, des logiciels et des matériels qui sont mis en place dans le cadre de la gouvernance.

::: note
L'infrastructure présentée est majoritairement déployée sur le cloud Azure, mais bénéficie d’une interconnexion avec les sites de Paris et Bruxelles permettant le monitoring des équipements réseaux présents on-site.
:::

\newpage

## 2. Architecture

### 2.1 Schéma logique général d'architecture

![Schéma logique gouvernance](img/schemes/gov_schema_general.png)

### 2.2 Revue des services

#### 2.2.1 Monitoring et supervision

##### 2.2.1.1 Schéma logique de fonctionnement

![Schéma logique monitoring](img/schemes/gov_schema_monitoring.png)

##### 2.2.1.2 Équipements on-premise

La présence d’équipements réseaux on-site nécessite un agent installé.

#### 2.2.2 Accès à la plateforme (landing zone)

##### 2.2.2.1 Groupe de management Azure

| Nom            | ID                | Description                                                           |
| -------------- | ----------------- | --------------------------------------------------------------------- |
| Maléo          | mg-maleo          | Groupe de management principal                                        |
| Sandbox        | mg-sandbox        | Groupe de management de l’env. sandbox                                |
| Projects       | mg-projects       | Groupe de management des env. d’infrastructures                       |
| maleo_website  | mg-maleo_website  | Groupe de management englobant le site web de Maléo                   |
| maleo_intranet | mg-maleo_intranet | Groupe de management englobant l’intranet de Maléo                    |
| Connectivity   | mg-connectivity   | Groupe de management contenant les ressources liées à la connectivité |
| Plateform      | mg-plateform      | Groupe de management contenant les ressources de gestion de l’infra.  |
| Gouvernance    | mg-governance     | Groupe de management content les ressources liées à la gouvernance.   |

##### 2.2.2.2 Abonnements Azure (subscription)

| Nom                 | ID                       | Description                                   |
| ------------------- | ------------------------ | --------------------------------------------- |
| maleo-gouvernance   | xxxx-xxxx-xxxx-xxxx-xxxx | Gestion et facturation gouvernance            |
| maleo-connectivity  | xxxx-xxxx-xxxx-xxxx-xxxx | Gestion et facturation connectivité           |
| maleo-website-prod  | xxxx-xxxx-xxxx-xxxx-xxxx | Environnement de production du projet website |
| maleo-website-pprd  | xxxx-xxxx-xxxx-xxxx-xxxx | Environnement de preprod du projet website    |
| maleo-website-dev   | xxxx-xxxx-xxxx-xxxx-xxxx | Environnement de de dev du projet website     |
| maleo-intranet-prod | xxxx-xxxx-xxxx-xxxx-xxxx | Environnement de prod du projet intranet      |
| maleo-intranet-pprd | xxxx-xxxx-xxxx-xxxx-xxxx | Environnement de preprod du projet intranet   |
| maleo-sandbox       | xxxx-xxxx-xxxx-xxxx-xxxx | Environnement sandbox                         |

#### 2.2.3 Bases de données

| Nom             | Type                      | Calcul                            | Stockage | Niveau          |
| --------------- | ------------------------- | --------------------------------- | -------- | --------------- |
| maleo-glpi-prod | Azure Databse for MariaDB | General Purpose (2Vcore, 5GB Ram) | 128GB    | General Purpose |
