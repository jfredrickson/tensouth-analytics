# Plausible Analytics

Based on the [example Plausible stack](https://github.com/plausible/hosting).

## Initial deployment

Create the .env file if needed; otherwise use it as a reference to configure environment variables:

```
cp example.env .env
```

Bring up the databases:

```
docker compose up -d db events-db
```

Run the database initialization scripts:

```
docker compose run app /entrypoint.sh db createdb
docker compose run app /entrypoint.sh db migrate
```

Finally, bring up the app:

```
docker compose up -d app
```
