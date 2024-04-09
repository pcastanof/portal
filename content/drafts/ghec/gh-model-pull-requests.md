
+++
date         = "2024-04-09"
title        = "Model d'Integració de Branques amb Pull Request"
description  = "El present document descriu el resultat de l' anàlisi realitzada en la gestió d' integració entre branques a GitHub a través de Pull Request."
weight      = "6"
sections    = ["GHEC"]
+++


<img src="https://identitatcorporativa.gencat.cat/web/.content/Documentacio/descarregues/dpt/COLOR/Presidencia/ctti_h2.jpg">

# Model d'Integració de Branques amb Pull Request.

## Objectiu 🚀
El present document descriu el resultat de l' anàlisi realitzada en la gestió d' integració entre branques a GitHub a través de Pull Request.

## PREREQUISIT
Cal que el lector tingui coneixements previs bàsics d'operativitat amb repositoris de codi Git.

## Al detall 📋

El model de treball amb Pull Request a Github descriu una mètode de treball a l'hora de realitzar integracions entre branques a Github, normalment una branca de features a una branca principal, per exemple, rellegir-se o màster.

Aquest procés permet la revisió del contingut de la branca a integrar en una principal abans de realitzar la integració.  Si el contingut d' aquesta branca no és apte als criteris del la persona que tingui el rol de revisor, aquesta branca no s' integrarà. 

El treball amb Pull Request té una sèrie d'avantatges :

1. El contingut d'una branca és revisat prèviament per un "peer" amb igual o més experiència en la tecnologia, permetent identificar errors prèviament a integrar en branques principals, la qual cosa facilita la detecció primerenca d'errors.
2. Permet realitzar un procés ordenat d'integració de branques.
3. Permet que la resta de membres de l'equip revisin el codi o puguin afegir comentaris a aquest desenvolupament, compartint opinions, estandarditzant implementacions o compartint el coneixement revisat.  
4. Ajuda a generar diferents punts de vista, la qual cosa repercuteix en la seguretat dels membres de l'equip, així com a la seva coexió interna i la seva autonomia.

## Fluxos més estàndards de Pull Request
Es descriuen els dos casos de Pull Request més estàndard que se solen realitzar en les diferents organitzacions.

1. Sol·licitud de Pull Request i aprovació directa pel reviewer als canvis, després de la seva revisió.

![Pull Request](/images/GHEC/pullrequestOK.png)

2. Sol·licitud de Pull Request, sol·licitud de més informació per part del Reviewer i re-sol·licitud de Pull Request després d'afegir canvis sol·licitats.

![Pull Request demanant més informació ](/images/GHEC/pullrequestKO.png)

## Exemple

Es descriuen exemples per a ambdós fluxos de Pull Request identificats anteriorment.

**Sol·licitud de Pull Request i aprovació directa pel reviewer als canvis, després de la seva revisió**

1. El desenvolupador demana una branca "Documentacio_feature" per realitzar els canvis necessaris per implementar el seu canvi, en aquest cas un canvi en la documentació.

2. Un cop pujat el desenvolupament a la branca, sol·licita amb Main/Master polsant en l'opció Pull Request.

![Sollicitud de Pull Request ](/images/GHEC/3SolicitudPullRequest.png)

3. Posteriorment el desenvolupador polsa a "Compare & Pull Request" apareixent la següent finestra per incloure la següent informació :

![Sollicitud de Pull Request ](/images/GHEC/4SolicitudPullRequest.png) 

+ Branca destí : Main
+ Branca origen : Documentacio_feature
+ Títol del Pull Request
+ Descripció de la Pull Request
+ Reviewer : usuari del membre de l'equip que realitzarà la revisió de codi
+ Un cop emplenada la informació, polsa a "Create Pull Request"

![Sollicitud de Pull Request ](/images/GHEC/4CreacionPullrequest.png)

4. Es crea la Pull Request i se li requereix al Reviewer la seva aprovació.

![Sollicitud de Pull Request ](/images/GHEC/5PullRequestCreada.png)

5. El Reviewer obté la Pull Request polsant a "Pull Request" al menut on apareixerà la petició de revisió i podrà veure els canvis.

![Sollicitud de Pull Request ](/images/GHEC/6RevisionCambios.png)

6. Si després de la revisió tot està OK, el reviewer polsa a "Merge Pull Request".

![Sollicitud de Pull Request ](/images/GHEC/7MergePullRequest.png)

7. GitHub retorna Ok al Merge i la branca "Documentacio_Feature" s'ha integrat a Main/Master
.
![Sollicitud de Pull Request ](/images/GHEC/8PullRequestRealizado.png)

**Sol·licitud de Pull Request, sol·licitud de més informació per part del Reviewer i re-sol·licitud de Pull Request després d'afegir canvis sol·licitats**

El desenvolupador realitza els passos 1 al 5 de l' apartat anterior.   En aquest cas realitza la modificació d' un dels documents.

6. El reviewer revisa els canvis realitzats polsant a "File Changed", i detecta un problema a l'enllaç Wiki pel que crea un comentari requerint més canvis i no accepta el merge.

![Sollicitud de Pull Request ](/images/GHEC/8ReviewCambios.png)

El missatge s'inclou al fil del Pull Request

![Sollicitud de Pull Request ](/images/GHEC/8ReviewCambiosII.png)


7. El desenvolupador rep el missatge, realitza els canvis i torna a demanar la Pull Request apareixent el nou canvi en el fil.

![Sol·licitud de Pull Request ](/images/GHEC/9ImproveCode.png)

8. El reviewer rep els canvis, els revisa, afegiu un comentari aprovant el canvi "Aprovat" i polsa a "Merge Pull Request"

![Sollicitud de Pull Request ](/images/GHEC/10AprobacionReview.png)

9. El merge de la branca a Master/Main és realitzat

![Sollicitud de Pull Request ](/images/GHEC/11AprobacionReview.png)

## Miscellaneous
Hi ha diferents combinacions addicionals a les dues descrites en aquesta guia, com per exemple, la possibilitat que siguin diversos Reviewers els que necessiten aprovar els canvis d'un document.