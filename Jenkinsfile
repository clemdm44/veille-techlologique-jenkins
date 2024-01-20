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
                error 'Build failed. Could not find stylesheet file app.component.css linked from the template.'
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
                      to: 'clement.dumoulin2021@campus-eni.fr'
        }

        failure {
            emailext subject: 'Build failed',
                      body: 'La construction de l\'application Angular a échoué. Veuillez vérifier les logs pour plus d\'informations.',
                      to: 'clement.dumoulin2021@campus-eni.fr'
        }
    }
}
