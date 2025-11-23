pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    environment {
        VERSION = '1.0.0'
    }

    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run tests stage')
    }

    stages {
        stage('Build') {
            steps {
                echo "Building version ${VERSION}.."
                bat 'mvn -version'
            }
        }
        stage('Test') {
            when {
                expression { params.executeTests == true }
            }
            steps {
                echo 'Testing with conditions..'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying version ${VERSION}.."
            }
        }
    }

    post {
        always {
            echo 'Pipeline Completed'
        }
    }
}
