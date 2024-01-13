pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
              tool 'Node 20.11.0'                
              bat 'npm install -Verbose'
            }
        }

        stage('Build Angular App') {
            steps {
              bat 'npm run build -Verbose'
            }
        }

        stage('Test') {
            steps {
              echo 'Testing..'
            }
        }

        stage('Deploy') {
            steps {
              echo 'Deploying....'
            }
        }
    }

    post {
        failure {
          script {
            echo 'La pipeline a échoué'
          }
        }
    }
}
