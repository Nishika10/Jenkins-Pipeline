pipeline {
    agent any

    environment {
        IMAGE_NAME = "html-nginx-demo"
        CONTAINER_NAME = "html-nginx-container"
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Pulling latest code from GitHub...'
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t ${IMAGE_NAME} .'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying container...'
                // Stop and remove old container (if any)
                sh '''
                if [ "$(docker ps -aq -f name=${CONTAINER_NAME})" ]; then
                    docker rm -f ${CONTAINER_NAME}
                fi
                docker run -d --name ${CONTAINER_NAME} -p 8080:80 ${IMAGE_NAME}
                '''
            }
        }
    }

    post {
        success {
            echo ' Deployment successful! Visit http://localhost:8080 to view the app.'
        }
        failure {
            echo ' Build or Deployment failed.'
        }
    }
}
