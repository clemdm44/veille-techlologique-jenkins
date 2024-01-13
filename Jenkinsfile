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
            bat 'node -v'
          }
      }
        stage('Build') {
            steps {
                // Les étapes de construction ici
            }
        }

        stage('Test') {
            steps {
                // Les étapes de test ici
            }
        }

        stage('Deploy') {
            steps {
                // Les étapes de déploiement ici
            }
        }
    }
}
