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
                sh 'mkdir -p out && javac -d out src/*.java'
            }
        }

        stage('Run Java Program') {
            steps {
                sh 'java -cp out Calculator < input.txt'
            }
        }
    }

    post {
        success {
            echo '✅ Build successful!'
        }
        failure {
            echo '❌ Build failed!'
        }
    }
}
