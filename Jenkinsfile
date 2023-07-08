pipeline {
 agent any 
    stages {
      stage ('git checkout') {
        steps {
          git branch: 'main', url: 'https://github.com/udaysk36/javaapp.git'
      }
    }
      stage ('UNIT TESTING') { 
        steps{
            sh 'mvn test'
        }
      }
   }     
}  
  
