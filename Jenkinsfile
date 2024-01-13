pipeline {
    agent any
    
    environment {
        NODEJS_HOME = tool 'Node 20.11.0'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                timeout(time: 1, unit: 'MINUTES') {
                    bat "${NODEJS_HOME}\\npm install"
                }
            }
        }

        stage('Build') {
            steps {
                bat "${NODEJS_HOME}\\ng build --prod"
            }
        }

        stage('Test') {
            steps {
                bat "${NODEJS_HOME}\\ng test"
            }
        }

        stage('Deploy') {
            steps {
                // Laissez cette étape vide pour le moment
                echo 'test'
            }
        }
    }

    post {
        success {
            emailext subject: 'Build réussi',
                      body: 'La construction de l\'application Angular s\'est terminée avec succès.',
                      to: 'clement.dumoulin1@gmail.com'
        }

        failure {
            emailext subject: 'Échec de la construction',
                      body: 'La construction de l\'application Angular a échoué. Veuillez vérifier les logs pour plus d\'informations.',
                      to: 'clement.dumoulin1@gmail.com'
        }
    }
}
