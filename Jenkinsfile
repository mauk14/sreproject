pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from your GitHub repository
                // git 'https://github.com/alibekkenny/heroku_test.git'
                git branch: "main", url: 'https://github.com/mauk14/sreproject.git'
            }
        }

        stage('Run Project') {
            steps {
                // Run your Node.js project
                sh 'nohup sudo /home/ec2-user/sreproject/sreproject'
            }
        }
    }

    post {
        success {
            // Actions to perform when the pipeline succeeds
            echo 'Golang project successfully started.'
        }
        failure {
            // Actions to perform when the pipeline fails
            echo 'Failed to start Golang project. Notify the team or take corrective actions.'
        }
    }
}