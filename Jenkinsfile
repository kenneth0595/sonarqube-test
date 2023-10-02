pipeline {
    agent any
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 1, unit: 'SECONDS')
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
