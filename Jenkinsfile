pipeline {
 agent any 
       environment {
           PATH="/opt/maven/bin/:$PATH"
   }    
    stages{
      stage ('git checkout') {
        steps {
          git branch: 'main', url: 'https://github.com/udaysk36/javaapp.git'
      }
    }
      stage ('unit test') { 
        steps{
            sh 'mvn test'
     }
   }
     stage ('Integration test') { 
        steps{
            sh 'mvn verify -DeskipUnitTest'
      }
   }
     stage('maven build') {
       steps{
            sh 'mvn clean install'
      }
   }
     stage('static code') {
       steps{
          script{
            withSonarQubeEnv(credentialsId: 'sonar-api') {
              sh 'mvn clean package sonar:sonar'
           }
        }
     }
    }
     stage('store art factory')
      steps{
       scripts{
            nexusArtifactUploader artifacts:
             [
               [
                 artifactId: 'spring-boot-starter-parent', 
                 classifier: '', 
                 file: 'target/2.2.1.jar', 
                 type: 'jar'
               ]
            ], 
                  credentialsId: 'nexus', 
                  groupId: 'org.springframework.boot', 
                  nexusUrl: '13.53.40.31:8081', 
                  nexusVersion: 'nexus3', 
                  protocol: 'http', 
                  repository: 'java-demoapp', 
                  version: '2.2.1'
            }
       }
   }
} 
     
