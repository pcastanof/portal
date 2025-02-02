+++
date        = "2022-06-13"
title       = "Correu"
description = "Enviament de correu electrònic."
sections    = "Canigó. Documentació Versió 3.6"
weight      = 1
+++

## Propòsit

Aquest mòdul té com a objectiu permetre l'enviament de correus electrònics a una o diverses adreces especificades a qualsevol dels següents recipients:

* Destinataris principals
* Destinataris secundaris
* Destinataris ocults

Permet diferents modes d'enviament, tant en text pla, com en mode HTML, i en tots 2 casos oferint la possibilitat d'adjuntar un o més fitxers en mode adjunt o inline. 

Versions i Dependències

## Instal.lació i Configuració

### Instal.lació

Per tal d'instal-lar el mòdul d'enviament de correu es pot incloure automàticament a través de l'eina de suport al desenvolupament o bé afegir manualment en el *pom.xml* de l'aplicació la següent dependència:

```xml
  ...
  <properties>
    ...
    <canigo.support.mailing.version>[3.0.0,3.1.0)</canigo.support.mailing.version>
  </properties>
  <dependencies>
    ...
    <dependency>
      <groupId>cat.gencat.ctti</groupId>
      <artifactId>canigo.support.mailing</artifactId>
      <version>${canigo.support.mailing.version}</version>
    </dependency>
  </dependencies>
```

A la [Matriu de Compatibilitats](/plataformes/canigo/documentacio-per-versions/3.6LTS/3.6.5/moduls/compatibilitat-per-modul/) es pot comprovar la versió del mòdul compatible amb la versió de Canigó utilitzada.

### Configuració

La configuració es realitza automàticament a partir de la eina de suport al desenvolupament. Aquesta eina genera
automàticament el fitxer de propietats necessari per a la configuració del servei.

Ubicacions proposades:
  - <PROJECT_ROOT>/src/main/resources/config/props/mail.properties, o
  - <PROJECT_ROOT>/src/main/resources/config/props/application.yml

|Propietat              |Requerit   | Valor Defecte |Descripció                                     |
|-----------------------|-----------|---------------|-----------------------------------------------|
|mail.host              | No        |localhost      |Nom del servidor de correu sortint (smtp)      |
|mail.port              | No        |25             |Port del servidor de correu sortint (smtp)     |
|mail.protocol          | No        |smtp           |Protocol del servidor de correu sortint (smtp) |
|mail.maxAttachmentSize | No        |1048576        |Mida màxima permesa dels fitxers adjunts       |
|mail.defaultEncoding   | No        |UTF-8          |Default encoding                               |
|mail.smtpTimeout       | No        |10000          |Timeout (smtp) mili segons                     |
|mail.smtpAuth          | No        |false          |Intent d'autenticar l'usuari utilitzant l'ordre AUTH |
|mail.isSmtpSSLEnabled  | No        |false          |Habilita l'ús de l'ordre STARTTLS per a canviar la connexió a una connexió protegida TLS |
|mail.debug             | No        |false          |Debug mode                                     |
|mail.username          | No        |               |Usuari de connexió al servidor de correu sorting (smtp) |
|mail.password          | No        |               |Password de l'usuari de connexió               |
|mail.encoded.password  | No        |               |Encoded password de l'usuari de connexió       |
|mail.extraProperties   | No        |{}             |Array extra de propietats. Valor d'exemple: {'mail.smtp.ssl.protocols':'TLSv1.2'} |

## Utilització del Mòdul

### Configuració

Exemple de configuració de l'arxiu de propietats: `mail.properties`

```properties
*.mail.host=localhost
*.mail.port=25
*.mail.protocol=smtp
*.mail.maxAttachmentSize=1048576
*.mail.defaultEncoding=UTF-8
*.mail.smtpTimeout=10000
*.mail.smtpAuth=true
*.mail.isSmtpSSLEnabled=true
*.mail.debug=true
*.mail.username=test@testcanigo.cat
*.mail.password=password
*.mail.extraProperties={\
  'mail.smtp.ssl.enable':'false',\
  'mail.smtp.ssl.protocols':'TLSv1.2',\
  'mail.smtp.connectiontimeout': '5000',\
  'mail.from': 'master@testcanigo.cat'\
  }
```

