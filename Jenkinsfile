pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                sh "https://github.com/sarath8008/clinic-1.git"
            }
        }
        stage('Build') {
            steps {
                sh "cd clinic-1 && mvn clean package"
            }
        }
    }
}
