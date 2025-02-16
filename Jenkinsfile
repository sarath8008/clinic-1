pipeline {
    agent { label 'slave1' }

    stages {
        stage('checkout') {
            steps {
                sh "rm -rf clinic-1"
                sh "git clone https://github.com/sarath8008/clinic-1.git"
            }
        }

        stage('build') {
            steps {
                sh """
                    cd clinic-1
                    mvn clean package
                """
            }
        }

        stage('deploy') {
            steps {
                sh """
                    scp clinic-1/target/*.war root@172.31.16.119:/opt/apache-tomcat-11.0.3/webapps/
                """
            }
        }
    }
}
