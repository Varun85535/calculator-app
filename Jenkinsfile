pipeline {
    agent any

    tools {
        jdk 'JDK17'      // Your JDK name in Jenkins
        maven 'MAVEN3'   // Your Maven name in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Varun85535/calculator-app.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Run App') {
            steps {
                bat 'java -cp target/calculator-app-1.0-SNAPSHOT.jar com.example.App'
            }
        }
    }

    post {
        success {
            echo 'Build, Test and App Run Completed Successfully!'
        }
        failure {
            echo 'Something Failed!'
        }
    }
}
