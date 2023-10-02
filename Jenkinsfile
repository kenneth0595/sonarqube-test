pipeline {
    agent any
    options {
        // Timeout counter starts AFTER agent is allocated
        buildDiscarder(logRotator(numToKeepStr: '5'))
    }
    stages {
        stage('Scan') {
            steps {
                withSonarQubeEnv(installationName: 'sonarqube') {
                    sh './mvnw clean org.sonarsource.scanner.maven:sonar-maven-plugin:5.0.1.3006:sonar'
                }
            }
        }
    }
}
