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
                sh 'docker compose up --build'
                sh 'docker compose ps'
            }
        }
    }
}