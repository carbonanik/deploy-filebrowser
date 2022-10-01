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
                sh '''
docker run \
    --name filebrowser \
    --network=behind-nginx-network \
    --restart unless-stopped \
    -v /:/srv \
    -v /data/filebrowser/database:/database/ \
    -v /data/filebrowser/config:/config/ \
    -e PUID=$(id -u) \
    -e PGID=$(id -g) \
    -p 8070:80 \
    -d \
    filebrowser/filebrowser:s6
                '''
            }
        }
    }
}