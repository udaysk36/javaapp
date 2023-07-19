pipeline {
 agent any 
    stages {
      stage ('git checkout') {
        steps {
          git branch: 'main', url: 'https://github.com/udaysk36/javaapp.git'
      }
    }
      stage ('build') { 
        steps{
            sh 'mvn clean package'
        }
      }
   }     
}  
  
