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
        stage('build') {
            steps {
                echo 'building backend...'
                  sh 'cd api && npm install'
                  sh 'cd api && npm run build'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
               sh '  scp -r webapp/dist ubuntu@172.31.41.206:/home/ubuntu/dist'
               
                
            }
        }
    }
    
}
    
