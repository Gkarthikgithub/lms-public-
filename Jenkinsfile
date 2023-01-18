pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                  sh 'cd webapp && npm install'
                  sh 'cd webapp && npm run build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh '   scp  -r webapp/dist ubuntu@172.31.33.4:/home/ubuntu/dist:~'
            }
        }
    }
}
