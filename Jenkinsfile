pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    checkout scm
                }
            }
        }

        stage('Compile Java Code') {
            steps {
                script {
                    sh 'mkdir -p out'
                    sh 'javac -d out src/*.java'  // Ensure Java files exist in src/
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
