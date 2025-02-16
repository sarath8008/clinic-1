pipeline {
    agent any

    stages {
        stage('Setup EC2 Environment') {
            steps {
                sh "export JAVA_HOME=\$(dirname \$(dirname \$(readlink -f \$(which java))))"
                sh "echo 'JAVA_HOME='\"\$JAVA_HOME\" | sudo tee -a /etc/environment"
                sh "export MAVEN_HOME=/usr/share/maven"
                sh "echo 'MAVEN_HOME='\"\$MAVEN_HOME\" | sudo tee -a /etc/environment"
                sh "source /etc/environment"
                sh "echo 'JAVA_HOME='\"\$JAVA_HOME\""
                sh "echo 'MAVEN_HOME='\"\$MAVEN_HOME\""
                sh "sudo apt autoremove -y"
            }
        }

        stage('Checkout Code') {
            steps {
                echo 'Cloning the repository...'
                sh "rm -rf clinic-1"
                sh "git clone https://github.com/sarath8008/clinic-1.git"
            }
        }

        stage('Build Application') {
            steps {
                echo 'Building the application using Maven...'
                sh "cd clinic-1 && mvn clean install"
            }
        }

        stage('Run Application') {
            steps {
                echo 'Running the Spring Boot application...'
                sh "cd clinic-1 && mvn spring-boot:run"
            }
        }
    }
}
