pipeline {
    agent any

    stages {

        stage('Manual Approval') {
            steps {
                script {
                    echo 'Proceeding with the deployment...'
                }
            }
        }
    }

    post {
        failure {
            echo 'Deployment failed'
        }
    }
}