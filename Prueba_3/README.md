<img src="https://i.ibb.co/VM5MzBT/craftech-logo3.png=150x" width="250" height="250">

>  ***ATENCION: La prueba tecnica completa debe ser entregada en un unico repositorio***

#### Prueba 3 - CI/CD

Dockerizar un nginx con el index.html default.
Elaborar un pipeline que ante cada cambio realizado sobre el index.html buildee la nueva imagen y la actualize en la plataforma elegida. (docker-compose, swarm, kuberenetes, etc.)
Para la creacion del CI/CD se puede utilizar cualquier plataforma (CircleCI, Gitlab, Github, Bitbucket.)

**Requisitos y deseables:**

La solución al ejercicio debe mostrarnos que usted puede:

Automatizar la parte del proceso de despliegue.
usar conceptos de CI para aprovisionar el software necesario para que los entregables se ejecuten
use cualquier herramienta de CI de su elección para implementar el entregable

***

## Resolución

### Dockerizacion de nginx
Cree una Dockerfile a partir de la imágen ofical nginx. Además cree una carpeta llamada "html" con el archivo "index.html" que va a hacer el **trigger** del flujo de github actions.

### Pasos realizados
Utilicé github actions ya que entrega debe ser realizada en un repositorio en github.

1. Cree una cuenta de Dockerhub.
2. Ingrese las credenciales como secretos en el repositorio a trabajar.
3. Cree el archivo "deploy.yml" dentro de la carpeta ".github/workflows"
4. Solución de problemas varios a la hora de hacer el proceso de CI. (Principalmente problemas de referencia)

***
## Test
Para realizar un test para el workflow de integración continua:
1. Colocarse dentro de la rama *feat-prueba_3*
2. Modificar el archivo "/Prueba_3/html/index.html"
3. Realizar un commit bajo el tipo *test*
4. Realizar un push

Luego ir a la sección *Actions* del repositorio para verificar.