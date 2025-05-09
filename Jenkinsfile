pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build --no-cache -t toquenElDom .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f toquenElDom || true'
                sh 'docker run -d -p 8081:80 --name toquenElDom toquenElDom'
            }
        }
    }
}

