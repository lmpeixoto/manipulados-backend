pipeline {
    agent {
        docker {
            image 'node:alpine'
            args '-p 5000:5000'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'yarn install'
            }
        }
        stage('SonarQube analysis') {
            environment {
                scannerHome = tool 'SonarQube_4.3.0'
            }
            steps {
                withSonarQubeEnv('Your Sonar Server Name here') {
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
    }
    }
    }
}
