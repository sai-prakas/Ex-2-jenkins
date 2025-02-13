pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/sai-prakas/Ex-2-jenkins.git'
            }
        }

        stage('Compile Java Code') {
            steps {
                bat 'if not exist out mkdir out'
                bat 'javac -d out src/*.java'
            }
        }

        stage('Run Java Program') {
            steps {
                bat 'java -cp out Calculator'
            }
        }
    }

    post {
        failure {
            echo "❌ Build failed!"
        }
    }
}
