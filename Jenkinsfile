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
            steps {
                script {
                    def scannerHome = tool 'sonarscan';
                    withSonarQubeEnv('sonarqube') {
                        sh "${tool("sonarscan ")}/bin/sonar-scanner -Dsonar.projectKey=reactapp -Dsonar.projectName=reactapp"
                    }
                }
      }
    }
    }
}
