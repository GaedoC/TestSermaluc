# Prueba Técnica Sermaluc
Desarrollo con Spring Boot, Spring Security, REST, OAuth2, Arquitectura de Microservicios compuesto por: Microservicio Servidor de registro, Microservicio Servidor Gateway, Microservicio servidor de Autenticación OAUTH2 y JWT, Microservicio Commons Usuarios, Microservicio  Usuarios.
##

# Requisitos para Levantar los servicios:
1. Open JDK JAVA 11 u 8
2. Maven
3. Curl o Postman
##

# Levantar proyecto en el siguiente Orden:


## 1. Generar JAR de libreria commons de Model de Usuarios:
Dirigirse al directorio del microservicio desde una consola y ejecutar las siguientes líneas de comandos:
1. cd ./springboot-servicio-usuarios-commons 
2. mvn clean install


## 2. Iniciar microservicio Eureka: 
Dirigirse al directorio del microservicio servidor eureka desde una consola y ejecutar las siguientes líneas de comandos:
1. cd ./springboot-servicio-eureka-server 
2. mvn clean install
3. mvn spring-boot:run
   
## 3. Iniciar microservicio OAuth:
Dirigirse al directorio del microservicio oauth desde una consola y ejecutar las siguientes líneas de comandos:
1. cd ./springboot-servicio-oauth-server 
2. mvn clean install
3. mvn spring-boot:run
   

## 4. Iniciar microservicio Usuarios:
Dirigirse al directorio del microservicio usuarios desde una consola y ejecutar las siguientes líneas de comandos:
1. cd ./springboot-servicio-usuarios-server 
2. mvn clean install
3. mvn spring-boot:run
   

## 5. Iniciar microservicio Gateway:
Dirigirse al directorio del gateway microservicio gateway desde una consola y ejecutar las siguientes líneas de comandos:
1. cd ./springboot-servicio-zuul-server 
2. mvn clean install
3. mvn spring-boot:run
   
##
# Probar microservicios con CURL.
Se puede probar en Postman adjunto en este repositorio se encuentra la colección con los request.En esta ocación lo realizaremos a traves de la línea de comandos utilizando la herramienta CURL.
- Request Metodo POST - Obtener Tóken ejecutamos por consola:
1. curl --location 'localhost:8090/api/security/oauth/token' --header 'Content-Type: application/x-www-form-urlencoded' --header 'Authorization: Basic ZnJvbnRlbmRhcHA6MTIzNDU=' --data-urlencode 'username=andres' --data-urlencode 'password=12345' --data-urlencode 
   'grant_type=password'
   
