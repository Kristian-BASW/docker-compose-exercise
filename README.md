# docker-compose-exercise# Docker Compose exercise: Run React and an API together

[Dansk](README.da.md) | **English**

In this exercise, you will run your React app and a new Minions API built with ASP.NET Core (.NET 10) in separate containers. You will bring the configuration together in a `compose.yaml` file so both services can be built, started, and stopped with a single command.

You should have completed the [Docker exercise](README.md) and have Docker running. Neither Bun nor the .NET SDK needs to be installed on your computer; they are used inside Docker images.

## 1. Prepare the project

Open a terminal in `docker-exercise` and check that Docker Compose is available:

```bash
docker compose version
```

We use the command `docker compose` with a space.

The API is in `docker-exercise/api`, next to the React app. The project contains the following files, which you will explore in this exercise:

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

The React app's existing API routes remain in the app. The new API is a separate service with its own code and Dockerfile.

```dockerignore
bin/
obj/
.git/
```

## 2. Bring the two services together with Compose

### Task

Open `compose.yaml` in the `docker-exercise` folder.

## 3. Build and start the environment

Run from the `docker-exercise` folder:

```bash
docker compose up -d
```

Check the status using:

```bash
docker compose ps
```

## 4. Test in the browser

Use your browser to check that both the API and the React app work.

## 5. Task: Display minions in React

Now connect the React app to the new API.

## 6. Stop and clean up

Stop the containers, but keep them:

```bash
docker compose stop
```

Start the same containers again:

```bash
docker compose start
```

Stop and remove the containers and network:

```bash
docker compose down
```

The images remain. These commands apply to this Compose project; the earlier container started with `docker run` is a separate environment.

## 7. Try it yourself

- Add a new minion to the API, rebuild, and check that the data changes.
- Try stopping only the API. What happens to the React page and its data? Start it again.
