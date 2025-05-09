pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'sudo docker build --no-cache -t toquenElDom .'
            }
        }
        stage('Run Container') {
            steps {
                sh 'sudo docker rm -f toquenElDom || true'
                sh 'sudo docker run -d -p 8081:80 --name toquenElDom toquenElDom'
            }
        }
    }
}
