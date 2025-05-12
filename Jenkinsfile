pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'docker build --no-cache -t toqueneldom .'
            }
        }
        stage('Run Container') {
            steps {
                sh 'docker rm -f toqueneldom || true'
                sh 'docker run -d -p 8081:80 --name toqueneldom toqueneldom'
            }
        }
    }
}
