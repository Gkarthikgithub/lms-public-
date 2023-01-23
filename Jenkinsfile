pipeline {
   agent any
      

    stages {
        stage('Build') {
            steps {
                echo 'Building frontend ..'
                  sh 'cd webapp && npm install'
                  sh 'cd webapp && npm run build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
               sh 'scp -r var/lib/workspace/lms-app/webapp/dist ubuntu@172.31.41.206:/home/ubuntu/dist'
               
                
            }
        }
    }
    
}
    
