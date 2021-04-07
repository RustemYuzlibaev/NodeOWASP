pipeline {
    agent {
        docker {
            image 'node'
        }
    }


    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        
        stage('Test') {
            docker {
                image 'debian'
                args '-v /opt/jenkins/:/opt/jenkins'
            }

            steps {
                sh '/tools/io.snyk.jenkins.tools.SnykInstallation/snyk_latest/snyk-alpine --version'
                snykSecurity snykInstallation: 'Snyk', 
                snykTokenId: 'ee8f389a-19df-40cd-8bff-caa44befcf25'
            }
        }
    }
}