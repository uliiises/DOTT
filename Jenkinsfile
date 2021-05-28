pipeline {
    agent any
    
    tools {
    jdk 'openjdk-11'
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }        
        }
        
        /*stage('Testing') {
            steps {
                sh 'mvn test'
            }
        }*/

        stage('SonarQube') {
            environment {
                scannerHome = tool 'Sonar' 
            }
            steps {
                withSonarQubeEnv('Sonar') {
                    sh "${scannerHome}/bin/sonar-scanner"
                }          
            }
        }

    }
}
