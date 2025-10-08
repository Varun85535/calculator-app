pipeline {
    agent any

    tools {
        maven 'Maven3' // Make sure Maven is installed in Jenkins global tools
        jdk 'JDK8'     // Make sure Java is installed in Jenkins global tools
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
    }

    post {
        success {
            echo 'Build, Test and Package Completed Successfully!'
        }
        failure {
            echo 'Build Failed!'
        }
    }
}
