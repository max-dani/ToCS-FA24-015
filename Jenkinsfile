pipeline {
    agent any
    tools {
        // Ensure Java and Maven are installed in Jenkins
        jdk 'JDK11'
    }
    stages {
        stage('Checkout') {
            steps {
                // Clone the repository
                checkout scm
            }
        }
        stage('Build') {
            steps {
                // Compile the Java program
                sh 'javac SquareCalculator.java'
            }
        }
        stage('Test') {
            steps {
                // Execute the program and print results
                sh 'java SquareCalculator'
            }
        }
        stage('Archive') {
            steps {
                // Archive the compiled Java class file
                archiveArtifacts artifacts: '*.class', fingerprint: true
            }
        }
    }
    post {
        always {
            // Clean up the workspace after the build
            cleanWs()
        }
    }
}
