pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
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
                echo 'Deploying..'
            }
        }
    }

    post {
        always {
            echo 'Pipeline Completed'
        }
    }
}
