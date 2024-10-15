pipeline {
    agent any 
    
    stages { 
        stage('SCM Checkout') {
            steps {
                retry(3) {
                    git branch: 'main', url: 'https://github.com/CydexCode/CI-CD-Pipeline-With-GitHub-Docker-and-Jenkins'
                }
            }
        }
        stage('Build Docker Image') {
            steps {  
                bat 'docker build -t sachinthanabuddhika/node_app:%BUILD_NUMBER% .'
            }
        }
        stage('Login to Docker Hub') {
            steps {
               withCredentials([string(credentialsId: 'test-dockerhub-password', variable: 'test-dockerhub-password')]) {
                    script {
                        bat 'docker login -u sachinthanabuddhika -p ${test-dockerhub-password}'
                    }
                }
            }
        }
        stage('Push Image') {
            steps {
                bat 'docker push sachinthanabuddhika/node_app:%BUILD_NUMBER%'
            }
        }
    }
    post {
        always {
            bat 'docker logout'
        }
    }
}
