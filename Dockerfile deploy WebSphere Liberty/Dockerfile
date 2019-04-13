# En este caso estoy parado en el directorio base del proyecto (donde esta el pom.xml) y ejecuto el siguiente
# comando para crear la imagen:
# docker image build -t <nombre-nueva-imagen> -f ./Dockerfile target
# Donde target es el directorio donde esta el WAR

# En el directorio target tambien tengo que poner el server.xml para asi configurar el adminCenter
# Para abrir el adminCenter: http://<ip-docker-machine>:9080/adminCenter
# Usuario y pwd estan configurados en el server.xml

# Crear el contenedor ejecutando:
# docker container run -p 9080:9080 -p 9443:9443 --name <nombre-contenedor> <nombre-nueva-imagen>

FROM websphere-liberty
COPY --chown=1001:0  RESTPrueba2.war /config/dropins/
RUN installUtility install adminCenter-1.0 --acceptLicense
COPY server.xml /opt/ibm/wlp/usr/servers/defaultServer/
ENV LICENSE accept
EXPOSE 80 9080 9448 9443 9060