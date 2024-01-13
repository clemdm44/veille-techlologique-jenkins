pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Check out the source code from your repository
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                // Use Node.js and npm installed on the Jenkins agent
                sh 'npm install'
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
                // Vous pouvez insérer ici vos commandes de déploiement
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
