pipeline {
 agent any 
    stages {
      stage ('git checkout') {
        steps {
          git branch: 'main', url: 'https://github.com/udaysk36/javaapp.git'
      }
    }
      stage ('unit test') { 
        steps{
           junit allowEmptyResults: true, checksName: 'junit test', testResults: 'javaapp/pom.xml'
        }
      }
   }     
}  
  
