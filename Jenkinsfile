pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Shivansh3634/ContainerOrchestrationFinalProjectShivansh.git'
            }
        }

        stage('Build') {
            steps {
                bat 'python -m venv venv'
                bat 'venv\\Scripts\\pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                bat 'venv\\Scripts\\python manage.py test'
            }
        }

        stage('Lint') {
            steps {
                bat 'venv\\Scripts\\pip install flake8'
                bat 'venv\\Scripts\\flake8 .'
            }
        }
    }
}
