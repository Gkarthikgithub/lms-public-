pipeline {
   agent any
      

    stages {
        stage('Build') {
            steps {
                echo 'Building frontend ...'
                  sh 'cd webapp && npm install'
                  sh 'cd webapp && npm run build'
                    sh '  scp -r webapp/dist ubuntu@172.31.47.209:/home/ubuntu/dist'
            }
        }
        stage('DB') {
            steps {
                echo 'DATABASE'
               
               
            }
        }
        stage('Deploy') {
            steps {
                echo 'BUILDING BACKEND.'
               
               sh 'cd api && npm install'
                  
                  
                  sh 'cd api && npm run build'
                  sh 'scp -r api/build ubuntu@172.31.47.209:/home/ubuntu/dist'
               
                
            }
        }
    }
    
}
    
