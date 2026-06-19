pipeline {
    agent any

    environment {
        IMAGE_NAME = "vedant-flask-app"
        CONTAINER_NAME = "flask-running-app"
    }

    stages {

        stage('Clone Repository') {
            steps {
                echo 'Cloning GitHub repo...'
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t ${IMAGE_NAME}:latest .'
            }
        }

        stage('Test Application') {
            steps {
                echo 'Testing application...'
                sh '''
                    docker run -d --name test-container -p 5001:5000 ${IMAGE_NAME}:latest
                    sleep 5
                    curl -f http://localhost:5001 || exit 1
                    docker stop test-container
                    docker rm test-container
                '''
            }
        }

        stage('Deploy Application') {
            steps {
                echo 'Deploying application...'
                sh '''
                    docker stop ${CONTAINER_NAME} || true
                    docker rm ${CONTAINER_NAME} || true
                    docker run -d \
                        --name ${CONTAINER_NAME} \
                        -p 5000:5000 \
                        ${IMAGE_NAME}:latest
                '''
            }
        }

    }

    post {
        success {
            echo 'Pipeline completed successfully! App is live.'
        }
        failure {
            echo 'Pipeline failed. Check logs above.'
        }
    }
}