![image](https://github.com/GaedoC/TestSermaluc/assets/17816969/f3c80b9f-4c26-4ff0-8645-a510619b1893)

- Request Metodo GET - Obtener todos los usuarios(No requiere Autenticación):
2. curl localhost:8090/api/usuarios/usuarios/
  
 ![image](https://github.com/GaedoC/TestSermaluc/assets/17816969/8e33b3b3-035c-47dc-b760-cc3ff16146ea)

- Request Metodo GET - Obtener usuario por Id(Requiere Autenticacion con Bearer Tóken, lo generamos en el punto 1 ):
3. curl --location 'localhost:8090/api/usuarios/usuarios/1' --header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX25hbWUiOiJ0ZXN0TW9kaWZpY2FkbzMzIiwic2NvcGUiOlsicmVhZCIsIndyaXRlIl0sImFwZWxsaWRvIjoiQWVkbzIzIiwiY29ycmVvIjoidGVzdDIzQG1haWwuY29tIiwiZXhwIjoxNzE0MzY5OTA0LCJub21icmUiOiJ0ZXN0TW9kaWZpY2FkbzMzIiwiYXV0aG9yaXRpZXMiOlsiUk9MRV9BRE1JTiIsIlJPTEVfVVNFUiJdLCJqdGkiOiJiNDg0ZTEwZi05YjdkLTRiY2UtOTAwYS0yMmUzNmFkMWQ4YjgiLCJjbGllbnRfaWQiOiJmcm9udGVuZGFwcCJ9.ojDV-xYS3b8O8OkLF_v-WLbLNizv-pIoo1BJY7VoLBs'
  
![image](https://github.com/GaedoC/TestSermaluc/assets/17816969/8408cb5e-d991-4a68-9e3d-f0c5a59e23a1)

- Request Metodo POST - Crear Usuario(Requiere Autenticacion con Bearer Tóken, lo generamos en el punto 1 ):
4. curl --location 'http://localhost:8090/api/usuarios/usuarios/' --header 'Content-Type: application/json' --header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX25hbWUiOiJhbmRyZXMiLCJzY29wZSI6WyJyZWFkIiwid3JpdGUiXSwiYXBlbGxpZG8iOiJBZWRvIiwiY29ycmVvIjoiY2FlZG9AbWFpbC5jb20iLCJleHAiOjE3MTQzNjkzMjAsIm5vbWJyZSI6IkNyaXN0b2JhbCIsImF1dGhvcml0aWVzIjpbIlJPTEVfQURNSU4iLCJST0xFX1VTRVIiXSwianRpIjoiMDc2Y2RhYTMtOTA1NC00ODVkLWFlNDktYWVlZDk1YTRmMGE1IiwiY2xpZW50X2lkIjoiZnJvbnRlbmRhcHAifQ.uB5hpOO1qVdx-OEdJnJDfP_ZtMXz34d8bOV9_axi6oE' --data-raw '{
    "fechaCreacion": null,
    "fechaActualizacion": null,
    "username": "test75352",
    "password": "$2a$10$NZp9GgbTPYFft6oPjZyLXOeIoGb.0WJGdqOSwqNjLzI2pfLXMJYsm",
    "enabled": true,
    "nombre": "test73552",
    "apellido": "Aedo75352",
    "email": "tes75532@mail.com",
    "phones": [
        { 
            "id": 1,
            "number": 56505213,
            "citycode": 9,
            "countryCode": 56
        },
        {
              "id": 2,
            "number": 56505213,
            "citycode": 9,
            "countryCode": 56
        }
    ],
    "roles": [
        {
            "id": 1,
            "nombre": "ROLE_USER"
        },
         {
            "id": 2,
            "nombre": "ROLE_ADMIN"
        }
    ]

}'
  
![image](https://github.com/GaedoC/TestSermaluc/assets/17816969/27c0b0a0-ee05-45d6-be2a-2df241f8c772)



- Request Metodo PUT - Actualizar Usuario(Requiere Autenticacion con Bearer Tóken, lo generamos en el punto 1):
5. curl --location 'http://localhost:8090/api/usuarios/usuarios/' --header 'Content-Type: application/json' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX25hbWUiOiJhbmRyZXMiLCJzY29wZSI6WyJyZWFkIiwid3JpdGUiXSwiYXBlbGxpZG8iOiJBZWRvIiwiY29ycmVvIjoiY2FlZG9AbWFpbC5jb20iLCJleHAiOjE3MTQzNjkzMjAsIm5vbWJyZSI6IkNyaXN0b2JhbCIsImF1dGhvcml0aWVzIjpbIlJPTEVfQURNSU4iLCJST0xFX1VTRVIiXSwianRpIjoiMDc2Y2RhYTMtOTA1NC00ODVkLWFlNDktYWVlZDk1YTRmMGE1IiwiY2xpZW50X2lkIjoiZnJvbnRlbmRhcHAifQ.uB5hpOO1qVdx-OEdJnJDfP_ZtMXz34d8bOV9_axi6oE' --data-raw '{
    "fechaCreacion": null,
    "fechaActualizacion": null,
    "username": "test2",
    "password": "$2a$10$NZp9GgbTPYFft6oPjZyLXOeIoGb.0WJGdqOSwqNjLzI2pfLXMJYsm",
    "enabled": true,
    "nombre": "test2",
    "apellido": "Aedo2",
    "email": "tes2@mail.com",
    "phones": [
        { 
            "id": 1,
            "number": 56505213,
            "citycode": 9,
            "countryCode": 56
        },
        {
              "id": 2,
            "number": 56505213,
            "citycode": 9,
            "countryCode": 56
        }
    ],
    "roles": [
        {
            "id": 1,
            "nombre": "ROLE_USER"
        },
         {
            "id": 2,
            "nombre": "ROLE_ADMIN"
        }
    ]

}'
![image](https://github.com/GaedoC/TestSermaluc/assets/17816969/7b63bf3f-427b-4cc9-8cc2-cfd493899ee0)



