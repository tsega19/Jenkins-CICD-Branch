pipeline {
    agent any 
    
    stages { 
        stage('SCM Checkout') {
            steps {
                retry(3) {
                    git branch: 'main', url: 'https://github.com/tsega19/CI-CD-Pipeline-With-GitHub-Docker-and-Jenkins'
                }
            }
        }
        stage('Build Docker Image') {
            steps {  
                bat 'docker build -t tsega1907/test-dockerhub-password:%BUILD_NUMBER% .'
            }
        }
        stage('Login to Docker Hub') {
            steps {
               withCredentials([string(credentialsId: 'test-dockerhub-password', variable: 'test-dockerhub-password')]) {
                    script {
                        bat 'docker login -u tsega1907 -p $@Etu1907s'
                    }
                }
            }
        }
        stage('Push Image') {
            steps {
                bat 'docker push tsega1907/test-dockerhub-password:%BUILD_NUMBER%'
            }
        }
    }
    post {
        always {
            bat 'docker logout'
        }
    }
}
