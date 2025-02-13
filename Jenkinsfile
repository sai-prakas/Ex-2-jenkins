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
                script {
                    def srcDir = 'src'
                    def outDir = 'out'

                    bat "if not exist ${outDir} mkdir ${outDir}"  // Ensure 'out' directory exists
                    bat "javac -d ${outDir} ${srcDir}/*.java"  // Compile Java files
                }
            }
        }

        stage('Run Java Program') {
            steps {
                script {
                    bat "java -cp out Calculator"  // Run the Java program
                }
            }
        }
    }

    post {
        success {
            echo '🎉 Build and execution successful!'
        }
        failure {
            echo '❌ Build failed!'
        }
    }
}
