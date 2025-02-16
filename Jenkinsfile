pipeline {
    agent agent {label 'slave1"}
    stages {
        stage('Checkout') {
            steps {
                sh git clone "https://github.com/sarath8008/clinic-1.git"
            }
        }
        stage('Build') {
            steps {
                sh "cd clinic-1 && mvn clean package"
            }
        }
    }
}
