# Docker Compose-opgave: Kør React og et API sammen

[English](README.md) | **Dansk**

I denne opgave skal du køre din React-app og et nyt Minions-API i ASP.NET Core (.NET 10) i hver sin container. Du samler opsætningen i en `compose.yaml`, så begge services kan bygges, startes og stoppes med én kommando.

Du skal have gennemført [Docker-opgaven](README.da.md) og have Docker startet. Hverken Bun eller .NET SDK behøver være installeret på din computer; de bruges inde i Docker-images.

## 1. Gør projektet klar

Åbn en terminal i `docker-exercise`, og kontroller, at Docker Compose er tilgængelig:

```bash
docker compose version
```

Vi bruger kommandoen `docker compose` med mellemrum.

API'et ligger i `docker-exercise/api`, ved siden af React-appen. Projektet indeholder følgende filer, som gennemgår i opgave:

```text
docker-exercise/
├── compose.yaml
├── react/
│   ├── Dockerfile
│   ├── package.json
│   ├── bun.lock
│   └── src/
└── api/
    ├── Dockerfile
    ├── .dockerignore
    ├── Minions.Api.csproj
    └── Program.cs
```

React-appens eksisterende API-ruter bliver i appen. Det nye API er en separat service med sin egen kode og Dockerfile.


```dockerignore
bin/
obj/
.git/
```

## 2. Saml de to services med Compose

### Opgave 

Åbn `compose.yaml` i `docker-exercise`-mappen

## 3. Byg og start miljøet

Kør fra `docker-exercise`-mappen:

```bash
docker compose up -d
```

Tjek status ved brug af 

```bash
docker compose ps
```
## 4. Test i browseren

Brug browseren til at teste at api'et virker og at react appen virker.

## 5. Opgave: Vis minions i React

Forbind nu React-appen med det nye API:

## 6. Stop og ryd op

Stop containerne, men behold dem:

```bash
docker compose stop
```

Start de samme containere igen:

```bash
docker compose start
```

Stop og fjern containerne og netværk:

```bash
docker compose down
```

Images bliver liggende. Kommandoerne gælder dette Compose-projekt; den tidligere container startet med `docker run` er et separat miljø.

## 7. Prøv selv

- Tilføj en ny minion i API'et, byg igen, og kontroller, at data ændres.
- Prøv kun at stoppe API'et. Hvad sker der med React-siden og dens data? Start det igen.
