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
                    bat '"%SONAR_SCANNER_HOME%\\bin\\sonar-scanner.bat"'
                }
            }
        }
    }
}
