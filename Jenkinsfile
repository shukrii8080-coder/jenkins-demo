
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                bat 'javac src\\Main.java'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    bat 'sonar-scanner.bat -Dsonar.projectKey=SACCO-Mobile-Banking-App -Dsonar.projectName="SACCO Mobile Banking App" -Dsonar.sources=src'
                }
            }
        }
    }
}
