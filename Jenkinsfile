pipeline {


    agent {
        docker {
            image 'node'
            args '-p 3000:3000'
        }
    }


    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        
        stage('Test') {
            steps {
                snykSecurity snykInstallation: 'Snyk', snykTokenId: 'ee8f389a-19df-40cd-8bff-caa44befcf25'
                sh 'npm test'
            }
        }
    }
}