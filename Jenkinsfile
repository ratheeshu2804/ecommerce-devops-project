pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ecommerce .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker stop ecommerce || true
                docker rm ecommerce || true
                docker run -d --name ecommerce -p 80:80 ecommerce
                '''
            }
        }
    }
}
