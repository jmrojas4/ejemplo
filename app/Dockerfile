# Utilizamos una imagen base de Node.js
FROM node:18
# Establecemos el directorio de trabajo dentro del contenedor
WORKDIR /usr/src/app
# Copiamos el archivo package.json y el archivo package-lock.json (si existe)
COPY package*.json ./
# Instalamos las dependencias del proyecto
RUN npm config set proxy http://172.17.33.10:3128/
RUN npm config set https-proxy http://172.17.33.10:3128/
RUN npm install
# Copiamos el resto de los archivos de la aplicación
COPY . .
# Exponemos el puerto 3000 para que la aplicación pueda ser accedida desde fuera del contenedor
EXPOSE 3000
# Comando que se ejecutará cuando el contenedor se inicie
CMD [ "node", "app.js" ]

