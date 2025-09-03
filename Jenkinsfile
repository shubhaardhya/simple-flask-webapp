pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/YOUR_USERNAME/simple-flask-webapp.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t simple-flask-webapp .'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker rm -f simple-flask-web-container || true'
                sh 'docker run -d -p 5000:5000 --name simple-flask-web-container simple-flask-webapp'
            }
        }
    }
}

