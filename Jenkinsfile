pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Shivansh3634/ContainerOrchestrationFinalProjectShivansh.git'
            }
        }

        stage('Build Docker') {
            steps {
                bat 'docker build -t shivansh3634/django-crm:latest "C:\\Users\\shiva\\OneDrive\\Desktop\\Container and orchestration final project\\django-crm"'
            }
        }

        stage('Push Docker') {
            steps {
                bat 'docker login -u <your-dockerhub-username> -p <your-dockerhub-password>'
                bat 'docker push shivansh3634/django-crm:latest'
            }
        }
    }
}
