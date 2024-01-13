pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Check out the source code from your repository
                checkout scm
            }
        }



        stage('Build Angular App') {
            steps {
                // Build the Angular app
                sh 'npm run build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                // Commande pour exécuter les tests Angular
                sh 'ng test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                // Commandes de déploiement
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
