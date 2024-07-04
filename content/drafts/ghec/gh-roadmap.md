
+++
date         = "2024-04-09"
title        = "Roadmap"
description  = "Roadmap de GitHub Enterprise Cloud (GHEC) a.k.a SIC+"
weight      = "10"
sections    = ["GHEC"]
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
- (En progrés) PoC integració Marc d'Automatització de Testing (MAT): execució tests funcionals amb Selenium i definició rollback automàtic per contenidors
- (En progrés) PoC integració Marc d'Automatització d'Observabilitat (MAO)​: healtcheck internet i definició rollback automàtic per contenidors
- (En progrés) Definició model desplegaments delegats (en màquines virtuals, clusters Kubernetes, ...) i PoC​
- (En progrés) Definició model desplegament bases de dades i PoC​
- (En progrés) Integració d'aplicacions pilot, noves i existents: Platges, Binaris, ... (backlog d'unes 20 aplicacions)​

## [Q3/Q4 2024] 1.1.0​

- Desplegaments avançats (Canary, Blue/Green, ...)*​
- Self-hosted runner de tipus Deployer (per desplegar en registres Docker privats, només accessibles des de la xarxa corporativa)​
- Certificació desplegaments a GCP​
- Suport a .NET​
- Suport Python (llenguatge a incorporar al Full de Ruta)​
- Desplegaments en APIM (API Manager corporatiu)
- CI/CD Apps mòbils
- CI/CD MLOps
- Integració completa amb MAT i MAO


*_Roadmap subjecte a canvis_