Exemple de configuració de l'arxiu de propietats: `application.yml`

```yaml
mail:
  host: localhost
  port: 25
  protocol: smtp
  maxAttachmentSize: 1048576
  defaultEncoding: UTF-8
  smtpTimeout: 10000
  smtpAuth: true
  isSmtpSSLEnabled: true
  debug: true
  username: test@testcanigo.cat
  password: password
  extraProperties: "{
    'mail.smtp.ssl.enable': 'false',
    'mail.smtp.ssl.protocols': 'TLSv1.2',
    'mail.smtp.connectiontimeout': '5000',
    'mail.from': 'master@testcanigo.cat'
  }"
```

<div class="message information">
És possible afegir variables dinàmicament concatenant dades a: `mail.extraProperties`.
</div>

### Controller

**MailController.java**: Controller que publica les operacions disponibles per a qui hagi de consumir-les.

Existeixen 2 beans injectats al context de l'aplicació (Spring) que poden ser consumits directament: *fluentMailService* i *encodedPasswordFluentMailService*

<br>
**Exemple utilitzant password no encriptat**:

```java
import cat.gencat.ctti.canigo.arch.support.mailing.FluentMailService;
import cat.gencat.ctti.canigo.arch.support.mailing.exception.MailModuleException;

import org.springframework.http.MediaType;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;

import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

@RestController
@RequestMapping("/mail")
public class MailController {

  private final FluentMailService fluentMailService;

  public MailController(FluentMailService fluentMailService) {
    this.fluentMailService = fluentMailService;
  }

  @GetMapping(produces = { MediaType.APPLICATION_JSON_VALUE })
  public void sendMail(
    @RequestParam(defaultValue = "test1@testcanigo.cat", value = "fromEMail") String fromEMail,
    @RequestParam(defaultValue = "test2@testcanigo.cat", value = "toEMail") String toEMail,
    @RequestParam(defaultValue = "Test message", value = "messageTitle") String messageTitle,
    @RequestParam(defaultValue = "This is a test", value = "messageBody") String messageBody
  ) throws MailModuleException {
    fluentMailService.send(fluentMailService
        .from(fromEMail)
        .to(toEMail)
        .subject(messageTitle)
        .message("<html>" +
          "<body>" + messageBody + "</body>" +
          "<footer>" + LocalDateTime.now().format(DateTimeFormatter.ISO_LOCAL_DATE_TIME) + "</footer>" +
          "</html>", true));
  }
}
```

<br>
**Exemple utilitzant password encriptat**:

```java
import cat.gencat.ctti.canigo.arch.support.mailing.FluentMailService;
import cat.gencat.ctti.canigo.arch.support.mailing.exception.MailModuleException;

import org.springframework.beans.factory.annotation.Qualifier;
import org.springframework.http.MediaType;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;

import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

@RestController
@RequestMapping("/mail")
public class MailController {

  @Qualifier("encodedPasswordFluentMailService")
  private final FluentMailService fluentMailService;

  public MailController(FluentMailService fluentMailService) {
    this.fluentMailService = fluentMailService;
  }

  @GetMapping(produces = { MediaType.APPLICATION_JSON_VALUE })
  public void sendMail(
    @RequestParam(defaultValue = "test1@testcanigo.cat", value = "fromEMail") String fromEMail,
    @RequestParam(defaultValue = "test2@testcanigo.cat", value = "toEMail") String toEMail,
    @RequestParam(defaultValue = "Test message", value = "messageTitle") String messageTitle,
    @RequestParam(defaultValue = "This is a test", value = "messageBody") String messageBody
  ) throws MailModuleException {
    fluentMailService.send(fluentMailService
        .from(fromEMail)
        .to(toEMail)
        .subject(messageTitle)
        .message("<html>" +
          "<body>" + messageBody + "</body>" +
          "<footer>" + LocalDateTime.now().format(DateTimeFormatter.ISO_LOCAL_DATE_TIME) + "</footer>" +
          "</html>", true));
  }
}
```
