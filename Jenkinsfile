pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/pavankumar90554/devops-real-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-app:ci .'
            }
        }

        stage('Run Container Test') {
            steps {
                sh 'docker run -d -p 5001:5000 devops-app:ci'
            }
        }
    }
}
