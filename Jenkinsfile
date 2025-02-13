pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    checkout scmGit(branches: [[name: 'main']],
                        userRemoteConfigs: [[url: 'https://github.com/sai-prakas/Ex-2-jenkins.git']])
                }
            }
        }

        stage('Compile Java Code') {
            steps {
                script {
                    sh 'mkdir -p out'
                    sh 'javac -d out src/*.java'
                }
            }
        }

        stage('Run Java Program') {
            steps {
                script {
                    sh 'java -cp out Calculator'
                }
            }
        }
    }

    post {
        failure {
            echo "❌ Build failed!"
        }
        success {
            echo "✅ Build successful!"
        }
    }
}
