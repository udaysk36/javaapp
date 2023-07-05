pipeline {
  agent any 
    stages {
      stage ('git checkout') {
        steps{
          git branch: 'main', url: 'https://github.com/udaysk36/javaapp.git'
      }
    } 
    stage ('Unittest') {
      steps{
        sh 'mvn clean verify-DskipITs=true';junit '**/target/surefire-reports/TEST-*.xml'archive 'target/*.jar'
      }
    } 
  }
} 
