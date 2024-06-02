# jenkins-academy


Este repo es para ir guardando algunas cosas para probar con jenkins.

Gracias

Saludos


## Como trabajar con esto

Seguir los siguientes pasos

- Primero, es necesario levantar el docker-compose:
```
docker-compose up -d
```

- Como primera vez, Para tener el password se puede hacer lo siguiente:
```
docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```

- Despues, es necesario instalar 2 plugins:
 - en `Cloud Providers` instalar `docker` URL: https://plugins.jenkins.io/docker-plugin/
 - `configurations as code` URL: https://plugins.jenkins.io/configuration-as-code/

NOTA: cada vez que se instala un plugin es necesario reiniciar el jenkins.

- Luego es necesario traer la configuracion del archivo `jenkins.yaml` y levantarlo desde el jcasc

Para esto es necesario copiar el archivo jenkins.yaml a al contenedor:
```
docker cp jenkins.yaml jenkins:/var/jenkins_home/jenkins.yaml
```

Y luego en la configuracion del JCasC importarlo.

## Para detener el jenkins

Para detener el docker compose:
```
docker-compose stop
```


## Para borrar todo

Para borrar todo:
```
docker-compose down
```

