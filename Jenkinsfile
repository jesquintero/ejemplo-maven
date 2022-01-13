pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                script {
                    sh "./mvnw clean compile -e"
                }
            }
        }
        
        stage('SonarQube Analysis') {
            steps {
                script {
                    def scannerHome = tool 'sonar-scanner';
                    withSonarQubeEnv('LocalSonarServer'){
                        sh "${scannerHome}/bin/sonar-scanner
                        -Dsonar.projectKey=ejemplo-maven
                        -Dsonar.sources=src
                        -Dsonar.java.binaries=build"
                    }
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    sh "./mvnw clean test -e"
                }
            }
        }
        
        stage('Clean') {
            steps {
                script {
                    sh "./mvnw clean package -e"
                }
            }
        }
        
        stage('Build') {
            steps {
                script {
                    sh "nohup bash mvnw spring-boot:run &"
                }
            }
        }
        
        stage('Test-Connection') {
            steps {
                script {
                    sh "curl -X GET 'http://localhost:8080/rest/mscovid/test?msg=testing'"
                }
            }
        }
    }
}
