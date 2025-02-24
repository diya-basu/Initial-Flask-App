pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/diya-basu/Initial-Flask-App.git', branch:'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name flask-container flask-app'
            }
        }
    }

    post {
        always {
            sh 'docker ps -a'
        }
    }
}


