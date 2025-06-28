pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                echo "Building Docker image: vinayvinnu24/adservice:v1"
                sh "docker build -t vinayvinnu24/adservice:v1 ."
            }
        }

        stage('Push Docker Image') {
            steps {
                echo "Pushing Docker image to Docker Hub"
                script {
                    withDockerRegistry([credentialsId: 'docker-cred') {
                        sh "docker push vinayvinnu24/adservice:v1 "
                    }
                }
            }
        }
    }
}
