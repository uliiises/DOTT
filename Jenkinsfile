pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }        
        }
        
        stage('SonarQube') { /* Conect Sonarqube scanner with SonarCloud to do continuous inspection of code quality 
                                     To the conection with SonarCloud I have my sonar-project.propierties file */
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
