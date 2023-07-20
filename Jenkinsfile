pipeline {
 agent any 
       environment {
           PATH="/opt/maven/bin/:$PATH"
   }    
    stages {
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
   }     
}  
  
