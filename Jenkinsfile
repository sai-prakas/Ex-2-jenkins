pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/sai-prakas/Ex-1.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    sh 'javac Main.java'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh 'java Main'
                }
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: '**/*.class', fingerprint: true
            }
        }
    }
}
