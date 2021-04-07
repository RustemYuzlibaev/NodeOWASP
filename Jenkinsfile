pipeline {
    agent {
        docker {
            image 'node'
            args '-v /opt/jenkins/:/opt/jenkins'
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
                sh '/opt/jenkins/tools/io.snyk.jenkins.tools.SnykInstallation/snyk_latest/snyk-alpine --version'
                snykSecurity snykInstallation: 'Snyk', 
                snykTokenId: 'ee8f389a-19df-40cd-8bff-caa44befcf25'
            }
        }
    }
}