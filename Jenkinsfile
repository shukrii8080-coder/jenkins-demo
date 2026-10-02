
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
                    script {
                        def scannerHome = tool 'SonarScanner'

                        bat "\"${scannerHome}\\bin\\sonar-scanner.bat\" -Dsonar.projectKey=SACCO-Mobile-Banking-App -Dsonar.projectName=\"SACCO Mobile Banking App\" -Dsonar.sources=src"
                    }
                }
            }
        }
    }
}
