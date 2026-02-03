pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/SUBASRI06/coffee-shop-devops.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t coffee-shop .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop coffee || true
                docker rm coffee || true
                docker run -d --name coffee -p 8080:80 coffee-shop
                '''
            }
        }
    }
}
