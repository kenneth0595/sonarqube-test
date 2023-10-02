pipeline {
       agent any
       stages{
           stage('SCM') {
               steps {
                   git branch: "main",
                   url: "https://github.com/kenneth0595/fastcampus-jenkins.git"
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
