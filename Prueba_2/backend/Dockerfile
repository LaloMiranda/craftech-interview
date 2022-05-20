FROM python:3.7

#Elijo como directorio de trabajo: project
WORKDIR /project

#Copio el contenido de la carpeta donde se ubica el dockerfile dentro de project
COPY . .

#Realizo un update e instalol a nueva version de pip
RUN apt-get update \
    && apt-get install python3-dev graphviz libgraphviz-dev pkg-config -y \
    && pip install --upgrade pip \
    && pip install pygraphviz

#Instalo el listado de items dentro de requirements
RUN pip3 install -r requirements.txt

EXPOSE 8000

#Corro el manage.py utilizando el puerto 8000
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
