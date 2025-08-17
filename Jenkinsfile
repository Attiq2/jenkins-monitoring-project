pipeline {
    agent { label 'ubuntu-agent' }

    environment {
        // Add any environment variables if needed
        DOCKER_HOST = 'unix:///var/run/docker.sock'
    }

    stages {
        stage('Checkout Monitoring Project') {
            steps {
                git branch: 'main',
                    url: 'git@github.com:Attiq2/jenkins-monitoring-project.git',
                    credentialsId: 'jenkins-github-ssh'
            }
        }

        stage('Checkout DevOps Intern Project') {
            steps {
                git branch: 'main',
                    url: 'git@github.com:Attiq2/devops-intern-project.git',   // ✅ correct repo
                    credentialsId: 'jenkins-github-ssh'
            }
        }

        stage('Build & Deploy Monitoring Stack') {
            steps {
                script {
                    sh '''
                        cd monitoring
                        docker-compose up -d
                    '''
                }
            }
        }
    }

    post {
        success {
            echo '✅ Monitoring stack deployed successfully!'
        }
        failure {
            echo '❌ Pipeline failed. Check logs for errors.'
        }
    }
}
