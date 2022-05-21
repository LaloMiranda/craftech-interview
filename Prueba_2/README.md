<img src="https://i.ibb.co/VM5MzBT/craftech-logo3.png=150x" width="250" height="250">

>  ***ATENCION: La prueba tecnica completa debe ser entregada en un unico repositorio***

#### Prueba 2 - Despliegue de una aplicación Django y React.js

Elaborar el deployment dockerizado de una aplicación en django (backend) con frontend en React.js contenida en el repositorio. Es necesario desplegar todos los servicios en un solo docker-compose.

Se deben entregar los Dockerfiles pertinentes para elaborar el despliegue y justificar la forma en la que elabora el deployment (supervisor, scripts, docker-compose, kubernetes, etc)

Subir todo lo elaborado a un repositorio (github, gitlab, bitbucket, etc). En el repositorio se debe incluir el código de la aplicación  y un archivo README.md con instrucciones detalladas para compilar y desplegar la aplicación, tanto en una PC local como en la nube (AWS o GCP).

***
## Resolución
Dentro de la carpeta *Prueba_2* ejecutar:
```console
sudo docker-compose up --build
```
Con esto construimos las imágenes y largamos los contenedores.

Se puede verificar el funcionamiento entrando a las siguientes direcciones desde el navegador:
```console
localhost:8000
localhost:3000
```


### Backend
Comencé el deployment utilizando la imágen de python:3.9 siguiende las instrucciones de la clase de capacitación dada por craftech. Esta versión de python resultó en problemas de compatibilidad con algunas de las dependencias por lo que opte por la versión python:3.7.
Luego me saltaron mensajes de error varios haciendo enfásis en faltas de dependencías que fueron arreglados modificando el Dockerfile. 

Finalmente construí el compose en el cual se realiza el build de la imágen y deployment de la misma obteniendo como resultado:

**ImproperlyConfigured: The SECRET_KEY setting must not be empty.**
Busque información y llegue a al siguiente [post.](https://stackoverflow.com/questions/7382149/whats-the-purpose-of-django-setting-secret-key) Esto me llevo a crear el archivo *.env* dentro de la carpeta backend y generar una SECRTE_KEY para su uso. Ahora si para finalizar, agregue esta variable de entorno al compose y el contenedor de Django termino funcionando.

### Frontend
Construí el Dockerfile y el compose en base a la documentación de React, no hubo mayores problemas, solo mensajes indicando que algunas dependencias correspondian a versiones deprecadas.