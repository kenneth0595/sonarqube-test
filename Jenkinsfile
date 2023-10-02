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
                    sh './mvnw clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.4:sonar'
                }
            }
        }
    }
}
