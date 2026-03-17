pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/drhudson1/java-devops-lab2.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Unit Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Code Coverage') {
            steps {
                bat 'mvn jacoco:report'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package'
            }
        }

    }

    post {

        always {
            junit '**/target/surefire-reports/*.xml'
        }

    }

}
