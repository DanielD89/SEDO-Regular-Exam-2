pipeline {
    agent {
        label 'windows'
    }

    environment {
        DOTNET_VERSION = '8.0'
    }

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
