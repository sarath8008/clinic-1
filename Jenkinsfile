pipeline {
  agent { label 'slave1' }	
    stages {
        stage('Checkout') {             
            steps {
                sh "rm -rf clinic-1"
                sh "git clone  https://github.com/sarath8008/clinic-1.git"
		sh "cd clinic-1"
            }
        }
		    stage('Set up Environment') {
        steps {
            sh 'export export JAVA_HOME=$(dirname $(dirname $(readlink -f $(which java))))'            
	    sh 'export MAVEN_HOME=/usr/share/maven'           
        }
    }
           stage('build') {             
            steps {               
                sh "mvn clean install"
                  }
        }
	         stage('Run Application') {
            steps {
                echo 'Running Spring Boot application...'
                sh 'mvn spring-boot:run '
                 
	    }    
	}       
    }
}
    
