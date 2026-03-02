pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('Build & Test') {
            steps {
                sh 'mvn clean install'
            }
        }
    }

    post {
        always {
            junit 'target/surefire-reports/*.xml'
        }
        success {
            echo 'Selenium Tests Passed!'
        }
        failure {
            echo 'Build or Tests Failed!'
        }
    }
}
