pipeline {
    agent any 
    tools {
        maven 'M2_HOME'
    }
    stages {
      stage('Build'){
        steps {
          echo "Build step"
            sh 'mvn clean'
            sh 'mvn install'
            sh 'mvn package'
            echo 'building the application'
          
        }
      
      
      }
        stage('test '){
        steps {
          echo "test step"
          sh 'mvn test'
            echo 'testing the application'
        }
      
      
      }
        stage('deploy'){
        steps {
          echo "deploy war file"
         echo 'deploying the application
            
        }
      
      
      }
    
    }

}



    


