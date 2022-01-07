# Getting Started

## Windows

### Compile Code
* ./mvnw.cmd clean compile -e

### Test Code
* ./mvnw.cmd clean test -e

### Jar Code
* ./mvnw.cmd clean package -e

### Run Jar
* Local:      ./mvnw.cmd spring-boot:run 
* Background: nohup bash mvnw.cmd spring-boot:run &

### Testing Application
* Abrir navegador: http://localhost:8080/rest/mscovid/test?msg=testing

## Linux

### Compile Code
* ./mvnw clean compile -e

### Test Code
* ./mvnw clean test -e

### Jar Code
* ./mvnw clean package -e

### Run Jar
* Local:      ./mvnw spring-boot:run 
* Background: nohup bash mvnw spring-boot:run &

### Testing Application
* curl -X GET 'http://localhost:8080/rest/mscovid/test?msg=testing'

### Jenkins on Ngrok
* Esta herramienta nos permite publicar una aplicación a través de una DNS dinámico desde nuestro PC
https://ngrok.com/


### Cambio para invocar el Github Webhook con push y Jenkinsfile para la tarea