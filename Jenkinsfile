pipeline {
    agent any

    environment {
        FRONTEND_IMAGE = 'ahmedhamdi1/devops-webapp-frontend'  
        BACKEND_IMAGE = 'ahmedhamdi1/devops-webapp-backend'    
        DOCKER_TAG = 'latest'
    }

    stages {
        stage('Clone Repository') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Images') {
            steps {
                script {
                    sh "docker build -t $FRONTEND_IMAGE:$DOCKER_TAG ./frontend"
                    sh "docker build -t $BACKEND_IMAGE:$DOCKER_TAG ./backend"
                }
            }
        }

        stage('Push Docker Images') {
            steps {
                script {
                    sh "docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD"
                    
                    sh "docker push $FRONTEND_IMAGE:$DOCKER_TAG"
                    
                    sh "docker push $BACKEND_IMAGE:$DOCKER_TAG"
                }
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                script {
                    sh "kubectl apply -f kubernetes/frontend-deployment.yaml"
                    sh "kubectl apply -f kubernetes/backend-deployment.yaml"
                }
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
