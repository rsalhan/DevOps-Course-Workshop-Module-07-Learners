pipeline {
    agent none

    stages {
        stage('Checkout') {
            steps {
                echo 'Building..'
            }
        }
        stage('Build the C# code') {
            steps {
                sh("dotnet build")
            }
        }
        stage('Runs the C# tests') {
            steps {
                sh("dotnet test")
            }
        }
    }
    stages {
        stage('Builds the TypeScript code - part 1.') {
            steps {
                dir('./DotnetTemplate.Web')
                sh("npm install")
            }
        }
        stage('Builds the TypeScript code - part 2.') {
            steps {
                dir('./DotnetTemplate.Web')
                sh("npm run build")
            }
        }
    }
}
