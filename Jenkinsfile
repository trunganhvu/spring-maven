pipeline {
    agent any  // Chạy trên bất kỳ node nào

    environment {
        IMAGE_NAME = "spring-maven-app"
        CONTAINER_NAME = "spring-maven-container"
        DOCKER_COMPOSE_PATH = "$WORKSPACE/docker-compose.yml"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/trunganhvu/spring-maven.git'
            }
        }

        stage('Build Maven Project') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh "docker build -t ${IMAGE_NAME} ."
            }
        }

        stage('Run with Docker Compose') {
            steps {
                sh "docker-compose -f ${DOCKER_COMPOSE_PATH} up -d --build"
            }
        }
    }

    post {
        always {
            echo "Pipeline finished"
        }
    }
}
