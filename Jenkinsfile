pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Repository checked out successfully'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-project .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '''
                docker rm -f my-project-container || true
                docker run -d --name my-project-container -p 80:80 my-project
                '''
            }
        }
    }
}
