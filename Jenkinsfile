pipeline {
    agent any
    stages {
        stage('verifing') {
            steps {
                sh '''
                docker version
                '''
            }
        }
        stage('start filebrowser') {
            steps {
                sh 'docker compose up -d --build'
                sh 'docker compose ps'
            }
        }
    }
}