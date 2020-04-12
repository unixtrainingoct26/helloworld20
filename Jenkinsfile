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
          
        }
      
      
      }
        stage('test '){
        steps {
          echo "test step"
          sh 'mvn test'
        }
      
      
      }
        stage('deploy'){
        steps {
          echo "deploy war file"
          sshPublisher(publishers: [sshPublisherDesc(configName: 'docker_host', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'docker rmi contact:2.0 ;docker build -t contact:2.0 . ; docker tag contact:2.0 dockeroct2020/contact:2.0 ; docker push dockeroct2020/contact:2.0 ; docker run -itd -p 8086:8080 dockeroct2020/contact:2.0', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '.', remoteDirectorySDF: false, removePrefix: 'webapp/target', sourceFiles: '**/*.war')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
        }
      
      
      }
    
    }

}



    


