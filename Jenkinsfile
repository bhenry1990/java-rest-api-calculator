pipeline {
    // small change
    agent any
    
    stages {
        stage ('Build') {
            steps {
                git 'https://github.com/bhenry1990/java-rest-api-calculator.git'
                // sh './mvnw clean compile'
                bat './mvnw clean compile'
            }
        }
        stage ('Test') {
            steps {
                // sh './mvn test'
                bat './mvnw test'
            }

            post {
                always {
                    junit'**/target/surefire-reports/TEST-*.xml'
                }
            }
        }
        stage ('Publish') {
            steps {
                // sh './mvn package'
                bat './mvn package'
            }
            post {
                success {
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
    }
}