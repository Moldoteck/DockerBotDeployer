# File structure for deploying created bots with docker
This structure allows easy maintanance of existent bots and integration of new ones.

# To build images:
1. Complete .env and google_api.json files where needed
2. Run `docker-compose build`

# To run images:
Run `docker-compose up -d`
Or
Run `docker-compose up container_name -d`

Use same strategy for restarting/stopping containers.

# To create backup for mongodb, run:
`docker-compose exec -T mongo sh -c 'mongodump --archive' > db.dump`

# To re-create mongodb from backup, run:
`docker-compose exec -T mongo sh -c 'mongorestore --drop --archive' < db.dump`