pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/sai-prakas/Ex-2-jenkins.git'
            }
        }

        stage('Compile Java Code') {
            steps {
                bat '''
                    if not exist out mkdir out
                    javac -d out src\\*.java
                '''
            }
        }

        stage('Run Java Program') {
            steps {
                bat 'java -cp out Main'
            }
        }
    }

    post {
        success {
            echo '✅ Build and Execution Successful!'
        }
        failure {
            echo '❌ Build failed!'
        }
    }
}
