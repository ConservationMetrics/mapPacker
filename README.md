# MapPacker

MapPacker is a web application that can be used to send a request for an offline map resource (raster mbtiles), to be generated by [mapgl-tile-renderer](http://github.com/conservationMetrics/mapgl-tile-renderer/).

## Configure

To get started, copy `.env.example` to `.env` and add your database and table information, authentication, and a Mapbox access token.

**Database:** Provide your database information in the relevant variables, including the table where offline map data is stored.

**Authentication strategy:** MapPacker supports three different authentication strategies: auth0, password (from an environmental var) with JWT key, or none. Set your authentication strategy in `NUXT_ENV_AUTH_STRATEGY`.

- If you are using an auth0 strategy, then you need to provide a domain, client ID, client secret, audience, and base URL.
- If you are using a password strategy, then you need to provide a password, and secret JWT key.

**Vue API key:** Generate an API key to add to request headers made by the Nuxt front end.

**Mapbox access token:** Provide an access token to be used across the application for authenticating with Mapbox maps.

## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

Add `--hostname 0.0.0.0` if you want the app to be accessible across your local network.

## Deployment

For deployment (e.g. on Azure), the following additional env vars are needed:

```
HOST: 0.0.0.0
NODE_ENV: production
```

Local deployment of Docker:

```sh
docker run --env-file=.env -it -p 8080:8080 mappacker:latest
```
