pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
            
            stage('SonarQube Scanner') {
            steps {
                
                enviroment {
                    scannerHome= tool 'Sonar'
                }
                steps{
                    withSonarQubeEnv('Sonar'){
                        sh "${scannerHome}/bin/sonar-scanner"
                    }
                }
            }
        }
    }
    }
    
}
