pipeline {
    agent any
    
    stages {
        stage ('Build') {
            steps {
                git 'https://github.com/bhenry1990/java-rest-api-calculator.git'
                // sh './mvnw clean compile'
                bat './mvnw clean compile'
            }
        }
    }
}