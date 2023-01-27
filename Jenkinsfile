pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'cd webapp &&sudo  docker build -t karthik/lms-app .'
               
            }
        }
       stage('push image') {
           steps{  
              withDockerRegistry([ credentialsId: "karthikeyudu", url: "" ]) {
              sh "sudo docker push karthik/lms-app"
        } 
        
           }
        
        
        
        
         
        }
        
        
        
        
        
        
            
        
        
            
        
    }
}

