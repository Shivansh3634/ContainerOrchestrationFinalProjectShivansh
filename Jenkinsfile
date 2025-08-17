pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Shivansh3634/django-crm.git'
            }
        }

        stage('Build') {
            steps {
                sh 'python -m venv venv'
                sh './venv/bin/pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                sh './venv/bin/python manage.py test'
            }
        }

        stage('Lint') {
            steps {
                sh './venv/bin/pip install flake8'
                sh './venv/bin/flake8 .'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy step yahan configure karna hai (e.g. Docker, server push, etc.)'
            }
        }
    }
}
