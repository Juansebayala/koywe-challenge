# Prerequisites

- [Node 18.18.2](https://github.com/nvm-sh/nvm)

# Setup

1. Run `npm i` to install the necessary dependencies (If you get the error "upstream dependency conflict", add the `--legacy-peer-deps` flag at the end.).
2. Create a `.env` file in the root directory and define the following environment variables:

```
PORT= Application port (e.g., 5000)
ALLOWED_ORIGINS= Frontend URL

CRYPTOMKT_URL= Cryptomkt API URL

DB_USER= Database username
DB_PASSWORD= Database password
DB_NAME= Database name
DB_PORT= Database port
DATABASE_URL= Database URL

JWT_ACCESS_SECRET= Secret key for the JWT access token

JWT_REFRESH_SECRET= Secret key for the JWT refresh token
```

3. Start the Docker container by running `docker compose up -d`.

## To set up the server locally, follow these steps:

1. Once Docker Compose is running, execute `npx prisma migrate deploy` to apply the database migrations.
2. After the database tables have been created, run `npm run start:dev` to start the Nest server in development mode.
3. Send a `POST` request to `localhost:{PORT}/auth/register` to create a new user, using the following JSON body: `{username, password}`.
4. Send a `POST` request to `localhost:{PORT}/auth/login` with the credentials of the previously created user, including the following JSON body: `{username, password}`. Use the returned accessKey to make authenticated requests.
