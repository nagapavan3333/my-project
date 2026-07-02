pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                echo 'Repository cloned successfully'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-website .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f my-container || true
                docker run -d --name my-container -p 80:80 my-website
                '''
            }
        }
    }
}
