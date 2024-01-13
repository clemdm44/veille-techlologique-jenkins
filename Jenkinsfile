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
              bat 'npm install'
            }
        }

        stage('Build Angular App') {
            steps {
              bat 'npm run build'
            }
        }

        stage('Test') {
            steps {
              echo 'Testing..'
              powershell 'ng test'
            }
        }

        stage('Deploy') {
            steps {
              echo 'Deploying....'
              # Ajoutez ici vos commandes de déploiement en PowerShell
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
