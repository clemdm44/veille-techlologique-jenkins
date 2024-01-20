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
                echo 'test'
            }
        }

        stage('Build') {
            steps {
                echo 'test'
                error 'Le build de l'application a échoué.'
            }
        }

        stage('Test') {
            steps {
                echo 'test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'test'
            }
        }
    }

    post {
        success {
            emailext subject: 'Build réussi',
                      body: 'La construction de l\'application Angular s\'est terminée avec succès.',
                      to: 'clement.dumoulin2021campus-eni.fr' 
        }

        failure {
            emailext subject: 'Échec de la construction',
                      body: 'La construction de l\'application Angular a échoué. Veuillez vérifier les logs pour plus d\'informations.',
                      to: 'clement.dumoulin2021campus-eni.fr'
        }
    }
}
