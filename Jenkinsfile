pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/sai-prakas/Ex-2-jenkins.git'
            }
        }
        stage('Compile Java Code') {
            steps {
                bat 'mkdir -p out'
                bat 'javac -d out src/Calculator.java'
            }
        }
        stage('Run Java Program') {
            steps {
                bat 'java -cp out Calculator'
            }
        }
    }
}
