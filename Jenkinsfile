pipeline {
    agent {
        label 'maven'
    }
environment {
    PATH = "/opt/apache-maven-3.9.8/bin:$PATH"
}
    stages {
        stage('build') {
            steps {
               sh 'mvn clean deploy'
            }
        }

        stage("SonarQube analysis") {
        environment {
            scannerHome = tool 'omar-sonar-scanner';
        }
        steps{ withSonarQubeEnv('omar-sonarqube-server') {
           sh "${scannerHome}/bin/sonar-scanner"
        }
        } 
        }
    }
}
