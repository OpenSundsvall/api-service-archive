# Archive

## Leverantör

Sundsvalls kommun

## Beskrivning
Archive är ett generiskt API mot kommunens e-arkiv, och har stöd för att

* Arkivera ärenden och dokument
* Söka efter arkiverade ärenden och dokument

I aktuell version (0.1) finns endast stöd för arkivering av ärenden och dokument från ByggR, även om tjänsten på sikt kommer att byggas ut med fler leverantörer.

## Tekniska detaljer

|Miljövariabel|Beskrivning|
|---|---|
|`FORMPIPE_PROXY_BASE_URL`|URL till FormpipeProxy-tjänst|
|`BYGGR_SUBMISSION_AGREEMENT_ID`|Leveransöverenskommelse för ByggR-arkivering|

### Paketera och starta tjänsten
Applikationen kan paketeras genom:

```
mvn package
```

Detta kommando skapar filen `api-service-archive-<version>.jar` i katalogen `target`. Tjänsten kan nu startas genom kommandot `java -jar target/api-service-archive-<version>.jar`.

### Bygga och starta tjänsten med Docker
Applikationen kan paketeras som en Docker-image genom:

```
docker build -f src/docker/Dockerfile -t api.sundsvall.se/ms-archive:latest .
```

Starta samma Docker-image i en container genom:

```
docker run -i --rm -p8080:8080 api.sundsvall.se/ms-archive
```

Alternativt kan tjänsten efter bygge enl. ovan startas i sandbox-läge genom:

```
docker-compose -f src/docker/docker-compose-sandbox.yml up

