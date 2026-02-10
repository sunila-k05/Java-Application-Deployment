pipeline {
    agent any

    tools {
        jdk 'jdk17'
        maven 'maven3'
    }

    environment {
        SONAR_TOKEN = credentials('sonar-token')
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Sonar Analysis') {
            steps {
                sh 'mvn sonar:sonar -Dsonar.login=$SONAR_TOKEN'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t java-application-deployment .'
            }
        }
    }
}
