
+++
date         = "2024-04-09"
title        = "Roadmap"
description  = "Roadmap de GitHub Enterprise Cloud (GHEC) a.k.a SIC+"
weight      = "10"
sections    = ["GHEC"]
aliases = [
    "/drafts/ghec/gh-roadmap",
    "/ghec/gh-roadmap",
    "/plataformes/ghec/gh-roadmap"
]
+++

## [Q1 2024] Beta 1.0.0​

- :heavy_check_mark: Model organitzatiu (enterprise, organitzacions, repositoris, ...)​
- :heavy_check_mark: Integració amb GICAR Cisco Duo i gestió d'accesos (teams, rols, ...)​
- :heavy_check_mark: Implementació workflows de CI i CD tant d'infraestructura (Terraform) com d'aplicació (Java, Node.js)​
- :heavy_check_mark: Implementació arquitectura self-hosted runners amb Azure Container Instances (ACI)​
- :heavy_check_mark: Certificació desplegaments contenidors a AWS ECS Fargate​
- :heavy_check_mark: Pilot EMIX​

## [Q2 2024] 1.0.0​

- :heavy_check_mark: Certificació desplegament de llibreries Maven/Npm​
- :heavy_check_mark: Certificació desplegaments contenidors a Azure Container Apps​
- :heavy_check_mark: Certificació desplegaments funcions a AWS Lambda
- :heavy_check_mark: Certificació desplegaments continguts estàtics a AWS S3
- :heavy_check_mark: Certificació desplegaments funcions a Azure Functions
- :heavy_check_mark: Certificació desplegaments continguts estàtics a Azure Blob Storage​
- :heavy_check_mark: PoC integració Marc d'Automatització de Testing (MAT): execució tests funcionals amb Selenium i definició rollback automàtic per contenidors
- :heavy_check_mark: PoC integració Marc d'Automatització d'Observabilitat (MAO)​: healtcheck internet i definició rollback automàtic per contenidors
- :heavy_check_mark: Definició model desplegaments delegats (en màquines virtuals, clusters Kubernetes, ...) i PoC​
- :heavy_check_mark: Definició model desplegament bases de dades i PoC​
- :heavy_check_mark: Integració d'aplicacions pilot, noves i existents: Platges, Binaris, ... (backlog d'unes 20 aplicacions)​

## [Q3/Q4 2024] 1.1.0​

- Certificació desplegaments a GCP​
- Suport a .NET​ incloent llibreries
- Suport Python (llenguatge a incorporar al Full de Ruta)​ excloent llibreries (GitHub Packages no dona suport)
- Desplegaments en APIM (API Manager corporatiu)
- Self-hosted runner de tipus Deployer per (1) desplegar en registres Docker privats, només accessibles des de la xarxa corporativa, i (2) execució de healthchecks intranet
- Implementació rollback automàtic per funcions i continguts estàtics
- Implantació polítiques seguretat CTTI
- Anàlisi desplegaments avançats (Canary, Blue/Green, ...) en AWS, Azure, GCP​
- Anàlisi CI/CD Apps mòbils
- Anàlisi CI/CD MLOps
- Suport integració MAT i MAO/MAM

## [Q1 2025] 1.2.0​

- Integració amb repositori d'artefactes centralitzat en modalitat SaaS (Artifactory, ...)
- Dashboard amb KPIs del servei

*_Roadmap subjecte a canvis_