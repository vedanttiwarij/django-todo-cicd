pipeline {
    agent any

    environment {
        IMAGE_NAME = "django-todo-app"
        CONTAINER_NAME = "django-running-app"
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

        stage('Deploy Application') {
            steps {
                echo 'Deploying Django app...'
                sh '''
                    docker stop ${CONTAINER_NAME} || true
                    docker rm ${CONTAINER_NAME} || true
                    docker run -d \
                        --name ${CONTAINER_NAME} \
                        -p 8000:8000 \
                        ${IMAGE_NAME}:latest
                '''
            }
        }

    }

    post {
        success {
            echo 'Pipeline completed! Django app is live on port 8000.'
        }
        failure {
            echo 'Pipeline failed. Check logs above.'
        }
    }
}