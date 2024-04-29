# Test Sermaluc
Pruba técnica SERMALUC.
##

# Requisitos# para Levantar los servicios:
Open JDK JAVA 11.
Maven.
Curl o Postman.
##

# Para levantar el proyecto:

# Iniciar microservicio Eureka: 
Dirigirse al directorio del microservicio servidor eureka desde una consola y ejecutar las siguientes líneas de comandos:
1. cd ./springboot-servicio-eureka-server 
2. mvn clean install
3. mvn spring-boot:run
   
# Iniciar microservicio OAuth:
Dirigirse al directorio del microservicio oauth desde una consola y ejecutar las siguientes líneas de comandos:
1. cd ./springboot-servicio-oauth-server 
2. mvn clean install
3. mvn spring-boot:run
   
# Iniciar microservicio Usuarios:
Dirigirse al directorio del microservicio usuarios desde una consola y ejecutar las siguientes líneas de comandos:
1. cd ./springboot-servicio-usuarios-server 
2. mvn clean install
3. mvn spring-boot:run
   
# Iniciar microservicio Gateway:
Dirigirse al directorio del gateway microservicio gateway desde una consola y ejecutar las siguientes líneas de comandos:
1. cd ./springboot-servicio-zuul-server 
2. mvn clean install
3. mvn spring-boot:run
   
# Generar JAR de libreria commons de Model/Entity de Usuarios:
Dirigirse al directorio del microservicio  desde una consola y ejecutar las siguientes líneas de comandos:
1. cd ./springboot-servicio-usuarios-commons 
2. mvn clean install
##

# Probando los end - point 

