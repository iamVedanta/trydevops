pipeline {
    agent any

    environment {
        IMAGE_NAME = "myapp"
        DOCKER_TAG = "latest"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/iamVedanta/trydevops.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME:$DOCKER_TAG .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -p 8081:8081 --name myapp_container -d $IMAGE_NAME:$DOCKER_TAG'
            }
        }
    }
}
