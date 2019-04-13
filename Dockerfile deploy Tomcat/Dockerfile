# En este caso estoy parado en el directorio base del proyecto (donde esta el pom.xml) y ejecuto el siguiente
# comando para crear la imagen:
# docker image build -t <nombre-nueva-imagen> -f ./Dockerfile target
# Donde target es el directorio donde esta el WAR
FROM tomcat:alpine
COPY RESTPrueba2.war /usr/local/tomcat/webapps/RESTPrueba2.war

