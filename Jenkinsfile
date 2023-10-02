pipeline {
       agent any
       stages{
           stage('SCM') {
               steps {
                   git branch: "dev",
                   url: "https://github.com/foo/bar.git"
               }
           }
        
                   stage('Test') {
               steps {
                   dir('backend') {
                       sh './gradlew test'
                   }
               }
           }
                
           stage('SonarQube analysis') {
               steps {
                   withSonarQubeEnv('sonarqube') { 
                       dir('backend') {
                           sh './gradlew sonarqube'
                       }
                   }
               }
           }
       }
   }
