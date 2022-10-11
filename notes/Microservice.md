---
title: Microservice
created: '2021-03-22T07:45:18.425Z'
modified: '2021-03-24T16:07:27.324Z'
---

# Microservice
- Independently deployable component
- interoperability
- message based communication

# Monolit
## Fordele ved monolit:
- enkle at udvikle
  - tech-stack er begrænset til få frameworks og databaser
  - logisk sammenhæng i al koden
- Nem at bygge koden
  - alt er samlet et sted
- Nemme at teste
  - der er kun få eksterne tind der skal mockes 
- nemme at deploye
  - der er kun applikationen skal skal udgives
- nemme at skalere
  - man kører bare flere instanser af hele applikationen bag en loadbalancer

## Ulemper ved monolit:
- Jo større en applikation er, des sværere bliver det for nye teammedlemmer at blive produktive
- Der skal bruges flere teams skal udvikle på en stor monolit
  - team til UI / til backend / til testing / til deploying
  - holdene kan ikke fungere selvstændigt, men skal hele tiden koordinere
- Kodebasen bliver sværere at håndtere og forstå efterhånden som den vokser
- Besværligt at benytte nye teknologier
  - selv en mindre udskiftning af en komponent kan betyde at en større del af koden skal skrives om
- Uhensigtsmæssig skalering
  - Når en del af applikationen har brug for mere kraft, bliver man nødt til at starte en instans af hele applikationen, hvilket betyder at der benyttes unødvendige ressourcer på dele som ikke har behov for skalering.
- applikationen database vokser sig stor
  - påvirker også performance
- en stor monolit med mange programmører skaber uoverskuelige udgivelser hvor der kan være mange 1000 ændringer der skal overskues

# Microservice

## Kommunikation
### RPC
- Ala "REST"
### Messaging
- En service `sender/publish` en `besked/message` eller et `event` til en `broker` eller en `kanal/channel`
  - andre services `abbonnerer/subscribe` på message eller event
- Skaber en løs kobling mellem services
  - `broker` søger for at holde på beskeder indtil services er klar til at tage imod dem
- Skab et fælles format som services kan forstå

## Distributed Services
Tilgængelighed

### Service Registry
Registrerer hvor Services befinder sig
- Services skal "selv-registrere" sig i registry (fordi deres lokation kan ændre sig)
- Services skal af-registrere dig når de lukkes ned
- Registry er en "telefon-bog" over hvor services befinder sig, så man spørger registry først, når man skal bruge en bestemt ressource

### CORS

### Circuit Breaker
**Problem:** Hvad hvis en service er nede eller på anden måde ikke tilgængelig?
Det manglende svar kan eskallere til et "manglende" svar i den kaldende service, som til sidst vil gøre hele applikationen utilgængelig.

"Circuit Breaker" går ud på at kalde en service via en proxy. Hvis der ikke kommer noget svar fra servicen man forsøger at kalde, vil Circuit Breaker sørge for at sende kaldet et andet sted hen. Der forsøges stadig løbende at få kontakt til servicen

### Gateway




# Implementing Cross-Cutting  Concerns for ASP.NET Core Microservices
- from Pluralsight
## Implementing Logging
- operational event during runtime
- Identify errors
- diagnose bugs

### Choosing what to log
- what info will be needed to diagnose a bug or runtime error?
- Balance
  - Log nok til at informationen er brugbar
  - undgå overflødig information - det er bare larm
- Beskeder skal indeholde nok detaljer og data til at understøtte en fornuftig analyse
  - eksempelvis: optag forespørgsler og ressource id'er
- Undgå at logge følsomme data

### Microsoft Logging Abstractions
- ILogger og ILogger<T>
- ILoggerFactory

#### Log Levels
Det øverste niveau indeholder også alle niveauer under sig - dvs. "Trace"-niveau vil også vise alle andre typer af logging beskeder fra andre log levels.

| Level | Usage |
|---:|:---|
| Trace | Log Detailed messages during development |
| Debug | Log verbose messages (occasionally in production) |
| Information| Log general flow of requests/operations |
| Warning| Log non-critical but abnormal events |
| Error | Log exceptions which cannot/are not gracefullt handled |
| Critical | Log major failures which require immediate attention |

Filter console log messages, use configuration to filter logs from categories by log level:
- `appsettings.json`:
```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    }
  }
  ...
}
```

- `"Default": "Information"` sætter logging niveauet for hele applikationen
- `"Microsoft": "Warning"` sætter logging niveauet lavere for kategorier der starter med "Microsoft" (dvs. færre beskeder)
- `"Microsoft.Hosting.Lifetime": "Information"` sætter logging niveauet højere for kategorier der starter med "Microsoft.Hosting.Lifetime" (dvs. flere beskeder, end ved kategorien "Microsoft")

#### Shared Library
Fordele:
- reducerer udviklingstid
- kode er skrevet og testet en gang
- fejl rettes et sted

Ulemper:
- Kan genintroducere kopling
- tilføjer vedligeholdelses kompleksitet
  - pakken skal tilføjes til koden i forbindelse med udgivelse
- Versionering og opdateringer skal være velovervejede

## Implementing Centralized Logging for Microservices
- ELK stack
  - Eleasticsearch
  - Kibana

## Health Checks
Hvad er det? Monitorerer web apps sundhed
- Exposer et HTTP endpoint
- Health Check resultatet indikerer om servicen kan benyttes


## Worker Services
Typiske workloads:
- Bearbejde beskeder/events fra en kø, service bus eller event stream
- Reagere på fil ændringer i en object/file store
- Aggregere data fra en fil store
- Berige data i data ingestion pipelines
- formatere og rense AI/ML datasæt











