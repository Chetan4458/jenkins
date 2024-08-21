pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    docker.build('app')
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    docker.image('app').inside {
                        sh 'npm test'  // or any other test command
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    docker.image('app').push('chetan311/app:latest')
                }
            }
        }
    }
}
