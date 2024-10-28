pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    docker.build('my-app-image')
                }
            }
        }
        stage('Test') {
            steps  docker.image('my-app-image').inside {
                sh 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker push my-app-image'
            }
