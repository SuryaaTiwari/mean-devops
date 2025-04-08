pipeline {
    agent any

    tools {
        jdk 'jdk-17'
        maven 'maven'
    }

    environment {
        DOCKER_CREDENTIALS_ID = 'dockerhub'
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/SuryaaTiwari/mean-devops-project.git'
            }
        }

        stage('Build & Push Backend') {
            steps {
                script {
                    docker.withRegistry('', DOCKER_CREDENTIALS_ID) {
                        def be = docker.build("suryaprakashtiwarirj/mean-backend", "backend")
                        be.push()
                    }
                }
            }
        }

        stage('Build & Push Frontend') {
            steps {
                script {
                    docker.withRegistry('', DOCKER_CREDENTIALS_ID) {
                        def fe = docker.build("suryaprakashtiwarirj/mean-frontend", "frontend")
                        fe.push()
                    }
                }
            }
        }

        stage('Deploy with Docker Compose') {
            steps {
                sh '''
                    docker-compose down
                    docker-compose pull
                    docker-compose up -d
                '''
            }
        }
    }
}

