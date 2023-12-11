@@ -1,35 +1,29 @@
pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                script {
                    git 'https://github.com/mahimakasture/pipeline.git'
                }
            }
        }
        
        stage('Build') {
            steps {
                script {
                    // Run the compilation command and capture the output
                    def buildOutput = bat(script: 'javac Main.java', returnStdout: true).trim()
                    bat(script: 'javac Main.java', returnStatus: true) // Use 'bat' on Windows

                    // Display the output
                    echo "Build Output: ${buildOutput}"
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run the test command and capture the output
                    def testOutput = bat(script: 'java Main', returnStdout: true).trim()
                    bat(script: 'java Main', returnStatus: true) // Use 'bat' on Windows

                    // Display the output
                    echo "Test Output: ${testOutput}"
                }
            }
        }
    }
    
    post {
        success {
            echo 'Build successful!'
        }
        
        failure {
            echo 'Build failed!'
        }
    }
}
