
pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Yuvankrishnastackly/Notes-Application.git'
            }
        }

        stage('Build') {
            steps {
                sh 'sudo docker compose build'
            }
        }

        stage('Deploy') {
            steps {
                sh 'sudo docker compose up -d'
            }
        }

        stage('Verify') {
            steps {
                sh 'sudo docker compose ps'
            }
        }
    }

    post {
        always {
            echo 'Deployment pipeline completed.'
        }
    }
}

