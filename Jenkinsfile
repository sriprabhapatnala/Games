pipeline {
    agent any

    environment {
        WORK_DIR = "/var/lib/jenkins/workspace/Game"
        IMAGE_NAME = "indie-gems"
        IMAGE_TAG  = "latest"
        CONTAINER_NAME = "indie-gems-container"
        PORT = "4000"
    }

    stages {

        stage('Checkout Code') {
            steps {
                dir("${WORK_DIR}") {
                    git branch: 'main', url: 'https://github.com/sriprabhapatnala/Games.git'
                }
            }
        }

        stage('Install Dependencies') {
            steps {
                dir("${WORK_DIR}") {
                    sh 'npm install'
                }
            }
        }

        stage('Run Tests (Optional)') {
            steps {
                dir("${WORK_DIR}") {
                    sh 'npm test || true'
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                dir("${WORK_DIR}") {
                    sh '''
                        docker rmi -f ${IMAGE_NAME}:${IMAGE_TAG} || true
                        docker build -t ${IMAGE_NAME}:${IMAGE_TAG} .
                    '''
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                dir("${WORK_DIR}") {
                    sh '''
                        docker rm -f ${CONTAINER_NAME} || true
                        docker run -d --name ${CONTAINER_NAME} -p ${PORT}:3000 ${IMAGE_NAME}:${IMAGE_TAG}
                    '''
                }
            }
        }
    }

    post {
        always {
            echo "Pipeline finished! Check http://13.204.85.107:${PORT}"
        }
    }
}
