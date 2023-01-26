pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'cd webapp &&sudo  docker build -t karthik/lms-app .'
                sh ' sudo docker push karthik/lms-app'
            }
        }
        stage('Push image') {
        withDockerRegistry([ credentialsId: "admin", url: "" ]) {
        sh "docker push karthik/lms-app"
        }
        
        
        
        
        
        
            
        
        
            
        
    }
}
}
