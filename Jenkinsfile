pipeline {
   agent {
      node{
         label 'build'
      }
   }
      

    stages {
        stage('Build') {
            steps {
                echo 'Building frontend ...'
                  sh 'cd webapp && npm install'
                  sh 'cd webapp && npm run build'
                    
            }
        }
        stage('DB') {
            steps {
                echo 'DATABASE.'
               sh ' sudo apt install postgresql -y'
               
               
               
            }
        }
        stage('Deploy') {
            steps {
                echo 'BUILDING BACKEND.'
               
               sh 'cd api && npm install'
                  
                  
                  sh 'cd api && npm run build'
                  
               
                
            }
        }
    }
    
}
    
