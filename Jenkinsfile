pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'cd webapp &&sudo  docker build -t karthik/lms-app .'
               
            }
        }
        stage('push image') {
             
              withDockerRegistry([ credentialsId: "docker-hub-credentials", url: "" ]) {
              sh "docker push karthik/lms-app"
        } 
        
        
        
        
        
        
         
        }
        
        
        
        
        
        
            
        
        
            
        
    }
}

