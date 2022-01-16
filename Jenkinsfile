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
    }
}