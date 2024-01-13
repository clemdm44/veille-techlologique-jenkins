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

}
