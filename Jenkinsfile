pipeline {
   agent {
      node{
         label 'build'
      }
   }
      

    stages {
        
        stage('DB') {
            steps {
                echo 'DATABASE.'
               
               
             

 sh'sudo apt-get update'
sh 'sudo apt-get -y install postgresql'

               
               
               
            }
        }
        stage('backend') {
            steps {
                echo 'BUILDING BACKEND..'
               
               sh 'cd api && npm install'

               sh 'cd api && sudo npm install -g pm2'
               sh 'cd api && sudo npx prisma db push'
               sh 'cd api && npm run build'
               sh 'cd api && NODE_PORT=8080 pm2 start -i 0 build/index.js'
               sh 'cd api &&  curl http://localhost:8080'
               sh 'sudo systemctl reload nginx'
               sh 'sudo systemctl restart nginx'
                  
                  
                  
                  
               
                
            }
        }
    
    
  
stage('Build') {
            steps {
                echo 'Building frontend ...'
                  sh 'cd webapp && npm install'
                  sh 'cd webapp && npm run build'
                    
            }
        }
    }
}
    
