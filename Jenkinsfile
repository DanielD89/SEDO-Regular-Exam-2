pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Restore the project') {
            steps {
                powershell 'dotnet restore'
            }
        }
        stage('Build the project') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Test the project') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
