# Nginx test

Esto es un repo simple que sirve para buildear una imagen de nginx con un archivo simple.

## Antes de comenzar

Es necesario crear un archivo de credenciales de docker hub en jenkins.

Para ello es necesario realizar los siguientes pasos:

- Primero es necesario crear una cuenta en https://hub.docker.com/

- Segundo, es necesario armar un archivo que tenga la siguiente estructura:
```json
{
  "auths": {
    "https://index.docker.io/v1/": {
      "auth": "CREDENCIALES_EN_BASE_64"
    }
  }
}
```

Donde el CREDENCIALES_EN_BASE_64 es el `nombre de usuario + ":" + contraseña` 

De esta forma:
```
echo -n {nombre_de_usuario}:{password} | base64
```

- Con este archivo, vamos a Jenkins y creamos un secreto de tipo String con el nombre `docker-hub-credentials`

NOTA: El secreto tiene que ser de tipo string, por que parece que existe un problema cuando se genera el secreto de tipo File y genera un secreto vacio.


y listo, estamos listos.
