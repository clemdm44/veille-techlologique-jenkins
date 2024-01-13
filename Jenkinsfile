pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building..'
                    // Commande pour installer les dépendances et compiler le projet Angular
                    sh 'npm install'
                    def buildResult = sh(script: 'ng build --prod', returnStatus: true)
                    
                    if (buildResult == 0) {
                        echo 'Build successful!'
                    } else {
                        error 'Build failed! Please check the compilation errors.'
                    }
                }
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
