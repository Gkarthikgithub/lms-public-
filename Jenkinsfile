pipeline {
    agent {
        node{
            label 'BUILD'
        }
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'cd webapp &&sudo  docker build -t karthik/lms-app .'
               
            }
        }
       stage('push image') {
           steps{ 
               echo 'pushing image'
              withDockerRegistry([ credentialsId: "docker", url: "" ]) {
              sh "sudo docker push karthik/lms-app"
        } 
        
           }
        
        
        
        
         
        }
        
        
        
        
        
        
            
        
        
            
        
    }
}

