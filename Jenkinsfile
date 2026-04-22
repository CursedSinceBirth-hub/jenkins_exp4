pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                echo "Building Docker Image..."
                bat 'docker build -t exp4-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                bat 'docker stop exp4-container || exit 0'
                bat 'docker rm exp4-container || exit 0'
            }
        }

        stage('Run Container') {
            steps {
                echo "Deploying container..."
                bat 'docker run -d -p 5002:5002 --name exp4-container exp4-app'
            }
        }

    }
}