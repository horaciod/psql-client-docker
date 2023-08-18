# psql-client-docker
Containerized PostgreSQL client for executing SQL commands in containerized environments

The `psql-client` image is stored on Docker Hub in the [rtdl/psql-client repository](https://hub.docker.com/r/rtdl/psql-client).


## Crear Imagen con 
docker build -t pgclientlocal . 

## Usar para backup 

```bash
 #!/bin/bash

export $(grep -v '^#' html/.env | xargs)
fecha=`date +%Y-%m-%d`
docker run -it --rm -v ${PWD}/dbclean2:/dbclean2 --entrypoint pg_dump pgclientsid postgresql://$DB_USERNAME:$DB_PASSWORD@$DB_HOST:$DB_PORT/$DB_DATABASE -f /dbclean2/ddi-$fecha.sql

ls -lh dbclean2/
```

