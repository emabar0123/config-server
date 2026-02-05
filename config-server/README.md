# Config Server

Minimal REST API that returns MongoDB configuration documents by name.

## Requirements

- Node.js 20+

## Run locally

```
npm install
npm start
```

Server listens on `PORT` (default `3000`).

## Environment

Set these variables (examples in `.env`):

```
MONGODB_URI=mongodb://admin:123@172.16.161.45:27017/?authSource=admin
MONGODB_DB=serpents-config
MONGODB_COLLECTION=configurations
PORT=3000
```

## API

Get a configuration by name:

```
GET /configurations/by-name/:name
```

Example:

```
curl http://localhost:3000/configurations/by-name/lil-test
```

## Docker

```
docker build -t config-server .
docker run -p 3000:3000 -e MONGODB_URI="mongodb://admin:123@172.16.161.45:27017/?authSource=admin" -e MONGODB_DB=serpents-config -e MONGODB_COLLECTION=configurations config-server
```
