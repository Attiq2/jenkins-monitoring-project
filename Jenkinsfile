pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Attiq2/devops-intern-project.git'
            }
        }

        stage('Build & Deploy Monitoring Stack') {
            steps {
                sh '''
                cd monitoring
                docker-compose down -v || true
                docker-compose up -d
                '''
            }
        }
    }

    post {
        always {
            sh 'docker ps'
        }
    }
}

