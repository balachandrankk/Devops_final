pipeline {
    agent any
    
    environment {
        COMPOSE_PROJECT_DIR = "${env.WORKSPACE}"  
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/balachandrankk/guvi_dev_final.git'
            }
        }

        stage('Build and Run') {
            steps {
                script {
                    sh 'docker-compose down || true'  
                    sh 'docker-compose up -d --build'  
                }
            }
        }

        stage('Verify') {
            steps {
                sh 'curl -I http://localhost:8081'  
            }
        }
    }
}
