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
                sh ' sudo scp -i -r webapp/dist ubuntu@172.31.35.56:~'
            }
        }
    }
}
