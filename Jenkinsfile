pipeline {
    agent any

    options {
        skipDefaultCheckout() // Skip the default checkout to control repository fetching
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out repository...'
                checkout scm
            }
        }

        stage('Set up Environment') {
            steps {
                echo 'Setting up Java environment...'
                sh '''
                    export JAVA_HOME=$(dirname $(dirname $(readlink -f $(which java))))
                    echo "JAVA_HOME=$JAVA_HOME"
                '''
            }
        }
    } 
} 
