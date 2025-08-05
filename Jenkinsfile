pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/AnandhuSajikumar/jenkins-devops-pipeline.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('flask-jenkins-demo')
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    sh 'docker run -d -p 5000:5000 flask-jenkins-demo'
                }
            }
        }
    }
}
