pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t calculator-app .'
            }
        }

        stage('Run Container') {
            steps {
                bat '''
                docker rm -f calculator || echo no container
                docker run -d -p 8004:8004 --name calculator calculator-app
                '''
            }
        }
    }
}
