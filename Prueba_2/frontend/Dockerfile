FROM node:current-alpine3.15

#Elijo como directorio de trabajo: project
WORKDIR /project

#Copio el contenido del directorio con sus dependencias
COPY . .

#instalo las dependencias
RUN npm install

EXPOSE 3000

#Largo la app
CMD ["npm", "start"]