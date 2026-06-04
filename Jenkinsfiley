pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/ratheeshu2804/ecommerce-devops-project.git'
            }
        }

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
