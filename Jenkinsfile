pipeline {
    agent any

    stages {
        stage('Docker Login') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', 
                                                  usernameVariable: 'DOCKER_USER', 
                                                  passwordVariable: 'DOCKER_PASS')]) {
                    sh "docker login -u $DOCKER_USER -p $DOCKER_PASS"
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                sh "docker build -t shivansh3634/django-crm:latest ."
            }
        }

        stage('Push Docker Image') {
            steps {
                sh "docker push shivansh3634/django-crm:latest"
            }
        }
    }
}
