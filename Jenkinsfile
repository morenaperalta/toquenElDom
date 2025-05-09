pipeline {
    agent {
        docker {
            image 'docker:latest'
            args '-v /var/run/docker.sock:/var/run/docker.sock -u root'
        }
    }
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

