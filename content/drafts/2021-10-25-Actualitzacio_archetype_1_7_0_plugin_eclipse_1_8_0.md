+++
date        = "2021-10-25"
title       = "Canigó. Actualització archetype 1.7.0 i plugin Eclipse 1.8.0"
description = "S'ha publicat una nova versió del archetype i del plugin de l'eclipse de Canigó per generar projectes amb Canigó 3.6.0"
#sections    = ["Notícies", "home"]
#categories  = ["canigo"]
#key         = "DESEMBRE2021"
+++

## Introducció

Dins dels lliurables de Canigó hi consten l'arquetipus (_archetype_) i el _plugin_ de l'Eclipse. Seguint l'objectiu de CS Canigó de proporcionar facilitadors per a la creació de projectes Canigó als desenvolupadors d'aplicacions, s'ha actualitzat ambdós lliurables per generar projectes amb Canigó **versió 3.6.0**. Podeu consultar l'abast complet de la nova versió del marc de treball a les [Release Notes 3.6"](/canigo-download-related/release-notes-canigo-36).

L'**arquetipus** és una eina Maven que facilita la creació de projectes seguint una plantilla. Utilitzant l'arquetipus i executant un _goal_ de maven obtenim un projecte Canigó amb una base preconfigurada preparada per a incorporar-li noves funcionalitats.

El **_plugin_** és un connector desenvolupat específicament per a l'IDE Eclipse que permet afegir-hi menús contextuals per a la creació de projectes Canigó utilitzant l'arquetipus de Maven, a més a més d'afegir mòduls a un projecte creat i amb una preconfiguració ja donada. Així, utilitzant l'Eclipse, podem crear un projecte i afegir-l'hi els mòduls necessaris obtenint un projecte preconfigurat per al marc de treball Canigó i estalviant temps als desenvolupadors.

## Novetats _archetype_

La versió 1.7.0 de l'arquetipus de Canigó incorpora les següents novetats:

- Creació de projectes amb Canigó 3.6.0 i JDK 11
- Actualització de la versió de Spring, Spring Boot, dependències i plugins
- Actualització del Swagger

## Novetats _plugin_ Eclipse

La nova versió 1.8.0 del _plugin_ utilitza la versió 1.7.0 de l'arquetipus de Canigó per generar projectes amb Canigó 3.6.0. Per instal·lar o actualitzar aquesta versió del _plugin_ és necessari seguir els passos descrits a la secció "Instal·lació" de la [documentació del _plugin_ Canigó per a Eclipse](/canigo-download-related/plugin-canigo/).

## Documentació addicional

Està disponible la documentació dels lliurables de Canigó 3.6 a: [Binaris de Canigó 3.6](/canigo/download/canigo-36/)

En el següent enllaç, es pot consultar la noticia de la publicació de la [versió 3.6.0 de Canigó](/drafts/2021-10-25-actualitzacio-canigo-3_6_0/)