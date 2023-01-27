pipeline {
   agent any
      

    stages {
        stage('Build') {
            steps {
                echo 'Building frontend ..'
                  sh 'cd webapp && npm install'
                  sh 'cd webapp && npm run build'
                    sh '  scp -r webapp/dist ubuntu@172.31.41.206:/home/ubuntu/dist'
            }
        }
        stage('DB') {
            steps {
                echo 'DATABASE'
               sh 'sudo yum install postgresql -y'
               sh 'sudo yum update -y'
            }
        }
        stage('Deploy') {
            steps {
                echo 'BUILDING BACKEND.'
               
               sh 'cd api && npm install'
                  sh 'cd api && sudo npm install -g pm2'
                  sh 'cd api && npx prisma db push'
                   sh    'cd api &&DATABASE_URL=("postgresql://postgres:password@localhost:5432/postgres")'
                  
                  sh 'cd api && npm run build'
                  sh 'cd api && NODE_PORT=8080 pm2 start -i 0 build/index.js'  
                  sh 'cd api && curl http://localhost:8080'
               
                
            }
        }
    }
    
}
    
